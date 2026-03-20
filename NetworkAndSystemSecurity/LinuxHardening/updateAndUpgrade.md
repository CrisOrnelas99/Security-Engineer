🔄 System Updates & Patch Management
🛡️ Importance of Updates

Regular updates fix security vulnerabilities and bugs.

Outdated systems are vulnerable to known exploits.

Always keep both software and kernel updated.

🐧 Updating Linux Systems
Debian-Based (Ubuntu)
apt update
apt upgrade

apt update → refresh package list

apt upgrade → install available updates

RedHat/Fedora
dnf update     # Newer systems (RHEL 8+)
yum update     # Older systems (RHEL 7-)
📦 Ubuntu LTS (Long Term Support)

Released every 2 years (e.g., 18.04, 20.04, 22.04).

Provides:

5 years free security updates

+5 years with Extended Security Maintenance (ESM) (paid)

Running unsupported versions = security risk.

🟥 RedHat Lifecycle

Total support: ~12 years

Full Support → 5 years

Maintenance Support → 5 years

Extended Life Phase → 2 years

Designed for long-term production stability.

⚙️ Kernel Updates

Kernel vulnerabilities can lead to full system compromise.

Example: Dirty COW

Exploits race condition in memory handling

Allows privilege escalation to root

Always update kernel to patch critical flaws.

🤖 Automatic Updates

Ensure updates are applied regularly.

Options:

Enable automatic updates

Monitor security advisories

Best suited for systems prioritising stability.

⚠️ Risks of Outdated Systems

No security patches → exposed to public exploits

Can compromise:

The system itself

The entire network

✅ Key Security Points

Regularly update packages and kernel.

Use supported OS versions (LTS or enterprise).

Enable automatic updates where appropriate.

Monitor security vulnerabilities and advisories.

Avoid running end-of-life systems.
