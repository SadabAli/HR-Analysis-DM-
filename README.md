# PRDA-03 HR Analytics

## 📊 Project Overview

This project focuses on analyzing employee workforce data using **Power
BI**. The objective is to understand workforce size, demographics, work
location, hiring and termination trends, departmental distribution,
employee status, and other HR characteristics.

The project was completed as part of the **DataMites -- Bengaluru,
Marathahalli** training program.

------------------------------------------------------------------------

## 🎯 Project Objectives

-   Analyze employee workforce data using Power BI.
-   Create important HR KPIs.
-   Analyze hiring trends by year.
-   Analyze gender, race, state, and department distributions.
-   Analyze employee age groups and employee status.
-   Analyze job titles and work locations.
-   Identify important HR insights.
-   Provide practical business suggestions based on the analysis.

------------------------------------------------------------------------

## 🗂️ Dataset

The project dataset contains **22,214 employee records**.

The dataset includes information such as:

-   Employee ID
-   First Name
-   Last Name
-   Birthdate
-   Age
-   Gender
-   Race
-   Department
-   Job Title
-   Location
-   Hire Date
-   Termination Date
-   City
-   State

------------------------------------------------------------------------

## 🧹 Data Preparation

The data was prepared using **Power Query** in Power BI.

### Termination Date Cleaning

The `termdate` column initially contained both the date and time.

The time portion was removed using:

**Text Before Delimiter → Space (" ")**

The column was then converted to the **Date** data type.

Missing termination dates were kept blank/null because they are useful
for identifying employees without a recorded termination date.

After the transformation, **Close & Apply** was used to load the cleaned
data into the Power BI model.

------------------------------------------------------------------------

## 📌 Key KPIs

  KPI                    Value
  ------------------- --------
  Total Employees       22,214
  Average Age            38.43
  Remote Employee %     24.75%
  HQ Employee %         75.25%

### DAX Measures

``` dax
Total Employees = COUNTROWS(Hr)
```

``` dax
Remote Employees % =
DIVIDE(
    CALCULATE(
        COUNTROWS(Hr),
        Hr[location] = "Remote"
    ),
    [Total Employees],
    0
)
```

``` dax
HQ Employees % =
DIVIDE(
    CALCULATE(
        COUNTROWS(Hr),
        Hr[location] = "HQ"
    ),
    [Total Employees],
    0
)
```

``` dax
Average Age = AVERAGE(Hr[Age])
```

------------------------------------------------------------------------

## 📈 Power BI Dashboard

The dashboard contains the following visualizations:

-   Hired Employees by Year
-   Terminated Employees by Year
-   Gender Distribution
-   Employees by State
-   Employees by Department
-   Employees by Race
-   Employees by Job Title
-   Employee Distribution by Location
-   Employee Status
-   Age Group Distribution
-   Employee Status by Department

The dashboard was intentionally kept focused instead of creating a
separate visualization for every column.

------------------------------------------------------------------------

## 🔎 Key Insights

### Workforce

-   The analysis covers **22,214 employee records**.
-   The average employee age is **38.43 years**.
-   **75.25%** of employees are classified as Headquarters-based.
-   **24.75%** are classified as Remote.

### Department

-   **Engineering** is the largest department with approximately **6.7K
    employees**.
-   **Accounting** is the second-largest displayed department with
    approximately **3.3K employees**.

### Location

-   **Ohio** has the largest employee concentration, with approximately
    **18.0K employees** shown in the dashboard.
-   Headquarters employees significantly outnumber Remote employees.

### Age

-   The **25--34, 35--44, and 45--54** groups are the largest age
    segments.
-   The Under 25 and 55+ groups are smaller in comparison.

### Employee Status

-   **18.29K (82.31%)** employees are classified as Active.
-   **3.93K (17.69%)** employees are classified as Terminated.

### Job Titles

Among the displayed job titles:

1.  Research Assistant II -- **754**
2.  Business Analyst -- **708**
3.  Human Resources Analyst II -- **613**
4.  Research Assistant -- **538**

### Hiring & Termination

-   Hiring counts show a sharp rise at the beginning of the displayed
    period followed by a comparatively stable pattern.
-   Termination counts increase to a visible peak and then decline
    toward the later period.

------------------------------------------------------------------------

## 💡 Business Suggestions

Based on the dashboard analysis:

1.  **Workforce Planning**\
    Review staffing requirements and future skill needs in Engineering
    because it has the largest workforce.

2.  **Remote/Hybrid Work Analysis**\
    Review which roles may be suitable for remote or hybrid work
    considering the current HQ and Remote distribution.

3.  **Employee Retention Analysis**\
    Investigate termination patterns by department, job title, age
    group, and location.

4.  **Training & Development**\
    Design training and career-development programs around the needs of
    the large 25--54 workforce segments.

5.  **Geographic Workforce Planning**\
    Monitor workforce concentration in Ohio and other locations for
    future hiring and capacity planning.

6.  **Continuous HR Reporting**\
    Continue using Power BI dashboards to monitor headcount, hiring,
    employee status, demographics, and workforce distribution.

------------------------------------------------------------------------

## 🛠️ Tools & Technologies

-   **Microsoft Power BI**
-   **Power Query**
-   **DAX**
-   **Microsoft Excel**

------------------------------------------------------------------------

## 📁 Project Deliverables

-   Power BI HR Analytics Dashboard
-   HR Analytics Project Report
-   Project Presentation (PPT)
-   Dataset analysis and KPI calculations

------------------------------------------------------------------------

## ⚠️ Note

The dashboard provides **descriptive analysis** of the available
employee data. The observed patterns do not by themselves establish
causal reasons for hiring or employee termination.

Also, the dashboard visual originally titled **"Hiring Rate by Year"**
is based on hired-employee counts by year. Therefore, it is described in
this README as **"Hired Employees by Year"**.

------------------------------------------------------------------------

## 👨‍💻 Author

**Mir Sadab Ali**

B.Tech -- Computer Science & Engineering\
Centurion University of Technology and Management

**Project:** PRDA-03 HR Analytics\
**Training:** DataMites -- Bengaluru, Marathahalli
