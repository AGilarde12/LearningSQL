Rounding to AVG salary 2 decimal places:
```sql
SELECT department, round(avg(salary),2)
FROM staff
GROUP BY
department
LIMIT 10
```

Output:

| Tool Name     | Avg Salary  |
|---------------|-------------|
| "Tools"       | "105020.72" |
| "Electronics" | "91615.12"  |
| "Sports"      | "93901.03"  |
| "Books"       | "94890.15"  |
| "Clothing"    | "95054.53"  |
| "Kids"        | "93237.55"  |
| "Music"       | "88507.22"  |
| "Automotive"  | "99658.00"  |
| "Outdoors"    | "112055.42" |
| "Garden"      | "101959.26" |

You can also use the trunc() value and put a certain amount of decimal places
