# 📊 Employee Attrition Analytics

An exploratory data analysis (EDA) project that investigates **why employees leave an organization**, using HR data on 1,480 employees. The analysis cleans the data, handles missing values and outliers, and visualizes attrition across demographics, pay, tenure, and departments.

**Author:** Borath Shiva Kumar · [GitHub](https://github.com/Shiva2202)

---

## 🎯 Objectives

- Clean and prepare the HR dataset for analysis
- Measure the overall attrition rate
- Identify which employee segments (gender, age group, salary band, department, education field, tenure) are most affected by attrition
- Present findings through clear visualizations

## 🗂️ Repository Structure

```
├── Attrition_Analytics.ipynb   # Full analysis notebook
├── Attrition_Analytics.csv     # Dataset (1,480 rows × 38 columns)
└── README.md
```

## 📁 Dataset

| Property | Value |
|---|---|
| Rows | 1,480 employees |
| Columns | 38 |
| Target | `Attrition` (Yes / No) |
| Missing values | 57, all in `YearsWithCurrManager` |

Features cover demographics (`Age`, `AgeGroup`, `Gender`, `MaritalStatus`), job details (`Department`, `JobRole`, `JobLevel`, `OverTime`, `BusinessTravel`), compensation (`MonthlyIncome`, `SalarySlab`, `PercentSalaryHike`, `StockOptionLevel`), satisfaction scores (`JobSatisfaction`, `EnvironmentSatisfaction`, `WorkLifeBalance`, etc.), and tenure (`YearsAtCompany`, `YearsInCurrentRole`, `YearsSinceLastPromotion`).

## 🛠️ Tech Stack

- **Python 3**
- **pandas**, **NumPy**: data manipulation
- **Matplotlib**, **Seaborn**: visualization
- **Jupyter / Google Colab**: environment

## 🔄 Workflow

1. **Load & inspect:** shape, `head`/`tail`, `info`, `describe`
2. **Data cleaning:** missing `YearsWithCurrManager` values imputed with the column mean
3. **Feature selection:** 10 key columns retained (`EmpID`, `Age`, `AgeGroup`, `Attrition`, `Department`, `Gender`, `EducationField`, `SalarySlab`, `YearsAtCompany`, `MonthlyIncome`)
4. **Feature engineering:** binary `Attrition Count` column (1 = left, 0 = stayed)
5. **Outlier treatment:** IQR method (1.5 × IQR) with capping on `YearsAtCompany` and `MonthlyIncome`
6. **Deduplication:** 10 duplicate rows removed → **1,470 rows** in the final dataset
7. **Visualization & insights**

## 🔍 Key Findings

**Overall attrition: 237 of 1,470 employees left, about 16.1%.**

| Dimension | Observation |
|---|---|
| **Gender** | More men left in absolute numbers (150 vs 87) |
| **Age group** | The 26–35 group has the most leavers (116); employees 55+ have the fewest |
| **Salary slab** | Employees earning **under 5k** account for the most attrition (163); the **15k+** band has the least (5) |
| **Department** | Research & Development has the highest attrition count (133); HR has the lowest (12) |
| **Education field** | Life Sciences has the most leavers (89) |
| **Tenure** | Attrition is concentrated among employees with under ~2.5 years at the company |

> 💡 **Note on rates:** The charts show raw counts, which partly reflect group size. Looking at attrition *rates* adds nuance: Sales has the highest rate (≈20.6%) versus R&D (≈13.8%); the 18–25 age group leaves at ≈36%; and the under-5k salary band at ≈22% versus ≈4% for 15k+. Converting the plots to rates is a natural next step.

## ▶️ How to Run

```bash
# 1. Clone the repository
git clone https://github.com/Shiva2202/<your-repo-name>.git
cd <your-repo-name>

# 2. Install dependencies
pip install pandas numpy matplotlib seaborn jupyter

# 3. Launch the notebook
jupyter notebook Attrition_Analytics.ipynb
```

> The notebook loads the data from `/content/Attrition_Analytics.csv` (Google Colab path). If running locally, change `file_path` to `'Attrition_Analytics.csv'`.

## 🚀 Future Improvements

- Plot attrition **rates** instead of raw counts
- Analyze the remaining features (OverTime, JobSatisfaction, WorkLifeBalance, YearsSinceLastPromotion)
- Add a correlation heatmap
- Build a predictive model (Logistic Regression, Random Forest) to flag employees at risk of leaving
- Create an interactive dashboard (Power BI / Tableau / Streamlit)

## 📬 Contact

**Borath Shiva Kumar**
GitHub: [@Shiva2202](https://github.com/Shiva2202)

---

⭐ If you found this project useful, consider giving it a star!
