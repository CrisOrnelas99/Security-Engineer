# 🔐 Introduction to Basic Cryptography Concepts

This section introduces fundamental cryptography concepts used to secure communication:

- **Symmetric Encryption** (e.g., AES)  
- **Asymmetric Encryption** (e.g., RSA)  
- **Diffie-Hellman Key Exchange**  
- **Hashing**  
- **Public Key Infrastructure (PKI)**  

The primary goal of cryptography is to ensure that only the intended recipient can understand a transmitted message.

---

# 🏛️ Classical Ciphers

## 1️⃣ Caesar Cipher (Substitution Cipher)

The **Caesar Cipher** is one of the earliest encryption techniques. It shifts each letter in the alphabet by a fixed number of positions.

### 🔑 Key Characteristics

- Encryption: Shift letters right by a fixed key  
- Decryption: Shift letters left by the same key  
- Example (Key = 3):  
  - `TRY HACK ME` → `WUB KDFN PH`  

### 🔢 Keyspace

- Possible keys: 1–25  
- Key = 0 or 26 → No change  
- Total effective keys: **25**  
- Small keyspace makes brute-force attacks feasible  

### 🔓 Brute Force Attack

If the key is unknown, all 25 possible shifts can be tested until readable plaintext appears.

**Definition:**  
Caesar Cipher is a **substitution cipher** because letters are replaced while their original order remains unchanged.

---

## 2️⃣ Transposition Cipher

A **transposition cipher** encrypts a message by rearranging the order of letters without changing the letters themselves.

### 🔄 Key Characteristics

- Letters remain unchanged  
- Only positions are rearranged  
- Plaintext is written column-wise  
- Columns are reordered using a numeric key  
- Ciphertext is read row-wise  
- Spaces are ignored during encryption  

### 📌 Difference from Substitution

| Cipher Type   | Operation                          |
|--------------|-------------------------------------|
| Substitution | Replaces letters                   |
| Transposition| Rearranges letter positions        |

---

# 🧠 Cryptographic Security Principles

An encryption algorithm is considered secure if:

- Recovering plaintext is **computationally infeasible**  
- Breaking it cannot be done in **polynomial time**  
- The required time to break it is impractically large  

### 🔐 Practical Security

- Breakable in one week → **Insecure**  
- Requires millions of years → **Practically Secure**  

Secure cryptography relies on mathematically hard problems that cannot be efficiently solved.

---

# 🔤 Mono-Alphabetic Substitution Cipher

A **mono-alphabetic substitution cipher** maps each letter of the alphabet to a unique different letter.

### 🔑 Key Characteristics

- One-to-one fixed letter mapping  
- Requires a shared secret key  
- Large theoretical keyspace (26!)  

### ⚠️ Weaknesses

Despite its large keyspace, it is vulnerable due to:

- **Letter frequency analysis**
  - Most common English letters:  
    - e (13%)  
    - t (9.1%)  
    - a (8.2%)  
- Common first letters:
  - t (16%)  
  - a (11.7%)  
  - o (7.6%)  
- Predictable dictionary word patterns  

These statistical patterns allow attackers to recover plaintext without knowing the key.

### ❌ Security Conclusion

Mono-alphabetic substitution is insecure and unsuitable for confidential communication.

---

# 📌 Overall Summary

- Classical ciphers (Caesar, Transposition, Mono-Alphabetic) are historically important but insecure.  
- Small keyspaces and statistical analysis make them easy to break.


- Secure encryption must rely on computationally hard mathematical problems.  
- Modern cryptography (AES, RSA, Diffie-Hellman, Hashing, PKI) replaces these weak classical methods.
- <img width="1218" height="484" alt="image" src="https://github.com/user-attachments/assets/8806514b-c47e-49d5-93cd-b8df8ea2e5be" />

