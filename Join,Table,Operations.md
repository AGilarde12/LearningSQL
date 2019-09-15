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


## UNION
Occasionally, you might need to combine data from multiple tables into one comprehensive dataset. This may be for tables with similar data within the same database or maybe there is a need to combine similar data across databases or even across servers.

To accomplish this, use the UNION and UNION ALL operators.

UNION combines multiple datasets into a single dataset, and removes any existing duplicates.
UNION ALL combines multiple datasets into one dataset, but does not remove duplicate rows.
UNION ALL is faster than UNION, as it does not perform the duplicate removal operation over the data set.

The UNION operator is used to combine the result-sets of two or more SELECT statements.

All SELECT statements within the UNION must have the same number of columns. The columns must also have the same data types. Also, the columns in each SELECT statement must be in the same order.
The syntax of UNION is as follows:
```SQL
SELECT column_name(s) FROM table1
UNION
SELECT column_name(s) FROM table2;
```

### UNION WITH NULL
If your columns don't match exactly across all queries, you can use a NULL (or any other) value such as:
```SQL
SELECT FirstName, LastName, Company FROM businessContacts
UNION
SELECT FirstName, LastName, NULL FROM otherContacts;
```
UNION ALL selects all rows from each table and combines them into a single table.

The following SQL statement uses UNION ALL to select data from the First and Second tables:
```SQL
SELECT ID, FirstName, LastName, City FROM First
UNION ALL
SELECT ID, FirstName, LastName, City FROM Second;
```

## INSERT INTO
```SQL
INSERT INTO table_name
VALUES (value1, value2, value3,...);
```
Or you can specify the columns for the insert:

```SQL
INSERT INTO table_name (column1, column2, column3, ...,columnN)  
VALUES (value1, value2, value3,...valueN);
```

## UPDATE AND WHERE
The UPDATE statement allows us to alter data in the table.

The basic syntax of an UPDATE query with a WHERE clause is as follows:
```SQL
UPDATE table_name
SET column1=value1, column2=value2, ...
WHERE condition;
```
You specify the column and its new value in a comma-separated list after the SET keyword.
If you omit the WHERE clause, all records in the table will be updated!

Example:
```SQL
UPDATE students 
SET university='Stanford'
WHERE name='John';
```

Updating more than one column:
```SQL
UPDATE Employees 
SET Salary=5000, FirstName='Robert'
WHERE ID=1;
```

## Creating a table
```SQL
CREATE TABLE table_name
(
column_name1 data_type(size),
column_name2 data_type(size),
column_name3 data_type(size),
....
columnN data_type(size)
);
```

Assume that you want to create a table called "Users" that consists of four columns: UserID, LastName, FirstName, and City.
Use the following CREATE TABLE statement:
```SQL
CREATE TABLE Users
(
   UserID int,
   FirstName varchar(100), 
   LastName varchar(100),
   City varchar(100),
   PRIMARY KEY(UserID)
); 
```

### Types of Data:
```SQL
Numeric
INT -A normal-sized integer that can be signed or unsigned.
FLOAT(M,D) - A floating-point number that cannot be unsigned. You can optionally define the display length (M) and the number of decimals (D).
DOUBLE(M,D) - A double precision floating-point number that cannot be unsigned. You can optionally define the display length (M) and the number of decimals (D).

Date and Time
DATE - A date in YYYY-MM-DD format.
DATETIME - A date and time combination in YYYY-MM-DD HH:MM:SS format.
TIMESTAMP - A timestamp, calculated from midnight, January 1, 1970
TIME - Stores the time in HH:MM:SS format.

String Type
CHAR(M) - Fixed-length character string. Size is specified in parenthesis. Max 255 bytes.
VARCHAR(M) - Variable-length character string. Max size is specified in parenthesis.
BLOB - "Binary Large Objects" and are used to store large amounts of binary data, such as images or other types of files.
TEXT - Large amount of text data.
```

## CONSTRAINTS
The following are commonly used SQL constraints:
```SQL
NOT NULL - Indicates that a column cannot contain any NULL value.
UNIQUE - Does not allow to insert a duplicate value in a column. The UNIQUE constraint maintains the uniqueness of a column in a table. More than one UNIQUE column can be used in a table.
PRIMARY KEY - Enforces the table to accept unique data for a specific column and this constraint create a unique index for accessing the table faster.
CHECK - Determines whether the value is valid or not from a logical expression.
DEFAULT - While inserting data into a table, if no value is supplied to a column, then the column gets the value set as DEFAULT.
```

## Creating a View
```SQL
CREATE VIEW List AS
SELECT FirstName, Salary
FROM  Employees;
```

You can the query the List as you're own query
```SQL
SELECT * FROM List;
```

Excercise:
Drag and drop from the options below to create a view named ''temp'' for students with the highest marks.
```SQL
CREATE VIEW temp AS 
SELECT id, name, mark 
FROM students 
ORDER BY mark DESC 
LIMIT 10;
```

### Quiz
Rearrange to select all student names and university names (use left join to show all student names).
```SQL
SELECT students.names, universities.names
FROM students
LEFT OUTER JOIN universities
ON students.university_id=universities.id
```

Drag and drop from the options below to insert a data item into the ''people'' table.
```SQL
INSERT INTO people
VALUES ('John Smith', '1', 22);
```




