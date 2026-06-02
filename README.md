# SQL-AND-POWER-BI-PROJECT-DATA-CLEANING-AND-VISUALIZATIONS-
An end-to-end HR data analysis project where I cleaned and analysed a dataset of over 22,000 employee records using MySQL, then visualised the findings in Power BI.

## Files Included
- <a href="https://github.com/AbdikadirIsse/SQL-AND-POWER-BI-PROJECT-DATA-CLEANING-AND-VISUALIZATIONS-/blob/main/The%20Raw%20Data%20Used.xlsx">Raw Dataset</a>
- <a href="https://github.com/AbdikadirIsse/SQL-AND-POWER-BI-PROJECT-DATA-CLEANING-AND-VISUALIZATIONS-/blob/main/SQL%20Queries%20used%20to%20clean%20the%20Data.sql">SQL Queries</a>
- <a href="https://github.com/AbdikadirIsse/SQL-AND-POWER-BI-PROJECT-DATA-CLEANING-AND-VISUALIZATIONS-/blob/main/POWER%20BI%20DASHBOARD%20-%20REPORT.pbix">PowerBI Report</a>

# Data Cleaning

- Renamed the ID column to employee_id for easier querying
- Standardised inconsistent date formats in birthdate and hire_date — some values used forward slashes, others used hyphens, and were converted using STR_TO_DATE and DATE_FORMAT
- Removed the timestamp and UTC value from termdate, keeping only the clean date
- Altered all date columns from text to proper DATE data type using ALTER TABLE
- Added a new age column calculated using TIMESTAMPDIFF between birthdate and current date
- Checked for outliers in age — found unrealistic birth years such as 2067 resulting in negative ages, and excluded all records where age was below 18 (967 records affected)
- Employees with a NULL termination date were treated as currently active


# Analysis — Questions Answered

- 1. What is the gender breakdown of employees?
- 2. What is the race/ethnicity breakdown?
- 3. What is the age distribution of employees?
- 4. How many employees work at headquarters vs remotely?
- 5. What is the average length of employment for terminated employees?
- 6. How does gender distribution vary across departments?
- 7. What is the distribution of job titles across the company?
- 8. Which department has the highest turnover rate?
- 9. How are employees distributed across states?
- 10. How has employee count changed over time (2000–2020)?
- 11. What is the average tenure by department?


# Power BI Dashboard
Built a two-page interactive dashboard in Power BI using the SQL query results of the above 11 Questions exported as CSV files:

## Page 1:

- Card showing average length of employment
- Bar chart - gender distribution
- Donut chart - headquarters vs remote employees
- Line chart - change in employee count from 2000 to 2020
- Map - employee distribution across US states
- Clustered column chart - race/ethnicity distribution

## Page 2:

- Clustered column chart - age group distribution
- Clustered column chart - age distribution by gender
- Table - department turnover rates sorted highest to lowest
- Clustered column chart - gender distribution by department

<img width="761" height="440" alt="Dashboard Page 1" src="https://github.com/user-attachments/assets/9f3269be-2cf7-4fc3-a638-7ab8f853bb4f" />
<img width="762" height="437" alt="Dashboard Page 2" src="https://github.com/user-attachments/assets/2f2541cd-77ca-4c1c-8ba1-c85fb3f27cf5" />




# Limitations

- Records with age below 18 were excluded due to unrealistic birth years found in the dataset, some employees had birth years as far as 2067, resulting in negative or impossible ages
- Termination dates set in the future were excluded from termination-related analysis
- NULL termination dates were treated as currently active employees


## Tools Used

- MySQL Workbench
- Power BI
