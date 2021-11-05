# Correlated subqueries

Cannot be run independently.

```sql
SELECT custid, orderid, orderdate, empid
FROM Sales.Orders AS O1
WHERE orderid =
  (SELECT MAX(O2.orderid)
   FROM Sales.Orders AS O2
   WHERE O2.custid = O1.custid);
```

Will find latest orderid for current customer.

We can also use subqueries for calculating percentage of some value. Let's investigate such example:

```sql
SELECT orderid, custid, val,
  CAST(100. * val / (SELECT SUM(O2.val)
                     FROM Sales.OrderValues AS O2
                     WHERE O2.custid = O1.custid)
       AS NUMERIC(5,2)) AS pct
FROM Sales.OrderValues AS O1
ORDER BY custid, orderid;
```

T-SQL supports EXISTS predicate that can be used with subquries.

Lets' find orders that was not completed for customer

```sql
SELECT custid, companyname
FROM Sales.Customers AS C
WHERE country = N'Spain'
  AND NOT EXISTS
    (SELECT * FROM Sales.Orders AS O
     WHERE O.custid = C.custid);
```
Quiz:
* How we can achieve the same result with joins?
* How to find previous orderid for every order in Orders table (advanced)?