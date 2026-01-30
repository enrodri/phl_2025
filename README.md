# PHL 2025: MBI-Driven Clinical Triage Architecture
### Quantifying Clinical Gaps in Valvular Heart Disease (VHD)

This project documents the development of the **Medication Burden Index (MBI)**, a weighted clinical metric designed to predict hemodynamic severity and optimize surgical triage in high-volume medical missions.

## 🚀 The Core Innovation: The MBI
The MBI transforms fragmented medication lists into a single, actionable score that serves as a proxy for structural heart disease severity. By calculating the ratio of **Total Daily Dose (TDD)** against **Maximum Clinical Doses**, the model identifies high-complexity candidates before they reach the echocardiography suite.

### 🧪 Mathematical Framework
$$MBI = \sum \left( \text{Class Weight} \times \frac{\text{Total Daily Dose}}{\text{Maximum Clinical Dose}} \right)$$

---

## 🛠️ Clinical Reference Tables

### 1. Pharmacological Weighting Logic
Each medication class is weighted based on its clinical significance regarding heart failure management and hemodynamic distress.

| Weight | Priority | Medication Classes | Clinical Significance |
|:---|:---|:---|:---|
| **3.0** | Critical | Loop Diuretics, Pulmonary Vasodilators | Signifies active heart failure or critical PH. |
| **2.0** | High | RAASi, SGLT2i, Beta-Blockers | Indicates chronic HF or significant remodeling. |
| **1.0** | Moderate | Anticoagulants, CCBs, Rate Control | Addresses secondary risks like AFib. |
| **0.5** | Maintenance | Lipid-Lowering, Metabolic | General health; lower immediate surgical impact. |

### 2. Operational Triage Zones
Based on the cohort analysis ($N=152$), these thresholds guide the intake staff in prioritizing patients.

| MBI Range | Triage Zone | Clinical Interpretation |
|:---|:---|:---|
| **< 2.27** | Standard | Near cohort average. Likely compensated. |
| **4.0 - 5.25** | **Zone 2: Sweet Spot** | High likelihood of complex mixed-lesion phenotypes. |
| **5.25 - 5.5** | **Zone 3: Critical** | **85% Precision** for Critical PH ($RVSP > 60 mmHg$). |
| **> 5.5** | Zone 4: Palliative | Pharmacological exhaustion; risk of surgical futility. |

---

## 🔬 Data Integrity & Methodology
### Solving the "Silence of the Normal" (MNAR Bias)
In clinical "sprints," normal findings are often left blank (Missing Not At Random). To prevent **Model Alarmism**, this project implements **Natural Normal Imputation**:
* **Strategy:** Restoring the physiological distribution using Gaussian noise centered at healthy means (e.g., $sPAP = 25 \pm 5 mmHg$).
* **Result:** 98% data completeness achieved on triage-critical variables.

### Key Clinical Findings
* **Top Pathologies:** Mitral Stenosis (32.2%) and Aortic Stenosis (22.4%).
* **Predictive Power:** The MBI achieves an **AUC of 0.82** for anatomical complexity.
* **Hemodynamic Correlation:** MBI scores effectively map the "Complexity Floor" where surgical benefit is maximized.

---
**Author:** Enyel A. Rodríguez G.  
**Project:** Quantifying Clinical Gaps in Valvular Heart Disease: Using the Medication Burden Index (MBI) to Triage High-Complexity Surgical Candidates.
**Context:** Project Health for Leon | León, Nicaragua 2025