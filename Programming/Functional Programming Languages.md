The underlying machinery of functional [[programming languages]] is based on Church's [[lambda calculus]][![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#lambdacalculus). The computational model is based on recursive functions and a program is considered a [[function]] thats maps inputs to outputs. Through the process of top-down refinement, a program is defined in terms of simpler functions.

Example languages in this category are [[Lisp]][![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#[[[[[[[[Lisp]]|[[li]]sp]]]]]]), Scheme[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#scheme), ML[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#ml), and [[Haskell]][![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#haskell).

Functional program example ([[Haskell]]):

gcd a b
  | a == b = a
  | a >  b = gcd (a-b) b
  | a <  b = gcd a (b-a)


## What is Functional Programming?
-   Functional[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#functional) programming is a declarative programming paradigm
	-   Computation is more implicit  and functional call is the only form of explicit control
-   But: imperative[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#imperative) [[programming languages]] are more widely used
	-  Integrated software development environments[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#softwaredevelopmentenvironment) for procedural[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#procedural) and object oriented[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#objectoriented) [[programming languages]] are "industrial strength" and often include extensive libraries
-   Many (commercial) applications exist for functional[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#functional) programming:
	-   Symbolic data manipulation
	-   Natural [[language]] processing
	-   Artificial intelligence
	-   Automatic theorem proving and computer algebra
	-   Algorithmic optimization of programs written in pure functional languages

## Origin of Functional Programming
- _Church's thesis_:
	-   All _models of computation_ are equally powerful and can compute any [[function]]
-   Turing's model of computation: _Turing machine_[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#turingmachine)
	- Reading/writing of values on an infinite tape by a finite state machine

-   Church's model of computation: _[[lambda calculus]]_[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#lambdacalculus)
	-   This inspired functional programming as a _concrete implementation_ of [[lambda calculus]][![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#lambdacalculus)

-   _Computability theory_
	-  A program can be viewed as a _constructive proof_ that some mathematical object with a desired property exists
	-  A [[function]] is a _mapping_ from inputs to output objects and computes output objects from appropriate inputs
	-  For example, the proposition that every pair of nonnegative integers (the inputs) has a greatest common divisor (the output object) has a constructive proof implemented by Euclid's algorithm written as a "[[function]]"

## Concepts of Functional Programming
-  _Functional[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#functional) programming_ defines the outputs of a program as mathematical [[function]] of the inputs with no notion of internal state (no side effects[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#sideeffect))
	- A _pure_ [[function]] can always be counted on to return the same results for the same input parameters
	- No assignments: dangling and/or uninitalized pointer references do not occur
	- [[Haskell]] is a pure functional programming [[language]]
- Non-pure functional [[programming languages]] include imperative features with side effects that affect global state (e.g. through destructive assignments to global variables)
	- Example: [[Lisp]], Scheme, and ML
- Useful features are found in functional languages that are often missing in imperative languages:
	- *First-[[class]] [[function]] values:* the ability of functions to return *newly* constructed functions
	- *Higher-oder functions:* functions that take other functions as input parameters or return functions.
	- *Polymorphism:* the ability to write functions that operate on more than one type of data
	- *Aggregate constructs for constructing structured objects:* the ability to specify a structured object-in-line, e.g. a complete list or record [[value]]
	- *[[Garbage collection]]*