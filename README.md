## Music Store Sales Analysis

### Problem Statement
Retail music stores need insights into customer behavior and product performance to maximize revenue. This project analyzes music store sales data to identify revenue drivers, high-performing genres, and valuable customers.

### Tools Used
- SQL
- Power BI

### Business Questions
- Which music genres and artists generate the highest revenue?
- Who are the top customers by total spend?
- How do sales vary by region?
- What are the monthly revenue trends?

### Key Business Insights
- A small number of genres contribute to the majority of revenue
- Repeat customers generate significantly higher lifetime value
- Certain regions outperform others in total sales
- Revenue shows consistent trends across months

##  Example SQL Queries
```sql
-- Top 10 Customers by Total Spend
SELECT customer_id,
       SUM(total_amount) AS total_spent
FROM invoices
GROUP BY customer_id
ORDER BY total_spent DESC
LIMIT 10;

-- Genre Revenue Breakdown
SELECT g.genre_name,
       SUM(il.unit_price * il.quantity) AS revenue
FROM invoice_items il
JOIN tracks t ON il.track_id = t.track_id
JOIN genres g ON t.genre_id = g.genre_id
GROUP BY g.genre_name;
📊 Visualizations

### Use Case
This analysis can support sales and marketing teams by:
- Focusing promotions on high-revenue genres and artists
- Identifying and rewarding high-value customers
- Improving regional sales strategies using performance data

### Project Assets
- SQL queries for sales and customer analysis
- Power BI dashboard for revenue and customer insights
