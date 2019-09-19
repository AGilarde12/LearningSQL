# Filtering and Grouping the Data

First, let's start by grouping the data by numeric values. Let's see who in the "Tools" department makes the most:
```sql
SELECT last_name, department, salary
FROM Staff
where salary > 100000 
AND department = 'Tools'
ORDER BY salary DESC
Limit 10
```
Output:

| Last Name    | Department | Salary |
|--------------|------------|--------|
| "Allen"      | "Tools"    | 149586 |
| "Harris"     | "Tools"    | 148940 |
| "Hill"       | "Tools"    | 144661 |
| "Webb"       | "Tools"    | 143595 |
| "Daniels"    | "Tools"    | 139061 |
| "Harvey"     | "Tools"    | 138179 |
| "Williamson" | "Tools"    | 135695 |
| "Cole"       | "Tools"    | 133190 |
| "Gonzalez"   | "Tools"    | 131830 |
| "Day"        | "Tools"    | 129890 |

Last lets find the same query, but with departments that begin with the letter B:
```sql
SELECT last_name, department, salary
FROM Staff
where salary > 100000 
AND department LIKE 'B%'
ORDER BY salary DESC
Limit 10
```
Output:

| Last Name   | Department | Salary |
|-------------|------------|--------|
| "Long"      | "Beauty"   | 149099 |
| "Howard"    | "Baby"     | 148687 |
| "Tucker"    | "Baby"     | 148573 |
| "Hudson"    | "Books"    | 146745 |
| "Perry"     | "Books"    | 146701 |
| "Rice"      | "Books"    | 145747 |
| "Wheeler"   | "Books"    | 145284 |
| "Armstrong" | "Beauty"   | 143853 |
| "Andrews"   | "Beauty"   | 142103 |
| "Moore"     | "Beauty"   | 142101 |
