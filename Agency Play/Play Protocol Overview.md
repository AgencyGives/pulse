### Play Protocol as a Computational Paradigm
The **Play Protocol** employs a **doxatic modal logic** of **Common Ground**. Built on a distributed purely functional runtime that is **lazy, non-garbage-collected massively parrallel** and **beta-optimal.** It is built on a new model of computation, the **Interaction Net** which supersedes the **Turing Machine** and the **Lambda Calculus**. 

The Protocol makes extensive use of λ-encoding for the representation of data-types as pure functions. Until the HVM, because of efficiency issues they have never been seriously considered for practical purposes.

Advantages of λ-encoding over other representations are:
1) that its operations can be typed in a type system of pure functions,
2) that it impliments primitive recursion on a data type simultaneously with the construction of data items, and
3) that it is a natural representation for partial evaluation and theorem proving.

By abusing beta-optimality of the Higher-Order Virtual Machine (HVM), we're able to turn some exponential-time algorithms into linear-time ones. *In general HVM is capable of applying any fusible function `2^n` times in linear time, which sounds impossible, but is indeed true.*

Thanks to beta-optimality, **the runtime itself is capable of deforesting!**

Additionally, Interaction Net adaptation of the cut-elimination theoreom for multiplicative linear logic correspond to the strong normalization property (every proof term reduces in a finite number of steps into a normal form). *There are derivations that could be completed in a a couple lines using cut, but whose analytic proof could not be completed in the lifespan of the universe.* [This is true for proof systems based on higher-order typed lambda calclus]

The Protocol architecture exemplies the following features:
- **Propositions as Types**: for each proposition in the logic there is a corresponding type in the programming language— and vice versa.
- **Proofs as Programs**: for each proof of a given proposition, there is a program of the corresponding type—and vice versa.
- **Simplification Proofs as evalutation of programs**: for each way to simplify a proof there is a corresponding way to evaluate a program—and vice versa. **Thanks to Interaction Nets**
- **Intuitionistic Type Theory**
- **Curry-Howard-Lambek isomorphism**: a three way isomorphism between types (in programming languages), propositions (in logic) and objects of a Cartesian closed category.

## Agents
Each **Agent** is a **Higher-Order Virtual Machine** with a local **Belief Base** a **Function Factory** and store of **Functions**.

The **Belief Base** consist among other Beliefs: **Beliefs about what is passed into a Function.**

**Functions** emit **φ** (**Propositions**).
- The identity of the Agent/Function is its own hash. 
- φ's type is the hash of the Agent/Function that produced it.

The Function emits possible propositions, the agent can then Accept/Believe the possible proposition.

Belief in the Proposition captures the state of inputs and the output as a routing table.

Proposition emittied are of the type of the hash of the function method
The Belief of the Proposition  is from the agent that Believes
and it is this Believer that has the routing table
So if i want to find out what made up the proposition emitted by the factory,
I would go to the agent that believes that proposition consult the routing table, and find what constituted that proposition.

Backwards propogation of claim, forwards propogation of plausability, and storage  by agent that Believed the claim.

If the agent's Belief was made with the expectation of future access, those giving access (mega-party) could base it not just on your belief but on network-plausability, and the difference between network plausability and your claim.

You may say "I did 500 pies" it routes backwards and their is a maximum claim possible.

the spread between max poss and claim can limit access... aka dont lie too much about what u did or i wont give u access.

## Functions (Spaces)
Every Function contains **Input Variables** and returns **Propositions**.

The the propositions being inputted determines the nature of the proposition according to a **method**.

The Belief of an Agent in its access to a proposition  as input variable essentially gives the function the permission to negate the proposition and emit a new proposition if I Believe the output.

The Function's ouput is always based on what the agent believes the inputs are...

- The output proposition will contain also negations and or replacements of other propositions.
	- Output Example: Bf(ψ ∧ ¬φ)
	- Propositions can include *the negation of the Inputs of the Factory*, the indication of Positive and Negative Externalities, as well as the transformation of the world.
- The **method**: can be dependant on input propositions, the possibility / impossibility of access to updating propositions.

#### Routing
Every Proposition returned by a function with the propositions that were inputed as variables are stored in an agent's **routing table**.

Each entry in the **routing table** is then a snapshot of a moment in which agent(s) believe a proposition as actual and everything about it's creation to be possible. This momentary point of view is captured in the routing table.

Any agent concerned with accessing information about the components that made up a proposition consults the routing table.

Any returned proposition is routed to the producer of the propositions that were inputted in the functions variables.

Any proposition about a proposition is also routed in this way, this is a form of backwards propogation.

Derivative Propositions (Propositions on Propositions) can be propagated forwards/backwards for example concerning **plausability**.

### **Accessibility**
An Agent can hold Beliefs about the **Accessibility Relation** between a  **φ** and a **Function's  input variables**.

Expiremental: ***Accessibility Relations can also define a cap/vest***

An Access Relation is thus also a qualitative and quantitative mapping, by relating a proposition to a variable in a function, a claim is being made that the proposition and the variable are identical.

An Agent **Believing the access relation** from  **φ**  to a **Factory's Input Variable**, means they ***implicitly*** ***Accept** the Factories' returned **ψ** about  **φ**.
- *Note that acceptance of a proposition is the basis of routing, to accept is to propagate.*

*Acceptance is not the same as Belief, and Acceptance can rely on Plausability.*

### Plausability
The agent's reasoning over its Belief Base will allow it to determine how **Plausible** the Proposition **ψ*** is based on the Agent's Beliefs about the current state of the world and all accessibility relations.

The agent emits a Belief about the **Plausability** of **ψ***, which can be useful information for agents to determine ***whether they Believe a Proposition***.

*For example, an Agent can choose to suspend Believing or not Believing a Proposition and Accept it while deliberately deffering resolution until the Proposition is Plausable enough.*
- Backwards and forwards propation of Propositions and Plausability facilitated through routing tables helps agents decide what to Believe.

*Plausability are expressed in a **Trinary Fuzzy Logic** as a scale of knowness [-1,0,1]:
- from -1 to 0 to 1, True (known), Unknown, False (known)

##### Beliefs
B(φ about functionvarRφ)
B(Possible)
B(Impossible) // false
B(Contingent)
B(Necessary)
B(Analyticity)
B(Realized) // true

**// This is a form of simple Propositional Accounting**
For example "apples" may be a possibility of a farm, access to the apples can be given to a baker.

The baker arrives at the farm to bake a pie.

When the baker store says it produced a pie with apples from the farm, the farm having given access to its apples to the baker accepts the implication that 5 apples have been turned into a pie.

-5 apples -> +1 pie

Agents might different views about what you have access to and thus different ideas of Plausability of certain Claims to the Realization of Propositions

*Consequently a factory as well as what is produced is what you believe it is...*

## Belief Base

**Categorical Belief**
Statement: φ.type → B<sub>a</sub>φ 
If a φ of a certain **type** is discovered agent<sub>a</sub> believes those φs.
- Since the type of a proposition is the hash of thr Agent/Factory that produced it, to trust the result

**Belief about Access**

**Nested Modalities**: Agents can **Accept** and/or **Believe** **φ** or **φs about other φs**
Statement: B<sub>a</sub>B<sub>i</sub>φ → B<sub>a</sub>φ 
If agent<sub>a</sub> believes that agent<sub>i</sub> believes that **φ**, then agent<sub>a</sub> also believes this.

**Nested Modality with Category**
Statement: B<sub>a</sub>B<sub>i</sub>φ.type → B<sub>a</sub>φ 
If agent<sub>a</sub> believes that agent<sub>i</sub> believes **φs** of a certain **type** , then agent<sub>a</sub> also believes those φs .

/* Unknown whether possible... perhaps it is*
**Category with Nested Modality**
Statement: φ.type related to  B<sub>a</sub>B<sub>i</sub> → B<sub>a</sub>φ
If a φ of a certain **type** is discovered agent<sub>a</sub> believes it.
agent<sub>a</sub> believes **φ** of a certain **type** if agent<sub>a</sub> believes agent<sub>i</sub> believes a **φ**, then agent<sub>a</sub> also believes this.

## Distributed Zero-Knowledge Common Ground Sync
Alice and Bob both have local a graph of higher order functions that return into other functions.

Alice takes the hash of a **function** and the **surrounding context** according to a **depth**.
Example of context: **func** with a +/- depth of 2
(func - func - **func** -func -func)
(hash - hash - **hash** - hash - hash)

Alice sends this **hash-structure** to Bob's Graph-Scanner

Bob Graph-Scanner looks for functions on its own graph whose hashes match those provided by Alice.

However, because multiple functions can have the same hash (a hash colliision) Alice decides to send test-proposition to Bob to destructure across input variables into the **function-structure** corresponding to the **hash-structure**, if the outputted value is the same as that viewed by Alice when she performs the same test, then they know to be:
1) Operating with the same structure and functions
2) Are completely in-sync about relevent propositions that might change function output.
	1) This includes the Propositions of other Agents, including personal Beleifs, that may have effected calculation.

**But what if the output propositions are different?**

Beleif Acceptance and Access Conditions

Access Conditions based on a Proposition being Beleived or Accepted by a set of Agents.

Proposition -> I say i planted a tree

and I want Access to the Tree Planting Party

Access conditions require beleif or acceptance by a stet of agents


## **Known Propositions about a Context**
Looking for a Set of Agents within a Context's Known Propositions

Each agent is a world.

## Interaction Combinators
A simple interaction-net graph-rewrite system called "interaction combinators" with only 3 symbols and 6 rules was shown to be a universal model of [computation][2].




If something is a tautology the agent Believes it.


## **From Common Ground to Action**
The syntax of propositional dynamic logic contains a language of _propositions_ (like "the ground is dry") and a language of _actions_ (like "it rains").


## **Temporal Logic**
*Until:* in the context of temporal logic, to express things like "A will be true at some point in the future and, until then, B is true" (until(A,B))

***Until*** makes temporal logic very expressive. In fact, on time flows isomorphic to the natural numbers, temporal logic with *until* and its mirror image **since** is as expressive as first-order logic, a result that has become known as Kamp's Theorem.

**Propositional Dynamic Logic**
A modal logic with infinitely many modalities (or, 'programs'), that form an algeba generated by atomic programs and formula tests using the operations of **composition, union and reflexive transitive closure**, familiar from regular expressions.