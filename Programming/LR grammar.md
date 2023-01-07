A LR grammar is a grammar suitable for bottom-up parsing. A LR(_n_) grammar is a grammar suitable for bottom-up parsing using _n_ lookeahead [[tokens]]. The [[class]] of LR grammars includes the [[class]] of LL grammars.

-   Bottom-up parser is a parser for LR class of grammars
-   Difficult to implement by hand
-   Tools (e.g. bison) exist that generate bottom-up parsers for LR grammars
-   Parsing is based on shifting tokens on a stack until it recognizes a right-hand side of a production which it then reduces to a left-hand side (nonterminal) with a partial parse tree