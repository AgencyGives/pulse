A problem with the if-then-else grammar for Pascal and C is the formulation of unambiguous grammar productions for if-then-else. The grammar below is ambiguous

<_stmt_> -> if <_expr_> then <_stmt_>
        | if <_expr_> then <_stmt_> else <_stmt_>

because we find two distinct derivations of the string

if C1 then if C2 then S1 else S2

(where C1 and C2 are some expressions, S1 and S2 are some statements):

<_stmt_>
  => if <_expr_> then <_stmt_>
  => if <_expr_> then if <_expr_> then <_stmt_> else <_stmt_>

and another [[derivation]]

<_stmt_>
  => if <_expr_> then <_stmt_> else <_stmt_>
  => if <_expr_> then if <_expr_> then <_stmt_> else <_stmt_>

An anuambiguous grammar for if-then-else is (you don't need to memorize this):

<_stmt_> -> <_balanced_stmt_>
        | <_unbalanced_stmt_>

<_balanced_stmt_> -> if <_expr_> then <_balanced_stmt_> else <_balanced_stmt_>
                 | <_other_stmt_>

<_unbalanced_stmt_> -> if <_expr_> then
                   | if <_expr_> then <_balanced_stmt_> else <_unbalanced_stmt_>

which is an [[LR grammar]][![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#lrgrammar), but not an [[LL grammar]][![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#llgrammar) and no pure [[top-down parser]][![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#topdownparser) can be used to parse program fragments with the unambiguous if-then-else grammar.