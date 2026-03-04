# TryHackMe – Qualitative vs Quantitative Risk Analysis | Notes & Key Concepts Learned

## Risk Analysis Approaches

There are two main approaches to risk analysis:

1. Qualitative Risk Analysis  
2. Quantitative Risk Analysis  

---

# Qualitative Risk Analysis

Qualitative risk analysis assigns descriptive ratings to risks instead of numerical values.

### It evaluates:

- Probability of a threat exploiting a vulnerability
- Impact of the risk if realised

Probability and impact are typically expressed as:
- High, Medium, Low  
- Red, Yellow, Green  

Risk levels are determined by combining probability and impact.

- Low probability + Low impact → Low risk  
- High probability + High impact → High risk  

Resource allocation depends on the assigned risk level.  
Higher risks receive greater attention and mitigation efforts.

---

# Quantitative Risk Analysis

Quantitative risk analysis assigns monetary values and numerical percentages to evaluate risk.

It is used to support financial decision-making.

---

## Single Loss Expectancy (SLE)

Formula:

SLE = Asset Value × Exposure Factor (EF)

Where:

- **Asset Value** = Monetary value of the asset  
- **Exposure Factor (EF)** = Percentage of loss caused by the threat  
- **SLE** = Financial loss from a single occurrence of the threat  

### Example:

Asset Value = $10,000  
EF = 90%  

SLE = $10,000 × 90% = $9,000  

This means a single ransomware incident would result in a $9,000 loss.

---

## Annualised Loss Expectancy (ALE)

Formula:

ALE = SLE × Annualised Rate of Occurrence (ARO)

Where:

- **ARO** = Expected frequency of the threat per year  
- **ALE** = Expected yearly financial loss  

### Example:

SLE = $9,000  
ARO = 0.5 (once every two years)  

ALE = $9,000 × 0.5 = $4,500  

This means the expected annual loss per laptop is $4,500.

---

# Purpose of ALE

ALE helps determine whether implementing a safeguard is financially justified.

If the cost of a control is lower than the expected annual loss, the control may be justified from a business perspective.

---

# Key Concepts Reinforced

- Qualitative analysis uses descriptive ratings (high/medium/low).
- Quantitative analysis uses financial values and formulas.
- SLE measures loss from a single incident.
- ALE measures expected annual loss.
- Quantitative analysis supports business-driven security decisions.
