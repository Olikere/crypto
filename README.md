# 🔐 Cryptography Lab

A study repository for cryptography: write-ups of challenges (CTFs and practice platforms), notes from books, and documentation of classic and modern attacks.

> ⚠️ **Spoiler warning:** this repository contains full solutions to challenges. Try solving them on your own before reading.
>
> 📚 **Educational purposes only:** all content is meant for learning and for use in authorized environments (CTFs, labs, training platforms).

---

## 📑 Table of Contents

- [Repository Structure](#-repository-structure)
- [Progress](#-progress)
- [Documented Attacks](#-documented-attacks)
- [Books and Resources](#-books-and-resources)
- [Tools](#-tools)
- [Getting Started](#-getting-started)
- [References](#-references)

---

## 📂 Repository Structure

```
.
├── challenges/
│   ├── cryptohack/
│   │   ├── intro/
│   │   ├── general/
│   │   ├── mathematics/
│   │   ├── symmetric-ciphers/
│   │   ├── rsa/
│   │   └── ...
│   ├── cryptopals/
│   │   ├── set1/
│   │   ├── set2/
│   │   └── ...
│   ├── tryhackme/
│   └── ctfs/
│       └── <ctf-name>-<year>/
├── attacks/
│   ├── rsa/
│   ├── aes/
│   ├── ecc/
│   └── ...
├── books/
│   ├── serious-cryptography/
│   └── ...
├── tools/            # reusable scripts and utilities
├── requirements.txt
└── README.md
```

Each challenge has its own folder containing:

```
challenge-name/
├── README.md     # short problem statement, solution idea, and takeaways
├── solve.py      # solve script
└── files/        # provided files (if any)
```

---

## 📈 Progress

| Platform | Link | Solved | Status |
|----------|------|:------:|:------:|
| CryptoHack | [cryptohack.org](https://cryptohack.org) | 0 / ? | 🟡 In progress |
| Cryptopals | [cryptopals.com](https://cryptopals.com) | 0 / 64 | 🟡 In progress |
| TryHackMe | [tryhackme.com](https://tryhackme.com) | 0 / ? | ⚪ Not started |
| Misc. CTFs | — | 0 | ⚪ Not started |

### Cryptopals

| Set | Topic | Status |
|-----|-------|:------:|
| 1 | Basics | ⬜ |
| 2 | Block crypto | ⬜ |
| 3 | Block & stream crypto | ⬜ |
| 4 | Stream crypto and randomness | ⬜ |
| 5 | Diffie-Hellman and friends | ⬜ |
| 6 | RSA and DSA | ⬜ |
| 7 | Hashes | ⬜ |
| 8 | Abstract Algebra | ⬜ |

---

## ⚔️ Documented Attacks

Each attack has its own page in `attacks/` covering: **concept, preconditions, math, implementation, and challenges where it was used.**

### RSA

| Attack | Condition | Write-up | Code |
|--------|-----------|:--------:|:----:|
| Direct factoring (small n) | Factorable n | ⬜ | ⬜ |
| Fermat | p and q close together | ⬜ | ⬜ |
| Small exponent / e-th root | Small e, no padding | ⬜ | ⬜ |
| Håstad broadcast | Same message, multiple moduli | ⬜ | ⬜ |
| Common modulus | Same n, different e's | ⬜ | ⬜ |
| Wiener | Small d | ⬜ | ⬜ |
| Coppersmith | Partially known bits | ⬜ | ⬜ |
| Bleichenbacher | PKCS#1 v1.5 padding oracle | ⬜ | ⬜ |

### Symmetric Ciphers

| Attack | Target | Write-up | Code |
|--------|--------|:--------:|:----:|
| ECB detection | AES-ECB | ⬜ | ⬜ |
| Byte-at-a-time ECB | AES-ECB | ⬜ | ⬜ |
| Padding oracle | AES-CBC | ⬜ | ⬜ |
| CBC bitflipping | AES-CBC | ⬜ | ⬜ |
| Nonce / keystream reuse | CTR, GCM, stream ciphers | ⬜ | ⬜ |
| Many-time pad | Reused XOR / OTP | ⬜ | ⬜ |

### Hashes and MACs

| Attack | Target | Write-up | Code |
|--------|--------|:--------:|:----:|
| Length extension | MD5, SHA-1, SHA-2 | ⬜ | ⬜ |
| Collisions | MD5, SHA-1 | ⬜ | ⬜ |
| MAC timing attack | Insecure comparison | ⬜ | ⬜ |

### Elliptic Curves and Diffie-Hellman

| Attack | Target | Write-up | Code |
|--------|--------|:--------:|:----:|
| Pohlig-Hellman | Group with smooth order | ⬜ | ⬜ |
| Baby-step Giant-step | DLP | ⬜ | ⬜ |
| Small subgroup | DH | ⬜ | ⬜ |
| Invalid curve | ECDH | ⬜ | ⬜ |
| Smart's attack | Anomalous curves | ⬜ | ⬜ |
| Nonce reuse / bias | ECDSA / DSA | ⬜ | ⬜ |

### Randomness and Others

| Attack | Target | Write-up | Code |
|--------|--------|:--------:|:----:|
| MT19937 state recovery | PRNG | ⬜ | ⬜ |
| LCG | PRNG | ⬜ | ⬜ |
| Lattice reduction (LLL) | HNP, knapsack | ⬜ | ⬜ |

---

## 📚 Books and Resources

| Book / Course | Author | Progress |
|---------------|--------|:--------:|
| Serious Cryptography | Jean-Philippe Aumasson | ⬜ |
| Cryptography Engineering | Ferguson, Schneier, Kohno | ⬜ |
| An Introduction to Mathematical Cryptography | Hoffstein, Pipher, Silverman | ⬜ |
| A Graduate Course in Applied Cryptography | Boneh, Shoup | ⬜ |
| Handbook of Applied Cryptography | Menezes et al. | ⬜ |
| Cryptography I (Coursera) | Dan Boneh | ⬜ |

Legend: ⬜ not started · 🟡 in progress · ✅ completed

---

## 🛠 Tools

- **Python 3** with:
  - [`pycryptodome`](https://pycryptodome.readthedocs.io/): cryptographic primitives
  - [`pwntools`](https://docs.pwntools.com/): interacting with remote services
  - [`gmpy2`](https://gmpy2.readthedocs.io/): arbitrary-precision arithmetic
  - [`sympy`](https://www.sympy.org/): symbolic math
- **[SageMath](https://www.sagemath.org/)**: elliptic curves, lattices, algebra
- **[RsaCtfTool](https://github.com/RsaCtfTool/RsaCtfTool)**: automated RSA attacks
- **[CyberChef](https://gchq.github.io/CyberChef/)**: quick data manipulation
- **[hashcat](https://hashcat.net/)** / **John the Ripper**: hash cracking
- **[z3](https://github.com/Z3Prover/z3)**: SMT solver

---

## 🚀 Getting Started

```bash
# Clone
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>

# Virtual environment
python3 -m venv venv
source venv/bin/activate

# Dependencies
pip install -r requirements.txt
```

For scripts that use Sage:

```bash
sage challenges/cryptohack/rsa/example/solve.sage
```

---

## 🔗 References

**Platforms**
- [CryptoHack](https://cryptohack.org)
- [Cryptopals](https://cryptopals.com)
- [TryHackMe](https://tryhackme.com)
- [CTFtime](https://ctftime.org)
- [Krypton wargame](https://overthewire.org/wargames/krypton/)

**Study Material**
- [CTF Wiki: Crypto](https://ctf-wiki.org/en/crypto/introduction/)
- [Crypto Stack Exchange](https://crypto.stackexchange.com)
- [Cryptography Engineering blog (Matthew Green)](https://blog.cryptographyengineering.com)
- [Trail of Bits: Cryptography](https://blog.trailofbits.com/category/cryptography/)

---

## 📝 License

Distributed under the MIT License. See [`LICENSE`](LICENSE) for more information.

---

<p align="center">
  Built to learn, fail, break, and understand. 🔓
</p>
