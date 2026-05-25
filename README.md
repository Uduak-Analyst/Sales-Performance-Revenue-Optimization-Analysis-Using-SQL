# Sales-Performance-Revenue-Optimization-Analysis-Using-SQL
Analyzed sales performance data using SQL to uncover revenue-driving regions, top-performing product categories, customer purchasing patterns, and the impact of discounts on revenue optimization. The project focuses on transforming raw sales data into actionable business insights that support strategic decision-making.
## Project Overview
This project analyzes sales performance data using SQL to uncover business insights related to revenue optimization, customer behavior, regional performance, and discount impact.

The goal of the project is to transform raw sales data into actionable insights that support strategic business decisions.

---

## Tools Used
- SQL
- Excel

---

## Business Questions Solved
1. Which product category generates the highest revenue?
2. Which region performs best?
3. Does discount reduce revenue?
4. Who are the top 10 customers by revenue?

---

## SQL Queries

### 1. Which Product Category Generates the Highest Revenue?

```sql
SELECT 
    Product_Category,
    ROUND(SUM(Revenue), 2) AS Total_Revenue
FROM sales_data
GROUP BY Product_Category
ORDER BY Total_Revenue DESC;
```

---

### 2. Which Region Performs Best?

```sql
SELECT 
    Region,
    ROUND(SUM(Revenue), 2) AS Regional_Revenue
FROM sales_data
GROUP BY Region
ORDER BY Regional_Revenue DESC;
```

---

### 3. Does Discount Reduce Revenue?

```sql
SELECT 
    CASE 
        WHEN Discount = 0 THEN 'No Discount'
        WHEN Discount BETWEEN 0.01 AND 0.10 THEN 'Low Discount'
        WHEN Discount BETWEEN 0.11 AND 0.20 THEN 'Medium Discount'
        ELSE 'High Discount'
    END AS Discount_Level,

    ROUND(AVG(Revenue),2) AS Avg_Revenue,
    COUNT(*) AS Total_Orders

FROM sales_data
GROUP BY Discount_Level
ORDER BY Avg_Revenue DESC;
```

---

### 4. Top 10 Customers by Revenue

```sql
SELECT 
    Customer_Name,
    ROUND(SUM(Revenue), 2) AS Total_Revenue,
    COUNT(Order_ID) AS Total_Orders
FROM sales_data
GROUP BY Customer_Name
ORDER BY Total_Revenue DESC
LIMIT 10;
```

---

## Key Insights
- Certain regions generated significantly higher revenue than others.
- A few product categories contributed most to total sales.
- Discount levels impacted average revenue performance.
- A small number of customers contributed heavily to business revenue.

---

## Project Outcome
This project demonstrates SQL proficiency, business intelligence thinking, and the ability to transform raw data into actionable business insights.
