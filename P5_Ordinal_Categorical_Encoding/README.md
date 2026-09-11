# P5 — Ordinal Categorical Encoding Using Pandas

## 📌 Practical Information

| Field              | Details                                                                               |
| ------------------ | ------------------------------------------------------------------------------------- |
| **Practical No.**  | P5                                                                                    |
| **Practical Name** | Transform String Labels into Numerical Equivalents Using Pandas DataFrame `replace()` |
| **Course Outcome** | CO1                                                                                   |
| **Hours**          | 8                                                                                     |

---

## 🎯 Aim

To transform **string labels of an ordinal categorical feature** into numerical equivalents using the Pandas DataFrame `replace()` method.

---

## 📚 Objectives

The objectives of this practical are:

* Understand categorical and ordinal features.
* Identify ordinal categories in a dataset.
* Understand the order and relationship between categorical values.
* Convert string labels into numerical values.
* Use the Pandas DataFrame `replace()` method for ordinal encoding.
* Prepare categorical data for machine learning algorithms.

---

## 🧠 Ordinal Categorical Feature

An **ordinal categorical feature** contains categories that have a meaningful order or ranking.

For example, a student's performance can be represented as:

```text
High > Medium > Low
```

These string labels can be converted into numerical values:

| String Label | Numerical Equivalent |
| ------------ | -------------------: |
| High         |                    3 |
| Medium       |                    2 |
| Low          |                    1 |

The numerical values preserve the original ordering of the categories.

---

## 🛠️ Technologies Used

* **Python**
* **Jupyter Notebook**
* **Pandas**

---

## 📂 Project Structure

```text
P5_Ordinal_Categorical_Encoding/
│
├── P5_Ordinal_Categorical_Encoding.ipynb
└── README.md
```

---

## 📊 Dataset

The practical uses a student dataset containing an ordinal categorical feature called **Performance**.

### Example Dataset

| Student | Performance |
| ------- | ----------- |
| Armi    | High        |
| Rahul   | Medium      |
| Priya   | Low         |
| Amit    | High        |
| Neha    | Medium      |
| Riya    | Low         |

Here, `Performance` is an **ordinal categorical feature** because the categories have a natural order:

```text
High > Medium > Low
```

---

## 📦 Library Used

The practical uses the Pandas library.

```python
import pandas as pd
```

---

## 🏗️ Creating the DataFrame

A Pandas DataFrame is created using the student data.

```python
df = pd.DataFrame({
    "Student": ["Armi", "Rahul", "Priya", "Amit", "Neha", "Riya"],
    "Performance": ["High", "Medium", "Low", "High", "Medium", "Low"]
})

print(df)
```

---

## 🔄 Converting String Labels to Numerical Values

The Pandas DataFrame `replace()` method is used to transform the ordinal string labels into numerical equivalents.

```python
df["Performance"] = df["Performance"].replace({
    "High": 3,
    "Medium": 2,
    "Low": 1
})
```

The resulting DataFrame becomes:

| Student | Performance |
| ------- | ----------: |
| Armi    |           3 |
| Rahul   |           2 |
| Priya   |           1 |
| Amit    |           3 |
| Neha    |           2 |
| Riya    |           1 |

---

## 🔍 Checking Data Types

The `dtypes` attribute can be used to verify the data types of the DataFrame columns.

```python
print(df.dtypes)
```

Expected output:

```text
Student        object
Performance     int64
dtype: object
```

The `Performance` column is now numerical.

---

## 🧠 Why Ordinal Encoding?

Machine learning algorithms generally work with numerical data. Therefore, categorical string labels can be converted into numerical values.

For an ordinal feature, the numerical values should preserve the category's natural order.

```text
High
 ↓
 3

Medium
 ↓
 2

Low
 ↓
 1
```

This allows the machine learning model to understand that:

```text
3 > 2 > 1
```

which represents:

```text
High > Medium > Low
```
---

## 🔄 Workflow

```text
Start
  ↓
Create Dataset
  ↓
Identify Ordinal Feature
  ↓
Define Category Order
  ↓
Use DataFrame replace() Method
  ↓
Convert String Labels to Numerical Values
  ↓
Check Data Types
  ↓
Display Encoded Data
  ↓
End
```
---

## 📈 Before and After Encoding

### Before Encoding

```text
Student    Performance
Armi       High
Rahul      Medium
Priya      Low
Amit       High
Neha       Medium
Riya       Low
```

### After Encoding

```text
Student    Performance
Armi       3
Rahul      2
Priya      1
Amit       3
Neha       2
Riya       1
```

---

## 🎓 Learning Outcomes

After completing this practical, the following concepts are understood:

* Understanding categorical features.
* Understanding ordinal categorical features.
* Identifying meaningful order among categories.
* Converting string labels into numerical equivalents.
* Using the Pandas DataFrame `replace()` method.
* Checking and understanding DataFrame data types.
* Preparing ordinal categorical data for machine learning models.

---

## ✅ Result

The ordinal categorical feature **Performance** was successfully transformed from string labels into numerical equivalents using the Pandas DataFrame `replace()` method.

The labels were encoded as:

```text
High   → 3
Medium → 2
Low    → 1
```
The encoded feature can now be used as numerical input for further machine learning operations.

---

## ⚙️ Requirements

Install Pandas using:

```bash
pip install pandas
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
P5_Ordinal_Categorical_Encoding/
```

and open:

```text
P5_Ordinal_Categorical_Encoding.ipynb
```

### Step 3: Execute the Notebook

Run all cells sequentially to:

1. Create the DataFrame.
2. Display the original categorical data.
3. Define the ordinal mapping.
4. Apply the `replace()` method.
5. Display the encoded data.
6. Check the resulting data types.

---

## 👩‍💻 Author

**Armi Sherathiya**

*AI/ML Engineer | Data Scientist*