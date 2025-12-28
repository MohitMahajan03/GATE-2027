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

* Maximum degree of a vertex in a Simple Graph is less than or equal to n-1 where n is the number of vertices present in the graph

#### Theorem 4

* Maximum number of edges in a Simple Graph is less than or equal to [n(n-1)/2].

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

* Visualization is important to check if the Simple graph is possible or not. <b>Important:</b> Refer <a href = "Discrete Mathematics/Graph Theory 03  Class Notes.pdf">Slide 6: Graph Theory 03 Class Notes.pdf </a>
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

* Cycle graph (Cn) (n >= 3): The degree of all vertices is 2, and the edges connect the vertices as a cycle.
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

* Complete Bipartite graph (Km,n): |V1| = m, |V2| = n.
    * All vertices of |V1| should be connected to all vertices of |V2|.
    * Ex: K 2,4

* Star Graph (K 1,n-1): It is an extended version of the complete bipartite graph.

* <b>Important</b> Complement Graph: (G<sup>c</sup>/ G<sup>|</sup>): V(G) = V(G<sup>c</sup>), In complement graphs, edges present in normal graph are absent and vice-versa.
    * When we super impose G and G<sup>c</sup>, we get a complete graph.
    * e(G) + e(G<sup>c</sup>) = Kn; e(G) + e(G<sup>c</sup>) = (n(n-1))/2 => e(G<sup>c</sup>) = (n(n-1))/2 - e(G).

* Line Graph (L(G)): Check PPT

    * Maximum degree of Line Graph of a Complete Graph of Kn is 2(n-2). Check notes for proof.

* Isomorphic graph (Same property Graph): G1, G2 are isomorphic to each other, if:
    * They have same number of vertices
    * They have same number of edges
    * They have the same degree sequence.
    * And they have 1:1 correspondence of vertices and edges.

    * Note!: If any 2 graphs satisfy the above 3 conditions they are not necessarily isomorphic. Always check incidence properties.

* Self-complement graph: (G is Equivalent to G<sup>c</sup>): When a graph is complement to it's own graph.
    * Total number of edges in self-complement graph = n(n-1)/4
    * For a self complement graph n or (n-1) should be divisible by 4.
    * C<sub>5</sub> is the only cycle graph which is self compelement

* Hypercube(Q<sub>n</sub>): Where "n" is number of bits.
    * V(Q<sub>n</sub>) = 2<sup>n</sup>
    * E(Q<sub>n</sub>) = n * 2<sup>n-1</sup>

* Petersen Graph

#### Theorem 7

* A Bipartite graph does not contain odd length cycle

#### Connected and Disconnected Graphs

* Walk : Going through the graph by alternating sequences of vertices and edges, such that we can repeat the vertices and edges as many times,
* Trail : Going through the graph by alternating sequences of vertices and edges, such that vertices can be repeated as many times but not edges.
* Path : Going through the graph by alternating sequences of vertices and edges, such that no repetition of vertices or edges can take place

#### Connected Graph

* When a path is available between all pair of vertices, then we call it as a connected graph
* If K = 1 then it is connected graph

* If G is disconnected then G<sup>c</sup> will be connected
* But if G is connected then G<sup>c</sup> may not be connected

#### Theorem 8

* If δ(G) >= (n-1)/2 then it is a connected graph.
* Vice Versa is not true.

#### Range of Edges

* For K = 1
    * n - 1(connected) <= e <= n(n-1)/2 (max)
    * Which also means, G is connected and does not contain a cycle. Therefore G is an Acyclic graph
    * Unique path exists between all pair of vertices.

* For K >= 2
    * Minimum number of edges for a disconnected graph = n - k
    * n-k <= e <= [(n-k)(n-k+1)]/2

#### Convert connected graph to a Disconnected graph

* Cut edge / bridge : Removal of a single edge from a graph will make graph as a disconnected graph.
    * If cut edge exists, then it can never be a part of a cycle.
    * If every edge is a cut edge, then it is a minimally connected graph or a tree.

* Cut edge set / Cut set: Removal of set of edges from a Graph that will make the graph as a disconnected graph

* Cut Vertex/ Cut Point/ Articulation Point : Removal of a single vertex from a graph that will make the graph as a disconnected graph.

* Cut Vertex set : Removal of set of vertices from a graph will make the graph a disconnected graph. 

* If cut edge exist does not mean that cut vertex also exists
* If cut vertex exist does not mean that cut edge also exists

#### Edge Connectivity (λ(G))

* Removal of minimum number of edges from a Graph that will make a graph as a Disconnected Graph.

* λ(G) <= δ(G)

* λ(G) <= δ(G) <= (2e/n) <= Δ(G) <= (n-1)

#### Vertex Connectivity (K(G))

* Removal of minimum number of Graph will that will make the graph disconnected or isolated vertex

* K(G) <= λ(G)

* K(G) <= λ(G) <= δ(G) <= (2e/n) <= Δ(G) <= (n-1)

#### Eulerian Graphs

* Closed Trail : It is a trail + starting and ending vertex is the same.
* Euler Circuit: It is a Closed trail such that it should cover all the edges exactly once.
* If a graph satisfies the euler circuit, then it is called as a Euler Graph/ Eulerian Graph.

* Euler line/ Euler path: It is a Open trail such that it should cover all edges exactly once

#### Theorem 9

* Graph is Eulerian iff the graph is a connected graph and Degrees of all vertices are even.

#### Theorem 10

* Graph is semi-Eulerian iff it contains exactly 2 odd degree vertices

#### Hamiltonian Graphs

* Closed Path: Path which consists of same starting and ending vertex.
* Hamiltonian Circuit: A closed path which covers all the vertices exactly once.
* Every Hamiltonian circuit contains Hamiltonian Path, but the vice versa is not true.

#### Coloring

* Properly Coloring: Adjacent vertex should not have same color.

#### Chromatic Number (X(G))

* Paint every vertex with minimum number of colors such that adjacent vertices are not of the same number.

* Chromatic number of trivial graph is always 1
* Chromatic number of tree (Acyclic connected graph) is always 2
* Every tree is always 2 chromatic.
* X(Cn) = 2 for n = even
* X(Cn) = 3 for n = odd
* X(Wn) = 3 for n = odd
* X(Wn) = 4 for n = even
* X(Kn) = n
* X(Qn) = 2
* X(Bipartite Graph) [connected] = 2

#### Independent Set (Refer Graph Theory Part 12)

* Set of non adjacent vertices (Refer Graph Theory Part 12)
* Maximal Independent Set : Independent set such that no new vertex can be added to the set.
* Independence Number β(G): Number of elements in the Maximal independent set
* β(G) >= n.(X(G))

#### Independent Edge Set / Matching set (Refer Graph Theory Part 12)

* It is a set of non adjacent edges.
* Maximal Matching set: It is a matching set such that we cannot add new edge into the set.
* Matching number m(G): Number of edges present in the larges maximal matching set.

#### Planarity

* Planar Graph: If we can draw a graph over a plane without intersection of it's edges.
* Non-Planar Graph : If we cannot draw a graph over a plane without intersection of it's edges.

* K5 is the first non planar graph: also called as Kerotski 1st graph (with minimum number of vertices)
* K3,3 is the first non planar graph: also called as Kerotski 2nd graph (with minimum number of edges)

#### Region / Faces

* When we draw planar graph over a plane (embedding), it creates a region / face (r / f).
* There are open region, which is unbounded and infinite
* There are closed, bounded and finite region.
* Euler formula -> n - e + f = 2 for connected planar graphs
* Euler formula -> n - e + f = K + 1 where K is number of components of Disconnected graph  

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
