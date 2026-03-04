# TryHackMe – Risk Assessment & Risk Management Process | Notes & Key Concepts Learned

## Risk Assessment Frameworks

Several methodologies exist for conducting risk assessments:

### NIST SP 800-30
A methodology developed by NIST that involves:
- Identifying risks
- Evaluating likelihood and impact
- Developing a risk response plan

### Facilitated Risk Analysis Process (FRAP)
A collaborative risk assessment method where stakeholders:
- Work together
- Identify risks
- Evaluate and prioritise risks

### Operationally Critical Threat, Asset, and Vulnerability Evaluation (OCTAVE)
Focuses on:
- Identifying critical assets
- Assessing threats and vulnerabilities
- Prioritising based on mission impact

### Failure Modes and Effects Analysis (FMEA)
Common in engineering and manufacturing:
- Identifies potential failure modes
- Analyses their effects
- Assesses likelihood of occurrence

---

# NIST SP 800-30 Risk Management Process

The risk management lifecycle consists of four steps:

1. Frame Risk  
2. Assess Risk  
3. Respond to Risk  
4. Monitor Risk  

---

# Frame Risk

Framing risk establishes the context and defines the risk management strategy.

Key elements of a risk frame:

### Risk Assumptions
- Assumptions about threats and vulnerabilities
- Likelihood of occurrence
- Expected impact and consequences

### Risk Constraints
- Budget limitations
- Resource availability
- Operational limitations

### Risk Tolerance
- Acceptable level of risk
- Degree of uncertainty the organisation can tolerate

### Priorities and Trade-offs
- High-priority business functions
- Trade-offs between different risks

Framing risk sets the foundation for all subsequent risk activities.

---

# Assess Risk

Risk assessment determines:

- Threats
- Vulnerabilities
- Impact
- Likelihood

### Example 1 – Natural Threat

Threat: Tsunami  
Vulnerability: Office located near the seashore  
Impact: Destruction of office equipment  
Likelihood: Negligible  

### Example 2 – Ransomware

Threat: Ransomware groups  
Vulnerability: Data stored on computer systems  
Impact: Business disruption  
Likelihood: High  

Risk assessment evaluates how likely a threat is and how severe the consequences would be.

---

# Respond to Risk

Four primary responses:

### Avoid Risk
Eliminate the activity causing the risk.

Example:
- Blocking Internet access on employee machines.

---

### Transfer Risk
Shift risk to another entity.

Example:
- Purchasing insurance against fire.

---

### Mitigate Risk
Implement controls to reduce likelihood or impact.

Example:
- Installing antivirus software.

---

### Accept Risk
Choose not to implement controls after analysis.

Important:
Accepting risk does not mean ignoring it. It means the cost of mitigation outweighs the potential loss or significantly alters business operations.

---

# Quantitative Risk Analysis

Quantitative analysis determines whether a safeguard is financially justified.

Key formulas:

### Single Loss Expectancy (SLE)
SLE = Asset Value × Exposure Factor (EF)

### Annualised Rate of Occurrence (ARO)
Frequency of the threat per year.

### Annualised Loss Expectancy (ALE)
ALE = SLE × ARO

### Value of Safeguard
Value of Safeguard = ALE_before − ALE_after − Annual Cost of Safeguard

If the result is positive, the safeguard is justified.

Example:
Installing antivirus reduces ARO significantly.  
If Value of Safeguard > 0 → Implementation is justified.

---

# Monitor Risk

Risk management is continuous.

Monitoring ensures:

- Identification of new risks
- Elimination of irrelevant risks
- Evaluation of existing controls

Monitoring focuses on:

### Effectiveness
Controls must remain effective over time.

Example:
Password complexity rules become ineffective if users write passwords on sticky notes.

---

### Change
Changes in:
- Business operations
- Information systems

New systems or expansions may introduce new risks.

---

### Compliance
Monitoring for:
- New laws
- Regulatory requirements
- Policy changes
- Audit findings

Failure to address compliance issues may lead to fines or legal consequences.

---

# Key Concepts Reinforced

- Risk management follows Frame → Assess → Respond → Monitor.
- Risk framing defines assumptions, constraints, tolerance, and priorities.
- Risk assessment evaluates threats, vulnerabilities, impact, and likelihood.
- Risk response includes avoidance, transfer, mitigation, and acceptance.
- Quantitative analysis supports business-driven security decisions.
- Continuous monitoring ensures long-term effectiveness and adaptability.
