

```markdown
# 🩺 Diabetes Readmission Risk Analysis

**Author:** _Clara Yousif_  
**Date:** October 2025  
**Note:** Educational project created as part of Clara’s _AI in Healthcare Self-Study Program_.

---

## 📘 Project Overview

Hospital readmissions within 30 days of discharge are a critical metric in healthcare — both medically and economically.  
This project analyzes over **100,000 diabetic patient encounters** from **130 U.S. hospitals (1999–2008)** to predict **30-day readmission risk** and identify the clinical factors that contribute most.

---

## 📂 Dataset

**Source:** [Kaggle – Diabetes 130-US hospitals for years 1999–2008](https://www.kaggle.com/datasets/brandao/diabetes)  
**Paper:** _Impact of HbA1c Measurement on Hospital Readmission Rates: Analysis of 70,000 Clinical Database Patient Records_

**Key Facts**

- 101,766 encounters, 50 attributes
- Features include demographics, diagnoses, lab results, medications, and utilization patterns
- Target variable: `readmitted` (`<30` = 1, otherwise 0)
```

data/
├─ diabetic_data.csv
└─ description.pdf

````

---

## ⚙️ Tech Stack

| Category   | Tools                                      |
|------------|--------------------------------------------|
| Language   | Python 3.10                                |
| Libraries  | pandas, NumPy, matplotlib, seaborn, scikit-learn |
| ML Models  | Logistic Regression, Random Forest, Calibrated Logistic (Isotonic) |
| Workflow   | Jupyter Notebook + GitHub                  |
| Environment| Conda / Anaconda                           |

---

## 🚀 How to Run

```bash
git clone https://github.com/claraashraf24/diabetes-readmission.git
cd diabetes-readmission
pip install -r requirements.txt
jupyter notebook notebooks/01_eda_and_model.ipynb
````

---



## 🔑 Top Predictors

| Rank | Feature             | Insight                                                      |
| ---- | ------------------- | ------------------------------------------------------------ |
| 1    | number_inpatient    | Frequent inpatient visits strongly increase readmission risk |
| 2    | diag_1              | Primary diagnosis code impacts risk (ICD category)           |
| 3    | num_procedures      | More procedures → higher chance of readmission               |
| 4    | number_emergency    | Frequent emergency visits correlate with risk                |
| 5    | admission_source_id | Admission type matters (emergency vs referral)               |
| 6    | diabetesMed, change | Medication use & change patterns are predictive              |

---

## 📈 Visualization Highlights

- Feature Importance (Logistic Regression)
- Calibration Curve

> Plots above are generated automatically from the notebook when executed.

---



**Conclusion:**  
Model exhibits generally fair performance across demographics; small groups require larger samples for robust validation.

---

## 🧭 Key Insights

- Readmission risk correlates with prior utilization (inpatient/emergency counts).
- HbA1c measurement and diabetes medication management contribute to outcome prediction.
- Model calibration ensures predicted probabilities align with observed frequencies.
- Fairness analysis indicates no systemic bias across gender, race, or age.

---

## 🧩 Next Steps

- **Feature Engineering:** Aggregate ICD codes, flag chronic conditions, derive HbA1c control variable.
- **Temporal Validation:** Train on early years → test on later years to simulate deployment.
- **Deployment:** Wrap calibrated model in a FastAPI microservice and expose a `/predict` endpoint.
- **Monitoring:** Track calibration drift and subgroup performance over time.
- **Ethical Review:** Maintain transparency, document limitations, and evaluate clinical suitability.

---

## 🧠 Learning Outcomes

This project demonstrates:

- End-to-end healthcare ML workflow
- Handling high-cardinality categorical data
- Model interpretability via permutation importance
- Calibration and fairness in medical prediction systems
- Responsible AI communication through documentation

---

## 🏁 Repository Structure

```
diabetes-readmission/
├─ data/
│  ├─ diabetic_data.csv
│  └─ description.pdf
├─ notebooks/
│  └─ 01_eda_and_model.ipynb
├─ src/
│  └─ utils.py
├─ requirements.txt
└─ README.md
```

---

## 📚 References

- Strack et al., _Impact of HbA1c Measurement on Hospital Readmission Rates: Analysis of 70,000 Clinical Database Patient Records_, Diabetes Care, 2014.
- [Kaggle Dataset Link](https://www.kaggle.com/datasets/brandao/diabetes)

