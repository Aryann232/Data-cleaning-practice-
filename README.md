# Employee Data Cleaning Using Python & Pandas

## 📌 Project Overview

This project focuses on cleaning and preprocessing a messy Employee dataset using Python and the Pandas library.

The objective is to identify and handle missing values, remove duplicate records, inspect unique values, correct data types, and prepare a clean dataset for further analysis and visualization in Power BI.

## 🎯 Project Objectives

- Understand the structure of the dataset.
- Identify and handle missing values.
- Explore unique and categorical values.
- Detect and remove duplicate records.
- Convert columns into appropriate data types.
- Export the cleaned dataset into CSV format.

## 🛠️ Tools & Technologies

- **Python 3**
- **Pandas** – Data manipulation and cleaning
- **NumPy** – Numerical operations
- **VS Code** – Development environment

## 📂 Dataset Information

The dataset contains employee-related information with the following 12 columns:

| Column Name | Description |
|---|---|
| Employee_ID | Unique employee identifier |
| First_Name | Employee's first name |
| Last_Name | Employee's last name |
| Age | Employee age |
| Department_Region | Department or region |
| Status | Employee status |
| Join_Date | Employee joining date |
| Salary | Employee salary |
| Email | Employee email address |
| Phone | Employee phone number |
| Performance_Score | Employee performance score |
| Remote_Work | Remote work status |

## 🔍 Data Cleaning Steps Performed

### 1. Load Dataset
Loaded the CSV file using Pandas.

```python
import pandas as pd
import numpy as np

df = pd.read_csv("Messy_Employee_dataset.csv")
```

### 2. Data Exploration
Inspected the dataset using:

- `head()`
- `tail()`
- `sample()`
- `info()`
- `describe()`
- `shape`
- `isnull().sum()`

### 3. Handle Missing Values

Identified missing values and filled them using statistical methods:

- **Age:** Filled missing values using Mean.
- **Salary:** Filled missing values using Median.

```python
df['Age'] = df['Age'].fillna(df['Age'].mean())
df['Salary'] = df['Salary'].fillna(df['Salary'].median())
```

### 4. Explore Unique Values

Used the following methods to understand categorical data:

```python
df['Department_Region'].unique()
df['Department_Region'].nunique()
df['Department_Region'].value_counts()
```

### 5. Identify and Remove Duplicates

Detected duplicate records and removed them.

```python
df.duplicated().sum()
df.drop_duplicates(inplace=True)
```

### 6. Correct Data Types

Converted Age into an integer data type and Join_Date into a datetime format.

```python
df['Age'] = df['Age'].astype('int64')

df['Join_Date'] = pd.to_datetime(
    df['Join_Date'],
    errors='coerce'
)
```

### 7. Export Cleaned Dataset

Saved the cleaned dataset as a CSV file.

```python
df.to_csv("Cleaned_Employee_Dataset.csv", index=False)
```

## 📊 Output

The project generates a cleaned employee dataset:

`Cleaned_Employee_Dataset.csv`

The output file is ready for further analysis and can be imported into Power BI for dashboard development.

## 💡 Key Learnings

- Practical experience with Pandas data-cleaning functions.
- Handling missing values using Mean and Median.
- Identifying and removing duplicate records.
- Exploring categorical data using unique values and value counts.
- Converting data types using Pandas.
- Exporting cleaned datasets for further analysis.

## 🚀 Future Improvements

- Handle inconsistent text values.
- Validate email addresses and phone numbers.
- Identify and investigate invalid employee ages and salaries.
- Detect and analyze outliers.
- Perform additional data validation before exporting.

---

**Project Category:** Data Cleaning & Data Preprocessing  
**Technology:** Python, Pandas, NumPy  
**Output:** Cleaned Employee Dataset (CSV)
