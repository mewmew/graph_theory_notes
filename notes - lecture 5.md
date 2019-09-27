# Lecture 5

## Menger

Menger's theorem

k-edge connected <=> k edge disjoint paths \forall u,v

k-vertex connected <=> k vertex disjoint paths \forall A,B (end points)

Min-cut = max-flow

## Hall - Perfect matching

Theorem. Hall (most used theorem in Graph Theory)

\forall A |N(A)| >= |A|

<=> Perfect matching

Neighbours of A: N(A)

### Proof

Add a source and a sink, directed graph from source to sink from the A to the B side of a bipartite graph.

Maximum matching is the maximum flow.

n = number of verticies on the left side

Cut cost:

min_{over all A}    n - |A| + N(A) = max flow over all A
                                   = max matching

## König Theorem.

Vertex cover (VC):    set of verticies that touch all edges
Maximal matching:     disjoint edges

Size of vertex cover >= size of maximal matching

Königs theorem: min VC = max-matching in bipartite graph


\bar{A}   complement of A

\bar{A} and N(A) is a VC for any A.

Take the best A that makes this as small as possible, i.e. the minimum-cut.

min_{for all A}   n - |A| + |N(A)| = maximum matching


## Theorem for perfect matching on regular bipartite graphs

Theorem.

(# neighbours = r) regular if same $r$ on all verticies.

A regular bipartite graph with with n verticies on each side has a perfect matching.


Pf. Need to prove |N(A)| >= |A|

for any A:


```
.       .
.       .
A      N(A)
.       .
.       .
.       .
```

Count all edges starting in A.

r|A|

How many enter into N(A) <= r|N(A)|

Thus:
|N(A)| >= |A|

Proof done.

In fact it is the union of r perfect matchings, Induction over r.

## Augmenting paths

Augmentings paths for matching M.
