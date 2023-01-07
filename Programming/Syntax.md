> In linguistics, **Syntax** () is the study of how words and morphemes combine to form larger units such as phrases and sentences. Central concerns of syntax include word order, grammatical relations, hierarchical sentence structure (constituency), agreement, the nature of crosslinguistic variation, and the relationship between form and meaning (semantics). There are numerous approaches to syntax that differ in their central assumptions and goals.
>
> [Wikipedia](https://en.wikipedia.org/wiki/Syntax)

In [computer science](https://en.wikipedia.org/wiki/Computer_science "Computer science"), the **syntax** of a [computer language](https://en.wikipedia.org/wiki/Computer_language "Computer language") is the rules that defines the combinations of symbols that are considered to be correctly structured [statements](https://en.wikipedia.org/wiki/Statement_(computer_science) "Statement (computer science)") or [expressions](https://en.wikipedia.org/wiki/Expression_(computer_science) "Expression (computer science)") in that language. This applies both to [programming languages](https://en.wikipedia.org/wiki/Programming_language "Programming language"), where the document represents [source code](https://en.wikipedia.org/wiki/Source_code "Source code"), and to [markup languages](https://en.wikipedia.org/wiki/Markup_language "Markup language"), where the document represents data.

The syntax of a language defines its surface form, computer languages are based on sequences of [characters](https://en.wikipedia.org/wiki/Character_(computing) "Character (computing)"), while [visual programming languages](https://en.wikipedia.org/wiki/Visual_programming_languages "Visual programming languages") are based on the spatial layout and connections between symbols (which may be textual or graphical). Documents that are syntactically invalid are said to have a [syntax error](https://en.wikipedia.org/wiki/Syntax_error "Syntax error"). **When designing the syntax of a language, a designer might start by writing down examples of both legal and illegal [strings](https://en.wikipedia.org/wiki/String_(computer_science) "String (computer science)"), before trying to figure out the general rules from these examples.**

Syntax therefore refers to the _form_ of the code, and is contrasted with [semantics](https://en.wikipedia.org/wiki/Semantics_(computer_science) "Semantics (computer science)") – the _meaning_. In processing computer languages, semantic processing generally comes after syntactic processing; however, **in some cases, semantic processing is necessary for complete syntactic analysis**, and these are done together or [concurrently](https://en.wikipedia.org/wiki/Concurrency_(computer_science) "Concurrency (computer science)"). In a [compiler](https://en.wikipedia.org/wiki/Compiler "Compiler"), the syntactic analysis comprises the [frontend](https://en.wikipedia.org/wiki/Compiler_frontend "Compiler frontend"), while the [semantic analysis](https://en.wikipedia.org/wiki/Semantic_analysis_(compilers) "Semantic analysis (compilers)") comprises the [backend](https://en.wikipedia.org/wiki/Compiler_backend "Compiler backend") (and middle end, if this phase is distinguished).

## Levels of syntax
Computer language syntax is generally distinguished into three levels:

-   **Words** – the lexical level, determining how characters form [tokens](https://en.wikipedia.org/wiki/Token_(parser) "Token (parser)");
-   **Phrases** – the grammar level, narrowly speaking, determining how tokens form phrases;
-   **Context** – determining what objects or variables names refer to, if types are valid, etc.

Distinguishing in this way yields modularity, allowing each level to be described and processed separately and often independently.

First, a lexer turns the linear sequence of characters into a linear sequence of tokens; this is known as "[lexical analysis](https://en.wikipedia.org/wiki/Lexical_analysis "Lexical analysis")" or "lexing".

Second, the parser turns the linear sequence of tokens into a hierarchical syntax tree; this is known as "[parsing](https://en.wikipedia.org/wiki/Parsing "Parsing")" narrowly speaking.

Thirdly, the contextual analysis resolves names and checks types.

This modularity is sometimes possible, but in many real-world languages an earlier step depends on a later step – **for example, [the lexer hack](https://en.wikipedia.org/wiki/The_lexer_hack "The lexer hack") in C is because tokenization depends on context.** Even in these cases, syntactical analysis is often seen as approximating this ideal model.

The parsing stage itself can be divided into two parts: the [parse tree](https://en.wikipedia.org/wiki/Parse_tree "Parse tree"), or "concrete syntax tree", which is determined by the grammar, but is generally far too detailed for practical use, and the [abstract syntax tree](https://en.wikipedia.org/wiki/Abstract_syntax_tree "Abstract syntax tree") (AST), which simplifies this into a usable form. The AST and contextual analysis steps can be considered a form of semantic analysis, as they are adding meaning and interpretation to the syntax, or alternatively as informal, manual implementations of syntactical rules that would be difficult or awkward to describe or implement formally.

The levels generally correspond to levels in the [Chomsky hierarchy](https://en.wikipedia.org/wiki/Chomsky_hierarchy "Chomsky hierarchy").

Words are in a [regular language](https://en.wikipedia.org/wiki/Regular_language "Regular language"), specified in the [lexical grammar](https://en.wikipedia.org/wiki/Lexical_grammar "Lexical grammar"), which is a Type-3 grammar, generally given as [regular expressions](https://en.wikipedia.org/wiki/Regular_expression "Regular expression").

Phrases are in a [context-free language](https://en.wikipedia.org/wiki/Context-free_language "Context-free language") (CFL), generally a [deterministic context-free language](https://en.wikipedia.org/wiki/Deterministic_context-free_language "Deterministic context-free language") (DCFL), specified in a [phrase structure grammar](https://en.wikipedia.org/wiki/Phrase_structure_grammar "Phrase structure grammar"), which is a Type-2 grammar, generally given as [production rules](https://en.wikipedia.org/wiki/Production_(computer_science) "Production (computer science)") in [Backus–Naur form](https://en.wikipedia.org/wiki/Backus%E2%80%93Naur_form "Backus–Naur form") (BNF). Phrase grammars are often specified in much more constrained grammars than full [context-free grammars](https://en.wikipedia.org/wiki/Context-free_grammar "Context-free grammar"), in order to make them easier to parse; while the [LR parser](https://en.wikipedia.org/wiki/LR_parser "LR parser") can parse any DCFL in linear time, the simple [LALR parser](https://en.wikipedia.org/wiki/LALR_parser "LALR parser") and even simpler [LL parser](https://en.wikipedia.org/wiki/LL_parser "LL parser") are more efficient, but can only parse grammars whose production rules are constrained. 

In principle, contextual structure can be described by a [context-sensitive grammar](https://en.wikipedia.org/wiki/Context-sensitive_grammar "Context-sensitive grammar"), and automatically analyzed by means such as [attribute grammars](https://en.wikipedia.org/wiki/Attribute_grammar "Attribute grammar"), though, in general, this step is done manually, via [name resolution](https://en.wikipedia.org/wiki/Name_resolution_(programming_languages) "Name resolution (programming languages)") rules and [type checking](https://en.wikipedia.org/wiki/Type_checking "Type checking"), and implemented via a [symbol table](https://en.wikipedia.org/wiki/Symbol_table "Symbol table") which stores names and types for each scope.

Tools have been written that automatically generate a lexer from a lexical specification written in regular expressions and a parser from the phrase grammar written in BNF: this allows one to use [declarative programming](https://en.wikipedia.org/wiki/Declarative_programming "Declarative programming"), rather than need to have procedural or functional programming. A notable example is the [lex](https://en.wikipedia.org/wiki/Lex_(software) "Lex (software)")-[yacc](https://en.wikipedia.org/wiki/Yacc "Yacc") pair.

These automatically produce a _concrete_ syntax tree; the parser writer must then manually write code describing how this is converted to an _abstract_syntax tree. Contextual analysis is also generally implemented manually. Despite the existence of these automatic tools, parsing is often implemented manually, for various reasons – perhaps the phrase structure is not context-free, or an alternative implementation improves performance or error-reporting, or allows the grammar to be changed more easily. Parsers are often written in functional languages, such as [Haskell](https://en.wikipedia.org/wiki/Haskell_(programming_language) "Haskell (programming language)"), or in scripting languages, such as [Python](https://en.wikipedia.org/wiki/Python_(programming_language) "Python (programming language)") or [Perl](https://en.wikipedia.org/wiki/Perl "Perl"), or in [C](https://en.wikipedia.org/wiki/C_(programming_language) "C (programming language)") or [C++](https://en.wikipedia.org/wiki/C%2B%2B "C++").

The syntax of textual programming languages is usually defined using a combination of [regular expressions](https://en.wikipedia.org/wiki/Regular_expression "Regular expression") (for [lexical](https://en.wikipedia.org/wiki/Lexical_analysis "Lexical analysis") structure) and [Backus–Naur form](https://en.wikipedia.org/wiki/Backus%E2%80%93Naur_form "Backus–Naur form") (for [grammatical](https://en.wikipedia.org/wiki/Context-free_grammar "Context-free grammar") structure) to inductively specify [syntactic categories](https://en.wikipedia.org/wiki/Syntactic_category "Syntactic category") (nonterminals) and _terminal_ symbols. S**yntactic categories are defined by rules called _productions_, which specify the values that belong to a particular syntactic category**. Terminal symbols are the concrete characters or strings of characters (for example [keywords](https://en.wikipedia.org/wiki/Keyword_(computer_programming) "Keyword (computer programming)") such as _define_, _if_, _let_, or _void_) from which syntactically valid programs are constructed.

A language can have different equivalent grammars, such as equivalent regular expressions (at the lexical levels), or different phrase rules which generate the same language. Using a broader category of grammars, such as LR grammars, can allow shorter or simpler grammars compared with more restricted categories, such as LL grammar, which may require longer grammars with more rules. Different but equivalent phrase grammars yield different parse trees, though the underlying language (set of valid documents) is the same.

### Complex grammars

The grammar needed to specify a programming language can be classified by its position in the [Chomsky hierarchy](https://en.wikipedia.org/wiki/Chomsky_hierarchy "Chomsky hierarchy"). The phrase grammar of most programming languages can be specified using a Type-2 grammar, i.e., they are context-free grammars though the overall syntax is context-sensitive (due to variable declarations and nested scopes), hence Type-1. However, there are exceptions, and for some languages the phrase grammar is Type-0 (Turing-complete).

In some languages like Perl and Lisp the **specification (or implementation) of the language allows constructs that execute during the parsing phase**. **Furthermore, these languages have constructs that allow the programmer to alter the behavior of the parser.** **This combination effectively blurs the distinction between parsing and execution, and makes syntax analysis an [undecidable problem](https://en.wikipedia.org/wiki/Undecidable_problem "Undecidable problem") in these languages, meaning that the parsing phase may not finish.** For example, in Perl it is possible to execute code during parsing using a `BEGIN` statement, and Perl function prototypes may alter the syntactic interpretation, and possibly even the syntactic validity of the remaining code.[[7]](https://en.wikipedia.org/wiki/Syntax_(programming_languages)#cite_note-7) Colloquially this is referred to as "only Perl can parse Perl" (because code must be executed during parsing, and can modify the grammar), or more strongly "even Perl cannot parse Perl" (because it is undecidable). Similarly, Lisp [macros](https://en.wikipedia.org/wiki/Macro_instruction "Macro instruction") introduced by the `defmacro` syntax also execute during parsing, meaning that a Lisp compiler must have an entire Lisp run-time system present. In contrast, C macros are merely string replacements, and do not require code execution.[[8]](https://en.wikipedia.org/wiki/Syntax_(programming_languages)#cite_note-8)[[9]](https://en.wikipedia.org/wiki/Syntax_(programming_languages)#cite_note-9)

**Overview**
- Tokens and regular expressions
- Synatx and context-free grammars
- Grammar derivations
- Parse trees
- Top-down and bottom-up parsing
- Recursive descent parsing

## Tokens Revisted
- Tokens are the basic building blocks of a programming language: keywords, identifiers, numbers, punctuation
- We saw that the first compiler phase (scanning) splits up a charecter stream into tokens
- Tokens have a special role with respect to:
	- *Free-format* language: source program is a sequence of tokens and horizontal/vertical position of a token on a page is unimportant (e.g. Pascal)
	- *Fixed-forma*t language: indentation and/or position of a token on a page is significant (early Basic, Fortan, Haskell)
	- *Case-sensitive* language: upper and lowercase are distinct (C, C++, Java)
	- *Case-insensitive* language: upper and lowercase are identical (Ada, Fortran, Pascal)

## Describing Tokens by Regular Expressions
- The makeup of a token is described by a *regular expression*
- A regular expression is
	- a charecter
	- *empty* (denoted e)
	- *concatenation*: sequence of regular expressions
	- *alternation*: regular expressions seperated by a bar |
	- *repitition:* a regular expression followed by a star (called a Kleene star)

## Context-Free Grammars: BNF
-   Regular expressions cannot describe nested constructs, but _context-free grammars_ can
-   Backus-Naur Form (BNF)[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#bnf) grammar _productions_ are of the form  
    <_nonterminal_> -> sequence of (non)terminals
-   A terminal[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#terminal)of a grammar is a token[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#token) e.g. specific programming language keyword, e.g. **return**
-   A <_nonterminal_>[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#nonterminal)denotes a  syntactic category
-   The symbol | denotes _alternative_ forms in a production, e.g. different program statements are catagorized, e.g.<_stmt_> -> **return** | **break** | <_id_> := <_expression_>
-   The special symbol e denotes _empty_, e.g. used in optional constructs, e.g.<_optional_static_> -> **static** | e
  
## Extended BNF

-   _Extended_ BNF includes an explicit form for _optional_ constructs with [ and ]
  
For example:  
<_stmt_> -> **for** <_id_> := <_expr_> **to** <_expr_> [ **step** <_expr_> ] **do** <_stmt_>-   _Extended_ BNF includes a _repetition_ construct *
  
For example:  
<_decl_> -> **int** <_id_> (, _<id_>)*


## Example Grammar for Expressions

Context-free grammar for a simple expression syntax with identifiers, integers, unary minus, parenthesis, and +, -, *, /  
 

Example expression grammar productions

<_expression_> -> identifier
              | unsigned_integer
              | - <_expression_>
              | ( <_expression_> )
              | <_expression_> <_operator_> <_expression_>

<_operator_> -> + | - | * | /

*Note that identifier and signed_integer are tokens defined by a regular expression, not by the grammar. They are provided as tokens by the scanner in a compiler.*

# Derivations

-   From a grammar we can derive _strings_ (= sequences of tokens/terminals)
-   In each _derivation step_ a nonterminal is replaced by a right-hand side (part after ->) of a production for that nonterminal
-   Each representation after each step is called a _sentential form_
-   When the nonterminal on the far right (left) in a sentential form is replaced in each derivation step the derivation is called _right-most (left-most)_
-   The final form consists of terminals only and is called the _yield_ of the derivation
-   A context-free grammar is a _generator_ of a _context-free language_: the language defined by the grammar is the set of all strings that can be derived

Example derivation (right-most)

<_expression_>
  => <_expression_> <_operator_> <_expression_>
  => <_expression_> <_operator_> identifier
  => <_expression_> + identifier
  => <_expression_> <_operator_> <_expression_> + identifier
  => <_expression_> <_operator_> identifier + identifier
  => <_expression_> * identifier + identifier
  => identifier * identifier + identifier

# Parsing and Parse Trees

-   A _parse tree[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#parsetree)_ depicts a derivation as a tree
-   The _nodes_ are the nonterminals[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#nonterminal)
-   The _children_ of a node are the symbols (terminals and nonterminals) on a right-hand side of a production
-   The _leaves_ are the terminals[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#terminal)
-   For example, given string slope*x+intercept a _parser[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#parser)_ constructs a parse tree[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#parsetree):

![Parse tree for slope*x+intercept](https://www.cs.fsu.edu/~engelen/courses/COP402003/parsetree1.gif)

-   An alternative parse tree[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#parsetree) for this string is:

![Alternative parse tree for slope*x+intercept](https://www.cs.fsu.edu/~engelen/courses/COP402003/parsetree2.gif)

