First we list each department in each row:
```sql
/* List departments in each row */
select
   department
from
   staff;
```

Then we use the distinct function to list each department name once:

```sql
/* List each department name once */
select distinct
  department
from
  staff;
```

Below e convert the department names to do different cases :
```sql
/* Convert the names of departments to upper case */
select distinct
   upper(department)
from
   staff;

/* Convert the names of departments to lower case */
select distinct
  lower(department)
from
  staff;
```

Below we concatenate two character strings together:

```sql
/* Concatenate two character strings */
select
  job_title || '-' || department
from
  staff;
```

Trimming whitepsace:
```sql
SELECT
   trim('   Software Engineer  ')
```

