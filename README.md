# Machine Learning Practicals

A collection of **10 Machine Learning practicals** implemented using Python, Jupyter Notebook, Pandas, NumPy, SciPy, and Scikit-learn.

This repository covers fundamental Machine Learning concepts including data handling, missing-value imputation, classification, ensemble learning, categorical encoding, dimensionality reduction, image-to-feature conversion, feature selection, sparse matrix reduction, and baseline regression.

---

## 📚 Course Information

| Field                    | Details          |
| ------------------------ | ---------------- |
| **Course**               | Machine Learning |
| **Program**              | M.Tech           |
| **Practical Count**      | 10               |
| **Programming Language** | Python           |
| **Environment**          | Jupyter Notebook |
| **Primary Library**      | Scikit-learn     |

---

## 🎯 Objectives

The main objectives of these practicals are:

* Understand fundamental Machine Learning concepts.
* Work with real and structured datasets.
* Perform data preprocessing and cleaning.
* Handle missing values using KNN.
* Implement classification algorithms.
* Understand imbalanced class problems.
* Perform categorical feature encoding.
* Apply dimensionality reduction techniques.
* Convert image data into numerical observations.
* Remove uninformative features.
* Reduce sparse feature matrix dimensions.
* Create baseline regression models.
* Evaluate Machine Learning models using appropriate metrics.

---

# 📂 Repository Structure

```text
ML_Practicals/
│
├── P1_Read_Write_CSV_Excel/
│   ├── P1_Read_Write_CSV_Excel.ipynb
│   ├──students.csv
│   ├──students.xlsx
│   └── README.md
│
├── P2_KNN_Missing_Values/
│   ├── P2_KNN_Missing_Values.ipynb
│   └── README.md
│
├── P3_Naive_Bayes_Classifier/
│   ├── P3_Naive_Bayes_Classifier.ipynb
│   └── README.md
│
├── P4_Random_Forest_Imbalanced_Classes/
│   ├── P4_Random_Forest_Imbalanced_Classes.ipynb
│   └── README.md
│
├── P5_Ordinal_Categorical_Encoding/
│   ├── P5_Ordinal_Categorical_Encoding.ipynb
│   └── README.md
│
├── P6_PCA_Dimensionality_Reduction/
│   ├── P6_PCA_Dimensionality_Reduction.ipynb
│   └── README.md
│
├── P7_Image_to_Observation/
│   ├── P7_Image_to_Observation.ipynb
│   └── README.md
│
├── P8_Remove_Uninformative_Features/
│   ├── P8_Remove_Uninformative_Features.ipynb
│   └── README.md
│
├── P9_Sparse_Matrix_Dimensionality_Reduction/
│   ├── P9_Sparse_Matrix_Dimensionality_Reduction.ipynb
│   └── README.md
│
├── P10_Dummy_Regressor_Baseline/
│   ├── P10_Dummy_Regressor_Baseline.ipynb
│   └── README.md
│
└── README.md
```

---

# 🧪 Practicals Overview

## P1 — Read and Write CSV & Excel Files

### Objective

To read and write **CSV and Excel files** using Python and Pandas.

### Concepts Covered

* Reading CSV files
* Writing CSV files
* Reading Excel files
* Writing Excel files
* DataFrame operations
* Pandas
* OpenPyXL

### Main Libraries

```python
import pandas as pd
```

### Technologies

* Python
* Jupyter Notebook
* Pandas
* OpenPyXL

---

## P2 — K-Nearest Neighbors for Missing Value Imputation

### Objective

To handle missing values in a dataset using **K-Nearest Neighbors (KNN) imputation**.

### Concepts Covered

* Missing values
* Data preprocessing
* KNN imputation
* Nearest neighbors
* Feature-based imputation

### Main Technique

```python
from sklearn.impute import KNNImputer

imputer = KNNImputer(n_neighbors=3)
```

### Technologies

* Python
* Pandas
* NumPy
* Scikit-learn

---

## P3 — Naïve Bayes Classifier

### Objective

To implement a **Naïve Bayes classification algorithm** and evaluate its accuracy.

### Concepts Covered

* Classification
* Training and testing data
* Gaussian Naïve Bayes
* Prediction
* Accuracy evaluation

### Main Algorithm

```python
from sklearn.naive_bayes import GaussianNB

model = GaussianNB()
model.fit(X_train, y_train)
```

### Evaluation

The model performance is evaluated using:

```python
from sklearn.metrics import accuracy_score

accuracy_score(y_test, y_pred)
```

### Technologies

* Python
* Pandas
* NumPy
* Scikit-learn

---

## P4 — Random Forest for Imbalanced Classes

### Objective

To implement a **Random Forest Classifier** for a dataset containing imbalanced classes.

### Concepts Covered

* Random Forest
* Ensemble learning
* Class imbalance
* Class weighting
* Classification report
* Confusion matrix

### Main Algorithm

```python
from sklearn.ensemble import RandomForestClassifier

model = RandomForestClassifier(
    n_estimators=100,
    class_weight="balanced",
    random_state=42
)
```

### Evaluation Metrics

* Accuracy
* Precision
* Recall
* F1-score
* Confusion Matrix

### Technologies

* Python
* Pandas
* NumPy
* Scikit-learn
* Matplotlib

---

## P5 — Ordinal Categorical Encoding

### Objective

To convert **ordinal categorical values** into numerical values.

### Example

```text
High   → 3
Medium → 2
Low    → 1
```

### Concepts Covered

* Categorical data
* Ordinal data
* Numerical encoding
* Pandas DataFrame
* Data preprocessing

### Example Code

```python
df["Performance"] = df["Performance"].replace({
    "High": 3,
    "Medium": 2,
    "Low": 1
})
```

### Technologies

* Python
* Pandas
* Jupyter Notebook

---

## P6 — PCA for Dimensionality Reduction

### Objective

To reduce the number of dimensions in a dataset using **Principal Component Analysis (PCA)**.

### Concepts Covered

* Dimensionality reduction
* Feature scaling
* Principal components
* Explained variance
* Data transformation

### Main Algorithm

```python
from sklearn.decomposition import PCA

pca = PCA(n_components=2)
X_pca = pca.fit_transform(X_scaled)
```

### Example

```text
Original Dimensions → 4
Reduced Dimensions  → 2
```

### Technologies

* Python
* Pandas
* NumPy
* Scikit-learn

---

## P7 — Image to Observation

### Objective

To convert an image into a **numerical observation/vector** that can be used as input for Machine Learning algorithms.

### Concepts Covered

* Image loading
* Image arrays
* Pixel values
* NumPy arrays
* Reshaping
* Feature representation

### Main Libraries

```python
import numpy as np
from PIL import Image
```

### Example

```python
image = Image.open("image.jpg")

image_array = np.array(image)

observation = image_array.reshape(1, -1)
```

### Concept

```text
Image
  ↓
Pixel Values
  ↓
NumPy Array
  ↓
Flatten / Reshape
  ↓
Machine Learning Observation
```

### Technologies

* Python
* NumPy
* Pillow
* Jupyter Notebook

---

## P8 — Removing Uninformative Features

### Objective

To identify and remove **uninformative or irrelevant features** from a dataset containing a categorical target vector.

### Example Features

```text
Previous_Marks
Attendance
Study_Hours
```

### Target

```text
Result
```

Example target categories:

```text
Pass
Fail
```

### Concepts Covered

* Feature selection
* Informative features
* Uninformative features
* Categorical target vector
* Variance-based feature selection
* Feature removal

### Main Technique

```python
from sklearn.feature_selection import VarianceThreshold

selector = VarianceThreshold(threshold=0)
X_selected = selector.fit_transform(X)
```

### Final Relevant Features

```text
Previous_Marks
Attendance
Study_Hours
```

### Technologies

* Python
* Pandas
* NumPy
* Scikit-learn

---

## P9 — Sparse Matrix Dimensionality Reduction

### Objective

To reduce the dimensionality of a **sparse feature matrix** while retaining important information.

### Concepts Covered

* Sparse matrices
* High-dimensional data
* Dimensionality reduction
* Truncated SVD
* Feature reduction
* Explained variance

### Creating a Sparse Matrix

```python
from scipy.sparse import csr_matrix

X = csr_matrix([
    [1, 0, 0, 0, 2],
    [0, 0, 3, 0, 0],
    [0, 4, 0, 0, 0],
    [0, 0, 0, 5, 0]
])
```

### Dimensionality Reduction

```python
from sklearn.decomposition import TruncatedSVD

svd = TruncatedSVD(
    n_components=2,
    random_state=42
)

X_reduced = svd.fit_transform(X)
```

### Example

```text
Original Shape → (4, 5)
Reduced Shape  → (4, 2)
```

### Technologies

* Python
* NumPy
* SciPy
* Scikit-learn

---

## P10 — DummyRegressor Baseline

### Objective

To create a simple **baseline regression model** using Scikit-learn's `DummyRegressor`.

### Concepts Covered

* Regression
* Baseline models
* DummyRegressor
* Mean prediction
* Model evaluation
* MAE
* MSE
* R² Score

### Main Algorithm

```python
from sklearn.dummy import DummyRegressor

dummy_model = DummyRegressor(strategy="mean")

dummy_model.fit(X_train, y_train)

y_pred = dummy_model.predict(X_test)
```

### Evaluation Metrics

```python
from sklearn.metrics import (
    mean_absolute_error,
    mean_squared_error,
    r2_score
)
```

The baseline can be used as a reference point for comparing more advanced regression models.

---

# 📊 Practical Summary

| Practical | Topic                     | Main Concept / Algorithm      |
| --------- | ------------------------- | ----------------------------- |
| **P1**    | Read & Write CSV/Excel    | Pandas, OpenPyXL              |
| **P2**    | Missing Value Imputation  | KNN Imputer                   |
| **P3**    | Classification            | Naïve Bayes                   |
| **P4**    | Imbalanced Classification | Random Forest                 |
| **P5**    | Categorical Encoding      | Ordinal Encoding              |
| **P6**    | Dimensionality Reduction  | PCA                           |
| **P7**    | Image Representation      | Image → Numerical Observation |
| **P8**    | Feature Selection         | VarianceThreshold             |
| **P9**    | Sparse Matrix Reduction   | Truncated SVD                 |
| **P10**   | Regression Baseline       | DummyRegressor                |

---

# 🧰 Technologies & Tools

The practicals use the following technologies:

### Programming Language

```text
Python
```

### Development Environment

```text
Jupyter Notebook
```

### Python Libraries

```text
Pandas
NumPy
SciPy
Scikit-learn
Matplotlib
Pillow
OpenPyXL
```

---

# 📦 Installation

Install the required libraries using:

```bash
pip install pandas numpy scipy scikit-learn matplotlib pillow openpyxl
```

To install Jupyter Notebook:

```bash
pip install notebook
```

---

# ▶️ How to Run the Practicals

### Step 1 — Clone the Repository

```bash
git clone https://github.com/Armi-123/Machine-learning-practicals.git
```

### Step 2 — Open the Repository

```bash
cd Machine-learning-practicals
```

### Step 3 — Start Jupyter Notebook

```bash
jupyter notebook
```

### Step 4 — Select a Practical

Open any practical folder:

```text
P1_Read_Write_CSV_Excel/
P2_KNN_Missing_Values/
P3_Naive_Bayes_Classifier/
...
P10_Dummy_Regressor_Baseline/
```

### Step 5 — Run the Notebook

Open the corresponding `.ipynb` file and execute the cells sequentially.

---

# 🔄 Overall Learning Workflow

The practicals collectively follow an important Machine Learning workflow:

```text
Data Handling
     ↓
Data Preprocessing
     ↓
Missing Value Handling
     ↓
Feature Encoding
     ↓
Feature Selection
     ↓
Dimensionality Reduction
     ↓
Machine Learning Algorithms
     ↓
Model Evaluation
     ↓
Baseline Comparison
```

---

# 🎓 Learning Outcomes

After completing all 10 practicals, the following Machine Learning concepts have been covered:

* Reading and writing structured data.
* Handling missing values.
* KNN-based data imputation.
* Naïve Bayes classification.
* Random Forest classification.
* Handling imbalanced classes.
* Ordinal categorical encoding.
* PCA-based dimensionality reduction.
* Image-to-numerical feature conversion.
* Removing uninformative features.
* Sparse matrix representation.
* Truncated SVD dimensionality reduction.
* Regression baseline creation.
* Model evaluation using appropriate metrics.

---

# 📌 Key Machine Learning Concepts Covered

```text
Data Handling
    ↓
Preprocessing
    ↓
Imputation
    ↓
Encoding
    ↓
Feature Selection
    ↓
Dimensionality Reduction
    ↓
Classification
    ↓
Regression
    ↓
Model Evaluation
    ↓
Baseline Modeling
```

---

# ✅ Conclusion

This repository contains **10 completed Machine Learning practicals** covering important concepts from data preprocessing to machine learning model development and evaluation.

The practicals provide hands-on experience with:

* Data preprocessing
* Classification
* Regression
* Feature engineering
* Feature selection
* Dimensionality reduction
* Sparse data processing
* Image data representation
* Model evaluation
* Baseline modeling

Each practical contains its own **Jupyter Notebook** and **README.md** with the objective, concepts, implementation details, and execution instructions.

---

## 👩‍💻 Author

**Armi Sherathiya**

*AI/ML Engineer | Data Scientist*

---

## ⭐ Repository

**Machine Learning Practicals**

```text
10 Practicals
10 Jupyter Notebooks
10 Practical READMEs
1 Complete Machine Learning Repository
```
