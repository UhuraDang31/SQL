# SQL
Ranking
https://www.sqlshack.com/overview-of-sql-rank-functions/
1. RANK()
2. DENSE_RANK()

Create a simple SELECT statement that will return all columns from the people table, and join to the sales table so that you can return the COUNT of all sales and RANK each person by their sale_count.

**people table schema**
_id, name_

**sales table schema**
_id, people_id, sale, price_

You should return all people fields as well as the sale count as "sale_count" and the rank as "sale_rank".
NOTE: Your solution should use pure SQL. Ruby is used within the test cases to do the actual testing.

SELECT people.id, people.name,
      COUNT(sales.sale) AS sale_count,
      DENSE_RANK() OVER ( ORDER BY COUNT(sales.sale) DESC) as sale_rank
FROM sales
JOIN people ON people.id = sales.people_id
GROUP BY people.id;


3. ROW_NUMBER()
4. NTILE
