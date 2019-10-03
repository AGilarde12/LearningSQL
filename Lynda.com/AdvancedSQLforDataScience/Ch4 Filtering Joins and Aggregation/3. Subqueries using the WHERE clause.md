# Subqueries using the WHERE clause

In this I use a subquery and WHERE clause to grab the person making the most money in the staff table
```sql
    SELECT 
    	s1.department, s1.last_name, s1.salary
    FROM
    	staff s1
    WHERE 
    	s1.salary =(SELECT
    				max(s2.salary)
    				FROM 
    				staff s2)
                    
    /* so above, I have a subquery that finds the max salary in the staff table. I then have a top level query which returns the department for whatever row has a salary that is equal to the max salary*/
    
    /*Second, for the top level SELECT statement I have the department, last name and the salary of the person in the staff table who has the max salary.*/;
```
Output:

| department | last_name | salary |
| ---------- | --------- | ------ |
| Grocery    | Stanley   | 149929 |
