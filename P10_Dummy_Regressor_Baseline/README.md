# P10 — Dummy Regressor Baseline Model

## 📌 Practical Information

| Field              | Details                                                       |
| ------------------ | ------------------------------------------------------------- |
| **Practical No.**  | P10                                                           |
| **Practical Name** | Creating a Baseline Model Using Scikit-learn's DummyRegressor |
| **Course Outcome** | CO1                                                           |
| **Hours**          | 8                                                             |

---

## 🎯 Aim

To create a simple **baseline regression model** using scikit-learn's `DummyRegressor` and use it as a reference for evaluating the performance of a machine learning regression model.

---

## 📚 Objectives

The objectives of this practical are:

* Understand the concept of a baseline model.
* Understand regression problems.
* Learn about scikit-learn's `DummyRegressor`.
* Create a simple baseline regression model.
* Generate baseline predictions.
* Evaluate the baseline model using regression metrics.
* Compare a machine learning model with a simple baseline.

---

## 🧠 What is a Baseline Model?

A **baseline model** is a simple model used as a reference point for evaluating the performance of a machine learning model.

Instead of learning complex relationships from the data, a baseline model makes simple predictions using a predefined strategy.

For example:

```text
Training Data
     ↓
DummyRegressor
     ↓
Simple Baseline Prediction
     ↓
Compare with Actual Values
     ↓
Evaluate Performance
```

A machine learning model should generally provide useful improvement over an appropriate baseline.

---

## 🤖 DummyRegressor

`DummyRegressor` is a simple regression estimator provided by **Scikit-learn**.

It does not learn meaningful relationships between input features and the target. Instead, it predicts values using a simple strategy.

Common strategies include:

* `mean`
* `median`
* `quantile`
* `constant`

The default strategy is:

```python
strategy="mean"
```

With the mean strategy, the model predicts the **mean value of the training target** for every test observation.

---

## 🛠️ Technologies Used

* **Python**
* **Jupyter Notebook**
* **NumPy**
* **Pandas**
* **Scikit-learn**

---

## 📂 Project Structure

```text
P10_Dummy_Regressor_Baseline/
│
├── P10_Dummy_Regressor_Baseline.ipynb
└── README.md
```

---

## 📊 Example Dataset

A simple dataset can be used to demonstrate regression.

Example:

| Study Hours | Previous Marks | Final Marks |
| ----------: | -------------: | ----------: |
|           2 |             60 |          65 |
|           3 |             65 |          70 |
|           4 |             70 |          75 |
|           5 |             75 |          80 |
|           6 |             80 |          85 |
|           7 |             85 |          90 |

Here:

* `Study Hours` and `Previous Marks` are input features.
* `Final Marks` is the target variable.

---

## 📦 Libraries Used

```python
import numpy as np
import pandas as pd

from sklearn.model_selection import train_test_split
from sklearn.dummy import DummyRegressor
from sklearn.metrics import mean_squared_error, mean_absolute_error, r2_score
```

---

## 🔹 Creating Features and Target

The input features and target variable are separated as:

```python
X = df[["Study_Hours", "Previous_Marks"]]

y = df["Final_Marks"]
```

Where:

```text
X → Input Features
y → Target Variable
```

---

## 🔹 Splitting the Dataset

The dataset is divided into training and testing data.

```python
X_train, X_test, y_train, y_test = train_test_split(
    X,
    y,
    test_size=0.2,
    random_state=42
)
```

The training data is used to calculate the baseline prediction, while the test data is used to evaluate it.

---

## 🔹 Creating DummyRegressor

A baseline model using the mean strategy is created as follows:

```python
dummy_model = DummyRegressor(strategy="mean")
```

The model is then trained:

```python
dummy_model.fit(X_train, y_train)
```

---

## 🔮 Making Predictions

Predictions are generated using:

```python
y_pred = dummy_model.predict(X_test)

print("Predictions:")
print(y_pred)
```

Since the `mean` strategy is used, the model predicts approximately the same value for every test observation.

---

## 📏 Evaluating the Baseline Model

The baseline can be evaluated using common regression metrics.

### Mean Absolute Error

```python
mae = mean_absolute_error(y_test, y_pred)

print("Mean Absolute Error:", mae)
```

### Mean Squared Error

```python
mse = mean_squared_error(y_test, y_pred)

print("Mean Squared Error:", mse)
```

### R² Score

```python
r2 = r2_score(y_test, y_pred)

print("R² Score:", r2)
```

---

## 🧪 Complete Code Example

```python
# P10 - DummyRegressor Baseline Model

import numpy as np
import pandas as pd

from sklearn.model_selection import train_test_split
from sklearn.dummy import DummyRegressor
from sklearn.metrics import mean_squared_error, mean_absolute_error, r2_score

# Create dataset
data = {
    "Study_Hours": [2, 3, 4, 5, 6, 7, 8, 9, 10, 11],
    "Previous_Marks": [60, 65, 70, 75, 80, 85, 88, 90, 92, 95],
    "Final_Marks": [65, 70, 75, 80, 85, 90, 92, 94, 96, 98]
}

df = pd.DataFrame(data)

print("Dataset:")
print(df)

# Separate features and target
X = df[["Study_Hours", "Previous_Marks"]]
y = df["Final_Marks"]

# Split the dataset
X_train, X_test, y_train, y_test = train_test_split(
    X,
    y,
    test_size=0.2,
    random_state=42
)

print("\nTraining Data:")
print(X_train)

print("\nTesting Data:")
print(X_test)

# Create DummyRegressor
dummy_model = DummyRegressor(strategy="mean")

# Train the baseline model
dummy_model.fit(X_train, y_train)

# Make predictions
y_pred = dummy_model.predict(X_test)

print("\nActual Values:")
print(y_test.values)

print("\nBaseline Predictions:")
print(y_pred)

# Calculate evaluation metrics
mae = mean_absolute_error(y_test, y_pred)
mse = mean_squared_error(y_test, y_pred)
r2 = r2_score(y_test, y_pred)

print("\nEvaluation Results:")
print("Mean Absolute Error:", mae)
print("Mean Squared Error:", mse)
print("R² Score:", r2)
```

---

## 🔄 Workflow

```text
Start
  ↓
Create / Load Dataset
  ↓
Separate Features and Target
  ↓
Split Dataset into Training and Testing Data
  ↓
Create DummyRegressor
  ↓
Select Baseline Strategy
  ↓
Train Baseline Model
  ↓
Generate Predictions
  ↓
Calculate Evaluation Metrics
  ↓
Analyze Baseline Performance
  ↓
End
```

---

## 📊 Baseline Prediction Strategy

When using:

```python
DummyRegressor(strategy="mean")
```

the model calculates the mean target value from the training data.

For example:

```text
Training Target Values
        ↓
Calculate Mean
        ↓
Mean = Baseline Prediction
        ↓
Predict Same Value for Test Samples
```

Therefore, the DummyRegressor provides a simple reference against which more advanced regression models can be compared.

---

## 🔍 Other DummyRegressor Strategies

### Mean

```python
DummyRegressor(strategy="mean")
```

Predicts the mean of the training target.

### Median

```python
DummyRegressor(strategy="median")
```

Predicts the median of the training target.

### Constant

```python
DummyRegressor(strategy="constant", constant=50)
```

Predicts a fixed constant value.

### Quantile

```python
DummyRegressor(strategy="quantile", quantile=0.5)
```

Predicts a selected quantile of the training target.

---

## 📈 Why Use a Baseline?

A baseline model helps answer an important question:

> Is the machine learning model actually learning useful patterns from the data?

For example:

```text
DummyRegressor
      ↓
Baseline Performance
      ↓
Train Advanced Regression Model
      ↓
Compare Performance
```

If an advanced model does not provide meaningful improvement over the baseline, the model, features, or data may require further investigation.

---

## 🎓 Learning Outcomes

After completing this practical, the following concepts are understood:

* Understanding baseline models.
* Understanding regression problems.
* Understanding `DummyRegressor`.
* Using different baseline strategies.
* Creating a mean-based regression baseline.
* Generating baseline predictions.
* Evaluating regression models.
* Understanding MAE, MSE, and R².
* Using a baseline for model comparison.

---

## ✅ Result

A simple regression baseline model was successfully created using **Scikit-learn's `DummyRegressor`**.

The model generated baseline predictions using the selected strategy and its performance was evaluated using:

```text
Mean Absolute Error
Mean Squared Error
R² Score
```

The DummyRegressor can be used as a reference point for comparing the performance of more advanced regression models.

---

## ⚙️ Requirements

Install the required libraries using:

```bash
pip install numpy pandas scikit-learn
```

---

## ▶️ How to Run

### Step 1: Open Jupyter Notebook

Run:

```bash
jupyter notebook
```

### Step 2: Open the Practical

Navigate to:

```text
P10_Dummy_Regressor_Baseline/
```

and open:

```text
P10_Dummy_Regressor_Baseline.ipynb
```

### Step 3: Execute the Notebook

Run all cells sequentially to:

1. Create or load the dataset.
2. Separate features and target.
3. Split the dataset.
4. Create the `DummyRegressor`.
5. Train the baseline model.
6. Generate predictions.
7. Calculate evaluation metrics.
8. Analyze the baseline performance.

---

## 👩‍💻 Author

**Armi Sherathiya**

*AI/ML Engineer | Data Scientist*
