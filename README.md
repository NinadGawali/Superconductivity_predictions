# 🔬 Robust Ensemble Meta-Learning for Superconducting Critical Temperature Prediction

This repository contains the code and methodology for predicting the **critical temperature (Tc)** of superconductors using a **stacked ensemble machine learning model**, combining **XGBoost** and **Gradient Boosting** with a meta-learner for improved generalization and accuracy.

> 🚀 Achieved a state-of-the-art R² score of **0.93** for Tc prediction.

---

## 📌 Table of Contents

- [Overview](#overview)
- [Motivation](#motivation)
- [Dataset](#dataset)
- [Methodology](#methodology)
- [Models Used](#models-used)
- [Results](#results)
- [Key Features](#key-features)
- [Installation](#installation)
- [Usage](#usage)
- [Future Scope](#future-scope)
- [Contributors](#contributors)
- [References](#references)

---

## 🧠 Overview

Superconductors exhibit zero electrical resistance and perfect diamagnetism below a specific critical temperature (Tc). Predicting this Tc is complex due to the non-linear interactions of material properties.

This project proposes a **robust ensemble meta-learning model** to accurately predict Tc by:

- Performing feature engineering on 168 raw features.
- Reducing multicollinearity and dimensionality.
- Applying advanced stacking models for improved predictions.

---

## 💡 Motivation

The traditional trial-and-error approach in superconductor discovery is **costly** and **time-consuming**. Machine Learning accelerates this process by:

- Learning patterns from known materials.
- Predicting properties of new compounds.
- Reducing experimental costs and time.

---

## 🗃️ Dataset

- Sources: Two publicly available superconductor databases.
- Features: 168 material descriptors (atomic radius, electronegativity, thermal conductivity, etc.)
- Target Variable: **Critical Temperature (Tc)**

Preprocessing:
- Z-score normalization
- Dimensionality reduction
- Correlation & skewness analysis
- Handling heteroskedasticity (Levene's Test)

---

## 🧪 Methodology

1. **Exploratory Data Analysis (EDA)**  
   - Shapiro-Wilk Test for normality  
   - Pearson correlation & multicollinearity check  
   - Boxplots and heatmaps for visual analysis

2. **Feature Engineering**  
   - Grouping based on periodic table properties  
   - Selection of most influential physical/chemical descriptors

3. **Model Development**  
   - Baseline regressors: Ridge, Lasso  
   - Tree-based models: Decision Tree, XGBoost, GradientBoost  
   - Final model: **Stacked Ensemble Model (XGBoost + GradientBoost + Meta-Learner)**

4. **Hyperparameter Tuning**  
   - Using `GridSearchCV` with cross-validation

5. **Evaluation Metrics**  
   - R² Score  
   - Root Mean Square Error (RMSE)

---

## 🧠 Models Used

| Model              | Test RMSE | Test R²  |
|--------------------|-----------|----------|
| Ridge Regression   | 17.23     | 0.7422   |
| Lasso Regression   | 17.33     | 0.7391   |
| XGBoost Regressor  | 8.78      | 0.9331   |
| **Stacked Ensemble** | **8.97**  | **0.9300** |

---

## 🔍 Key Features Influencing Tc

Top contributors identified by Ridge & Lasso Regression:

- Weighted Mean of Atomic Radius
- Electron Affinity (Standard Deviation)
- Valence Electron Configuration Entropy
- Thermal Conductivity (Weighted Mean)
- Electronegativity Index (Entropy & Std. Dev)

---

## ⚙️ Installation

1. Clone the repo:

```bash
git clone https://github.com/your-username/superconductor-tc-prediction.git
cd superconductor-tc-prediction
```

## Author
- (@Ninad_Gawali)[ninadgawali2004@gmail.com]
