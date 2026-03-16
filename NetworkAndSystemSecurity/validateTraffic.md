# Cheat Sheet: Network Zoning, Firewalls & SSL Inspection

## 1. Network & Firewall Fundamentals
* **Traffic Correlation:** Identifying the state of a packet based on (Protocol, Process, Direction, etc.).
* **Stateless vs. Stateful:**
    * **Stateless:** Filters packets individually (e.g., standard ACLs). No memory of past packets.
    * **Stateful:** Tracks the state of active connections. Filters based on protocols, ports, and session history.

---

## 2. Zone-Based Policy (ZBF)
Zone-pairs are **direction-based** and **stateful**. Traffic must be explicitly defined for every direction between every VLAN/Zone.



### VyOS Configuration Workflow
1.  **Assign Interfaces to Zones:**
    ```bash
    set zone-policy zone LAN default-action drop
    set zone-policy zone LAN interface eth0.10
    ```
2.  **Define Rulesets (State Management):**
    Always include rules for established/related traffic to allow return packets.
    ```bash
    name lan-wan {
      default-action drop
      rule 1 {
        action accept
        state { established enable; related enable }
      }
      rule 100 {
        action accept
        protocol ipv4-icmp
      }
    }
    ```
3.  **Apply Zone-Pair:**
    ```bash
    set zone-policy zone WAN from LAN firewall name lan-wan
    ```

---

## 3. SSL/TLS Inspection (Deep Packet Inspection)
Standard firewalls cannot see inside HTTPS (Port 443). SSL Inspection acts as a **transparent proxy** to decrypt and scan traffic.



### The Process
1.  **Intercept:** Acts as a "Man-in-the-Middle" (MITM) between the host and the internet.
2.  **Decrypt:** Breaks the encryption to reveal the plaintext data.
3.  **Inspect (UTM):** Feeds data into **IPS (Intrusion Prevention)** and **Web Filters**.
4.  **Re-encrypt:** Packs the data back up and sends it to the destination.

### Comparison: Pros vs. Cons
| Feature | Benefit/Risk |
| :--- | :--- |
| **Visibility** | Detects malware beacons hidden in legitimate HTTPS traffic. |
| **Security** | Allows IPS/UTM to scan for exploits in encrypted streams. |
| **Privacy** | **Risk:** Can intercept sensitive data (passwords, banking info). |
| **Performance** | **Risk:** High CPU overhead; acts as a single point of failure. |
| **Bypass** | Advanced actors may use "Trusted Domains" to evade inspection. |

---

## 4. Quick Reference: Zone-Pair Mapping
| Source Zone | Destination Zone | Protocol | Action |
| :--- | :--- | :--- | :--- |
| LAN | WAN | HTTPS/DNS | Accept |
| WAN | LAN | ICMP | Drop (Default) |
| LOCAL | LAN | SSH | Accept |
