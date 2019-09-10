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
LEFT JOIN

The LEFT JOIN returns all rows from the left table, even if there are no matches in the right table.

This means that if there are no matches for the ON clause in the table on the right, the join will still return the rows from the first table in the result.

The basic syntax of LEFT JOIN is as follows:
```SQL
SELECT table1.column1, table2.column2...
FROM table1 LEFT OUTER JOIN table2
ON table1.column_name = table2.column_name;
```
See Image:
![Left Join](https://api.sololearn.com/DownloadFile?id=2834)

The following SQL statement will return all customers, and the items they might have:
```SQL
SELECT customers.Name, items.Name 
FROM customers LEFT OUTER JOIN items 
ON customers.ID=items.Seller_id;
```

### RIGHT JOIN
The RIGHT JOIN returns all rows from the right table, even if there are no matches in the left table.

The basic syntax of RIGHT JOIN is as follows:
```SQL
SELECT table1.column1, table2.column2...
FROM table1 RIGHT JOIN table2
ON table1.column_name = table2.column_name;
```
Consider the same example from our previous lesson, but this time with a RIGHT JOIN:
```SQL
SELECT customers.Name, items.Name FROM customers
RIGHT JOIN items ON customers.ID=items.Seller_id;
```
The RIGHT JOIN returns all the rows from the right table (items), even if there are no matches in the left table (customers).

See Image:

![Right Join](https://api.sololearn.com/DownloadFile?id=2838)
