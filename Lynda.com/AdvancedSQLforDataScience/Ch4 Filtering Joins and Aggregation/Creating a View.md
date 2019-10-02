In this excercise we group data from the staff, company divisons, and company regencetable. We want to createa view withthe approrpriate joins. This savestime and saves us from having to repeatedly right join statements

```sql
/*what we have here is a select statement that uses two left joins and
it selects all the rows from the staff table, it selects the company division, and the company regions name.*/
/* To not keep typing it, we use the CREATE VIEW command */

CREATE VIEW staff_div_reg AS 
SELECT
	s.*, cd.company_division, cr.company_regions
FROM 
	staff s
LEFT JOIN
	company_divisions cd
ON
	s.department = cd.department
LEFT JOIN
	company_regions cr
on
	s.region_id = cr.region_id
```

To check, we use:
```sql
SELECT
	count(*)
FROM
	staff_div_reg
```

All the rows we ned are returned
