# Module 01
# Propositional Logic & Boolean Algebra

*The formal language of access control — and the algebra that simplifies it.*

---

## Module Overview

Propositional logic is the simplest formal language that can express a security
policy. Every access control rule — "admin and not suspended", "privileged
operations must be logged", "MFA required for all admins" — is a Boolean formula
waiting to be written precisely.

This module builds that language from the ground up: the five logical connectives,
the truth table as a verification tool, and Boolean algebra as a simplification
engine. By the end you will be able to read, write, and audit access control
policies in formal notation — and catch bugs that code review misses.

**Security thread:** Access Control & Policy Logic `[AC]` · Neural Network Architecture `[NN]`

---

## Prerequisites

| Module | What you need from it |
|---|---|
| Module 00 · Unit 01 | Proof techniques — direct proof, contrapositive, counterexample |

---

## What You Will Be Able To Do

By the end of this module you will be able to:

- Express any access control policy as a Boolean formula using $\neg$, $\wedge$, $\vee$, $\rightarrow$, $\leftrightarrow$
- Construct a truth table for any formula with up to four variables
- Prove logical equivalence by truth table and by algebraic law
- Detect the "missing check" class of access control bug algebraically
- Simplify a complex policy expression using Boolean algebra laws
- Convert a formula to DNF and CNF
- Identify logic gates as the hardware realisation of Boolean connectives
- Analyse the MFA bypass pattern — an OR of complementary terms that silently erases a check

---

## Unit Roadmap

### Unit 01 — Propositions and Logical Connectives
*Estimated time: 50–60 min*

Introduces atomic and compound propositions, the five connectives with their
truth tables, operator precedence, and De Morgan's Laws. The centrepiece is a
first look at an ABAC policy expressed as a Boolean formula — and the
short-circuit evaluation question that sets up Unit 02.

**The key question this unit answers:** How do I write a security policy as a
formal logical expression?

---

### Unit 02 — Truth Tables
*Estimated time: 55–65 min*

The truth table as an exhaustive verification tool. Tautologies, contradictions,
and satisfiability. Formal proof of De Morgan's Laws by truth table. The
"missing check" vulnerability — where a conjunct silently defaults to True,
erasing a security condition — fully formalised and verified computationally.

**The key question this unit answers:** How do I verify that a policy does what
I intend, for every possible input?

---

### Unit 03 — Boolean Algebra and Access Control
*Estimated time: 60–70 min*

The eleven Boolean algebra laws as a policy refactoring toolkit. Algebraic
simplification of compound policy expressions. DNF and CNF normal forms.
The MFA bypass — a four-step algebraic derivation showing how an OR of
complementary terms silently removes a security check. Logic gates as the
hardware realisation of Boolean connectives, connecting software policy to
TPU and GPU architecture.

**The key question this unit answers:** How do I simplify and audit a complex
policy expression without constructing a truth table?

---

## The Module Arc

The three units form one argument:

> **Access control policy is Boolean algebra. Boolean algebra has a hardware
> realisation. Both layers are vulnerable to the same class of formal error.**

Unit 01 gives you the vocabulary. Unit 02 gives you the verification method.
Unit 03 gives you the simplification tools — and the proof that the complement
law erases an MFA check in four algebraic steps, regardless of whether it appears
in software policy or a circuit gate.

---

## Security Thread Connection

| Concept | [AC] Access Control | [NN] Hardware |
|---|---|---|
| $\wedge$ (AND) | All conditions must hold | AND gate in logic circuit |
| $\vee$ (OR) | Any condition grants access | OR gate |
| $\neg$ (NOT) | Exclusion clause | NOT gate |
| Complement law | MFA check erased | Complementary signals cancel |
| DNF | All paths to access | Truth table of combinational circuit |

---

*fischer³ Education · [learn.fischer3.net](https://learn.fischer3.net)*
