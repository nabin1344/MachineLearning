Linear Regression

📌 Overview

This project demonstrates Linear Regression, one of the most fundamental supervised machine learning algorithms.

Linear Regression is used to predict a continuous numerical outcome based on one or more predictor variables.

Example

Predict a person’s income using education, age, and work experience.

⸻

🎯 Objective

Build a Linear Regression model to predict:

Outcome variable: income

using:

* education_years
* age
* experience

⸻

🧠 What is Linear Regression?

Linear Regression models the relationship between one dependent variable and one or more independent variables.

In simple terms:

Predictors (X)
      ↓
Linear Regression Model
      ↓
Predicted Outcome (y)

For this project:

Education + Age + Experience
              ↓
       Linear Regression
              ↓
            Income

⸻

📊 Dataset

The dataset contains 100 observations.

Variable	Description	Type
education_years	Number of years of education	Numerical
age	Age in years	Numerical
experience	Years of work experience	Numerical
income	Annual income	Numerical outcome

Predictor variables (X)

X = df[["education_years", "age", "experience"]]

Outcome variable (y)

y = df["income"]

⸻

🔄 Machine Learning Workflow

Load Data
    ↓
Inspect Data
    ↓
Define X and y
    ↓
Train/Test Split
    ↓
Train Model
    ↓
Make Predictions
    ↓
Evaluate Model
    ↓
Interpret Coefficients
    ↓
Check Residuals

⸻

💻 Minimal Code

1. Load data

import pandas as pd
df = pd.read_csv("linear_regression_income_dataset.csv")

2. Define X and y

X = df[["education_years", "age", "experience"]]
y = df["income"]

3. Train/Test split

from sklearn.model_selection import train_test_split
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=42
)

4. Train the model

from sklearn.linear_model import LinearRegression
model = LinearRegression()
model.fit(X_train, y_train)

5. Make predictions

y_pred = model.predict(X_test)

6. Evaluate

from sklearn.metrics import mean_absolute_error, mean_squared_error, r2_score
mae = mean_absolute_error(y_test, y_pred)
rmse = mean_squared_error(y_test, y_pred) ** 0.5
r2 = r2_score(y_test, y_pred)
print("MAE:", mae)
print("RMSE:", rmse)
print("R²:", r2)

⸻

📏 Evaluation Metrics

MAE — Mean Absolute Error

Measures the average size of prediction errors.

“How wrong am I on average?”

Lower MAE is generally better.

⸻

RMSE — Root Mean Squared Error

Similar to MAE, but gives more weight to large errors.

“How badly am I making large mistakes?”

Lower RMSE is generally better.

For the same predictions:

RMSE ≥ MAE

⸻

R² — R-squared

Measures how much of the variation in the outcome is explained by the model.

“How much of the variation in income can my model explain?”

Higher R² generally indicates better explanatory performance, but R² should not be interpreted alone.

⸻

🔍 Model Interpretation

The model coefficients show how the predicted outcome changes with each predictor, holding the other predictors constant.

pd.DataFrame({
    "Variable": X.columns,
    "Coefficient": model.coef_
})

For example, if the coefficient for education_years is positive:

Higher education years are associated with higher predicted income, holding age and experience constant.

⸻

📉 Residual Analysis

A residual is:

Residual = Actual − Predicted

Residuals help us assess whether the model’s errors show problematic patterns.

residuals = y_test - y_pred

A residual plot can be used to visually assess the errors.

⸻

🧪 Key Assumptions

For statistical inference, important Linear Regression assumptions include:

1. Linearity
2. Independence of observations/errors
3. Homoscedasticity
4. Approximately normal residuals for certain inference procedures
5. No severe multicollinearity among predictors

These assumptions should be checked rather than automatically assumed.

⸻

🛠️ Libraries Used

* Python
* pandas
* scikit-learn
* matplotlib

⸻

📚 Key Concepts Learned

* Dependent vs independent variables
* Features (X) and target (y)
* Train/test split
* Model fitting
* Prediction
* MAE
* RMSE
* R²
* Coefficients
* Intercept
* Residuals
* Linear Regression assumptions

⸻

🧠 Golden Rule

Linear Regression
        ↓
Predict a NUMBER
        ↓
Example:
Age + Education + Experience
        ↓
Income = 75,000

Remember

Linear Regression answers: “How much?”

⸻

🚀 Next Model

After Linear Regression, the next model in this learning roadmap is:

Logistic Regression

It is used when the outcome is a classification, such as:

Disease / No Disease
Yes / No
Pass / Fail
0 / 1
