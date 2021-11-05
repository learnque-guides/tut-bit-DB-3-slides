# Exercise 1

Explain what's wrong in the following query and provide a correct alternative:

```sql
SELECT Customers.custid, Customers.companyname, Orders.orderid, Orders.orderdate
FROM Sales.Customers AS C
  INNER JOIN Sales.Orders AS O
    ON Customers.custid = Orders.custid;
```
