Retrieve all students between the ages of 18 and 22.
```SQL
SELECT name FROMstudents 
WHERE age 
BETWEEN 18 AND 22;
```

Update the "students" table to set Jake's university to MIT. His id is 682.
```sql
UPDATE students 
SET university='MIT'
WHERE id=682
```

When you inserted "elephant" as a new animal, you forgot to include the elephant's age. Correct this mistake by updating the "zoo" table.
```sql
UPDATE zoo 
SET age=14
WHERE animal='elephant'
```

Update the food_balance to 23 for animals whose age is greater than the average age of the animals.
```sql
UPDATE zoo
SET food_balance=23 
WHERE age > 
(SELECT AVG(age)
FROM zoo);
```

You need your customer's names, along with the names of the cities in which they live. The names of the cities are stored in a separate table called "cities".
```sql
SELECT customers.name, cities.name
FROM customers
RIGHT
OUTER JOIN cities
ON cities.id=customers.city_id;
```
In the university's table containing student data, the students' last names have been omitted. Correct this by adding a new column to the table.
```sql
ALTER TABLE students
ADD last_name VARCHAR(100);
```

Retrieve from MIT, Stanford, and Harvard the names of all students whose first name is Jake.
```sql
SELECT name FROM students
WHERE university
IN ('MIT', 'Stanford', 'Harvard') 
AND name='Jake';

