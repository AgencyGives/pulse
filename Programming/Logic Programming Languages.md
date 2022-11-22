Logic [[programming languages]] are declarative languages that derive results by logical inference. [[Prolog]][![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#prolog)for example, is based on propositional logic. The computational model consists of an inference process on a database to find values that satisfy certain constraints and relationships.

Logic program example ([[Prolog]]):

gcd(A, A, A).  % note: if the first two arguments are the same, the third argument (GCD) is A
gcd(A, B, G) :- A > B, N is A-B, gcd(N, B, G).
gcd(A, B, G) :- A < B, N is B-A, gcd(A, N, G).