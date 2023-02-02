In [computer science](https://en.wikipedia.org/wiki/Computer_science "Computer science"), **terminal and nonterminal symbols** are the lexical elements used in specifying the [production rules](https://en.wikipedia.org/wiki/Production_(computer_science) "Production (computer science)") constituting a [formal grammar](https://en.wikipedia.org/wiki/Formal_grammar "Formal grammar"). _Terminal symbols_ are the elementary symbols of the [language](https://en.wikipedia.org/wiki/Formal_language "Formal language") defined by a formal grammar. _Nonterminal symbols_ (or _syntactic variables_) are replaced by groups of terminal symbols according to the production rules.

The terminals and nonterminals of a particular grammar are two [disjoint sets](https://en.wikipedia.org/wiki/Disjoint_sets "Disjoint sets").

## Terminal Symbols
Terminal symbols are literal symbols that may appear in the outputs of the production rules of a formal grammar and which cannot be changed using the rules of the grammar. Applying the rules recursively to a source string of symbols will usually terminate in a final output string consisting only of terminal symbols.

## Non-Terminal Symbols
Nonterminal symbols are those symbols that can be replaced. They may also be called simply _syntactic variables_. A formal grammar includes a _start symbol_, a designated member of the set of nonterminals from which all the strings in the language may be derived by successive applications of the production rules. In fact, the language defined by a grammar is precisely the set of _terminal_ strings that can be so derived.

[Context-free grammars](https://en.wikipedia.org/wiki/Context-free_grammar "Context-free grammar") are those grammars in which the left-hand side of each production rule consists of only a single nonterminal symbol. This restriction is non-trivial; not all languages can be generated by context-free grammars. Those that can are called context-free languages. These are exactly the languages that can be recognized by a non-deterministic [push down automaton](https://en.wikipedia.org/wiki/Push_down_automaton "Push down automaton"). Context-free languages are the theoretical basis for the syntax of most [programming languages](https://en.wikipedia.org/wiki/Programming_languages "Programming languages").

## Production Rules
A grammar is defined by [production rules](https://en.wikipedia.org/wiki/Production_(computer_science) "Production (computer science)") (or just 'productions') that specify which symbols may replace which other symbols; these rules may be used to [generate strings](https://en.wikipedia.org/wiki/String_generation "String generation"), or to parse them. Each such rule has a _head_, or left-hand side, which consists of the string that may be replaced, and a _body_, or right-hand side, which consists of a string that may replace it. Rules are often written in the form _head_ → _body_; e.g., the rule _a_ → _b_ specifies that _a_ can be replaced by _b_.

![[Pasted image 20221123223455.png]]