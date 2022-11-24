A parse tree depicts a [[derivation]][![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#derivation) as a tree: the nodes are the [[nonterminals]][![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#nonterminal), the children of a node are the symbols ([[terminals]] and [[nonterminals]]) of a right-hand side of a [[production]][![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#production) for the nonterminal at the node, and the leaves are the [[terminals]][![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#terminal).

Given the grammar

<_id_list_> -> identifier <_id_list_tail_>

<_id_list_tail_> -> , identifier <_id_list_tail_>
                | ;

The parse tree of "A,B,C;" is  
![[Parser tree example](https://www.cs.fsu.edu/~engelen/courses/COP402003/topdown4.gif)
S -> SS | (S) | e
S => SS => S(S)
=> (S)(S)
=> (S)()
=>()()

Leftmost derivation
S => SS => (S)S
=> ()(S)
=> ()()

In any derivation i can always find a leftmost derivation, because it is a context free-grammar.