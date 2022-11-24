A [topological ordering](https://en.wikipedia.org/wiki/Topological_sorting "Topological sorting") of a directed acyclic graph: every [edge](https://en.wikipedia.org/wiki/Edge_(graph_theory) "Edge (graph theory)") goes from earlier in the ordering (upper left) to later in the ordering (lower right). A directed graph is acyclic if and only if it has a topological ordering.

![[Pasted image 20221123203937.png]]

Adding the red edges to the blue directed acyclic graph produces another DAG, the [transitive closure](https://en.wikipedia.org/wiki/Transitive_closure "Transitive closure") of the blue graph. For each red or blue edge _u_ → _v_, v is [reachable](https://en.wikipedia.org/wiki/Reachability "Reachability") from u: there exists a blue path starting at u and ending at v.

![[Pasted image 20221123204018.png]]

## **Advantages of the DAG in Compiler Design**
-   Code can be represented by a Directed acyclic graph that describes the inputs and outputs of each of the arithmetic operations performed within the code; this representation allows the compiler to perform common subexpression elimination efficiently.
-   Several programming languages describe value systems that are linked together by a directed acyclic graph. When one value changes, its successors are recalculated; each value in the DAG is evaluated as a function of its predecessors.

https://www.geeksforgeeks.org/directed-acyclic-graph-in-compiler-design-with-examples/
