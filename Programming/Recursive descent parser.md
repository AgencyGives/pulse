- Predictive parsing method for LL(1) grammar (LL with one token lookahead)
- Based on recursive subroutines

- Each nonterminal has a subroutine that implements the production(s) for that nonterminal so that calling the subroutine will parse a part of a string described by the nonterminal
-  When more than one alternative production exists for a nonterminal, lookahead token from scanner should decide which production is to be applied

LL(1) for a simple calculator language

<_expr_> -> <_term_> <_term_tail_>

<_term_tail_> -> <_add_op_> <_term_> <_term_tail_> | e

<_term_> -> <_factor_> <_factor_tail_>

<_factor_tail_> -> <_mult_op_> <_factor_> <_factor_tail_> | e

<_factor_> -> ( <_expr_> ) | - <_factor_>
          | identifier | unsigned_integer

<_add_op_> -> + | -

<_mult_op_> -> * | /


### Example Recursive Descent Parsing
![[Pasted image 20221125124340.png]]