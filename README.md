# ☕ Cafe Sales Data Cleaning Using SQL (PostgreSQL)

## 📌 Project Overview

Data quality is one of the most critical aspects of data analysis. Before performing any meaningful analysis, datasets must be cleaned and standardized to ensure accuracy and reliability.

In this project, I performed end-to-end data cleaning on a Cafe Sales dataset containing **10,000 transaction records** using **PostgreSQL**. The dataset contained multiple data quality issues, including missing values, invalid entries, inconsistent formats, and incorrect calculations.

The goal was to transform the raw dataset into a clean, structured, and analysis-ready dataset that can be used for reporting and business decision-making.

---

## 🎯 Objectives

- Identify data quality issues in the raw dataset
- Handle missing and invalid values
- Standardize inconsistent records
- Validate transaction calculations
- Convert data into appropriate data types
- Create a clean dataset ready for analysis

---

## 🛠️ Tools Used

- PostgreSQL
- SQL
- CSV Dataset
- GitHub

---

## 📊 Dataset Information

| Attribute | Description |
|------------|------------|
| transaction_id | Unique transaction identifier |
| item | Product sold |
| quantity | Quantity purchased |
| price_per_unit | Price per item |
| total_spent | Total transaction amount |
| payment_method | Payment mode used |
| store_location | Store location |
| transaction_date | Date of transaction |

**Total Records:** 10,000

---

# 🔍 Data Quality Issues Identified

The dataset contained the following issues:

### Missing Values
- NULL values
- Blank values

### Invalid Entries
- UNKNOWN
- ERROR
- N/A

### Data Type Issues
- Numeric fields stored as text
- Invalid date values

### Calculation Errors
- Incorrect Total Spent values
- Missing Price Per Unit values

### Inconsistent Values
- Payment methods
- Store locations
- Product information

---

# 🧹 Data Cleaning Process

## 1. Data Exploration

Performed an initial assessment of the dataset to identify:

- Missing values
- Invalid records
- Data type inconsistencies
- Duplicate and incorrect entries

Example:

```sql
SELECT *
FROM cafe_sales_raw;
```

---

## 2. Handling Missing & Invalid Values

Cleaned fields containing:

- NULL
- UNKNOWN
- ERROR
- Blank values

Used SQL functions such as:

```sql
CASE WHEN
COALESCE()
NULLIF()
TRIM()
```

---

## 3. Data Standardization

Standardized values across:

### Item

Replaced invalid item names with appropriate values.

### Payment Method

Standardized payment methods and replaced missing entries.

### Store Location

Corrected inconsistent store location records.

---

## 4. Data Type Conversion

Converted columns into appropriate data types.

Examples:

```sql
CAST(quantity AS INT)

CAST(price_per_unit AS NUMERIC(10,2))

CAST(total_spent AS NUMERIC(10,2))
```

---

## 5. Recalculating Transaction Amounts

Validated and recalculated transaction totals using:

```sql
total_spent = quantity * price_per_unit
```

This ensured transaction accuracy throughout the dataset.

---

## 6. Date Cleaning

Handled:

- NULL dates
- Invalid dates
- UNKNOWN dates

Converted valid records into standard PostgreSQL date format.

---

## 7. Creating Final Clean Dataset

Created a final cleaned table:

```sql
CREATE TABLE clean_cafe_sales_data AS
SELECT ...
```

The final dataset is ready for reporting and business analysis.

---

# ✅ Data Validation Checks

Performed quality checks to verify:

- No invalid quantities
- No invalid prices
- No invalid payment methods
- Correct transaction totals
- Consistent date formats
- Successful data type conversions

---

# 📈 Results

### Before Cleaning

❌ Missing values

❌ Invalid entries

❌ Inconsistent formats

❌ Incorrect calculations

❌ Analysis not reliable

### After Cleaning

✅ Clean and structured dataset

✅ Standardized values

✅ Accurate calculations

✅ Consistent data types

✅ Analysis-ready data

---

# 💡 SQL Concepts Demonstrated

- Data Cleaning
- Data Transformation
- Data Validation
- CASE Statements
- COALESCE()
- NULLIF()
- CAST()
- CTEs (Common Table Expressions)
- Aggregate Functions
- Data Standardization
- Table Creation

---

# 🚀 Key Learnings

Through this project, I gained hands-on experience in:

- Real-world data cleaning techniques
- Data quality assessment
- PostgreSQL data transformation
- Handling missing and inconsistent data
- Preparing datasets for analytics projects

---

# 📂 Project Structure

```text
Cafe-Sales-Data-Cleaning-SQL/
│
├── Dataset/
│   ├── dirty_cafe_sales.csv
│   └── clean_cafe_sales.csv
│
├── SQL/
│   └── Data_cleaning.sql
│
├── Screenshots/
│   ├── raw_data.png
│   ├── cleaning_process.png
│   └── final_dataset.png
│
└── README.md
```

---

# 👨‍💻 Author

**Ganesh Kurmi**

Financial Data Analyst | SQL | Power BI | Excel

### Connect With Me

- LinkedIn: *(Add your LinkedIn URL)*
- GitHub: *(Add your GitHub URL)*

---

⭐ If you found this project useful, feel free to star the repository.
