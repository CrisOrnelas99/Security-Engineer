# What I Learned — Authorisation (Key Notes)

- **Authorisation** happens **after authentication**.
- It defines **what an authenticated user is allowed to access and do**.

- Authorisation examples:
  - Gym member can use equipment during business hours, but cannot take equipment home.
  - Hotel guest can access their assigned room and allowed facilities, but not other rooms.
  - Employee (sales) can access sales files, but not HR/accounting files.

- **Access control** is what **enforces** authorisation rules.
  - Authorisation = the policy/permissions (what should be allowed).
  - Access control = the mechanism that enforces it (locks, keys, smart cards, file permissions, server rules).

- In systems:
  - You can access your own account/resources (e.g., your email inbox).
  - You should be denied access to other users’ resources by default.
