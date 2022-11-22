Considered a revolution in programming in the 70s (much like object-oriented programming in the late 80s and early 90s). A programming technique that emphasizes top-down design, modularization of code (large routines are broken down into smaller, modular, routines), structured types (eg. records, sets, pointers, and multi-dimensional arrays), descriptive variable and constant names, and extensive commenting conventions. The use of the GOTO statement is discouraged to avoid spaghetti code (code that exhibits a criss-cross control flow behavior at run-time). Certain programming statements are indented in order to make loops and other program logic easier to follow.

Structured languages, such as Pascal[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#pascal) and Ada[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#ada), force the programmer to write a structured program. However, unstructured languages such as Fortran 77[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#fortran77), Cobol[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#cobol), and Basic[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#basic) require discipline on the part of the programmer to follow.

Here is an example of a non-structured program in C[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#c) that counts the number of goto's in a file whose filename is given as an argument on the command line. This program can be used to measure the "spaghettiness" of a C program:

#include <stdio.h>
#include <malloc.h>
main(togo,toog)
int togo;
char *toog[];
{char *ogto,   tgoo[80];FILE  *ogot;  int    oogt=0, ootg,  otog=79,
ottg=1;if (    togo==  ottg)   goto   gogo;  goto    goog;  ggot:
if (   fgets(  tgoo,   otog,   ogot)) goto   gtgo;   goto   gott;
gtot:  exit(); ogtg: ++oogt;   goto   ogoo;  togg:   if (   ootg > 0)
goto   oggt;   goto    ggot;   ogog:  if (  !ogot)   goto   gogo;
goto   ggto;   gtto:   printf( "%d    goto   \'s\n", oogt); goto
gtot;  oggt:   if (   !memcmp( ogto, "goto", 4))     goto   otgg;
goto   gooo;   gogo:   exit(   ottg); tggo:  ootg=   strlen(tgoo);
goto   tgog;   oogo: --ootg;   goto   togg;  gooo: ++ogto;  goto
oogo;  gott:   fclose( ogot);  goto   gtto;  otgg:   ogto=  ogto +3;
goto   ogtg;   tgog:   ootg-=4;goto   togg;  gtgo:   ogto=  tgoo;
goto   tggo;   ogoo:   ootg-=3;goto   gooo;  goog:   ogot=  fopen(
toog[  ottg],  "r");   goto    ogog;  ggto:  ogto=   tgoo;  goto
ggot;}

Fortran and Basic programs developed in the early days of computing were difficult to read and understand, somewhat similar to this example in terms of the choice in variable names (limit 6 characters in Fortran and 2 in Basic) and the frequent use of goto.