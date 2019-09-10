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
