# Part 1: Business Data Cleaning, Validation & Excel Reporting

## Project Overview

This project focuses on cleaning, validating, and analyzing retail order data exported from multiple business systems. The raw dataset contained data quality issues such as missing values, duplicate records, inconsistent text formatting, mixed date formats, and invalid discount values.

The objective was to prepare an analysis-ready dataset, apply business validation rules, generate data quality reports, and create management-friendly summary reports using Excel and Google Sheets.

---

## Dataset Description

Dataset Name: raw_orders.xlsx

The dataset contains retail order-level information including:

- Order ID
- Order Date
- Ship Date
- Customer Information
- Region, State, and City
- Product Category and Sub-category
- Quantity
- Unit Price
- Discount
- Sales
- Cost
- Profit
- Payment Status
- Order Status

---

## Tools Used

- Microsoft Excel
- Google Sheets
- Pivot Tables
- Excel Functions
  - TRIM()
  - PROPER()
  - COUNTIF()
  - IF()
  - DATEVALUE()

---

## Data Cleaning Activities Performed

### Text Standardization

The following fields were cleaned and standardized:

- Customer Name
- Segment
- Region
- State
- City
- Category
- Sub-category
- Ship Mode

Actions performed:

- Removed leading and trailing spaces
- Standardized capitalization
- Corrected inconsistent category names
- Created helper columns for cleaned values

### Date Validation

The following date fields were reviewed:

- Order Date
- Ship Date

Actions performed:

- Standardized date formats
- Flagged mixed date formats
- Identified invalid shipping records
- Calculated shipping delay days

### Duplicate Handling

- Duplicate Order IDs identified: 63
- Exact Duplicate Records identified and removed: 75
- Remaining cleaned records retained for analysis

### Discount Validation

Business validation checks were applied:

- Negative discounts identified: 16
- Discounts above 50% identified: 7

### Calculated Fields Created

The following calculated fields were added:

- cleaned_discount
- calculated_sales
- calculated_profit
- profit_margin
- shipping_delay_days
- order_month
- order_year
- data_quality_flag

---

## Business Rules Applied

- Missing Region values were treated as "Unknown"
- Missing Ship Mode values were treated as "Unknown"
- Missing Discounts were treated as 0 where applicable
- Negative Discounts were flagged as Invalid
- Discounts above acceptable limits were flagged as Invalid
- Cancelled Orders were excluded from completed sales reporting
- Refunded Orders were analyzed separately
- Invalid shipping records were flagged for review

---

## Data Quality Summary

### Missing Values

| Issue | Count |
|---------|---------|
| Missing Region | 93 |
| Missing Ship Mode | 89 |
| Missing Discount | 85 |

### Duplicate Analysis

| Metric | Count |
|---------|---------|
| Duplicate Order IDs | 63 |
| Exact Duplicate Records | 75 |
| Records Flagged | 201 |

### Discount Issues

| Issue | Count |
|---------|---------|
| Negative Discounts | 16 |
| Discounts Above 50% | 7 |

### Date Issues

| Issue | Count |
|---------|---------|
| Mixed Date Formats | Yes |
| Invalid Shipping Records | 199 |

### Final Record Quality

| Status | Count |
|---------|---------|
| Clean | 711 |
| Warning | 171 |
| Invalid | 30 |

---

## Pivot Reports Created

The following pivot summaries were created:

1. Sales and Profit by Region
2. Sales and Profit by Category and Sub-category
3. Order Count by Ship Mode
4. Profit Margin by Customer Segment
5. Refunded / Cancelled Orders by Region
6. Monthly Sales Trend

---

## Key Business Insights

- South region generated the highest overall sales.
- Technology and Furniture categories contributed significantly to revenue.
- Standard Class shipping accounted for the highest order volume.
- Several records contained shipping date anomalies requiring operational review.
- A notable number of records contained missing values and duplicate information.
- Data quality improvements significantly enhanced reporting reliability.

---

## Assumptions

- Missing discounts were treated as zero when appropriate.
- Mixed date formats were standardized where possible.
- Duplicate records identified as exact duplicates were removed.
- Original source data was preserved separately for audit purposes.

---

## Limitations

- Some date values were ambiguous due to inconsistent source formatting.
- Business-specific validation rules may differ from operational systems.
- Additional manual review may be required for flagged records.

---

## Repository Contents

data/
- raw_orders.xlsx
- cleaned_orders.xlsx

outputs/
- data_quality_report.xlsx
- pivot_summary.xlsx
- cleaning_log.md

screenshots/
- raw_data_preview.png
- cleaned_data_preview.png
- pivot_summary_1.png
- pivot_summary_2.png

---

## Screenshots

Screenshots have been included in the screenshots folder as evidence of:

- Raw dataset review
- Cleaned dataset output
- Pivot analysis outputs
- Reporting activities
