# P8 — Removing Uninformative Features from a Dataset

## 📌 Practical Information

| Field              | Details                                                                       |
| ------------------ | ----------------------------------------------------------------------------- |
| **Practical No.**  | P8                                                                            |
| **Practical Name** | Remove Uninformative Features from a Dataset with a Categorical Target Vector |
| **Course Outcome** | CO1                                                                           |
| **Hours**          | 8                                                                             |

---

## 🎯 Aim

To identify and remove **uninformative or irrelevant features** from a dataset containing a **categorical target vector**, and retain only the features that are useful for machine learning.

---

## 📚 Objectives

The objectives of this practical are:

* Understand the concept of informative and uninformative features.
* Identify features that do not contribute useful information to a model.
* Understand categorical target variables.
* Remove unnecessary features from a dataset.
* Select relevant features for machine learning.
* Compare the dataset before and after feature removal.
* Prepare a cleaner dataset for further machine learning tasks.

---

## 🧠 Uninformative Features

An **uninformative feature** is a feature that provides little or no useful information for predicting the target variable.

Such features may include:

* Constant-value features
* Features with the same value for most observations
* Duplicate features
* Irrelevant attributes
* Features that do not provide useful information about the target

Removing such features can make the dataset simpler and may improve the efficiency of machine learning models.

---

## 🎯 Categorical Target Vector

A **categorical target vector** contains categories or class labels that the machine learning model is expected to predict.

For example:

```text
Pass
Fail
```

or:

```text
Yes
No
```

The target variable is kept separate from the input features during feature selection.

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
P8_Remove_Uninformative_Features/
│
├── P8_Remove_Uninformative_Features.ipynb
└── README.md
```

---

## 📊 Dataset

The practical uses student-related features and a categorical target vector.

Example input features include:

| Feature            | Description                    |
| ------------------ | ------------------------------ |
| **Previous_Marks** | Marks obtained previously      |
| **Attendance**     | Student attendance             |
| **Study_Hours**    | Number of hours spent studying |

The target vector represents a categorical outcome such as:

```text
Pass / Fail
```

The objective is to identify and remove features that are not useful for predicting the target.

---

## 📦 Libraries Used

```python
import pandas as pd
import numpy as np
```

Scikit-learn can also be used for feature-selection techniques when required:

```python
from sklearn.feature_selection import VarianceThreshold
```

---

## 🔍 Identifying Uninformative Features

One way to identify an uninformative numerical feature is to check its variance.

A feature with zero variance has the same value for every observation and therefore does not provide useful information for distinguishing between observations.

```python
selector = VarianceThreshold(threshold=0)

X_reduced = selector.fit_transform(X)
```

---

## 🗑️ Removing Uninformative Features

After identifying the unnecessary features, they can be removed from the DataFrame.

For example:

```python
df = df.drop(columns=["Uninformative_Feature"])
```

The remaining features are then used as input variables for the machine learning model.

---

## 📋 Example Feature Selection

### Before Feature Removal

```text
Previous_Marks
Attendance
Study_Hours
Student_ID
Constant_Feature
Target
```

If `Student_ID` or `Constant_Feature` does not provide useful predictive information, it can be removed.

### After Feature Removal

```text
Previous_Marks
Attendance
Study_Hours
Target
```

The resulting dataset contains the relevant input features and the categorical target vector.

---

## 🧠 Feature Selection Concept

The basic idea of the practical is:

```text
Original Dataset
       ↓
Identify Features
       ↓
Analyze Feature Information
       ↓
Identify Uninformative Features
       ↓
Remove Uninformative Features
       ↓
Retain Relevant Features
       ↓
Use for Machine Learning
```

---

## 🔄 Workflow

```text
Start
  ↓
Load Dataset
  ↓
Identify Features and Target
  ↓
Analyze Feature Values
  ↓
Check for Uninformative Features
  ↓
Remove Uninformative Features
  ↓
Retain Relevant Features
  ↓
Separate Target Vector
  ↓
Display Final Dataset
  ↓
End
```

---

## 📈 Before and After Feature Selection

### Before

The dataset may contain both useful and unnecessary features:

```text
Previous_Marks
Attendance
Study_Hours
Uninformative_Feature
Target
```

### After

The uninformative feature is removed:

```text
Previous_Marks
Attendance
Study_Hours
Target
```

This produces a cleaner feature set for further analysis and machine learning.

---

## 🎓 Learning Outcomes

After completing this practical, the following concepts are understood:

* Understanding feature selection.
* Understanding informative and uninformative features.
* Identifying irrelevant features.
* Understanding categorical target vectors.
* Removing unnecessary features from a dataset.
* Using Pandas for feature removal.
* Understanding variance-based feature selection.
* Preparing a clean dataset for machine learning.

---

## ✅ Result

The uninformative features were successfully identified and removed from the dataset.

The resulting dataset contains the relevant features:

```text
Previous_Marks
Attendance
Study_Hours
```

along with the **categorical target vector**, making the dataset more suitable for further machine learning operations.

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
P8_Remove_Uninformative_Features/
```

and open:

```text
P8_Remove_Uninformative_Features.ipynb
```

### Step 3: Execute the Notebook

Run all cells sequentially to:

1. Load the dataset.
2. Identify the feature columns.
3. Identify the categorical target vector.
4. Analyze the features.
5. Identify uninformative features.
6. Remove unnecessary features.
7. Display the final selected features.

---

## 👩‍💻 Author

**Armi Sherathiya**

*AI/ML Engineer | Data Scientist*
