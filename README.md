# コラッツ予想と素数生存写像

**Working Paper in Number Theory — v11.0**

*Prime Survival Dynamics, Chen-type Theorem, and Connection to Known Conjectures*

Reinterprets the Collatz conjecture (3n+1 problem) as a prime survival map and establishes three main results via congruence-based proofs.

> This repository does not claim a proof of the Collatz conjecture.

---

## Erratum (2026-11-12)

This repository holds v11, an early version. Several statements in the PDF are wrong or were later retracted.

- **"If Dickson's conjecture holds, the Collatz conjecture is false" is retracted** (retracted in v16). An infinite orbit of the one-step map p -> (3p+1)/2 is not a Collatz counterexample, and no such infinite orbit exists (next item).
- **No number stays in pattern c forever.** Since (3n+1)/2 + 1 = 3(n+1)/2, a number n = 3 (mod 4) leaves pattern c after exactly v2(n+1) - 1 steps, prime or not. The conclusion "only c-P can remain in c forever" should read "nothing remains in c forever". What is open is whether arbitrarily long finite prime chains exist; for each fixed length this would follow from Dickson's conjecture.
- **Lemma 1 is wrong as stated.** Proposition 1-B (c-B exits in at most 2 steps) fails: 95 -> 143 -> 215 -> 323 -> 485 stays composite and in c for three steps. The mod-8 table is wrong for n = 7 (mod 8) (15 -> 23 = 7 mod 8). Proposition 1-A fails as stated: 63 -> 95 stays in c.
- **Lemma 4 is not proved.** The infinitude of primes p with (3p+1)/2 prime is supported by numerics and heuristics only.
- Section 7 is a skeleton; the "complete proof" attempt of v12 was withdrawn in v13.
- Unaffected: Lemma 3 (monotone growth) and the no-local-obstruction statement of Section 6.

The original text presented these as established. See `collatz-prime-survival` (v20) for the later, narrower positioning. The PDF in `paper/` is the original, uncorrected version.

---

## Overview

All positive integers are classified into four exhaustive, mutually exclusive patterns (a1, a2, b, c) based on congruence conditions mod 4. Pattern c — the only self-referential class — is further subdivided into c-P (primes), c-A (multiples of 3), and c-B (mixed composites).

The central results are:

- **Lemma 1** (c-A/c-B finite escape): c-A exits in 1 step; c-B exits in at most 2 steps — proved by congruence argument
- **Lemma 3** (Monotone prime chain): The prime chain under the Collatz map is strictly increasing
- **§6** (No local obstruction): Absence of local obstruction established by congruence
- **§7** (Chen-type theorem skeleton): Proof skeleton that "for infinitely many primes p, (3p+1)/2 is P2 (prime or semiprime)"

---

## Main Results

### Proved (Rigorous)

| Result | Method | Status |
|--------|--------|--------|
| c-A finite escape (1 step) | Congruence mod 4, mod 8 | ✗ false as stated, see Erratum |
| c-B finite escape (≤ 2 steps) | Congruence mod 8 | ✗ false, see Erratum |
| c-pattern self-reference: only n ≡ 7 (mod 8) | Congruence table | ✓ (but the image is 3 or 7 mod 8, see Erratum) |
| Monotone growth of prime chains (Lemma 3) | Direct computation | ✓ proved |
| No local obstruction (§6) | Congruence | ✓ proved |
| Chen-type theorem skeleton (§7) | Proof framework | ✓ skeleton |

### Remaining Open

| Problem | Status |
|---------|--------|
| §7(v): Selberg sieve rigorous refinement | Open |
| Dickson's conjecture (main body) | Open |

---

## Structure

```
§1   Pattern classification (a1, a2, b, c) — exhaustive mod 4
§2   Lemma 1: c-A/c-B finite escape          ✓ proved
§3   Lemma 2: Prime infinitude                ✓
§4   Lemma 3: Monotone prime chain            ✓ proved
§5   Lemma 4: Prime theorem infinitude        ✓
§6   No local obstruction                     ✓ proved
§7   Chen-type theorem for Collatz            skeleton
```

---

## Open Problems

- Selberg sieve rigorous bound for §7(v)
- Full proof of Dickson's conjecture
- Extension of Chen-type result to infinite orbit

---

## Repository Structure

```
collatz-act1/
├── README.md
├── paper/
│   └── collatz_prime_survival_dynamics_v11.pdf   — full paper (v11.0)
└── LICENSE
```

---

## Related Work

This paper is part of a series on Collatz dynamics:

- [collatz-act1](https://github.com/KAMANOI/collatz-act1) — Foundational paper: prime survival dynamics and Chen-type theorem (v11)
- [collatz-renewal-structure](https://github.com/KAMANOI/collatz-renewal-structure) — Paper A: exact operator structure and finite information memory
- [collatz-finite-mixing-geometry](https://github.com/KAMANOI/collatz-finite-mixing-geometry) — Paper B: finite-level mixing geometry
- [collatz-spectral-amplification](https://github.com/KAMANOI/collatz-spectral-amplification) — Paper C: spectral amplification
- [collatz-scale-coherence](https://github.com/KAMANOI/collatz-scale-coherence) — Paper D: scale-coherence rigidity
- [collatz-valuation-renewal](https://github.com/KAMANOI/collatz-valuation-renewal) — Valuation renewal, finite residue connectivity, and orbitwise gap
- [collatz-residual-core](https://github.com/KAMANOI/collatz-residual-core) — The residual core: structural decomposition
- [collatz-congruence-synchronization](https://github.com/KAMANOI/collatz-congruence-synchronization) — Paper H: nested congruence constraints on synchronization
- [collatz-record-renewal](https://github.com/KAMANOI/collatz-record-renewal) — Paper N: record renewal compatibility
- [collatz-hensel-escape](https://github.com/KAMANOI/collatz-hensel-escape) — Paper O: Hensel memory and 2-adic escape target
- [collatz-hensel-scarcity](https://github.com/KAMANOI/collatz-hensel-scarcity) — Paper T: Hensel conditional scarcity and telescoping contradiction
- [collatz-prefix-counting](https://github.com/KAMANOI/collatz-prefix-counting) — Paper V: direct prefix counting and synchronization collapse
- [collatz-first-passage](https://github.com/KAMANOI/collatz-first-passage) — Paper W: first-passage obstruction (closes series A–V)
- [collatz-series-summary](https://github.com/KAMANOI/collatz-series-summary) — Series summary: research program on Collatz synchronization dynamics
- [collatz-prime-survival](https://github.com/KAMANOI/collatz-prime-survival) — Paper X v20: prime survival in affine Collatz dynamics

---

## Author

Hiroki Kamanoi
hirokikamanoi@gmail.com
2026

---
Related research and services by HDR (Human Driven Reality): https://hdr-ai.com/#research
