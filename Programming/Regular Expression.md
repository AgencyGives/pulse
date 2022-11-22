Regular expressions describe the [[tokens]][![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#token) of a programming language. A regular expression is one of

-   a character
-   empty (denoted e)
-   concatenation: sequence of regular expressions denoting a concatenation
-   alternation: regular expressions separated by a bar | are alternative forms
-   repetition: a regular expression followed by a star * means that the regular expression is repeated zero, one, or more times

For example, the regular expression describing an identifier in C/C++ is:

identifier -> letter (letter | digit)*

digit -> 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9

letter -> a | b | c | d | e | f | g | h | i | j | k | l | m | n | o | p | q | r | s | t | u | v | w | x | y | z
        | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z
        | _

For [[compiler]] design, tools exist that generate efficient scanners[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#scanner) automatically from regular expressions (e.g. flex).