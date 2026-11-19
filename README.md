# Who Leaves and Why? HR Employee Attrition Analysis & Data Storytelling

> An analysis featuring 15 visualizations based on IBM HR data to identify high-risk employee groups and formulate priority retention recommendations.

![Python](https://img.shields.io/badge/Python-3.x-blue)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-11557c)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-4c72b0)

<!-- Add a main project image here, for example, a chart showing attrition by Job Role:
![Preview](images/preview.png) -->

---

## Project Summary

Employee attrition (resignation) incurs costs related to recruitment, training, and the loss of institutional knowledge. This project analyzes **1,470 employees** from the *IBM HR Employee Attrition* dataset to answer: **who is most at risk of resigning, and what factors are associated with it?**

The project focuses on **data storytelling**—transforming raw data into clear visualizations, actionable insights, and measurable business recommendations. Each chart is designed using principles of *decluttering* (removing unnecessary elements) and *highlighting* (using accent colors specifically to draw attention to key groups).

> This project is an **exploratory and descriptive analysis**, not a predictive model.

## Business Problems

1. What kind of employees are most at risk of resigning?
2. Which factors (e.g., salary, overtime, tenure, job satisfaction, etc.) are associated with attrition?
3. Which interventions should the HR team prioritize?

## Dataset

| Item | Description |
|---|---| | Source | IBM HR Analytics Employee Attrition & Performance (public dataset, fictitious data) |
| Size | 1,470 rows, 35 columns |
| Target | `Attrition` (Yes = 237 employees, No = 1,233 employees) |
| Attrition rate | **16.1%** |
| Missing values ​​| None |

Features used include: `Age`, `MonthlyIncome`, `OverTime`, `YearsAtCompany`, `Department`, `JobRole`, `MaritalStatus`, `DistanceFromHome`, `Education`, and satisfaction scores (`JobSatisfaction`, `EnvironmentSatisfaction`, `WorkLifeBalance`, `RelationshipSatisfaction`).

## Analysis Steps

1. **Load data** and check its structure and for any missing values.
2. **Data cleaning**
- Remove 3 constant columns (`EmployeeCount`, `StandardHours`, `Over18`). 
- Create binary columns: `Attrition_bin` and `OverTime_bin`. 
- Convert ordinal scores (satisfaction, education) into human-readable labels. 
- Create categories for distance from home: Near (1–10 km), Medium (11–20 km), and Far (21–29 km).
3. **Visualization**: 15 charts categorized by three levels of difficulty (starter, guided, independent, and advanced).
4. **Insights**: Each chart includes observations, interpretations, and recommendations.
5. **Executive summary** with three priority recommendations.

## List of Visualizations

| No | Topic | Chart Type |
|:-:|---|---|
| 1 | Distribution of employee age | Histogram |
| 2 | Employee salary: Overtime vs. non-overtime | Boxplot |
| 3 | Average salary trend based on tenure | Line chart |
| 4 | Relationship between age and monthly income | Scatter plot |
| 5 | Number of employees by department | Bar chart |
| 6 | Proportion of education levels | Pie chart |
| 7 | Salary distribution: resigned vs. retained | Histogram |
| 8 | Work-life balance by department | Boxplot |
| 9 | Attrition rate by job role | Horizontal bar chart |
| 10 | Satisfaction score patterns by department | Heatmap |
| 11 | Overtime composition by department | Stacked bar chart |
| 12 | Distance from home and propensity to resign | Bar chart |
| 13 | Salary distribution and tenure | Histogram + boxplot |
| 14 | Marital status and attrition by job role | Stacked bar + bar chart |
| 15 | Satisfaction factors: resigned vs. retained | Heatmap + bar chart |

## Key Findings

**Employee profile at highest risk of resignation:** young (< 35 years old), low salary (< USD 3,500), short tenure (< 3 years), and frequent overtime.

- **Overtime:** Attrition is **30.5%** for employees who work overtime, compared to **10.4%** for those who do not (nearly 3 times higher). Approximately 28% of employees work overtime regularly, distributed evenly across all departments.
- **Job role:** **Sales Representative (39.8%)**—about 2.5 times the average—followed by Laboratory Technician (23.9%) and Human Resources (23.1%). The most stable roles are Research Director (2.5%) and Manager (4.9%).
- **Salary:** The median salary for employees who resigned is **USD 3,202**, compared to **USD 5,204** for those who remained. Among those who resigned, 47.7% earned less than USD 3,000 (compared to 22.9% among those who remained).
- **Tenure:** Attrition is **29.8%** for employees with < 2 years of tenure, compared to **10.8%** for those with > 5 years of tenure. - **Age:** 38.4% of employees who resigned were under 30 years old.
- **Marital status:** 25.5% for single employees, compared to 12.5% ​​for married employees and 10.1% for divorced employees.
- **Commute distance:** Attrition rates increase from 14.0% (1–10 km) to 20.0% (11–20 km) and 22.1% (21–29 km).
- **Department:** Sales 20.6%, Human Resources 19.0%, R&D 13.8%.
- **Education:** Attrition tends to decrease as the level of education increases, from 18.2% (below college level) to 10.4% (Doctor).
- **Satisfaction:** The largest gaps between employees who resigned and those who stayed are found in *Job Satisfaction* (Δ 0.31) and *Environment Satisfaction* (Δ 0.31), while *Work-Life Balance* shows a difference of only Δ 0.12.

## Priority Recommendations

| Priority | Intervention | Target | Timeline |
|:-:|---|---|---|
| 1 | Audit and adjust salaries for employees earning < USD 3,000 with < 2 years of tenure | Reduce entry-level attrition from ~30% to ≤ 18% | 3 months |
| 2 | Redesign incentives for Sales Representatives and implement company-wide overtime limits | Reduce Sales Representative attrition from 39.8% to ≤ 25% | 6 months |
| 3 | Implement a "First 3 Years Retention" program (milestone bonuses and guaranteed salary reviews) | Reduce attrition for employees with 0–2 years of tenure from 29.8% to ≤ 18% | 12 months |

## Repository Structure

```
.
├── README.md
├── HR-Employee-Attrition.csv        # dataset
├── Full_Answer_HR_Attrition.ipynb   # analysis notebook
└── images/                          # (optional) screenshots of charts for the README
```

## How to Run

```bash
# 1. Clone the repository
git clone https://github.com/<username>/<repo-name>.git
cd <repo-name>

# 2. Install libraries
pip install pandas numpy matplotlib seaborn jupyter

# 3. Run the notebook
jupyter notebook Full_Answer_HR_Attrition.ipynb
```

Ensure the `HR-Employee-Attrition.csv` file is located in the same folder as the notebook.

## Limitations

- The relationships identified are **correlational**, not causal.
- The dataset is fictitious and represents a single point in time; therefore, longitudinal trends cannot be analyzed. - The monetary figures or financial impacts presented in the recommendations are estimates based on specific assumptions.

## Skills Demonstrated

Data Cleaning · Exploratory Data Analysis · Data Visualization (Matplotlib, Seaborn) · Data Storytelling · HR Analytics · Business Recommendations

## Author

**[Your Name]**
[LinkedIn](https://www.linkedin.com/in/username) · [Email](mailto:email@example.com)

## Data Source

IBM HR Analytics Employee Attrition & Performance Dataset.
