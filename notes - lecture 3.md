# Lecture 3

## P vs NP

P poly time (decision problems)
NP non-deterministic poly time

Yes-answers have a certificate that can be checked in poly time.

Examples:

Hamiltonian path: certificate is the hamiltonian path.
not k-connected: certificate is k-1 verticies that is disconnected.

## K-connectivity

For any (v, w) give k disjoint paths that connect v and w.

If we have three disjoint paths, then removing two verticies would not be enough to make the graph disconnected.

## P = NP?

P <= NP

P = NP?

Everybody P != NP.

## NP-complete problems

NP-complete problems are problems in NP such that if they are in P then P=NP.

An NP-complete problem can be used to translate *any* NP problem into a P problem in poly time?

Favourite problem:

Satisfiability of 3 CNF (conjunctive normal form) formulas - the 3 refers to clauses of 3:

(x_1 OR x_2 OR x_3) AND (NOT x_1 OR NOT X_2 OR NOT x_4) AND (x_1 OR x_2 OR x_4)

Cook-Levin theorem (1971 and 1973): 3-SAT is NP-complete.

## Theorem: Directed Hamiltonian path is NP-complete.

Proof: Take a formula on 3-CNF, compute graph G

Given a formula with n boolean variables m clauses of size 3.

![Hamiltonain paths](inc/lecture_3/hamiltonian_3cnf.png)

Going left to right on level i "<=>" X_i = true

Add nodes corresponding to clauses that can be visited if that clause is true.

Hamiltonian path of basic graph

x_i false --->--- on i'th level

x_i false ---<---

Visit each clause vertex where you pass variable that satisfies the clause.

If you can solve Hamiltonan path, then you can solve 3-SAT.

The other way around also holds, by Cook-Levin.

Conclusion: We will not have necessary & sufficient conditions for Hamiltonicity.

(unless P=NP)
