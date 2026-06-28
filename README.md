# Part 1 - Business Data Cleaning, Validation & Excel Reporting

## Repository Information

This repository contains the complete solution for **Part 1: Business Data Cleaning, Validation & Excel Reporting**.

The objective was to clean, validate, and prepare a retail sales dataset for business analysis using Microsoft Excel.

---

# Folder Structure

```
part1_data_cleaning/

├── data/
│   ├── raw_orders.xlsx
│   └── cleaned_orders.xlsx
│
├── outputs/
│   ├── data_quality_report.xlsx
│   ├── pivot_summary.xlsx
│   └── cleaning_log.md
│
├── screenshots/
│   ├── raw_data_preview.png
│   ├── cleaned_data_preview.png
│   ├── pivot_summary_1.png
│   └── pivot_summary_2.png
│
└── README.md
```

---

# Problem Summary

The retail order dataset contained several data quality issues including:

- Missing values
- Duplicate records
- Duplicate Order IDs
- Mixed date formats
- Invalid discounts
- Inconsistent text formatting
- Sales and profit calculation mismatches
- Invalid shipping dates

The objective was to clean the dataset and generate analysis-ready reports.

---

# Dataset Description

The dataset contains retail order information including:

- Order ID
- Customer Details
- Product Information
- Region
- Category
- Sales
- Cost
- Profit
- Discount
- Shipping Details
- Payment Status
- Order Status

---

# Tools Used

- Microsoft Excel
- Excel Tables
- Pivot Tables
- Excel Formulas
- Conditional Formatting
- Data Validation

---

# Data Cleaning Steps

The following cleaning steps were performed:

### Text Cleaning

- Removed extra spaces
- Standardized capitalization
- Corrected inconsistent text values

### Date Cleaning

- Converted dates into a consistent format
- Validated order and shipping dates
- Calculated shipping delay

### Missing Value Handling

- Missing Region → Unknown
- Missing Ship Mode → Unknown
- Missing Discount → 0 (where applicable)

### Duplicate Handling

- Removed exact duplicate records
- Flagged duplicate Order IDs with conflicting information

### Business Rule Validation

- Invalid discounts identified
- Shipping date validation
- Payment status validation
- Order status validation

---

# Calculated Columns

The following calculated columns were created:

- cleaned_discount
- calculated_sales
- calculated_profit
- profit_margin
- shipping_delay_days
- order_month
- order_year
- data_quality_flag

---

# Business Rules Applied

- Missing Region → Unknown
- Missing Ship Mode → Unknown
- Missing Discount → 0
- Negative Discount → Invalid
- Discount greater than allowed range → Invalid
- Cancelled Orders excluded from completed sales summary
- Failed Payments excluded from completed sales summary
- Refunded Orders summarized separately
- Ship Date before Order Date flagged as Invalid

---

# Data Quality Issues Identified

The following quality issues were analyzed:

- Missing Values
- Duplicate Records
- Duplicate Order IDs
- Invalid Discounts
- Date Issues
- Order Status Issues
- Sales and Profit Mismatches

A complete summary is available in:

```
outputs/data_quality_report.xlsx
```

---

# Pivot Reports Created

The following Pivot Tables were developed:

1. Sales and Profit by Region
2. Sales and Profit by Category and Sub-Category
3. Order Count by Ship Mode
4. Average Profit Margin by Customer Segment
5. Refunded, Cancelled and Failed Orders by Region
6. Monthly Sales Trend

---

# Key Business Insights

- Regional sales performance can be compared using the Region Pivot Report.
- Product category profitability is summarized by Category and Sub-Category.
- Monthly sales trends support seasonal business analysis.
- Shipping methods with the highest order volume were identified.
- Cancelled, refunded and failed payment orders were separately analyzed.
- Data quality issues were identified and documented for future improvements.

---

# Assumptions

- Missing discounts were treated as zero where business rules permitted.
- Unknown values were retained instead of deleting records.
- Discount values above the allowed limit were treated as invalid.
- Duplicate Order IDs with conflicting values were retained for manual review.

---

# Limitations

- Some duplicate records require manual business verification.
- Data quality depends on source system accuracy.
- Category standardization was based on observed inconsistencies.

---

# Screenshots Included

The repository contains the following screenshots:

- Raw Dataset Preview
- Cleaned Dataset Preview
- Sales and Profit by Region Pivot Table
- Monthly Sales Trend Pivot Table

---

# Deliverables

This repository includes:

- Raw Dataset
- Cleaned Dataset
- Data Quality Report
- Pivot Summary Report
- Cleaning Log
- Screenshots
- README Documentation

