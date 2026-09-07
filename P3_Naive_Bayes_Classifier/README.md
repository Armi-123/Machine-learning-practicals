# P3 — Naïve Bayes Classifier and Accuracy

## 📌 Practical Information

| Field              | Details                                  |
| ------------------ | ---------------------------------------- |
| **Practical No.**  | P3                                       |
| **Practical Name** | Implementation of Naïve Bayes Classifier |
| **Course Outcome** | CO1                                      |
| **Hours**          | 8                                        |

---

## 🎯 Aim

To implement a **Naïve Bayes classifier** for the given dataset and compute the **accuracy of the classifier**.

---

## 📚 Objectives

The objectives of this practical are:

* Understand the concept of the Naïve Bayes classification algorithm.
* Load and preprocess the given dataset.
* Separate the dataset into features and target variables.
* Split the dataset into training and testing sets.
* Train a Naïve Bayes classifier.
* Make predictions on the test dataset.
* Calculate the accuracy of the classifier.
* Evaluate the performance of the classification model.

---

## 🛠️ Technologies Used

* **Python**
* **Jupyter Notebook**
* **Pandas**
* **NumPy**
* **Scikit-learn**

---

## 📂 Project Structure

```text
P3_Naive_Bayes_Classifier/
│
├── P3_Naive_Bayes_Classifier.ipynb
└── README.md
```

---

## 📊 Dataset

The practical uses a classification dataset containing input features and a target/class label.

The dataset is divided into:

* **Features (X)** — Input variables used for prediction.
* **Target (y)** — Class/category that the model needs to predict.

Example structure:

| Feature 1 | Feature 2 | Feature 3 | Target  |
| --------: | --------: | --------: | ------- |
|       5.1 |       3.5 |       1.4 | Class A |
|       6.2 |       2.8 |       4.8 | Class B |
|       7.1 |       3.0 |       5.9 | Class C |

> The actual dataset and target values depend on the dataset provided for the practical.

---

## 📦 Libraries Used

```python
import pandas as pd
import numpy as np

from sklearn.model_selection import train_test_split
from sklearn.naive_bayes import GaussianNB
from sklearn.metrics import accuracy_score
```

---

## 🔍 Data Preparation

The dataset is loaded using Pandas.

```python
df = pd.read_csv("dataset.csv")
```

The features and target variable are separated.

```python
X = df.drop("Target", axis=1)
y = df["Target"]
```

---

## ✂️ Train-Test Split

The dataset is divided into training and testing data.

```python
X_train, X_test, y_train, y_test = train_test_split(
    X,
    y,
    test_size=0.2,
    random_state=42
)
```

Here:

* **80%** of the data is used for training.
* **20%** of the data is used for testing.
* `random_state=42` ensures reproducible results.

---

## 🤖 Naïve Bayes Classifier

The **Gaussian Naïve Bayes** classifier is created using Scikit-learn.

```python
model = GaussianNB()
```

The model is trained using the training dataset.

```python
model.fit(X_train, y_train)
```

---

## 🔮 Prediction

The trained model is used to predict the classes of the test data.

```python
y_pred = model.predict(X_test)
```

The predicted values can then be compared with the actual target values.

---

## 📈 Accuracy Calculation

The accuracy of the classifier is calculated using `accuracy_score()`.

```python
accuracy = accuracy_score(y_test, y_pred)

print("Accuracy:", accuracy)
```

Accuracy can also be displayed as a percentage:

```python
print("Accuracy:", accuracy * 100, "%")
```

### Accuracy Formula

**Accuracy** represents the proportion of correctly classified observations out of all observations.

```text
Accuracy = Correct Predictions / Total Predictions
```

---

## 🧠 Naïve Bayes Concept

Naïve Bayes is a **probabilistic classification algorithm** based on Bayes' theorem.

It assumes that the input features are conditionally independent given the class.

The basic workflow is:

```text
Input Dataset
      ↓
Data Preprocessing
      ↓
Separate Features and Target
      ↓
Train-Test Split
      ↓
Train Naïve Bayes Model
      ↓
Predict Test Data
      ↓
Compare Actual vs Predicted
      ↓
Calculate Accuracy
```

---

## 🔄 Workflow

```text
Start
  ↓
Load Dataset
  ↓
Explore Dataset
  ↓
Preprocess Data
  ↓
Separate X and y
  ↓
Split Dataset
  ↓
Create Naïve Bayes Model
  ↓
Train Model
  ↓
Predict Test Data
  ↓
Calculate Accuracy
  ↓
Display Result
  ↓
End
```

---

## 📊 Model Evaluation

The classifier performance is evaluated by comparing:

* **Actual Class Labels**
* **Predicted Class Labels**

Example:

| Actual  | Predicted |
| ------- | --------- |
| Class A | Class A   |
| Class B | Class B   |
| Class C | Class B   |
| Class A | Class A   |

The number of correct predictions is used to calculate the classifier's accuracy.

---

## 🎓 Learning Outcomes

After completing this practical, the following concepts are understood:

* Understanding the Naïve Bayes classification algorithm.
* Understanding Bayes' theorem and probabilistic classification.
* Loading and preparing a dataset using Pandas.
* Splitting data into training and testing sets.
* Implementing `GaussianNB` using Scikit-learn.
* Making predictions using a trained classifier.
* Calculating classification accuracy.
* Evaluating the performance of a machine learning model.

---

## ✅ Result

The **Naïve Bayes classifier** was successfully implemented for the given dataset.

The model was trained using the training data, predictions were generated for the test data, and the **accuracy of the classifier was successfully calculated**.

---

## ⚙️ Requirements

Install the required libraries using:

```bash
pip install pandas numpy scikit-learn
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
P3_Naive_Bayes_Classifier/
```

and open:

```text
P3_Naive_Bayes_Classifier.ipynb
```

### Step 3: Execute the Notebook

Run all cells sequentially to:

1. Load the dataset.
2. Explore and preprocess the data.
3. Separate features and target.
4. Split the dataset.
5. Train the Naïve Bayes classifier.
6. Predict the test data.
7. Calculate and display the accuracy.

---

## 👩‍💻 Author

**Armi Sherathiya**

*AI/ML Engineer | Data Scientist*
