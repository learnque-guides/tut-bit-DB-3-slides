# Right join

**RIGHT JOIN** returns all the rows of the table on the right side of the join and matching rows of the table on the left side of join. For the rows for which there is no matching row on left side, the result-set will contain null.

<div style="text-align: center">
<img alt="Right join" src="./images/right_join.png" width="300"></img>
</div>

```sql
SELECT column_name(s)
FROM table1
RIGHT OUTER JOIN table2
ON table1.column = table2.column
```