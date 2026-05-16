# Predicting Crime Severity in Boston: A Spatiotemporal Machine Learning Approach

This repository contains the data analysis, predictive modeling, and the complete scientific paper focused on predicting crime severity in Boston using spatial and temporal features. 

The primary challenge addressed in this study is severe **class imbalance** and its impact on tree-based machine learning models.

[Read the Full Scientific Paper](docs/Predicting_Crime_Severity_Fairly.pdf)

---

## Project Overview
Using data spanning from 2015 to 2025, this project evaluates the performance of Random Forest and Decision Tree classifiers in predicting crime severity level based on where (district) and when (season, hour, day of the week) a crime occurred. 

### Key Features Explored:
*   **Spatial:** District, Reporting Area.
*   **Temporal:** Year, Month, Day of the Week, Hour, Season.
*   **Engineered:** Interaction terms (e.g., `season × hour`, `day × district`).

---

## Methodology & Experiments
To mitigate the severe majority-class dominance in the dataset, 5 distinct experimental setups were engineered and tested:

1.  **Baseline Random Forest:** Imbalanced data.
2.  **Class-Weighted Random Forest:** Penalizing majority class misclassifications.
3.  **Binary Modeling:** Isolating minority classes to test separability.
4.  **Undersampling:** Equalizing distributions by reducing the majority class.
5.  **Oversampling (SMOTE):** Generating synthetic instances of minority classes.

---

## 📊 Key Results

The experiments demonstrated that simply balancing class distributions (via SMOTE or Undersampling) was insufficient, highlighting that predictive limitations are driven more by **feature quality and information density** than imbalance alone. Class-weighted models offered the best compromise between fairness (macro metrics) and overall accuracy.

### Performance Summary:
| Model Setup | Accuracy | F1 Macro | Precision Macro | Recall Macro |
| :--- | :---: | :---: | :---: | :---: |
| **Exp 1: Baseline RF** | 49.71% | 23.45% | 40.41% | 33.62% |
| **Exp 2: Class-Weighted RF** | 40.47% | 38.81% | 39.20% | 39.85% |
| **Exp 3: Binary Model** | 58.17% | 56.40% | 56.37% | 56.50% |
| **Exp 4: Undersampling** | 39.50% | 39.49% | 39.68% | 39.52% |
| **Exp 5: SMOTE** | 41.11% | 41.14% | 41.25% | 41.11% |

*Note: Models trained on 2015–2018 data generalized well when tested against the recent 2023–2025 dataset, proving strong temporal stability in spatiotemporal crime patterns.*

---

## Repository Structure

```text
├── notebooks/          # Jupyter Notebook containing EDA and Model training
├── docs/               # Full scientific paper in PDF format
└── README.md           # Project summary and key insights

```

---

## Tech Stack
- **Language:** Python

- **Libraries:** scikit-learn, pandas, numpy, matplotlib

- **Concepts:** Supervised Learning, Class Imbalance, Spatiotemporal Analysis, Feature Engineering

For a detailed breakdown of the mathematical background, feature engineering steps, and future work proposals, please check the complete paper.
