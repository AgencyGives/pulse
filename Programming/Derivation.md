**Program derivation** is the derivation of a program from its specification, by mathematical means.

-   From a grammar we can derive _strings_ (= sequences of tokens/terminals)
-   In each _derivation step_ a nonterminal is replaced by a right-hand side (part after ->) of a production for that nonterminal
-   Each representation after each step is called a _sentential form_
-   When the nonterminal on the far right (left) in a sentential form is replaced in each derivation step the derivation is called _right-most (left-most)_
-   The final form consists of terminals only and is called the _yield_ of the derivation
-   A context-free grammar is a _generator_ of a _context-free language_: the language defined by the grammar is the set of all strings that can be derived

Example derivation (right-most)

<_expression_>
  => <_expression_> <_operator_> <_expression_>
  => <_expression_> <_operator_> identifier
  => <_expression_> + identifier
  => <_expression_> <_operator_> <_expression_> + identifier
  => <_expression_> <_operator_> identifier + identifier
  => <_expression_> * identifier + identifier
  => identifier * identifier + identifier

To _derive_ a program means to write a formal specification, which is usually non-executable, and then apply mathematically correct rules in order to obtain an executable program satisfying that specification. The program thus obtained is then correct by construction. Program and [correctness](https://en.wikipedia.org/wiki/Correctness_(computer_science) "Correctness (computer science)") proof are constructed together.

The approach usually taken in [formal verification](https://en.wikipedia.org/wiki/Formal_verification "Formal verification") is to first write a program, and then provide a [proof](https://en.wikipedia.org/wiki/Mathematical_proof "Mathematical proof") that it conforms to a given [specification](https://en.wikipedia.org/wiki/Program_specification "Program specification"). The main problems with this are that

-   the resulting proof is often long and cumbersome;
-   no insight is given as to how the program was developed; it appears "like a rabbit out of a hat";
-   should the program happen to be incorrect in some subtle way, the attempt to verify it is likely to be long and certain to be fruitless.

Program derivation tries to remedy these shortcomings by

-   keeping proofs shorter, by development of appropriate mathematical notations;
-   making design decisions through formal manipulation of the specification.

Terms that are roughly synonymous with program derivation are: transformational programming, algorithmics, deductive programming.

