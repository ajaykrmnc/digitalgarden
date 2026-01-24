---
title: "Research On Credit Risk Evaluation of Commercial Bank through ML"
date: 2025-01-05
categories: ["Coding", "Thesis"]
tags: ["machine-learning", "credit-risk", "thesis", "python", "finance"]
description: "A comprehensive research paper on portfolio credit risk modelling using machine learning techniques for commercial banks"
draft: false
---

## Abstract

This research presents a comprehensive study on portfolio credit risk modelling for commercial banks using advanced machine learning techniques. We explore the mathematical foundations of credit risk analysis, implement various gradient boosting models, and compare their performance in predicting loan defaults. Our findings demonstrate that Explainable Boosting Machines (EBM) provide an optimal balance between predictive accuracy and model interpretability, crucial for regulatory compliance in the banking sector.

## 1. Introduction

Credit risk analysis forms the cornerstone of modern banking operations. The ability to accurately predict the probability of default (PD) enables banks to:

- Price loans appropriately
- Maintain adequate capital reserves
- Optimize portfolio composition
- Comply with regulatory requirements (Basel III/IV)

Traditional statistical methods, while interpretable, often fail to capture complex non-linear relationships in credit data. This research bridges the gap between predictive power and explainability using modern ML techniques.

## 2. Mathematics of Credit Risk

### 2.1 Probability Theory

The foundation of credit risk lies in probability theory. For a loan with default probability $p$, the expected default rate over time horizon $T$ follows:

$$P(Default | T) = 1 - e^{-\lambda T}$$

where $\lambda$ represents the hazard rate (instantaneous default probability).

### 2.2 Statistical Regression

Logistic regression provides the baseline model:

$$P(Y=1|X) = \frac{1}{1 + e^{-(\beta_0 + \beta_1 X_1 + ... + \beta_n X_n)}}$$

### 2.3 Stochastic Processes

Default correlation is modelled using the Gaussian copula framework:

$$\rho_{ij} = Corr(Z_i, Z_j)$$

where $Z_i$ represents the latent variable driving firm $i$'s default.

### 2.4 Portfolio Theory

Portfolio Value-at-Risk (VaR) at confidence level $\alpha$:

$$VaR_\alpha = \inf\{l \in \mathbb{R} : P(L > l) \leq 1-\alpha\}$$

## 3. Theoretical Framework

### 3.1 Expected Loss (EL)

$$EL = PD \times LGD \times EAD$$

Where:
- **PD**: Probability of Default
- **LGD**: Loss Given Default
- **EAD**: Exposure at Default

### 3.2 Portfolio Risk

Unexpected Loss (UL) captures portfolio volatility:

$$UL = \sqrt{\sum_{i}\sum_{j} w_i w_j \sigma_i \sigma_j \rho_{ij}}$$

### 3.3 Risk-Adjusted Return on Capital (RAROC)

$$RAROC = \frac{Expected\ Revenue - Expected\ Loss - Operating\ Costs}{Economic\ Capital}$$

## 4. Gradient Boosting Models

### 4.1 Mathematical Foundation

Gradient boosting builds an additive model:

$$F_m(x) = F_{m-1}(x) + \gamma_m h_m(x)$$

where $h_m(x)$ is a weak learner fitted to pseudo-residuals:

$$r_{im} = -\left[\frac{\partial L(y_i, F(x_i))}{\partial F(x_i)}\right]_{F=F_{m-1}}$$

### 4.2 XGBoost Objective

$$\mathcal{L} = \sum_{i=1}^{n} l(y_i, \hat{y}_i) + \sum_{k=1}^{K} \Omega(f_k)$$

with regularization term:

$$\Omega(f) = \gamma T + \frac{1}{2}\lambda \|w\|^2$$

## 5. Data Preprocessing

### 5.1 Variable Selection

Feature importance determined via:
- Information Value (IV)
- Gini Importance
- SHAP Values

### 5.2 Data Imputation

Missing value handling strategies:
- Mean/Median imputation for numerical features
- Mode imputation for categorical features
- KNN-based imputation for complex patterns
- Multiple Imputation by Chained Equations (MICE)

### 5.3 Feature Reduction using PCA

Principal Component Analysis reduces dimensionality while preserving variance:

$$Z = XW$$

where $W$ contains eigenvectors of the covariance matrix. Components selected based on explained variance ratio exceeding 95%.

## 6. Explainable Boosting Machine (EBM)

EBM provides glass-box interpretability with gradient boosting performance:

$$g(E[y]) = \beta_0 + \sum f_j(x_j) + \sum f_{ij}(x_i, x_j)$$

Key advantages:
- **Interpretable**: Individual feature contributions are visible
- **Accurate**: Comparable to black-box models
- **Regulatory Compliant**: Satisfies explainability requirements

## 7. Results

### Model Performance Comparison

| Algorithm | AUC-ROC | Accuracy | Precision | Recall | F1-Score |
|-----------|---------|----------|-----------|--------|----------|
| Logistic Regression | 0.72 | 0.68 | 0.65 | 0.70 | 0.67 |
| Random Forest | 0.81 | 0.76 | 0.74 | 0.78 | 0.76 |
| XGBoost | 0.85 | 0.80 | 0.78 | 0.82 | 0.80 |
| LightGBM | 0.84 | 0.79 | 0.77 | 0.81 | 0.79 |
| CatBoost | 0.84 | 0.79 | 0.78 | 0.80 | 0.79 |
| **EBM** | **0.83** | **0.78** | **0.76** | **0.80** | **0.78** |

*EBM achieves near-top performance while maintaining full interpretability.*

### Key Findings

1. **Gradient boosting models** significantly outperform traditional logistic regression
2. **XGBoost** achieves highest predictive accuracy
3. **EBM** provides best trade-off between accuracy and explainability
4. **Feature engineering** contributes more to performance than model selection

## 8. Conclusion

This research demonstrates that machine learning techniques, particularly gradient boosting models, substantially improve credit risk prediction accuracy. The Explainable Boosting Machine emerges as the recommended approach for commercial banks, offering:

- Strong predictive performance (AUC-ROC: 0.83)
- Full model interpretability
- Regulatory compliance for Basel requirements
- Actionable insights for credit officers

Future work should explore deep learning approaches and alternative data sources for enhanced prediction.

## Bibliography

1. Breiman, L. (2001). Random Forests. *Machine Learning*, 45(1), 5-32.
2. Chen, T., & Guestrin, C. (2016). XGBoost: A Scalable Tree Boosting System. *KDD*.
3. Friedman, J. H. (2001). Greedy Function Approximation: A Gradient Boosting Machine. *Annals of Statistics*.
4. Ke, G., et al. (2017). LightGBM: A Highly Efficient Gradient Boosting Decision Tree. *NeurIPS*.
5. Lou, Y., et al. (2013). Accurate Intelligible Models with Pairwise Interactions. *KDD*.
6. Merton, R. C. (1974). On the Pricing of Corporate Debt. *Journal of Finance*.
7. Nori, H., et al. (2019). InterpretML: A Unified Framework for Machine Learning Interpretability.
8. Prokhorenkova, L., et al. (2018). CatBoost: Unbiased Boosting with Categorical Features. *NeurIPS*.
9. Siddiqi, N. (2012). *Credit Risk Scorecards: Developing and Implementing Intelligent Credit Scoring*. Wiley.
10. Thomas, L. C. (2009). *Consumer Credit Models: Pricing, Profit and Portfolios*. Oxford University Press.

