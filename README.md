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

The following steps outline the systematic approach taken in the code to clean the student dataset:

Initialization: Define the raw dataset using a dictionary and load it into a Pandas DataFrame.

Detection & Replacement:

Identify non-standard missing markers (like "-").

Use replace() to convert these markers into np.nan so Pandas can recognize them as nulls.

Type Casting:

Convert the Age and Marks columns from objects/strings to float/int using pd.to_numeric.

Use errors='coerce' to ensure any remaining unparseable data becomes NaN.

Missing Value Analysis:

Calculate the total count of nulls per column using df.isnull().sum().

Imputation Strategy:

Mean Imputation: Fill missing Age values with the average age of the group.

Median Imputation: Fill missing Marks with the median score (more robust to outliers).

String Normalization:

Apply .str.upper() to the Department column to fix inconsistent capitalization.

Date Standardization:

Convert Admission_Date to a uniform YYYY-MM-DD format using pd.to_datetime.

Final Verification: Display the cleaned DataFrame to ensure no NaN values remain and formats are consistent.

Conclusion:

Through this experiment, we successfully demonstrated the essential workflow of Data Wrangling. We transformed a messy dataset containing inconsistent strings, non-standard null characters, and mixed date formats into a clean, structured format ready for analysis.

Key takeaways include:

Handled the FutureWarning by understanding that modern Pandas prefers direct assignment (e.g., df[col] = df[col].fillna(...)) over the inplace=True parameter for certain operations.

Observed how Imputation helps in retaining data rows that would otherwise be lost if we simply deleted rows with missing values.

Ensured data integrity by standardizing text and date formats, which is crucial for accurate filtering and grouping in data science projects.
