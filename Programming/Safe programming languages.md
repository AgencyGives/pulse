[[Strong typing]][![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#strongtyping) is considered the most important safety issue of a programming language as typing errors are always detected. Among other things are the safety issues  dealing with the use of a progamming language on the Internet, such as in [[Java]] and C# which have elaborate authentication schemes. Languages such as C and C++ are not safe, because the [[compiler]] and runtime environment cannot guarantee type safety. For example, pointer casts can be used to change the type of the data pointed to without actually converting the data.

Here is an example of a safe cast to convert an integer to a float:

**int** n = 5;
**float** f = (float)n;

This is an example of an unsafe cast, which is prohibited in type-safe languages:

**int** n = 5;
**float** *fp = (float*)&n;

Such casts, whether explicit as above or implicit, can lead to disaster. Type-safe languages usually do not support pointer arithmetic to prevent accessing data of the ''wrong'' type.