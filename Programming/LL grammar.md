An LL grammar is a grammar suitable for top-down parsing. If it is not possible to write a [[recursive descent parser]] for a grammar, it is not LL(1). An LL(_n_) grammar is a grammar suitable for top-down parsing using _n_ lookahead [[tokens]].

An LL grammar cannot have left-recursive productions[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#production), because a [[recursive descent parser]] would recursively call itself forever without consuming any input characters.

The following grammar is _not_ LL(1)

<A> -> <B> <C>
<A> -> a

<B> -> a b
<B> -> b

<C> -> c

It is not LL(1) because the subroutine for nonterminal A cannot decide which [[production]] to use when it sees an a on the input:

proc A
  if next_token="a"
    _?? cannot decide whether the first or second [[production]] for <A> applies here ??_

The grammar is LL(2), because the token after next token can be used to determine which [[production]] should be applied:

proc A
  if next_token="a" and token_after_next_token="b"
    B()
    C()
  else if next_token="b"
    B()
    C()
  else
    match("a");