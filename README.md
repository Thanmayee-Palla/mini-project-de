P&L and Workforce Analysis

Overview

This project consolidates financial and HR data from two companies (TechNova Industries and Nova AI) to provide comprehensive P&L reporting and workforce analytics for fiscal year 2025.

Key Performance Indicators (KPIs)

1. Monthly Consolidated Revenue - Total revenue across both companies with month-over-month growth
2. Cost of Sales by Month - Direct costs to deliver products and services
3. Monthly Gross Profit Margin - Profitability percentage after cost of sales
4. Operating Expense Breakdown - Overhead costs by category and company
5. Average Compensation by Position - Total compensation grouped by position level
6. Net Profit by Month - Bottom-line profitability after all expenses
7. Overtime and Bonus Analysis - Variable compensation by department
8. Cost per Department - Total departmental costs including payroll
9. Headcount Distribution by Department - Active employee count by department
10. Payroll Cost as % of Revenue - Labor efficiency ratio

Data Sources

AWS S3 Bucket: s3://de-mini-project-123/

- company.csv
- departments.csv
- employee.csv
- payroll.csv
- general_ledgers.csv
- accounts.csv

Architecture

Bronze Layer - Raw data ingestion from S3
Silver Layer - Data cleansing and transformation
Gold Layer - Dimensional model with fact tables, dimension tables, and analytical cubes

KPIs use pre-aggregated cubes (cube_financial and cube_hr_workforce) for optimized query performance.

Implementation

1. Bronze Layer - Run 01_bronze/nb_bronze_s3_ingest
2. Silver Layer - Run all notebooks in 02_silver/
3. Gold Layer - Run notebooks in 03_gold/ in sequence:
   - 01_dims/ (dimension tables)
   - 02_fact/ (fact tables)
   - 03_cubes/ (analytical cubes)
   - 04_kpis/ (KPI calculations using cubes)

Technology Stack

- Platform: Databricks on AWS
- Storage: Delta Lake
- Catalog: Unity Catalog (plworkforce_catalog)
- Processing: Apache Spark (PySpark and SQL)

Data Summary

- 2 companies
- 13 months (January 2025 - January 2026)
- 17,000+ financial transactions
- 2,700+ payroll records
- 1,300+ employees

Project: P&L and Workforce Analysis
Catalog: plworkforce_catalog