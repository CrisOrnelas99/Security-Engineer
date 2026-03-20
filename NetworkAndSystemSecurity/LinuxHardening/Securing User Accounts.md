👤 Privilege Management & Account Security
⚠️ Root Account Risks

Root account has unrestricted system control → high risk of misconfiguration.

Mistakes as root can render the system unusable or unbootable.

Best practice: avoid daily use of root; use non-root accounts.

🔑 Using sudo

sudo (Super User Do) allows controlled execution of privileged commands.

Users must be added to the sudoers group.

Add User to sudo Group (Debian/Ubuntu)
usermod -aG sudo username
Add User to wheel Group (RedHat/Fedora)
usermod -aG wheel username

-aG → append user to group without removing existing memberships.

🚫 Disable Root Account

Prevent direct root login by changing its shell.

Modify /etc/passwd
root:x:0:0:root:/root:/sbin/nologin

Replaces /bin/bash with /sbin/nologin.

Blocks interactive login for root.

🔐 Enforce Strong Password Policy
Configuration Files

RedHat/Fedora:

/etc/security/pwquality.conf

Debian/Ubuntu:

/etc/pam.d/common-password
Install Library (Debian/Ubuntu)
apt-get install libpam-pwquality
Key Options

difok → minimum character differences from old password

minlen → minimum password length

minclass → required character classes (uppercase, lowercase, digits, etc.)

badwords → disallowed words in passwords

retry → number of attempts allowed

Example Config
difok=5
minlen=10
minclass=3
retry=2
👥 Disable Unused Accounts

Remove access for users no longer needing the system.

Method: Change Shell

Edit /etc/passwd:

michael:x:1000:1000:Michael:/home/michael:/sbin/nologin

Prevents login while preserving account data.

⚙️ Secure Service Accounts

Service accounts (e.g., www-data, nginx, mongo) should:

Use /sbin/nologin

Not allow interactive login

Reduces impact of Remote Code Execution (RCE) vulnerabilities.

✅ Key Security Points

Avoid direct root usage; use sudo for privilege escalation.

Disable root login to reduce attack surface.

Enforce strong password policies using pwquality.

Disable unused and service accounts to prevent misuse.

Apply least privilege principle across all accounts.
