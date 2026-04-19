# Module 02
# Predicate Logic & Quantifiers

*The language of security guarantees — and the witnesses that break them.*

---

## Module Overview

Propositional logic (Module 01) talks about fixed truth values: $A$ is true or
false, period. But real security systems operate over *populations* of objects —
all users, all inputs, all network packets, all agent tool calls. To reason about
populations formally, you need predicate logic and quantifiers.

This module introduces the $\forall$ and $\exists$ quantifiers, builds the formal
vocabulary for security specifications, and culminates in a complete audit
methodology: translate any informal security requirement into a testable formal
claim, compute its violation condition, and run it against a simulated system.

**Security thread:** Access Control & Policy Logic `[AC]` · Protocol Verification `[PV]`

---

## Prerequisites

| Module | What you need from it |
|---|---|
| Module 01 | The five connectives: $\neg$, $\wedge$, $\vee$, $\rightarrow$, $\leftrightarrow$ |
| Module 00 · Unit 01 | Counterexamples and the $\forall$/$\exists$ asymmetry |

---

## What You Will Be Able To Do

By the end of this module you will be able to:

- Distinguish a predicate from a proposition and identify the domain of a quantified statement
- Write and evaluate $\forall$ and $\exists$ statements over finite domains
- Negate quantified statements correctly using the duality laws: $\neg\forall \equiv \exists\neg$
- Identify free and bound variables in a formula
- Explain why $\forall x\,\exists y$ and $\exists y\,\forall x$ describe fundamentally different systems
- Translate any informal security requirement into a formal predicate logic statement in four steps
- Compute the violation condition of any formal property
- Generate a structured formal audit report with witnesses for every finding

---

## Unit Roadmap

### Unit 01 — Predicates and Quantifiers
*Estimated time: 55–65 min*

Promotes $\forall$ and $\exists$ from background notation to first-class objects.
Predicates as functions from objects to truth values. The domain of discourse.
Universal quantifier as giant conjunction; existential as giant disjunction.
Witnesses and counterexamples. Free vs bound variables — and why an unquantified
formula is not yet a security guarantee. Nested quantifiers: why the difference
between $\forall u\,\exists k$ (per-user keys — correct) and $\exists k\,\forall u$
(shared master key — catastrophic) is a security property.

**The key question this unit answers:** How do I write a formal claim about *all*
users, *all* inputs, or *all* system states?

---

### Unit 02 — Formalizing Security Properties
*Estimated time: 60–70 min*

The application unit. The four-step translation method turns informal English
requirements into formal predicate logic statements. Four major security
properties formalised from first principles: injection safety, privilege bounds,
session integrity, and agentic AI tool call safety. A reusable `SecurityProperty`
class implements the audit engine. The formal audit runs against a simulated system
with planted vulnerabilities — Bob (admin, no MFA), Grace (suspended admin),
unlogged privileged operations, and two agent tool call violations all surface
as formal findings with explicit witnesses.

**The key question this unit answers:** How do I turn a security requirement into
something I can test, prove, or refute?

---

## The Module Arc

The two units form one argument:

> **Every security guarantee is a $\forall$ claim. Every vulnerability is the
> $\exists$ witness to its negation. Every security audit is a search for witnesses.**

Unit 01 gives you the language. Unit 02 puts it to work — on injection safety,
privilege bounds, session integrity, and agentic AI, all using the same formal
machinery and the same audit report structure.

---

## Security Thread Connection

| Formal structure | Security translation | Example |
|---|---|---|
| $\forall x \in D,\; P(x)$ | Security guarantee | "Every admin has MFA" |
| $\exists x \in D,\; \neg P(x)$ | Violation / finding | "Bob is an admin without MFA" |
| $\forall x\,\exists y\; R(x,y)$ | Per-user resource | Each user has their own key |
| $\exists y\,\forall x\; R(x,y)$ | Shared resource | One key for all — catastrophic |
| Witness | Audit finding | The specific user, input, or call that fails |

---

*fischer³ Education · [learn.fischer3.net](https://learn.fischer3.net)*
