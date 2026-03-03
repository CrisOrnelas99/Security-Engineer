# TryHackMe – STRIDE Framework | Notes & Key Concepts Learned

## Overview

The STRIDE framework is a threat modelling methodology developed by Microsoft to identify and categorise security threats in systems and software design.

STRIDE is based on six threat categories:

| Category | Definition | Security Principle Violated |
|-----------|------------|----------------------------|
| Spoofing | Impersonating a user or system to gain unauthorised access | Authentication |
| Tampering | Unauthorised modification of data or code | Integrity |
| Repudiation | Denying an action due to lack of logging or auditing | Non-repudiation |
| Information Disclosure | Unauthorised access to sensitive information | Confidentiality |
| Denial of Service | Disrupting availability of systems or services | Availability |
| Elevation of Privilege | Gaining higher access rights than permitted | Authorisation |

STRIDE is closely aligned with the CIA triad and core security principles.

---

## STRIDE Categories Explained

### Spoofing (Authentication Violation)
Impersonating another user or system.

Examples:
- Sending emails as another user
- Creating phishing websites to steal credentials

---

### Tampering (Integrity Violation)
Modifying data, files, or configurations without authorisation.

Examples:
- Changing another user’s password
- Installing backdoors using elevated access

---

### Repudiation (Non-repudiation Violation)
Denying actions due to insufficient logging or auditing.

Examples:
- Denying fraudulent transactions
- Denying sending malicious communications

---

### Information Disclosure (Confidentiality Violation)
Exposing sensitive data to unauthorised parties.

Examples:
- Accessing misconfigured databases
- Publicly exposed cloud storage with sensitive documents

---

### Denial of Service (Availability Violation)
Making systems unavailable to legitimate users.

Examples:
- Flooding servers with traffic
- Ransomware encrypting critical systems

---

### Elevation of Privilege (Authorisation Violation)
Gaining higher permissions than intended.

Examples:
- Accessing admin consoles as a normal user
- Exploiting local privilege escalation vulnerabilities

---

## STRIDE in Threat Modelling

A structured approach to applying STRIDE:

### 1. System Decomposition
- Break the system into components (applications, services, networks, data flows).
- Identify trust boundaries and attack surfaces.

### 2. Apply STRIDE Categories
- Analyse each component against all six STRIDE categories.
- Identify relevant threats per category.

### 3. Threat Assessment
- Evaluate likelihood and impact.
- Prioritise based on overall risk.

### 4. Develop Countermeasures
- Implement controls aligned to each category.
  - Example: Prevent spoofing with SPF, DKIM, and DMARC.
  - Prevent tampering with integrity checks and access controls.
  - Prevent EoP through patching and least privilege.

### 5. Validation and Verification
- Conduct testing (penetration testing, code reviews, audits).
- Confirm controls effectively mitigate risks.

### 6. Continuous Improvement
- Update threat models as systems evolve.
- Monitor emerging threats.
- Improve controls over time.

---

## STRIDE Checklist Representation

Threat modelling results are often represented in a checklist format, marking which STRIDE categories apply to each scenario.  

Some attack scenarios may fall under multiple categories.

Example mappings:
- Spoofed email → Spoofing + Repudiation  
- SQL injection → Tampering + Information Disclosure  
- Public cloud data exposure → Information Disclosure  
- Privilege escalation exploit → Elevation of Privilege + Tampering  

---

## Practical Application Scenario

Scenario:
An e-commerce company is designing a new cloud-based payment processing system.

Critical assets:
- Customer payment data
- Transaction records
- Sensitive business information

Teams involved:
- Development Team
- System Architecture Team
- Security Team
- Business Stakeholders
- Network Infrastructure Team

Using STRIDE in this context ensures:

- Authentication mechanisms prevent spoofing.
- Data integrity protections prevent tampering.
- Logging prevents repudiation.
- Encryption prevents information disclosure.
- Redundancy and monitoring prevent denial of service.
- Least privilege and patching prevent elevation of privilege.

---

## Key Concepts Reinforced

- STRIDE provides a structured way to categorise threats.
- Each category aligns with a core security principle.
- Systems must be analysed component-by-component.
- Multiple STRIDE categories may apply to a single threat.
- Threat modelling requires cross-team collaboration.
- STRIDE supports proactive identification of vulnerabilities before deployment.

The STRIDE framework strengthens secure system design by ensuring that authentication, integrity, confidentiality, availability, and authorisation are systematically evaluated.
