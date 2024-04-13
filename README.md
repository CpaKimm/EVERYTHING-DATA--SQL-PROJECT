# Human Resources Analysis

****Project Overview**

The data analysis intends to provide insights on employee distribution within the organization as well as termination isights. 
By analysizing the data, am able to know ethnicity, gender, locality  source and popular recruitment of employees to assist in future recruitments.


**Data Analysis**

	The human resource data was obtained from Kaggle website.

	The data was clean and did not require any cleaning.

	Used SQL to write queries which provide the needed data.

	Used power BI for visualization

**Analysis Questions**

1.	What is the employee gender distribution in the organization?
	
3.	What is the employee Marital status distribution in the organization?

5.	What is the employee Ethnicity distribution of employees?

7.	What is the employee citizenship distribution of employees?
	
9.	What is the employee termination distribution per department?

11.	What is the employee Performance Score distribution?

13.	What is the employee total number of Employees terminated?

15.	What is the employee termination distribution?
	
17.	What is the employee termination distribution per gender?
	
19.	Which department has the highest employee turnover

21.	What is the employee distribution of Recruitment source?

23.	No of employees per department

25.	No of managers

27.	No of Active Employees

29.	Average employee satisfaction rate


**SQL Queries**

--1.	Sex distribution in the organization

Select Sex, count(Sex) as No_Of_Employees from hr
where EmploymentStatus = 'active'
group by Sex

 


--2.	Marital status distribution in the organization

Select MaritalDesc, count(MaritalDesc) as No_Of_Employees from hr
where EmploymentStatus = 'active'
group by MaritalDesc

 

--3.    Ethnicity distribution of employees

Select RaceDesc, count(RaceDesc) as No_Of_Employees from hr
where EmploymentStatus = 'active'
group by RaceDesc

 

--4.	citizenship distribution of employees

Select CitizenDesc, count(CitizenDesc) as No_Of_Employees from hr
where EmploymentStatus = 'active'
group by CitizenDesc


 



--5.	Termination distrbution per department

Select Department, count(TermReason) as Terminated_Cases from hr
where DateofTermination is not null
group by Department

 



--6.	Performance Score distribution

Select PerformanceScore, count(PerformanceScore) as No_Of_Employees from hr
where DateofTermination is null
group by PerformanceScore

 

--7.	Total number of Employees terminated

select count(DateofTermination) as No_Terminated_Employees from hr
where DateofTermination is not null

 

--8.    Reason for termination distribution

Select TermReason, count(TermReason) as No_Terminated_Employees from hr
where DateofTermination is not null
group by TermReason
 


--9.	Termination distrbution per gender

Select Sex, count(TermReason) as No_Of_Employees from hr
group by Sex

 


--10.	Department with highest employee turnover

Select top 1 Department, count(TermReason) as No_Of_Employees from hr
group by Department
order by No_Of_Employees desc

 
--11.	Distribution of Recruitment source

Select RecruitmentSource, count(RecruitmentSource) as No_Of_Employees from hr
group by RecruitmentSource

 

--12.	No of employees per departments

Select Department, count(Department) as No_Of_Employees from hr
where EmploymentStatus = 'active'
group by Department

 


--13.	No of managers

select count(distinct managerID) Count_Of_Managers from hr
where EmploymentStatus = 'active'
 
--14.	No of Active Employees

select count(EmploymentStatus) Total_Active_Employees from hr
where EmploymentStatus = 'active'

 
--15.	Avg Employee satifaction

select avg(EmpSatisfaction) Avg_Employees_Satisfaction from hr


 **Analysis Findings**

 	There are more females than males in the organization. 56% female and 44% male. The organization should strive to employ more females in future recruitment.
 
	There are more single people in the organization

	There are more white people in the organization. They form 60% of total employees.

	Most of the employees are US Citizens at 96%

	The production department has the highest termination cases at 80%

	78% of the employees fully meet the performance score while 4% do not.

	Employee movement to another position is the main termination reason.

	60% of terminated employees are females

	42% of the active employees were recruited through Indeed. The online web application is the least used recruitment source.

	The production department has the highest number of employees and constitutes 60% of the employee population.

	The organization has a total of 21 active managers

	The organization has 207 active employees while 104 have been terminated.

	The Average employee satisfaction rate is 3


