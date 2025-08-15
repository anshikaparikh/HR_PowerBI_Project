# HR_PowerBI_Project
1. Objective

To analyze employee data and provide actionable insights into workforce demographics, attrition trends, and department performance using Power BI.

2. Dataset Details

Source: HR Employee Data (Employee, Survey, Training tables)

Size: ~3000 employee records

Key Columns: Employee ID, Department, Gender, Age, Start Date, Exit Date, Training Date, Survey Date

Time Period: Multiple years of employee records

3. Steps Taken
Data Transformation

Cleaned null/missing values

Converted date formats

Derived calculated columns: Age, Tenure, IsActive, Tenure Group

Removed duplicates & ensured correct data types

Data Modelling

Created Date Table and marked as Date Table

Established relationships between:

Employee ↔ Date Table (via StartDate, ExitDate, TrainingDate)

Set Active relationship with Training Date for analysis

Removed ambiguous relationships

DAX Measures

Total Employees = COUNTROWS(Employee)

Active Employees = CALCULATE(COUNTROWS(Employee), Employee[IsActive] = "Yes")

Attrition Count = CALCULATE(COUNTROWS(Employee), Employee[IsActive] = "No")

Attrition Rate = DIVIDE([Attrition Count], [Total Employees], 0)

Average Age = AVERAGE(Employee[Age])

Average Tenure = AVERAGE(Employee[Tenure])

Visualizations

KPI Cards: Total Employees, Active Employees, Attrition Rate, Average Age, Average Tenure

Bar Charts: Department-wise Headcount, Gender Distribution

Line Chart: Monthly Hires vs Exits

Slicers:  Department, Gender, IsActive (with sync for all pages)

4. Key Insights

Attrition Rate: ~51%, indicating high employee turnover.

Highest Attrition: Sales & Production departments.

Average Age: ~54 years, suggesting senior workforce dominance.


Gender Ratio: Slightly male-dominated workforce.

New Hires Trend: Most hires in 2019–2020, decline after 2021.
