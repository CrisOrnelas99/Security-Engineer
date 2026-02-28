# What I Learned — Accountability, Logging, Log Forwarding, SIEM

- **Accountability** means users can be held responsible for actions they perform after they are authenticated and authorised.
- Accountability requires **auditing**, which depends on **logging**.

- Why accountability matters:
  - Prevents abuse of access (insiders/rogue employees).
  - Builds trust in systems (example: bank teller actions must be traceable).
  - Allows investigations when something goes wrong.

- **Logging** = recording events in a system, including:
  - User actions (who did what)
  - System events
  - Errors
  - Access attempts
- Logs support:
  - Compliance/audits
  - Incident response
  - Forensics (finding what happened and who did it)

- With good logging, security teams can:
  - Detect anomalies (unusual access patterns)
  - Spot attacks (repeated failed logins)
  - Trigger alerts when suspicious activity occurs

- Logs must be protected:
  - Should be stored **securely**
  - Often need to be **tamper-proof**
  - Attackers may try to delete/modify logs to hide actions

- **Log forwarding** = sending logs from systems to a central location.
  - Helps store logs safely (often on a separate logging server)
  - Combines logs from many sources for easier monitoring

- Benefit of centralised logs:
  - Easier correlation across multiple systems
  - Better detection of multi-step attacks

- **SIEM (Security Information and Event Management)**:
  - Collects logs from many sources
  - Analyses them for threats/anomalies
  - Sends alerts to security teams
  - Supports compliance reporting and forensic investigations
