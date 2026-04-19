# Module 08
# Number Theory & Modular Arithmetic

*The mathematics that makes encryption possible — and the reasons it is hard to break.*

---

## Module Overview

Every secure channel in AI deployment — TLS connections to APIs, encrypted model
weights, key agreement protocols between agents — rests on a small set of number-
theoretic facts. These facts are not magic; they follow from divisibility, modular
arithmetic, and properties of prime numbers that are provable with the tools from
this course.

Module 08 builds number theory from divisibility up through the Chinese Remainder
Theorem, Fermat's Little Theorem, and the mathematical structure of RSA key
generation. By the end you will understand not just *that* RSA works, but *why*
— and why the hardness of factoring is the security assumption everything depends on.

**Security thread:** Cryptographic Structure `[CS]`

---

## Prerequisites

| Module | What you need from it |
|---|---|
| Module 03 · Unit 02–03 | Functions, bijections, modular inverse as a bijection |
| Module 00 · Unit 01 | Proof by contradiction — used to prove uniqueness of modular inverses |
| Module 07 · Unit 01 | Counting — the size of $\mathbb{Z}_n^*$ (Euler's totient function) |

---

## What You Will Be Able To Do

By the end of this module you will be able to:

- Apply divisibility rules and compute GCD using the Euclidean algorithm
- Perform arithmetic in $\mathbb{Z}_n$ — addition, multiplication, and modular exponentiation
- State Fermat's Little Theorem and use it to speed up modular exponentiation
- Compute modular inverses using the Extended Euclidean Algorithm
- Define Euler's totient function $\phi(n)$ and compute it for prime products
- Explain the RSA key generation procedure from first principles
- Prove that RSA decryption recovers the original plaintext (using Euler's theorem)
- Explain why breaking RSA requires factoring $n$ — the computational hardness assumption
- Describe the Diffie-Hellman key exchange and the discrete logarithm problem
- Analyse the security parameters (key length, prime size) of deployed cryptographic systems

---

## Unit Roadmap

### Unit 01 — Divisibility and Modular Arithmetic
*Estimated time: 60–70 min*

Divisibility, GCD, and the Euclidean algorithm. The integers modulo $n$:
$\mathbb{Z}_n$ as a set with addition and multiplication. Modular inverses and
when they exist — a number $a$ has an inverse mod $n$ iff $\gcd(a, n) = 1$.
The Extended Euclidean Algorithm for computing inverses efficiently. Fermat's
Little Theorem: $a^{p-1} \equiv 1 \pmod{p}$ for prime $p$ — the foundation of
fast modular exponentiation and a key step in the RSA correctness proof.

**The key question this unit answers:** How does arithmetic work in a finite
universe of numbers — and what properties make certain numbers special?

---

### Unit 02 — Cryptographic Primitives
*Estimated time: 65–75 min*

Euler's totient function and Euler's theorem. RSA key generation step by step:
choose primes $p$ and $q$, compute $n = pq$ and $\phi(n)$, choose public exponent
$e$, compute private key $d = e^{-1} \pmod{\phi(n)}$. RSA encryption and
decryption as modular exponentiation. Proof of correctness: $m^{ed} \equiv m
\pmod{n}$ follows from Euler's theorem. The factoring hardness assumption:
knowing $n$ but not $p$ and $q$ makes computing $\phi(n)$ — and thus $d$ — hard.
Diffie-Hellman key exchange and the discrete logarithm problem. Connection to
TLS: how these primitives underpin every secure API connection an AI system makes.

**The key question this unit answers:** How does RSA actually work, why is it
secure, and what mathematical hardness assumption does it rest on?

---

## The Module Arc

The two units form one argument:

> **Secure communication is modular arithmetic. The security comes from number-
> theoretic hardness: factoring large numbers is computationally infeasible with
> known algorithms. Understanding the mathematics makes the security assumptions
> explicit — and their limits visible.**

Unit 01 builds the arithmetic foundation. Unit 02 assembles it into RSA and
Diffie-Hellman, connecting the abstract number theory to the TLS connections
that protect every deployed AI system.

---

## Security Thread Connection

| Number theory concept | Cryptographic meaning | Security implication |
|---|---|---|
| $\gcd(a, n) = 1$ | $a$ is invertible mod $n$ | Private key exists iff $\gcd(e, \phi(n)) = 1$ |
| Modular exponentiation | RSA encrypt/decrypt | $O(\log e)$ multiplications — efficient |
| Fermat's Little Theorem | Fast primality testing | Large prime generation for RSA |
| Euler's theorem $a^{\phi(n)} \equiv 1$ | RSA correctness proof | Decryption recovers plaintext |
| Factoring hardness | RSA security assumption | Breaking RSA requires factoring $n = pq$ |
| Discrete logarithm | Diffie-Hellman security | Forward secrecy in TLS |

---

*fischer³ Education · [learn.fischer3.net](https://learn.fischer3.net)*
