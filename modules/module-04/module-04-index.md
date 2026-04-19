# Module 04
# Graph Theory I — Structure

*The native language of networks, neural architectures, and agent workflows.*

---

## Module Overview

A graph is a set of objects connected by relationships. That description is simple
enough to sound abstract — but it describes enterprise networks, neural network
architectures, transformer attention mechanisms, dependency trees, and agentic AI
tool call workflows all at once.

Module 04 builds graph theory from the ground up: the formal vocabulary, directed
graphs and DAGs, and then the direct application to neural network topology. By the
end you will recognise the graph structure behind every major AI architecture and
understand why "can the attacker reach the target?" and "can the gradient reach the
weight?" are the same formal question.

**Security thread:** Attack Graphs & Reachability `[AG]` · Neural Network Architecture `[NN]`

---

## Prerequisites

| Module | What you need from it |
|---|---|
| Module 03 · Unit 02 | Binary relations — a graph edge set is a relation $E \subseteq V \times V$ |
| Module 02 · Unit 01 | $\forall / \exists$ quantifiers — connectivity is a $\forall\exists$ statement |

---

## What You Will Be Able To Do

By the end of this module you will be able to:

- Define a graph $G = (V, E)$ and compute degree, adjacency, and neighbourhood
- Distinguish walks, paths, trails, and cycles, and explain why each matters for security
- Determine whether a graph is connected and identify its connected components
- Represent an access control relation as a bipartite graph
- Define a directed graph and compute in-degree and out-degree
- Define a DAG and explain why acyclicity guarantees termination
- Compute a topological ordering using Kahn's algorithm
- Detect cycles in a directed graph using DFS back-edge classification
- Represent a feedforward neural network, transformer attention, and MCP agent workflow as graphs
- Compute the blast radius of removing a vertex from any of these graph structures

---

## Unit Roadmap

### Unit 01 — Graph Definitions
*Estimated time: 55–65 min*

Vertices, edges, degree, neighbourhood, walks, paths, cycles, and connectivity —
all from first principles. The Handshaking Lemma as a structural sanity check.
Connected components as equivalence classes of the reachability relation. Bipartite
graphs as the formal structure of access control matrices. Weighted graphs as the
language of quantified risk.

**The key question this unit answers:** What is the precise vocabulary for describing
any networked system — and what does degree tell me about security risk?

---

### Unit 02 — Directed Graphs and DAGs
*Estimated time: 60–70 min*

Directed edges, in-degree and out-degree, directed paths and reachability. DAGs
as the formal structure of anything that must terminate: package dependencies,
build systems, neural network forward passes, agent workflows. Kahn's algorithm
for topological ordering — implemented from scratch with step logging. Cycle detection
via DFS back edges. A simulated agent tool call DAG showing how a back edge creates
an infinite loop, and why DAG detection is a concrete safety check.

**The key question this unit answers:** What does it mean for a computation or
a workflow to have a guaranteed end point — and how do I verify it formally?

---

### Unit 03 — Neural Network Topology
*Estimated time: 65–75 min*

Every major neural architecture mapped to a graph structure: feedforward MLP as a
layered complete bipartite DAG, transformer attention as a complete weighted directed
graph (full) or upper-triangular DAG (causal/GPT-style), autograd computation graph
as a DAG of operations, MCP agent tool call network as a directed hierarchy with
safety constraints. Ablation as vertex removal. Blast radius computed from
reachability. Prompt injection in attention framed as adversarial modification of
the attention weight matrix.

**The key question this unit answers:** What graph structure underlies each neural
architecture — and what does that structure tell me about safety, gradient flow, and
adversarial vulnerability?

---

## The Module Arc

The three units form one argument:

> **Every system you care about — networks, software, neural models, agent workflows
> — is a graph. The properties of that graph determine what is reachable, what can
> fail, and what the blast radius looks like.**

Unit 01 gives you the vocabulary. Unit 02 adds direction and the crucial DAG
property. Unit 03 applies both to the AI architectures the rest of the course
reasons about.

---

## Security Thread Connection

| Graph concept | `[AG]` Attack Graphs | `[NN]` Neural Architecture |
|---|---|---|
| Vertex | Host / service | Neuron / operation |
| Arc $(u, v)$ | $u$ exploitable to reach $v$ | Data flows from $u$ to $v$ |
| DAG | No lateral movement loops | Forward pass terminates |
| Topological order | Lateral movement sequence | Layer execution order |
| Reachability | Can attacker reach target? | Can gradient reach weight? |
| Removing a vertex | Host takedown / segmentation | Ablation / model surgery |

---

*fischer³ Education · [learn.fischer3.net](https://learn.fischer3.net)*
