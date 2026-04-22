# Module 00
# Orientation & Proof Techniques

*Why formal reasoning is not optional in security engineering.*

---

## Module Overview

This module is not a warm-up. It is the foundation that every subsequent module
builds on. Security engineering makes universal claims — "every input is validated",
"no process exceeds its privilege bound", "all privileged operations are logged" —
and universal claims require formal proof or a counterexample to settle.

Module 00 gives you the five proof techniques that appear throughout the course,
introduces the concept of a system invariant, and makes the adversarial asymmetry
precise: proving a universal claim requires reasoning about all cases; disproving it
requires exactly one counterexample.

**Security thread:** Access Control & Policy Logic `[AC]` · Attack Graphs & Reachability `[AG]`

---

## Prerequisites

None. This is the starting point.

---

## What You Will Be Able To Do

By the end of this module you will be able to:

- Construct a **direct proof** of a simple security claim, citing each step
- Apply **proof by contrapositive** — start from a failure condition and derive the structural cause
- Use **proof by contradiction** — assume the bad state is reachable and derive an impossibility
- Produce a **counterexample** to decisively refute a universal security claim
- Define a system **invariant** and reason about whether it is preserved by every state transition
- Identify the adversarial asymmetry: prove $\forall x,\; P(x)$ requires all cases; disprove it needs one

---

## Unit Roadmap

### Unit 01 — Proof Techniques for Security Reasoning
*Estimated time: 50–60 min*

The five core techniques introduced through security-flavoured examples:
transitivity of RBAC role permissions (direct proof), TLS certificate validity
(contrapositive), uniqueness of decryption keys (contradiction), input length
as a security property (counterexample), and privilege level bounds (invariant).
Three Python demonstrations: automated counterexample search over odd integers
with composites flagged in red, invariant monitoring comparing a safe run against
a privilege-escalation bug, and a side-by-side flowchart of all three proof strategies.

**The key question this unit answers:** What are the formal tools for making
a security argument rigorous — and where does each one reappear later in the course?

---

## The Module Arc

Module 00 is one unit with one argument:

> **A security guarantee is a formal claim. Formal claims require proof. The five
> techniques here are the machinery behind every proof in this course and in the
> security research literature.**

The module is intentionally short. Its purpose is to name the tools before
they are needed — so that when a direct proof appears in Module 03, a contrapositive
in Module 05, and an invariant in Module 09, the structure is already familiar.

---

## Where These Techniques Reappear

| Technique | Later application |
|---|---|
| Direct proof | Module 03 · Unit 03: bijection proof for cryptographic permutations |
| Contrapositive | Module 05 · Unit 01: $t \notin R(s)$ proves lateral movement blocked |
| Contradiction | Module 08 · Unit 02: uniqueness of modular inverses for RSA |
| Counterexample | Module 01 · Unit 02: one truth-table row violates an access control policy |
| Invariant | Module 09 · Unit 02: protocol state machine never enters illegal state |

---

*fischer³ Education · [courses.fischer3.net (coming soon)](https://courses.fischer3.net)*
