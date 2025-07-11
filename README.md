# My Excel Data Analytics Projects

I completed these projects showcasing my skills in Excel with the help of Luke Barousse's "Excel for Data Analytics" YouTube video (https://youtu.be/pCJ15nGFgVg?si=VyeR3DjywT_Cs24J). Throughout the process I learned not only the basics about Excel such as formulas, charts, and spreadsheets, but also some of the more advanced features of Excel like pivot tables, power query, and power pivot.



## Project 1: Salary Dashboard
This dashboard analyzes how the job title, country, and employment type (full-time, part-time, etc.) impact salary.

![image](https://github.com/user-attachments/assets/41dbc78b-8ac5-408e-b1ba-20689f9a2c4d)


### Skill 1 Used - Charts
- Used a bar chart to help visualize the difference in median salary between major job titles (data scientist, data analyst, data engineer, etc.)
- Used a map chart have an easier time visualizing where most jobs were being posted geographically
- Used a bar chart to clearly compare what type of employment was most common for data jobs


### Skill 2 Used - Formulas
Below is the formula used to calculate the median salary of jobs according to the title.
```
=MEDIAN(
  IF(
    (jobs[job_title_short]=A2)*
    (jobs[job_country]=country)*
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
    (jobs[salary_year_avg]<>0),
    jobs[salary_year_avg]
  )
)
```
The code would only include a job's salary_year_avg in the overall median calculation for that job title if...
- Job title matched the desired title
- Job country matched the desired country
- Job type matched the desired employment type, and
- The job entry didn't have a blank value listed for their salary_year_avg


### Skill 3 Used - Data Validation
- Created filtered lists for job title, country, and employment type that were added as data validation rules
- This ensured an user could easily change what data they were looking at while being restricted to existing values only

[Find my work here](Project_1-Dashboard)



## Project 2: Salary Analysis
This analysis aimed to discover which skills were most sought after and how knowledge of those skills impacted someone's salary.

![image](https://github.com/user-attachments/assets/64a06beb-8f1a-4b7f-bc2d-625434c7460b)
![image](https://github.com/user-attachments/assets/38eee553-4a07-448e-b127-cf7c88cabde7)


### Skill 1 Used - Pivot Tables and Pivot Charts
- Created pivot tables which allowed me the flexibility to add and remove variables from my table as I saw fit
- Created pivot charts that created a visualization of the relationship of different variables such as median salary and skill likelihood (what % of the job postings specified that skill)
- Both pivot tables and pivot charts helped give me a deeper understanding of how variables in my dataset interacted with each other


### Skill 2 Used - Power Query
- Used to perform ETL (Extract, Transform, and Load) for the project
- Extract: From one Excel file I created two queries. One that contained all the information about the job postings, and one that contained just the job title and skills requested
- Transform: Cleaning the data by removing columns that were unneeded, trimming whitespace, and editing the format of certain columns
- Load: Loaded both queries into my workbook to act as the basis of the data model I would use for the project


### Skill 3 Used - Power Pivot
- Created a relationship between my two queries to view valuable information from both of them
- Created explicit measures such as the median salary for jobs in the US and the median salary for jobs outside the US, allowing me to perform further analysis (not pictured above)

[Find my work here](Project_2-Analysis)
