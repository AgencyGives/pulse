Backus-Naur Form (BNF) is a form of context-free grammar frequently used to describe a programming language syntax.

-   BNF grammar productions are of the form
  
<_nonterminal_> -> sequence of (non)[[terminals]]  
and give a description of the syntax for the nonterminal-   A terminal[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#terminal)of a grammar is a token[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#token) e.g. specific programming language keyword or identifier
-   A <_nonterminal_>[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#nonterminal)denotes a  syntactic category, e.g. a collection of program statements.
  
For example, an assignment statement  
<_stmt_> -> <_id_> := <_expr_>-   The symbol | (bar) denotes alternative forms in a [[production]], e.g. different program statements are catagorized.
  
For example:  
<_stmt_> -> **return** | **break** | <_id_> := <_expression_>-   The special symbol e denotes empty, and is often used in optional constructs.
  
For example:  
<_optional_static_> -> **static** | e

-   Extended BNF includes an explicit form for optional constructs with [ and ].
  
For example:  
<_stmt_> -> **for** <_id_> := <_expr_> **to** <_expr_> [ **step** <_expr_> ] **do** <_stmt_>-   Extended BNF includes a repetition construct * (star).
  
For example:  
<_decl_> -> **int** <_id_> (, <_id_>)*