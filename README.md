
---

## 🐼 Step-by-Step Guide to Pandas

---

### ✅ Step 1: **Install pandas**

If you haven’t installed it yet:

```bash
pip install pandas
```

---

### ✅ Step 2: **Import pandas**

```python
import pandas as pd
```

---

### ✅ Step 3: **Create a DataFrame**

```python
data = {
    'Name': ['Alice', 'Bob', 'Charlie'],
    'Age': [25, 30, 35],
    'City': ['New York', 'Paris', 'London']
}

df = pd.DataFrame(data)
print(df)
```

---

### ✅ Step 4: **Read Data from CSV / Excel**

```python
# From CSV
df = pd.read_csv('filename.csv')

# From Excel
df = pd.read_excel('filename.xlsx')
```

---

### ✅ Step 5: **View Data**

```python
df.head()       # First 5 rows
df.tail()       # Last 5 rows
df.shape        # (rows, columns)
df.columns      # Column names
df.info()       # Data types and non-null counts
df.describe()   # Summary stats
```

---

### ✅ Step 6: **Select Data**

```python
df['Name']              # Single column
df[['Name', 'Age']]     # Multiple columns
df.iloc[0]              # First row (by index)
df.loc[0]               # First row (by label)
df.iloc[0:2]            # First 2 rows
```

---

### ✅ Step 7: **Filter Data**

```python
df[df['Age'] > 28]             # Rows where Age > 28
df[df['City'] == 'London']     # Rows where City == London
```

---

### ✅ Step 8: **Add / Modify Columns**

```python
df['NewAge'] = df['Age'] + 1           # Add column
df['IsAdult'] = df['Age'] > 18         # Boolean column
```

---

### ✅ Step 9: **Delete Columns / Rows**

```python
df.drop('NewAge', axis=1, inplace=True)     # Delete column
df.drop(0, axis=0, inplace=True)            # Delete row by index
```

---

### ✅ Step 10: **Group and Aggregate**

```python
df.groupby('City')['Age'].mean()     # Average age per city
df.groupby('City').agg({'Age': ['mean', 'max']})
```

---

### ✅ Step 11: **Sort Data**

```python
df.sort_values('Age')                 # Ascending
df.sort_values('Age', ascending=False)  # Descending
```

---

### ✅ Step 12: **Missing Data**

```python
df.isnull()                # Check missing
df.dropna()                # Remove rows with missing values
df.fillna(0)               # Replace missing with 0
```

---

### ✅ Step 13: **Save Data**

```python
df.to_csv('output.csv', index=False)
df.to_excel('output.xlsx', index=False)
```

---

## 🚀 What's Next?

* Learn about merging/joining DataFrames (`merge`, `concat`)
* Work with datetime data (`pd.to_datetime`)
* Use `apply()` for row/column-wise custom operations
* Explore pivot tables and reshaping (`pivot_table`, `melt`)

---
Perfect! Let’s go **step-by-step with examples** using a **real-world-style dataset**.

We’ll use a fictional **student data set** for demonstration.

---

## 📊 **Step-by-Step Pandas with Real-World Dataset**

### 🔰 Step 1: **Import pandas**

```python
import pandas as pd
```

---

### 📋 Step 2: **Create a Dataset (Student Records)**

```python
data = {
    'StudentID': [101, 102, 103, 104],
    'Name': ['Alice', 'Bob', 'Charlie', 'David'],
    'Marks': [88, 92, 79, 85],
    'City': ['New York', 'Paris', 'London', 'Paris']
}

df = pd.DataFrame(data)
print(df)
```

**Output:**

```
   StudentID     Name  Marks      City
0        101    Alice     88  New York
1        102      Bob     92     Paris
2        103  Charlie     79    London
3        104    David     85     Paris
```

---

### 🔍 Step 3: **Basic Data Overview**

```python
df.head()          # First 5 rows
df.tail()          # Last 5 rows
df.shape           # (Rows, Columns)
df.columns         # Column names
df.info()          # Summary of data types
df.describe()      # Stats for numeric columns
```

---

### 🎯 Step 4: **Selecting Columns**

```python
df['Name']                  # Single column
df[['Name', 'Marks']]       # Multiple columns
```

---

### 🔎 Step 5: **Filtering Data**

```python
df[df['Marks'] > 85]               # Students with Marks > 85
df[df['City'] == 'Paris']          # Students in Paris
```

---

### ➕ Step 6: **Add a New Column**

```python
df['Grade'] = ['B', 'A', 'C', 'B']
print(df)
```

---

### ✏️ Step 7: **Modify a Column**

```python
df['Passed'] = df['Marks'] >= 80
print(df[['Name', 'Marks', 'Passed']])
```

---

### ❌ Step 8: **Delete a Column or Row**

```python
df.drop('Grade', axis=1, inplace=True)  # Delete column
df.drop(2, axis=0, inplace=True)        # Delete row with index 2
```

---

### 🔗 Step 9: **Group & Aggregate**

```python
df.groupby('City')['Marks'].mean()  # Average marks by city
```

---

### 🔁 Step 10: **Sort Data**

```python
df.sort_values(by='Marks', ascending=False)
```

---

### 🧱 Step 11: **Missing Data**

Let’s simulate missing data:

```python
df.loc[1, 'Marks'] = None
print(df)

df.isnull()          # Check missing
df.fillna(0)         # Replace missing with 0
df.dropna()          # Drop rows with missing
```

---

### 💾 Step 12: **Save to CSV/Excel**

```python
df.to_csv('students.csv', index=False)
df.to_excel('students.xlsx', index=False)
```

---

## ✅ Summary Table of Common Commands

| Task                 | Command                    |
| -------------------- | -------------------------- |
| Read CSV             | `pd.read_csv('file.csv')`  |
| View first rows      | `df.head()`                |
| Select column        | `df['col']`                |
| Filter rows          | `df[df['col'] > value]`    |
| Add new column       | `df['new'] = ...`          |
| Delete column        | `df.drop('col', axis=1)`   |
| Group data           | `df.groupby('col').mean()` |
| Sort                 | `df.sort_values(by='col')` |
| Missing values check | `df.isnull()`              |
| Save to file         | `df.to_csv('file.csv')`    |

---

