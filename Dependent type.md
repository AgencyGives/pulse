> In computer science and logic, a **Dependent type** is a type whose definition depends on a value. It is an overlapping feature of type theory and type systems. In intuitionistic type theory, dependent types are used to encode logic's quantifiers like "for all" and "there exists". In functional programming languages like Agda, ATS, Coq, F*, Epigram, and Idris, dependent types help reduce bugs by enabling the programmer to assign types that further restrain the set of possible implementations.
>
> Two common examples of dependent types are dependent functions and dependent pairs. The return type of a dependent function may depend on the value (not just type) of one of its arguments. For instance, a function that takes a positive integer 
>
>, where the array length is part of the type of the array. (Note that this is different from polymorphism and generic programming, both of which include the type as an argument.) A dependent pair may have a second value the type of which depends on the first value. Sticking with the array example, a dependent pair may be used to pair an array with its length in a type-safe way.
>
> Dependent types add complexity to a type system. Deciding the equality of dependent types in a program may require computations. If arbitrary values are allowed in dependent types, then deciding type equality may involve deciding whether two arbitrary programs produce the same result; hence type checking may become undecidable.
>
> [Wikipedia](https://en.wikipedia.org/wiki/Dependent%20type)