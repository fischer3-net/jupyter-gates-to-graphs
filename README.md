# Logic Gates to Attack Graphs

!["fischer3_logo"](/assets/favicon3.svg "fischer3_logo")

## Discrete Mathematics for AI Security

> *The formal mathematics behind how AI systems reason, fail, and get exploited.*

A [fischer³ Education](https://fischer3.net) course. Part of the series that includes **Threat Surfaces** (multivariable calculus for AI security).

---

### What This Course Is

Discrete mathematics is not a prerequisite to get through — it is the native language of:

- How neural networks are structured as directed graphs
- How access control policies are modeled as Boolean logic
- How attack propagation is analyzed as graph reachability
- How protocol correctness is verified with logic and automata
- How prompt injection and adversarial inputs are framed as constraint satisfaction problems

Every module connects a discrete math concept to a concrete AI or AI-security application. The math is how you reason precisely about real threats.

---

### Audience

- Security practitioners upskilling into AI systems
- ML engineers who need formal foundations
- PhD-track students preparing for graduate coursework in AI or security
- Developers building on [Agent Scrutiny](https://fischer3.net) who want to understand the formal threat models

---

### Module Map

| Module | Topic | Security Thread |
|---|---|---|
| 00 | Orientation & Proof Techniques | Why formal reasoning matters in security |
| 01 | Propositional Logic & Boolean Algebra | Access control policies; logic gates in TPUs/GPUs |
| 02 | Predicate Logic & Quantifiers | Formalizing security properties |
| 03 | Sets, Relations & Functions | Type systems, input validation, cryptographic permutations |
| 04 | Graph Theory I — Structure | Neural network topology; computation graphs; DAGs |
| 05 | Graph Theory II — Algorithms | Attack graph reachability; lateral movement |
| 06 | Trees & Recursion | Decision trees; parse trees for prompt analysis |
| 07 | Combinatorics & Counting | Attack surface enumeration; adversarial example counting |
| 08 | Number Theory & Modular Arithmetic | Cryptographic primitives underlying secure AI deployment |
| 09 | Automata & Formal Languages | Protocol state machines; prompt grammar analysis |
| 10 | Capstone | Formal threat model for an agentic AI system |

---

### Security Thread Tags

`[AC]` Access Control & Policy Logic — `[AG]` Attack Graphs & Reachability — `[CS]` Cryptographic Structure — `[NN]` Neural Network Architecture — `[PV]` Protocol Verification — `[AE]` Adversarial Enumeration

---

### Technology Stack

| Component | Decision |
|---|---|
| Site generator | Jupyter Book 1.x (`>=0.15,<1.0`) |
| Deployment | GitHub Pages via GitHub Actions |
| Interactive execution | Google Colab (launch buttons) |
| Graded exercises | Moodle at `courses.fischer3.net` |

### Live Site

[gates2graphs.fischer3.net](https://gates2graphs.fischer3.net)

### Running Locally

```bash
pip install -r requirements-book.txt
jupyter-book build .
```

Open `_build/html/index.html` in your browser.

---

*fischer³ Education · [courses.fischer3.net (coming soon)](https://courses.fischer3.net)*