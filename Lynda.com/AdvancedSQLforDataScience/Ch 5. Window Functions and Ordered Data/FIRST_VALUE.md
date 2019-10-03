 We could also select a set of attributes grouped by department and include the first value by department in each row using something called The First Value Function. Let's take a look:
 
```sql
SELECT
  department,
  last_name,
  salary,
  first_value(salary) OVER (PARTITION BY department ORDER BY salary DESC)
FROM
  staff
```

