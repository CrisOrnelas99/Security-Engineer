🔐 Filesystem Partition & Encryption
🧩 Encryption Fundamentals

Encryption converts data into unreadable format without a decryption key.

Protects data even if an attacker gains full physical access (e.g., stolen laptop).

Encrypted disk = useless data without key, similar to damaged storage.

💽 LUKS (Linux Unified Key Setup)

LUKS is a standard for Linux disk encryption.

Uses block device encryption with flexible cipher support.

Commonly integrated into modern Linux distributions.

📦 LUKS Disk Layout

phdr (Partition Header)

Stores UUID, cipher, cipher mode, key length, master key checksum.

KM1–KM8 (Key Material Slots)

Up to 8 key slots, each containing the master key encrypted with a user password.

Multiple users can unlock the same encrypted disk using different passwords.

Bulk Data

Actual data encrypted using the master key.

🔑 Key Derivation (PBKDF2)

User password is not used directly as encryption key.

Key is derived using PBKDF2 (Password-Based Key Derivation Function 2):

key = PBKDF2(password, salt, iteration_count, derived_key_length)

Salt + iterations increase resistance to brute-force attacks.

🔄 Encryption & Decryption Process

Encryption:

enc_data = encrypt(cipher_name, cipher_mode, key, original, original_length)

Decryption:

original = decrypt(cipher_name, cipher_mode, key, enc_data, original_length)

Supports multiple ciphers and modes (e.g., AES-XTS).

🛠️ LUKS Setup (Command Line)
Installation
apt install cryptsetup
yum install cryptsetup-luks
dnf install cryptsetup-luks
Steps

Identify partition

lsblk
fdisk -l
blkid

Encrypt partition

cryptsetup -y -v luksFormat /dev/sdb1

Open encrypted partition

cryptsetup luksOpen /dev/sdb1 EDCdrive

Overwrite existing data

dd if=/dev/zero of=/dev/mapper/EDCdrive

Create filesystem

mkfs.ext4 /dev/mapper/EDCdrive

Mount partition

mount /dev/mapper/EDCdrive /media/secure-USB
🔍 LUKS Configuration Inspection
cryptsetup luksDump /dev/sdb1

Displays:

UUID

Cipher (e.g., aes-xts-plain64)

Key size (e.g., 512-bit)

PBKDF settings (e.g., SHA256, iterations, salt)
