# Ames Housing – Regression Model Comparison

This project compares **Linear Regression**, **Ridge**, **Lasso**, and **ElasticNet**
models on the Ames Housing dataset to evaluate the impact of regularization
techniques on high-dimensional and multicollinear data.

The main objective is to analyze how different regularization approaches
affect prediction performance and model stability in housing price prediction.

---

## Dataset
- **Ames Housing Dataset**
- Target variable: **SalePrice**
- Contains both numerical and categorical features
- High dimensionality after one-hot encoding

> The dataset is not included in the repository due to size constraints.
> It can be obtained from the Kaggle *House Prices: Advanced Regression Techniques* competition.

---

## Methodology

### Data Preprocessing
- **Missing Value Handling**
  - Categorical variables filled with `"None"`
  - Structural numerical missing values (e.g. garage, basement related features) filled with `0`
  - Remaining numerical missing values filled with **median**
- **Categorical Encoding**
  - One-hot encoding applied using `get_dummies`
- **Feature Scaling**
  - `StandardScaler` applied **only to numerical features**
  - Dummy (0/1) variables were not scaled
- **Data Splitting**
  - Train-test split applied before modeling

### Model Training
- Hyperparameter tuning performed using **GridSearchCV**
- Cross-validation used to ensure robust model comparison

---

## Models Compared
- **Linear Regression**
- **Ridge Regression** (L2 Regularization)
- **Lasso Regression** (L1 Regularization)
- **ElasticNet Regression** (L1 + L2 Regularization)

---

## Evaluation Metrics
- **R² Score**
- **Mean Squared Error (MSE)**
- **Root Mean Squared Error (RMSE)**

These metrics were used to evaluate both predictive accuracy and error magnitude.

---

## Results
- **Ridge Regression** achieved the **highest R² score** and **lowest RMSE**
- **Linear Regression** performed worst due to lack of regularization
- **Lasso** and **ElasticNet** produced competitive results but slightly underperformed Ridge

<p align="center">
  <img src="r2_score.png" width="45%">
  <img src="rmse.png" width="45%">
</p>

---

## Conclusion
Ridge Regression proved to be the most suitable model for the Ames Housing dataset.
Its L2 regularization effectively handled multicollinearity and high dimensionality
by shrinking coefficients in a balanced manner, leading to improved generalization
performance compared to Linear Regression.

This study demonstrates the importance of regularization when working with
complex, feature-rich datasets.

---

## Key Takeaways
- Regularization significantly improves regression performance
- Ridge Regression is particularly effective in multicollinear settings
- Feature scaling is critical for Lasso and ElasticNet models
- Proper handling of missing values and categorical variables is essential

---

## Technologies Used
- Python
- Pandas, NumPy
- Scikit-learn
- Matplotlib











