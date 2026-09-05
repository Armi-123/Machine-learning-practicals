# P2 — K-Nearest Neighbors (KNN) for Missing Value Imputation

## 📌 Practical Information

| Field              | Details                                                           |
| ------------------ | ----------------------------------------------------------------- |
| **Practical No.**  | P2                                                                |
| **Practical Name** | Using K-Nearest Neighbors (KNN) to Fill or Predict Missing Values |
| **Course Outcome** | CO1                                                               |
| **Hours**          | 8                                                                 |

---

## 🎯 Aim

To use the **K-Nearest Neighbors (KNN)** algorithm to fill or predict missing values in a dataset.

---

## 📚 Objectives

The objectives of this practical are:

* Understand missing values in datasets.
* Identify missing values using Pandas.
* Preprocess data containing missing values.
* Understand the working of the KNN algorithm.
* Use KNN to predict missing values.
* Compare the dataset before and after missing-value imputation.
* Improve data quality for further machine learning tasks.

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
P2_KNN_Missing_Values/
│
├── P2_KNN_Missing_Values.ipynb
└── README.md
```

---

## 📊 Dataset

This practical uses a dataset containing numerical features with some **missing values (`NaN`)**.

The dataset is analyzed to identify missing values and then the **K-Nearest Neighbors (KNN)** algorithm is used to estimate suitable values for the missing entries.

### Example

| Feature 1 | Feature 2 | Feature 3 |
| --------: | --------: | --------: |
|        10 |        20 |        30 |
|        15 |       NaN |        35 |
|        20 |        25 |        40 |
|       NaN |        30 |        45 |
|        25 |        35 |        50 |

The missing values are predicted using information from nearby observations.

---

## 📦 Libraries Used

```python
import pandas as pd
import numpy as np

from sklearn.impute import KNNImputer
```

---

## 🔍 Identifying Missing Values

Pandas is used to check for missing values in the dataset.

```python
df.isnull().sum()
```

This displays the number of missing values present in each column.

---

## 🤖 KNN Imputation

The `KNNImputer` class from Scikit-learn is used to estimate missing values based on the nearest observations.

```python
imputer = KNNImputer(n_neighbors=3)

df_imputed = imputer.fit_transform(df)
```

The value of:

```python
n_neighbors=3
```

means that the algorithm considers the **3 nearest neighbors** when estimating a missing value.

---

## 🔄 Converting the Result Back to DataFrame

After imputation, the resulting NumPy array can be converted back into a Pandas DataFrame.

```python
df_imputed = pd.DataFrame(
    df_imputed,
    columns=df.columns
)

print(df_imputed)
```

---

## 🧠 How KNN Imputation Works

KNN imputation follows these basic steps:

```text
Load Dataset
     ↓
Identify Missing Values
     ↓
Select K Nearest Neighbors
     ↓
Calculate Values from Neighbors
     ↓
Predict Missing Value
     ↓
Create Complete Dataset
```

For each missing value, KNN searches for observations that are most similar to the available values and uses them to estimate the missing value.

---

## 📈 Before and After Imputation

### Before Imputation

The dataset contains missing values:

```text
Feature 1    Feature 2    Feature 3
10           20           30
15           NaN          35
20           25           40
NaN          30           45
25           35           50
```

### After KNN Imputation

The missing values are replaced with estimated values based on neighboring observations.

```text
Feature 1    Feature 2    Feature 3
10           20           30
15           XX           35
20           25           40
XX           30           45
25           35           50
```

> **Note:** The actual imputed values depend on the dataset and the selected number of neighbors.

---

## ⚙️ Important Parameter

### `n_neighbors`

The `n_neighbors` parameter determines how many neighboring observations are considered for predicting a missing value.

Example:

```python
KNNImputer(n_neighbors=3)
```

A suitable value of `K` should be selected according to the dataset.

---

## 🔄 Workflow

```text
Start
  ↓
Load Dataset
  ↓
Check Missing Values
  ↓
Analyze Dataset
  ↓
Apply KNN Imputer
  ↓
Predict Missing Values
  ↓
Create Imputed DataFrame
  ↓
Verify Missing Values
  ↓
Display Final Dataset
  ↓
End
```

---

## 🎓 Learning Outcomes

After completing this practical, the following concepts are understood:

* Understanding missing values in datasets.
* Detecting missing values using Pandas.
* Understanding the KNN algorithm.
* Using `KNNImputer` from Scikit-learn.
* Predicting missing values using neighboring observations.
* Performing basic data preprocessing.
* Preparing a dataset for further machine learning tasks.

---

## ✅ Result

The missing values in the dataset were successfully **identified and filled using the K-Nearest Neighbors (KNN) imputation technique**.

The resulting dataset contains fewer or no missing values and can be used for further data analysis and machine learning tasks.

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
P2_KNN_Missing_Values/
```

and open:

```text
P2_KNN_Missing_Values.ipynb
```

### Step 3: Execute the Notebook

Run all cells sequentially to:

1. Load the dataset.
2. Identify missing values.
3. Apply KNN imputation.
4. Predict missing values.
5. Verify the completed dataset.

---

## 👩‍💻 Author

**Armi Sherathiya**

*AI/ML Engineer | Data Scientist*