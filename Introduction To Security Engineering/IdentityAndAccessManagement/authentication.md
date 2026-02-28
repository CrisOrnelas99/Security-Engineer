# What I Learned — Authentication (Key Notes)

- **Authentication** verifies the identity of a user/system after they claim it (identification).
- **Identification** = “Who are you?” (username/email/ID).
- **Authentication** = “Prove it’s you.”

- Main authentication factors:
  - **Something you know**
  - **Something you have**
  - **Something you are**
- Less common factors:
  - **Somewhere you are** (location)
  - **Something you do** (behavior)

- **Something you know** (memorized secrets):
  - Passwords
  - Passphrases
  - PINs
  - Phone unlock patterns (still “something you know”)

- **Something you have** (physical possession):
  - Phone/SIM for SMS or call verification codes
  - Hardware security keys (USB/USB-C/NFC) like Yubico, Titan, Nitrokey, Thetis
  - OTP generators

- **Something you are** (biometrics):
  - Fingerprint
  - Face recognition
  - Retina/eye scanners
  - Voice recognition
  - Often used with a PIN/password backup

- **Multi-Factor Authentication (MFA)** = using **2 or more** factors for stronger security.
- **2FA** is a type of MFA (exactly two factors).
  - Example: ATM = card (**something you have**) + PIN (**something you know**).
  - Example: safe = key (**something you have**) + PIN (**something you know**).

- Purpose of MFA:
  - Adds security if one factor is compromised (e.g., weak/stolen password).
