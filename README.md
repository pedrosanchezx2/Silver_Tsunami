# Silver_Tsunami

## Overview of the Analysis
  Through this analysis we intend to know how many employees out of the total population are soon to be retired and how many are elegible for the mentorhip program.
  
## Results
- 1,549 roles need to be filled as the silver tsunami begins to impact. 

![image](https://user-images.githubusercontent.com/113708861/203562091-f6b5677c-554a-4adf-b558-6699003fcd1f.png)
-We have enough staff members to mentor the next generation of Pewlett Hackard employees, but saying that they are qualified, requieres more comprehension on the list of minimun required habilities to fulfill the job (soft and hard skills).
- Seniour Staff members have the highest retiring count among the rest of the titles and engineers will be the second. This must create a warning that company should start developing internal positions or seek for them in the market. 
- 97% of the population, their birthdate is in January. 

![image](https://user-images.githubusercontent.com/113708861/203564408-ede977e8-21c2-4a2b-ad58-a9c9ca7e32ce.png)
- There was a 17 years gap for the elegible employees, meaning we could be expecting that next generation will round between 15 - 17 years. 

![image](https://user-images.githubusercontent.com/113708861/203565339-b0654d1d-1900-4ea4-a49a-a79d333ff514.png)


## Summary 
- Using the next code, we found out that there are no managers that are currently elegible for the program.
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

- Also we found out that 58% of the population are males and the rest are females. This was possible by matching the emp no from the last table created and joining with the gender from the employee database. 


*I was asked on my last submission to upload the ERD but it is not part of the deliverable requirements, only asked to use it for the analysis. Only 10 tables are able to be shown in the non paid subscription. 
![image](https://user-images.githubusercontent.com/113708861/203561280-f1373372-f8e7-4ba6-9329-42b14d2b9586.png)

*Please note that CSV files are uploaded directly to the github
![image](https://user-images.githubusercontent.com/113708861/203560215-1e87dc98-b784-43a9-af34-4f828a5ad3ae.png)

