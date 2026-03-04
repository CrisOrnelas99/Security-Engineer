# TryHackMe – Supply Chain Risk | Notes & Key Concepts Learned

## Supply Chain

A supply chain is a sequence of suppliers that contribute to the delivery of a product.

In information systems, the product can be:

- Hardware
- Software
- Services

Supply chain risk arises when vulnerabilities exist within suppliers that may impact the organisation relying on them.

---

# Types of Supply Chain Risks

## Hardware-Related Risk

Threat actors may introduce malicious components into hardware.

Example:
- Hardware Trojans embedded in electronic devices.

Purpose:
- Provide unauthorised functionality.
- Create hidden access points.
- Compromise system integrity.

---

## Software-Related Risk

Software can be compromised during development or distribution.

Example:
- Inserting malicious code (Software Trojan) into source code.

Worst-case scenario:
- Attacker successfully modifies source code before distribution.

Impact:
- Data compromise
- System manipulation
- Long-term persistent access

---

## Service-Related Risk

Third-party service providers may introduce risk.

Examples:
- Downtime
- Data breaches
- Service outages

Organisations must evaluate:
- The security posture of service providers
- Their security controls and practices
- Their incident response capabilities

---

# Example Scenario – Accounting Firm

An accounting firm relies on multiple suppliers:

### Hardware Supplier
- Computers
- Printers

### Software Supplier
- Accounting software

### Service Provider
- Email services

Even if the accounting firm implements strong internal security controls, risk may originate from:

- Malicious code inserted into accounting software.
- Compromise of email provider servers.
- Hardware tampering before delivery.

This demonstrates that security extends beyond internal controls and must include supplier risk evaluation.

---

# Key Concepts Reinforced

- Supply chain risk affects hardware, software, and services.
- Third-party dependencies introduce indirect risk.
- A strong internal security posture is insufficient without supplier assessment.
- Compromise at any point in the supply chain can impact confidentiality, integrity, and availability.
- Organisations must assess supplier security programs before engaging services.

Supply chain security is a critical component of overall risk management.
