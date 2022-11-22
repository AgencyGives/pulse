A side effect is an intentional modification of the value of a location in memory to affect the global state of the machine. Side effects can change the behavior of a [[function]] across multiple [[function]] calls. Functions that return a value that solely depends on the values of the parameters passed to it is called side-effect free.

Example of a [[function]] with a side effect:

sum = 0;
**int** accumulate(**int** value)
{ sum += value;
  **return** sum;
}