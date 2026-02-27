# 🔐 What I Learned — Asymmetric Encryption & RSA

- Symmetric encryption requires a **secure channel** to exchange keys (confidentiality + integrity).
- Asymmetric encryption only requires a **reliable channel** (integrity focused, not confidentiality).

- Asymmetric encryption uses a **key pair**:
  - Public key → shared openly.
  - Private key → kept secret.
  - Private key cannot realistically be derived from the public key.

- Core rule:
  - Encrypt with **public key** → decrypt with **private key**.
  - Encrypt with **private key** → decrypt with **public key**.

- For confidentiality:
  - Alice encrypts with Bob’s public key.
  - Only Bob can decrypt with his private key.
  - Bob replies using Alice’s public key.

- For integrity, authenticity, and nonrepudiation:
  - Bob encrypts (signs) with his private key.
  - Anyone decrypts with Bob’s public key.
  - If valid:
    - Integrity confirmed.
    - Authenticity confirmed.
    - Nonrepudiation established.
  - In practice, a hash is signed.

- Asymmetric encryption is slower than symmetric encryption.
- Real systems combine both for efficiency.

---

- <img width="743" height="650" alt="image" src="https://github.com/user-attachments/assets/25a9e1ff-d131-4990-ba03-1e776828d37a" />
<img width="1273" height="235" alt="image" src="https://github.com/user-attachments/assets/ac6dfd1e-e1d2-4da2-bf2c-d522a822dd92" />

- <img width="748" height="303" alt="image" src="https://github.com/user-attachments/assets/6fb08019-9eab-463f-b70c-abc3535777e5" />
<img width="1265" height="176" alt="image" src="https://github.com/user-attachments/assets/225f3c3d-bb01-4cd5-a2fb-f32389af54da" />
<img width="828" height="319" alt="image" src="https://github.com/user-attachments/assets/18cb402f-9407-495f-8920-ea103aff1a43" />

- <img width="741" height="324" alt="image" src="https://github.com/user-attachments/assets/50bc09ed-5eea-4bb6-9af3-fe0deafd8a9a" />
<img width="816" height="323" alt="image" src="https://github.com/user-attachments/assets/9ced067f-dd3d-4d19-a6b8-4282e8ffd0ae" />







