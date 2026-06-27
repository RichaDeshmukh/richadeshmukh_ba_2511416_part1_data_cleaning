# Data Cleaning Log

## Project
Part 1: Business Data Cleaning, Validation & Excel Reporting

---

## Objective

The objective of this project was to clean and validate the retail order dataset to produce an analysis-ready dataset for business reporting. Data quality issues were identified, corrected where possible, and documented according to the specified business rules.

---

## Issues Identified

The following data quality issues were identified during the cleaning process:

- Leading and trailing spaces in text fields
- Inconsistent text capitalization
- Mixed date formats in order_date and ship_date
- Missing values in region, ship_mode, and discount
- Duplicate Order IDs
- Exact duplicate records
- Ship dates occurring before order dates
- Missing order dates and ship dates
- Invalid discount values (negative or greater than the allowed range)
- Sales and profit calculation mismatches
- Cancelled and refunded orders
- Failed payment records

---

## Cleaning Actions Performed

### Text Cleaning

The following columns were standardized:

- customer_name
- segment
- region
- state
- city
- category
- sub_category
- ship_mode
- payment_status
- order_status

Actions performed:

- Removed leading and trailing spaces using TRIM()
- Standardized text case using PROPER()
- Corrected inconsistent category names
- Removed unnecessary spaces and formatting inconsistencies

---

### Date Cleaning

The following columns were cleaned:

- order_date
- ship_date

Actions performed:

- Converted text values into valid Excel dates
- Standardized all dates into a consistent format
- Identified missing dates
- Flagged records where ship_date occurred before order_date

---

### Duplicate Handling

Actions performed:

- Identified exact duplicate records
- Identified duplicate Order IDs
- Removed only exact duplicate rows
- Flagged duplicate Order IDs with conflicting information for manual review

---

### Missing Value Handling

Business rules applied:

- Missing Region → replaced with "Unknown"
- Missing Ship Mode → replaced with "Unknown"
- Missing Discount → replaced with 0 only when other sales fields were valid

---

### Business Rule Validation

Applied the following validations:

- Negative discount values flagged as Invalid
- Discount values above the allowed range flagged as Invalid
- Cancelled orders excluded from completed sales analysis
- Failed payment records excluded from completed sales analysis
- Refunded orders identified separately
- Ship dates earlier than order dates flagged as invalid

---

## Calculated Columns Added

The following columns were created:

- cleaned_discount
- calculated_sales
- calculated_profit
- profit_margin
- shipping_delay_days
- order_month
- order_year
- data_quality_flag

---

## Records Removed

- Exact duplicate rows were removed after validation.
- Conflicting duplicate Order IDs were retained and flagged for review.

---

## Records Flagged

Records were flagged for the following reasons:

- Missing required values
- Invalid discount
- Invalid shipping dates
- Duplicate Order IDs
- Calculation mismatches

---

## Assumptions

- Missing discounts were treated as zero only when all other sales-related fields were valid.
- Discount values greater than 100% were considered invalid.
- Unknown values were retained instead of deleting records to preserve business data.

---

## Limitations

- Some conflicting duplicate records require manual business verification.
- Category standardization was performed based on visible inconsistencies only.
- Business rules were applied only according to assignment requirements.

---

## Output Files Generated

- cleaned_orders.xlsx
- data_quality_report.xlsx
- pivot_summary.xlsx
- cleaning_log.md