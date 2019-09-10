# Joining Tables

Rather than storing the customer name in both tables, the orders table contains a reference to the customer ID that appears in the customers table. This approach is more efficient, as opposed to storing the same text values in both tables.
In order to be able to select the corresponding data from both tables, we will need to join them on that condition.

## Joining Tables

To join the two tables, specify them as a comma-separated list in the FROM clause:
```SQL
SELECT customers.ID, customers.Name, orders.Name, orders.Amount
FROM customers, orders
WHERE customers.ID=orders.Customer_ID
ORDER BY customers.ID;
```

Each table contains "ID" and "Name" columns, so in order to select the correct ID and Name, fully qualified names are used.

Note that the WHERE clause "joins" the tables on the condition that the ID from the customers table should be equal to the customer_ID of the orders table.

Drag and drop from the options below to complete the following statement, which shows item names and the names of customers who bought the items.
```SQL
SELECT customers.name, items.names 
FROM customers, items
WHERE items.seller_id =
 customers.id
```
## Custom Names
Custom names can be used for tables as well. You can shorten the join statements by giving the tables "nicknames":
```SQL
SELECT ct.ID, ct.Name, ord.Name, ord.Amount
FROM customers AS ct, orders AS ord
WHERE ct.ID=ord.Customer_ID
ORDER BY ct.ID;
```

## Types of Joins

### INNER JOIN
INNER JOIN is equivalent to JOIN. It returns rows when there is a match between the tables.
Only the records matching the join condition are returned.
```SQL
SELECT column_name(s)
FROM table1 INNER JOIN table2 
ON table1.column_name=table2.column_name;
```
See Image:

![Inner Join Image](https://api.sololearn.com/DownloadFile?id=2833)

### LEFT JOIN

### RIGHT JOIN
