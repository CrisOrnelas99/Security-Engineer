# Cheat Sheet: Layer 2 Security (Snooping & Inspection)

## 1. DHCP Snooping
DHCP Snooping is a Layer 2 security feature that acts as a barrier between untrusted hosts and trusted DHCP servers to prevent **Rogue DHCP Server** attacks.



### Key Functions
* **Validation:** Differentiates between Trusted (Server-side) and Untrusted (Client-side) ports.
* **Rate-Limiting:** Prevents DHCP starvation attacks by limiting the number of DHCP packets per second.
* **Binding Database:** The switch builds a table of `MAC Address <-> IP Address <-> Lease <-> VLAN <-> Interface`.

### Drop Conditions
A packet is dropped if:
1.  A DHCP server packet (Offer/Ack) is received on an **untrusted** port.
2.  The Source MAC address does not match the DHCP Client Hardware Address.
3.  A `DHCPRELEASE` or `DHCPDECLINE` is sent from an interface/MAC not matching the database.
4.  The packet includes a relay agent address that is not `0.0.0.0`.

---

## 2. Dynamic ARP Inspection (DAI)
DAI is a security feature that validates Address Resolution Protocol (ARP) packets to prevent **ARP Spoofing/Poisoning**.



### How it Works
1.  **Interception:** The switch intercepts all ARP packets on untrusted ports.
2.  **Verification:** It compares the **Sender MAC** and **Sender IP** in the ARP packet against the **DHCP Snooping Binding Database**.
3.  **Action:** * **Match:** Packet is forwarded.
    * **Mismatch:** Packet is logged and discarded.

### Comparison Example
| Scenario | ARP Sender MAC | ARP Sender IP | Database Entry | Result |
| :--- | :--- | :--- | :--- | :--- |
| **Valid** | `02:c8:85:b5:5a:aa` | `10.10.0.1` | `02:c8:85:b5:5a:aa` / `10.10.0.1` | **Forward** |
| **Spoofed** | `02:c8:85:bb:bb:bb` | `10.10.0.1` | `02:c8:85:b5:5a:aa` / `10.10.0.1` | **Drop** |

---

## 3. Summary Table: L2 Security
| Feature | Protection Against | Layer | Key Dependency |
| :--- | :--- | :--- | :--- |
| **DHCP Snooping** | Rogue DHCP Servers / Starvation | 2 | Trusted/Untrusted Ports |
| **DAI** | ARP Poisoning / Man-in-the-Middle | 2 | DHCP Snooping Binding DB |
