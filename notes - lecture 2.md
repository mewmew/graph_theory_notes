# Lecture 2

adam

## Table of Contents

Graph theory: Per Alexandersson

* Terminology
* Spanning trees
* Connections
* Euler tours
* Hamiltonian cycles

## Terminology

Walk - visit same vertex and edges multiple times

Trail - walk with no repeated edges

Path - walk with no repeated verticies (and thus no repeated edges)

Cycle - Path visiting at least 3 verticies and the edge (x_0, x_n)
   - (no repeated verticies)

Circuit - closed trail (may have repeated verticies)

Tour - Circuit.

## Spanning tree

A tree that contains every vertex of the graph.

* Prim's algorithm for finding minimal spanning trees.
   - greedy algorithm
   - start with any smallest edge.
   - extend with the cheapest edge, over and over.
* Kruskal's algorithm for finding minimal spanning trees.
   - pick the cheapest edge globally, as long as we don't construct a cycle.
