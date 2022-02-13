## Overview of the analysis: Explain the purpose of this analysis.

This analysis/project is mainly to forecast the situation that will arise in future regarding mass employee retirement as majority of the employee in the company/organisation are on the verge of retirement according to their joining date and/or birth date. This analysis will give the mangement about the timeline of employees retirement and numbers basis  titles as below:

![image](https://user-images.githubusercontent.com/96365651/153735757-489879b5-f7c4-4069-881b-dca9c1f788a1.png)

Also, we have submitting numbers of retirees according to the department name and list of the candidates who are reitiring, but still can mentor new hires for easy transition.

## Results: Provide a bulleted list with four major points from the two analysis deliverables. Use images as support where needed.

A) From the output of retiring_titles analysis there are 2 major concerns which needs to be addressed/taken care immediately
  
      1) Out of 25,916 employees who are retiring from the designation of "Senior Engineer" in near future, only 261 employees are eligible for mentoring. This can be dire situation if management does not take imnediate action and start hiring soon to keep the gap less between new hires and retirees.
      2) Out of 24,926 employees who are retiring from the designation of "Senior Staff" in near future, only 439 employees are eligible for mentoring. This can be dire situation if management does not take imnediate action and start hiring soon to keep the gap less between new hires and retirees.


B) From the output of mentorship_eligibilty analysis there are 2 further major issues as below

      1) Only 57 Assistant Engineers are eligible for mentorship after retirement. The number is very low
      2) Only 77 Technique Leader are eligible for mentorship after retirement. The number is very low and the position is techinical and that too of a management level. Management have to start working and train existing junior employee so that they can take lead position in future. 

![image](https://user-images.githubusercontent.com/96365651/153738992-2a0717ae-88d8-430d-ac63-542b29ad60a5.png)



## Summary: Provide high-level responses to the following questions, then provide two additional queries or tables that may provide more insight into the upcoming "silver tsunami."

# How many roles will need to be filled as the "silver tsunami" begins to make an impact?

Assuming that out of total employee to be retired of 72,458 emplyees, 1,549 are eligible for mentorship. According to that calculation, we can say that organisation needs to start hire (not immediately but soon) 70,909 employees. However to prepare for Silver Tsunami organisation needs to start hiring employees in percentage of the headcount requirement so that at the end when the existing employees are retiring, organisation will be placed in better position to not get impacted by mass retirement.

# Are there enough qualified, retirement-ready employees in the departments to mentor the next generation of Pewlett Hackard employees?

As of now when we look at the count of eligible mentors, it seems to be very low compared to the numbers of retirement-ready employees. However management can make the eligibility criteria a bit lenient so that more retirement-ready employees can be eligible for mentorship and can remain with the organisation after retirement for training new hires. This seems to be best way to increase the number of mentors who can support now employees to settle-in quickly and at the same time organisation will not impacted due to mass retirement.


**Query No. 1**

SELECT COUNT(me.emp_no), me.title

INTO mentorship_counts

FROM mentorship_eligibilty as me

GROUP BY me.title

ORDER BY COUNT(me.emp_no) DESC;

![image](https://user-images.githubusercontent.com/96365651/153741018-6173b7d0-6308-4ca5-a8b4-039342eaceef.png)


**Query No. 2**

SELECT d.dept_name, ROUND(SUM(s.salary), 2)

INTO dept_salary

FROM salaries AS s

INNER JOIN dept_emp AS de ON (de.emp_no = s.emp_no)

INNER JOIN departments AS d ON (d.dept_no = de.dept_no )

GROUP BY d.dept_name;

![image](https://user-images.githubusercontent.com/96365651/153741116-df8e4cd5-9c20-47a6-948a-9d9d1c020e20.png)












