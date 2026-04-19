# Module 09
# Automata & Formal Languages

*The formal machinery of protocols, state machines, and input validation.*

---

## Module Overview

A finite automaton is the simplest formal model of a system that changes state
in response to inputs. That description fits an MCP handshake, a TLS session, a
login flow, a rate limiter, and the regex engine validating API inputs — all of them.

Module 09 builds automata theory from finite state machines up through regular
expressions and the Pumping Lemma. The security applications are direct and
concrete: the MCP protocol modelled as a state machine with violation conditions
defined formally, and the ReDoS vulnerability analysed as a structural property
of the regex engine's NFA construction.

**Security thread:** Protocol Verification `[PV]` · Adversarial Enumeration `[AE]`

---

## Prerequisites

| Module | What you need from it |
|---|---|
| Module 06 · Unit 01–02 | Trees and parse trees — automata process strings that grammars generate |
| Module 04 · Unit 02 | DAGs and directed graphs — automata are directed graphs with states as vertices |
| Module 02 · Unit 01 | $\forall / \exists$ — protocol correctness is a $\forall$ claim over all inputs |

---

## What You Will Be Able To Do

By the end of this module you will be able to:

- Define a finite automaton formally as a 5-tuple $(Q, \Sigma, \delta, q_0, F)$
- Trace any input string through a DFA and determine acceptance
- Construct an NFA for a given language and explain the subset construction for DFA conversion
- Model a protocol as a finite automaton with clearly defined accepting and error states
- Identify state machine violations — transitions that the protocol specification forbids
- Write and analyse regular expressions as NFA descriptions
- Identify catastrophic backtracking (ReDoS) vulnerability in a regex pattern
- Explain why some languages cannot be recognised by any finite automaton (Pumping Lemma)
- Connect regex-based input validation to the formal language it accepts

---

## Unit Roadmap

### Unit 01 — Finite Automata
*Estimated time: 55–65 min*

DFAs: states, alphabet, transition function, start state, accepting states. Tracing
input strings step by step. NFAs: multiple possible transitions, $\epsilon$-transitions,
non-deterministic acceptance. The subset construction: converting an NFA to an
equivalent DFA. Regular languages as the class of languages recognised by finite
automata. Why the automaton model captures exactly the systems that can be
implemented with bounded memory — and why that bound matters for protocol design.

**The key question this unit answers:** What is a finite state machine, and what
class of systems can it model?

---

### Unit 02 — Protocol State Machines
*Estimated time: 60–70 min*

Protocols as finite automata: each message is an input symbol, each protocol
phase is a state, and protocol correctness is the claim that the automaton
never enters an error state. The MCP handshake modelled as a formal state
machine — states for `UNINITIALISED`, `NEGOTIATING`, `AUTHENTICATED`,
`ACTIVE`, and `ERROR`, with transitions for each protocol message. State
machine violations defined as transitions into the error state from incorrect
prior states. The invariant from Module 00 reappears: a correctly implemented
protocol is an automaton where the error state is unreachable. Visualised as
a directed graph (connecting back to Module 04) with violation edges highlighted.

**The key question this unit answers:** How do I formally specify a protocol
and verify that an implementation never reaches an illegal state?

---

### Unit 03 — Regular Expressions and ReDoS
*Estimated time: 60–70 min*

Regular expressions as a notation for finite automata. The three core operations:
concatenation, union ($|$), and Kleene star ($*$). NFA construction from a regex
(Thompson's construction). How a backtracking regex engine explores the NFA:
depth-first with backtracking on failure. Catastrophic backtracking (ReDoS):
patterns like `(a+)+` that cause exponential state explosion on certain inputs.
A concrete ReDoS example with timing measurements. The formal characterisation:
ReDoS occurs when the NFA has exponentially many paths through an ambiguous
repetition structure. Defence: prefer DFA-based engines or rewrite patterns to
eliminate ambiguity.

**The key question this unit answers:** What does a regex actually compute —
and how can an attacker craft an input that makes the engine run for seconds,
minutes, or indefinitely?

---

## The Module Arc

The three units form one argument:

> **Protocol correctness and input validation safety are both questions about
> what a state machine can and cannot reach. Formal automata theory gives you
> the vocabulary to state these properties precisely and the tools to verify them.**

Unit 01 builds the formal model. Unit 02 applies it to protocol verification.
Unit 03 applies it to the regex engines that validate every API input — and
shows how a structural property of the NFA becomes a denial-of-service vulnerability.

---

## Security Thread Connection

| Automata concept | `[PV]` Protocol Verification | `[AE]` Regex / Input Validation |
|---|---|---|
| State $q \in Q$ | Protocol phase (uninitialised, active, …) | Engine position in NFA |
| Accepting state $F$ | Protocol successfully completed | Input matches the pattern |
| Error state | Protocol violation — illegal transition | Regex engine reports no match |
| Transition $\delta(q, a)$ | Response to receiving message $a$ in state $q$ | Engine step on character $a$ |
| Unreachable error state | Protocol invariant holds — no violations | Pattern is safe from ReDoS |
| Reachable error state | Protocol violation possible — finding | ReDoS vulnerability exists |

---

*fischer³ Education · [learn.fischer3.net](https://learn.fischer3.net)*
