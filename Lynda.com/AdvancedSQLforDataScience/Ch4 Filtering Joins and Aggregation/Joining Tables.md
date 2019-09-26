## IN PROGRESS
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

    
/*First we want to visualize the different columns from company divisons*/

/*The problem we're trying to solve is the staff table includes a department for each employee. Since we dont keep division information in the staff table, we have to look it up.*/

