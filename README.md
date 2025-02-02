# Walmart Sales Data Analysis

## 📌 Project Overview

This project analyzes Walmart's sales data to identify top-performing branches and products, sales trends, and customer behavior. The goal is to derive insights that can help optimize sales strategies.

The dataset was sourced from the [Kaggle Walmart Sales Forecasting Competition](https://www.kaggle.com/c/walmart-recruiting-store-sales-forecasting), which provides historical sales data from 45 Walmart stores. The dataset includes various factors such as store locations, department-wise sales, and holiday markdown events that influence sales performance.

## 🎯 Objectives
- Understand the factors influencing sales across different branches.
- Identify the most and least performing product lines.
- Analyze customer demographics and buying patterns.
- Evaluate the impact of sales strategies and seasonal trends.

## 📊 Dataset Overview
The dataset contains sales transactions from three Walmart branches located in **Mandalay, Yangon, and Naypyitaw**. It consists of **17 columns and 1000 rows**, providing detailed insights into transactions.

| Column                  | Description                             | Data Type      |
|------------------------|-----------------------------------------|---------------|
| invoice_id              | Unique ID for each transaction          | VARCHAR(30)   |
| branch                  | Store branch identifier                 | VARCHAR(5)    |
| city                    | Location of the branch                  | VARCHAR(30)   |
| customer_type           | Type of customer                        | VARCHAR(30)   |
| gender                  | Customer's gender                       | VARCHAR(10)   |
| product_line            | Category of the product                 | VARCHAR(100)  |
| unit_price              | Price per unit of product               | DECIMAL(10,2) |
| quantity                | Number of units purchased               | INT           |
| VAT                     | Value-added tax on purchase             | FLOAT(6,4)    |
| total                   | Total cost after tax                    | DECIMAL(10,2) |
| date                    | Date of transaction                     | DATE          |
| time                    | Time of transaction                     | TIMESTAMP     |
| payment_method          | Payment method used                     | VARCHAR(30)   |
| cogs                    | Cost of Goods Sold (COGS)               | DECIMAL(10,2) |
| gross_margin_percentage | Gross profit margin percentage          | FLOAT(11,9)   |
| gross_income            | Total profit from the transaction       | DECIMAL(10,2) |
| rating                  | Customer rating                         | FLOAT(2,1)    |

## 🔍 Analysis Conducted

### 1️⃣ Product Performance Analysis
- Identifying the best and worst performing product lines.
- Evaluating revenue contribution by product category.
- Analyzing seasonal trends in product sales.

### 2️⃣ Sales Trend Analysis
- Understanding sales fluctuations over different time periods (daily, weekly, monthly).
- Assessing the effectiveness of existing sales strategies.
- Identifying the impact of promotional markdowns.

### 3️⃣ Customer Behavior Analysis
- Segmenting customers based on purchasing patterns.
- Determining the most profitable customer segments.
- Analyzing customer preferences by gender and payment method.

## 🚀 Methodology

### 🛠 Data Preprocessing
- Handling missing values and null entries.
- Cleaning and formatting data for analysis.
- Creating a structured database using SQL.

### 🏗 Feature Engineering
- **Time-based analysis:** Extracting hour, day, and month of purchase.
- **Branch-level insights:** Identifying peak hours and busiest days.
- **Customer segmentation:** Categorizing customers based on purchase history.

### 📈 Exploratory Data Analysis (EDA)
- Visualizing trends using charts and graphs.
- Analyzing correlations between different variables.
- Identifying key drivers of revenue and profit.

## 📌 Key Business Questions Answered

### 🌍 General Insights
1. How many unique cities are in the dataset?
2. Which branch is located in each city?

### 🛒 Product-related Questions
1. How many unique product lines are available?
2. What is the most common payment method?
3. Which product line generates the highest revenue?
4. Which product line has the highest VAT contribution?
5. Which city generates the highest revenue?
6. Which product lines perform above average?
7. What is the most preferred product line by gender?
8. What is the average rating for each product line?

### 📊 Sales-related Questions
1. How do sales vary by time of day?
2. Which customer type contributes the most revenue?
3. Which city has the highest tax percentage (VAT)?
4. Which customer type pays the most in VAT?

### 👥 Customer Behavior Questions
1. How many unique customer types exist?
2. What is the most common customer type?
3. Which customer type makes the most purchases?
4. What is the gender distribution of customers?
5. Which branch has the highest female-to-male ratio?
6. Which time of day receives the most customer ratings?
7. Which day of the week has the best average ratings?

## 📌 Revenue & Profit Calculation

The financial calculations used in this project are:

\[ \text{COGS} = \text{Unit Price} \times \text{Quantity} \]

\[ \text{VAT} = 5\% \times \text{COGS} \]

\[ \text{Total Sales (Gross Revenue)} = \text{COGS} + \text{VAT} \]

\[ \text{Gross Profit} = \text{Total Sales} - \text{COGS} \]

\[ \text{Gross Margin} = \frac{\text{Gross Income}}{\text{Total Revenue}} \]

### Example Calculation:
- **Unit Price** = 45.79
- **Quantity** = 7
- **COGS** = 45.79 * 7 = 320.53
- **VAT** = 5% of 320.53 = 16.03
- **Total Revenue** = 320.53 + 16.03 = 336.56
- **Gross Margin** = (16.03 / 336.56) ≈ **4.76%**

## 💻 SQL Implementation

The data is processed and analyzed using SQL. The database is structured as follows:

```sql
-- Create database
CREATE DATABASE IF NOT EXISTS walmart_sales;

-- Create sales table
CREATE TABLE IF NOT EXISTS sales (
    invoice_id VARCHAR(30) NOT NULL PRIMARY KEY,
    branch VARCHAR(5) NOT NULL,
    city VARCHAR(30) NOT NULL,
    customer_type VARCHAR(30) NOT NULL,
    gender VARCHAR(30) NOT NULL,
    product_line VARCHAR(100) NOT NULL,
    unit_price DECIMAL(10,2) NOT NULL,
    quantity INT NOT NULL,
    tax_pct FLOAT(6,4) NOT NULL,
    total DECIMAL(12,4) NOT NULL,
    date DATE NOT NULL,
    time TIME NOT NULL,
    payment VARCHAR(15) NOT NULL,
    cogs DECIMAL(10,2) NOT NULL,
    gross_margin_pct FLOAT(11,9),
    gross_income DECIMAL(12,4),
    rating FLOAT(2,1)
);
```

🔗 **For complete SQL queries, check the** [SQL_queries.sql](https://github.com/Princekrampah/WalmartSalesAnalysis/blob/master/SQL_queries.sql) **file.**

---

## 🏆 Key Takeaways
✅ Identified peak sales hours and best-performing products.
✅ Analyzed revenue trends to optimize sales strategies.
✅ Gained insights into customer behavior and segmentation.

🚀 **Next Steps:**
- Build predictive models for future sales trends.
- Implement customer loyalty analysis.
- Optimize product recommendations based on buying patterns.

📌 **Connect with me on [LinkedIn](#) | Check out my [GitHub](#) for more projects!**

