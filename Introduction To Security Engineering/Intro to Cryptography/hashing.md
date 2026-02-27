# 🔐 What I Learned — Hashing & HMAC

- A **cryptographic hash function** takes input of any size and outputs a **fixed-size** value called a **message digest / checksum**.
- Example: **SHA-256** outputs **256 bits (32 bytes)**.
- Hashes are usually shown in **hex**:
  - 1 hex digit = **4 bits**
  - SHA-256 = **64 hex digits**

- Hash output length is **always the same**, no matter the file size (small file or multi-GB file).

- Main uses of hashing:
  - **Password storage:** store the **hash** instead of plaintext passwords (passwords are also salted in practice).
  - **Detecting modifications:** tiny changes in input cause a **completely different hash** (avalanche effect).

- Even changing **1 bit** in a file results in a totally different SHA-256 checksum, so hashes help detect:
  - intentional tampering
  - transfer/corruption errors

- Secure hash algorithms (still considered safe):
  - **SHA224, SHA256, SHA384, SHA512**
  - **RIPEMD160**

- Broken/unsafe hash algorithms:
  - **MD5**, **SHA-1**
- “Broken” means attackers can create **hash collisions** (different files with the same checksum), making tamper detection unreliable.

- **HMAC** (Hash-based Message Authentication Code) = hash + **secret key**.
- HMAC provides integrity + authenticity because it requires knowing the secret key.
- HMAC uses:
  - **secret key**
  - **ipad** (inner pad constant)
  - **opad** (outer pad constant)
 
  - <img width="733" height="546" alt="image" src="https://github.com/user-attachments/assets/960901fd-4c8a-4603-9cc2-59155a24c4d1" />
  - <img width="1229" height="107" alt="image" src="https://github.com/user-attachments/assets/a1a1459a-24c9-40b0-8dfd-099c4a576dcc" />

  - <img width="733" height="324" alt="image" src="https://github.com/user-attachments/assets/539090ff-a396-44f8-a959-6b0f154a8a5a" />

  -<img width="745" height="322" alt="image" src="https://github.com/user-attachments/assets/8031159a-302d-41df-b3f6-21f2451dc226" />
  - <img width="1261" height="191" alt="image" src="https://github.com/user-attachments/assets/80c4a1cb-4cd4-48a8-b85d-9811cb991fda" />





