# Why Your AI Security Team Needs to Think Like Mathematicians

![fischer³ Education logo](assets/favicon3.svg "f3_logo")

## The Hidden Gap in AI Security Talent — and What to Do About It

### Robert Fischer

---

There is a conversation happening in every organisation that has deployed, or is planning to deploy, AI systems in production. It usually starts with a reasonable question from a manager or executive: *"Is this secure?"*

The honest answer, in most organisations today, is that nobody knows precisely. Not because the engineers are incompetent. Because the field of AI security is moving faster than the educational infrastructure that trains people to reason about it, and most of the people doing the work are operating on instinct rather than on formal, verifiable foundations.

This article is about that gap — what it costs, why it exists, and a specific way to close it.

---

### The Problem Is Not Skill. It Is Vocabulary.

Experienced security engineers know how to find vulnerabilities. Experienced ML engineers know how to build models. But when an AI system is attacked — when a language model is manipulated through a crafted prompt, when an AI agent calls a tool it was never supposed to call, when an attacker finds a path through your network that your team never considered — the tools needed to *reason precisely* about what happened, and to *prove* that a fix actually prevents recurrence, are different from the tools either group was trained on.

Those tools are mathematical. And they are not exotic or inaccessible — they are the discrete mathematics taught in first-year computer science programs. The problem is that they were never taught with AI security as the context.

A security engineer who learned set theory in 2005 was shown how to operate on abstract collections of numbers. They were not shown that the "blast radius" of a compromised network node is formally a reachability set, that you can compute it with a ten-line algorithm, and that you can *prove* a network segment is isolated by demonstrating that no path exists between two sets of nodes. The mathematics is the same. The application — and therefore the motivation to internalise it — was invisible.

---

### What This Looks Like in Practice

Consider three scenarios that are playing out in organisations right now.

**Scenario One: The AI agent that did something unexpected.**

An AI agent integrated with internal tools took an action that fell outside its intended scope. No data was lost. Nothing was obviously exploited. But nobody could say with certainty *why* it happened, whether it could happen again, or whether the fix they applied actually addressed the root cause.

A team with formal foundations would have modelled the agent's tool-call workflow as a directed graph before deployment, verified it was acyclic (meaning it must terminate and cannot loop), and specified the authorisation policy as a formal statement that can be mechanically checked against the system's actual behaviour. The incident would not have been a mystery. The fix would have been provable.

**Scenario Two: The vulnerability that was "patched" three times.**

A web-facing API had a recurring injection vulnerability. Developers patched it twice. The third occurrence was different enough that the previous fix did not apply. The security team described it as "a different class of injection."

Injection vulnerabilities — SQL injection, command injection, prompt injection — all share the same formal structure: user-controlled content appearing in a position in the system where it is interpreted as an instruction rather than as data. An engineer who understands this formally can write a test that is not tied to any specific attack pattern, because it tests the structural property rather than the surface symptom. Patching the surface three times is expensive. Understanding the structure once is efficient.

**Scenario Three: The RSA key that nobody checked.**

An internal service was discovered to be using a 1024-bit RSA key for an API that handled sensitive data. The engineers who built it knew RSA was the right choice. They did not know that 1024-bit keys had been considered below the minimum security threshold since 2013, that the birthday attack meant their session tokens were smaller than they appeared, or that the specific mathematical structure of the key size directly determined the effort an attacker would need to break it.

This is not a careless mistake. It is a knowledge gap. The engineers knew *what* the tool was. They did not know *why* specific parameters matter, which requires understanding the underlying mathematics well enough to evaluate a configuration decision rather than just copy one from documentation.

---

### What the Course Provides

*["Logic Gates to Attack Graphs: Discrete Mathematics for AI Security"](intro.md)* is a university-level course built around this gap. Every topic — Boolean logic, graph theory, cryptography, automata — is taught through AI security applications specifically, not as abstract exercises.

By the end of the course, a practitioner can:

**State security guarantees precisely.** Not "the system validates all inputs" but a formal claim with a clear violation condition — the kind of claim that can be tested, audited, and verified, not just asserted.

**Analyse attack paths quantitatively.** Model a network or system as a weighted graph, compute the minimum-cost route an attacker would take, rank vulnerabilities by their actual effect on that cost, and produce a mathematically grounded prioritisation for remediation work.

**Verify protocol correctness.** Model a communication protocol as a state machine, prove which states are reachable and which are not, and enumerate the specific message sequences that would violate the protocol — before deployment, not after an incident.

**Evaluate cryptographic configurations.** Understand why specific key sizes, hash function output lengths, and token entropy levels either do or do not provide adequate security — not by memorising a table, but by understanding the mathematical relationship between parameters and security guarantees.

**Reason about AI-specific threats.** Prompt injection, adversarial inputs, jailbreak search spaces, agent workflow safety — all formally characterised in terms that allow systematic analysis rather than ad-hoc testing.

---

### The Business Case

Security incidents involving AI systems are qualitatively different from traditional software incidents in one important respect: the attack surface is broader and harder to enumerate by inspection alone. An AI agent that can call tools, read data, and compose responses has a much larger attack surface than a deterministic function. Reasoning about it requires mathematical tools.

The cost of a formal education is one-time. The cost of repeated incidents, missed vulnerabilities, and patch-it-again cycles is ongoing. The cost of a significant breach — regulatory, reputational, operational — is potentially existential for a product or a team.

More practically: organisations that can produce formal security specifications for their AI systems are increasingly differentiated in enterprise sales conversations, in regulatory environments that are moving toward requiring documented assurance, and in the talent market where the most capable security engineers want to work with teams that operate at this level of rigour.

---

### Who Benefits Most

The course is particularly well-suited for three categories of technical staff:

**Security engineers moving into AI/ML environments** who have strong operational instincts but find the formal reasoning behind AI-specific threats unfamiliar.

**ML engineers taking on security responsibilities** who understand how models work but have not been trained to think adversarially or to reason about system-level security properties.

**Technical leads and architects** who need to evaluate security claims, review threat models, and make build vs. buy vs. harden decisions with confidence.

The course is self-paced, freely accessible via browser, interactive through Google Colab, and available with graded exercises and ISC2 CPE credit at [courses.fischer3.net (coming soon)](https://courses.fischer3.net). The time investment is approximately 90 to 120 hours of focused study across eleven modules.

---

### The Bottom Line

The question is not whether AI systems can be built securely. They can. The question is whether your team has the vocabulary to reason about security with the precision that AI systems require — to specify what "secure" means formally, to verify it, and to prove when a change actually makes things better rather than just different.

That vocabulary exists. It is teachable. And the window in which having it is a differentiator is closing, because the organisations that invest in it now will set the standard that everyone else is eventually measured against.

---

*Logic Gates to Attack Graphs is a free, open-access course from [fischer³ Education](https://fischer3.net), part of a mathematics series for AI security practitioners. Graded exercises and ISC2 CPE certificates are available at [courses.fischer3.net (coming soon)](https://courses.fischer3.net).*
