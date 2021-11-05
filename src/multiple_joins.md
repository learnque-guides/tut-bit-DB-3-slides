# Composite join

A composite join is simply a join where you need to match multiple attributes from each side.

```sql
SELECT * FROM dbo.Table1 AS T1
  INNER JOIN dbo.Table2 AS T2
    ON T1.col1 = T2.col1
    AND T1.col2 = T2.col2
```
