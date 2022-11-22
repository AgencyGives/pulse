A rule with a grammar [[production]] that is used to operate on the values of the attributes of [[terminals]] and [[nonterminals]] in the grammar.

Example

_grammar production               semantic rule_

<number1> -> <number2> <digit>   number1.value := 10*number2.value + digit.value
<number>  -> <digit>             number.value := digit.value
<digit>   -> 0                   digit.value := 0
           | 1                   digit.value := 1
           | 2                   digit.value := 2
           | 3                   digit.value := 3
           | 4                   digit.value := 4
           | 5                   digit.value := 5
           | 6                   digit.value := 6
           | 7                   digit.value := 7
           | 8                   digit.value := 8
           | 9                   digit.value := 9

In this example, the [[nonterminals]] <number> and <digit> have an attribute 'value' that holds the value of the numeric representation defined by the grammar. When the semantic rules are applied on the syntactic representation of the input, the rules compute the value of the input. When the values computed are used to check the validity of the input, then the semantic rules are used to enforce [[semantic checks]][![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#semanticchecks). Note: the nonterminal <number> has subscripts in the first production to distinguish the nonterminal on the left hand side and right hand side of the production.