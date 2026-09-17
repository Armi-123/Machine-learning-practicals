# P6 — PCA for Dimensionality Reduction

## 📌 Practical Information

| Field              | Details                                                           |
| ------------------ | ----------------------------------------------------------------- |
| **Practical No.**  | P6                                                                |
| **Practical Name** | Dimensionality Reduction Using Principal Component Analysis (PCA) |
| **Course Outcome** | CO1                                                               |
| **Hours**          | 8                                                                 |

---

## 🎯 Aim

To use **Principal Component Analysis (PCA)** to reduce the dimensions of a dataset while preserving the important information present in the data.

---

## 📚 Objectives

The objectives of this practical are:

* Understand the concept of dimensionality reduction.
* Understand the working principle of Principal Component Analysis (PCA).
* Analyze the dimensions of a dataset.
* Apply PCA to reduce the number of features.
* Transform high-dimensional data into lower-dimensional data.
* Compare the original and reduced dimensions.
* Understand the importance of dimensionality reduction in machine learning.

---

## 🧠 Principal Component Analysis (PCA)

**Principal Component Analysis (PCA)** is a dimensionality reduction technique that transforms a dataset with many features into a smaller number of new features called **principal components**.

The principal components are created in such a way that they retain as much of the important variation in the original data as possible.

### Basic Concept

```text
Original Dataset
      ↓
Standardize Data
      ↓
Apply PCA
      ↓
Calculate Principal Components
      ↓
Select Required Components
      ↓
Reduced-Dimension Dataset
```

---

## ⚠️ Note About Linearly Inseparable Data

PCA is a **linear dimensionality-reduction technique**. It does not make linearly inseparable classes linearly separable by itself.

In this practical, PCA is used to **reduce the number of dimensions/features** of the data. If the data contains linearly inseparable classes, PCA may still provide a lower-dimensional representation, but it does not guarantee that the classes will become linearly separable.

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
P6_PCA_Dimensionality_Reduction/
│
├── P6_PCA_Dimensionality_Reduction.ipynb
└── README.md
```

---

## 📊 Dataset

The practical uses a dataset containing multiple numerical features.

For example, a dataset may initially contain **4 dimensions/features**:

| Feature 1 | Feature 2 | Feature 3 | Feature 4 |
| --------: | --------: | --------: | --------: |
|       2.5 |       2.4 |       1.2 |       0.8 |
|       0.5 |       0.7 |       1.8 |       1.1 |
|       2.2 |       2.9 |       2.0 |       1.5 |
|       1.9 |       2.2 |       1.5 |       1.0 |

PCA can transform these original features into a smaller number of principal components.

---

## 📦 Libraries Used

```python
import pandas as pd
import numpy as np

from sklearn.decomposition import PCA
from sklearn.preprocessing import StandardScaler
```

---

## 📏 Standardizing the Data

Before applying PCA, the features can be standardized so that features with different scales do not dominate the analysis.

```python
scaler = StandardScaler()

X_scaled = scaler.fit_transform(X)
```

---

## 🔽 Applying PCA

PCA can be used to reduce the dataset to a specified number of components.

For example, to reduce **4 dimensions to 2 dimensions**:

```python
pca = PCA(n_components=2)

X_pca = pca.fit_transform(X_scaled)
```

The transformed dataset now contains two principal components:

```text
Original Dimensions: 4
        ↓
       PCA
        ↓
Reduced Dimensions: 2
```

---

## 📊 Creating the Reduced DataFrame

The transformed data can be converted into a Pandas DataFrame.

```python
df_pca = pd.DataFrame(
    X_pca,
    columns=["PC1", "PC2"]
)

print(df_pca)
```

Here:

* **PC1** = First Principal Component
* **PC2** = Second Principal Component

---

## 📈 Explained Variance

PCA provides the amount of variance explained by each principal component.

```python
print(pca.explained_variance_ratio_)
```

The cumulative explained variance can be calculated using:

```python
print(pca.explained_variance_ratio_.cumsum())
```

A higher explained variance means that the selected components retain more information from the original dataset.

---

## 🔄 Before and After PCA

### Before PCA

The original dataset contains multiple dimensions:

```text
Feature 1
Feature 2
Feature 3
Feature 4
```

**Original Dimensions: 4**

### After PCA

The dataset is transformed into:

```text
PC1
PC2
```

**Reduced Dimensions: 2**

---

## 🧠 PCA Workflow

```text
Start
  ↓
Load Dataset
  ↓
Select Numerical Features
  ↓
Standardize Features
  ↓
Apply PCA
  ↓
Calculate Principal Components
  ↓
Select Required Components
  ↓
Transform Dataset
  ↓
Check Reduced Dimensions
  ↓
End
```

---

## 📊 Dimensionality Reduction

Dimensionality reduction reduces the number of features while attempting to preserve important information.

```text
Original Data
4 Features
    ↓
   PCA
    ↓
Reduced Data
2 Principal Components
```

This can make data easier to visualize and can reduce the computational complexity of subsequent machine learning tasks.

---

## 🎓 Learning Outcomes

After completing this practical, the following concepts are understood:

* Understanding dimensionality reduction.
* Understanding Principal Component Analysis (PCA).
* Understanding principal components.
* Standardizing data before PCA.
* Applying PCA using Scikit-learn.
* Reducing the number of dimensions/features.
* Calculating explained variance.
* Comparing original and reduced dimensions.
* Understanding the limitations of PCA for linearly inseparable data.

---

## ✅ Result

PCA was successfully applied to the given dataset to reduce its dimensionality.

The original dataset had **4 dimensions**, which were reduced to **2 principal components** while retaining important information from the original data.

The practical successfully demonstrates **dimensionality reduction using Principal Component Analysis (PCA)**.

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
P6_PCA_Dimensionality_Reduction/
```

and open:

```text
P6_PCA_Dimensionality_Reduction.ipynb
```

### Step 3: Execute the Notebook

Run all cells sequentially to:

1. Load the dataset.
2. Select the required features.
3. Standardize the data.
4. Apply PCA.
5. Reduce the dimensions.
6. Display the transformed data.
7. Check explained variance.
8. Compare the original and reduced dimensions.

---

## 👩‍💻 Author

**Armi Sherathiya**

*AI/ML Engineer | Data Scientist*
