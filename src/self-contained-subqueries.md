# Self-contained subqueries

Can be executed independently.

```sql
SELECT orderid, orderdate, empid, custid
  FROM Sales.Orders
WHERE orderid = (SELECT MAX(O.orderid)
                  FROM Sales.Orders AS O);
```

Why this doesn't work???

```sql
SELECT orderid
FROM Sales.Orders
WHERE empid =
  (SELECT E.empid
   FROM HR.Employees AS E
   WHERE E.lastname LIKE N'D%');
```

The form of the multivalue subquery with IN predicate:

```
<scalar_expression> IN (<multivalued subquery>)
```

Some examples :)

Write a query that returns orders placed by customers from the United States. You can write a query against the Orders table that returns orders where the customer ID is in the set of customer IDs of customers from the United States