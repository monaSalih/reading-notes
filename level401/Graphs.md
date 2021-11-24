# Graphs

A graph is a non-linear data structure that can be looked at as a collection of vertices (or nodes) potentially connected by line segments named edges.

## Directed vs Undirected
Undirected Graphs
An Undirected Graph is a graph where each edge is undirected or bi-directional. This means that the undirected graph does not move in any direction.

## Directed Graphs (Digraph)
A Directed Graph also called a Digraph is a graph where every edge is directed.

Unlike an undirected graph, a Digraph has direction. Each node is directed at another node with a specific requirement of what node should be referenced next.

## Complete Graphs

A complete graph is when all nodes are connected to all other nodes.

## Connected
A connected graph is graph that has all of vertices/nodes have at least one edge.

## Disconnected
A disconnected graph is a graph where some vertices may not have edges.

## Acyclic Graph
An acyclic graph is a directed graph without cycles.

A cycle is when a node can be traversed through and potentially end up back at itself.


## Weighted Graphs
A weighted graph is a graph with numbers assigned to its edges


## Traversals
* Breadth First
In a breadth first traversal, you are starting at a specific vertex/node. This node must be specified when calling the BreadthFirst() method.

* Depth First
In a depth first traversal, we approach it a bit different than the way we do when working with a depth first traversal of a tree.