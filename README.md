# Machine Learning Practicals

A complete collection of **10 Machine Learning practicals** implemented using **Python, Pandas, NumPy, and Scikit-learn**.

This repository covers fundamental Machine Learning concepts including data handling, missing-value imputation, classification, imbalanced datasets, categorical encoding, dimensionality reduction, image processing, feature selection, sparse matrices, and baseline regression models.

---

## 📌 Repository Overview

This repository contains practical implementations completed as part of the **Machine Learning practical syllabus**.

The practicals are implemented using **Jupyter Notebook (`.ipynb`)** and are organized separately for easy understanding and execution.

---

## 🛠️ Technologies & Libraries

- **Python**
- **Jupyter Notebook**
- **Pandas**
- **NumPy**
- **Scikit-learn**
- **Matplotlib**

---

## 📚 Practicals Covered

| Practical | Topic | Main Concept / Algorithm |
|-----------|-------|--------------------------|
| P1 | Read & Write CSV and Excel | Pandas |
| P2 | KNN Missing Values | K-Nearest Neighbors |
| P3 | Naive Bayes Classifier | Gaussian Naive Bayes |
| P4 | Random Forest – Imbalanced Classes | Random Forest + Class Balancing |
| P5 | Ordinal Categorical Encoding | Pandas `replace()` |
| P6 | PCA Dimensionality Reduction | Principal Component Analysis |
| P7 | Image to Observation | Image Pixel Processing |
| P8 | Remove Uninformative Features | Mutual Information |
| P9 | Sparse Matrix Dimensionality Reduction | Sparse Matrix / Dimensionality Reduction |
| P10 | Dummy Regressor Baseline | DummyRegressor |

---

# 📂 Project Structure

```text
ML_Practicals/
│
├── P1_Read_Write_CSV_Excel/
│   └── P1_Read_Write_CSV_Excel.ipynb
│
├── P2_KNN_Missing_Values/
│   └── P2_KNN_Missing_Values.ipynb
│
├── P3_Naive_Bayes_Classifier/
│   └── P3_Naive_Bayes_Classifier.ipynb
│
├── P4_Random_Forest_Imbalanced_Classes/
│   └── P4_Random_Forest_Imbalanced_Classes.ipynb
│
├── P5_Ordinal_Categorical_Encoding/
│   └── P5_Ordinal_Categorical_Encoding.ipynb
│
├── P6_PCA_Dimensionality_Reduction/
│   └── P6_PCA_Dimensionality_Reduction.ipynb
│
├── P7_Image_to_Observation/
│   └── P7_Image_to_Observation.ipynb
│
├── P8_Remove_Uninformative_Features/
│   └── P8_Remove_Uninformative_Features.ipynb
│
├── P9_Sparse_Matrix_Dimensionality_Reduction/
│   └── P9_Sparse_Matrix_Dimensionality_Reduction.ipynb
│
└── P10_Dummy_Regressor_Baseline/
    └── P10_Dummy_Regressor_Baseline.ipynb


🧪 Practical Details
P1 — Read & Write CSV and Excel
Objective

Read and write data using CSV and Excel files.

Concepts Covered
Creating a Pandas DataFrame
Writing DataFrame to CSV
Reading CSV files
Writing DataFrame to Excel
Reading Excel files
Libraries
import pandas as pd
P2 — KNN Missing Values
Objective

Use K-Nearest Neighbors (KNN) to fill or predict missing values in a dataset.

Concepts Covered
Missing values
KNN imputation
Data preprocessing
Numerical data handling
Main Algorithm

K-Nearest Neighbors

Library
from sklearn.impute import KNNImputer
P3 — Naive Bayes Classifier
Objective

Implement a Naive Bayes classifier and calculate its accuracy.

Algorithm Used

Gaussian Naive Bayes

Main Concepts
Classification
Training and testing data
Model prediction
Accuracy calculation
Main Code
from sklearn.naive_bayes import GaussianNB

model = GaussianNB()
model.fit(X_train, y_train)
y_pred = model.predict(X_test)

Accuracy is calculated using:

from sklearn.metrics import accuracy_score

accuracy_score(y_test, y_pred)
P4 — Random Forest for Imbalanced Classes
Objective

Use a Random Forest classifier to handle a highly imbalanced target vector.

Algorithm Used

Random Forest Classifier

Important Parameter
class_weight="balanced"

This gives greater importance to minority classes.

Main Code
from sklearn.ensemble import RandomForestClassifier

model = RandomForestClassifier(
    n_estimators=100,
    class_weight="balanced",
    random_state=42
)

P5 — Ordinal Categorical Encoding
Objective

Convert ordinal categorical string labels into numerical equivalents using Pandas replace().

Example
Low       → 1
Medium    → 2
High      → 3
Main Code
mapping = {
    "Low": 1,
    "Medium": 2,
    "High": 3
}

df["Performance"] = df["Performance"].replace(mapping)
Concept

Ordinal Encoding

The categories have a meaningful order:

Low < Medium < High
P6 — PCA Dimensionality Reduction
Objective

Reduce the dimensions of a dataset using Principal Component Analysis (PCA).

Concepts Covered
Feature scaling
Standardization
Dimensionality reduction
Principal components
Explained variance
Example
Original Dimensions → 4
Reduced Dimensions  → 2
Main Code
from sklearn.preprocessing import StandardScaler
from sklearn.decomposition import PCA

scaler = StandardScaler()
X_scaled = scaler.fit_transform(X)

pca = PCA(n_components=2)
X_pca = pca.fit_transform(X_scaled)
P7 — Convert Image into an Observation
Objective

Convert an image into a numerical observation that can be used as input for Machine Learning.

Concepts Covered
Image representation
Pixel values
Grayscale images
Flattening
Normalization
Machine Learning input format
Example

A:

5 × 5 image

contains:

25 pixels

After flattening:

1 observation × 25 features
Main Code
observation = image.flatten()

Normalize pixel values:

normalized_observation = observation / 255.0

Convert into ML input:

X = normalized_observation.reshape(1, -1)
P8 — Remove Uninformative Features
Objective

Identify and remove uninformative features from a dataset with a categorical target vector.

Technique Used

Mutual Information

Mutual information measures how much information a feature provides about the target variable.

Main Function
from sklearn.feature_selection import mutual_info_classif
Main Code
mi_scores = mutual_info_classif(
    X,
    y,
    random_state=42
)

Features with very low information scores can be removed.

Workflow
Dataset
   ↓
Categorical Target
   ↓
Calculate Mutual Information
   ↓
Identify Uninformative Features
   ↓
Remove Features
   ↓
Final Dataset
P9 — Sparse Matrix Dimensionality Reduction
Objective

Perform dimensionality reduction on sparse data while preserving the efficiency of sparse matrix representation.

Concepts Covered
Sparse matrices
High-dimensional data
Dimensionality reduction
Efficient data representation
Important Concept

Sparse matrices contain many zero values.

Instead of storing every zero, sparse matrix representations store mainly the non-zero values, which can save memory.

P10 — Dummy Regressor Baseline
Objective

Create a simple baseline regression model using Scikit-learn's DummyRegressor.

Model Used

DummyRegressor

A DummyRegressor provides a simple baseline against which more advanced regression models can be compared.

Main Code
from sklearn.dummy import DummyRegressor

model = DummyRegressor(strategy="mean")
model.fit(X_train, y_train)

y_pred = model.predict(X_test)
Concept

A baseline model provides a reference performance.

If a machine learning model cannot perform better than the baseline, the model may not be learning useful patterns from the data.

🔑 Key Machine Learning Concepts Covered

This repository covers several important Machine Learning concepts:

Data Handling
CSV
Excel
Pandas DataFrame
Data Preprocessing
Missing-value imputation
Ordinal encoding
Feature selection
Feature scaling
Classification
KNN
Naive Bayes
Random Forest
Dimensionality Reduction
PCA
Sparse matrix dimensionality reduction
Image Processing
Pixel representation
Image flattening
Normalization
Feature Selection
Mutual Information
Removing uninformative features
Regression
DummyRegressor
Baseline model
⚙️ Installation

Clone the repository:

git clone https://github.com/YOUR-USERNAME/machine-learning-practicals.git

Move into the project directory:

cd machine-learning-practicals

Install the required libraries:

pip install pandas numpy scikit-learn matplotlib openpyxl jupyter
▶️ How to Run

Start Jupyter Notebook:

jupyter notebook

Then open any practical notebook:

P1_Read_Write_CSV_Excel/
P2_KNN_Missing_Values/
P3_Naive_Bayes_Classifier/
...
P10_Dummy_Regressor_Baseline/

Run the notebook cells sequentially.

📊 Practical Learning Flow

The practicals are arranged to gradually cover important Machine Learning preprocessing and modeling concepts:

Data Handling
     ↓
Missing Value Handling
     ↓
Classification
     ↓
Imbalanced Data
     ↓
Categorical Encoding
     ↓
Dimensionality Reduction
     ↓
Image → Numerical Data
     ↓
Feature Selection
     ↓
Sparse Data
     ↓
Regression Baseline
🎯 Learning Outcomes

After completing these practicals, you will have hands-on experience with:

Reading and writing datasets using Pandas
Handling missing values using KNN
Building classification models
Using Naive Bayes
Using Random Forest
Handling imbalanced classes
Encoding ordinal categorical variables
Applying PCA
Converting images into ML observations
Selecting informative features
Working with sparse matrices
Creating baseline regression models
Evaluating Machine Learning models
📦 Requirements

Recommended environment:

Python 3.x
Jupyter Notebook
Pandas
NumPy
Scikit-learn
Matplotlib
OpenPyXL
📌 Notes
Each practical is maintained in a separate Jupyter Notebook.
Most practical datasets are created directly inside the notebooks for easy execution.
The examples are designed for educational and practical-learning purposes.
Results may vary slightly depending on dataset splits, random states, and library versions.
🚀 Future Improvements

Possible future additions to this repository:

More Machine Learning algorithms
Hyperparameter tuning
Cross-validation
Model comparison
Confusion matrix visualization
ROC-AUC evaluation
Regression models
Ensemble learning
Real-world datasets
End-to-end Machine Learning projects
👩‍💻 Author

Armi Sherathiya

AI/ML Engineer | Data Scientist

Skills:

Python
Machine Learning
Generative AI
SQL
Data Science
⭐ Acknowledgement

This repository was created as part of Machine Learning practical learning and experimentation using Python and Scikit-learn.

📜 License

This project is intended for educational and learning purposes.


### One small recommendation before pushing 🚀

Since this is your **college ML practical repository**, I would keep the README exactly this way but change:

```text
Armi Sherathiya
