# Vehicle Insurance Cross-Sell Prediction

## Project Overview
An insurance company offering health insurance wants to cross-sell vehicle insurance to existing customers.  
This project builds a machine learning model to identify customers likely to buy vehicle insurance, enabling targeted marketing & improved conversions.

## Business Objective
Predict which health insurance customers will be interested in purchasing vehicle insurance.

## Dataset
- Source: Insurance customer dataset
- Rows: 381109
- Target variable: `Response` (1 = Interested, 0 = Not Interested)

## Approach
1. Exploratory Data Analysis (EDA)
2. Feature Engineering
3. Handling class imbalance using **SMOTE**
4. Model building using **XGBoost**
5. Model evaluation using:
   - Accuracy
   - Precision, Recall, F1-Score
   - ROC-AUC

## 🛠 Tech Stack
| Category | Tools |
|---|---|
Programming | Python |
ML Libraries | Scikit-Learn, XGBoost, imbalanced-learn |
Data | Pandas, NumPy |
Visualization | Seaborn, Matplotlib |
Environment | Jupyter / Google Colab |

## ✅ Key Features
- Business-driven ML use case (cross-sell)
- Class imbalance handling (real-world scenario)
- Feature importance & model insights

## 📈 Results :
| Metric | Random Forest | XG Boost |
|---|---|---|
Accuracy	| 82.37%	| 78.06% |
Precision (Class 1)	| 0.32	| 0.32 |
Recall (Class 1)	| 0.40	| 0.71 |
F1-score (Class 1)	| 0.36	| 0.44 |
Precision (Class 0)	| 0.91	| 0.95 |
Recall (Class 0)	| 0.88	| 0.79 |
F1-score (Class 0)	|0.90	| 0.86 |
AUC	| 0.75	| 0.85 |

**Random Forest**
- Performs better in overall accuracy.
- Strong at classifying the majority class (0).
- Weaker recall for minority class (1), which may be critical depending on business priority.

**XGBoost**
- Higher recall for class 1 (71%) — this means it identifies more people who are actually interested in the insurance offer.
- Slightly overfits (training accuracy 86%, test 78%) but gives better attention to the under represented class.
- Recommendation: Considering the business goal is to maximize conversions (i.e., catch as many interested customers as possible), and max AUC, we will select XGBoost due to its higher recall on class 1.
