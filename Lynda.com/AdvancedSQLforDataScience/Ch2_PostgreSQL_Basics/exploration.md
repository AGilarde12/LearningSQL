# Exploring the newly created Database

First, let's start with some simple group by queries:
```sql
SELECT count(*) 
FROM staff
GROUP BY
gender
```

We now see that there are 496 females and 504 males in the company

Grouping by department:
```sql
SELECT department, count(*) 
FROM staff
GROUP BY
department
```

Finding max and min salary while grouping by department:
```sql
SELECT department,max(salary), min(salary) 
FROM staff
Group by 
department
```

Grouping the same query by gender:
```sql
SELECT gender,max(salary), min(salary) 
FROM staff
Group by 
gender
```

