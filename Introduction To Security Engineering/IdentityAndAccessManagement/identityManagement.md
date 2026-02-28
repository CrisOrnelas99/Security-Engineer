#  What I Learned — IdM vs IAM (Key Notes)

- **Identity Management (IdM)** is the policies + technologies for:
  - **Identification**
  - **Authentication**
  - **Authorisation**
- Goal: ensure **authorised users/devices** get access to needed resources, and **unauthorised** are blocked.
- Requires every user/device to have a **digital identity**.

- Why IdM matters:
  - Protects sensitive data
  - Supports regulatory compliance
  - Streamlines access processes
  - Reduces identity-related costs
  - Improves user experience

- IdM systems commonly provide:
  - **Centralised identity database** (users + access rights)
  - **User provisioning** (create/manage accounts)
  - Authentication + authorisation management
  - Monitoring of user access
- Benefit: simplifies identity control across many systems and reduces unauthorised access risk.

- **Identity and Access Management (IAM)** is broader than IdM:
  - Includes IdM functions plus more controls and governance.
  - Common IAM features:
    - User provisioning + lifecycle (onboarding/offboarding)
    - Access control (e.g., RBAC)
    - **MFA**
    - **Single Sign-On (SSO)**
    - Identity governance + compliance management
    - Auditing and monitoring access/activity
- IAM helps meet requirements like **HIPAA, GDPR, PCI DSS**.

- Relationship between IdM and IAM:
  - Some sources use them interchangeably.
  - Other sources separate them:
    - **IdM** = managing identities, attributes, permissions (users/devices/groups).
    - **IAM** = broader system that evaluates policy and enforces access decisions + governance.
- Boundary is often blurry, but IAM is usually the more complete access/security platform.
