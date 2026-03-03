# TryHackMe – MITRE ATT&CK Framework | Notes & Key Concepts Learned

## Overview of MITRE ATT&CK

MITRE ATT&CK (Adversarial Tactics, Techniques, and Common Knowledge) is a globally accessible knowledge base of adversary behaviors and attack methods. Developed by the MITRE Corporation, it helps organisations understand how attackers operate and how to defend against them.

The framework is structured as a matrix consisting of:

- **Tactics** – High-level adversary objectives (e.g., Initial Access, Privilege Escalation).
- **Techniques** – Specific methods used to achieve those objectives.

Each technique page typically includes:

- Technique name and detailed description
- Procedure examples (real-world usage by threat actors)
- Mitigations (recommended defensive measures)
- Detections (ways to identify the activity)
- References (external research and reports)

This structure provides both offensive insight and defensive guidance.

---

## Integrating MITRE ATT&CK into Threat Modelling

MITRE ATT&CK can be incorporated into the threat modelling process after identifying threats.

Updated flow:

1. Identify Threats  
2. Map to MITRE ATT&CK  

After identifying threats, they can be mapped to relevant ATT&CK tactics and techniques. This mapping provides:

- Deeper understanding of attacker behavior
- Real-world examples of exploitation
- Suggested mitigations and detection strategies
- Structured prioritisation of risks

Using ATT&CK improves visibility into potential attack paths and strengthens defensive planning.

---

## Common Use Cases of MITRE ATT&CK

The framework can be used for:

- Identifying potential attack paths based on infrastructure
- Developing threat scenarios aligned with known threat groups
- Prioritising vulnerability remediation
- Improving detection engineering
- Enhancing incident response preparedness

For example:
- If an organisation uses Office 365, techniques targeting O365 become directly relevant.
- If operating in a specific industry, mapped threat groups targeting that industry can guide defensive focus.

---

# MITRE ATT&CK Navigator

The ATT&CK Navigator is an open-source, web-based tool used to visualise and customise ATT&CK matrices.

It allows security teams to:

- Create custom layers
- Select and highlight relevant techniques
- Filter techniques by platform or technology
- Score and annotate techniques
- Export results for reporting and reuse

---

## Matrices Available

Three matrices exist:

- **Enterprise** – Enterprise networks and IT environments
- **Mobile** – Mobile devices and platforms
- **ICS** – Industrial Control Systems

For most organisations, the Enterprise matrix is the primary focus.

---

## Key Navigator Features

### 1. Searching & Selecting Techniques

- Search by keyword, threat group, software, mitigation, campaign, or data source.
- Selecting a threat group highlights all techniques attributed to it.
- Techniques can be multi-selected and grouped.

---

### 2. Viewing, Sorting & Filtering

- Filter by platform (e.g., Windows, Linux, Office365, GCP).
- Sort alphabetically or by score.
- Expand sub-techniques for deeper visibility.
- Export layers as JSON, Excel, or SVG.

This enables focused analysis on specific technologies or threat actors.

---

### 3. Annotating Techniques

Techniques can be annotated with:

- Background color (grouping/highlighting)
- Scores (impact, likelihood, priority)
- Comments (observations or notes)
- Metadata (custom tags)
- External links
- Toggle state (disable/grey out techniques)

Annotations help prioritise and document threat modelling decisions.

---

# Practical Scenario Application

Scenario context:

Industry: Financial Services  
Threat Groups:
- APT28
- APT29
- Carbanak
- FIN7
- Lazarus Group

Technologies Used:
- Google Cloud Platform (GCP)
- Internal online banking platform
- CRM system

Critical Assets:
- Customer financial data
- Transaction records
- Personally Identifiable Information (PII)

Using ATT&CK Navigator:

1. Map techniques attributed to relevant threat groups.
2. Filter techniques related to GCP and web applications.
3. Identify techniques that directly impact critical assets.
4. Prioritise high-impact techniques.

---

## High-Priority Techniques Identified

- **Exploit Public-Facing Application (T1190)**  
  Critical for securing externally exposed systems.

- **Exploitation for Privilege Escalation (T1068)**  
  Prevents attackers from gaining elevated access to sensitive data.

- **Data from Cloud Storage (T1530)**  
  Essential for protecting cloud-hosted financial data.

- **Network Denial of Service (T1498)**  
  Impacts availability of services and customer access.

These techniques directly relate to confidentiality, integrity, and availability of critical assets.

---

# Key Takeaways

- MITRE ATT&CK provides structured insight into adversary behavior.
- Mapping threats to ATT&CK improves visibility into real-world attack patterns.
- ATT&CK Navigator enables visual prioritisation and documentation.
- Industry-specific threat groups enhance targeted risk assessment.
- High-value assets should guide prioritisation of techniques.
- After identifying relevant techniques, the next step is implementing and validating security controls.

MITRE ATT&CK strengthens threat modelling by aligning defensive strategies with documented adversary tactics and techniques.
