# Read: Class 35 Read: 35 -Graphs

* A graph is a non-linear data structure that can be looked at as a collection of vertices (or nodes) potentially connected by line segments named edges

* Vertex - A vertex, also called a “node”, is a data object that can have zero or more adjacent vertices.
* Edge - An edge is a connection between two nodes.
* Neighbor - The neighbors of a node are its adjacent nodes, i.e., are connected via an edge.
* Degree - The degree of a vertex is the number of edges connected to that vertex.

## Directed vs Undirected

* Undirected Graphs: is a graph where each edge is undirected or bi-directional. This means that the undirected graph does not move in any direction.

* Directed Graphs (Digraph) : is a graph where every edge is directed.

## Complete vs Connected vs Disconnected

* Complete Graphs : is when all nodes are connected to all other nodes.
* A connected graph is graph that has all of vertices/nodes have at least one edge.
* A disconnected graph is a graph where some vertices may not have edges.

## Acyclic vs Cyclic

* An acyclic graph is a directed graph without cycles.
* A cycle is when a node can be traversed through and potentially end up back at itself.
* A directed acyclic graph is also called a DAG. 
* A Cyclic graph is a graph that has cycles.
* A cycle is defined as a path of a positive length that starts and ends at the same vertex.


## Graph Representation

* We represent graphs through:
    1. Adjacency Matrix
    2. Adjacency List

* An Adjacency matrix is represented through a 2-dimensional array. If there are n vertices, then we are looking at an n x n Boolean matrix
* An adjacency list is a collection of linked lists or array that lists all of the other vertices that are connected.


## Weighted Graphs

* A weighted graph is a graph with numbers assigned to its edges. These numbers are called weights.

## Traversals

* Breadth First
* Depth First

## Real World Uses of Graphs

* GPS and Mapping
* Driving Directions
* Social Networks
* Airline Traffic
* Netflix uses graphs for suggestions of products