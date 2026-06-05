# 📊 Customer Data Profiling & Exploratory Data Analysis (EDA)

<p align="center">
  <img src="Screenshot 2026-06-03 171538.png" width="700">
</p>

## 🚀 Project Overview

This project demonstrates a complete **Data Profiling and Exploratory Data Analysis (EDA)** workflow using Python. The objective is to collect data from multiple sources, assess data quality, clean missing values, and perform statistical analysis through visualizations.

The project covers:

* CSV Data Loading
* JSON Data Processing
* SQLite Database Integration
* REST API Data Extraction
* Missing Value Analysis
* Duplicate Detection
* Data Cleaning
* Univariate Analysis
* Data Profiling

---

# 🛠️ Technologies Used

| Technology       | Purpose                   |
| ---------------- | ------------------------- |
| Python           | Programming Language      |
| Pandas           | Data Analysis             |
| NumPy            | Numerical Computation     |
| SQLite3          | Database Operations       |
| Requests         | API Integration           |
| Matplotlib       | Data Visualization        |
| Seaborn          | Statistical Visualization |
| Jupyter Notebook | Development Environment   |

---

# 📂 Project Structure

```text
Customer-EDA-Project/
│
├── project1.ipynb
├── customer2.csv
├── customer2.json
├── customer.db
├── README.md
│
├── Screenshot 2026-06-03 171538.png
├── Screenshot 2026-06-03 171552.png
├── Screenshot 2026-06-03 171558.png
├── Screenshot 2026-06-03 171609.png
├── Screenshot 2026-06-03 171621.png
├── Screenshot 2026-06-03 171627.png
└── Screenshot 2026-06-03 171633.png
```

---

# 🔄 Workflow

## 1️⃣ Import Libraries

```python
import pandas as pd
import numpy as np
import sqlite3
import requests
import matplotlib.pyplot as plt
import seaborn as sns
```

---

## 2️⃣ Load Dataset

```python
df = pd.read_csv("customer2.csv")
```

### Output

<img src="Screenshot 2026-06-03 171538.png" width="800">

---

## 3️⃣ Dataset Information

```python
df.info()
```

### Output

<img src="Screenshot 2026-06-03 171552.png" width="800">

---

## 4️⃣ Statistical Summary

```python
df.describe()
```

### Output

<img src="Screenshot 2026-06-03 171558.png" width="800">

---

## 5️⃣ Load JSON Data

```python
json_df = pd.read_json("customer2.json")
```

---

## 6️⃣ Load SQLite Database

```python
conn = sqlite3.connect("customer.db")

query = "SELECT * FROM Customers"

sql_df = pd.read_sql(query, conn)

conn.close()
```

### Output

<img src="Screenshot 2026-06-03 171609.png" width="800">

---

## 7️⃣ API Data Extraction

```python
url = "https://jsonplaceholder.typicode.com/users"

response = requests.get(url)

api_df = pd.DataFrame(response.json())
```

### Output

<img src="Screenshot 2026-06-03 171621.png" width="800">

---

## 8️⃣ Missing Value Analysis

```python
df.isnull().sum()
```

### Output

<img src="Screenshot 2026-06-03 171627.png" width="800">

---

## 9️⃣ Duplicate Record Detection

```python
df.duplicated().sum()
```

---

## 🔟 Missing Value Imputation

### Numerical Features

```python
num_cols = df.select_dtypes(include=np.number).columns

for col in num_cols:
    df[col] = df[col].fillna(df[col].median())
```

### Categorical Features

```python
cat_cols = df.select_dtypes(include='object').columns

for col in cat_cols:
    df[col] = df[col].fillna(df[col].mode().iloc[0])
```

---

# 📈 Data Visualization

### Age Distribution

```python
sns.histplot(df["Age"], kde=True)
plt.show()
```

### Income Distribution

```python
sns.histplot(df["Income"], kde=True)
plt.show()
```

### Output

<img src="Screenshot 2026-06-03 171633.png" width="800">

---

# 📊 Key Insights

✅ Dataset contains customer demographic and purchasing information.

✅ Missing values were successfully identified and treated.

✅ Numerical attributes were imputed using median values.

✅ Categorical attributes were imputed using mode values.

✅ No duplicate records were found.

✅ Histograms provided insights into customer age and income distributions.

✅ Multiple data sources were integrated successfully.

---

# 🎯 Learning Outcomes

* Data Profiling
* Data Cleaning
* Missing Value Handling
* Database Connectivity
* API Data Extraction
* Exploratory Data Analysis
* Data Visualization
* Python Data Analytics Workflow

---

# 📌 Conclusion

This project demonstrates an end-to-end Data Profiling and Exploratory Data Analysis process. The workflow begins with data collection from multiple sources and concludes with data cleaning, profiling, and visualization. The project establishes a strong foundation for future Machine Learning and Predictive Analytics applications.

---

# 👨‍💻 Author

**Manan Patel**

Data Analytics | Data Science | Machine Learning Enthusiast

⭐ If you found this project useful, consider giving it a star on GitHub!
