# Practical13

Aim: To perform processing on a dataset and dealing with missing values.

Theory :

In data science, missing values are often represented as NaN (Not a Number).
Handling missing values is a critical data preprocessing step in Python, as missing data can skew analysis, reduce model accuracy, and cause algorithms to fail.
Replacing missing values with statistical estimates. Common strategies include using the Mean (average), Median (middle value), or a constant like 0.
Correcting inconsistencies, such as different date formats or varying text capitalization (e.g., "cse" vs "CSE"), to ensure data integrity.

isna(): Returns a Boolean DataFrame (True/False) indicating where values are missing.

notna(): The inverse of isna(), returning True for cells that contain valid data.

sum(): When chained with isna(), it counts the total number of missing values per column.

sum(axis=1): Calculates the count of missing values for each individual row.

dropna(): Removes any rows or columns that contain at least one missing value.

fillna(value): Replaces NaN entries with a specific provided value, such as a constant or a calculated mean.

replace(old, new): Searches for specific characters or placeholders (like "-") and swaps them with actual NaN objects.

to_numeric(): Converts column data types to numbers, turning unparseable data into NaN if errors='coerce' is used.

mean(): Calculates the mathematical average of a column, often used to fill gaps in numerical data.

median(): Identifies the middle value of a dataset, which is useful for imputation when data has outliers.

str.upper(): Converts all text in a string column to uppercase to ensure categorical consistency.

pd.to_datetime(): Converts various string representations of dates into a unified, standard date-time format.

Conclusion:

The program demonstrates that Data Wrangling is a multi-step process. By successfully replacing inconsistent placeholders with NaN, imputing gaps with statistical averages (Mean/Median), and standardizing text and date formats, the raw dataset is transformed into a clean, "tidy" format ready for reliable analysis.
