# Module 03
# Sets, Relations & Functions

*The formal foundations of permission systems, type checking, and cryptographic permutations.*

---

## Module Overview

In Modules 01 and 02 we built the logic of security claims. But logic needs
*things to reason about* — collections of users, domains of inputs, sets of
permissions, spaces of cryptographic keys. Set theory provides the precise
language for all of these.

This module builds set theory from the ground up, formalises the two-argument
predicates of Module 02 as binary relations, and culminates in bijective functions —
the mathematical heart of symmetric cryptography. By the end you will be able to
reason formally about permission inheritance, access control matrices, trust-level
partitions, and why hash collisions are mathematically unavoidable.

**Security thread:** Access Control & Policy Logic `[AC]` · Cryptographic Structure `[CS]`

---

## Prerequisites

| Module | What you need from it |
|---|---|
| Module 02 | Predicates and quantifiers — the domain $D$ in $\forall x \in D$ is a set |
| Module 01 | The five connectives — set operations mirror Boolean algebra laws |

---

## What You Will Be Able To Do

By the end of this module you will be able to:

- Define sets using roster, set-builder, and predicate notation
- Apply all six set operations: $\cup$, $\cap$, $\setminus$, complement, $\triangle$, $\times$
- Compute the power set and explain the exponential explosion it represents
- Verify De Morgan's Laws for sets
- Define a binary relation and classify it as reflexive, symmetric, antisymmetric, and/or transitive
- Compute equivalence classes and interpret them as security zones
- Classify functions as injective, surjective, or bijective
- Prove a function is a bijection using the formal definition
- Construct and apply the inverse of a bijection
- Explain why the Pigeonhole Principle guarantees hash collisions
- Compute the birthday bound and explain why short hash outputs are insecure

---

## Unit Roadmap

### Unit 01 — Sets and Operations
*Estimated time: 55–65 min*

The formal set as an unordered collection of distinct elements. Three notation
styles. Six operations with security interpretations: union as role merging,
intersection as mandatory access control, difference as privilege gap, complement
as attack surface, symmetric difference as policy change delta, Cartesian product
as the full access matrix space. Power set as the exponential explosion that makes
per-user permission assignment unscalable — and RBAC the natural solution.

**The key question this unit answers:** How do I formally describe collections of
objects, permissions, and inputs?

---

### Unit 02 — Relations and Functions
*Estimated time: 60–70 min*

Binary relations as the formal counterpart of two-argument predicates. The four
structural properties — reflexive, symmetric, antisymmetric, transitive — each
with a security interpretation. Equivalence relations as partitions: trust levels,
network segments, and RBAC roles are all equivalence classes. Functions as
total, deterministic relations. Injective, surjective, and bijective classification
— with hash collision resistance (injective) and PRNG coverage (surjective) as the
security motivations.

**The key question this unit answers:** How do I formally model the structure
*between* objects — permissions, trust, access, and reachability?

---

### Unit 03 — Bijections and Cryptographic Permutations
*Estimated time: 65–75 min*

Bijection proofs, composition of bijections, permutations as bijections from a set
to itself. The Substitution-Permutation Network as a composition of bijective layers.
Key spaces as sets: AES-128 has $2^{128}$ keys, each corresponding to a distinct
bijection on the 128-bit block space. The Pigeonhole Principle: if the domain is
larger than the codomain, collisions are unavoidable. The birthday bound: you expect
a collision after $\sqrt{|\text{output set}|}$ evaluations — the reason short hash
outputs are insecure.

**The key question this unit answers:** What is the formal mathematical structure
of an encryption function, and why must it be a bijection?

---

## The Module Arc

The three units form one argument:

> **The objects security systems operate on are sets. The policies governing those
> objects are relations. The cryptographic primitives securing those policies are
> bijective functions.**

Unit 01 provides the vocabulary. Unit 02 provides the structure between objects.
Unit 03 connects set theory to the cryptography that protects everything above it.

---

## Security Thread Connection

| Set / relation / function concept | Security meaning |
|---|---|
| Permission set | $\text{perms}(r) = \{\text{read}, \text{write}, \ldots\}$ |
| $A \setminus B$ (difference) | Privilege gap — what $A$ can do that $B$ cannot |
| Equivalence class | Security zone; RBAC role; trust level |
| Bijection $E_\kappa$ | Encryption function — must be invertible |
| $\|\mathcal{K}\| = 2^k$ | Key space size — determines brute-force resistance |
| Pigeonhole Principle | Hash collisions mathematically guaranteed |
| Birthday bound $\sqrt{n}$ | Expected collision queries for output space size $n$ |

---

*fischer³ Education · [learn.fischer3.net](https://learn.fischer3.net)*
