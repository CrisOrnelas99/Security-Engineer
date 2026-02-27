# 🔐 Basic Cryptography Concepts

## 📚 Core Topics
This content covers the foundational cryptography concepts used to protect communications:

- **Symmetric Encryption** (e.g., AES)
- **Asymmetric Encryption** (e.g., RSA)
- **Diffie-Hellman Key Exchange**
- **Hashing**
- **Public Key Infrastructure (PKI)**

Cryptography enables sending a message that only the intended recipient can understand.

---

# 🏛️ Classical Ciphers

## 1️⃣ Caesar Cipher (Substitution Cipher)

The **Caesar Cipher** is an ancient cipher that encrypts by shifting letters by a fixed number of positions.

### 🔁 How It Works
- Encryption: shift letters right by a fixed key  
- Decryption: shift letters left by the same key  

Example (key = 3):
- `TRY HACK ME` → `WUB KDFN PH`

### 🔑 Keyspace
- Valid keys: **1 to 25**
- Key = 0 or 26 → no change
- Total effective keys: **25**
- Small keyspace makes brute-force feasible

### 🔓 Brute Force Decryption
If ciphertext is intercepted and the key is unknown, try all 25 shifts until readable plaintext appears.

Example ciphertext:
- `YMNX NX FQUMF GWFAT HTSYFHYNSL YFSLT MTYJQ RNPJ`

Key = 5 produces:
- `THIS IS ALPHA BRAVO CONTACTING TANGO HOTEL MIKE`

**Definition:** Caesar is a **substitution cipher** because each letter is substituted with another letter.

---

## 2️⃣ Transposition Cipher

A **transposition cipher** encrypts by rearranging letter positions without changing the letters.

### 🔁 Key Characteristics
- Reorders letters using a key (e.g., `42351`)
- Write plaintext by columns, reorder columns by key, read ciphertext by rows
- Spaces are typically removed/ignored

**Key Difference**
- Substitution cipher: replaces letters
- Transposition cipher: rearranges letter order

---

# 🔤 Mono-Alphabetic Substitution Cipher

Each letter maps to a unique substitute letter (a fixed alphabet mapping).

Example mapping:
- `abcdefghijklmnopqrstuvwxyz`
- `xpatvrzyjhecsdikbfwunqgmol`

The recipient must know the mapping key to decrypt.

### ❌ Why It Breaks
Even with a large keyspace (26!), it is vulnerable due to:

- **Letter frequency analysis**
  - Common English letters: e (13%), t (9.1%), a (8.2%)
- **Common first-letter frequency**
  - t (16%), a (11.7%), o (7.6%)
- **Dictionary word patterns**

Ciphertext can often be decrypted without the key using analysis tools.

---

# 🧠 Security Principles in Encryption

An encryption algorithm is considered secure when recovering the plaintext is **computationally infeasible**.

- Secure systems rely on mathematically hard problems
- Polynomial-time solvable problems are considered feasible at scale

### ⏳ Practical Security
- Breakable in **one week** → insecure
- Breakable in **1 million years** → practically secure

---

# 🔐 Symmetric Encryption & Modern Cryptography

## 🧩 Core Cryptographic Components

- **Cryptographic Algorithm (Cipher):** Defines encryption and decryption processes.
- **Key:** Secret value used to transform plaintext ↔ ciphertext.
- **Plaintext:** Original readable message.
- **Ciphertext:** Encrypted unreadable message.

---

## 🔑 Symmetric Encryption

A **symmetric encryption algorithm** uses the same key for encryption and decryption.

- Sender: plaintext + key → ciphertext
- Receiver: ciphertext + same key → plaintext
- Without the key, decryption is not feasible

### ⚠️ Requirement
Both parties must agree on a shared secret key securely before communication.

---

# 🏛️ DES vs AES

## 🔒 Data Encryption Standard (DES)
- Published by **NIST** in 1977
- Key size: **56 bits**
- Proven breakable via brute-force:
  - 1997: DES challenge solved
  - 1998: DES key broken in 56 hours
- No longer secure

## 🔐 Advanced Encryption Standard (AES)
- Published by **NIST** in 2001
- Key sizes: **128, 192, 256 bits**
- Still considered secure and widely used

### 🔄 AES Core Transformations
AES applies multiple rounds of transformations:

- **SubBytes(state):** S-box byte substitution
- **ShiftRows(state):** row shifting offsets (1, 2, 3)
- **MixColumns(state):** fixed matrix multiplication per column
- **AddRoundKey(state):** XOR with round key

- State size: **128-bit (16 bytes)** as a 4×4 array
- Rounds depend on key size
- Defined in **FIPS PUB 197**

---

# 📋 Symmetric Algorithms Supported by GPG (Example: GnuPG 2.37.7)

- **AES, AES192, AES256**
- **IDEA**
- **3DES** (Deprecated 2023, Disallowed 2024)
- **CAST5 (CAST-128)**
- **BLOWFISH**
- **TWOFISH**
- **CAMELLIA128, CAMELLIA192, CAMELLIA256**

Most listed algorithms are **block ciphers**.

---

# 🧱 Block Ciphers vs Stream Ciphers

## 🧊 Block Ciphers
- Encrypt plaintext in fixed-size blocks (commonly 128 bits)
- Example: AES
- Convert text to bytes (e.g., ASCII/hex), pack into 16-byte blocks

## 🌊 Stream Ciphers
- Encrypt plaintext **byte-by-byte**
- Process data sequentially as a stream

---

# 🛡️ Security Properties Achieved with Symmetric Encryption

Assuming a secure cipher and protected key:

- **Confidentiality:** Interceptors cannot recover plaintext from ciphertext
- **Integrity:** Ciphertext modification causes decryption failure or corrupted output
- **Authenticity:** Successful decryption indicates the sender knows the secret key

---

# 📈 Scalability Problem: Key Explosion

Number of keys required for symmetric communication grows quickly:

- 2 users → 1 key
- 3 users → 3 keys
- 100 users → 4950 keys



<img width="1006" height="391" alt="image" src="https://github.com/user-attachments/assets/902d8421-a011-415e-8b86-2105b223916f" />
<img width="1279" height="207" alt="image" src="https://github.com/user-attachments/assets/dcc823a2-c758-4c8d-9330-6a0543cc0298" />



<img width="690" height="374" alt="image" src="https://github.com/user-attachments/assets/de51485d-2c22-412f-ab94-bfc5269db5c4" />
<img width="1298" height="315" alt="image" src="https://github.com/user-attachments/assets/788ac6cf-acc4-493e-950b-ec2fc06b1baa" />



<img width="666" height="380" alt="image" src="https://github.com/user-attachments/assets/1a333420-034a-4625-8a5b-96ab7c1c4be1" />
<img width="1281" height="235" alt="image" src="https://github.com/user-attachments/assets/7e80710d-0da0-4f2d-9bf1-d977dcbca4eb" />




