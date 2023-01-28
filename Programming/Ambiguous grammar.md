A grammar is ambiguous if a string exists that has more than one distinct [[derivation]] resulting in distinct parse trees. See also [[ambiguous if-then-else]][![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#ambiguousifthenelse).

# Ambiguous Grammars

-   When more than one distinct derivation of a string exists resulting in distinct parse trees, the grammar is _ambiguous_ (as is the case above)
-   A programming language construct should have only one parse tree to avoid misinterpretation by a compiler
-   For expression grammars,  [[Associative]]] and [[Precedence]] of operators need to be included somehow

The grammar for simple expressions below is ambiguous:

<expression> -> identifier
              | unsigned_integer
              | - <expression>
              | ( <expression> )
              | <expression> <operator> <expression>

<operator> -> + | - | * | /

because we find two distinct (left-most) derivations for the string a-b+1:

<_expression_>
  => <_expression_> <_operator_> <_expression_>
  => <_expression_> <_operator_> <_expression_> <_operator_> <_expression_>
  => identifier <_operator_> <_expression_> <_operator_> <_expression_>
  => identifier - <_expression_> <_operator_> <_expression_>
  => identifier - identifier <_operator_> <_expression_>
  => identifier - identifier + <_expression_>
  => identifier - identifier + unsigned_integer
        (a)     -    (b)     +       (1)

and

<_expression_>
  => <_expression_> <_operator_> <_expression_>
  => identifier <_operator_> <_expression_>
  => identifier - <_expression_>
  => identifier - <_expression_> <_operator_> <_expression_>
  => identifier - identifier <_operator_> <_expression_>
  => identifier - identifier + <_expression_>
  => identifier - identifier + unsigned_integer
        (a)     -    (b)     +       (1)

The simple expression grammar below is unambiguous:

<_expression_> -> <_term_>
              | <_expression_> <_add_op_> <_term_>

<_term_> -> <_factor_>
        | <_term_> <_mult_op_> <_factor_>

<_factor_> -> identifier | unsigned_integer
          | - <_factor_> | ( <_expression_> )

<_add_op_> -> + | -

<_mult_op_> -> * | /

We find only one [[derivation]] for all strings in the language defined by the grammar. For example, the left-most [[derivation]] of a-b+1 is:

<_expression_>
  => <_expression_> <_add_op_> <_term_>
  => <_expression_> <_add_op_> <_term_> <a_dd_op_> <_term_>
  => <_term_> <_add_op_> <_term_> <_add_op_> <_term_>
  => <_factor_> <_add_op_> <_term_> <_add_op_> <_term_>
  => identifier <_add_op_> <_term_> <_add_op_> <_term_>
  => identifier - <_term_> <_add_op_> <_term_>
  => identifier - <_factor_> <_add_op_> <_term_>
  => identifier - identifier <_add_op_> <_term_>
  => identifier - identifier + <_term_>
  => identifier - identifier + <_factor_>
  => identifier - identifier + unsigned_integer
        (a)     -    (b)     +       (1)