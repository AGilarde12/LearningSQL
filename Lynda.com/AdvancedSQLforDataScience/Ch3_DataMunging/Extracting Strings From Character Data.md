Using the Substring function for a string and a range it returns the characters from the string that are in that range
```sql
SELECT
	SUBSTRING('abcdefghijkl' FROM 1 FOR 3) test_string
  /* This returns abc */
```

Using the OVERLAY function we can change and edit strings to make it easier to work with.
Imagine we wanted to change an assistant job title to be asst.
```sql
SELECT
OVERLAY(job_title PLACING 'Asst.' FROM 1 FOR 9)
FROM staff
WHERE job_title LIKE 'Assistant%'
```
