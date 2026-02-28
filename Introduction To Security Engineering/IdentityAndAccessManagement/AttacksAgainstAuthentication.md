# What I Learned — Weak Authentication Protocols & Replay Attacks

- Creating your own authentication protocol is dangerous.
- Always use **tested and peer-reviewed protocols** instead of designing custom ones.

- Analogue example (shared passphrase):
  - Club uses a secret phrase for entry.
  - If attacker overhears it → they can enter.
  - Even multiple secret Q&A pairs can eventually be learned.
  - Simple shared secrets are vulnerable to eavesdropping.

- Digital problem:
  - Sending **username + password in cleartext** → attackers can capture credentials.
  - Encrypting password with a shared secret key seems safer.
  - But if the encrypted password is always the same, it can be reused.

- **Replay Attack**:
  - Attacker captures a valid login packet.
  - Re-sends (replays) it later.
  - Server accepts it as valid.
  - Attacker authenticates without knowing the password.

- Root problem:
  - Authentication response is **static and reusable**.

- Solution concept:
  - Make each authentication attempt **unique**.
  - Example: include **current time/date** in the encrypted response.
  - Ensures response is valid only for a short period.
  - Requires time synchronization.

- Key takeaway:
  - Authentication protocols must prevent:
    - Eavesdropping
    - Replay attacks
  - Proper cryptographic design is critical.
  - Never rely on naive or home-made authentication mechanisms.
