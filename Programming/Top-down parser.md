Also called a predictive [[parser]]. This type of [[parser]] proceeds building a [[parse tree]] from the root down. An example top-down [[parser]] is a [[recursive descent parser]][![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#recursivedescentparser).
-   Top-down parser is a parser for LL class of grammars (which is a subset of the larger LR class of grammars)
-   Also called _predictive_ parser
-   Top-down parser constructs parse tree from the root down
-   Easy to implement a predictive parser for an LL grammar by hand
-   LL grammars cannot exhibit _left-recursive productions[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#production)_ (but LR can)

Top-down parsing of A,B,C;

1

![Top-down parsing step 1](https://www.cs.fsu.edu/~engelen/courses/COP402003/topdown1.gif)

2

![Top-down parsing step 2](https://www.cs.fsu.edu/~engelen/courses/COP402003/topdown2.gif)

3

![Top-down parsing step 3](https://www.cs.fsu.edu/~engelen/courses/COP402003/topdown3.gif)

4

![Top-down parsing step 4](https://www.cs.fsu.edu/~engelen/courses/COP402003/topdown4.gif)

-   Top-down parsing is called _predictive_ parsing because it predicts what it is going to see:

-   As root <_id_list_> is predicted
-   After reading A the parser predicts that <_id_list_tail_> must follow
-   After reading , and B the parser predicts that <_id_list_tail_> must follow
-   After reading , and C the parser predicts that <_id_list_tail_> must follow
-   After reading ; the parser stops