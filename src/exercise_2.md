# Exercise 2

Return US customers, and for each customer the total number of orders and total quantities.
Tables involved: Customers, Orders and OrderDetails tables

Tip: Since you will use aggregation function COUNT, SUM, you need to group data by customer id as well. You need to be ware that some record my have duplicates during join. So you need to ditsinct (DISTINCT) them in one of the aggregation function.

Desired output:
```
custid      numorders   totalqty
----------- ----------- -----------
32          11          345
36          5           122
43          2           20
45          4           181
48          8           134
55          10          603
65          18          1383
71          31          4958
75          9           327
77          4           46
78          3           59
82          3           89
89          14          1063
```