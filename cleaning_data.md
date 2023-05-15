What issues will you address by cleaning the data?
1.remove duplicate values from table
2.update city and country value with null with inappropriate value
3.update productprice value




Queries:
Below, provide the SQL queries you used to clean your data.

-- update city values with NULL for inappropriate city value.

UPDATE 
        all_sessions
SET 
        city = NULL 
WHERE
         city = 'not available in demo dataset' or city = '(not set)'

-- update country values with NULL for inappropriate country value.

UPDATE all_sessions
SET country = NULL
WHERE country = '(not set)'


--create table with unique values and remove duplicates.



CREATE TABLE TEMP_table
AS
SELECT
        DISTINCT * 
FROM tablename

DROP TABLE tablename

ALTER TABLE TEMP_table
RENAME TO tablename


--productprice update


UPDATE all_sessions SET "productPrice" = "productPrice"/1000000



