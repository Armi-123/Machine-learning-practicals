# P9 — Dimensionality Reduction of Sparse Feature Matrix

## 📌 Practical Information

| Field              | Details                                              |
| ------------------ | ---------------------------------------------------- |
| **Practical No.**  | P9                                                   |
| **Practical Name** | Reducing the Dimensionality of Sparse Feature Matrix |
| **Course Outcome** | CO1                                                  |
| **Hours**          | 8                                                    |

---

## 🎯 Aim

To reduce the dimensionality of a **sparse feature matrix** using dimensionality reduction techniques while preserving the important information in the data.

---

## 📚 Objectives

The objectives of this practical are:

* Understand the concept of sparse feature matrices.
* Understand dimensionality reduction.
* Create a sparse feature matrix.
* Apply a dimensionality reduction technique.
* Reduce the number of features while preserving important information.
* Convert high-dimensional sparse data into a lower-dimensional representation.
* Understand the importance of dimensionality reduction in machine learning.

---

## 🧠 Sparse Feature Matrix

A **sparse feature matrix** is a matrix in which most of the values are zero.

For example:

```text
[[1, 0, 0, 0, 2],
 [0, 0, 3, 0, 0],
 [0, 4, 0, 0, 0],
 [0, 0, 0, 5, 0]]
```

In this matrix, most elements are `0`, so it is called a **sparse matrix**.

Sparse matrices are commonly used in:

* Text classification
* Natural Language Processing (NLP)
* Document-term matrices
* Recommendation systems
* One-hot encoded data
* High-dimensional machine learning datasets

---

## 📉 Dimensionality Reduction

**Dimensionality reduction** is the process of reducing the number of features in a dataset while retaining as much useful information as possible.

For example:

```text
Original Feature Matrix
        ↓
1000 Features
        ↓
Dimensionality Reduction
        ↓
50 Features
```

Reducing the number of features can:

* Reduce computational cost
* Reduce memory usage
* Remove redundant information
* Improve model efficiency
* Make high-dimensional data easier to analyze

---

## 🛠️ Technologies Used

* **Python**
* **Jupyter Notebook**
* **NumPy**
* **SciPy**
* **Scikit-learn**

---

## 📂 Project Structure

```text
P9_Sparse_Matrix_Dimensionality_Reduction/
│
├── P9_Sparse_Matrix_Dimensionality_Reduction.ipynb
└── README.md
```

---

## 📊 Sparse Feature Matrix

A sparse matrix can be created using SciPy.

Example:

```python
from scipy.sparse import csr_matrix

X = csr_matrix([
    [1, 0, 0, 0, 2],
    [0, 0, 3, 0, 0],
    [0, 4, 0, 0, 0],
    [0, 0, 0, 5, 0]
])

print(X)
```

The `csr_matrix` stores the non-zero elements efficiently instead of storing every zero value.

---

## 🔍 Converting Sparse Matrix to Dense Form

The sparse matrix can be displayed in normal matrix form using:

```python
print(X.toarray())
```

Output:

```text
[[1 0 0 0 2]
 [0 0 3 0 0]
 [0 4 0 0 0]
 [0 0 0 5 0]]
```

---

## 📉 Dimensionality Reduction Using Truncated SVD

For sparse feature matrices, **Truncated Singular Value Decomposition (Truncated SVD)** is a suitable dimensionality reduction technique.

It can work directly with sparse matrices without requiring the complete matrix to be converted into a dense matrix.

```python
from sklearn.decomposition import TruncatedSVD

svd = TruncatedSVD(n_components=2, random_state=42)

X_reduced = svd.fit_transform(X)

print("Reduced Matrix:")
print(X_reduced)
```

---

## 📏 Checking Dimensions

The dimensions before and after reduction can be checked using:

```python
print("Original Shape:", X.shape)
print("Reduced Shape:", X_reduced.shape)
```

Example:

```text
Original Shape: (4, 5)
Reduced Shape: (4, 2)
```

This shows that the original **5-dimensional feature space** has been reduced to **2 dimensions**.

---

## 📊 Explained Variance

Truncated SVD provides information about how much variance is captured by the selected components.

```python
print("Explained Variance Ratio:")
print(svd.explained_variance_ratio_)

print("Total Explained Variance:")
print(svd.explained_variance_ratio_.sum())
```

The explained variance ratio helps determine how much information is retained by the reduced representation.

---

## 🧪 Complete Code Example

```python
# P9 - Sparse Matrix Dimensionality Reduction

import numpy as np
from scipy.sparse import csr_matrix
from sklearn.decomposition import TruncatedSVD

# Create a sparse feature matrix
X = csr_matrix([
    [1, 0, 0, 0, 2],
    [0, 0, 3, 0, 0],
    [0, 4, 0, 0, 0],
    [0, 0, 0, 5, 0]
])

print("Original Sparse Matrix:")
print(X)

print("\nDense Representation:")
print(X.toarray())

# Apply Truncated SVD
svd = TruncatedSVD(
    n_components=2,
    random_state=42
)

X_reduced = svd.fit_transform(X)

# Display reduced matrix
print("\nReduced Matrix:")
print(X_reduced)

# Display dimensions
print("\nOriginal Shape:")
print(X.shape)

print("\nReduced Shape:")
print(X_reduced.shape)

# Display explained variance
print("\nExplained Variance Ratio:")
print(svd.explained_variance_ratio_)

print("\nTotal Explained Variance:")
print(svd.explained_variance_ratio_.sum())
```

---

## 🔄 Workflow

```text
Start
  ↓
Create Sparse Feature Matrix
  ↓
Check Matrix Dimensions
  ↓
Apply Truncated SVD
  ↓
Select Number of Components
  ↓
Transform Sparse Matrix
  ↓
Obtain Reduced Feature Matrix
  ↓
Compare Original and Reduced Dimensions
  ↓
Analyze Explained Variance
  ↓
End
```

---

## 📐 Dimensionality Reduction Example

### Before Reduction

```text
Number of Samples = 4
Number of Features = 5

Shape = (4, 5)
```

### After Reduction

```text
Number of Samples = 4
Number of Components = 2

Shape = (4, 2)
```

Therefore:

```text
5 Features
    ↓
Truncated SVD
    ↓
2 Components
```

---

## 💡 Why Truncated SVD?

Truncated SVD is useful for sparse data because:

* It works efficiently with sparse matrices.
* It does not require converting the entire sparse matrix into a dense matrix.
* It can reduce a large number of features.
* It is commonly used for text and NLP data.
* It produces a lower-dimensional representation of the original data.

---

## 🎓 Learning Outcomes

After completing this practical, the following concepts are understood:

* Understanding sparse matrices.
* Understanding high-dimensional feature spaces.
* Understanding dimensionality reduction.
* Creating sparse matrices using SciPy.
* Applying Truncated SVD.
* Reducing the number of features.
* Comparing original and reduced dimensions.
* Understanding explained variance.
* Preparing high-dimensional sparse data for machine learning.

---

## ✅ Result

The dimensionality of the sparse feature matrix was successfully reduced using **Truncated SVD**.

The original sparse feature matrix:

```text
Shape = (4, 5)
```

was reduced to:

```text
Shape = (4, 2)
```

while retaining important information through the selected SVD components.

---

## ⚙️ Requirements

Install the required libraries using:

```bash
pip install numpy scipy scikit-learn
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
P9_Sparse_Matrix_Dimensionality_Reduction/
```

and open:

```text
P9_Sparse_Matrix_Dimensionality_Reduction.ipynb
```

### Step 3: Execute the Notebook

Run all cells sequentially to:

1. Create the sparse feature matrix.
2. Display the sparse matrix.
3. Apply Truncated SVD.
4. Reduce the dimensionality.
5. Display the reduced matrix.
6. Compare original and reduced dimensions.
7. Check explained variance.

---

## 👩‍💻 Author

**Armi Sherathiya**

*AI/ML Engineer | Data Scientist*
