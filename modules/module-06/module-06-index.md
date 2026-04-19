# Module 06
# Trees & Recursion

*The formal structure of hierarchical decisions — from parsing to classification.*

---

## Module Overview

Trees are everywhere in computing — in file systems, expression evaluators, parsers,
classifiers, and compiler internals. They are also the precise structure behind
two security-critical problems: understanding how an interpreter assigns meaning to
an input (parse trees), and how an access control classifier makes a decision
(decision trees).

Module 06 formalises trees as the most constrained special case of graphs —
connected, acyclic, with exactly $|V|-1$ edges — then builds upward to parse trees
and decision trees, connecting formal grammar theory to prompt injection and Boolean
policy logic to adversarial path-finding.

**Security thread:** Protocol Verification `[PV]` · Adversarial Enumeration `[AE]` · Access Control `[AC]`

---

## Prerequisites

| Module | What you need from it |
|---|---|
| Module 04 · Unit 01–02 | Graphs, DAGs, DFS — trees are a special case of both |
| Module 01 · Unit 01–02 | Boolean connectives and truth tables — decision trees are truth tables in tree form |

---

## What You Will Be Able To Do

By the end of this module you will be able to:

- State the five equivalent definitions of a tree and prove $|E| = |V| - 1$ by induction
- Identify root, parent, child, leaf, depth, and height in any rooted tree
- Perform pre-order, in-order, and post-order traversals and explain their evaluation semantics
- Compute BFS and DFS spanning trees of a network and explain which is preferred for security analysis
- Define a context-free grammar and build the parse tree for any string in its language
- Explain why ambiguous grammars create security vulnerabilities
- Formally describe what a prompt injection attack does to a parse tree
- Build a decision tree for a multi-attribute access control policy
- Trace any input through a decision tree and verify the leaf label against a truth table
- Implement a black-box adversarial path-finder and compute the worst-case query count

---

## Unit Roadmap

### Unit 01 — Tree Definitions
*Estimated time: 50–60 min*

The five equivalent characterisations of a tree. The $|E| = |V| - 1$ equation as
a structural sanity check. Rooted tree vocabulary. Binary trees and their height
bounds: $\lceil \log_2 n \rceil$ for balanced, $n-1$ for degenerate — the difference
between $O(\log n)$ and $O(n)$ operations. Pre-order, in-order, and post-order
traversals on a Boolean policy expression tree, connecting traversal order to policy
evaluation order. BFS and DFS spanning trees compared — BFS gives the minimum-hop
attack tree.

**The key question this unit answers:** What exactly is a tree, and how does
traversal order determine the semantics of evaluation?

---

### Unit 02 — Parse Trees and Prompt Injection
*Estimated time: 60–70 min*

Context-free grammars as rewrite rule systems. Parse trees as the formal record
of how an interpreter assigned structure to a token sequence. Terminals as leaf
nodes (pure data), non-terminals as internal nodes (structural roles). The key
insight: an injection attack promotes user-controlled tokens from leaf (terminal)
positions to internal (non-terminal) positions — they acquire structural authority
they should not have. Side-by-side parse trees for a clean prompt and an injected
one, with the `InjectedInstruction` subtree highlighted. A formal tree-based
injection detector implementing the Module 02 audit pattern.

**The key question this unit answers:** What formally changes in the parse tree
structure when a prompt injection succeeds — and how do I detect it?

---

### Unit 03 — Decision Trees and Security Classifiers
*Estimated time: 60–70 min*

Decision trees as truth tables in tree form: internal nodes are Boolean tests,
leaves are classification labels. The ABAC policy $A \wedge T \wedge \neg S$ from
Module 01 re-expressed as a decision tree, with all 8 inputs traced and verified
against the Module 01 truth table. A multi-label classifier (ALLOW / DENY /
ESCALATE / LOG_AND_ALLOW / QUARANTINE) for a four-attribute policy. The adversarial
path-finder: a black-box oracle attack that queries the classifier to find the ALLOW
leaf, confirming that $2^n$ queries suffice for $n$ Boolean features.

**The key question this unit answers:** How does an attacker probe a decision
tree classifier to find the path to ALLOW — and what does tree depth tell me
about adversarial search cost?

---

## The Module Arc

The three units form one argument:

> **Trees are the formal structure of hierarchical decisions. Whether that decision
> is how to parse an expression, how to interpret a prompt, or whether to grant
> access — understanding the tree structure is understanding the decision.**

Unit 01 gives you the foundation. Unit 02 shows what injection does to a parse tree.
Unit 03 shows what an adversary does to a decision tree. Both attacks are the same
operation: finding a path to a desired leaf by manipulating the tree structure.

---

## Security Thread Connection

| Tree concept | `[PV]` Parse Trees | `[AE]` Decision Trees |
|---|---|---|
| Terminal (leaf) | Pure data token | Leaf label: ALLOW / DENY |
| Non-terminal (internal) | Structural role — can produce subtrees | Boolean test: one policy condition |
| Injection | User token at non-terminal position | Adversarial input satisfying ALLOW path |
| Ambiguous grammar | Parser differential vulnerability | Multiple interpretations of same input |
| Tree depth | Grammar nesting depth | Number of conditions checked; search cost |
| Post-order traversal | Bottom-up evaluation order | Policy engine evaluation sequence |

---

*fischer³ Education · [learn.fischer3.net](https://learn.fischer3.net)*
