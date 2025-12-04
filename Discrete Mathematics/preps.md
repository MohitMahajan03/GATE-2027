# Discrete Mathematics 8-10 marks

* Aptitude (Analytical + logical approach) is the foundation of discrete mathematics.

## Introduction to Discrete Mathematics

* Set Theory 2-4 marks
    * Sets and relations
    * Functions
    * Group Theory

* Graph Theory 2-4 marks
* Mathematical Logic 2-4 marks
    * Predicate Logic
    * Propositional Logic

* Combinatorics 2-4 marks

### Pre-requisites

* Permutation
* Combination
* Binomial Expansion

### Graph Theory

* Every Graph is made up of <b>vertices</b> and <b>edges</b>
* G = (V, E) : Graph = ({Set of Vertices} , {Set of Edges}), where, V = {v1, v2, v3, ...} and E = {e1, e2, e3, ...}
* Vertices are also called order and edges are also called as size.
* Each edge should be associated with a pair of unordered vertices (Which results in a non directed graph)
* End vertices: A vertex with degree exactly one, meaning it is connected to the rest of the graph by a single edge.
* Loop : If an edge is connected to the same vertex then it's called a loop.
* Degree / Valency: The number of edges incident on a vertex (Degree contributed by self loop = 2) Also called as number of welding points.
* If a degree of a vertex is odd, then it's called a odd degree vertex, If a degree of a vertex is even, then it's called a even degree vertex.
* Parallel edges: If 2 or more edges are associated with same vertices then we call them as parallel edges.
* Any vertex having degree = 1 is called as a pendant vertex
* Graphs can have 0 edges also, but has to have vertices.

#### Categories of Graphs

1. Simple Graph - No parallel edges and no loops
2. Multi Graph - Only parallel edges are present but no self loops
3. Pseudo Graph - Both parallel edges and loops are present.

#### Handshaking Theorem

* Sum of Degrees of all vertices = 2 * number of edges
* Therefore number of Sum of Degrees of all vertices is always even
* Number of odd degree vertices in a graph are always even

#### Theorem 2

* Number of odd degree vertices will always be even.
* Proof:
</br>

Let {o1, o2, o3,...} be a set of degrees of vertices which are odd and {e1, e2, e3, ...} be a set of degrees of vertices which are even </br>

{o1+o2+o3+...} + {e1+e2+e3+...} = Even number </br>
we know that even + even = even and odd + odd = even,</br>
Therefore, the set {o1, o2, o3, ...} should have even number of vertices only.

#### Theorem 3

* Maximum degree in a Simple Graph is less than or equal to n-1 where n is the number of vertices present in the graph

#### Theorem 4

* Maximum number of edges in the a Simple Graph is less than or equal to [n(n-1)/2].

#### Theorem 5

* Total number of Simple Graphs that are possible with any number of vertices is equal to 2<sup>e</sup> where e is the number of maximum edges that can be assigned to the graph.

* For example: if the number of vertices of a graph = 4, then maximum number of edges = [4(3)/2] = 6. Now number of Simple Graphs = 2<sup>6</sup> = 64.

* This can also be written as,  2<sup>[n(n-1)/2]</sup>.

* Now, this using combinatorics can be written as <sup>[n(n-1)/2]</sup>C<sub>e</sub>
* Therefore, if we have to find total graphs for 4 vertices with atleast 2 edges, then the answer will be = <sup>6</sup>C<sub>2</sub> + <sup>6</sup>C<sub>3</sub> + <sup>6</sup>C<sub>4</sub> + <sup>6</sup>C<sub>5</sub> + <sup>6</sup>C<sub>6</sub>
* And if the question is flipped, if we have to find total graphs for 4 vertices with atmost 2 edges, then the answer will be = <sup>6</sup>C<sub>0</sub> + <sup>6</sup>C<sub>1</sub> + <sup>6</sup>C<sub>2</sub>

#### Theorem 6

* Minimum Degree of a graph [δ(G)]
* Maximum Degree of a graph [Δ(G)]
* Average Degree = (Sum of all Degrees)/(Total number of vertices) = [2e/n]
* In most graphs we get δ(G) <= (2e/n) <= Δ(G)

#### Degree Sequence

* Writing degrees of all vertices either in increasing or in decreasing order (GATE standard is to write in decreasing order)

* Where is it applied? For Ex: What will be the total number of edges for the graph od Degree Sequence 5, 2, 2, 2, 2, 1? 
    * Ans: sum of degree of all vertices = 2e. 5 + 2 + 2 + 2 + 2 + 1 = 14. Therefore, e = 7.

* Visualization is important to check if the Simple graph is possible or not. <b>Important:</b> Refer <a href = "Discrete Mathematics/Graph Theory 03  Class Notes.pdf"> Slide 6: Graph Theory 03 Class Notes.pdf</a>

* The other way to check if the degree sequence gives a simple graph or not is by plotting the graph.
    * This can also be done by checking number of odd degree vertex and also maximum number of edges possible, and also checking for pendant vertices. <b>Refer</b><a href = "Discrete Mathematics/Graph Theory 03  Class Notes.pdf"> Slide 7: Graph Theory 03 Class Notes.pdf </a>

#### Havel - Hakimi Theorem

* This theorem is used to verify if a graph is possible for large Degree Sequence
* This algorithm helps reduce the size of the Degree Sequence to a more easy format which can be used to verify if the graph can be formed or not.
*<b>Important</b> Refer <a href = "Discrete Mathematics/Graph Theory 03  Class Notes.pdf"> Slide 13: Graph Theory 03 Class Notes.pdf</a>

#### Types of Graphs

* Complete Graph (Kn)(n >= 1): The number of vertices >= 1. And Degrees of all vertices must be n - 1.
    * Sum of degrees of all vertices = 2e. Then n(n-1) = 2e. Therefore e = [n(n-1)/2]
    * [δ(G)] = (2e/n) = [Δ(G)] = (n-1)

* Regular Graph: Degree of all graphs are same
    * [δ(G)] = (2e/n) = [Δ(G)]

* Therefore all complete graphs are regular graphs

* Cycle graph (Cn) (n >= 3): The degree of all vertices is 2, and the edges are connect the vertices as a cycle.
    * Therefore, sum of degree of all vertices = n * 2 = 2e, then n = e.
    * Number of vertices = number of edges.
    * All Cycle graphs are regular

* Cyclic Graph: It is a graph containing a cycle.

* Wheel Graph (Wn) (n >= 4):  It is a cycle graph with a spokes attached to the center node
    * The degree of the center node is always n-1
    * The degree of the remaining vertices are always 3
    * Therefore sum of degrees of all vertices = (n-1) + (n-1)(3) = 2e => e = 2(n-1)

* Bipartite Graph: It's a graph of 2 partitions
    * The Vertices of these graphs can be divided into 2 partitions, such that all the edges will be from 1 set to another set, but not in same set.
    * Note: Any graph having odd length cycle as a sub graph can never be a bipartite graph
    * 2 or more isolated vertices also form a bipartite graph

#### Theorem 7

* A Bipartite graph does not contain odd length cycle


#### Important questions

1. <a href = "GATE-2027/Discrete Mathematics/Graph Theory 02  Class Notes.pdf">Page 17, Problems on Theorem 1 and others (Graph Theory 02)</a>, <a href = https://github.com/MohitMahajan03/GATE-2027/blob/main/Discrete%20Mathematics/Graph%20Theory%2002%20%20Class%20Notes.pdf> Github </a>
2. <a href = "GATE-2027/Discrete Mathematics/Graph Theory 03  Class Notes.pdf">Page 14, Problems on Havel - Hakimi Theorem and others (Graph Theory 03)</a>

### Sets

* It is a well defined, <b><u>unordered</u></b> <b><u>distinct</u></b> collection of elements (Doesn't matter if they have any meaning or not.). </br> A = {1,2,3} = {2,1,3}</br> B = {1, 2, a, b, Jan, Feb} </br>

* <b><i>Elements of a set need not be of same type.</i></b>

* C = {1, 2, {1, 2, 3}, {1, 2}, {3}}. </br> There are 5 elements in set C.

* <b><u>Cardinality</u></b> of a set is defined as number of elements in the set.</br> It is denoted by |A| given a set A.

* Cardinality of A = {1, 2, 3} is |A| = 3. </br> B = {1, {1}, {1, 2}, {1, 2, 3}, 3} is |B| = 5. </br> C = {} is |C| = 0.

* Empty set is also donated by <b>φ</b>(phi). Therefore C = φ.

<b><u>Interesting Notes</b></u></br>

If A = {{}} and B = {} is A = B? or A != B </br>

* A is a set containing an element and that element is an empty set. Therefore |A| = 1.
* But B is a set of no elements. Therefore |B| = φ
* Therefore A != B </br>

If A = {{{{}}}}, Then |A| = 1, as elements in a set are separated by ",". </br>. Therefore (lay man's terms) anything written inside the outer most {}, that set is not empty!

* A = {{1, 2}, {2, 1}} is not a set as {1, 2} == {2, 1}. Therefore A is not a set!

* Multi-set : A set where duplication of elements is allowed. Ex: {1, 2, 2, 3, 4}

* A set can be represented in 3 formats

<ol>
    <li>Roaster form or Tabular form</li>
    <li>Set-builder form</li>
    <li>Statement form</li>
</ol>

### Functions

* Function is a mapping from objects of 1 set to objects of another set.
* LHS can point at only 1 object at RHS at a time.
