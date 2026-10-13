
# Financial Analysis Dashboard

## Project Description

This project is an end-to-end financial transaction analysis built using Microsoft Power BI. It cleans and models two raw CSV files (transactions and customers), creates DAX measures for transaction volume, value, fees, taxes, and year-over-year (YoY) comparisons, and presents the results in a dark-themed, two-page interactive dashboard titled **Finance Analysis**.

The dashboard allows users to filter data by Year, Occupation, and Merchant Category, switch the headline metric using a Dynamic Metric selector, and drill down from a high-level overview to individual transaction records.

## Tech Stack

- **Tool:** Microsoft Power BI Desktop
- **Data Preparation:** Power Query
- **Calculations:** DAX
- **Data Sources:** CSV files

## Functions Used

- **Power Query:** `Csv.Document`, `Table.PromoteHeaders`, `Table.TransformColumnTypes`, `Table.Distinct`, `Text.Trim`, `Number.Abs`, `Table.ReplaceValue`, `Text.Upper`, `Table.CombineColumns`
- **DAX:** `SUM`, `DISTINCTCOUNT`, `AVERAGE`, `CALCULATE`, `SAMEPERIODLASTYEAR`, `DIVIDE`, `SELECTEDVALUE`, `CALENDAR`, `MIN`, `MAX`, `NAMEOF`

## Data Source

The dataset was sourced from Kaggle and consists of two files:

- **finance_transactions.csv** — 50,000 rows containing transaction details such as transaction ID, date, account ID, customer ID, transaction type, channel, merchant category, amount, fees, taxes, currency, transaction status, fraud indicator, risk score, and reference number.
- **customers.csv** — 5,000 rows containing customer details such as customer ID, gender, date of birth, city, state, occupation, customer segment, annual income, joining date, and name.

**Data Period:** January 1, 2023 – April 30, 2026  
**Currency:** Indian Rupees (INR)

## Features and Highlights

- Two report pages: Overview Analysis and Transaction Detail View.
- Five headline KPIs on both pages:
  - Total Amount
  - Total Transactions
  - Average Transaction Value
  - Total Fees
  - Total Tax
- Interactive slicers for Year, Dynamic Metric, Occupation, and Merchant Category.
- Dynamic header card displaying the selected metric and year.
- Year-over-year (YoY) comparisons for transaction amount, transaction count, average value, fees, and tax.
- Transaction breakdowns by month, transaction status, customer segment, state, gender, and transaction type.
- Transaction-level detail table with 10 fields for audit and drill-down.
- Data cleaning, including duplicate removal, missing fee handling, text standardization, and merging customer names.

## Business Problem and Goals

### Business Problem

A financial organization needs a centralized Finance Analytics Dashboard to monitor financial transactions, customer behavior, fees, taxes, and transaction performance across business segments and regions.

The management team faces challenges in tracking:

- Overall transaction growth and financial performance.
- Monthly trends in transaction amounts.
- Successful, failed, and pending transactions.
- Customer segment contribution.
- State-wise financial performance.
- Transaction type performance.
- Gender-based customer analysis.
- Year-over-year performance changes.

### Goals of the Dashboard

- Monitor key financial KPIs in one place.
- Identify high-performing customer segments and states.
- Analyze transaction patterns and trends.
- Track operational fees and taxes.
- Understand customer demographics.
- Support better financial decision-making and business strategy.

## Interactive Filters

Users can filter the dashboard using:

- **Year**
- **Dynamic Metric**
- **Occupation**
- **Merchant Category**

## KPI Requirements

- **Total Amount:** Total transaction amount processed, with YoY growth comparison.
- **Total Transactions:** Number of transactions performed and yearly volume changes.
- **Average Transaction Value:** Average amount per transaction.
- **Total Fees:** Total fees collected from transactions.
- **Total Tax:** Total tax generated from transactions.

## Chart Requirements

- **Total Amount by Month — Area Chart:** Analyzes monthly transaction trends and identifies seasonal spikes or drops.
- **Total Amount by Transaction Status — Donut Chart:** Compares successful, failed, and pending transaction amounts.
- **Total Amount by Customer Segment — Horizontal Bar Chart:** Identifies the most valuable segments: Retail, Premium, SME, Corporate, and Wealth.
- **Total Amount by State — Horizontal Bar Chart:** Compares states to identify top-performing regions.
- **Transaction Type Analysis — Table:** Compares amount, fees, tax, and transaction count across 10 transaction types.
- **Total Amount by Gender — Donut Chart:** Shows transaction value distribution between male and female customers.

The second dashboard page provides a detailed grid view for drilling down into individual transaction records.

## Dashboard Walkthrough

### Page 1 — Overview Analysis

- **Navigation Panel:** Page navigation and four slicers for Year, Dynamic Metric, Occupation, and Merchant Category.
- **Header and KPI Cards:** Dashboard title, dynamic metric/year card, and five KPIs.
- **Monthly Trend:** Area chart showing transaction value trends and growth.
- **Transaction Status:** Donut chart showing the share of transaction value classified as Success, Failed, or Pending.
- **Customer Segment:** Bar chart comparing transaction value across Retail, Premium, SME, Corporate, and Wealth.
- **State Analysis:** Bar chart showing transaction value by customer state.
- **Transaction Type Analysis:** Table comparing amount, fees, tax, and transaction count across 10 transaction types.
- **Gender Analysis:** Donut chart showing transaction value distribution between female and male customers.

### Page 2 — Transaction Details

- Consistent navigation, slicers, header, and KPI cards.
- Transaction-level detail table containing:
  - Transaction ID
  - Transaction Date
  - Transaction Type
  - Transaction Status
  - Gender
  - Customer Segment
  - State
  - Amount
  - Fees
  - Tax

This page supports detailed transaction checking and drill-down analysis.

## Business Impact and Key Insights

### 1. Transaction Scale and Fee Yield

- Total transaction value: **₹455.53 million (₹45.55 crore)**.
- Total transactions: **50,000**.
- Average transaction value: **₹9,110.68**.
- Total fees: **₹7.26 lakh**, approximately 0.16% of transaction value.
- Total tax: **₹1.31 lakh**, approximately 0.03% of transaction value.

Fee income is relatively small compared with the total transaction value processed.

### 2. Growth Trends

- Transaction value was ₹137.07 million in 2023, ₹135.62 million in 2024, and ₹137.53 million in 2025.
- Year-over-year growth was -1.1% in 2024 and +1.4% in 2025.
- Transaction volume remained close to 15,000 transactions annually.
- January–April 2026 recorded ₹45.32 million compared with ₹45.86 million in the same period of 2025, a decline of 1.2%.
- Monthly transaction value generally remained between ₹10 million and ₹12.5 million, with no clear seasonal peak.

### 3. Transaction Type Contribution

- Loan EMI contributed ₹130.93 million, or 28.7% of total transaction value.
- Transfers contributed ₹120.63 million, or 26.5%.
- Together, these two transaction types accounted for 55.2% of total value while representing 35% of transactions.
- Adding Deposits and Investments brought the contribution of the top four transaction types to 81.1%.
- These transaction types had an average transaction value of approximately ₹14,000, compared with around ₹5,000 or less for several other transaction types.

### 4. Transaction Status Analysis

- Failed transactions accounted for ₹47.46 million, or 10.4% of total transaction value, across 5,096 transactions.
- Pending transactions accounted for ₹19.06 million, or 4.2% of total value.
- Together, failed and pending transactions represented 14.6% of transaction value.
- Failed transactions had an average value of ₹9,312, compared with ₹9,075 for successful transactions.
- ₹75,458 in fees was recorded against failed transactions, representing approximately 10% of total fees. This may require further review.

### 5. Customer Segment Analysis

- Retail contributed 54.5% of total transaction value.
- Premium contributed 18.5%.
- SME contributed 15.8%.
- Corporate contributed 6.8%.
- Wealth contributed 4.5%.

Average transaction values were similar across segments, ranging from approximately ₹9,000 to ₹9,150. This suggests that differences in total value are more closely related to transaction volume than to average transaction size.

### 6. Geographic and Gender Analysis

- Maharashtra contributed 15.0% of total transaction value, amounting to ₹68.29 million.
- Karnataka contributed 11.6%.
- Gujarat contributed 11.0%.
- These three states accounted for 37.6% of total transaction value.
- Telangana and Chandigarh were among the smallest contributors, at approximately 4% each.
- Female customers accounted for 51.7% of transaction value, while male customers accounted for 48.3%.

### 7.Snapshots
[Snapshot1](https://github.com/vaishnavig824-cmd/finance-analysis-dashboard/blob/main/Snapshots%20of%20the%20Dashboard/Screenshot%201%20Finance.png)
[Snapshot2](

