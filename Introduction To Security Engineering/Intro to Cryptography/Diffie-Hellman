# 🔐 What I Learned — Diffie-Hellman Key Exchange (Key Notes)

- Diffie-Hellman allows two parties to agree on a **shared secret key over an insecure channel**.
- The channel can be monitored (eavesdroppers can see messages).
- It is an **asymmetric key exchange algorithm**, not used to encrypt data directly.

- Publicly agreed values:
  - `q` → large prime number.
  - `g` → generator (number < q).

- Private values:
  - Alice chooses secret `a`.
  - Bob chooses secret `b`.
  - These are never shared.

- Public values:
  - Alice computes:
    ```
    A = g^a mod q
    ```
    and sends A to Bob.
  - Bob computes:
    ```
    B = g^b mod q
    ```
    and sends B to Alice.

- Shared secret calculation:
  - Alice computes:
    ```
    key = B^a mod q
    ```
  - Bob computes:
    ```
    key = A^b mod q
    ```
  - Both get the **same secret key**.

- Even if an attacker knows `q`, `g`, `A`, and `B`, they cannot feasibly compute the shared secret.
- Security is based on the difficulty of the **Discrete Logarithm Problem**.

- Real implementations use very large primes (e.g., **2048-bit or larger**).
- Small numbers are only for demonstration.

---

## 🖥️ OpenSSL Diffie-Hellman Commands

Generate DH parameters (2048-bit):
