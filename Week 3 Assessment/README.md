Data cleaning, exploration, and visualization.

# User Data Cleaning and Visualization

## Project Overview

This project focuses on cleaning a dataset of user records, exploring key patterns, and visualizing insights. The dataset includes demographic information, KYC (Know Your Customer) verification status, and occupation details for users in Nigeria and Canada.

---

## Steps Performed

### 1. **Data Loading**

* Imported CSV into a pandas DataFrame:

```python
import pandas as pd
df = pd.read_csv('/content/drive/MyDrive/user_data (1).csv')
```

* Previewed first 20 rows using:

```python
df.head(20)
```

---

### 2. **Data Cleaning**

* **Replaced empty strings with NaN:**

```python
import numpy as np
df = df.replace(r'^\s*$', np.nan, regex=True)
```

* **Checked columns:**

```python
df.columns
```

* **Dropped unnamed column if present:**

```python
df = df.loc[:, ~df.columns.str.contains('^Unnamed')]
```

* **Checked for duplicates:**

```python
df.duplicated().sum()
```

* Saved a clean copy of the data:

```python
df.to_csv('cleaned_user_data.csv', index=False)
```

---

### 3. **Exploratory Data Analysis (EDA)**

* **Examined missing values:**

```python
df.isnull().sum()
```

* **Checked unique values per column:**

```python
df.nunique()
```

* **Looked at distributions by Gender, KYC status, Generation, Country, and Industry.**

---

### 4. **Data Visualization**

Using **Matplotlib** and **Seaborn**:

```python
import matplotlib.pyplot as plt
import seaborn as sns
```

* **User distribution by country**
* **KYC Status vs Completed Profile**
* **Age distribution histogram**
* **Gender breakdown (pie chart / count plot)**
* **Industry vs Generation (bar plot)**

---

## Key Findings

1. **Data Gaps**

   * Several missing entries in `ReferredBy`, `Standardized_State`, and `Industry`.
   * Empty rows successfully replaced with `NaN`.

2. **User Demographics**

   * Users span across **Millennials, Gen Z, and Gen X**, with no Baby Boomers present.
   * A mix of **Male, Female, and Non-Binary users**, showing diversity.

3. **KYC Verification**

   * Significant portion of users have not started or failed KYC.
   * Only a subset of users have **CompletedProfile = TRUE** and **KYC = Passed**.

4. **Country Insights**

   * Users primarily from **Nigeria and Canada**.
   * Occupations vary widely (students, artisans, managers, tech, finance, trades).

5. **Industry Spread**

   * Heavy representation from **Student**, **Management**, **Technology**, and **Other** categories.



