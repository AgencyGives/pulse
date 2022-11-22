Lisp (LISt Processing language) was developed by McCarthy as a realization of Church's [[lambda calculus]][![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#lambdacalculus). Many dialects exists, among which Common Lisp and Scheme[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#scheme) are the most popular. Lisp is the dominant language used in Artificial Intelligence. The emphasis is on symbolic computation rather than numeric. Lisp is very powerful for symbolic computation with lists and Lisp often used in artificial intelligence. As a functional language[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#functional), all control is performed by [[recursion]][![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#recursion) and conditional expressions. Lisp was the first language with implicit memory management (automatic allocate and deallocate) by "[[garbage collection]]"[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#garbagecollection). Lisp heavily influenced [[functional programming languages]] (e.g. ML[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#ml), Miranda[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#miranda), [[Haskell]][![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#haskell))

## Simple and elegant design of Lisp
- *Homogeneity of programs and data:* a Lisp program is a list and can be manipulated in Lisp as a list
- *Self-definition:* a Lisp interpreter can be written in Lisp
- *Interactive:* interaction with use through "read-eval-print" loop

### Scheme (Lisp Dialect)
- Lisp and Scheme adopt _Cambridge Polish notation_ for expressions:
	- An expression is an _atom_, e.g. a number, string, or identifier name
	- An expression is a _list_ whose first element is the function name (or operator) followed by the arguments which are expressions:
		(_function arg1 arg2 arg3 ..._)
- The _"Read-eval-print" loop_ provides user interaction: an expression is read, evaluated by evaluating the arguments first and then the function/operator is called after which the result is printed
	- Input: 9
	- Output: 9
	- Input:(+ 3 4)
	- Output: 7
	- Input:(+ (* 2 3) 1)
	- Output: 7

- User can load a program from a file with the load function
	- (load "my_scheme_program")
	- The file name should use the .scm extension

### Scheme Data Structures
- The only data structures in Lisp and Scheme are *atoms* and *lists*
- Atoms are:
	- Numbers, e.g. 7
	- Strings, e.g. "abc"
	- Identifier names (variables), e.g. x
	- Boolean values true #t and false #f 
	- Symbols which are quoted identifiers which will not be evaluated
- Lists:
	- To distinguish list data structures from expressions that are written as lists, a quote (') is used to quote the list:
	- '(elt1 elt2 elt3 ...)
