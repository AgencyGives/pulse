Although object-oriented programming[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#oop) is gaining more popularity, the procedural languages are still the most familiar and successful languages. The basic mode of operation is the modification of variables which is sometimes referred to as computing via side effects[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#sideeffect): procedural languages are based on statements that influence subsequent computation by chaning the value of memory. The success of these languages can be mainly contributed to the efficiency of the language implementation in our current computer architectures, called the von Neumann computer architectures. This common architecture exhibits a central processing unit (CPU) and memory which are connected by a bus.

Example procedural languages are Fortran 77[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#fortran77), Basic[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#basic), Pascal[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#pascal), Ada[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#ada), and C[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#c).

Procedural program example (C):

**int** gcd(**int** a, **int** b)
{ **while** (a != b)
    **if** (a > b) a = a-b; **else** b = b-a;
  **return** a;
}