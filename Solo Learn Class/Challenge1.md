In the "users" table of website logins and passwords, select the first 10 records in the table.
```SQL
SELECT * FROM users
LIMIT 10
```

create the table "users" to store website user logins and passwords.
```SQL
CREATE TABLE users (
id INT NOT NULL 
AUTO_INCREMENT,
login VARCHAR(100),
password VARCHAR(100) )
```

select all students under age 21. The result should be sorted according to the students' names.
```SQL
SELECT * 
FROM students
WHERE age < 21
ORDER BY name
```

Your boss asks you to print the list of the first one hundred customers who have balances greater than $1000 or who are from NY.
```SQL
SELECT * FROM customers
WHERE balance > 1000 
OR city = 'NY'
LIMIT 100
```

You need the ages of all bears and lions. The first query shows the ages of bears and birds from zoo1, the other shows the ages of lions and crocodiles from zoo2.
