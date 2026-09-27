# 📊 NumPy & Pandas Data Manipulation

## 📌 Overview

This repository contains hands-on practice with **NumPy and Pandas**, focusing on fundamental data manipulation and analysis techniques in Python.

The exercises cover **NumPy arrays, Pandas Series, and Pandas DataFrames**, including array operations, indexing, slicing, filtering, grouping, and data manipulation.

---

## 🛠️ Technologies Used

- Python
- NumPy
- Pandas
- Google Colab / Jupyter Notebook

---

# 🔢 NumPy Array Operations

A temperature dataset containing daily average temperatures for two weeks was used to practice NumPy operations.

## 1. Creating a 1D NumPy Array

Created a one-dimensional NumPy array containing temperatures for seven days.

```python
temperatures_w1 = np.array(
    [22.5, 25.3, 20.8, 23.4, 26.1, 24.8, 21.9]
)
```

## 2. Array Inspection

Explored important NumPy array properties such as:

- Shape
- Data type
- Number of elements

```python
temperatures_w1.shape
temperatures_w1.dtype
temperatures_w1.size
```

## 3. Array Operations

Converted temperatures from **Celsius to Fahrenheit** using:

```python
temperatures_fahrenheit = (temperatures_w1 * 9/5) + 32
```

Calculated:

- Maximum temperature
- Minimum temperature
- Mean temperature

```python
temperatures_w1.max()
temperatures_w1.min()
temperatures_w1.mean()
```

---

## 4. Array Slicing and Indexing

Practiced NumPy slicing to retrieve specific temperature values.

```python
# First three days
temperatures_w1[:3]

# Weekend - last two days
temperatures_w1[-2:]

# Middle three days
temperatures_w1[2:5]
```

---

## 5. Creating a 2D NumPy Array

Created a two-dimensional array representing temperature data for two weeks.

```python
temperatures = np.array([
    [22.5, 25.3, 20.8, 23.4, 26.1, 24.8, 21.9],
    [19.2, 22.5, 21.3, 24.0, 23.5, 22.8, 20.1]
])
```

Each **row represents a week**, while each **column represents a day**.

---

## 6. 2D Array Inspection and Slicing

Inspected:

```python
temperatures.shape
temperatures.dtype
temperatures.size
```

Retrieved individual weeks:

```python
temperatures[0]
temperatures[1]
```

Retrieved weekend temperatures for both weeks:

```python
temperatures[:, -2:]
```

---

# 🐼 Pandas Series Operations

A Pandas Series containing student marks and rank labels was created to practice indexing, filtering, and manipulation.

## 1. Creating a Pandas Series

```python
marks = pd.Series(
    [95, 92, 89, 85, 80],
    index=["Rank1", "Rank2", "Rank3", "Rank4", "Rank5"]
)
```

---

## 2. Indexing and Slicing

Practiced accessing Series values using `.loc` and `.iloc`.

```python
# First-ranked student's mark
marks.iloc[0]

# Top three ranks
marks.loc["Rank1":"Rank3"]

# Third-ranked student's mark
marks.iloc[2]
```

Applied Boolean filtering to identify students with marks greater than 90:

```python
marks[marks > 90]
```

---

## 3. Manipulating a Series

Updated the first-ranked student's mark:

```python
marks.loc["Rank1"] = 100
```

Removed the last-ranked student:

```python
marks = marks.drop("Rank5")
```

Calculated CGPA by dividing marks by 10:

```python
cgpa = marks / 10
```

---

# 📋 Pandas DataFrame Operations

A transaction dataset was created to practice DataFrame exploration, filtering, grouping, and manipulation.

The dataset contains:

- Transaction ID
- Product Category
- Region
- Amount

---

## 1. Data Exploration

Explored the DataFrame using:

```python
transactions.head()
transactions.tail()
transactions.shape
transactions.columns
transactions.dtypes
```

Selected specific columns:

```python
transactions[["ProductCategory", "Amount"]]
```

Retrieved the last three columns:

```python
transactions.iloc[:, -3:]
```

---

## 2. Data Filtering

Filtered transactions where:

- Region is `North`
- Amount is greater than `200`

```python
transactions[
    (transactions["Region"] == "North") &
    (transactions["Amount"] > 200)
]
```

---

## 3. Unique Values and Value Counts

Calculated the frequency of each product category:

```python
transactions["ProductCategory"].value_counts()
```

Retrieved unique regions:

```python
transactions["Region"].unique()
```

---

## 4. GroupBy Analysis

Grouped transactions by region and calculated the average transaction amount:

```python
transactions.groupby("Region")["Amount"].mean()
```

This demonstrates how Pandas `groupby()` can be used to summarize data across different categories.

---

## 5. DataFrame Manipulation

Updated the amount for Transaction ID `102`:

```python
transactions.loc[
    transactions["TransactionID"] == 102,
    "Amount"
] = 165
```

Created a new `Discount` column representing 10% of the transaction amount:

```python
transactions["Discount"] = transactions["Amount"] * 0.10
```

Removed Transaction ID `109`:

```python
transactions.drop(
    transactions[transactions["TransactionID"] == 109].index,
    inplace=True
)
```

Deleted the `Discount` column:

```python
transactions.drop(columns="Discount", inplace=True)
```

---

# 💡 Concepts Practiced

Through these exercises, I practiced:

- NumPy 1D and 2D arrays
- Array properties
- Vectorized operations
- Array indexing and slicing
- Celsius-to-Fahrenheit conversion
- Aggregate functions (`max`, `min`, `mean`)
- Pandas Series creation
- `.loc` and `.iloc`
- Boolean filtering
- Series manipulation
- Pandas DataFrame creation
- DataFrame exploration
- Column selection
- Conditional filtering
- `value_counts()`
- `unique()`
- `groupby()`
- Creating calculated columns
- Updating and deleting rows
- Adding and removing columns

---

## 🎯 Learning Outcome

This hands-on practice strengthened my understanding of how **NumPy and Pandas are used for data manipulation and analysis in Python**.

I learned how to work with arrays and tabular data, perform calculations efficiently, retrieve data using indexing and slicing, filter records based on conditions, summarize data using aggregation, and modify Series and DataFrames.

These concepts form an important foundation for **data cleaning, exploratory data analysis, and Data Analytics**.

