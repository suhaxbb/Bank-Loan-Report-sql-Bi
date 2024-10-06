# 💼 Bank Loan Report Dashboard

## 📝 Overview

This project involves creating a **comprehensive Bank Loan Report Dashboard** using **SQL** to query loan data and **Power BI** for visualization. The dashboard provides valuable insights into:

- Loan applications
- Funded amounts
- Interest rates
- Loan statuses

It offers both high-level overviews and granular breakdowns of loan performance, allowing stakeholders to assess loan health, track key metrics, and make informed decisions.

## 🛠️ Project Structure

1. **SQL Queries**: SQL queries were used to extract and transform data from the financial loan database.
2. **Power BI**: The SQL database was connected to Power BI to create insightful visualizations.
3. **DAX Formulas**: DAX formulas were applied to calculate KPIs such as monthly loan performance, average interest rates, and debt-to-income ratios.

## 🌟 Key Features

- **Loan Performance Breakdown**: Analyze loans by term (36 vs. 60 months), state, purpose (e.g., debt consolidation, home improvement), and employee length.
  
- **Dynamic Filters**: Filters by grade, purpose, and homeownership (e.g., rent vs mortgage) to customize the analysis.

- **Monthly and Yearly Comparisons**: Month-over-month and year-over-year tracking of metrics such as loan applications, funded amounts, and interest rates.

- **Good vs. Bad Loans**: Classify loans into good (fully paid or current) vs. bad (charged off) categories, and calculate their financial impact.

## 🖥️ SQL Queries

The following SQL queries were used to extract the relevant data:

- **Total Loan Applications**:
    ```sql
    SELECT COUNT(id) AS total_loan_applications FROM financial_loan;
    ```

- **Funded Amounts**:
    ```sql
    SELECT SUM(loan_amount) AS Total_Funded_Amount FROM financial_loan;
    ```

- **Interest Rates**:
    ```sql
    SELECT AVG(int_rate) * 100 AS Avg_Interest_Rate FROM financial_loan;
    ```

- **Good Loan Percentage**:
    ```sql
    SELECT (COUNT(CASE WHEN loan_status = 'Fully Paid' OR loan_status = 'Current' THEN id END) * 100) / COUNT(id) AS Good_Loan_Percentage FROM financial_loan;
    ```

## 📊 DAX Formulas

Key metrics were calculated using DAX in Power BI:

- **Total Funded Amount (DAX)**:
    ```DAX
    Total Funded Amount = SUM(financial_loan[loan_amount])
    ```

- **Good Loan Applications (DAX)**:
    ```DAX
    Good Loan Applications = CALCULATE(COUNT(financial_loan[id]), financial_loan[loan_status] = "Fully Paid" || financial_loan[loan_status] = "Current")
    ```

- **Average Interest Rate (DAX)**:
    ```DAX
    Avg Interest Rate = AVERAGE(financial_loan[int_rate]) * 100
    ```

## 📈 Key Visualizations

The dashboard includes a variety of visualizations to provide actionable insights:

- **KPI Cards**: Highlight key metrics such as total loan applications, funded amounts, and interest rates.
- **Bar Charts**: Display loans by categories like term, employee length, and purpose.
- **Line Graphs**: Show monthly and yearly trends for loan applications and funded amounts.
- **Pie Charts**: Visualize the distribution of good vs. bad loans and their financial impact.
- **Filters**: Allow dynamic analysis by filtering data based on grade, state, loan purpose, and homeownership.

## 🚀 How to Run the Project

### 1. Database Setup:
Ensure the financial loan data is stored in a relational database, then run the SQL queries provided to extract the necessary data.

### 2. Power BI Setup:
- **Connect Power BI** to the SQL database.
- Use the extracted data to create visualizations such as bar charts, line graphs, and KPIs.
- Apply the DAX formulas to calculate key metrics.

### 3. Visualization:
- Add **dynamic filters** to the dashboard for a detailed analysis (e.g., by loan purpose, term, or grade).
- Generate insights and create visual reports on loan performance, good vs. bad loans, and other financial metrics.

## 📌 Conclusion

The Bank Loan Report Dashboard provides valuable insights into bank loan data, serving as a powerful tool for analyzing trends, performance metrics, and risk factors in loan portfolios. With this dashboard, stakeholders can make data-driven decisions to improve loan performance and reduce risk.

---


