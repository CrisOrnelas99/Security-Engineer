# 🔐 What I Learned — Symmetric Encryption (Key Notes)

## 🧩 Basic Terms
- **Cipher/Algorithm:** Rules that do encryption/decryption.
- **Key:** Secret value the cipher uses to lock/unlock data.
- **Plaintext:** Original readable message.
- **Ciphertext:** Encrypted unreadable message.

## 🔑 Symmetric Encryption
- Same **key** is used to **encrypt and decrypt**.
- Both people must **share the secret key first**.
- If you don’t have the key, you **can’t recover the plaintext**.

## 🏛️ DES vs AES
- **DES (1977):** 56-bit key → **too small**, brute-forced → **not secure**.
- **AES (2001):** 128/192/256-bit keys → **secure and widely used**.
- AES is complex (multiple rounds of transformations), which makes it harder to break.

## 🧱 Block vs Stream Ciphers
- **Block cipher:** Encrypts data in fixed-size blocks (commonly **128 bits / 16 bytes**).
- **Stream cipher:** Encrypts data **byte-by-byte**.

## 🛡️ What Symmetric Encryption Gives You (If key stays secret)
- **Confidentiality:** attackers can’t read the message.
- **Integrity:** tampering breaks decryption / produces garbage.
- **Authenticity:** decrypting successfully suggests the sender knew the secret key.

## 📈 Main Problem: Key Scaling
- More users = **many more shared keys**.
- 100 users → about **4950 keys** needed.
- Hard to manage, replace, and share keys securely → leads into **asymmetric encryption**.

## 🧰 Practical Tools I Used
### GPG
- Encrypt: `gpg --symmetric --cipher-algo CIPHER message.txt`
- Decrypt: `gpg --output original_message.txt --decrypt message.gpg`
- ASCII output: add `--armor`

### OpenSSL
- Encrypt: `openssl aes-256-cbc -e -in message.txt -out encrypted_message`
- Decrypt: `openssl aes-256-cbc -d -in encrypted_message -out original_message.txt`
- Stronger password-based key: add `-pbkdf2 -iter 10000`

- <img width="669" height="439" alt="image" src="https://github.com/user-attachments/assets/b5fdb4b8-c18f-4fdd-b19f-9d9a1a58af7e" />
<img width="1288" height="396" alt="image" src="https://github.com/user-attachments/assets/a4f7dc77-c33b-4360-b91e-d7956773ad84" />

- <img width="692" height="351" alt="image" src="https://github.com/user-attachments/assets/d90cb2f3-b691-4437-9b28-8495eb89e864" />
<img width="1297" height="324" alt="image" src="https://github.com/user-attachments/assets/ae0f8479-f112-4b70-a902-bd9aea31c07c" />

- <img width="693" height="388" alt="image" src="https://github.com/user-attachments/assets/c48231b3-e6ce-4b69-aac6-ef5949573aad" />
<img width="1284" height="195" alt="image" src="https://github.com/user-attachments/assets/a771aa41-7e6d-4071-9741-a0f9e9c39f12" />





