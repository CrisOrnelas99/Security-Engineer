# 🔐 What I Learned — MITM Risk, PKI, and Certificates

- Diffie-Hellman lets Alice and Bob agree on a **shared secret key** even if eavesdroppers can read the traffic.
- Diffie-Hellman alone is vulnerable to a **Man-in-the-Middle (MITM)** attack because:
  - Alice cannot prove she is talking to Bob.
  - Bob cannot prove he is talking to Alice.

- MITM (Mallory) attack idea:
  - Mallory intercepts Alice’s public value `A` and sends her own value `M` to Bob pretending to be Alice.
  - Mallory intercepts Bob’s public value `B` and sends `M` to Alice pretending to be Bob.
  - Alice computes a key with `M`, Bob computes a key with `M`.
  - Result: Alice and Bob think they share a secret, but Mallory can **read/modify** messages between them.

- Fix requires **authentication** → this is where **PKI (Public Key Infrastructure)** is used.

- HTTPS trust concept:
  - Browser shows a **lock icon** when HTTPS uses a **valid certificate**.
  - A website certificate is trusted because it is signed by a **Certificate Authority (CA)** (example: DigiCert).
  - If the browser does not trust the CA, it shows a **security warning**.

- To get a trusted certificate:
  - Create a **CSR (Certificate Signing Request)** containing your public key and identity info.
  - Send the CSR to a **CA** to sign it (self-signing is usually insecure for real use).
  - Trust works only if the client already trusts the CA.

- After the browser receives a trusted signed certificate:
  - The **TLS/SSL handshake** happens.
  - Client and server agree on **ciphers** and a **secret key** for secure communication.

- PKI is needed for scalability because it uses a **trusted third party** (CA) to validate identity.

## 🖥️ Commands I Learned

Generate a CSR (and new 4096-bit RSA key):
- <img width="740" height="495" alt="image" src="https://github.com/user-attachments/assets/0e4a2427-352d-4a2c-9757-6b98dbe107d5" />
- <img width="762" height="277" alt="image" src="https://github.com/user-attachments/assets/ef813f9e-097b-4e74-ab10-fd6b46633807" />

- <img width="1282" height="87" alt="image" src="https://github.com/user-attachments/assets/fad6284d-610d-4a6f-8714-ee1b8c62232b" />
- <img width="1217" height="498" alt="image" src="https://github.com/user-attachments/assets/a345e76d-257b-41e9-ba7d-19974d72d14e" />




