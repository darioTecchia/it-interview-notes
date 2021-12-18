# Graphs
## Depth-First Search (DFS)
Depth-first search (DFS) is an algorithm for traversing or 
searching tree or graph data structures. One starts at 
the root (selecting some arbitrary node as the root in 
the case of a graph) and explores as far as possible 
along each branch before backtracking.

![Algorithm Visualization](https://upload.wikimedia.org/wikipedia/commons/7/7f/Depth-First-Search.gif)

## Breadth-First Search (BFS)
Breadth-first search (BFS) is an algorithm for traversing 
or searching tree or graph data structures. It starts at
the tree root (or some arbitrary node of a graph, sometimes 
referred to as a 'search key') and explores the neighbor
nodes first, before moving to the next level neighbors.

![Algorithm Visualization](https://upload.wikimedia.org/wikipedia/commons/5/5d/Breadth-First-Search-Algorithm.gif)

## Kruskal’s Algorithm - finding Minimum Spanning Tree (MST) for weighted undirected graph
Kruskal's algorithm is a minimum-spanning-tree algorithm which 
finds an edge of the least possible weight that connects any two 
trees in the forest. It is a greedy algorithm in graph theory 
as it finds a minimum spanning tree for a connected weighted 
graph adding increasing cost arcs at each step. This means it 
finds a subset of the edges that forms a tree that includes every
vertex, where the total weight of all the edges in the tree is 
minimized. If the graph is not connected, then it finds a 
minimum spanning forest (a minimum spanning tree for each 
connected component).

![Kruskal Algorithm](https://upload.wikimedia.org/wikipedia/commons/5/5c/MST_kruskal_en.gif)

![Kruskal Demo](https://upload.wikimedia.org/wikipedia/commons/b/bb/KruskalDemo.gif)

A demo for Kruskal's algorithm based on Euclidean distance.

### Minimum Spanning Tree

A **minimum spanning tree** (MST) or minimum weight spanning tree 
is a subset of the edges of a connected, edge-weighted 
(un)directed graph that connects all the vertices together, 
without any cycles and with the minimum possible total edge 
weight. That is, it is a spanning tree whose sum of edge weights 
is as small as possible. More generally, any edge-weighted 
undirected graph (not necessarily connected) has a minimum 
spanning forest, which is a union of the minimum spanning 
trees for its connected components.

![Minimum Spanning Tree](https://upload.wikimedia.org/wikipedia/commons/d/d2/Minimum_spanning_tree.svg)

A planar graph and its minimum spanning tree. Each edge is 
labeled with its weight, which here is roughly proportional 
to its length.

![Minimum Spanning Tree](https://upload.wikimedia.org/wikipedia/commons/c/c9/Multiple_minimum_spanning_trees.svg)

This figure shows there may be more than one minimum spanning 
tree in a graph. In the figure, the two trees below the graph 
are two possibilities of minimum spanning tree of the given graph.

## Dijkstra Algorithm - finding the shortest paths to all graph vertices from single vertex
Dijkstra's algorithm is an algorithm for finding the shortest 
paths between nodes in a graph, which may represent, for example, 
road networks. 

The algorithm exists in many variants; Dijkstra's original variant 
found the shortest path between two nodes, but a more common 
variant fixes a single node as the "source" node and finds 
shortest paths from the source to all other nodes in the graph, 
producing a shortest-path tree.

![Dijkstra](https://upload.wikimedia.org/wikipedia/commons/5/57/Dijkstra_Animation.gif)

Dijkstra's algorithm to find the shortest path between `a` and `b`.
It picks the unvisited vertex with the lowest distance, 
calculates the distance through it to each unvisited neighbor, 
and updates the neighbor's distance if smaller. Mark visited
(set to red) when done with neighbors.

## Bellman-Ford Algorithm - finding the shortest paths to all graph vertices from single vertex
The Bellman–Ford algorithm is an algorithm that computes shortest 
paths from a single source vertex to all of the other vertices 
in a weighted digraph. It is slower than Dijkstra's algorithm 
for the same problem, but more versatile, as it is capable of 
handling graphs in which some of the edge weights are negative 
numbers.

![Bellman-Ford](https://upload.wikimedia.org/wikipedia/commons/2/2e/Shortest_path_Dijkstra_vs_BellmanFord.gif)

### Complexity
Worst-case performance `O(|V||E|)`
Best-case performance	`O(|E|)`
Worst-case space complexity `O(|V|)`

## Detect Cycle - for both directed and undirected graphs (DFS and Disjoint Set based versions)
In graph theory, a **cycle** is a path of edges and vertices 
wherein a vertex is reachable from itself. There are several 
different types of cycles, principally a **closed walk** and 
a **simple cycle**.

### Definitions
A **closed walk** consists of a sequence of vertices starting 
and ending at the same vertex, with each two consecutive vertices
in the sequence adjacent to each other in the graph. In a directed graph,
each edge must be traversed by the walk consistently with its direction: 
the edge must be oriented from the earlier of two consecutive vertices 
to the later of the two vertices in the sequence. 
The choice of starting vertex is not important: traversing the same cyclic 
sequence of edges from different starting vertices produces the same closed walk.

A **simple cycle may** be defined either as a closed walk with no repetitions of 
vertices and edges allowed, other than the repetition of the starting and ending 
vertex, or as the set of edges in such a walk. The two definitions are equivalent 
in directed graphs, where simple cycles are also called directed cycles: the cyclic 
sequence of vertices and edges in a walk is completely determined by the set of 
edges that it uses. In undirected graphs the set of edges of a cycle can be 
traversed by a walk in either of two directions, giving two possible directed cycles 
for every undirected cycle. A circuit can be a closed walk allowing repetitions of 
vertices but not edges; however, it can also be a simple cycle, so explicit 
definition is recommended when it is used.

### Example
![Cycles](https://upload.wikimedia.org/wikipedia/commons/e/e7/Graph_cycle.gif)

A graph with edges colored to illustrate **path** `H-A-B` (green), closed path or 
**walk with a repeated vertex** `B-D-E-F-D-C-B` (blue) and a **cycle with no repeated edge** or 
vertex `H-D-G-H` (red)

#### Cycle in undirected graph
![Undirected Cycle](https://www.geeksforgeeks.org/wp-content/uploads/cycleGraph.png)

#### Cycle in directed graph
![Directed Cycle](https://cdncontribute.geeksforgeeks.org/wp-content/uploads/cycle.png)

## Prim’s Algorithm - finding Minimum Spanning Tree (MST) for weighted undirected graph
In computer science, **Prim's algorithm** is a greedy algorithm that 
finds a minimum spanning tree for a weighted undirected graph. 

The algorithm operates by building this tree one vertex at a 
time, from an arbitrary starting vertex, at each step adding 
the cheapest possible connection from the tree to another vertex.

![Prim's Algorithm](https://upload.wikimedia.org/wikipedia/commons/f/f7/Prim%27s_algorithm.svg)

Prim's algorithm starting at vertex `A`. In the third step, edges 
`BD` and `AB` both have weight `2`, so `BD` is chosen arbitrarily. 
After that step, `AB` is no longer a candidate for addition 
to the tree because it links two nodes that are already 
in the tree.

### Minimum Spanning Tree
A **minimum spanning tree** (MST) or minimum weight spanning tree 
is a subset of the edges of a connected, edge-weighted 
(un)directed graph that connects all the vertices together, 
without any cycles and with the minimum possible total edge 
weight. That is, it is a spanning tree whose sum of edge weights 
is as small as possible. More generally, any edge-weighted 
undirected graph (not necessarily connected) has a minimum 
spanning forest, which is a union of the minimum spanning 
trees for its connected components.

![Minimum Spanning Tree](https://upload.wikimedia.org/wikipedia/commons/d/d2/Minimum_spanning_tree.svg)

A planar graph and its minimum spanning tree. Each edge is 
labeled with its weight, which here is roughly proportional 
to its length.

![Minimum Spanning Tree](https://upload.wikimedia.org/wikipedia/commons/c/c9/Multiple_minimum_spanning_trees.svg)

This figure shows there may be more than one minimum spanning 
tree in a graph. In the figure, the two trees below the graph 
are two possibilities of minimum spanning tree of the given graph.

## Topological Sorting - DFS method
In the field of computer science, a topological sort or 
topological ordering of a directed graph is a linear ordering 
of its vertices such that for every directed edge `uv` from 
vertex `u` to vertex `v`, `u` comes before `v` in the ordering.

For instance, the vertices of the graph may represent tasks to 
be performed, and the edges may represent constraints that one 
task must be performed before another; in this application, a 
topological ordering is just a valid sequence for the tasks.

A topological ordering is possible if and only if the graph has
no directed cycles, that is, if it is a [directed acyclic graph](https://en.wikipedia.org/wiki/Directed_acyclic_graph) 
(DAG). Any DAG has at least one topological ordering, and algorithms are 
known for constructing a topological ordering of any DAG in linear time.

![Directed Acyclic Graph](https://upload.wikimedia.org/wikipedia/commons/c/c6/Topological_Ordering.svg)

A topological ordering of a directed acyclic graph: every edge goes from 
earlier in the ordering (upper left) to later in the ordering (lower right). 
A directed graph is acyclic if and only if it has a topological ordering.

### Example

![Topologic Sorting](https://upload.wikimedia.org/wikipedia/commons/0/03/Directed_acyclic_graph_2.svg)

The graph shown above has many valid topological sorts, including:

- `5, 7, 3, 11, 8, 2, 9, 10` (visual left-to-right, top-to-bottom)
- `3, 5, 7, 8, 11, 2, 9, 10` (smallest-numbered available vertex first)
- `5, 7, 3, 8, 11, 10, 9, 2` (fewest edges first)
- `7, 5, 11, 3, 10, 8, 9, 2` (largest-numbered available vertex first)
- `5, 7, 11, 2, 3, 8, 9, 10` (attempting top-to-bottom, left-to-right)
- `3, 7, 8, 5, 11, 10, 2, 9` (arbitrary)

### Application

The canonical application of topological sorting is in 
**scheduling a sequence of jobs** or tasks based on their dependencies. The jobs 
are represented by vertices, and there is an edge from `x` to `y` if 
job `x` must be completed before job `y` can be started (for 
example, when washing clothes, the washing machine must finish 
before we put the clothes in the dryer). Then, a topological sort 
gives an order in which to perform the jobs.

Other application is **dependency resolution**. Each vertex is a package
and each edge is a dependency of package `a` on package 'b'. Then topological
sorting will provide a sequence of installing dependencies in a way that every
next dependency has its dependent packages to be installed in prior.

## Bridges - DFS based algorithm
In graph theory, a **bridge**, **isthmus**, **cut-edge**, or **cut arc** is an edge 
of a graph whose deletion increases its number of connected components. Equivalently, 
an edge is a bridge if and only if it is not contained in any cycle. A graph is said 
to be bridgeless or isthmus-free if it contains no bridges.

![Bridges in graph](https://upload.wikimedia.org/wikipedia/commons/d/df/Graph_cut_edges.svg)

A graph with 16 vertices and 6 bridges (highlighted in red)

![Bridgeless](https://upload.wikimedia.org/wikipedia/commons/b/bf/Undirected.svg)

An undirected connected graph with no cut edges

![Bridges in graph](https://www.geeksforgeeks.org/wp-content/uploads/Bridge1.png)

![Bridges in graph](https://www.geeksforgeeks.org/wp-content/uploads/Bridge2.png)

![Bridges in graph](https://www.geeksforgeeks.org/wp-content/uploads/Bridge3.png)

## Strongly Connected Components - Kosaraju's algorithm
A directed graph is called **strongly connected** if there is a path 
in each direction between each pair of vertices of the graph. 
In a directed graph G that may not itself be strongly connected, 
a pair of vertices `u` and `v` are said to be strongly connected 
to each other if there is a path in each direction between them.

![Strongly Connected](https://upload.wikimedia.org/wikipedia/commons/5/5c/Scc.png)

Graph with strongly connected components marked

## Travelling Salesman Problem - shortest possible route that visits each city and returns to the origin city
The travelling salesman problem (TSP) asks the following question: 
"Given a list of cities and the distances between each pair of 
cities, what is the shortest possible route that visits each city 
and returns to the origin city?"

![Travelling Salesman](https://upload.wikimedia.org/wikipedia/commons/1/11/GLPK_solution_of_a_travelling_salesman_problem.svg)

Solution of a travelling salesman problem: the black line shows 
the shortest possible loop that connects every red dot.

![Travelling Salesman Graph](https://upload.wikimedia.org/wikipedia/commons/3/30/Weighted_K4.svg)

TSP can be modelled as an undirected weighted graph, such that 
cities are the graph's vertices, paths are the graph's edges, 
and a path's distance is the edge's weight. It is a minimization 
problem starting and finishing at a specified vertex after having 
visited each other vertex exactly once. Often, the model is a 
complete graph (i.e. each pair of vertices is connected by an 
edge). If no path exists between two cities, adding an arbitrarily 
long edge will complete the graph without affecting the optimal tour.
