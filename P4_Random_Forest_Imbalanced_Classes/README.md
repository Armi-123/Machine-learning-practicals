# P4 — Random Forest Classifier for Imbalanced Classes

## 📌 Practical Information

| Field              | Details                                                                                  |
| ------------------ | ---------------------------------------------------------------------------------------- |
| **Practical No.**  | P4                                                                                       |
| **Practical Name** | Using Random Forest Classifier to Balance a Target Vector with Highly Imbalanced Classes |
| **Course Outcome** | CO1                                                                                      |
| **Hours**          | 8                                                                                        |

---

## 🎯 Aim

To use a **Random Forest classifier** to handle and balance a target vector containing **highly imbalanced classes** and evaluate the performance of the classifier.

---

## 📚 Objectives

The objectives of this practical are:

* Understand the concept of class imbalance in machine learning.
* Identify highly imbalanced classes in a target vector.
* Analyze the distribution of target classes.
* Apply a Random Forest classifier to the dataset.
* Handle class imbalance using appropriate Random Forest techniques.
* Train the classifier on the given dataset.
* Make predictions using the trained model.
* Evaluate the performance of the classifier.

---

## 🛠️ Technologies Used

* **Python**
* **Jupyter Notebook**
* **Pandas**
* **NumPy**
* **Scikit-learn**
* **Matplotlib**

---

## 📂 Project Structure

```text
P4_Random_Forest_Imbalanced_Classes/
│
├── P4_Random_Forest_Imbalanced_Classes.ipynb
└── README.md
```

---

## 📊 Dataset

The practical uses a classification dataset containing a **target vector with highly imbalanced classes**.

Class imbalance occurs when one class contains significantly more observations than another class.

### Example

| Class   | Number of Samples |
| ------- | ----------------: |
| Class 0 |               900 |
| Class 1 |               100 |

In this example, Class 0 is the **majority class**, while Class 1 is the **minority class**.

A machine learning model trained directly on such data may become biased toward the majority class.

---

## ⚖️ Understanding Class Imbalance

**Class imbalance** occurs when the number of observations in one class is significantly different from the number of observations in another class.

For example:

```text
Class 0: ██████████████████████████████████████████████████ 900
Class 1: █████ 100
```

The Random Forest classifier can be configured to give greater importance to minority classes using class weights.

---

## 📦 Libraries Used

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import accuracy_score, classification_report, confusion_matrix
```

---

## 🔍 Checking Class Distribution

The distribution of the target variable can be checked using:

```python
print(y.value_counts())
```

The percentage distribution can also be calculated:

```python
print(y.value_counts(normalize=True) * 100)
```

This helps identify whether the target vector contains highly imbalanced classes.

---

## 🌳 Random Forest Classifier

Random Forest is an ensemble machine learning algorithm that combines multiple decision trees to make predictions.

A Random Forest classifier can handle class imbalance by assigning different weights to different classes.

Example:

```python
model = RandomForestClassifier(
    n_estimators=100,
    class_weight="balanced",
    random_state=42
)
```

The parameter:

```python
class_weight="balanced"
```

automatically assigns higher weights to minority classes and lower weights to majority classes.

---

## ✂️ Train-Test Split

The dataset is divided into training and testing sets.

```python
X_train, X_test, y_train, y_test = train_test_split(
    X,
    y,
    test_size=0.2,
    random_state=42,
    stratify=y
)
```

The `stratify=y` parameter helps maintain a similar class distribution in both the training and testing datasets.

---

## 🤖 Training the Random Forest Model

The Random Forest classifier is trained using the training data.

```python
model.fit(X_train, y_train)
```

---

## 🔮 Prediction

The trained model is used to predict the target classes for the test dataset.

```python
y_pred = model.predict(X_test)
```

The predicted values can then be compared with the actual target values.

---

## 📈 Model Evaluation

### Accuracy

The accuracy of the classifier can be calculated using:

```python
accuracy = accuracy_score(y_test, y_pred)

print("Accuracy:", accuracy)
print("Accuracy:", accuracy * 100, "%")
```

### Classification Report

A classification report provides additional performance measures:

```python
print(classification_report(y_test, y_pred))
```

It includes:

* Precision
* Recall
* F1-score
* Support

### Confusion Matrix

The confusion matrix can be generated using:

```python
cm = confusion_matrix(y_test, y_pred)

print(cm)
```

---

## 🧠 Why Use `class_weight="balanced"`?

For highly imbalanced datasets, a model can favor the majority class.

Using:

```python
class_weight="balanced"
```

allows the Random Forest classifier to automatically adjust class weights according to their frequencies.

Conceptually:

```text
Majority Class
      ↓
Lower Weight
      ↓
Random Forest

Minority Class
      ↓
Higher Weight
      ↓
Random Forest
```

This helps the model pay more attention to minority-class observations.

---

## 🔄 Workflow

```text
Start
  ↓
Load Dataset
  ↓
Analyze Target Distribution
  ↓
Identify Imbalanced Classes
  ↓
Separate Features and Target
  ↓
Train-Test Split
  ↓
Create Random Forest Classifier
  ↓
Apply Balanced Class Weights
  ↓
Train Model
  ↓
Predict Test Data
  ↓
Evaluate Model
  ↓
Display Results
  ↓
End
```

---

## 📊 Model Performance

The Random Forest classifier is evaluated using multiple metrics rather than relying only on accuracy.

| Metric               | Purpose                                                            |
| -------------------- | ------------------------------------------------------------------ |
| **Accuracy**         | Measures overall correct predictions                               |
| **Precision**        | Measures how many predicted positive samples are actually positive |
| **Recall**           | Measures how many actual positive samples are correctly identified |
| **F1-Score**         | Provides a balance between precision and recall                    |
| **Confusion Matrix** | Shows correct and incorrect predictions for each class             |

For highly imbalanced datasets, **precision, recall, and F1-score** are particularly useful because accuracy alone may not fully represent model performance.

---

## 🎓 Learning Outcomes

After completing this practical, the following concepts are understood:

* Understanding class imbalance in machine learning.
* Identifying majority and minority classes.
* Understanding the Random Forest classification algorithm.
* Using `RandomForestClassifier` from Scikit-learn.
* Handling imbalanced classes using `class_weight="balanced"`.
* Splitting an imbalanced dataset using stratification.
* Making predictions using Random Forest.
* Evaluating classification performance using accuracy, precision, recall, F1-score, and confusion matrix.

---

## ✅ Result

The **Random Forest classifier** was successfully implemented for a dataset containing highly imbalanced classes.

The target class distribution was analyzed, balanced class weights were applied using the Random Forest classifier, predictions were generated, and the model performance was evaluated using appropriate classification metrics.

---

## ⚙️ Requirements

Install the required libraries using:

```bash
pip install pandas numpy scikit-learn matplotlib
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
P4_Random_Forest_Imbalanced_Classes/
```

and open:

```text
P4_Random_Forest_Imbalanced_Classes.ipynb
```

### Step 3: Execute the Notebook

Run all cells sequentially to:

1. Load the dataset.
2. Analyze the target class distribution.
3. Identify class imbalance.
4. Prepare features and target variables.
5. Split the dataset using stratification.
6. Create a Random Forest classifier.
7. Apply balanced class weights.
8. Train the model.
9. Generate predictions.
10. Evaluate the classifier.

---

## 👩‍💻 Author

**Armi Sherathiya**

*AI/ML Engineer | Data Scientist*
