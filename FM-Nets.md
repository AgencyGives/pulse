##   FM-Net: a massively parallel, low-level machine language

[![](https://raw.githubusercontent.com/moonad/Assets/master/images/inet-simulation.gif)](https://raw.githubusercontent.com/moonad/Assets/master/images/inet-simulation.gif)

_Interaction Net (inet) simulation_

Formality terms are compiled to a memory-efficient interaction net system called FM-Net. Interaction nets are graphs where nodes have labeled ports, one being the main one, plus a list of "rewrite rules" that are activated whenever two nodes are connected by their main ports. A simple interaction-net graph-rewrite system called "interaction combinators" with only 3 symbols and 6 rules was shown to be a universal model of [computation][2]. As a universal mode, interaction-nets combine many useful properties of other models such as Turing machines and the lambda calculus. Like Turing machines, interactions-nets can be evaluated as a series of atomic, local operations with a clear physical implementation. Like the lambda calculus, interaction-nets are inherently parallel, but in a more robust manner, admitting desirable computational properties such as strong confluence, optimal sharing and zero-cost garbage-collection.

We use a slightly modified version of interaction combinators, called FM-Net as our lowest-level machine language, extending interaction combinators with additional graph node types for efficient numeric operations. Our implementation has advantages over previous interaction net graph-reduction systems (such as the Bologna Optimal Higher-order Machine) in that it requires no book-keeping, requires only 128 bits per lambda or pair, has unboxed 32-bit integers and constant-time beta reduction. This is possible due to Formality's stratification, a structural discipline on how terms are duplicated, inherited from its underlying logic, Elementary Affine.

### [](https://github.com/Soonad/Whitepaper#node-types)Node Types

Our FM-Net system includes 6 types of nodes, ERA, CON, OP1, OP2, ITE, NUM.

[![](https://raw.githubusercontent.com/moonad/Assets/master/images/fm-net-node-types.png)](https://raw.githubusercontent.com/moonad/Assets/master/images/fm-net-node-types.png)

-   `CON` has 3 ports and an integer label. It is used to represent lambdas, applications, boxes (implicitly) and duplications. Just `CON` is enough for beta-reduction.
    
-   `ERA` has 1 port and is used to free empty memory, which happens when a function that doesn't use its bound variable is applied to an argument.
    
-   `NUM` has 1 port and stores an integer and is used to represent native numbers.
    
-   `OP1` has 2 ports and stores one integer and an operation id. `OP2` has 3 ports and an operation id. They are used for numeric operations such as addition and multiplication.
    
-   `ITE` has 3 ports and an integer label. It is used for if-then-else, and is required to enable number-based branching.
    

Note that the position of the port matters. The port on top is called the `main` port. The first port counter-clockwise to the main port (i.e., to the left on this drawing) is the `aux0` port, and the first port clockwise to the main port (i.e., to the right on this drawing) is the `aux1` port.

### [](https://github.com/Soonad/Whitepaper#rewrite-rules)Rewrite rules

In order to perform computations, FM-Net has a set of rewrite rules that are triggered whenever two nodes are connected by their main ports. This is an extensive list of those rules:

[![](https://raw.githubusercontent.com/moonad/Assets/master/images/fm-net-rewrite-rules.png)](https://raw.githubusercontent.com/moonad/Assets/master/images/fm-net-rewrite-rules.png)

Note that, while there are many rules (since we need to know what to do on each combination of a node), most of those have the same "shape" (such as OP2-OP2, ITE-ITE), so they can reuse the same code. There are only 5 actually relevant rules:

-   **Erasure**: When an `ERA` or a `NUM` node collides with anything, it "destroys" the other node, and propagates itself to destroy all nodes connected to it.
    
-   **Substitution**: When two `CON` nodes of equal label collide, and also on the `OP2-OP2` / `ITE-ITE` cases, both nodes are destroyed, and their neighbors are connected. That's the rule that performs beta-reduction because it allows connecting the body of a lambda (which is represented with `CON`) to the argument of an application (which is, too, represented with `CON`). Note that on the OP2-OP2 and ITE-ITE cases, that's just a default rule that doesn't matter, since those cases can't happen on valid Formality programs.
    
-   **Duplication**: When different nodes collide, they "pass through" each other, duplicating themselves in the process. This allows, for example, `CON` nodes with a label `>1` to be used to perform deep copies of any term, with `dup x = val; ...`. It can copy lambdas and applications because they are represented with `CON` nodes with a label `0`, pairs and pair-accessors, because they are represented with `CON` nodes with a label `1`, and `ITE`, `OP1`, `OP2`, because they are different nodes.
    
    It also allows duplications to duplicate terms that are partially duplicated (i.e., which must duplicate, say, a λ-bound variable), as long as the `CON` labels are different, otherwise, the `CON` nodes would instead fall in the substitution case, destroying each other and connecting neighbors, which isn't correct. That's why FMC's box system is necessary: to prevent concurrent duplication processes to interfere with each other by ensuring that, whenever you duplicate a term with `dup x = val; ...`, all the duplication `CON` nodes of `val` will have a labels higher than the one used by that `dup`.
    
-   **If-Then-Else** When an `ITE` node collides with a `NUM` node, it becomes a `CON` node with one of its ports connected to an `ERA` node. That's because then/else branches are actually stored in a pair, and this allows you to select either the `fst` or the `snd` value of that pair and discard the other branch.
    
-   **Num-Operation** When `OP2` collides with a `NUM`, it becomes an `OP1` node and stores the number inside it; i.e., the binary operation becomes a unary operation with `NUM` partially applied. When that `OP1` collides with another `NUM`, then it performs the binary operation on both operands, and return a new `NUM` with the result. Those rules allow us to add, multiply, divide and so on native numbers.
    

### [](https://github.com/Soonad/Whitepaper#compiling-formality-terms-to-fm-net)Compiling Formality terms to FM-Net

The process of compiling Formality terms to FM-Net can be defined by the following function `k_b(net)`:

[![](https://raw.githubusercontent.com/moonad/Assets/master/images/fm-net-compilation.png)](https://raw.githubusercontent.com/moonad/Assets/master/images/fm-net-compilation.png)

This function recursively walks through a term, creating nodes and "temporary variables" (`x_b`) in the process. It also keeps track of the number of boxes it passed through, `b`. For example, on the lambda (`{x}f`) case, the procedure creates a `CON` node with a label `0`, creates a "temporary variable" `x_b` on the `aux0` port, recurses towards the body of the function, `f` on the `aux1` port, and then returns the `main` port (because there is a black ball on it). Notice that there isn't a case for `VAR`. That's what those "temporary variables" are for. On the `VAR` case, two things can happen:

1.  If the corresponding "temporary variable" `x_b` was never used, simply return a pointer to it.
    
2.  If the corresponding "temporary variable" `x_b` was used, create a "CON" node with a label `2 + b`, connect its main port to the old location of `x_b`, its `aux0` to the port `x_b` pointed to, and return a pointer to its `aux1` port.
    

This process allows us to create as many `CON` nodes as needed to duplicate `dup`-bound variables, and labels those nodes with the layer of that `dup` (plus 2, since labels 0 and 1 are used for lambdas/applications and pairs/projections). Note that this process is capable of duplicating λ-bound variables, but this isn't safe in practice, and won't happen in well-typed inputs.

### [](https://github.com/Soonad/Whitepaper#implementation)