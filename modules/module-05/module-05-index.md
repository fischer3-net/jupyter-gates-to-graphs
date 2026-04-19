# Module 05
# Graph Theory II — Algorithms

*From structure to action: computing reachability, finding the cheapest attack path,
and proving that segmentation works.*

---

## Module Overview

Module 04 gave you the vocabulary for describing networked systems as graphs.
Module 05 gives you the algorithms to answer the questions that matter:
*Can the attacker reach the target?* *What is the cheapest path?*
*How many edges must be removed to block all paths?*

The three units build a complete operational pipeline: BFS/DFS compute the full
blast radius, Dijkstra finds the minimum-cost attack path on a CVSS-weighted graph,
and the min-cut theorem gives the formal lower bound on how many network controls
are needed for complete isolation — with a proof that every segmentation control
directly raises the attacker's cost.

**Security thread:** Attack Graphs & Reachability `[AG]`

---

## Prerequisites

| Module | What you need from it |
|---|---|
| Module 04 · Unit 01–02 | Graphs, directed graphs, adjacency, paths, reachability |
| Module 02 · Unit 02 | Formal security properties — the $\forall / \exists$ audit structure |
| Module 00 · Unit 01 | Proof by contrapositive — $t \notin R(s)$ proves lateral movement blocked |

---

## What You Will Be Able To Do

By the end of this module you will be able to:

- Implement BFS and DFS from scratch and trace their execution step by step
- Compute the full reachability set $R(s)$ from any entry point
- Prove or disprove a formal isolation guarantee using BFS
- Implement Dijkstra's algorithm and trace every relaxation step
- Convert CVSS scores to attacker cost weights and build a weighted attack graph
- Compute the minimum-cost attack path from any entry point to any target
- Rank vulnerabilities by patch impact — the cost increase from removing each edge
- State and prove the Edge Removal Theorem
- Compute the minimum edge cut using max-flow and verify Menger's theorem
- Implement a greedy segmentation strategy and quantify its security improvement
- Produce a formal isolation proof: $\delta_w^{(G-C)}(s,t) = \infty$

---

## Unit Roadmap

### Unit 01 — Graph Traversal and Reachability
*Estimated time: 55–65 min*

BFS and DFS from scratch with full step logging. BFS correctness proof: shortest
hop distances are optimal. DFS edge classification: back edges signal cycles —
the formal structure of persistence loops. The reachability audit: for every
entry point, compute $R(s)$; intersect with targets; produce formal findings with
witnesses. The connection back to Module 00: $t \notin R(s)$ is a proof by
contrapositive that lateral movement to $t$ from $s$ is blocked.

**The key question this unit answers:** What systems can the attacker reach from
a given entry point — and how do I formally prove that a target is unreachable?

---

### Unit 02 — Shortest Path and Attack Graphs
*Estimated time: 60–70 min*

Weighted shortest path problem. CVSS scores converted to attacker costs:
$w = 10 - \text{CVSS} + 0.1$. Dijkstra's algorithm with relaxation step logging.
The full enterprise attack graph with 16 CVSS-weighted edges. Minimum-cost path
from both entry points — the insider threat bar chart makes quantitatively visible
how much cheaper the insider path is. Patch impact analysis: rank every
vulnerability by the cost delta its removal produces. The highest-delta edges are
the defender's highest-return investments.

**The key question this unit answers:** Which path would the attacker actually
take — and which vulnerabilities are worth patching first?

---

### Unit 03 — Zero-Trust Segmentation
*Estimated time: 65–75 min*

The Edge Removal Theorem: removing any critical path edge strictly increases the
minimum attack cost — proved formally and verified computationally. Zero-trust
segmentation defined as systematic edge removal until all paths are blocked.
Greedy segmentation: iteratively remove the highest-delta edge, tracking cost
at each step. Minimum edge cut via max-flow: the theoretical lower bound on
the number of controls needed. Menger's theorem verified: min cut equals the
number of edge-disjoint attack paths. The module closes with a formal isolation
proof: after applying the min cut, $\delta_w^{(G-C)}(s,t) = \infty$ for all
entry/target pairs.

**The key question this unit answers:** What is the minimum number of network
controls needed to completely block the attack — and how do I prove it works?

---

## The Module Arc

The three units form one operational pipeline:

> **Compute what is reachable. Find the cheapest path to reach it. Remove the
> minimum controls to block it. Prove it is blocked.**

This is the complete mathematical foundation of network attack graph analysis —
from the first edge in the graph to the formal isolation guarantee.

---

## Security Thread Connection

| Algorithm concept | Security meaning |
|---|---|
| BFS reachability $R(s)$ | Full blast radius of initial compromise |
| BFS distance $d(s,t)$ | Minimum hops for lateral movement |
| $t \notin R(s)$ | Isolation guarantee — lateral movement provably blocked |
| DFS back edge | Cycle — persistence loop |
| Dijkstra $\delta_w(s,t)$ | Minimum attacker effort to reach target |
| Patch delta $\Delta w(e)$ | Security value of patching one vulnerability |
| Min edge cut $\lambda$ | Minimum network controls for full isolation |
| $\delta_w = \infty$ | Zero-trust ideal — complete isolation achieved |

---

*fischer³ Education · [learn.fischer3.net](https://learn.fischer3.net)*
