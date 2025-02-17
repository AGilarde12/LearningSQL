# Filtering

## WHERE

The WHERE clause is used to extract only those records that fulfill a specified criterion.

The syntax for the WHERE clause:
```SQL
SELECT column_list 
FROM table_name
WHERE condition;
```

Drag and drop from the options below to select the name of the student whose id is equal to 23.
```SQL
SELECT id,name
FROM students
WHERE id = 23
```


## BETWEEN
The BETWEEN operator selects values within a range. The first value must be lower bound and the second value, the upper bound.

The syntax for the BETWEEN clause is as follows:
```SQL
SELECT column_name(s)
FROM table_name
WHERE column_name BETWEEN value1 AND value2;
```

The following SQL statement selects all records with IDs that fall between 3 and 7:
```SQL
SELECT * FROM customers 
WHERE ID BETWEEN 3 AND 7;
```

## AND OR
Logical Operators

Logical operators can be used to combine two Boolean values and return a result of true, false, or null.
The following operators can be used:

```SQL
AND -- True if both expressions are true
OR -- True if either expression is true
IN -- True if an operand is equal to one of a list of expressions
NOT -- Returns True if an expression is not true
```

```SQL
SELECT ID, FirstName, LastName, Age
FROM customers
WHERE Age >= 30 AND Age <= 40;
```
AND OR
The statement below selects all customers from the city "New York" AND with the age equal to "30" OR “35":

```SQL
SELECT * FROM customers
WHERE City = 'New York'
AND (Age=30 OR Age=35);
```

Drag and drop from the options below to select customers whose ids are either 1 or 2, and whose city is ''Boston''.
```SQL
SELECT * FROM customers
WHERE (id = 1 OR id = 2)
AND city = 'Boston'
```

## IN OR OUT
The in operator lets you make your query more clean

```SQL
SELECT * FROM customers 
WHERE City IN ('New York', 'Los Angeles', 'Chicago');
```

The NOT IN operator allows you to exclude a list of specific values from the result set.

If we add the NOT keyword before IN in our previous query, customers living in those cities will be excluded:
```SQL
SELECT * FROM customers 
WHERE City NOT IN ('New York', 'Los Angeles', 'Chicago');
```

## CONCAT
The CONCAT function is used to concatenate two or more text values and returns the concatenating string.

Let's concatenate the FirstName with the City, separating them with a comma:
```SQL
SELECT CONCAT(FirstName, ', ' , City) FROM customers;
```

MAKE IT A NEW COLUMN
```
SELECT CONCAT(FirstName,', ', City) AS new_column 
FROM customers;
```

## UPPER AND LOWER

The UPPER function converts all letters in the specified string to uppercase.
The LOWER function converts the string to lowercase.

The following SQL query selects all LastNames as uppercase:
```
SELECT FirstName, UPPER(LastName) AS LastName 
FROM employees;
```

Similarly, the AVG function returns the average value of a numeric column:
```SQL
SELECT AVG(Salary) FROM employees;
```


## SUBQUERRY
A single subquery will return the same result more easily.
```
SELECT FirstName, Salary FROM employees 
WHERE  Salary > (SELECT AVG(Salary) FROM employees) 
ORDER BY Salary DESC;
```




## LIKE OPERATOR
The Like Operator

The LIKE keyword is useful when specifying a search condition within your WHERE clause.
```
SELECT column_name(s)
FROM table_name
WHERE column_name LIKE pattern;
```

SQL pattern matching enables you to use "_" to match any single character and "%" to match an arbitrary number of characters (including zero characters).

For example, to select employees whose FirstNames begin with the letter A, you would use the following query:
```
SELECT * FROM employees 
WHERE FirstName LIKE 'A%';
```

## LIKE AND IN
Drag and drop from the options below to complete the statement, which selects ''name'' 
and minimum of the "cost'' from ''items'', filtering by name and seller id.

```SQL
SELECT name, MIN(cost) 
FROM items WHERE name 
LIKE '%boxes of frogs' AND 
seller_id IN (68, 6, 18)
```


QUIZ
Drag and drop from the options below to select name and age from ''students'',
where age is greater than the average of all ages. Use a subquery to calculate the average value of age.

```SQL
SELECT name, age 
FROM students
WHERE age >
(SELECT AVG(age)
 FROM students)
```
