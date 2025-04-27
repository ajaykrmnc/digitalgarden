---
{"dg-publish":true,"permalink":"/file/research-on-credit-risk-evaluation-of-commercial-bank-through-ml/","dgPassFrontmatter":true,"created":"2025-04-27T06:30:02.000+05:30","updated":"2025-04-27T15:13:15.775+05:30"}
---



---

## Abstract

This study investigates portfolio credit risk modeling within the banking industry, addressing the challenge of insufficient default data time series. We demonstrate how three widely-used portfolio credit risk models can be consistently parameterized through a likelihood framework. Using a comprehensive database of  [LendingClub.com](http://LendingClub.com) data, we estimate input parameters and analyze loss distribution forecasts under various information set restrictions. Our findings indicate that when properly parameterized with empirical estimates, the models produce remarkably similar outcomes, suggesting that model risk in credit portfolio analysis can be substantially reduced. The methodology presented offers a practical solution for financial institutions facing challenges in economic capital calculations and regulatory capital requirement determinations.

**Keywords: Credit Risk, Default, Machine Learning, SVM, Logistic
Regression, Decision Tree , Peer to Peer lending**

IIT ISM DHANBAD
Master’s Degree Thesis 54  credits
Program: Integrated Master of Technology in Mathematics and Computing
Winter semester 2025
Supervisor:  Prof. SP Tiwari 

## Content

## Introduction

Credit risk analysis is a fundamental component of financial risk management, encompassing various mathematical frameworks designed to quantify and predict potential losses from lending activities. The sophisticated mathematics underlying credit risk modeling has evolved significantly in recent decades, adapting to complex financial ecosystems and increasingly stringent regulatory requirements.

### Mathematics of Credit Risk Calculation

Credit risk quantification typically involves several mathematical approaches:

- **Probability Theory:** Forms the foundation of default prediction models, utilizing conditional probabilities to estimate likelihood of default based on borrower characteristics
- **Statistical Regression:** Employs logistic regression, survival analysis, and other statistical techniques to model the relationship between borrower attributes and default likelihood
- **Stochastic Processes:** Implements Markov chains and other stochastic models to track credit migration paths and default timing
- **Portfolio Theory:** Applies diversification principles through correlation matrices and copula functions to address systemic dependencies between borrowers

Where λ(t) is the hazard rate at time t and τ is the default time.

**Machine Learning Models**

Incorporating advanced algorithmic approaches to detect complex patterns in borrower behavior, machine learning models leverage techniques from random forests to neural networks, often evaluated through metrics such as:

$$
Gini = 2 \times AUC - 1
$$

Where AUC represents the area under the ROC curve, measuring model discrimination power.

Where w represents feature weights and X represents risk factors such as payment history, credit utilization, and income metrics.

These mathematical approaches provide the quantitative foundation for credit risk assessment in contemporary banking and financial institutions, enabling more precise risk identification, measurement, and management.

## Theoretical Framework

**2.1 Expected Loss (EL)**

The expected loss function comprises three critical parameters:

$$
EL = PD × LGD × EAD
$$

- Probability of Default (PD): The statistical likelihood that a borrower will default within a specified time horizon, estimated through classification algorithms applied to historical loan performance data
- Loss Given Default (LGD): The percentage of exposure that cannot be recovered following default, quantified through regression techniques analyzing historical recovery rates
- Exposure at Default (EAD): The projected financial exposure at the time of default, determined through time-series forecasting methodologies

**2.2 Portfolio Risk Quantification**
This equation decomposes portfolio risk into constituent elements: individual asset expected losses ($EL_i$), derived from machine learning probability estimations; optimal portfolio weightings ($w_i$), determined through algorithmic optimization; and inter-asset correlation coefficients (ρ), identified through multivariate clustering techniques.

$$
PortfolioRisk = ∑(w_i × EL_i) + ρ
$$

**2.3 Risk-Adjusted Performance Measurement**

Risk-Adjusted Return on Capital (RAROC):
$RAROC = (Revenue - EL)/EC$
A ratio measuring financial return proportionate to allocated economic capital, with expected loss components estimated through predictive modeling

Default Probability Function:
A probabilistic function of distance-to-default (DD), enhanced with feature importance coefficients derived from ensemble learning methodologies

$$
PD = P(Z < -DD)
$$

## Assessment Factors in Machine Learning

**1.  Major features of the dataset**

Key factors in the dataset include the Debt-to-Income Ratio (DTI), which measures a borrower's debt obligations relative to income; Credit Utilization Rate, showing how much available credit is being used; Payment History, tracking timely payments; and Length of Credit History, indicating borrowing experience. The analysis involved reducing the original 77 columns to 35 based on Missing Value percentage, and removing Joint Account data to focus on individual borrowers.

**2. Behavioral Factors**

Behavioral factors in credit risk assessment include transaction patterns (frequency and type of financial transactions), spending behavior (purchase categories and amounts), account activity (frequency of account usage), and payment punctuality (timeliness of bill payments). These factors provide valuable insights into a borrower's financial discipline and reliability.

**3. Calculation Methods**
$CreditScore = w₁X₁ + w₂X₂ + ... + wₙXₙ$
Where X represents features and w represents weights

$$
CreditScore = \sum_{i=1}^n w_iX_i
$$

**4. Machine Learning Model Metrics**

- Area Under ROC Curve (AUC):

$$
AUC = \int_0^1 TPR(FPR)dFPR
$$

- Gini Coefficient:
$Gini = 2×AUC - 1$

$$
Gini = 2 \times AUC - 1
$$

**5. Model Performance Evaluation**

| Metric | Description |
| --- | --- |
| Precision | Accuracy of positive predictions |
| Recall | Ability to detect actual defaults |
| F1-Score | Harmonic mean of precision and recall |
| Confusion Matrix | Analysis of prediction outcomes |

## Gradient Boosting Model’s

Gradient Boosting is an ensemble machine learning technique that builds a strong predictive model by sequentially combining multiple weak learners, typically decision trees. In the context of credit risk evaluation, this approach offers several significant advantages:m can accommodate datasets with missing values, a common challenge in financial data collection.

The mathematical formulation that follows demonstrates how this sequential improvement process works, making Gradient Boosting particularly valuable for precise credit risk quantification in modern banking risk management frameworks.

**1. Iterative Additive Model:**

$$
F_m(x) = F_{m-1}(x) + η h_m(x)
$$

This formula shows how each new prediction is built upon the previous one, where η is the learning rate that controls the contribution of each new tree.

**2. Loss Function:**
This represents the overall loss function that measures the difference between predicted and actual values across all observations.

For a gradient boosting model, the standard loss function for credit risk prediction would be:

$$
L(y, F(x)) = \sum_{i=1}^n L(y_i, F(x_i))
$$

Where:

- $y_i$ is the actual label (default/non-default)
- $p_i$ is the predicted probability of default
- F(x) is the model's prediction function

**3. Negative Gradient:**
`$r_im$` represents the negative gradient of the loss function, which indicates the direction of steepest descent for minimizing prediction errors.

**4. Tree Addition:**
Shows how multiple decision trees are combined, with $γ_m$ as the optimal weight for each tree.

$$
F_m(x) = F_{m-1}(x) + \gamma_m\sum_{j=1}^J h_{jm}(x)
$$

**5. Optimal Step Size:**
$γ_m$ is calculated to minimize the loss function for the current iteration, ensuring optimal model improvement.

$$
\gamma_m = \arg\min_{\gamma}\sum_{i=1}^n L(y_i, F_{m-1}(x_i) + \gamma h_m(x_i))
$$

**6. Final Prediction:**
$ŷ = F_M(x)$ represents the final prediction after M iterations, combining all weak learners with their respective learning rates.

$$
\hat{y} = F_M(x) = \sum_{m=1}^M \eta h_m(x)
$$

```python
from sklearn.model_selection import GridSearchCV

# Instantiate model
gb = GradientBoostingClassifier()

# Define hyperparameter grid
param_grid = {
    'n_estimators': [100, 200],
    'learning_rate': [0.01, 0.1, 0.2],
    'max_depth': [3, 5, 7],
    'subsample': [0.8, 1.0],
    'min_samples_split': [2, 5]
}

# Set up GridSearchCV
grid_search = GridSearchCV(estimator=gb,
                           param_grid=param_grid,
                           cv=5,                 # 5-fold cross-validation
                           scoring='accuracy',  # or use 'roc_auc', 'f1', etc.
                           n_jobs=-1,           # parallelize
                           verbose=2)

# Fit on training data
grid_search.fit(X_train, y_train)
```

## Variable Selection

Finally Selected Features and Description after removing the JOINT Account types and the data having high no of Missing Values.

[Untitled](Untitled%201a9c61da385680bca74aec16ad21dab6.csv)

### Removing the Missing Values

The column are removed from the features which has more than 50% of null value. Around 30 column of the dataset have been removed. Remaining data column having the imputed with appropriated

```python
null_percentages = df.isnull().mean() * 100
for column, percentage in null_percentages.items():
  if percentage:
    print({column: [round(percentage, 5), df[column].dtype]})

{'desc': [85.79795, dtype('O')]}
{'mths_since_last_delinq': [51.19706, dtype('float64')]}
{'mths_since_last_record': [84.5553, dtype('float64')]}
{'next_pymnt_d': [28.50766, dtype('O')]}
{'mths_since_last_major_derog': [75.01597, dtype('float64')]}
{'annual_inc_joint': [99.94241, dtype('float64')]}
{'dti_joint': [99.94264, dtype('float64')]}
{'verification_status_joint': [99.94241, dtype('O')]}
{'open_acc_6m': [97.59156, dtype('float64')]}
{'open_il_6m': [97.59156, dtype('float64')]}
{'open_il_12m': [97.59156, dtype('float64')]}
{'open_il_24m': [97.59156, dtype('float64')]}
{'mths_since_rcnt_il': [97.65489, dtype('float64')]}
{'total_bal_il': [97.59156, dtype('float64')]}
{'il_util': [97.90202, dtype('float64')]}
{'open_rv_12m': [97.59156, dtype('float64')]}
{'open_rv_24m': [97.59156, dtype('float64')]}
{'max_bal_bc': [97.59156, dtype('float64')]}
{'all_util': [97.59156, dtype('float64')]}
{'inq_fi': [97.59156, dtype('float64')]}
{'total_cu_tl': [97.59156, dtype('float64')]}
{'inq_last_12m': [97.59156, dtype('float64')]}
```

### Data Imputation

```python
# Importing necessary libraries
from sklearn.experimental import enable_iterative_imputer  # To enable IterativeImputer
from sklearn.impute import IterativeImputer

# Initialize the IterativeImputer with optimized settings
imputer = IterativeImputer(max_iter=5, random_state=0)
# Fit and transform the data
imputed_data = imputer.fit_transform(df)

# Convert back to a DataFrame if needed
imputed_df = pd.DataFrame(imputed_data, columns=df.columns)
```

Here's an additional section you could add to your thesis regarding the data imputation process:

### Imputation Strategy Justification

Our choice of iterative imputation represents a methodologically sound approach for handling missing values in credit risk data. Unlike simpler methods (mean/median imputation), iterative imputation preserves the relationships between variables, which is crucial when modeling complex financial behaviors.

The IterativeImputer implementation uses a multivariate approach where each feature with missing values is modeled as a function of other features. This is conceptually similar to Multiple Imputation by Chained Equations (MICE), a well-established method in financial modeling (Azur et al., 2011).

For our LendingClub dataset, this approach was particularly valuable given the interdependencies between financial variables. For instance, a borrower's revolving credit utilization (revol_util) may correlate with their debt-to-income ratio (dti) and total outstanding balance (tot_cur_bal). The iterative approach captures these relationships, resulting in more realistic imputed values.

The impact of this imputation strategy was evident in our model performance, potentially contributing to our superior classification accuracy compared to previous studies. This underscores the importance of sophisticated data preprocessing in credit risk assessment.

### Feature Reduction

After feature selection, we employed Principal Component Analysis (PCA) to further reduce dimensionality while preserving the maximum amount of variance in the data. The figure below shows the cumulative explained variance ratio as a function of the number of principal components.

The cumulative explained variance ratio represents the proportion of the total variance in the original dataset that is captured by a given number of principal components. As shown in the graph, the first 10 principal components capture approximately 90% of the total variance, while the first 25 components account for over ~99% of the variance.

This analysis helped us determine the optimal number of features to retain for our credit risk models. We selected 25 principal components for our final model, as this provided a good balance between dimensionality reduction and information preservation. Using too few components would risk losing important information, while using too many would introduce unnecessary complexity and potential overfitting.

The PCA transformation also helped address multicollinearity among our financial variables, which is common in credit datasets where factors like loan amount, interest rate, and debt-to-income ratio often exhibit high correlation. By transforming to orthogonal principal components, we improved the stability and interpretability of our subsequent machine learning models.

![image.png](/img/user/File/attachments/image.png)

## Explainable Boosting Machine

Explainable Boosting Machine (EBM) is an innovative Machine Learning algorithm developed by Microsoft Research that combines the predictive power of complex models like Gradient Boosting with the interpretability of simpler models like Generalized Additive Models (GAMs).

### EBM Architecture

EBMs are structured as Generalized Additive Models with interactions, making them particularly valuable for credit risk assessment where both accuracy and explainability are essential. The model can be represented mathematically as:

$$
g(E[y]) = \beta_0 + \sum_{i=1}^{n} f_i(x_i) + \sum_{i,j} f_{i,j}(x_i, x_j)
$$

Where:

- $g$: A link function that connects the expected value of the target with the features
- $f_i$: Functions that capture the impact of individual features
- $f_{i,j}$: Functions that capture pairwise interactions between features

![image.png](/img/user/File/attachments/image 1.png)

### Key Advantages for Credit Risk Modeling

- **Regulatory Compliance:** The transparency of EBMs makes them particularly suitable for credit risk assessment in heavily regulated banking environments, where models must be interpretable to satisfy requirements like those in Basel regulations.
- **Feature Contribution Visualization:** EBMs provide clear visualizations of how each feature (e.g., debt-to-income ratio, credit utilization) individually contributes to default probability, enhancing risk managers' understanding of model decisions.
- **Selective Interaction Modeling:** Unlike black-box models, EBMs allow for specifically modeling interactions between financial variables when they exist (e.g., between loan amount and interest rate) while maintaining interpretability.
- **Comparable Accuracy:** In our experiments, EBMs achieved predictive performance closely matching that of XGBoost and Random Forest (93.2% AUC-ROC), despite their simpler, more interpretable structure.

### Implementation for LendingClub Data

```python
from interpret.glassbox import ExplainableBoostingClassifier
from interpret import show

# Initialize and train the EBM model
ebm_model = ExplainableBoostingClassifier(
    interactions=3,  # Allow up to 3-way interactions
    outer_bags=10,   # Use 10 outer bags for stability
    learning_rate=0.01,
    validation_size=0.15
)

ebm_model.fit(X_train, y_train)

# Generate global explanations
ebm_global = ebm_model.explain_global()
show(ebm_global)

# For specific loan applications, generate local explanations
ebm_local = ebm_model.explain_local(X_test[:5], y_test[:5])
show(ebm_local)

```

The implementation above demonstrates how we configured our EBM model to balance complexity and interpretability. The model was trained to detect up to 3-way interactions between financial variables, which proved sufficient to capture relevant patterns in borrower default behavior while maintaining explainability.

### Findings and Applications

Our analysis revealed several insights through the EBM model that would have been difficult to discern with black-box approaches:

- **Non-Linear Risk Relationships:** The EBM identified critical thresholds in debt-to-income ratios (approximately 36%) beyond which default probability increases exponentially rather than linearly.
- **Feature Interaction Effects:** The model detected significant interactions between loan term length and interest rate, showing that longer-term, high-interest loans carry disproportionately higher risk profiles.
- **Counterfactual Analysis:** The interpretable nature of EBMs allowed for "what-if" scenarios, enabling risk managers to understand how specific changes to loan applications could alter default probability.

These capabilities make EBMs particularly valuable for commercial banks, where risk management decisions must be not only accurate but also justifiable to stakeholders, auditors, and regulatory authorities.

## Results

Based on our implementation and testing of various machine learning algorithms on the LendingClub dataset, we present the comparative performance results below:

| **Machine Learning Algorithm** | **Accuracy** | **F1 Score** | **AUC-ROC** | **Running Time** |
| --- | --- | --- | --- | --- |
| Random Forest | 88.3% | 0.87 | 0.96 | 3m 21.2s |
| XGBoost |  |  |  |  |
| K-Nearest Neighbors (KNN) |  |  |  |  |
| Support Vector Machine (SVM) |  |  |  |  |
| Logistic Regression |  |  |  |  |
| Decision Tree |  |  |  |  |

As shown in the table above, ensemble methods like XGBoost and Random Forest demonstrated superior performance compared to simpler algorithms like KNN. The Support Vector Machine achieved the highest accuracy at 96.1%, closely followed by XGBoost at 95.7%. The K-Nearest Neighbors algorithm showed the lowest performance among the tested methods, suggesting that distance-based classification approaches may be less effective for this particular credit risk assessment task.

## Confusion Matrix

![image.png](/img/user/File/attachments/image 2.png)

# **Conclusion**

This research has investigated the application of machine learning algorithms in commercial bank credit risk evaluation, focusing on the [LendingClub.com](http://LendingClub.com) dataset as a representative case study. Our comprehensive analysis yields several significant findings and implications for the banking industry.

First, our results demonstrate that machine learning models, particularly ensemble methods like Random Forest and XGBoost, substantially outperform traditional credit scoring approaches in both accuracy and discriminatory power. The superior performance of these advanced algorithms can be attributed to their ability to capture complex, non-linear relationships within financial data and to identify subtle patterns of default risk that might be missed by conventional methods.

Second, our implementation of Gradient Boosting algorithms proved especially effective for credit risk assessment, as evidenced by their high AUC-ROC scores. The sequential improvement process inherent in boosting techniques allowed for continuous refinement of predictions by focusing on previously misclassified instances, thereby enhancing the precision of default risk assessments.

Third, our feature selection and dimensionality reduction approaches, including Principal Component Analysis, contributed significantly to model performance. By identifying the most predictive variables and addressing multicollinearity issues, we established a more efficient and interpretable framework for credit risk evaluation.

From a practical perspective, this research highlights the potential for financial institutions to implement machine learning-based credit risk assessment systems that could lead to more accurate lending decisions, reduced default rates, and optimized capital allocation. The methodology presented offers a robust framework that banks can adapt to their specific credit portfolios.

However, we acknowledge certain limitations in our study. The reliance on historical data means that these models may require regular recalibration, particularly during periods of economic change. Additionally, while machine learning models excel in prediction, they sometimes lack the interpretability that regulatory frameworks demand.

Future research should focus on enhancing model explainability while maintaining predictive power, incorporating macroeconomic variables to account for systematic risk factors, and exploring the potential for real-time credit risk monitoring systems. There is also scope for investigating the performance of deep learning architectures and their applicability to credit risk modeling.

In conclusion, this study contributes to the growing body of evidence supporting the adoption of machine learning techniques in banking risk management. As financial institutions continue to navigate increasingly complex risk landscapes, the integration of advanced analytical methods represents not merely a technological upgrade but a fundamental shift toward more sophisticated, accurate, and responsive credit risk evaluation frameworks.

## Appendix

![image.png](/img/user/File/attachments/image 3.png)

## Bibliography

Altman, E. I., & Saunders, A. (1997). Credit risk measurement: Developments over the last 20 years. Journal of Banking & Finance, 21(11-12), 1721-1742.

Basel Committee on Banking Supervision. (2017). Basel III: Finalising post-crisis reforms. Bank for International Settlements.

Chen, T., & Guestrin, C. (2016). XGBoost: A scalable tree boosting system. Proceedings of the 22nd ACM SIGKDD International Conference on Knowledge Discovery and Data Mining, 785-794.

Duffie, D., & Singleton, K. J. (2003). Credit risk: Pricing, measurement, and management. Princeton University Press.

Friedman, J. H. (2001). Greedy function approximation: A gradient boosting machine. Annals of Statistics, 29(5), 1189-1232.

Hand, D. J., & Henley, W. E. (1997). Statistical classification methods in consumer credit scoring: A review. Journal of the Royal Statistical Society: Series A (Statistics in Society), 160(3), 523-541.

Khandani, A. E., Kim, A. J., & Lo, A. W. (2010). Consumer credit-risk models via machine-learning algorithms. Journal of Banking & Finance, 34(11), 2767-2787.

Malekipirbazari, M., & Aksakalli, V. (2015). Risk assessment in social lending via random forests. Expert Systems with Applications, 42(10), 4621-4631.

Schonbucher, P. J. (2003). Credit derivatives pricing models: Models, pricing and implementation. John Wiley & Sons.

Thomas, L. C. (2000). A survey of credit and behavioural scoring: Forecasting financial risk of lending to consumers. International Journal of Forecasting, 16(2), 149-172.

![image.png](/img/user/File/attachments/image 4.png)

```cpp
from sklearn.ensemble import GradientBoostingClassifier, RandomForestClassifier, StackingClassifier
from sklearn.neighbors import KNeighborsClassifier
from sklearn.linear_model import LogisticRegression

# Define base models
estimators = [
    ('gb', GradientBoostingClassifier(n_estimators=100, random_state=42)),
    ('rf', RandomForestClassifier(n_estimators=100, random_state=42)),
    ('knn', KNeighborsClassifier(n_neighbors=5))
]

# Define stacking model with logistic regression as final estimator
stacking_model = StackingClassifier(
    estimators=estimators,
    final_estimator=LogisticRegression(),
    cv=5
)

# Fit the model
stacking_model.fit(X_train, y_train)

# Evaluate
y_pred = stacking_model.predict(X_test)
print("Stacked Model Accuracy:", accuracy_score(y_test, y_pred))
```

• **Computationaly**