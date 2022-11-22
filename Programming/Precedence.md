The precedence of an operator indicates the priority of applying the operator relative to other operators. For example, multiplication has a higher precedence than addition, so a+b*c is evaluated by multiplying b and c first, after which a is added. That is, multiplication groups more tightly compared to addition. The rules of operator precedence vary from one programming language to another.

The relative precedences between operators can be captured in a grammar. A nonterminal is introduced for every group of operators with identical precedence. The nonterminal of the group of operators with lowest precedence is the nonterminal for the expression as a whole. Productions for (left [[associative]]) binary operators with lowest to highest precedences are written of the form

<_expr_> -> <_expr1_> | <_expr_> <_lowest_op_> <_expr1_>

<_expr1_> -> <_expr2_> | <_expr1_> <_one_but_lowest_op_> <_expr2_>

...

<_expr9_> -> <_term_> | <_expr9_> <_highest_op_> <_term_>

<_term_> -> identifier | number | - <_term_> | ( <_expr_> )

where <_lowest_op_> is a nonterminal denoting all operators with the same lowest precedence, etc.