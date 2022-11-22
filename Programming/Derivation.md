**Program derivation** is the derivation of a program from its specification, by mathematical means.

To _derive_ a program means to write a formal specification, which is usually non-executable, and then apply mathematically correct rules in order to obtain an executable program satisfying that specification. The program thus obtained is then correct by construction. Program and [correctness](https://en.wikipedia.org/wiki/Correctness_(computer_science) "Correctness (computer science)") proof are constructed together.

The approach usually taken in [formal verification](https://en.wikipedia.org/wiki/Formal_verification "Formal verification") is to first write a program, and then provide a [proof](https://en.wikipedia.org/wiki/Mathematical_proof "Mathematical proof") that it conforms to a given [specification](https://en.wikipedia.org/wiki/Program_specification "Program specification"). The main problems with this are that

-   the resulting proof is often long and cumbersome;
-   no insight is given as to how the program was developed; it appears "like a rabbit out of a hat";
-   should the program happen to be incorrect in some subtle way, the attempt to verify it is likely to be long and certain to be fruitless.

Program derivation tries to remedy these shortcomings by

-   keeping proofs shorter, by development of appropriate mathematical notations;
-   making design decisions through formal manipulation of the specification.

Terms that are roughly synonymous with program derivation are: transformational programming, algorithmics, deductive programming.