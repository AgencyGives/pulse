An operator is left associative if the operations are performed from the left to the right in an expression. Similarly, an operator is right associative if the operations are performed from the right to the left in an expression. For example, addition is left associative and in the expression 1 + 2 + 3 the numbers 1 and 2 are added first, after which 3 is added. Note that for the addition of numbers the associativity of + does not matter as the terms can be reordered in a formal system. However, limited numeric precision in a computer restricts this reordering and an overflow may occur when the terms are reordered. Also, if the terms are functions with side effects[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#sideeffect) the result would be different after reordering. Arithmetic operators in a programming language are typically left associative with the notable [[exception]] of exponentiation (^) which is right associative. However, this rule of thumb is not universal.

Associativity can be captured in a grammar. For a left associative binary operator op we have a [[production]] of the form

<_expr_> -> <_term_> | <_expr_> op <_term_>

and for a right associative operator <op> we have a [[production]] of the form

<_expr_> -> <_term_> | <_term_> op <_expr_>

Note that the [[production]] for a left associative operator is left recursive[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#production) and therefore has to be rewritten for a [[recursive descent parser]]:

<_expr_> -> <_term_> <_more_terms_>

<_more_terms_> -> op <_term_> <_more_terms_> | e