# Subqueries using the FROM clause

In this example we try to pull the department executives average salary and view them by department

```sql
    /* Assume that anyone who earns over 100k is an executive. We want the average salary of 
    department executives grouped by department*/
    SELECT
    s1.department,
    round(avg(s1.salary))
    FROM
    	(SELECT
    	department,
    	salary
    	FROM staff
    	WHERE salary> 100000) s1
    /*Let's also group by the department to get the averages of department executives over 100k*/
    GROUP BY 
    s1.department;
              
```
Output:

| department  | round  |
| ----------- | ------ |
| Books       | 125114 |
| Health      | 128508 |
| Automotive  | 124300 |
| Home        | 128761 |
| Outdoors    | 126402 |
| Electronics | 124825 |
| Shoes       | 123536 |
| Baby        | 125354 |
| Toys        | 126293 |
| Beauty      | 125529 |
| Games       | 128756 |
| Jewelery    | 123887 |
| Industrial  | 125143 |
| Grocery     | 129747 |
| Music       | 124875 |
| Tools       | 124637 |
| Computers   | 124035 |
| Movies      | 120877 |
| Garden      | 128793 |
| Kids        | 127565 |
| Clothing    | 125692 |
| Sports      | 131570 |
