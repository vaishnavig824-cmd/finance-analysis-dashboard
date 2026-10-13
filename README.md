Financial Analysis Dashboard

Description

This project is an end-to-end financial transaction analysis built in Microsoft Power BI. It cleans and models two raw CSV files (transactions and customers), builds DAX measures for volume, value, fees, tax and year-over-year comparison, and presents the results in a dark-themed, two-page interactive dashboard titled “Finance Analysis”.
The dashboard lets a user slice the data by Year, Occupation and Merchant Category, switch the headline metric with a Dynamic Metric selector, and drill from a high-level overview down to individual transaction records.

Tech Stack

1	Tool: Microsoft Power BI Desktop
2 Data preparation: Power Query 
3	Calculations: DAX
4	Source files: CSV

Functions used

1	Power Query: Csv.Document, Table.PromoteHeaders, Table.TransformColumnTypes, Table.Distinct, Text.Trim, Number.Abs, Table.ReplaceValue, Text.Upper, Table.CombineColumns
2	DAX: SUM, DISTINCTCOUNT, AVERAGE, CALCULATE, SAMEPERIODLASTYEAR, DIVIDE, SELECTEDVALUE, CALENDAR, MIN, MAX, NAMEOF
Data Source
The data comes from Kaggle and consists of two files:
•	finance_transactions.csv (50,000 rows): transaction_id, transaction_date, account_id, customer_id, transaction_type, channel, merchant_category, amount, fee_amount, tax_amount, currency (INR), transaction_status, is_fraud, risk_score, reference_no
•	customers.csv (5,000 rows): customer_id, gender, date_of_birth, city, state, occupation, customer_segment, annual_income, join_date, name
Data period: 1 Jan 2023 – 30 Apr 2026. All amounts are in Indian Rupees (INR). 
Features and Highlights
•	Two report pages: Overview Analysis and Transaction (detail view), connected with a page navigator
•	Five headline KPIs on every page: Total Amount, Total Transactions, Average Transaction Value, Total Fees and Total Tax
•	Left-hand slicer panel: Year, Dynamic Metric, Occupation and Merchant Category
•	Dynamic header card that shows the selected metric and selected year
•	Year-over-year measures built for amount, transactions, average value, fees and tax
•	Breakdowns by month, transaction status, customer segment, state, gender and transaction type
•	Transaction-level table with 10 fields for audit and drill-down
•	Cleaned data model: duplicates removed, missing fees filled, text standardised, names merged
Business Problem and Goals
Business problem
A financial organization wants a centralized Finance Analytics Dashboard to monitor financial transactions, customer behaviour, fees, taxes and transaction performance across business segments and regions. The management team finds it hard to track:
•	Overall transaction growth and financial performance
•	Monthly trends in transaction amounts
•	Successful vs failed transactions
•	Customer segment contribution
•	State-wise financial performance
•	Transaction type profitability
•	Gender-based customer analysis
•	Year-over-Year (YoY) performance changes
Goals of the dashboard
•	Monitor key KPIs from a single page
•	Identify high-performing customer segments and states
•	Analyse transaction patterns and trends
•	Track operational fees and taxes
•	Understand customer demographics
•	Improve financial decision-making and business strategy
Interactive filters
Users can filter the whole dashboard by Year, Dynamic Measure, Occupation and Merchant Category.
KPI requirements
•	Total Amount: total transaction amount processed, with YoY growth comparison. Measures: Total amount, PY Amount, yoy, yoy%
•	Total Transactions: number of transactions performed and yearly volume change. Measures: Total Transaction, PY transaction, yoy%
•	Average Transaction Value: average amount per transaction. Measures: Avg Transaction Value, yoy% avg
•	Total Fees: total fees collected from transactions. Measures: Total Fees, Py fees, yoy% fees
•	Total Tax: total tax generated from all transactions. Measures: Total tax, PY Tax, yoy% tax
Chart requirements
•	Total Amount by Month (area chart): analyse monthly amount trends and spot seasonal spikes or drops
•	Total Amount by Transaction Status (donut chart): compare Success, Failed and Pending amounts to measure operational efficiency and success rate
•	Total Amount by Customer Segment (horizontal bar chart): find the most valuable segments – Retail, Premium, SME, Corporate, Wealth
•	Total Amount by State (horizontal bar chart): compare states to identify top-performing regions
•	Transaction Type Analysis (table): compare Amount, Fees, Tax and Transaction count across 10 transaction types to understand profitability by category
•	Total Amount by Gender (donut chart): understand Male vs Female participation

Dashboard 2 adds a detailed grid view so users can drill down to the underlying transaction records.
Dashboard Walkthrough (Page-wise)
Page 1 – Overview Analysis
•	Left panel: page navigator and four slicers – Year, Dynamic Metric, Occupation, Merchant Category.
•	Header and KPI cards: dashboard title, dynamic metric/year card, and five KPIs – Total Amount, Total Transaction, Avg Transaction Value, Total Fees, Total Tax.
•	Total Amount by Month (area chart): monthly transaction value trend, used to check seasonality and growth.
•	Transaction Status (donut chart): share of value that is Success, Failed or Pending.
•	Customer Segment (bar chart): value by Retail, Premium, SME, Corporate and Wealth.
•	State (bar chart): value by customer state to show geographic concentration.
•	Transaction Type Analysis (table): amount, fees, tax and transaction count for each of the 10 transaction types.
•	Gender (donut chart): split of transaction value between Female and Male customers.
Page 2 – Transaction
•	Same navigation panel, slicers, header and five KPI cards as Page 1, so filters stay consistent.
•	Transaction detail table: transaction ID, date, type, status, gender, customer segment, state, amount, fees and tax – for row-level checking and drill-down.
Business Impact and Insights
•	Scale and fee yield: The business processed ₹455.53 million (₹45.55 crore) across 50,000 transactions, with an average transaction value of ₹9,110.68. Fees were ₹7.26 lakh (about 0.16% of value) and tax was ₹1.31 lakh (about 0.03%), so fee income is small compared with the money moved.
•	Growth is flat and not seasonal: Yearly value was ₹137.07M in 2023, ₹135.62M in 2024 (−1.1%) and ₹137.53M in 2025 (+1.4%), with about 15,000 transactions every year. 2026 has only four months of data, so compare like-for-like: Jan–Apr 2026 was ₹45.32M against ₹45.86M in Jan–Apr 2025 (−1.2%). Monthly value stays in a narrow ₹10–12.5M band with no clear peak season.
•	Two products drive most of the value: Loan EMI (₹130.93M, 28.7%) and Transfer (₹120.63M, 26.5%) together make up 55.2% of value from only 35% of transactions. Adding Deposit and Investment takes the top four to 81.1%. These types have an average ticket of about ₹14,000, versus about ₹5,000 or less for Card Payment, Bill Payment, Withdrawal and the remaining types.
•	14.6% of transaction value did not complete: Failed transactions total ₹47.46M (10.4% of value, 5,096 transactions) and Pending ones ₹19.06M (4.2%). Failed transactions also have a higher average value (₹9,312) than successful ones (₹9,075). In addition, ₹75,458 of fees (about 10% of all fees) is recorded against failed transactions, which is worth reviewing.
•	Retail customers carry the business: Retail contributes 54.5% of value, followed by Premium (18.5%), SME (15.8%), Corporate (6.8%) and Wealth (4.5%). Average ticket size is almost the same in every segment (about ₹9,000–₹9,150), so Corporate and Wealth customers are not transacting larger amounts; value follows the number of customers in each segment.
•	Geographic concentration: Maharashtra leads with 15.0% of value (₹68.29M), followed by Karnataka (11.6%) and Gujarat (11.0%); these three states account for 37.6% of the total. Telangana and Chandigarh are the smallest at about 4% each. Female customers account for 51.7% of value and Male customers for 48.3%.
