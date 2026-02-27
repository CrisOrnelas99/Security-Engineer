# 🔐 What I Learned — Password Storage Security

- Cryptography protects passwords in **transit** (e.g., HTTPS using SSL/TLS).
- We also need to protect passwords **at rest** (stored in databases).

- Worst practice:
  - Store **username + plaintext password**.
  - If database is breached → attacker instantly gets all passwords.

- Better approach:
  - Store **username + hash(password)**.
  - Hash functions are **one-way (irreversible)**.
  - Attacker must guess passwords and hash them to find matches.

- Problem:
  - **Rainbow tables** exist.
  - They contain precomputed password hashes.
  - Attacker can look up a hash and recover common passwords easily.
  - MD5 and other weak hashes are especially vulnerable.

- Solution: **Salting**
  - Add a random **salt** to password before hashing.
  - Example:
    ```
    hash(password + salt)
    ```
  - Or:
    ```
    hash(hash(password) + salt)
    ```
  - Salt must be:
    - Random
    - Unique per user
  - Salt prevents rainbow table attacks because each hash becomes unique.

- Stronger improvement:
  - Use a **Key Derivation Function (KDF)** like **PBKDF2**.
  - PBKDF2:
    - Uses password + salt.
    - Applies hashing for **many iterations** (e.g., hundreds of thousands).
  - Slows down brute-force attacks significantly.

- Best practices:
  - Never store plaintext passwords.
  - Use strong hash algorithms (not MD5 or SHA-1).
  - Use unique salts per user.
  - Use PBKDF2 or another secure password hashing/KDF method.

- Goal:
  - Even if database is leaked, recovering real passwords should be **computationally expensive**.
 
  - <img width="764" height="485" alt="image" src="https://github.com/user-attachments/assets/96b23fd3-cbff-40f0-bf09-ee451e0cf694" />
  - <img width="2518" height="967" alt="image" src="https://github.com/user-attachments/assets/309cf98d-3abf-4096-8914-f06623ead09e" />

