In [computer science](https://en.wikipedia.org/wiki/Computer_science "Computer science"), **scannerless parsing** (also called **lexerless parsing**) performs tokenization (breaking a stream of characters into words) and parsing (arranging the words into phrases) in a single step, rather than breaking it up into a [pipeline](https://en.wikipedia.org/wiki/Pipeline_(software) "Pipeline (software)") of a [lexer](https://en.wikipedia.org/wiki/Lexical_analysis "Lexical analysis") followed by a [parser](https://en.wikipedia.org/wiki/Parser "Parser"), executing [concurrently](https://en.wikipedia.org/wiki/Concurrent_computation "Concurrent computation"). A [language grammar](https://en.wikipedia.org/wiki/Syntax_(programming_languages)#Complex_grammars "Syntax (programming languages)") is scannerless if it uses a single formalism to express both the [lexical](https://en.wikipedia.org/wiki/Lexical_analysis "Lexical analysis") (word level) and phrase level structure of the language.

Dividing processing into a lexer followed by a parser is more modular; scannerless parsing is primarily used when a clear lexer–parser distinction is unneeded or unwanted. Examples of when this is appropriate include [TeX](https://en.wikipedia.org/wiki/TeX "TeX"), most [wiki](https://en.wikipedia.org/wiki/Wiki "Wiki") grammars, [makefiles](https://en.wikipedia.org/wiki/Makefile "Makefile"), simple application-specific [scripting languages](https://en.wikipedia.org/wiki/Scripting_language "Scripting language"), and [Raku](https://en.wikipedia.org/wiki/Raku_(programming_language) "Raku (programming language)").

## Advantages
-   Only **one [metalanguage](https://en.wikipedia.org/wiki/Metalanguage "Metalanguage")** is needed
-   **Non-regular lexical structure** is handled easily
-   **"Token classification" is unneeded** which removes the need for design accommodations such as "[the lexer hack](https://en.wikipedia.org/wiki/The_lexer_hack "The lexer hack")" and language [reserved words](https://en.wikipedia.org/wiki/Reserved_word "Reserved word") (such as "while" in [C](https://en.wikipedia.org/wiki/C_(programming_language) "C (programming language)"))
-   Grammars can be **compositional** (can be merged without human intervention)

## Disadvantages
-   Since the lexical scanning and syntactic parsing are combined, the resulting parser tends to be **more complicated** and thus **harder to understand and debug**. The same will hold for the associated grammar, if a grammar is used to generate the parser.
-   The resulting parser tends to be significantly **less efficient** than a lexer-parser pipeline with regard to both **time** and **memory**.