Using rank to tell where the salary falls in the department

```sql
SELECT
  department,
  last_name,
  salary,
  rank() OVER (PARTITION BY department ORDER BY salary DESC)
FROM 
  staff
```

