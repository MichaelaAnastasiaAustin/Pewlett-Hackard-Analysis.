# Pewlett-Hackard-Analysis.

## Overview of the analysis

The purpose of this analysis was to help prepare Bobby’s manager for the “silver tsunami” as many current employees reach retirement age. Specifically, we were asked to determine the number of retiring employees per title, as well as identify employees who are eligible to participate in a mentorship program. 

## Results

### Retirement Titles
- First, we created a "Retirement Titles" query to find all the titles of employees who were born between January 1, 1952 and December 31, 1955. This resulted in an extremely large table (133,776 rows) that is difficult to work with. See linked table here [retirement_titles](Data/retirement_titles.csv). The large size of this output is because there are duplicate entries for the employees that have switched titles over the years.

### Unique Titles
- To remove these duplicates, we applied the DISTINCT ON statement to our query. This resulted in a condensed, but still very large table with 72,458 rows of data. See linked table here [unique_titles](Data/unique_titles.csv). The fact that the output of this "Unique Titles" table was still so large after condensing the data to only the most recent title of each employee underscores the mass exodus of employees who will be retiring.

### Retiring Titles
- Next, we applied GROUPBY to a new query to identify the number of employees by their most recent job title who are about to retire. This resulted in a much more accessible "Retiring Titles" table for us to analyze-- [retiring_titles](Data/retiring_titles.csv). Specifically, we can easily see that most retiring employees are either Senior Engineer(25,916 retiring) or Senior Staff(24,926 retiring). So, Pewlett Hackard will definitely need to prioritize filling these two positions.

![retiring_titles](https://github.com/MichaelaAnastasiaAustin/Pewlett-Hackard-Analysis./blob/main/retiring_titles_IMG.png)

### Mentorship Eligibility
- Finally, we created a table  that holds the employees who are eligible to participate in a mentorship program. This [mentorship_eligibility](Data/mentorship_eligibility.csv) produces 1549 rows of data-- a much smaller number of employees than the number retiring. But, this table provides a great starting point to identify just how many positions we can fill internally, before having to move to external recruitment.

![mentorship_eligibility](https://github.com/MichaelaAnastasiaAustin/Pewlett-Hackard-Analysis./blob/main/mentorship_eligibility_IMG.png)

## Summary

### How many roles will need to be filled as the "silver tsunami" begins to make an impact?

- To identify the total number of roles that will need to be filled as the "silver tsunami" begins to make an impact, we applied SUM to the "retiring_titles" query, as written in the Employee_Database_challenge.sql file. The output, saved as [total_roles](Data/total_roles.csv), tells us that there are 72,458 total roles that will need to be filled.


### Are there enough qualified, retirement-ready employees in the departments to mentor the next generation of Pewlett Hackard employees?

- To determine if there are enough qualified, retirement-ready employees in the departments to mentor the next generation of Pewlett Hackard employees, we created another query, applying GROUPBY so that we can group the mentor-eligible employees by department(see Employee_Database_challenge.sql file for query). This resulted in a new table linked here [mentorship_dept](Data/mentorship_dept.csv), which we can use to quickly compare to "retiring_titles". In doing so, we can see that there are significantly less mentor-eligible employees than there are retiring titles. So, we will need to look externally for support in mentoring the next generation of Pewlett Hackard employees.

![mentorship_dept](https://github.com/MichaelaAnastasiaAustin/Pewlett-Hackard-Analysis./blob/main/mentorship_dept_IMG.png)

