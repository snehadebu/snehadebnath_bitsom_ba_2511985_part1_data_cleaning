# Data Cleaning Log

## Issues Identified

1. Inconsistent text formatting in customer names, regions, categories, segments, and ship modes.
2. Mixed date formats in order_date and ship_date columns.
3. Missing values in selected fields.
4. Invalid discount values including negative discounts and discounts above acceptable business thresholds.
5. Duplicate records and duplicate order IDs.
6. Inconsistent order and payment statuses.
7. Calculation differences between provided sales/profit values and recalculated values.

## Cleaning Actions Performed

* Applied TRIM() to remove leading and trailing spaces.
* Applied PROPER() to standardize text capitalization.
* Created cleaned helper columns for customer names, categories, regions, segments, and ship modes.
* Reviewed mixed date formats and flagged problematic records.
* Recalculated sales using quantity, unit price, and discount.
* Recalculated profit using sales and cost.
* Calculated profit margin.
* Created order month and order year fields.
* Created data quality flags for clean, warning, and invalid records.

## Business Rules Applied

* Missing region values were treated as "Unknown".
* Missing ship mode values were treated as "Unknown".
* Missing discounts were treated as 0 where applicable.
* Negative discounts were flagged as invalid.
* Discounts above the acceptable threshold were flagged as invalid.
* Refunded and cancelled orders were excluded from completed sales analysis.
* Invalid shipping records were flagged for review.

## Records Flagged

* Records with invalid discounts.
* Records with cancelled or returned status.
* Records with mixed or problematic date formats.
* Records with shipping date anomalies.

## Assumptions

* Original sales and profit values were retained for comparison.
* Mixed date formats were not force-corrected when ambiguity existed.
* Business rules were applied consistently across all records.

## Limitations

* Some source records contained ambiguous date formats.
* Automated cleaning may not resolve all business-specific exceptions.
* Additional validation may be required before production reporting.
