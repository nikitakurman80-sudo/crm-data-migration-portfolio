# CRM Data Migration — Data Quality Report

**Project:** CRM Data Migration & SQL Validation  
**Prepared by:** Mykyta Kurman  
**Dataset:** 1,000 synthetic customer records  
**Tools:** Microsoft Excel, CSV  
**Project Stage:** Data Profiling & Data Cleaning

## 1. Executive Summary

This project simulates a customer data migration from a legacy CRM system to a new SaaS platform.

The objective was to identify data quality issues, standardize valid records, and flag unresolved issues before migration.

The source dataset contained 1,000 customer records across seven fields.

## 2. Data Quality Assessment

| Data Quality Issue | Findings | Action Taken |
|---|---:|---|
| Duplicate Customer IDs | 10 duplicate pairs (20 affected rows) | Flagged for manual review |
| Missing Emails | 10 | Flagged for investigation |
| Invalid Email Formats | 10 | Identified through validation |
| Email Formatting Issues | 8 | Normalized case and whitespace |
| Invalid Phone Numbers | 8 | Marked REVIEW_REQUIRED |
| Invalid Signup Dates | 6 | Marked REVIEW_REQUIRED |
| Invalid Customer Statuses | 5 | Marked REVIEW_REQUIRED |

*Counts represent issue categories and should not be added together as a count of unique affected customers.*

## 3. Data Cleaning Methodology

### Duplicate Detection

Used Excel COUNTIF logic to identify duplicate customer IDs. Conflicting records were flagged as `REVIEW_REQUIRED` rather than automatically deleted or merged.

### Email Standardization

Applied Excel text functions to remove unnecessary whitespace and convert email addresses to lowercase.

Eight email values required formatting changes.

Missing and invalid email addresses were preserved for further investigation.

### Phone Validation

Validated phone numbers against the project's required 10-digit format.

Eight records failed validation and were flagged for manual review.

### Date Validation

Checked signup dates using Excel date conversion functions.

Six invalid dates were identified and marked for investigation.

### Status Validation

Validated customer statuses against the permitted values `active` and `inactive`.

Five records contained unsupported status values.

## 4. Migration Readiness

**Current status: NOT READY FOR FINAL IMPORT**

The dataset has completed initial profiling and rule-based cleaning.

Outstanding issues require further review before production migration, including duplicate identity conflicts, missing or invalid emails, phone numbers, dates, and statuses.

## 5. Next Steps

1. Define source-to-target CRM field mappings.
2. Establish handling rules for unresolved records.
3. Validate cleaned data using SQL.
4. Simulate migration into a target database.
5. Reconcile source and target record counts.
6. Document migration results and remaining exceptions.

## 6. Skills Demonstrated

- Data Profiling
- Data Quality Assessment
- Excel Data Validation
- Data Cleaning and Standardization
- Duplicate Detection
- Exception Handling
- Migration Readiness Assessment
- Technical Documentation

**Note:** This is a simulated portfolio project using synthetic data, not a production customer migration.
