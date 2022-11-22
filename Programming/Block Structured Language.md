A language that supports the local declaration of variables with a limited scope[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#scope) in a block or compound statement. For example, the following C fragment declares a temporary integer variable n to be used in the loop to copy a file from standard input to standard output:

{   int n;
    while ((n = getchar()) != EOF)
        putchar(n);
}

Variable n has a local scope[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#staticscope) limited to the block and it's value is only accessible within the block.

In C, C++, Java, and C#, a block is opened with { and closed with }. Pascal and Ada use begin and end keywords to delimit a block.

The use of blocks is so common today that we don't tend to think of it as something special.