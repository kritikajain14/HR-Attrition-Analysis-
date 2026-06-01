# HR-Attrition-Analysis
A 3-page interactive Power BI dashboard analysing employee attrition across 1,470 IBM employees

# 📌 Key Findings
-- Attrition Rate -  16.12% — 237 out of 1,470 employees left
-- Top Department - Sales accounts for 56% of all exits
--Top Roles Leaving - Laboratory Technicians & Sales Executives
-- Salary Impact - Lowest salary band has the highest churn rate
-- Tenure Danger Zone - Year 1–2 shows the sharpest attrition spike
-- Root Cause - Low job satisfaction + poor work-life balance = highest risk

<img width="1920" height="1080" alt="Screenshot 2026-06-01 161934" src="https://github.com/user-attachments/assets/8ac4c7b1-fdfe-4b81-a38f-f7746897849c" />
<img width="1920" height="1080" alt="Screenshot 2026-06-01 161922" src="https://github.com/user-attachments/assets/5ba75b07-6a9d-417d-9db9-07f1096809e9" />
<img width="1920" height="1080" alt="Screenshot 2026-06-01 161906" src="https://github.com/user-attachments/assets/c9a6f857-d10b-4e5d-b824-4f7cce58da66" />

## 📊 Dashboard Pages
# Page 1 — Overview

KPI cards: Total Employees, Active Employees, Attrition Count, Attrition Rate
Donut chart: Attrition by Department
Bar chart: Attrition by Job Role
Slicer: Filter by Department

# Page 2 — Who Is Leaving?

Column chart: Attrition by Age Group
Bar chart: Attrition by Salary Slab
Matrix with conditional formatting: Attrition by Education Field + Gender

# Page 3 — Why Are They Leaving?

Line chart: Attrition by Years at Company
Bar chart: Attrition by Job Satisfaction (1–4 scale)
Bar chart: Attrition by Work-Life Balance (1–4 scale)

# 🗂️ Dataset
Source: IBM HR Analytics Employee Attrition Dataset — Kaggle
Rows - 1,470 
Columns - 35 (after cleaning: 32)
Target Variable - Attrition (Yes / No)

# 🛠️ Tools & Techniques
Power Query (Data Cleaning)

Removed redundant columns: EmployeeCount, Over18, StandardHours
Fixed data types for numeric and categorical fields
Created Age Group and Salary Slab calculated columns

# DAX Measures 
Attrition Rate = 
DIVIDE(
    COUNTROWS(FILTER(HR_Data, HR_Data[Attrition] = "Yes")),
    COUNTROWS(HR_Data),
    0
)

Active Employees = 
COUNTROWS(FILTER(HR_Data, HR_Data[Attrition] = "No"))

Avg Monthly Income = AVERAGE(HR_Data[MonthlyIncome])

Attrition Count = 
COUNTROWS(FILTER(HR_Data, HR_Data[Attrition] = "Yes"))





