# 🔐 What I Learned – Basic Cryptography

## 📚 Core Cryptography Concepts
I learned the foundational concepts of cryptography used to secure communication:

- **Symmetric Encryption** (e.g., AES) – Uses the same key for encryption and decryption.
- **Asymmetric Encryption** (e.g., RSA) – Uses a public key for encryption and a private key for decryption.
- **Diffie-Hellman Key Exchange** – Securely establishes a shared secret over an insecure channel.
- **Hashing** – Produces a fixed-length digest for data integrity verification.
- **Public Key Infrastructure (PKI)** – Manages digital certificates and public key distribution.

---

## 🏛️ Classical Encryption Techniques

### Caesar Cipher
- A substitution cipher that shifts letters by a fixed number.
- Has a keyspace of 25 possible keys.
- Easily broken using brute-force attacks.
- Demonstrated how encryption and decryption depend on the shared key.

### Transposition Cipher
- Rearranges letter positions instead of replacing them.
- Maintains original letters but changes their order.
- Uses a numeric key to reorder columns.
- Highlighted the difference between substitution and rearrangement.

---

## 🔤 Mono-Alphabetic Substitution Cipher
- Maps each letter of the alphabet to a unique substitute letter.
- Has a very large theoretical keyspace (26!).
- Still vulnerable due to frequency analysis.
- Demonstrated that large keyspace alone does not guarantee security.

---

## 🧠 Cryptographic Security Principles
- Secure encryption must be computationally infeasible to break.
- A secure system relies on mathematically hard problems.
- If encryption can be broken in a short time, it is insecure.
- Practical security depends on time complexity and resistance to analysis.

---

## 📌 Key Takeaways
- Classical ciphers are historically important but insecure.
- Brute force and frequency analysis can break weak encryption.
- Modern cryptography improves security using strong mathematical foundations.
- Security is measured by computational feasibility, not just key size.
