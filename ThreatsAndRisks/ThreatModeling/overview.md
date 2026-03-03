# TryHackMe – Threat Modelling | Notes & Key Concepts Learned

## Overview

Threat modelling is a structured and systematic approach to identifying, analysing, and reducing security risks within an organisation. Its purpose is to proactively identify weaknesses before attackers exploit them and to reduce overall risk exposure.

Threat modelling focuses on understanding how threats, vulnerabilities, and risks interact within systems, applications, and infrastructure.

---

## Threat, Vulnerability, and Risk

Clear distinction between the three core concepts:

**Threat**  
A potential event, actor, or action that could cause harm (e.g., cyber attacks, insider threats, natural disasters).

**Vulnerability**  
A weakness in a system, application, or process that can be exploited (e.g., misconfigurations, software bugs, design flaws).

**Risk**  
The likelihood and impact of a threat exploiting a vulnerability.

Risk can be understood as:

Risk = Likelihood × Impact

Understanding this relationship is essential for prioritising security efforts effectively.

---

## High-Level Threat Modelling Process

A simplified threat modelling process includes:

1. **Define Scope**  
   Identify systems, applications, and networks involved in the exercise.

2. **Asset Identification**  
   Map system architecture and dependencies.  
   Identify critical assets such as customer data, financial information, and intellectual property.

3. **Identify Threats**  
   Consider cyber attacks, insider threats, physical threats, and social engineering.

4. **Analyse Vulnerabilities and Prioritise Risks**  
   Assess weaknesses and evaluate their potential impact.  
   Prioritise risks based on likelihood and severity.

5. **Develop and Implement Countermeasures**  
   Apply security controls such as access management, patching, monitoring, and configuration hardening.

6. **Monitor and Evaluate**  
   Continuously test and assess the effectiveness of implemented controls.  
   Track risk reduction over time.

Threat modelling is a continuous process, not a one-time activity.

---

## Collaboration Across Teams

Threat modelling requires coordination between multiple teams:

- **Security Team** – Leads the process and defines mitigation strategies.
- **Development Team** – Integrates security into the development lifecycle.
- **IT & Operations** – Manages infrastructure and configurations.
- **Governance, Risk & Compliance (GRC)** – Ensures regulatory alignment.
- **Business Stakeholders** – Define critical assets and risk tolerance.
- **End Users** – Provide insights into real-world usage and potential weaknesses.

Security is a shared organisational responsibility.

---

## Attack Trees

Attack trees are graphical models used to analyse potential attack scenarios.

- **Root Node** – Attacker’s primary objective.
- **Branches** – High-level attack strategies.
- **Leaf Nodes** – Specific techniques or vulnerabilities.

They provide a structured way to break down complex attack scenarios into manageable components.

---

## Attack Paths

Attack paths represent chains of interconnected vulnerabilities that an attacker can exploit to achieve a goal.

- Starting point: Initial access or entry vector.
- Intermediate steps: Exploited weaknesses.
- End goal: Compromise of sensitive data or systems.

Understanding attack paths helps identify and eliminate weak links.

## MITRE ATT&CK

MITRE ATT&CK focuses on real-world adversary behaviour by mapping attacker tactics and techniques.  
Unlike DREAD and STRIDE, which concentrate on risk scoring and categorisation, ATT&CK provides a practical and operational perspective based on documented attack patterns.

### Use Cases:
- Assess effectiveness of existing security controls against known attack techniques.
- Map threat actors to organisational infrastructure.
- Identify potential attack paths.
- Improve detection engineering and incident response readiness.
- Strengthen defensive strategies using real adversary data.

Primary Strength: Real-world, adversary-focused analysis.

---

## DREAD

DREAD provides a numerical, qualitative scoring model for evaluating and prioritising risks.  
It offers a structured way to calculate and compare threat severity.

### Use Cases:
- Assess potential risk levels of identified vulnerabilities.
- Prioritise remediation efforts using calculated risk scores.
- Support decision-making with measurable criteria.
- Compare multiple vulnerabilities objectively.

Primary Strength: Risk prioritisation through structured scoring.

---

## STRIDE

STRIDE is a structured threat categorisation framework designed primarily for software systems and application design.  
It systematically reviews threats across six defined categories aligned with core security principles.

### Use Cases:
- Analyse and categorise threats in system components.
- Identify vulnerabilities during system design.
- Guide secure architecture development.
- Map threats to authentication, integrity, confidentiality, availability, and authorisation concerns.

Primary Strength: Systematic threat identification during system design.

---

## PASTA

PASTA is a risk-centric and business-aligned threat modelling framework.  
It integrates technical threat analysis with organisational objectives and compliance requirements.

### Use Cases:
- Conduct comprehensive, risk-driven threat modelling.
- Align security initiatives with business goals.
- Simulate realistic attack scenarios.
- Prioritise threats based on business impact and risk tolerance.
- Develop adaptable methodologies tailored to organisational needs.

Primary Strength: Holistic, business-aligned threat modelling.

---

# Shared Benefits Across All Frameworks

All four frameworks contribute to organisational security by:

- Enhancing threat awareness.
- Identifying vulnerabilities systematically.
- Prioritising mitigation efforts.
- Improving security control implementation.
- Supporting continuous improvement.
- Adapting to evolving threat landscapes.

---

# Overall Comparison Summary

- **MITRE ATT&CK** → Adversary-focused and operational.
- **DREAD** → Risk scoring and prioritisation.
- **STRIDE** → Structured threat categorisation for system design.
- **PASTA** → Business-aligned, risk-centric modelling.

Each framework has distinct strengths and can be used individually or combined to strengthen an organisation’s threat modelling and risk management strategy.

## Key Concepts Reinforced

- Threat modelling is proactive risk management.
- Risk exists when threats exploit vulnerabilities.
- Security decisions must be based on likelihood and impact.
- Continuous monitoring strengthens defence posture.
- Cross-team collaboration improves effectiveness.
- Structured modelling techniques improve visibility into attack surfaces.

Threat modelling strengthens organisational security by aligning technical controls with business objectives and risk tolerance.
