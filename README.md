# 🐼 Pandas Functions & Methods

A structured quick-reference guide to important **Pandas functions and methods** used in **Data Analysis, Data Science, and Machine Learning**.

---
## Introduction to Pandas
`What is Pandas?`

Pandas is a Python library used for:

Data manipulation
Data cleaning
Data analysis
Data preprocessing
Feature engineering
Machine Learning dataset preparation

It mainly provides two powerful data structures:

**Series** → One-dimensional labeled data.
**DataFrame** → Two-dimensional tabular data.

# 📌 Table of Contents

1. Pandas Basics
2. Series
3. DataFrame
4. Creating DataFrames
5. Loading Data
6. Exploring Data
7. Selecting Data
8. Row Selection
9. Filtering Data
10. Adding and Modifying Columns
11. Renaming Data
12. Deleting Data
13. Missing Values
14. Duplicate Data
15. Sorting Data
16. Statistical Functions
17. Unique Values
18. GroupBy Operations
19. Combining DataFrames
20. Apply, Map and Replace
21. String Operations

---

# 1️⃣ Pandas Basics

| Function / Syntax | Parameters | One-Line Explanation | Example |
|---|---|---|---|
| `import pandas as pd` | — | Imports the Pandas library with the alias `pd`. | `import pandas as pd` |

---

# 2️⃣ Series

## `pd.Series()`

| Parameter | One-Line Explanation | Example |
|---|---|---|
| `data` | Provides the values for the Series. | `pd.Series([10, 20, 30])` |
| `index` | Defines custom labels for values. | `pd.Series([10, 20], index=["A", "B"])` |
| `dtype` | Defines the data type. | `pd.Series([1, 2], dtype="float")` |
| `name` | Assigns a name to the Series. | `pd.Series([1, 2], name="Marks")` |

## Common Series Methods

| Function / Method | Important Parameters | One-Line Explanation | One-Line Example |
|---|---|---|---|
| `head()` | `n=5` | Returns the first `n` values. | `s.head(5)` |
| `tail()` | `n=5` | Returns the last `n` values. | `s.tail(5)` |
| `dtype` | — | Returns the data type. | `s.dtype` |
| `index` | — | Returns index labels. | `s.index` |
| `values` | — | Returns underlying values. | `s.values` |
| `size` | — | Returns total number of elements. | `s.size` |
| `shape` | — | Returns Series dimensions. | `s.shape` |
| `mean()` | `skipna` | Returns the average value. | `s.mean()` |
| `median()` | `skipna` | Returns the middle value. | `s.median()` |
| `mode()` | `dropna` | Returns the most frequent value. | `s.mode()` |
| `sum()` | `skipna` | Returns the total sum. | `s.sum()` |
| `min()` | `skipna` | Returns the smallest value. | `s.min()` |
| `max()` | `skipna` | Returns the largest value. | `s.max()` |
| `std()` | `skipna`, `ddof` | Returns standard deviation. | `s.std()` |
| `var()` | `skipna`, `ddof` | Returns variance. | `s.var()` |
| `unique()` | — | Returns unique values. | `s.unique()` |
| `nunique()` | `dropna` | Returns the number of unique values. | `s.nunique()` |
| `value_counts()` | `normalize`, `sort`, `dropna` | Counts occurrences of unique values. | `s.value_counts()` |
| `isnull()` | — | Detects missing values. | `s.isnull()` |
| `notnull()` | — | Detects non-missing values. | `s.notnull()` |
| `fillna()` | `value` | Replaces missing values. | `s.fillna(0)` |
| `dropna()` | — | Removes missing values. | `s.dropna()` |
| `astype()` | `dtype` | Converts values to another data type. | `s.astype(int)` |

---

# 3️⃣ DataFrame

## `pd.DataFrame()`

| Parameter | One-Line Explanation | Example |
|---|---|---|
| `data` | Provides data for the DataFrame. | `pd.DataFrame(data)` |
| `index` | Defines row labels. | `pd.DataFrame(data, index=[1, 2])` |
| `columns` | Defines column names. | `pd.DataFrame(data, columns=["A", "B"])` |
| `dtype` | Defines the data type. | `pd.DataFrame(data, dtype=float)` |

---

# 4️⃣ Creating DataFrames

| Method | One-Line Explanation | One-Line Example |
|---|---|---|
| Dictionary | Creates a DataFrame from key-value data. | `pd.DataFrame({"Name": ["A", "B"]})` |
| List | Creates a DataFrame from rows. | `pd.DataFrame([[1, 2], [3, 4]])` |
| List of Dictionaries | Creates a DataFrame from dictionaries. | `pd.DataFrame([{"A": 1}, {"A": 2}])` |
| NumPy Array | Creates a DataFrame from an array. | `pd.DataFrame(np.array([[1, 2], [3, 4]]))` |

---

# 5️⃣ Loading Data

| Function | Important Parameters | One-Line Explanation | One-Line Example |
|---|---|---|---|
| `pd.read_csv()` | `filepath_or_buffer`, `sep`, `header`, `names`, `usecols`, `dtype`, `nrows` | Loads CSV data into a DataFrame. | `pd.read_csv("data.csv")` |
| `pd.read_excel()` | `io`, `sheet_name`, `header`, `usecols`, `nrows` | Loads Excel data into a DataFrame. | `pd.read_excel("data.xlsx")` |
| `pd.read_json()` | `path_or_buf`, `orient`, `dtype` | Loads JSON data into a DataFrame. | `pd.read_json("data.json")` |
| `pd.read_sql()` | `sql`, `con`, `index_col`, `params` | Loads SQL query results into a DataFrame. | `pd.read_sql("SELECT * FROM users", con)` |

---

# 6️⃣ Exploring Data

| Function / Attribute | Important Parameters | One-Line Explanation | One-Line Example |
|---|---|---|---|
| `head()` | `n=5` | Displays the first rows. | `df.head()` |
| `tail()` | `n=5` | Displays the last rows. | `df.tail()` |
| `shape` | — | Returns the number of rows and columns. | `df.shape` |
| `columns` | — | Returns column names. | `df.columns` |
| `index` | — | Returns row index labels. | `df.index` |
| `info()` | `verbose`, `show_counts`, `memory_usage` | Shows dataset structure and data types. | `df.info()` |
| `describe()` | `percentiles`, `include`, `exclude` | Generates statistical summary. | `df.describe()` |
| `dtypes` | — | Returns the data type of each column. | `df.dtypes` |

---

# 7️⃣ Selecting Data

| Method | Important Parameters | One-Line Explanation | One-Line Example |
|---|---|---|---|
| `[]` | Column name | Selects a single column. | `df["Age"]` |
| `[[]]` | Column list | Selects multiple columns. | `df[["Age", "Salary"]]` |
| `get()` | `key`, `default` | Safely retrieves a column. | `df.get("Age")` |

---

# 8️⃣ Row Selection

| Method | Parameters | One-Line Explanation | One-Line Example |
|---|---|---|---|
| `loc[]` | Row labels, column labels | Selects data using labels. | `df.loc[0:5, ["Name"]]` |
| `iloc[]` | Row positions, column positions | Selects data using positions. | `df.iloc[0:5, 0:2]` |
| `at[]` | Row label, column label | Accesses one value using labels. | `df.at[0, "Name"]` |
| `iat[]` | Row position, column position | Accesses one value using positions. | `df.iat[0, 0]` |

---

# 9️⃣ Filtering Data

| Method | Important Parameters | One-Line Explanation | One-Line Example |
|---|---|---|---|
| Boolean Filtering | Condition | Filters rows using a condition. | `df[df["Age"] > 20]` |
| AND `&` | Multiple conditions | Filters rows where all conditions are true. | `df[(df["Age"] > 20) & (df["Score"] > 80)]` |
| OR `|` | Multiple conditions | Filters rows where any condition is true. | `df[(df["Age"] > 20) | (df["Score"] > 80)]` |
| `isin()` | `values` | Filters values present in a list. | `df[df["City"].isin(["Chennai", "Delhi"])]` |
| `between()` | `left`, `right`, `inclusive` | Filters values within a range. | `df[df["Age"].between(20, 30)]` |
| `query()` | `expr` | Filters data using a query expression. | `df.query("Age > 20")` |

---

# 🔟 Adding and Modifying Columns

| Method | Important Parameters | One-Line Explanation | One-Line Example |
|---|---|---|---|
| Column Assignment | Column name, values | Creates or updates a column. | `df["Age"] = 20` |
| Column Calculation | Existing columns | Creates a column using calculations. | `df["Total"] = df["A"] + df["B"]` |
| `np.where()` | `condition`, `x`, `y` | Creates values based on a condition. | `df["Result"] = np.where(df["Score"] >= 50, "Pass", "Fail")` |

---

# 1️⃣1️⃣ Renaming Data

| Method | Important Parameters | One-Line Explanation | One-Line Example |
|---|---|---|---|
| `rename()` | `mapper`, `index`, `columns`, `inplace` | Renames rows or columns. | `df.rename(columns={"Age": "Student_Age"})` |
| `df.columns` | Column names | Replaces all column names. | `df.columns = ["A", "B", "C"]` |

---

# 1️⃣2️⃣ Deleting Data

| Method | Important Parameters | One-Line Explanation | One-Line Example |
|---|---|---|---|
| `drop()` | `labels`, `axis`, `index`, `columns`, `inplace` | Removes specified rows or columns. | `df.drop(columns=["Age"])` |
| Drop Rows | `index` | Removes rows using index labels. | `df.drop(index=[0, 1])` |
| Drop Columns | `columns` | Removes selected columns. | `df.drop(columns=["Age", "City"])` |

---

# 1️⃣3️⃣ Missing Values

| Method | Important Parameters | One-Line Explanation | One-Line Example |
|---|---|---|---|
| `isnull()` | — | Detects missing values. | `df.isnull()` |
| `isna()` | — | Detects missing values. | `df.isna()` |
| `notnull()` | — | Detects non-missing values. | `df.notnull()` |
| `notna()` | — | Detects non-missing values. | `df.notna()` |
| `isnull().sum()` | — | Counts missing values per column. | `df.isnull().sum()` |
| `dropna()` | `axis`, `how`, `subset`, `inplace` | Removes missing rows or columns. | `df.dropna()` |
| `fillna()` | `value`, `axis`, `inplace` | Replaces missing values. | `df.fillna(0)` |
| `ffill()` | `axis`, `limit` | Fills missing values using previous values. | `df.ffill()` |
| `bfill()` | `axis`, `limit` | Fills missing values using next values. | `df.bfill()` |

---

# 1️⃣4️⃣ Duplicate Data

| Method | Important Parameters | One-Line Explanation | One-Line Example |
|---|---|---|---|
| `duplicated()` | `subset`, `keep` | Detects duplicate rows. | `df.duplicated()` |
| `duplicated().sum()` | — | Counts duplicate rows. | `df.duplicated().sum()` |
| `drop_duplicates()` | `subset`, `keep`, `inplace` | Removes duplicate rows. | `df.drop_duplicates()` |

---

# 1️⃣5️⃣ Sorting Data

| Method | Important Parameters | One-Line Explanation | One-Line Example |
|---|---|---|---|
| `sort_values()` | `by`, `axis`, `ascending`, `inplace` | Sorts data using column values. | `df.sort_values("Score")` |
| Descending Sort | `ascending=False` | Sorts values from highest to lowest. | `df.sort_values("Score", ascending=False)` |
| Multiple Sorting | Column list | Sorts using multiple columns. | `df.sort_values(["City", "Score"])` |
| `sort_index()` | `axis`, `ascending` | Sorts data using index labels. | `df.sort_index()` |

---

# 1️⃣6️⃣ Statistical Functions

| Function | Important Parameters | One-Line Explanation | One-Line Example |
|---|---|---|---|
| `mean()` | `axis`, `skipna` | Returns the arithmetic average. | `df["Score"].mean()` |
| `median()` | `axis`, `skipna` | Returns the middle value. | `df["Score"].median()` |
| `mode()` | `axis`, `dropna` | Returns the most frequent value. | `df["Score"].mode()` |
| `min()` | `axis`, `skipna` | Returns the smallest value. | `df["Score"].min()` |
| `max()` | `axis`, `skipna` | Returns the largest value. | `df["Score"].max()` |
| `sum()` | `axis`, `skipna` | Returns the total sum. | `df["Score"].sum()` |
| `count()` | `axis` | Counts non-missing values. | `df.count()` |
| `std()` | `axis`, `skipna`, `ddof` | Returns standard deviation. | `df["Score"].std()` |
| `var()` | `axis`, `skipna`, `ddof` | Returns variance. | `df["Score"].var()` |
| `quantile()` | `q`, `axis` | Returns a specified quantile value. | `df["Score"].quantile(0.25)` |
| `prod()` | `axis`, `skipna` | Returns the product of values. | `df["Score"].prod()` |
| `abs()` | — | Returns absolute values. | `df["Score"].abs()` |

---

# 1️⃣7️⃣ Unique Values

| Method | Important Parameters | One-Line Explanation | One-Line Example |
|---|---|---|---|
| `unique()` | — | Returns all unique values. | `df["City"].unique()` |
| `nunique()` | `axis`, `dropna` | Counts unique values. | `df["City"].nunique()` |
| `value_counts()` | `normalize`, `sort`, `ascending`, `dropna` | Counts each unique value. | `df["City"].value_counts()` |

---

# 1️⃣8️⃣ GroupBy Operations

| Method | Important Parameters | One-Line Explanation | One-Line Example |
|---|---|---|---|
| `groupby()` | `by`, `as_index`, `sort` | Groups data based on a column. | `df.groupby("City")` |
| `mean()` | — | Calculates the average for each group. | `df.groupby("City")["Salary"].mean()` |
| `sum()` | — | Calculates the total for each group. | `df.groupby("City")["Salary"].sum()` |
| `min()` | — | Finds the minimum for each group. | `df.groupby("City")["Salary"].min()` |
| `max()` | — | Finds the maximum for each group. | `df.groupby("City")["Salary"].max()` |
| `count()` | — | Counts values for each group. | `df.groupby("City")["Salary"].count()` |
| `median()` | — | Finds the median for each group. | `df.groupby("City")["Salary"].median()` |
| `std()` | — | Calculates standard deviation for each group. | `df.groupby("City")["Salary"].std()` |
| `agg()` | Functions or dictionary | Performs one or multiple aggregations. | `df.groupby("City")["Salary"].agg(["mean", "max"])` |

---

# 1️⃣9️⃣ Combining DataFrames

| Method | Important Parameters | One-Line Explanation | One-Line Example |
|---|---|---|---|
| `pd.concat()` | `objs`, `axis`, `join`, `ignore_index` | Combines DataFrames vertically or horizontally. | `pd.concat([df1, df2])` |
| `pd.merge()` | `left`, `right`, `how`, `on`, `left_on`, `right_on` | Combines DataFrames using common columns. | `pd.merge(df1, df2, on="ID")` |
| Inner Join | `how="inner"` | Keeps only matching rows. | `pd.merge(df1, df2, on="ID", how="inner")` |
| Left Join | `how="left"` | Keeps all rows from the left DataFrame. | `pd.merge(df1, df2, on="ID", how="left")` |
| Right Join | `how="right"` | Keeps all rows from the right DataFrame. | `pd.merge(df1, df2, on="ID", how="right")` |
| Outer Join | `how="outer"` | Keeps all rows from both DataFrames. | `pd.merge(df1, df2, on="ID", how="outer")` |

---

# 2️⃣0️⃣ Apply, Map and Replace

| Method | Important Parameters | One-Line Explanation | One-Line Example |
|---|---|---|---|
| `apply()` | `func`, `axis` | Applies a function to data. | `df["Age"].apply(lambda x: x * 2)` |
| `map()` | `arg`, `na_action` | Maps Series values to new values. | `df["Gender"].map({"Male": 1, "Female": 0})` |
| `replace()` | `to_replace`, `value`, `inplace` | Replaces specified values with new values. | `df.replace("Male", 1)` |

---

# 2️⃣1️⃣ String Operations

| Method | Important Parameters | One-Line Explanation | One-Line Example |
|---|---|---|---|
| `.str.lower()` | — | Converts text to lowercase. | `df["Name"].str.lower()` |
| `.str.upper()` | — | Converts text to uppercase. | `df["Name"].str.upper()` |
| `.str.title()` | — | Converts text to title case. | `df["Name"].str.title()` |
| `.str.capitalize()` | — | Capitalizes the first character. | `df["Name"].str.capitalize()` |
| `.str.strip()` | `to_strip` | Removes characters from both ends. | `df["Name"].str.strip()` |
| `.str.lstrip()` | `to_strip` | Removes characters from the left side. | `df["Name"].str.lstrip()` |
| `.str.rstrip()` | `to_strip` | Removes characters from the right side. | `df["Name"].str.rstrip()` |
| `.str.len()` | — | Returns the length of each string. | `df["Name"].str.len()` |
| `.str.contains()` | `pat`, `case`, `regex`, `na` | Checks whether text contains a pattern. | `df["Email"].str.contains("@")` |
| `.str.startswith()` | `pat`, `na` | Checks whether text starts with a pattern. | `df["Name"].str.startswith("A")` |
| `.str.endswith()` | `pat`, `na` | Checks whether text ends with a pattern. | `df["Email"].str.endswith(".com")` |
| `.str.replace()` | `pat`, `repl`, `regex` | Replaces text patterns. | `df["Name"].str.replace("Mr.", "")` |
| `.str.split()` | `pat`, `n`, `expand` | Splits text into multiple parts. | `df["Name"].str.split(" ")` |
| `.str.find()` | `sub` | Finds the position of text. | `df["Email"].str.find("@")` |
| `.str.extract()` | `pat`, `expand` | Extracts text using a pattern. | `df["Email"].str.extract(r"@(.*)")` |

---

# 🤖 Pandas for Machine Learning

| Machine Learning Task | Important Pandas Functions |
|---|---|
| Load Dataset | `read_csv()`, `read_excel()`, `read_json()` |
| Explore Dataset | `head()`, `tail()`, `info()`, `describe()` |
| Select Features | `[]`, `loc[]`, `iloc[]` |
| Filter Dataset | `isin()`, `between()`, `query()` |
| Handle Missing Values | `isnull()`, `fillna()`, `dropna()` |
| Remove Duplicates | `duplicated()`, `drop_duplicates()` |
| Data Analysis | `mean()`, `median()`, `std()`, `var()` |
| Categorical Analysis | `unique()`, `nunique()`, `value_counts()` |
| Feature Transformation | `apply()`, `map()`, `replace()` |
| Combine Datasets | `concat()`, `merge()` |
| Group Analysis | `groupby()`, `agg()` |
| Text Cleaning | `.str.lower()`, `.str.strip()`, `.str.replace()` |

---

# 🚀 Conclusion

This repository contains a quick-reference guide to essential Pandas functions used for:

- Data Cleaning
- Data Analysis
- Data Preprocessing
- Feature Engineering
- Machine Learning Preparation

> **"Good Machine Learning starts with good data, and good data preparation starts with Pandas."** 🐼📊🤖
