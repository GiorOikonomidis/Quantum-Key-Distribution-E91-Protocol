# Quantum Key Distribution — The E91 Protocol

A technical paper on quantum cryptography and quantum key distribution, focusing on
**Ekert's 1991 (E91) protocol** — how entanglement is used to establish a shared secret
key, and how a Bell-inequality test turns eavesdropping into something physically
detectable rather than merely computationally hard.

![Topic](https://img.shields.io/badge/Topic-Quantum_Cryptography-6A4C93)
![Protocol](https://img.shields.io/badge/Protocol-E91_(Ekert_1991)-1E88E5)
![Format](https://img.shields.io/badge/Format-PDF_·_17_pages-critical)
![License](https://img.shields.io/badge/License-CC_BY_4.0-blue)

📄 **[Read the paper → `Quantum_Cryptography_.pdf`](Quantum_Cryptography_.pdf)**

---

## Subject

Classical key distribution rests on computational hardness: RSA and Diffie–Hellman are
secure because factoring and discrete logarithms are *expensive*, not because they are
impossible. That assumption has an expiry date — Shor's algorithm breaks both on a
sufficiently large quantum computer.

Quantum key distribution replaces the computational assumption with a physical one. The
security of E91 rests on quantum mechanics itself: measurement disturbs state, and
entanglement correlations violate bounds that any classical (local hidden-variable)
explanation must obey. An eavesdropper cannot observe the channel without perturbing it,
and that perturbation is *measurable* by the legitimate parties.

The paper builds from classical foundations up to the protocol mechanics, so it stands on
its own without prior background in quantum information.

---

## Contents

**1 · General introduction to cryptography**
  1.1 What cryptography is, and an overview of its use
  1.2 The need for key-distribution algorithms
  1.3 Why cryptography is necessary
  1.4 Notable cryptographic algorithms

**2 · Quantum cryptography**
  2.1 Introduction to quantum cryptography
  2.2 Quantum key distribution
  2.3 The E91 key distribution protocol
   2.3.1 Why E91
   2.3.2 How E91 works — key creation · entanglement verification
   2.3.3 Worked example

**3 · Conclusions**

---

## Why E91 specifically

E91 is treated separately from the better-known BB84 because the source of its security is
different in kind. BB84 relies on the no-cloning theorem — an eavesdropper cannot copy an
unknown quantum state. E91 goes further: the two parties share **entangled pairs**, and
rather than trusting the channel, they *test* it. A subset of measurements is sacrificed
to check whether the observed correlations violate a Bell inequality.

If they do, no local hidden-variable model — and therefore no classical interception —
can explain the results, and the remaining measurements are safe to distil into a key. If
the violation is absent or degraded, the parties learn the channel was compromised and
discard it.

This makes eavesdropping detection a **consequence of physics** rather than an added
protocol step, which is the conceptual point the paper develops.

---

## Related work in this repository collection

This paper sits alongside implementation work on classical cryptography — see
[**ECDH_RSA_implementetion**](https://github.com/GiorOikonomidis/ECDH_RSA_implementetion),
which implements elliptic-curve Diffie–Hellman key exchange and RSA from primitives in C.
Together they cover both sides of the key-distribution problem: the classical algorithms
in practice, and the quantum protocol designed to outlive them.

---

## Citation

```
Oikonomidis, G. (2025). Quantum Cryptography: Quantum Key Distribution — E91 Protocol.
```

---

## License

The paper is released under
[Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).
You may share and adapt it, including commercially, with attribution.
