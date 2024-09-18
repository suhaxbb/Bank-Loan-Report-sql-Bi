# Bank Loan Report Dashboard

# Overview
This project involves creating a comprehensive Bank Loan Report Dashboard using SQL to query the loan data and Power BI for visualization.

The dashboard provides insights into loan applications, funded amounts, interest rates, and loan statuses, offering both high-level overviews and granular breakdowns of loan performance.

# Project Structure

SQL Queries: Queries were used to extract and transform data from the financial loan database.

Power BI: Connected the SQL database to Power BI, and used various visualizations to analyze the data.

DAX Formulas: Used DAX to calculate KPIs such as monthly loan performance, average interest rates, and debt-to-income (DTI) ratios.
Key Features

# Loan Performance Breakdown
Analyzed loans by term (36 vs 60 months), state, purpose (e.g., debt consolidation, home improvement), and employee length.

# Dynamic Filters
Filters by grade, purpose, and homeownership (e.g., rent vs mortgage) to customize analysis.

# Monthly and Yearly Comparisons
Month-over-month and year-over-year tracking, including metrics like loan applications, funded amounts, and interest rates.

# Good vs Bad Loans
Highlighted loan health by classifying loans into good (fully paid or current) and bad (charged off) categories, calculating their financial impact.

# SQL Queries

The following SQL queries were used to extract the relevant data:

Total Loan Applications:
SELECT COUNT(id) AS total_loan_applications FROM financial_loan;

Funded Amounts:
SELECT SUM(loan_amount) AS Total_Funded_Amount FROM financial_loan;

Interest Rates:
SELECT AVG(int_rate) * 100 AS Avg_Interest_Rate FROM financial_loan;

Good Loan Percentage:
SELECT 
(COUNT(CASE WHEN loan_status = 'Fully Paid' OR loan_status = 'Current' THEN id END) * 100) / 
COUNT(id) AS Good_Loan_Percentage 
FROM financial_loan;

# DAX Formulas

Key metrics were calculated using DAX formulas in Power BI:

Total Funded Amount (DAX):
Total Funded Amount = SUM(financial_loan[loan_amount])

Good Loan Applications (DAX):
Good Loan Applications = CALCULATE(COUNT(financial_loan[id]), 
financial_loan[loan_status] = "Fully Paid" || financial_loan[loan_status] = "Current")

Average Interest Rate (DAX):
Avg Interest Rate = AVERAGE(financial_loan[int_rate]) * 100


# Key Visualizations

The dashboard includes a variety of visualizations designed to provide actionable insights:

KPI Cards: Highlight total loan applications, funded amounts, and other key metrics.

Bar Charts: Break down loans by categories such as loan term, employee length, and purpose.

Line Graphs: Show trends in monthly and yearly loan applications and funded amounts.

Pie Charts: Display the distribution of good vs. bad loans and their respective financial impacts.

Filters: Enable dynamic analysis with filters based on grade, state, loan purpose, and homeownership.


# How to Run the Project

Database Setup:

Ensure that the financial loan data is stored in a relational database.
Run the SQL queries provided to extract the necessary data.

Power BI Setup:

Connect Power BI to the SQL database.

Use the extracted data to create visualizations such as bar charts, line graphs, and KPIs.
Apply the provided DAX formulas to calculate key metrics.

Visualization:

Add dynamic filters to the dashboard for more detailed analysis (e.g., by loan purpose, term, or grade).
Generate insights and visual reports on loan performance, bad vs good loans, and financial metrics.

# Conclusion

This dashboard provides valuable insights into bank loan data and serves as a powerful tool for analyzing trends, performance metrics, and risk factors in loan portfolios.




