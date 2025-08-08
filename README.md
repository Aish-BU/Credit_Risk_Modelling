# Credit Risk Modeling | Calculation of PD, LGD, EAD, and EL with Machine Learning in Python

---

## Background

Credit risk modeling is a critical function for financial institutions, representing the risk that borrowers may fail to repay loans, credit cards, or other credit facilities. In many cases, borrowers may only partially repay the principal and interest amounts, increasing the lender’s exposure to loss. Both traditional statistical methods and modern machine learning techniques play a vital role in managing large datasets and developing accurate predictive models.

This project harnesses advanced data science and machine learning to build comprehensive credit risk models in line with Basel II regulatory requirements, aiming to provide robust risk quantification and actionable scorecards for daily credit decisioning.

---

## Project Overview

The objective of this project is to develop an end-to-end AI-powered credit risk modeling pipeline using Lending Club loan data. The goal is twofold: (1) to generate a practical scorecard for loan approval and risk-based pricing, and (2) to establish a pipeline for calculating exposure loss through integrated risk components.

The process follows a structured, stepwise approach consistent with Basel II standards:

1. **Preprocessing and Feature Engineering:** Convert raw loan data into suitable formats, including fine and coarse classing to create dummy variables.
2. **Probability of Default (PD) Modeling:** Develop logistic regression models to estimate the likelihood of borrower default.
3. **Scorecard Generation:** Translate the PD model into a user-friendly scorecard CSV for practical credit risk evaluation.
4. **Loss Given Default (LGD) Modeling:** Use beta regression to estimate the proportion of loss if default occurs.
5. **Exposure at Default (EAD) Modeling:** Apply linear regression to forecast exposure at the time of default.
6. **Expected Loss (EL) Calculation:** Integrate PD, LGD, and EAD to quantify expected loss and overall credit risk exposure.
7. **Model Validation and Monitoring:** Assess model stability and performance over time using population stability indices and new data from 2015.

This notebook series includes revisions and additions from the credit risk course on 365 Learning, enhancing the practical and theoretical framework of credit risk analytics.

---

## Key Documents (Notebooks)

* **L01:** Data preprocessing and feature engineering — transforming raw data into model-ready input.
* **L02:** Probability of Default modeling — logistic regression, scorecard creation, and cutoff determination.
* **L03:** Loss Given Default, Exposure at Default, and Expected Loss modeling — applying beta and linear regression techniques.
* **L04:** Model validation — assessing population stability index and model performance with updated data.

---

## Dataset

The dataset, sourced from Lending Club and available on Kaggle, contains over 800,000 consumer loans issued in the US between 2007 and 2015. For modeling, data is split into two periods: 2007-2014 for model training and 2015 for validation and monitoring. This approach simulates real-world deployment and regulatory compliance checks.

---

## Model Performances

| Model                       | Technique           | Key Metrics                 |
| --------------------------- | ------------------- | --------------------------- |
| Probability of Default (PD) | Logistic Regression | Accuracy: 0.572, AUC: 0.684 |
| Loss Given Default (LGD)    | Beta Regression     | Accuracy: 0.595, AUC: 0.640 |
| LGD Stage 2                 | Linear Regression   | Accuracy: 0.777             |
| Exposure at Default (EAD)   | Linear Regression   | Accuracy: 0.658             |

Further improvements and enhancements are possible through feature engineering, ensemble modeling, and hyperparameter tuning.

---

## Deliverables

* An interpretable scorecard compliant with regulatory standards.
* A dataframe to analyze cutoff impacts on borrower acceptance rates.
* Robust LGD, EAD, and EL models.
* A pipeline to monitor model stability through population stability index metrics.

---

## Technologies

* Python 3.8
* Jupyter Notebook 6.4.12
* Key Python libraries (detailed in `requirements.txt`)
* VSCode 1.71.2
* Google Colab-ready for easy cloud execution without local setup.

---

## Getting Started

Clone the repository and install dependencies:

```bash
git clone https://github.com/Aish-BU/Credit_Risk_Modelling.git
cd Credit_Risk_Modelling
pip3 install -r requirements.txt
```

---

## Project Directory Layout

```
.
├── Notebooks               # Jupyter notebooks for each project phase  
├── src                     # Scripts containing reusable functions
├── data                    # Datasets (some stored on Google Drive)    
├── LICENSE
├── README.md 
└── requirements.txt
```

---

## Business Impact

As a passionate risk analytics practitioner, I find this project immensely rewarding as it blends statistical rigor with machine learning to solve real-world financial challenges. By delivering scalable, interpretable credit risk models aligned with regulatory frameworks, this work empowers banks to make data-driven lending decisions that optimize profitability while managing risk effectively. The project’s comprehensive pipeline supports dynamic model monitoring, ensuring sustained model performance and regulatory compliance — critical in today’s evolving financial landscape.



## 📊 Results Summary

This project implements an end-to-end credit risk modeling pipeline using Lending Club loan data. The solution includes:

* **Probability of Default (PD)**
* **Loss Given Default (LGD)**
* **Exposure at Default (EAD)**
* **Expected Loss (EL)**
* **Model Monitoring (Population Stability Index, PSI)**

### Key Findings

* **Dataset:**

  > Over 800,000 loans from 2007–2014 (training), validated on 2015 data.

* **Probability of Default (PD):**

  > PD model based on logistic regression provided strong separation between good and bad loans.

* **Loss Given Default (LGD):**

  * **Average Recovery Rate:** \~6%
  * **Mean LGD:** 94%
  * *Most defaults resulted in near-total loss after recoveries.*
  * **Top predictors:** Loan grade and verification status.

* **Exposure at Default (EAD):**

  * **Mean EAD:** \$10,799
  * *Most defaults occurred before major principal repayment.*

* **Expected Loss (EL):**

  * **Mean EL per loan:** \$1,090
  * **Portfolio EL rate:** 7.6% (expected loss per \$1 lent)
  * **Total expected loss:** \$508 million (vs. \$6.66 billion funded)

* **Model Monitoring (PSI):**

  * **Overall PSI:** 0.85 (*significant drift*)
  * **Features with notable change:**

    * `initial_list_status` (PSI = 0.33) — Significant shift
    * `Score` (PSI = 0.14) — Moderate shift
  * **Action:** Model retraining/recalibration is recommended for continued accuracy.

---

### 📌 Business Implications

* **High loss severity and exposure at default** require careful risk pricing and capital allocation.
* **Borrower profiles have changed over time**—regular monitoring and model updates are essential.
* **Expected loss rate (7.6%)** provides a data-driven basis for credit policy and capital planning.

---

**For best results, retrain and monitor the models regularly as new data becomes available.**

---
