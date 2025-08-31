# Amazon-Sales-Dashboard-Q1-2025-Insights
#📖 Project Overview
This project showcases the development of an end-to-end sales performance dashboard using Microsoft Power BI. The primary objective was to transform raw transactional data from a CSV file into an interactive, insightful, and visually appealing dashboard. This tool is designed to help business stakeholders understand sales trends, identify top-performing products and regions, and make data-driven decisions.

The dashboard provides a comprehensive overview of key performance indicators (KPIs) and allows for dynamic filtering to explore the data in detail.

#✨ Key Features & Insights
Executive KPI Summary: At-a-glance view of critical metrics like Total Sales, Total Orders, Average Order Value (AOV), and Customer Cancellation Rate.

Time-Series Analysis: A monthly trend chart visualizes sales performance and growth, highlighting seasonality and the impact of marketing campaigns.

Product & Category Analysis: Bar charts identify the most profitable product categories and top-selling individual products, enabling better inventory and marketing focus.

Geographical Insights: Analysis of sales by customer location reveals top-performing markets and opportunities for regional growth.

Interactive Slicers: Dynamic filters for Year and Customer Location empower users to drill down into the data and uncover specific insights on their own.

# Actionable Insights from the Dashboard:
Peak Sales Month: Identified March as the highest revenue-generating month.

Top Category: 'Electronics' stands out as the most significant contributor to total sales.

Key Markets: New York and San Francisco are the leading cities in terms of sales volume.

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



