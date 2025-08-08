# Credit Risk Modeling | Calculation of PD, LGD, EAD, and EL with Machine Learning in Python

---

## 📚 Background

Credit risk modeling is a critical function for financial institutions, representing the risk that borrowers may fail to repay loans, credit cards, or other credit facilities. In many cases, borrowers may only partially repay the principal and interest amounts, increasing the lender’s exposure to loss. Both traditional statistical methods and modern machine learning techniques play a vital role in managing large datasets and developing accurate predictive models.

This project harnesses advanced data science and machine learning to build comprehensive credit risk models in line with Basel II regulatory requirements, aiming to provide robust risk quantification and actionable scorecards for daily credit decisioning.

---

## 🚀 Project Overview

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

## 🗂️ Key Notebooks

* **L01:** Data preprocessing and feature engineering — transforming raw data into model-ready input.
* **L02:** Probability of Default modeling — logistic regression, scorecard creation, and cutoff determination.
* **L03:** Loss Given Default, Exposure at Default, and Expected Loss modeling — applying beta and linear regression techniques.
* **L04:** Model validation — assessing population stability index and model performance with updated data.

---

## 📊 Dataset

The dataset, sourced from Lending Club and available on Kaggle, contains over 800,000 consumer loans issued in the US between 2007 and 2015. For modeling, data is split into two periods: 2007-2014 for model training and 2015 for validation and monitoring. This approach simulates real-world deployment and regulatory compliance checks.

---

## ⚙️ Model Performances

| Model                       | Technique           | Key Metrics                 |
| --------------------------- | ------------------- | --------------------------- |
| Probability of Default (PD) | Logistic Regression | Accuracy: 0.572, AUC: 0.684 |
| Loss Given Default (LGD)    | Beta Regression     | Accuracy: 0.595, AUC: 0.640 |
| LGD Stage 2                 | Linear Regression   | Accuracy: 0.777             |
| Exposure at Default (EAD)   | Linear Regression   | Accuracy: 0.658             |

Further improvements are possible via feature engineering, ensemble modeling, and hyperparameter tuning.

---

## 📦 Project Directory Layout

```
Aish-BU/
│
├── L01_LoanData_CreditRisk_Preprocessing_PD.html           # Data preprocessing & feature engineering
├── L02_LoanData_CreditRisk_PD_Scorecard_Cutoffs.html       # PD modeling, scorecard, cutoffs
├── L03_LoanData_CreditRisk_LGD,_EAD_and_Expected_Loss.html # LGD, EAD, Expected Loss modeling
├── L04_LoanData_CreditRisk_PSI_check.html                  # Model stability (PSI) check
│
├── functions.py       # Custom Python functions
├── requirements.txt   # Python dependencies
├── README.md          # Project overview and instructions
└── (Add datasets/outputs as needed)
```

---

## 🚦 How to Use This Project

1. **Clone the Repository**

   ```bash
   git clone https://github.com/yourusername/Aish-BU.git
   cd Aish-BU
   ```

2. **Install Dependencies**

   * Recommended: use a virtual environment.

   ```bash
   pip install -r requirements.txt
   ```

3. **Run the Notebooks**

   * Open the `.html` notebooks in your browser for a read-only view, **or**
   * Run `.ipynb` notebooks (if available) in Jupyter Notebook or Google Colab.

4. **Custom Functions**

   * Import and use `functions.py` for data preprocessing/model utilities.

5. **Explore Each Notebook**

   * **L01:** Data cleaning & feature engineering
   * **L02:** PD modeling and scorecard
   * **L03:** LGD, EAD, EL calculations
   * **L04:** Model monitoring (PSI)

---

## 🏦 Business Impact

By combining statistical rigor with machine learning, this project delivers scalable and interpretable credit risk models aligned with regulatory frameworks. Banks and lenders can leverage these models to:

* **Make data-driven lending decisions**
* **Optimize profitability**
* **Manage and monitor risk exposure**
* **Stay compliant with Basel II and regulatory requirements**

The pipeline supports dynamic model monitoring, ensuring sustained model performance and regulatory compliance in today’s evolving financial landscape.

---

## 📊 Results Summary

**End-to-end credit risk modeling using Lending Club loan data:**
Includes PD, LGD, EAD, EL, and model monitoring (PSI).

### Key Findings

* **Dataset:**
  Over 800,000 loans from 2007–2014 (training), validated on 2015 data.
* **PD Model:**
  Logistic regression provided strong separation between good and bad loans.
* **LGD:**

  * **Avg. Recovery Rate:** \~6%
  * **Mean LGD:** 94%
  * *Most defaults resulted in near-total loss after recoveries.*
  * **Top predictors:** Loan grade, verification status
* **EAD:**

  * **Mean EAD:** \$10,799
  * *Most defaults occurred before major principal repayment.*
* **EL:**

  * **Mean EL per loan:** \$1,090
  * **Portfolio EL rate:** 7.6% (expected loss per \$1 lent)
  * **Total expected loss:** \$508 million (vs. \$6.66 billion funded)
* **Model Monitoring (PSI):**

  * **Overall PSI:** 0.85 (*significant drift*)
  * **Notable feature changes:**

    * `initial_list_status` (PSI = 0.33) — Significant shift
    * `Score` (PSI = 0.14) — Moderate shift
  * **Action:** Retrain/recalibrate models for continued accuracy

---

### 📌 Business Implications

* **High loss severity and exposure at default** require careful risk pricing and capital allocation.
* **Borrower profiles have changed over time**—regular monitoring and model updates are essential.
* **Expected loss rate (7.6%)** provides a robust, data-driven foundation for credit policy and capital planning.

---

**For best results, retrain and monitor the models regularly as new data becomes available.**

