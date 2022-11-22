The concept of a class extends the notion of abstract data types[![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#adt) (ADTs) with [[inheritance]][![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#[[inheritance]]). ADTs are limited to packages that encapsulate a data type declaration with a set of operations.

The following is an example [[stack]] template class in C++:

**template** <**class** element> **class** stack
{ **private**:
    **int** top;
    element[] s;
  **public**:
    [[stack]](**int** size)
    { s = **new** element[size]; top = 0; };
    ~[[stack]]()
    { **delete**[] s; };
    **void** push(element elem)
    { s[top++] = elem; };
    **void** pop(void)
    { top--; };
    element top(**void**)
    { **return** s[top-1]; };
};