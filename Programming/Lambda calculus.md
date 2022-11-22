A very simple algebraic model of computation designed byAlonzo Church in the 60s. In its pure form, everything is a [[function]] (even primitive types such as numbers and compound data structures such as lists). While the syntax and the rewrite rules of lambda calculus are very primitive, it has been shown that lambda calculus provides a theoretical model of computation. This model is actually easier to program than a Turing machine, the other well-known model of computation. [[Lisp]][![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#lisp) is a direct realization of lambda calculus as a programming language.

A _lambda expression_ is recursively defined as

-   a _name_ which is treated as a symbolic constant or [[function]] name
-   a _variable_
-   a lambda _abstraction_ which is essentially a nameless [[function]] written as l _var . lambda-expression,_ where _var_ is a variable denoting the formal argument (input value) and _lambda-expression_ is the body of the [[function]] (the return value)
-   a [[function]] _application_ written as adjacent lambda expressions
-   a parenthesized lambda expression

Only two rewrite rules on lambda expressions are necessary to model universal computation: _alpha reduction_ and _beta reduction_. The difference between a name and a variable becomes clear in the context in which they are used. A variable is used in a lambda abstraction to represent the input parameter, while a name is ``inert'', i.e. it has no value other than the name itself.

Some examples:

_f a_ denotes the application of a [[function]] symbol _f_ to an argument _a_.

_l v . v_ is a lambda abstraction that denotes the identity [[function]]: argument _v_ takes a value and the [[function]] returns the (unchanged) value. The application of this [[function]] to an expression _a_, for example, is written (_l v . v_) _a_ and this evaluates to _a_ (argument _v_ takes _a_ and the [[function]] returns the value of _v_).

_l v. f v_ is a lambda abstraction that, when applied to a value, applies _f_ to it. For example, (_lv. f v_) _a_ results in _f a_.

_l f. f a_ is a lambda abstraction that, when applied to a [[function]] name, applies this [[function]] to _a_. For example, (_l_ _f. f a_) _g_ results in _g a_.