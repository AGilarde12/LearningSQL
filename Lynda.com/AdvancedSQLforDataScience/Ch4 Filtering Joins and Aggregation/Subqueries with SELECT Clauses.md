# Subqueries with SELECT Clauses
In this lesson, I learned how to use a simple subquery and match my tables correctly for avg. calculations:

```sql
/* subquerries can be used in three different parts*/

SELECT
s1.last_name,
s1.salary,
s1.department,
	(SELECT round(avg(salary)) FROM staff s2 WHERE s2.department = s1.department)
FROM
staff s1
LIMIT 10

/*The s1 allows you to tell SQl which table we want to pull from*/

/*The subquerry above is inserted after the department select and the where s2. = s1. allows us 
to make sure we're averaging for the correct departments*/
```

| last_name  | salary | department | round  |
| ---------- | ------ | ---------- | ------ |
| Kelley     | 67470  | Computers  | 99095  |
| Armstrong  | 71869  | Sports     | 93901  |
| Carr       | 101768 | Automotive | 99658  |
| Murray     | 96897  | Jewelery   | 87812  |
| Ellis      | 63702  | Grocery    | 101114 |
| Phillips   | 118497 | Tools      | 105021 |
| Williamson | 65889  | Computers  | 99095  |
| Harris     | 84427  | Toys       | 96187  |
| James      | 108657 | Jewelery   | 87812  |
| Sanchez    | 108093 | Movies     | 100912 |

---
