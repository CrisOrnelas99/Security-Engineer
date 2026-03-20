🔐 Securing Remote Access
🌍 Remote Access Risks

Remote access is convenient but exposes a service attackers can target.

Common threats:

Password sniffing

Password guessing / brute force

Exploiting the remote service

🛡️ Protect Against Password Sniffing

Use encrypted remote access protocols.

SSH is the standard secure protocol for remote access and file transfer.

Telnet sends credentials in cleartext and is insecure.

Avoid any protocol that does not encrypt traffic.

🔑 Protect Against Password Guessing

Internet-facing SSH servers are constantly targeted for login attempts.

Attackers often try:

root account

common passwords

reused passwords

Even a strong-looking password can fail if it is common or reused.

🚫 SSH Hardening Guidelines

Disable remote root login

Disable password authentication

Use public key authentication only

⚙️ sshd_config Security Settings

SSH server configuration file:

/etc/ssh/sshd_config
Disable root login
PermitRootLogin no
Enable public key authentication
PubkeyAuthentication yes
Disable password authentication
PasswordAuthentication no
🗝️ SSH Key Authentication

Public key authentication is more secure than passwords.

Generate an SSH key pair:

ssh-keygen -t rsa

Creates:

Private key → id_rsa

Public key → id_rsa.pub

📤 Copy Public Key to Server

Transfer public key to target SSH server:

ssh-copy-id username@server

Server uses the public key to authenticate the user without a password.

⚠️ Important Precaution

Confirm physical or alternate access before disabling password login.

Prevents accidental lockout if key-based login is not working.

✅ Key Security Points

Use SSH, never Telnet, for remote access.

Block direct root login.

Prefer SSH keys over passwords.

Disable password authentication after verifying key access.

Strong remote access security reduces brute-force and credential theft risks.
