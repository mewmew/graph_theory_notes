# Lecture 4 - flows

Per Alexandersson

It is easier to prove things about matches if we have information about flow!

A flow is an assignment, a function on directed edges f(x, y) = -f(y, x) \in Z (integers). (x, y) \in V^2.

A pair of verticies (x, y) has a direction, an edge does not (according to the book).

If f(x, y) > 0 this is the amount of flow (e.g. water) leaving x going to y.

The total of incoming water should be the same as the total of outgoing.

![flow graph](inc/lecture_4/flow.png)

Kirchhoff's law (same amount of incoming as outgoing).

## Circulation

We have a flow f.

f(x, y) = -f(y, x) for all (x, y) \in V^2

Kirchhoff's law holds for every vertex in circulation?

\sum_{(v, x) \in V^2}(f(v, x)) = \sum_{(y,v) \in V^2}(f(y, v))     for all v \in V

<=>

\sum_{e \in E, v,(v,x) \in e \forall x}(f(e)) = 0

x, y \subseteq V

->
F(X, Y) = {set edegs starting in X, ending in Y}


Measures how much water is flowing from X to Y:

   Define f(x, y) := \sum_{(x,y) \in F(X, Y)}(f(x, y))

Amount of water flowing from X to X.

   f(x, x) = 0

Every edge is counted twice, once in each direction with opposite signs, so the total has to be zero.

_
x
\bar{x} = complement of x.

f(x, \bar{x}) = 0

Compute the flow out for every vertex. All the internal edges are going to cancel.

f(x, V) = 0    (x to everything by Kirchhoff's law is 0)

f(x, x \union \bar{x}) = f(x, x) + f(x, \bar{x})
f(x, V) = 0 + f(x, \bar{x})
0 = f(x, \bar{x})

## Networks

N(G, S, t, c)   c = capacuty, c(x, y) >= 0 for all (x, y) \in V^2

c(x, y) : V^2 -> N_0

How much flow we allow on each edge.

A flow on N is a function f such that

* f(x, y) = -f(y, x)
* f(v, V) = 0  for all v \ in V \{s, t}
* f(x, y) <= c(x, y)

f(s, v) >= 0
f(v, t) >= 0

## Cut

A *cut* is a set S \subseteq V, s \in S, t \in \bar{S}

Capacity of a cut:

Define c(S, \bar{S}) as before.

Flow across the cut is the same as the flow out of the source.
f(s, \bar{s}) = f({s}, V) = |f|

Value of f.

The total amount of water flowing from left to right over the cut is the same as the outgoing amount from the source s.

![cut](inc/lecture_4/cut.png)


Want to find f that maximizes |f|

Max flowing cut theorem.

   f(S, \bar{s}) <= c(S, \bar{S})    for all cuts S.

The flow that maximizes this happens exactly when we can find equality.

Max-flow = min-cut

## Ford-Foulkerson alg.

Step 1:
![Ford-Foulkerson. step 1](inc/lecture_4/ford-folkersan.png)

Edge is saturated, cannot push more from s to b

The direction of a flow could flip with this algorithm.

Step 2:
![Ford-Foulkerson. step 2](inc/lecture_4/ford-folkersan_step_2.png)

We do not follow paths that are already saturated. We follow paths where we can increase the flow.

## Matchings in bipartite graphs

![matching in bipartite graph](inc/lecture_4/matchings_in_bipartite_graphs.png)

Matching as flow.

Connect a source to the nodes of the left side of the bipartite graph and the nodes of the right side of the bipartite graph to a sink.

![matching_as_flow](inc/lecture_4/matching_as_flow.png)
