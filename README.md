# Silver_Tsunami

## Overview of the Analysis
  Through this analysis we intend to know how many employees out of the total population are soon to be retired and how many are elegible for the mentorhip program.
  
##Results
Seniour Staff members have the highest retiring count among the rest of the titles and engineers will be the second. This must create a warning that company should start developing internal positions or seek for them in the market. 


#SUMMARY 
Using the next code, we found out that there are no managers that are currently elegible for the program. Also we found out htat 58% of the population are males and the rest are females. This was possible by matching the emp no from the last table created and joining with the gender from the employee database. 
SELECT DISTINCT ON (e.emp_no)
	e.emp_no,
	e.first_name,
	e.last_name,
	e.birth_date,
	de.from_date,
	de.to_date,
	ti.title
INTO mentorship_elegibility
FROM employees as e
	INNER JOIN dept_emp as de
		ON (e.emp_no = de.emp_no)
	Inner JOIN titles as ti
		ON (ti.emp_no = e.emp_no)
WHERE de.to_date = '9999-01-01' 
	AND (e.birth_date BETWEEN '1965-01-01' AND '1965-12-31')
ORDER BY e.emp_no;
