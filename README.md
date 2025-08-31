# Amazon-Sales-Dashboard-Q1-2025-Insights
# 📖 Project Overview
This project showcases the development of an end-to-end sales performance dashboard using Microsoft Power BI. The primary objective was to transform raw transactional data from a CSV file into an interactive, insightful, and visually appealing dashboard. This tool is designed to help business stakeholders understand sales trends, identify top-performing products and regions, and make data-driven decisions.

The dashboard provides a comprehensive overview of key performance indicators (KPIs) and allows for dynamic filtering to explore the data in detail.

# 🎯 Objectives

Analyze sales transactions from Amazon dataset

Identify top-performing products, categories, and regions

Evaluate customer preferences through payment methods

Track order status (Completed, Pending, Cancelled)

Provide management with KPIs & trends for decision-making

# 📊 Dashboard Features
# 🔹 KPIs (Top Section)

Total Sales

Total Orders

Total Quantity Sold

Average Sales per Order

Cancelled Orders

#🔹 Visuals

Sales Trends Over Time (Line/Column Chart)

Sales by Products & Categories

Regional Sales Performance (Map & Bar Chart)

Payment Method Analysis (Pie/Bar Chart)

Order Status Tracking (Donut Chart)

Customer Leaderboard (Table)

# 📈 Key Business Insights

Top Products: Refrigerators & Laptops drive majority of revenue

Top Category: Electronics dominates sales

Customer Preference: PayPal & Credit Card are most used payment methods

Order Status: 37% Completed, 36% Cancelled, 26% Pending (room for improvement in operations)

Sales Trends: Peak sales observed in February & March

# 🛠️ Technical Implementation
This project followed a structured business intelligence workflow to ensure data accuracy, model efficiency, and a user-friendly final product.

# 1. Data Source
File: amazon_sales_data 2025.csv

Description: A flat file containing transactional sales records for the year 2025.

# 2. Data Transformation (ETL)
Tool: Power Query

# Process:

Connected to the CSV data source.

Corrected data types, specifically converting the Date column from text to a proper date format.

Checked for data integrity and consistency across all columns. No missing values were found, which simplified the cleaning process.

# 3. Data Modeling
A Star Schema model was implemented.

A dedicated Calendar Table was created using DAX to handle all time-based calculations.

A one-to-many relationship was established between the Calendar table (one side) and the Sales table (many side) on the Date key. This is a best practice for enabling powerful time-intelligence functions.

# 4. DAX Measures
Several DAX measures were created to calculate and analyze business performance. Key measures include:

Total Sales: Total Sales = SUM('amazon_sales_data 2025'[Total Sales])

Total Orders: Total Orders = DISTINCTCOUNT('amazon_sales_data 2025'[Order ID])

Average Order Value: Average Order Value = DIVIDE([Total Sales], [Total Orders])

Monthly Sales Growth %: A time-intelligence measure comparing sales to the previous month.

Cancellation Rate: Cancellation Rate = DIVIDE([Cancelled Orders], [Total Orders])

YTD Sales: YTD Sales = TOTALYTD([Total Sales], 'Calendar'[Date])



