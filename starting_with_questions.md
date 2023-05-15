Answer the following questions and provide the SQL queries used to find the answer.

    
**Question 1: Which cities and countries have the highest level of transaction revenues on the site?**


SQL Queries:
SELECT city,country,MAX("totalTransactionRevenue") 
AS highest_revenue
FROM all_sessions
WHERE "totalTransactionRevenue" IS NOT NULL 
GROUP BY city,country,"totalTransactionRevenue"
ORDER BY MAX("totalTransactionRevenue")DESC,city,country


Answer:United states has the highest level of transaction revenues on the site
      and city which has highest level of transaction is atlanta,sunnyvale from united states.




**Question 2: What is the average number of products ordered from visitors in each city and country?**


SQL Queries:
SELECT city,country,AVG(units_sold) AS avg_product_ordered
FROM all_sessions AS s
INNER JOIN analytics AS a
ON s."visitId" = a.visitid
WHERE units_sold IS NOT NULL
GROUP BY city,country
ORDER BY avg_product_ordered DESC



Answer:Average products ordered from chicago (united states) is 6.15 
       and from new york (united states) is 4.71







**Question 3: Is there any pattern in the types (product categories) of products ordered from visitors in each city and country?**


SQL Queries:
SELECT city,country,AVG(units_sold) AS avg_product_ordered,"v2ProductCategory"
FROM all_sessions AS s
INNER JOIN analytics AS a
ON s."visitId" = a.visitid
WHERE units_sold IS NOT NULL
GROUP BY city,country,"v2ProductCategory"
ORDER BY avg_product_ordered DESC



Answer:Most products are ordered from the spring sale category in mountainview (united states)
      And the next popular category is shop by Brand in chicago (united states)





**Question 4: What is the top-selling product from each city/country? Can we find any pattern worthy of noting in the products sold?**


SQL Queries:
SELECT city,country,"v2Productname",MAX(units_sold) AS highest_selling_product
FROM all_sessions AS s
INNER JOIN analytics AS a
ON s."visitId" = a.visitid
WHERE units_sold IS NOT NULL
GROUP BY city,country,"v2Productname"
ORDER BY highest_selling_product DESC



Answer:top-selling product in mountain view (united states) is "grip highlighter pen 3 pack"
       second top-selling product in chicago (united states) is "google alpine style backpack"





**Question 5: Can we summarize the impact of revenue generated from each city/country?**

SQL Queries:

SELECT city,country,SUM(revenue) AS total_revenue_generated
FROM all_sessions as s
INNER JOIN analytics as a
ON s."visitId" = a.visitid
WHERE revenue IS NOT NULL
GROUP BY city,country
ORDER BY total_revenue_generated DESC


Answer:sum of the revenue according to each city which gives contribution of each city in towards the total revenue.








