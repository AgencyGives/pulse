A scanner of a [[compiler]][![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#compiler) breaks up the character stream of a source program into [[tokens]][![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#tokens). The process of scanning comprises the lexical analysis phase of a [[compiler]]. The purpose of scanning is to simplify the task of the [[parser]] of the [[compiler]]. Comments and white space are removed, keywords are recognized and represented as [[tokens]][![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#tokens), identifers for names of variables and functions are stored in a symbol table and tagged with source file and line numbers.

Example scanner written in Java:

**import** java.io.*;
**public** **class** Scanner
{ **public** **static** **void** main(String argv[]) **throws** IOException
  { FileInputStream stream = **new** FileInputStream(argv[0]);
    InputStreamReader reader = **new** InputStreamReader(stream);
    StreamTokenizer tokens = **new** StreamTokenizer(reader);
    **int** next = 0;
    **while** ((next = tokens.nextToken()) != tokens.TT_EOF)
    { **switch** (next)
      { **case** tokens.TT_WORD:
          System.out.println("WORD:   " + tokens.sval);
          **break**;
        **case** tokens.TT_NUMBER:
          System.out.println("NUMBER: " + tokens.nval);
          **break**;
        **default**:
          **switch** ((char)next)
          { **case** '"':
              System.out.println("STRING: " + tokens.sval);
              **break**;
            **case** '\'':
              System.out.println("CHAR:   " + tokens.sval);
              **break**;
            **default**:
              System.out.println("PUNCT:  " + (char)next);
          }
      }
    }
    stream.close();
  }
}

[Get Java source](https://www.cs.fsu.edu/~engelen/courses/COP402003/Scanner.java). Save it with file name "Scanner.java", compile it with "javac Scanner.java", and run it with "Scanner Scanner.java", where the scanner is applied to itself.