A referentially transparent expression  is composed of side-effect free functions and operators. No side-effects may occur in the evaluation of the expression. As a result, the expression evaluates to a value that is solely depending on the values of the variables used in the expression.

Example of a non-referentially transparent expression (where 'accumulate' and 'sum' are defined in[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#sideeffect)) is:

accumulate(2) + sum

This expression uses a [[function]] with a [[side effect]]. The value of this expression is undetermined in C and C++, because these languages allow different operator evaluation orders, which means that the value of 'sum' may or may not have been updated through the 'accumulate' call.