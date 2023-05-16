What are your risk areas? Identify and describe them.	

-Refering correct datatype to each coulmns created under the tables.
-Checking correlation between the different tables of database.



QA Process:
Describe your QA process and include the SQL queries used to execute it.

-Checking for the NULL values to confirm how much NULL value we have in the coulmns.


SELECT COUNT(*)
FROM tablename
WHERE coulmnname IS NULL/IS NOT NULL


-checking for duplicates value in each table.

SELECT COUNT(*)
FROM 
( SELECT coulmn1,coulmn2,coulmn3,...,COUNT(*)
  FROM tablename
 GROUP BY coulmn1,coulmn2,coulmn3,...,
 HAVING COUNT (*) > 1
 
)
AS subquery;



