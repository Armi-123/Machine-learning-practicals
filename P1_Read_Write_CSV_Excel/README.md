# P1 — Read and Write CSV & Excel Files

## 📌 Practical Information

| Field              | Details                                                                |
| ------------------ | ---------------------------------------------------------------------- |
| **Practical No.**  | P1                                                                     |
| **Practical Name** | Python Programming: Read and Write CSV File, Read and Write Excel File |
| **Course Outcome** | CO1                                                                    |
| **Hours**          | 8                                                                      |

---

## 🎯 Aim

To read and write data using **CSV and Excel files** with Python and Pandas.

---

## 📚 Objectives

The objectives of this practical are:

* Create and work with a Pandas DataFrame.
* Write DataFrame data into a CSV file.
* Read data from a CSV file.
* Write DataFrame data into an Excel file.
* Read data from an Excel file.
* Understand basic file handling using Pandas.

---

## 🛠️ Technologies Used

* **Python**
* **Jupyter Notebook**
* **Pandas**
* **OpenPyXL**

---

## 📂 Project Structure

```text
P1_Read_Write_CSV_Excel/
│
├── P1_Read_Write_CSV_Excel.ipynb
├── students.csv
├── students.xlsx
└── README.md
```

---

## 📊 Dataset

The practical uses a simple student dataset containing the following columns:

| Name  | Age | Marks |
| ----- | --: | ----: |
| Armi  |  21 |    85 |
| Rahul |  22 |    78 |
| Priya |  21 |    92 |
| Amit  |  23 |    88 |
| Neha  |  22 |    95 |

### Dataset Columns

* **Name** — Name of the student
* **Age** — Age of the student
* **Marks** — Marks obtained by the student

---

## 📦 Libraries Used

The practical uses the **Pandas** library for data handling.

```python
import pandas as pd
```

For Excel file operations, **OpenPyXL** is used as the Excel engine.

---

## 📄 CSV File Operations

### 1. Write Data to CSV

The DataFrame is written to a CSV file using `to_csv()`.

```python
df.to_csv("students.csv", index=False)
```

The `index=False` parameter prevents Pandas from writing the DataFrame index as an additional column.

### 2. Read Data from CSV

The CSV file is read using `read_csv()`.

```python
df_csv = pd.read_csv("students.csv")
print(df_csv)
```

---

## 📊 Excel File Operations

### 1. Write Data to Excel

The DataFrame is written to an Excel file using `to_excel()`.

```python
df.to_excel("students.xlsx", index=False)
```

### 2. Read Data from Excel

The Excel file is read using `read_excel()`.

```python
df_excel = pd.read_excel("students.xlsx")
print(df_excel)
```

---

## 🔄 Workflow

```text
Create DataFrame
       ↓
Write Data to CSV
       ↓
Read CSV File
       ↓
Write Data to Excel
       ↓
Read Excel File
       ↓
Display Data
```

---

## 🎓 Learning Outcomes

After completing this practical, the following concepts are understood:

* Creating a DataFrame using Pandas
* Reading CSV files
* Writing CSV files
* Reading Excel files
* Writing Excel files
* Basic dataset handling using Python
* Basic file handling using Pandas

---

## ✅ Result

The CSV and Excel files were successfully **created, written, and read** using Python and Pandas.

This practical successfully demonstrates the basic operations required for **CSV and Excel file handling using Python**.

---

## ⚙️ Requirements

Install the required Python libraries using:

```bash
pip install pandas openpyxl
```

---

## ▶️ How to Run

### Step 1: Open Jupyter Notebook

Run the following command in the terminal:

```bash
jupyter notebook
```

### Step 2: Open the Practical

Navigate to:

```text
P1_Read_Write_CSV_Excel/
```

and open:

```text
P1_Read_Write_CSV_Excel.ipynb
```

### Step 3: Execute the Notebook

Run the notebook cells sequentially to execute the practical and perform the CSV and Excel file operations.

---

## 👩‍💻 Author

**Armi Sherathiya**

*AI/ML Engineer | Data Scientist*
