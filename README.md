# Analyzing-Motorcycle-Part-Sales-Using-SQL
# Wholesale Net Revenue Analysis (SQL)

##  Project Summary

This project performs a SQL-based analysis of wholesale sales for a regional motorcycle-parts distributor operating three warehouses: **North**, **Central**, and **West**.

Using SQL only, the objective was to calculate **net wholesale revenue** for each combination of:

- Product line  
- Month (June, July, August 2021)  
- Warehouse  

Net revenue was computed as:

net_revenue = SUM(total) - SUM(payment_fee)

This provides leadership with a clear view of which product categories and warehouses generate the most wholesale revenue after payment-processing costs.



##  What This Project Achieved (Using MySQL Only)

✔ Filtered the sales table to include **only wholesale orders**  
✔ Extracted and labels the **month** from the order date  
✔ Grouped sales by **product line, month, and warehouse**  
✔ Calculated **net revenue** after subtracting payment fees  
✔ Ordered the results for easier reporting  
✔ Exported the final SQL output into a structured CSV file  


##  Dataset Structure (SQL Table)

The analysis uses one SQL table: **`sales`**

| Column        | Type     | Description |
|---------------|----------|-------------|
| order_number  | VARCHAR  | Unique order ID |
| date          | DATE     | Order date (June–August 2021) |
| warehouse     | VARCHAR  | North, Central, or West |
| client_type   | VARCHAR  | Wholesale or Retail |
| product_line  | VARCHAR  | Product category |
| quantity      | INT      | Number of items |
| unit_price    | FLOAT    | Price per item |
| total         | FLOAT    | Total sale amount |
| payment       | VARCHAR  | Payment method |
| payment_fee   | FLOAT    | Fee charged for payment processing |

---

## SQL Query Used in the Analysis

```sql
SELECT
    product_line,
    CASE
        WHEN EXTRACT('month' FROM date) = 6 THEN 'June'
        WHEN EXTRACT('month' FROM date) = 7 THEN 'July'
        WHEN EXTRACT('month' FROM date) = 8 THEN 'August'
    END AS month,
    warehouse,
    SUM(total) - SUM(payment_fee) AS net_revenue
FROM sales
WHERE client_type = 'Wholesale'
GROUP BY
    product_line,
    month,
    warehouse
ORDER BY
    product_line,
    month,
    net_revenue DESC;


## Files Included

├── notebook.ipynb               # SQL notebook containing the analysis
├── wholesale_net_revenue.csv    # Exported results of the SQL query
└── README.md                    # Project documentation

## Results Overview (CSV Output)

The final CSV contains the computed fields:

product_line, month, warehouse, net_revenue

Each row represents one product line in one warehouse for one month.


