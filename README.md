# **Experiment No. 13 :Data Wrangling**
### **Aim**

To perform preprocessing of datasets and handle missing and inconsistent values using data wrangling techniques in Python.

### **Theory**

Data wrangling is a crucial preprocessing step in data analysis where raw data is cleaned and transformed into a usable format. Real-world datasets often contain missing values, inconsistent formats, and incorrect data types.

Effective data wrangling ensures:

- Improved data quality
- Better accuracy in analysis
- Reduced chances of misleading results

Key operations include detecting missing values, handling them appropriately, converting data types, and maintaining consistency across the dataset. The Pandas library provides efficient tools to perform these tasks.

###### _Dataset 1: Missing Value Analysis_

This dataset is created with missing values to understand detection and handling techniques.

Detection of Missing Values
- df1.isna() → Identifies missing values
- df1.isnull() → Same as isna()
Detection of Valid Values
- df1.notna() → Identifies non-missing values
- df1.notnull() → Same as notna()
Quantifying Missing Data
- df1.isna().sum() → Column-wise count
- df1.isna().sum(axis=1) → Row-wise count

Insight:

- Column C2 has the highest number of missing values
- Removing Missing Values
- df1.dropna() → Removes rows with missing values
- df1.dropna(axis=1) → Removes columns with missing values

Observation:

- Dropping rows may cause data loss
- Dropping columns removes entire features
- Filling Missing Values (Imputation)
- df1.fillna(0) → Replace with constant
- df1.fillna(df1.mean()) → Column mean
- df1.fillna(df1.mean(axis=1)) → Row-wise mean

Insight:
- Mean imputation preserves dataset size
###### _Dataset 2: Data Cleaning and Transformation_

This dataset contains inconsistent entries and mixed data types.

Handling Invalid Entries
df.replace("-", np.nan) → Converts invalid values to NaN
Data Type Conversion
- pd.to_numeric(df["Age"], errors="coerce")
- pd.to_numeric(df["Marks"], errors="coerce")

Insight:

- Invalid values are converted to NaN
- Missing Value Analysis
- df.isna().sum() → Displays missing values per column

Observation:
- Missing values exist in Age and Marks
- Imputation Techniques
- df["Age"].fillna(df["Age"].mean()) → Mean imputation
- df["Marks"].fillna(df["Marks"].median()) → Median imputation

Insight:
- Median is better for marks to handle outliers
- Data Standardization
- df["Department"].str.upper() → Converts text to uppercase
Date Conversion
- pd.to_datetime(df["Admission_Date"], errors="coerce")

Insight:
Enables time-based analysis
Command Summary
- isna() / isnull() → Detect missing values
- notna() / notnull() → Detect non-missing values
- sum() → Count missing values
- dropna() → Remove missing data
- fillna() → Replace missing values
- replace() → Standardize invalid entries
- to_numeric() → Convert to numeric data
- str.upper() → Standardize text
- to_datetime() → Convert to datetime format
Output Summary
- Missing values detected using boolean functions
- Column-wise analysis identified most affected features
- Invalid values converted to NaN
- Data types corrected
- Missing values handled using mean and median
- Text standardized for consistency
- Date column converted into datetime format
### **Conclusion**

The experiment demonstrates how raw datasets can be cleaned and transformed using Pandas. Instead of removing incomplete data, imputation techniques were applied to preserve data integrity. The final dataset becomes clean, consistent, and suitable for further analysis, highlighting the importance of data preprocessing.
