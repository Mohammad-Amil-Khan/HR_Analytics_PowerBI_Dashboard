# HR Analytics Dashboard - Employee Insights

## Introduction

This Power BI dashboard analyzes HR data to derive key workforce insights, focusing on employee attrition, tenure, salary distribution, and demographic trends. The dashboard uses DAX measures to compute essential HR metrics, enabling data-driven decision-making.

## Dataset Overview

The dataset consists of **1480 records** and **38 columns**, capturing employee demographics, job roles, performance ratings, and attrition data.

## Objective

The aim of this project is to develop an HR Analytics Dashboard using Power BI to analyze key workforce metrics, enabling data-driven decision-making for employee attrition, tenure, salary distribution, and demographic trends.

## Key DAX Measures & Insights

### 1. Employee Count

- **Question:** How many unique employees are currently in the organization?
- **DAX Measure:**
  ```DAX
  Employee_Count = DISTINCTCOUNT(HR_Analytics[EmpID])
  ```
- **Insight:** Ensures the count of unique employees, preventing duplication errors. The total workforce size is a fundamental HR metric.

### 2. Employee Attrition

- **Question:** Determine how many employees have left the company over time?
- **DAX Measure:**
  ```DAX
  Employee_Attrition = CALCULATE([Employee_Count], HR_Analytics[Attrition]="Yes")
  ```
- **Insight:** Helps track the number of employees who have left the organization, which is crucial for analyzing turnover trends.

### 3. Attrition Percentage

- **Question:** What percentage of the workforce is leaving the company, and how does it impact our business?
- **DAX Measure:**
  ```DAX
  Attrition% = [Employee_Attrition]/[Employee_Count]
  ```
- **Insight:** Represents workforce stability. A high attrition rate signals possible issues like dissatisfaction, salary gaps, or management concerns.

### 4. Average Years at Company

- **Question:** What is the average tenure of employees in the organization?
- **DAX Measure:**
  ```DAX
  Avg_Years_atCompany = AVERAGE(HR_Analytics[YearsAtCompany])
  ```
- **Insight:** Indicates employee retention and tenure trends. A lower average tenure may suggest hiring and retention challenges.

### 5. Average Salary

- **Question:** What is the average monthly salary of the employees, and how does it vary across departments?
- **DAX Measure:**
  ```DAX
  Avg_Salary = AVERAGE(HR_Analytics[MonthlyIncome])
  ```
- **Insight:** Reflects salary distribution. Comparing this metric across departments helps in ensuring equitable compensation.

### 6. Average Age of Employees

- **Question:** What is the average age of the employees, and how does it affect workforce planning?
- **DAX Measure:**
  ```DAX
  Avg_Age = AVERAGE(HR_Analytics[Age])
  ```
- **Insight:** Identifies workforce demographics. An older average age may indicate experience but could also mean future retirement planning challenges.

## Dashboard Analysis & Visuals

### 1. Attrition by Age Group (Bar Graph)

- **Question:** How does employee attrition vary across different age groups?
- **Insight:** Younger employees (e.g., 20–35 years) have the highest attrition rate, indicating possible dissatisfaction, career switching, or lack of growth opportunities. Older employees (40+ years) have lower attrition, suggesting stability and long-term commitment.

### 2. Attrition by Years at Company (Histogram)

- **Question:** What is the trend of attrition based on the number of years employees have been with the company?
- **Insight:** Employees with fewer years at the company (0–5 years) show the highest attrition, indicating early-stage dissatisfaction or ineffective onboarding. Employees with longer tenure (10+ years) have significantly lower attrition, showing higher company loyalty.

### 3. Attrition by Education Field (Donut Chart)

- **Question:** Which education fields experience the highest employee attrition, and why?
- **Insight:** Certain education fields, such as **Life Science** and **Medical** experience higher attrition, possibly due to better opportunities elsewhere or lack of career advancement. Employees from **Technical** fields show relatively stable retention.

### 4. Employees Attrition by Job Role & Job Satisfaction (100% Stacked Bar Chart)

- **Question:** How does job role and job satisfaction influence employee attrition?
- **Insight:** Job roles with high attrition include **Sales Executive** and **Laboratory Technician**, possibly due to work pressure or limited career growth. Employees with lower job satisfaction ratings (**1 or 2**) contribute significantly to attrition, highlighting the need for better engagement strategies.

## Conclusion & Recommendations

- **High Attrition Rate:** Departments with high attrition should be analyzed for work conditions, salary disparities, and engagement initiatives.
- **Salary Adjustments:** HR should review job roles with low salaries to improve retention and motivation.
- **Retention Strategies:** Since early attrition is high, onboarding programs and mentorship initiatives should be reinforced.
- **Succession Planning:** Older workforce segments need structured career transition and knowledge-sharing plans.
