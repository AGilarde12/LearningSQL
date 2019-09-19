# Basic Statistical functions in SQL

Firstly, let's use the database to understand the total salary being paid out to employees:
```sql
SELECT
sum(salary)
FROM
STAFF
```
The printout reads: "97,331,223"

Second, let's break it down by department ordered by the salary sums (for the top 5 departments):
```sql
SELECT department,sum(salary)
FROM STAFF
Group by department
ORDER BY sum(salary) DESC
Limit 5
```
Output:

| Department | Sum     |
|------------|---------|
| Beauty     | 5481063 |
| Outdoors   | 5378660 |
| Computers  | 5152963 |
| Games      | 5090304 |
| Clothing   | 5037890 |


Now lets attach an AVG function to it rounding for 2 decimals:
```sql
SELECT
department,sum(salary), round(avg(salary),2)
FROM STAFF
Group by department
ORDER BY sum(salary) DESC
Limit 5
```
Output:

| Department | Sum     | Avg         |
|------------|---------|-------------|
| Beauty     | 5481063 | "103416.28" |
| Outdoors   | 5378660 | "112055.42" |
| Computers  | 5152963 | "99095.44"  |
| Games      | 5090304 | "103883.76" |
| Clothing   | 5037890 | "95054.53"  |


Finally let's attach the variance and STDV of the population:
```sql
SELECT
department, sum(salary), round(avg(salary),2), round(var_pop(salary),2), round(stddev_pop(salary),2)
FROM STAFF
Group by department
ORDER BY sum(salary) DESC
Limit 5
```
Output:

| Department | Sum     | Avg         | Variance        | STDV       |				
|------------|---------|-------------|-----------------|------------|				
| Beauty     | 5,481,063 | 103,416.28 | 952,478,558.54  | 30,862.25 |				
| Outdoors   | 5,378,660 | 112,055.42 | 745,849,798.45  | 27,310.25 |				
| Computers  | 5,152,963 | 99,095.44  | 930,175,201.52  | 30,498.77 |				
| Games      | 5,090,304 | 103,883.76 | 104,0425,239.16 | 32,255.62 |				
| Clothing   | 5,037,890 | 95,054.53  | 1,000,324,590.36 | 31,627.91 |				
