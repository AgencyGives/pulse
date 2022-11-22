The concept of an ADT is based on encapsulating data and a set of operations on the data. An ADT declaration is in some respect similar to a [[class]] declaration in an object-oriented programming language, except that the abstract data type is typically declared in a module. Like a [[class]], an abstract data type has an internal state and a set of operations on its state. However, the state is global, i.e. only one "instance" exists at any one time. [[Inheritance]][![Define this term](https://www.cs.fsu.edu/~engelen/courses/COP402003/define.gif)](https://www.cs.fsu.edu/~engelen/courses/COP402003/board.html#[[[[[[[[[[inheritance]]]]]]]]]]) is not supported.

The following Modula-2 example [[stack]] abstraction is from the textbook page 124:

CONST [[stack]]_size = ...
TYPE element = ...
...
MODULE [[stack]];
IMPORT element, [[stack]]_size;
EXPORT push, pop;
TYPE
  [[stack]]_index = [1..[[stack]]_size];
VAR
  s   : ARRAY [[stack]]_index OF element;
  top : [[stack]]_index;

[[PROCEDURE]] error; ...

[[PROCEDURE]] push (elem : element);
BEGIN
  IF top = [[stack]]_size THEN
    error;
  ELSE
    s[top] := elem;
    top := top + 1;
  END;
END push;

[[PROCEDURE]] pop () : element
BEGIN
  IF top = 1 THEN
    error;
  ELSE
    top := top - 1;
    RETURN s[top];
  END;
END pop;

BEGIN
  top := 1;
END [[stack]];