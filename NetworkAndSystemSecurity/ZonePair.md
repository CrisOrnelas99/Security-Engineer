This summary is designed to be saved as a .md (Markdown) file. It strips away the conversational filler and organizes the technical concepts into a structured, high-level overview of Zone-Based Firewalls and VyOS configuration.Markdown# Cheat Sheet: Zone-Based Firewalls (ZBF) & VyOS
# Cheat Sheet: Zone-Based Firewalls (ZBF) & VyOS

## 1. Key Concepts
* **Traffic Correlation:** Standardizing packet states based on protocol, process, and direction.
* **Stateless vs. Stateful:**
    * **Stateless:** Filters packets individually without context (e.g., standard ACLs).
    * **Stateful:** Tracks the state of network connections. It understands if a packet is part of an existing, valid session.
* **Zone-Pairs:** A direction-based policy enforcing traffic rules between two specific zones (e.g., LAN → WAN). Each direction requires its own rule.

---

## 2. Firewall Logic & Hierarchy


1.  **Define Zones:** Assign a common name to a physical or virtual interface (VLAN).
2.  **Set Default Actions:** Usually set to `drop` (Security by Default).
3.  **Create Rulesets:** Define what specific traffic is allowed or denied.
4.  **Apply Zone-Pairs:** Bind the ruleset to a source and destination.

---

## 3. VyOS Configuration Syntax

### Initializing Zones
Before rules are applied, interfaces must be mapped to zones:
```bash
# Define zone name, default action, and member interface
set zone-policy zone <ZONE_NAME> default-action drop
set zone-policy zone <ZONE_NAME> interface <ethX.VLAN>
Defining RulesetsRulesets handle the logic. Standard practice includes allowing "Established" and "Related" traffic so return traffic isn't blocked.Bashname <RULESET_NAME> {
  default-action drop
  
  # Rule 1: Allow established/related traffic (Stateful)
  rule 1 {
    action accept
    state {
      established enable
      related enable
    }
  }
  
  # Rule 2: Drop invalid packets
  rule 2 {
    action drop
    state {
      invalid enable
    }
  }

  # Custom Rule: Example for ICMP (Ping)
  rule 100 {
    action accept
    protocol ipv4-icmp
    log enable
  }
}
Applying the Zone-PairThis command "glues" the ruleset to the directional flow between two zones.Bashset zone-policy zone <DEST_ZONE> from <SOURCE_ZONE> firewall name <RULESET_NAME>
4. Quick Reference Table: PlanningWhen designing a firewall, map out every possible interaction:SourceDestinationProtocolActionLANWANHTTP/HTTPSAcceptWANLANICMPDropLANLOCALSSHAcceptANYANYANYDrop (Default)5. Troubleshooting & TipsDirection Matters: LAN → WAN is a different policy than WAN → LAN.IPv6: Don't forget to create specific rules for IPv6 if your network uses it; IPv4 rules will not catch IPv6 traffic.Interface Naming: Ensure sub-interfaces match your VLANs (e.g., eth0.30 for VLAN 30).
## 1. Key Concepts
* **Traffic Correlation:** Standardizing packet states based on protocol, process, and direction.
* **Stateless vs. Stateful:**
    * **Stateless:** Filters packets individually without context (e.g., standard ACLs).
    * **Stateful:** Tracks the state of network connections. It understands if a packet is part of an existing, valid session.
* **Zone-Pairs:** A direction-based policy enforcing traffic rules between two specific zones (e.g., LAN → WAN). Each direction requires its own rule.

---

## 2. Firewall Logic & Hierarchy


1.  **Define Zones:** Assign a common name to a physical or virtual interface (VLAN).
2.  **Set Default Actions:** Usually set to `drop` (Security by Default).
3.  **Create Rulesets:** Define what specific traffic is allowed or denied.
4.  **Apply Zone-Pairs:** Bind the ruleset to a source and destination.

---

## 3. VyOS Configuration Syntax

### Initializing Zones
Before rules are applied, interfaces must be mapped to zones:
```bash
# Define zone name, default action, and member interface
set zone-policy zone <ZONE_NAME> default-action drop
set zone-policy zone <ZONE_NAME> interface <ethX.VLAN>
Defining RulesetsRulesets handle the logic. Standard practice includes allowing "Established" and "Related" traffic so return traffic isn't blocked.Bashname <RULESET_NAME> {
  default-action drop
  
  # Rule 1: Allow established/related traffic (Stateful)
  rule 1 {
    action accept
    state {
      established enable
      related enable
    }
  }
  
  # Rule 2: Drop invalid packets
  rule 2 {
    action drop
    state {
      invalid enable
    }
  }

  # Custom Rule: Example for ICMP (Ping)
  rule 100 {
    action accept
    protocol ipv4-icmp
    log enable
  }
}
Applying the Zone-PairThis command "glues" the ruleset to the directional flow between two zones.Bashset zone-policy zone <DEST_ZONE> from <SOURCE_ZONE> firewall name <RULESET_NAME>
4. Quick Reference Table: PlanningWhen designing a firewall, map out every possible interaction:SourceDestinationProtocolActionLANWANHTTP/HTTPSAcceptWANLANICMPDropLANLOCALSSHAcceptANYANYANYDrop (Default)5. Troubleshooting & TipsDirection Matters: LAN → WAN is a different policy than WAN → LAN.IPv6: Don't forget to create specific rules for IPv6 if your network uses it; IPv4 rules will not catch IPv6 traffic.Interface Naming: Ensure sub-interfaces match your VLANs (e.g., eth0.30 for VLAN 30).
