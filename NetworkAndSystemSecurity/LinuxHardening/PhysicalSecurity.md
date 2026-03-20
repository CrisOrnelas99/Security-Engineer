🛡️ Physical Security & Defence-in-Depth
Defence-in-Depth

Defence-in-Depth means using multiple layers of security instead of relying on one control.

Physical security is one of the first security layers because physical access can bypass many software protections.

🚪 Physical Security Importance

Prevent attackers from gaining physical access to computer systems.

If an attacker enters an office or server room, they can:

Remove the disk drive

Steal the whole system

Perform attacks that require little technical skill

🔓 Physical Access Risks

Even with strong, complex passwords, physical access can still compromise a system.

An attacker can use GRUB to reset the root account password.

Key idea: “Boot access = root access”

This means anyone who can access the boot process may gain administrative control.

🖥️ Boot Protection with GRUB

If physical security fails, extra protection should be added at the bootloader level.

Many BIOS/UEFI firmware systems allow a boot password.

A boot password can stop unauthorised users from booting the system.

This is more suitable for personal systems than servers.

⚠️ Limitation on Servers

Boot passwords are usually impractical for servers because someone must be physically present to enter the password.

For remote or enterprise servers, this may interrupt normal operations.

🔐 GRUB Password Protection

A GRUB password helps prevent unauthorised users from:

Accessing advanced boot options

Resetting the root password

Booting into modes that provide root access

A common tool used is grub2-mkpasswd-pbkdf2

This tool:

Prompts for the password twice

Generates a PBKDF2 hash

Produces a hash that is added to the correct GRUB configuration file

🧾 Command Syntax
grub2-mkpasswd-pbkdf2
Output Purpose

The generated PBKDF2 hash is placed in the appropriate GRUB config file.

The exact file depends on the Linux distribution, such as Fedora or Ubuntu.

☁️ Cloud System Limitation

GRUB password protection is generally not useful in cloud environments.

In cloud systems, users usually do not have physical terminal access, so a boot password is not practical.
