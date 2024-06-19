# Supermarket Sales Analysis and Insights Dashboard

## Overview

This project aims to create a comprehensive dashboard that provides valuable insights into the sales performance, customer behavior, payment methods, peak sales times, and customer satisfaction for a supermarket chain operating in multiple cities. The goal is to leverage data-driven insights to optimize supermarket operations, enhance customer engagement, and drive overall business growth.

## Features

- **Sales Overview**: Displays total sales, number of transactions, and average transaction value.
- **Branch Performance**: Showcases best-selling products by branch, total sales by branch, and average customer rating by branch.
- **Customer Insights**: Highlights purchase patterns by gender and customer type, and top products for members vs. non-members.
- **Payment Methods Analysis**: Analyzes sales distribution and average transaction value by payment method.
- **Time-Based Analysis**: Visualizes sales trends by day of the week and peak sales hours.
- **Customer Satisfaction**: Displays average customer rating by product line and visualizes customer feedback comments.

## Dataset

The dataset used for this analysis is a historical sales record of a supermarket company with data recorded over three months. It includes details such as invoice ID, branch, city, customer type, gender, product line, unit price, quantity, tax, total amount, date, time, payment method, cost of goods sold (COGS), gross margin percentage, gross income, and customer rating.

## Database Schema

### Tables

1. **Branch**
   - `Branch_id`
   - `City_id`

2. **City**
   - `City_id`
   - `City_name`

3. **Customer**
   - `Customer_id`
   - `Customer_type`
   - `Gender`

4. **Product**
   - `Product_id`
   - `Product_line`
   - `Unit_price`

5. **Invoice**
   - `Invoice_id`
   - `Branch_id`
   - `Customer_id`
   - `Product_id`
   - `Date`
   - `Time`
   - `Payment_method`
   - `Rating`

6. **Sales**
   - `Sales_id`
   - `Invoice_id`
   - `Quantity`
   - `Tax`
   - `Total`
   - `COGS`
   - `Gross_margin_percentage`
   - `Gross_income`

## Analytical Approach

### 1. Optimizing Product Performance Across Cities
- **Approach**: Utilize SQL queries to calculate total sales and quantity sold for each product across cities.
  
### 2. Understanding Customer Purchase Behavior
- **Approach**: Segment sales data by gender and customer type using SQL queries. Visualize insights using stacked bar charts to compare purchasing behaviors between member and non-member customers.
  
### 3. Effectiveness of Payment Methods
- **Approach**: Analyze sales distribution by payment method using SQL queries.
  
### 4. Peak Sales Times and Operational Efficiency
- **Approach**: Aggregate sales data by hour using SQL queries.
  
### 5. Customer Satisfaction Analysis
- **Approach**: Calculate average customer ratings by city using SQL queries.

## SQL Queries

### Example Query: Optimizing Product Performance Across Cities

```sql
SELECT 
    c.City_name, 
    p.Product_line, 
    SUM(s.Total) AS Total_Sales, 
    SUM(s.Quantity) AS Quantity_Sold
FROM 
    Sales s
JOIN 
    Invoice i ON s.Invoice_id = i.Invoice_id
JOIN 
    Branch b ON i.Branch_id = b.Branch_id
JOIN 
    City c ON b.City_id = c.City_id
JOIN 
    Product p ON i.Product_id = p.Product_id
GROUP BY 
    c.City_name, p.Product_line
ORDER BY 
    Total_Sales DESC;
```

## Conclusion

This project successfully demonstrates how a comprehensive dashboard can be created to analyze and visualize sales data, providing actionable insights into sales performance, customer behavior, payment methods, time-based trends, and customer satisfaction. These insights are crucial for optimizing supermarket operations, enhancing customer engagement, and driving business growth.

## How to Use

1. Clone the repository.
2. Import the dataset into your preferred SQL database management system.
3. Run the provided SQL queries to create tables and populate them with data.
4. Use your favorite data visualization tools (e.g., Power BI, Tableau) to create the dashboard using the insights generated from the SQL queries.



## Acknowledgements

Thanks to everyone who contributed to the dataset and to all who perform analyses and provide feedback.

---

