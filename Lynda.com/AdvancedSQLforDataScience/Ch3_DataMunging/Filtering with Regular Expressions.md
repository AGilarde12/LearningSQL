Let's select just assistants at levels three or four. To do that I use the SIMILAR TO operator. Now I want to match anything that has the word assistant, and has either the roman numeral III or the roman numeral IV.
```sql
SELECT job_title
FROM staff
Where job_title SIMILAR TO '%Assistant%(III|IV)'
LIMIT 5
```
The output is:

| Job Title                      |
|--------------------------------|
| "Office Assistant IV"          |
| "Accounting Assistant III"     |
| "Research Assistant IV"        |
| "Research Assistant IV"        |
| "Human Resources Assistant IV" |
