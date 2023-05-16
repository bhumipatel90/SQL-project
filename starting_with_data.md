Question 1: Which product is ordered maximum time ?

SQL Queries:
SELECT name,total_ordered
FROM sales_reports
WHERE total_ordered IS NOT NULL
ORDER BY total_ordered DESC

Answer: Ballpen LED light pen



Question 2:What is the time spent by the customer online which gave maximum revenue?

SQL Queries:
SELECT a.timeonsite,s."fullVisitorid",revenue
FROM analytics AS a
INNER JOIN all_sessions AS s
ON a.visitid = s."visitId"
WHERE revenue IS NOT NULL
GROUP BY a.timeonsite,s."fullVisitorid",revenue
ORDER BY revenue DESC,a.timeonsite

Answer:
timeonsite:264
revenue:396000000


Question 3: Distinguish the products which are ordered most and least ?

SQL Queries:
SELECT name,total_ordered,
CASE
     WHEN total_ordered > 100 THEN 'maximum'
     ELSE 'minimum'
    END AS product_ordered

FROM sales_reports
ORDER BY total_ordered DESC

Answer:
13 products are ordered most of the time 
and rest of them are ordered less.


Question 4: Which products needs to be restock ?


SQL Queries:
SELECT name,total_ordered,"stockLevel"
FROM sales_reports
WHERE total_ordered > "stockLevel"
ORDER BY total_ordered DESC

Answer: 
Android infant short sleeve tee pewter and youth baseball raglan heather/black needs to be restock again



Question 5: 

SQL Queries:

Answer:
