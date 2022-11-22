[[BNF]][![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#bnf) grammar productions are of the form

<_nonterminal_> -> sequence of (non)[[terminals]]

Productions provide descriptions of the syntax for a syntactic category denoted by a nonterminal.

A production is _immediately left recursive_ if it is of the form

<A> -> <A> ...

and a production is _immediately right recursive_ if it is of the form

<A> -> ... <A>

where <A> is some nonterminal.

Productions can be left or right recursive through other productions. For example

<A> -> <B> ...

<B> -> <A> ...