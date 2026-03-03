# TryHackMe – PASTA Framework | Notes & Key Concepts Learned

## Overview

PASTA (Process for Attack Simulation and Threat Analysis) is a structured, risk-centric threat modelling framework designed to identify, analyse, and prioritise security risks in systems, applications, and infrastructure.

Created by Tony UcedaVélez and Marco Morana (2015), PASTA focuses on aligning security analysis with business objectives and risk management. It uses a seven-step methodology to simulate attack scenarios and evaluate their impact.

The core principle of PASTA is that threat modelling should be driven by risk, not just technical vulnerabilities.

---

# Seven-Step Methodology

## 1. Define the Objectives

- Establish the scope of the threat modelling exercise.
- Identify systems, applications, and networks involved.
- Define security objectives.
- Identify compliance and regulatory requirements.

Focus: Align security goals with business requirements.

---

## 2. Define the Technical Scope

- Create an inventory of assets (hardware, software, data).
- Understand system architecture and dependencies.
- Map data flows and system integrations.

Focus: Gain a complete technical understanding of the environment.

---

## 3. Decompose the Application

- Break the system into components and modules.
- Identify:
  - Entry points
  - Trust boundaries
  - Attack surfaces
  - User roles and privilege levels
  - Data flows

Focus: Identify where and how attacks can occur.

---

## 4. Analyse the Threats

- Identify possible threat actors:
  - External attackers
  - Insider threats
  - Accidental exposures
- Use threat intelligence and attack frameworks.
- Consider industry-specific threats.

Focus: Understand who might attack and why.

---

## 5. Vulnerabilities and Weaknesses Analysis

- Identify weaknesses such as:
  - Misconfigurations
  - Software bugs
  - Unpatched systems
- Use:
  - Static code analysis
  - Dynamic analysis
  - Vulnerability scanning
  - Penetration testing

Focus: Identify technical gaps attackers could exploit.

---

## 6. Analyse the Attacks

- Simulate realistic attack scenarios.
- Use techniques such as Attack Trees.
- Evaluate:
  - Likelihood of success
  - Potential impact

Focus: Understand how threats could realistically unfold.

---

## 7. Risk and Impact Analysis

- Assess overall risk based on:
  - Likelihood
  - Impact
- Prioritise threats.
- Implement countermeasures aligned with risk tolerance.

Focus: Make informed, risk-based remediation decisions.

---

# Practical Guidelines

To effectively apply PASTA:

- Define clear, measurable objectives.
- Ensure complete asset identification.
- Document trust boundaries and attack surfaces.
- Use updated threat intelligence.
- Combine automated tools with manual testing.
- Simulate real-world attack scenarios.
- Prioritise based on business impact.
- Continuously update the model as systems evolve.

PASTA should be tailored to the organisation’s specific environment.

---

# Benefits of the PASTA Framework

- Risk-centric and business-aligned.
- Comprehensive seven-step structure.
- Encourages cross-team collaboration.
- Supports regulatory and compliance requirements.
- Enables proactive risk identification.
- Improves communication between technical and business teams.

The framework ensures a structured and thorough analysis of the entire threat landscape.

---

# Example Application Scenario

Scenario: Online Banking Platform (Asia Pacific Region)

Critical Assets:
- Customer financial data
- Transaction records
- Account credentials
- Personal Identifiable Information (PII)

Teams Involved:
- Development Team
- System Architecture Team
- Security Team
- Business Stakeholders

Using PASTA in this scenario involves:

- Defining objectives aligned with financial regulations.
- Mapping cloud architecture and data flows.
- Identifying trust boundaries between users and banking systems.
- Analysing threats such as credential theft, API abuse, and insider threats.
- Identifying vulnerabilities in authentication, APIs, and infrastructure.
- Simulating attack paths targeting transaction systems.
- Prioritising high-impact risks affecting financial data.

---

# Key Concepts Reinforced

- PASTA is a risk-driven threat modelling framework.
- Threat modelling must align with business and compliance objectives.
- Attack simulation improves understanding of real-world impact.
- Risk prioritisation drives remediation decisions.
- Collaboration across teams strengthens overall security posture.
- Threat modelling is iterative and evolves with the system.

PASTA provides a comprehensive, structured approach to understanding and mitigating security risks across complex environments.
