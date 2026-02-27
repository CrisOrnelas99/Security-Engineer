# 🔐 What I Learned — HTTPS, TLS & Password Verification

- When connecting to a website over **HTTPS**, the client first requests the server’s **SSL/TLS certificate**.
- The server sends its certificate to the client.
- The client verifies that the certificate is **valid and trusted**.

- A certificate is considered valid if:
  - It is **digitally signed** by a trusted third party (Certificate Authority).
  - The signature is created by encrypting a **hash of the certificate** with the CA’s private key.

- The client:
  - Decrypts the signature using the CA’s **public key**.
  - Compares the decrypted hash with the certificate’s actual hash.
  - If they match → certificate is valid.
  - If the CA is not trusted → connection warning or blocked.

- After certificate validation, the **TLS handshake** begins.
- During the handshake:
  - Client and server agree on:
    - A **symmetric encryption algorithm**
    - A **shared secret session key**
- All further communication in that session is encrypted using **symmetric encryption**.

- Login process:
  - Client sends username and password through the encrypted TLS session.
  - Server verifies credentials.

- Secure password storage on server:
  - Server stores **hash(password + salt)**.
  - Salt is random and unique per user.
  - Protects against database breaches and rainbow table attacks.

- Overall:
  - TLS protects credentials **in transit**.
  - Hashing + salting protects passwords **at rest**.
