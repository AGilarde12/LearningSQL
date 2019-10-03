Using the view we just made in our previous exercise, we select the company division, company region, gender, and their counts from the view

We also group the columns using a group set, and order them as well.

```sql
SELECT
	company_division,
	company_regions,
	gender,
	count(*)
FROM
	staff_div_reg
GROUP BY
	GROUPING SETS (company_division, company_regions, gender)
ORDER BY
	company_regions,
	company_division,
	gender
```

