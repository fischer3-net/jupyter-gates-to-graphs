# Module 10
# Capstone — Formal Threat Model for an Agentic AI System

*Every tool in the course, applied to a single real system.*

---

## Module Overview

The capstone is the course's payoff. Every module has built one piece of a formal
toolkit: propositional logic for policy analysis, predicate logic for security
specifications, set theory for permission structures, graph theory for reachability
and attack paths, trees for structural analysis, combinatorics for attack surface
sizing, number theory for cryptographic reasoning, and automata for protocol
verification.

In Module 10, all of those pieces are applied together to a single target: an
agentic AI system consisting of an orchestrating agent, multiple MCP servers,
tool endpoints, a user-facing API, and a persistent data store. The output is
a complete formal threat model — not a checklist, but a mathematically precise
document that proves which security properties hold and identifies the witnesses
where they do not.

**Security thread:** All threads — `[AC]` `[AG]` `[CS]` `[NN]` `[PV]` `[AE]`

---

## Prerequisites

All prior modules. The capstone is designed to be completed after all other modules
are done. If you are arriving here from a specific module, the table below shows
which sections of the capstone draw most heavily on each module.

| Module | Where it appears in the capstone |
|---|---|
| Module 01 | Access control policy formalisation — ABAC formulas for tool permissions |
| Module 02 | Formal security property specification and audit |
| Module 03 | Permission set algebra; key space analysis |
| Module 04 | Agent tool call graph structure; DAG verification |
| Module 05 | Attack path analysis; minimum-cost path to target; segmentation |
| Module 06 | Prompt injection parse tree analysis; classifier decision trace |
| Module 07 | Attack surface sizing; adversarial input enumeration |
| Module 08 | TLS and key exchange security parameters |
| Module 09 | MCP handshake state machine; protocol violation detection |

---

## What You Will Produce

By completing this module you will have:

- A **formal system model**: the agentic system as a directed graph with typed nodes
  (agent, servers, tools, data stores) and annotated edges (trust relationships, data flows)
- A **permission specification**: all tool-call authorisation conditions expressed as
  Boolean formulas in $\wedge$, $\vee$, $\neg$ with formal violation conditions
- A **formal security property set**: injection safety, privilege bounds, session
  integrity, and tool call safety all written as predicate logic statements with
  their $\exists$-violation conditions
- An **attack graph analysis**: CVSS-weighted edges, minimum-cost attack path
  from the external API to the persistent data store, patch impact ranking
- A **formal audit report**: structured findings with formal property statements,
  violation conditions, and specific witnesses for every finding
- A **protocol verification**: the MCP handshake as a state machine, with all
  transition invariants verified
- A **segmentation proof**: a minimum edge cut that achieves $\delta_w = \infty$
  for all entry-to-target pairs, with formal isolation proof

---

## Unit Roadmap

### Unit 01 — Formal Threat Model Construction
*Estimated time: 90–120 min*

The complete threat modelling pipeline applied to the target system. Each section
of the notebook directly invokes the formal tools from one or more earlier modules.
The notebook is structured as a professional deliverable — the kind of document
you would present to a security review board or include in a PhD research proposal.

**The key question this unit answers:** Given a complete agentic AI system, how
do I apply every formal tool from this course to produce a mathematically rigorous
threat model?

---

## The Module Arc

The capstone has one argument — the argument of the whole course:

> **The formal mathematics of discrete structures is not background preparation
> for AI security. It is the precise language in which AI security properties
> are stated, proved, and refuted. Every claim in this threat model is either
> formally verified or identified as an open finding requiring remediation.**

The capstone is the proof of that claim.

---

## Course Summary — What You Have Built

| Module | Core capability |
|---|---|
| 00 | Formal proof techniques — the toolkit for every argument |
| 01 | Access control as Boolean algebra — read and audit any policy |
| 02 | Security properties as predicate logic — formalise and audit any requirement |
| 03 | Permissions as sets, trust as relations, encryption as bijections |
| 04 | Networks and AI architectures as graphs — reachability and blast radius |
| 05 | Attack paths, minimum cost, and formal isolation proofs |
| 06 | Parsing, injection structure, and decision tree adversarial analysis |
| 07 | Attack surface sizing — exact counts for any enumerable threat space |
| 08 | Cryptographic primitives from first principles — RSA, DH, TLS |
| 09 | Protocol state machines and regex safety — formal verification of input handling |
| 10 | Full formal threat model — all tools, one system, one document |

---

*fischer³ Education · [learn.fischer3.net](https://learn.fischer3.net)*
