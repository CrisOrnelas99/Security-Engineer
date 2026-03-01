# What I learned – Security Principles & Models

##  Overview
This room explores the foundational concepts of security, including the **CIA Triad**, extended security principles, major security models, defense-in-depth, ISO/IEC design principles, trust models, and risk terminology.

Understanding these principles is critical for designing secure systems and making informed security decisions.

---

#  The CIA Triad

Security is commonly evaluated using three core principles:

##  Confidentiality
Ensures that only authorized individuals can access sensitive data.

- Example (Online Shopping): Credit card details should only be visible to the payment processor.
- Example (Healthcare): Medical records must remain private under legal regulations.

---

##  Integrity
Ensures data cannot be altered without detection.

- Example (Online Shopping): Shipping address should not be modified by an attacker.
- Example (Healthcare): Altered medical records could lead to life-threatening treatment errors.

---

##  Availability
Ensures systems and services are accessible when needed.

- Example (Online Shopping): Website must be accessible to place orders.
- Example (Healthcare): Doctors must access patient records during visits.

>  Security requires balancing all three. Over-prioritizing one can weaken the others.

---

#  The DAD Triad (Opposite of CIA)

- **Disclosure** → Opposite of Confidentiality  
- **Alteration** → Opposite of Integrity  
- **Destruction/Denial** → Opposite of Availability  

Attacks typically target one of these three areas.

---

#  Beyond CIA

##  Authenticity
Ensures data truly comes from the claimed source.

##  Nonrepudiation
Ensures a sender cannot deny their action (e.g., placing an order).

Both are essential for:
- E-commerce
- Banking
- Healthcare
- Legal systems

---

#  Parkerian Hexad

Proposed by Donn Parker (1998), expanding CIA into six elements:

1. Confidentiality  
2. Integrity  
3. Availability  
4. Authenticity  
5. Utility  
6. Possession  

###  Utility
Data must be usable. Encrypted data without a key has no utility.

###  Possession
Protects against unauthorized control or theft (e.g., ransomware or stolen backups).

---

#  Security Models

##  Bell-LaPadula Model (Confidentiality)

- **No Read Up** (Simple Security Property)
- **No Write Down** (Star Property)
- Uses access control matrix

Summary: *Write Up, Read Down*

Focus: Prevent disclosure of sensitive data.

---

##  Biba Model (Integrity)

- **No Read Down**
- **No Write Up**

Summary: *Read Up, Write Down*

Focus: Prevent data corruption.

---

##  Clark-Wilson Model (Integrity via Controlled Access)

Key Concepts:
- **CDI (Constrained Data Item)** – Protected data
- **UDI (Unconstrained Data Item)** – External input
- **TP (Transformation Procedure)** – Authorized operations
- **IVP (Integrity Verification Procedure)** – Validates integrity

Focus: Integrity through well-defined processes.

---

#  Defence-in-Depth (Multi-Level Security)

Security should exist in multiple layers.

Example:
- Locked drawer  
- Locked room  
- Locked building  
- Security cameras  

Even if one control fails, others remain in place.

---

#  ISO/IEC 19249 Principles

## Architectural Principles

- **Domain Separation** – Separate privilege levels
- **Layering** – Security at multiple abstraction levels
- **Encapsulation** – Hide internal implementation
- **Redundancy** – Backup systems for availability
- **Virtualization** – Isolated environments for containment

---

## Design Principles

- **Least Privilege** – Grant minimal required access
- **Attack Surface Minimization** – Disable unnecessary services
- **Centralized Parameter Validation** – Validate inputs in one place
- **Centralized Security Services** – Central authentication systems
- **Fail-Safe Error Handling** – Fail securely without leaking data

---

#  Trust Models

## Trust but Verify
- Trust entities but monitor and log activity.
- Requires IDS/IPS, logging, and monitoring systems.

## Zero Trust
- Never trust by default.
- Always authenticate and authorize.
- Assume breach.
- Uses microsegmentation and strict access control.

---

#  Vulnerability, Threat, and Risk

## Vulnerability
A weakness in a system.

## Threat
A potential danger exploiting that weakness.

## Risk
Likelihood × Impact of a threat exploiting a vulnerability.

> Security decisions are risk-based — not all risks can be eliminated.

---

#  Key Takeaways

- Security revolves around **Confidentiality, Integrity, and Availability**.
- Additional elements include **Authenticity, Nonrepudiation, Utility, and Possession**.
- Security requires layered defense and structured models.
- Risk management balances protection with business needs.
- Zero Trust reduces implicit trust and limits breach impact.

---

##  Reflection

Effective security is not about eliminating all threats —  
it is about reducing risk to acceptable levels while maintaining business functionality.
