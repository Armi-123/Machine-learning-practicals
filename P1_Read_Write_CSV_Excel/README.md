# P1 — Read and Write CSV & Excel Files

## Practical Information

| Field | Details |
|---|---|
| Practical No. | P1 |
| Practical Name | Python Programming: Read and Write CSV File, Read and Write Excel File |
| Hours | 8 |
| CO | CO1 |

## Aim

To read and write data using CSV and Excel files with Python and Pandas.

## Objectives

- Create and work with a Pandas DataFrame.
- Write DataFrame data into a CSV file.
- Read data from a CSV file.
- Write DataFrame data into an Excel file.
- Read data from an Excel file.
- Understand basic file handling using Pandas.

## Technologies Used

- Python
- Jupyter Notebook
- Pandas
- OpenPyXL

## Project Structure

```text
P1_Read_Write_CSV_Excel/
│
├── P1_Read_Write_CSV_Excel.ipynb
├── students.csv
├── students.xlsx
└── README.md


Dataset

The practical uses student data containing the following columns:

Name	Age	Marks
Armi	21	85
Rahul	22	78
Priya	21	92
Amit	23	88
Neha	22	95
Libraries Used
import pandas as pd
CSV File Operations
Write Data to CSV
df.to_csv("students.csv", index=False)
Read Data from CSV
df_csv = pd.read_csv("students.csv")
print(df_csv)
Excel File Operations
Write Data to Excel
df.to_excel("students.xlsx", index=False)
Read Data from Excel
df_excel = pd.read_excel("students.xlsx")
print(df_excel)
Workflow
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
Learning Outcomes

After completing this practical, the following concepts are understood:

Creating a DataFrame using Pandas
Reading CSV files
Writing CSV files
Reading Excel files
Writing Excel files
Basic dataset handling using Python
Result

The CSV and Excel files were successfully created, written, and read using Python and Pandas.

The practical successfully demonstrates basic CSV and Excel file handling.

Requirements

Install the required libraries using:

pip install pandas openpyxl
How to Run

Open the Jupyter Notebook:

jupyter notebook

Then open:

P1_Read_Write_CSV_Excel.ipynb

Run the cells sequentially to execute the practical.

Author

Armi Sherathiya

AI/ML Engineer | Data Scientist