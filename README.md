# Customer Sales Data Cleaning & Preprocessing (EDA)

A structured data cleaning pipeline built with Python and pandas to transform raw, inconsistent transactional data into an analysis-ready dataset.

## Key Issues Identified & Handled
* **Missing Values:** Handled across critical columns using median and mode imputation; dropped records with missing core identifiers (`Customer_ID`).
* **Text Normalization:** Standardized string values (`Gender`, `City`, `Country`) to lowercase, trimmed unnecessary whitespaces, and mapped country code variations (e.g., `ind` $\rightarrow$ `india`).
* **Duplicate Records:** Removed identical duplicate rows and deduplicated unique customer records.
* **Outlier Treatment:** 
  * Filtered out non-realistic `Age` entries (<15 and >100) before imputing with the median.
  * Removed negative `Purchase_Amount` values and handled extreme skewness using IQR-based capping (Winsorization).
* **Logical Consistency:** Enforced temporal validation by removing invalid entries where `Last_Purchase_Date` preceded `Signup_Date`.
* **Type Casting:** Converted string dates into proper `datetime64` format and standardized numeric types.

## Tech Stack
* Python
* pandas
* matplotlib

## Project Structure
* `Data Cleaning (EDA).ipynb` - Step-by-step Jupyter Notebook detailing the data cleaning pipeline.
* `messy_customer_sales_data.csv` - Original dataset with inconsistencies, null values, and outliers.
* `cleaned_customer_sales_data.csv` - Final transformed, cleaned dataset ready for downstream analysis or ML modeling.
