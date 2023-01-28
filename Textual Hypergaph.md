Sentences are strings, words are points in the chain

The same words can show a list of all sentances that reference it, before and after.

// Nested array of scentance references with scentance.word.position in the sentance array of the word refrence, with the name of this array being the word.

index : 
word : sentance.(word set/list)

index : 
list : List.[itemindexSet],  List.[itemindexSet],  List.[itemindexSet].

Sentances are simply read from left to right.

A sentance is composed of tokens (words), the words are hashed for the index for the hash table.

// Hash collisions between words/array position are reasoned over with common ground.

// Tokens/words/content labels can be assigned a type

Many sentances can use the same words, and so it the same word can reference the words that come before and after it, of many other scentances.

The metainterpreter with holes crawls through the network to create new scentances.

Use monads to do this
