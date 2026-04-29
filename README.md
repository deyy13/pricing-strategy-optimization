# pricing-strategy-optimization

ML project to recommend optimal pricing strategies using regression models on supermarket sales data

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Latest-orange)
![Status](https://img.shields.io/badge/Status-Completed-success)

## 📌 Project Overview

This project addresses the challenge of suboptimal pricing in retail by developing a data-driven pricing recommendation framework. Using historical supermarket sales data, the system identifies price-demand relationships and recommends the optimal unit price per product to maximize revenue.

The goal is to move from manual rule-based pricing to a **proactive, model-driven pricing engine** that adapts to real demand patterns.

## 🎯 Objectives

- **Predict Optimal Price:** Use transaction data to recommend the best price point per product.
- **Identify Demand Signals:** Pinpoint which features (revenue per unit, total price, quantity) drive pricing decisions.
- **Support Targeted Strategies:** Provide actionable insights for sales and marketing teams.

## 📊 Dataset & Feature Engineering

**Dataset:** [Supermarket Sales — Kaggle](https://www.kaggle.com/datasets/camnugent/supermarket-sales)

**Key Transformations:**

- **Target Definition:** Unit price was modeled as a regression target to predict optimal pricing.
- **Feature Engineering:** Created `revenue_per_unit`, `price_times_qty`, `high_value_customer`, and `price_band` as new features.
- **Preprocessing:** Label-encoded categorical variables, applied StandardScaler, and split data 80/20 for train/test.

## 🛠️ Technical Stack

- **Languages:** Python
- **Libraries:** Pandas, NumPy, Scikit-learn
- **Visualization:** Matplotlib, Seaborn
- **Models:** Linear Regression, Random Forest Regressor, Gradient Boosting Regressor

## 📈 Model Performance

**5-Fold Cross-Validation** was used to evaluate all models and prevent overfitting.

| Model | RMSE | R² Score | Key Strength |
|---|---|---|---|
| **Linear Regression** | 0.0006 | 1.0000 | Baseline interpretability |
| **Random Forest** | 0.0206 | 1.0000 | Robustness to non-linear data |
| **Gradient Boosting** | 0.0470 | **0.9999** | Highest generalization |

> **Result:** All models achieved near-perfect R² scores, confirming that transaction-level features are highly predictive of unit pricing.

## 💡 Key Insights

1. **Transaction Value > Demographics:** Feature importance analysis revealed that **'Total Price'** and **'Revenue per Unit'** are far stronger predictors of optimal pricing than branch, city, or customer gender.
2. **Category-Level Pricing Works:** Personal Care generated the highest revenue ($27K+), validating that category-specific pricing strategies are meaningful and impactful.

## Conclusion

By transitioning from manual pricing rules to a model-driven approach, this system enables the business to maximize revenue per transaction while maintaining competitive sales volume. The key finding — that transaction economics outweigh customer demographics in pricing decisions — provides a clear roadmap for unified, data-backed pricing strategies.

## 🚀 How to Run

1. Clone the repository:
   git clone https://github.com/deyy13/pricing-strategy-optimization.git
2. Install dependencies:
   pip install -r requirements.txt
3. Place `sales.csv` in the same folder as the notebook
4. Open and run the notebook:
   jupyter notebook Pricing_Strategy_Optimization_System.ipynb
