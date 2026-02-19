# Analyzing-Motorcycle-Part-Sales-Using-SQL


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

-Filtered the sales table to include **only wholesale orders**  
-Extracted and labels the **month** from the order date  
-Grouped sales by **product line, month, and warehouse**  
-Calculated **net revenue** after subtracting payment fees  
-Ordered the results for easier reporting  
-Exported the final SQL output into a structured CSV file  

## Files Included

-notebook.ipynb              →    SQL notebook containing the analysis
-wholesale_net_revenue.csv   →    Exported results of the SQL query
-README.md                   →    Project documentation

##  Dataset Structure (SQL Table)

The analysis uses one SQL table titled "sales".

## SQL Query Used in the Analysis

An SQL Query was used to obtain our output which are both included in the Project Notebook.

## Results Overview (CSV Output)

The final CSV contains the computed fields:

product_line, month, warehouse, net_revenue

Each row represents one product line in one warehouse for one month.




