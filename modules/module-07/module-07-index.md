# Module 07
# Combinatorics & Counting

*How many? The mathematics of attack surface enumeration and adversarial search.*

---

## Module Overview

Combinatorics answers the question *how many* — how many possible inputs exist,
how many distinct attack paths traverse a network, how many adversarial examples
fit within a given perturbation budget, how many tokens does an LLM vocabulary
contain, how large is the key space an attacker must search.

These numbers determine the feasibility of every exhaustive attack: brute-force
key search, fuzz testing, adversarial example generation, and token-space jailbreak
enumeration. Counting principles turn qualitative claims ("there are a lot of
possible inputs") into precise quantitative ones ("there are exactly $2^{128}$
possible AES keys, requiring $2^{127}$ expected guesses for a brute-force attack").

**Security thread:** Adversarial Enumeration `[AE]` · Cryptographic Structure `[CS]`

---

## Prerequisites

| Module | What you need from it |
|---|---|
| Module 03 · Unit 01 | Sets and cardinality — $|A|$, power sets, Cartesian products |
| Module 03 · Unit 03 | Key space as a set — $|\mathcal{K}| = 2^k$ |
| Module 02 · Unit 01 | $\exists$ quantifier — adversarial examples are witnesses |

---

## What You Will Be Able To Do

By the end of this module you will be able to:

- Apply the **multiplication rule**, **addition rule**, and **inclusion-exclusion principle**
- Compute permutations $P(n,k)$ and combinations $\binom{n}{k}$ and interpret them in security contexts
- State and apply the **Pigeonhole Principle** to collision resistance and birthday attacks
- Compute the size of a token vocabulary space and the number of distinct $k$-token sequences
- Enumerate attack surfaces using combinations — the number of ways to select $k$ vulnerable components
- Formalise adversarial example counting: how many inputs are within $\epsilon$ of a given input
- Compute the birthday bound for hash functions and session tokens
- Explain why the token space of an LLM is astronomically large — and what that means for jailbreak search

---

## Unit Roadmap

### Unit 01 — Counting Principles
*Estimated time: 55–65 min*

The four fundamental counting tools: multiplication rule (sequences of independent
choices), addition rule (mutually exclusive cases), inclusion-exclusion (overlapping
cases), and the Pigeonhole Principle (unavoidable collisions). Permutations and
combinations with security interpretations: password complexity, key space size,
the number of distinct session tokens before a collision is likely. Visualised
throughout with bar charts of feasibility thresholds — the point where brute-force
transitions from computationally infeasible to tractable.

**The key question this unit answers:** How do I count the exact size of an
attack surface, a key space, or an input domain?

---

### Unit 02 — Adversarial Enumeration
*Estimated time: 60–70 min*

Adversarial enumeration applies the counting toolkit to AI security. The LLM token
vocabulary: a typical vocabulary has 50,000+ tokens; a sequence of $k$ tokens
has $50000^k$ possible combinations — numbers that make exhaustive jailbreak search
impractical but targeted search very tractable. Adversarial example budgets: how
many inputs lie within $L_\infty$ distance $\epsilon$ of a given input in a
discrete feature space. Attack path enumeration: how many distinct paths exist in
an attack graph between entry and target. The birthday bound derived from first
principles: expected collision after $\sqrt{n}$ queries, connecting combinatorics
to the cryptographic security parameters of Module 03.

**The key question this unit answers:** How many adversarial examples, attack paths,
or jailbreak inputs exist within a given constraint — and what does that number
mean for the attacker's feasibility?

---

## The Module Arc

The two units form one argument:

> **Every attack that involves searching — brute force, fuzzing, adversarial
> examples, jailbreak generation — is a combinatorial enumeration problem.
> Counting gives you the exact size of the search space; that number determines
> whether the attack is feasible.**

Unit 01 gives you the counting machinery. Unit 02 applies it to the AI security
problems that define the course's threat model.

---

## Security Thread Connection

| Counting concept | `[AE]` Adversarial Enumeration | `[CS]` Cryptography |
|---|---|---|
| $n!$ (permutations) | Orderings of attack steps | Key arrangement complexity |
| $\binom{n}{k}$ (combinations) | Choosing $k$ vulnerable components from $n$ | Choosing $k$ bits to flip |
| Multiplication rule | Cartesian product of attack dimensions | Key space $= 2^k$ |
| Pigeonhole Principle | Adversarial inputs guaranteed to collide on any short hash | Hash collision unavoidability |
| Birthday bound $\sqrt{n}$ | Expected queries to find collision | Session token safety threshold |
| $50000^k$ | LLM token sequence space | Adversarial prompt search space |

---

*fischer³ Education · [learn.fischer3.net](https://learn.fischer3.net)*
