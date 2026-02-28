#  What I Learned — Access Control Models (DAC, RBAC, MAC)

- Access control models define how a system grants/blocks access to resources.
- Common models:
  - **DAC (Discretionary Access Control)**
  - **RBAC (Role-Based Access Control)**
  - **MAC (Mandatory Access Control)**

- **DAC**
  - The **resource owner** chooses who gets access and what permissions they have.
  - Example: sharing a folder/album by adding specific users.
  - Works well for small/simple sharing.
  - Becomes hard to manage at scale, especially when roles change often.

- **RBAC**
  - Access is based on a user’s **role/group** (job function).
  - Example: accountants can access accounting resources but not R&D resources.
  - Easier to manage at scale:
    - New role → add user to new group
    - Role removed → remove user from group

- **MAC**
  - System-enforced strict security model that limits user control.
  - Used for highly sensitive/classified environments.
  - Users typically cannot:
    - Change permissions freely
    - Install software
    - Perform non-required actions
  - Linux examples:
    - **AppArmor** (Debian/Ubuntu)
    - **SELinux** (Red Hat/Fedora)
