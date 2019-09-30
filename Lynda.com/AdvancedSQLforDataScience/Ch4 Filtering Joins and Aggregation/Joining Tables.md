The problem we're trying to solve is the staff table includes a department for each employee. Since we dont keep division information in the staff table, we have to look it up.

```sql
/*First we want to visualize the different columns from company divisons*/
/*This query allows us to return the merged table*/
SELECT
	s.last_name,
    s.department,
    cd.company_division
FROM
	staff s
JOIN
	company_divisons cd
ON
	s.department = cd.department
```
Running this query returns less than 1000 results. This is because there are some null values in the database.
The Query below returns the null values:

```sql
SELECT
	s.last_name,
    s.department,
    cd.company_division
FROM 
	staff s LEFT JOIN
	company_divisions cd
ON
	s.department = cd.department
WHERE company_division IS NULL
/* This is how we find the companies without a company_division*/
```

Output:
				(NULLS)
				
| last_name | department | company_division |
| --------- | ---------- | ---------------- |
| Scott     | Books      |                  |
| Smith     | Books      |                  |
| Palmer    | Books      |                  |
| Howell    | Books      |                  |
| Larson    | Books      |                  |
| Robinson  | Books      |                  |
| Fields    | Books      |                  |
| Fox       | Books      |                  |
| Reynolds  | Books      |                  |
| Watson    | Books      |                  |
| Peterson  | Books      |                  |
| Griffin   | Books      |                  |
| Fowler    | Books      |                  |
| Stone     | Books      |                  |
| Rivera    | Books      |                  |
| Moreno    | Books      |                  |
| Harris    | Books      |                  |
| Mccoy     | Books      |                  |
| Ray       | Books      |                  |
| Wheeler   | Books      |                  |
| Owens     | Books      |                  |
| Fuller    | Books      |                  |
| Murphy    | Books      |                  |
| Bailey    | Books      |                  |
| Brooks    | Books      |                  |
| Lane      | Books      |                  |
| Arnold    | Books      |                  |
| Jordan    | Books      |                  |
| Matthews  | Books      |                  |
| Black     | Books      |                  |
| Rice      | Books      |                  |
| Reynolds  | Books      |                  |
| Little    | Books      |                  |
| Olson     | Books      |                  |
| Garza     | Books      |                  |
| Campbell  | Books      |                  |
| Payne     | Books      |                  |
| Elliott   | Books      |                  |
| Hall      | Books      |                  |
| Hunter    | Books      |                  |
| Turner    | Books      |                  |
| Hamilton  | Books      |                  |
| Johnson   | Books      |                  |
| Spencer   | Books      |                  |
| Perry     | Books      |                  |
| Hudson    | Books      |                  |
| Anderson  | Books      |                  |
