# 👥 HR Employee Attrition Analysis (Excel)

> **Attrition is concentrated in overtime, young and low-paid employees. Who leaves, and what can a company do about it?**

An end-to-end Excel analysis of 1,470 IBM employees: data checks, helper columns, pivot tables, slicers and an interactive dashboard that shows who is most likely to leave and why.

![Dashboard](dashboard.png)

---

## 🎯 Business questions

1. How many employees leave, and what is the overall attrition rate?
2. Does working overtime change the chance of leaving?
3. Which age groups and tenure bands are the most at risk?
4. Is low pay linked to higher attrition?
5. Which job roles and travel patterns see the most exits?

## 📦 Dataset

| | |
|---|---|
| Source | [IBM HR Analytics Employee Attrition & Performance](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset) on Kaggle |
| Size | 1,470 rows, 35 columns (one row per employee) |
| Coverage | A fictional dataset created by IBM data scientists |
| After preparation | 1,470 employees: 237 left and 1,233 stayed, with 4 helper columns added |

> The raw dataset is not re-uploaded here. Please download it from the source above.

## 🧹 Data preparation

Every step is recorded in the **Cleaning Log** sheet of the workbook.

| Step | What I did | Result |
|---|---|---|
| 1 | Reviewed size and structure | 1,470 employees, 35 columns |
| 2 | Searched every column for blank cells | No missing data, so nothing needed filling |
| 3 | Checked for duplicate rows, comparing every column except `EmployeeNumber` | 0 duplicates removed |
| 4 | Checked that every employee ID is unique | 0 duplicate IDs |
| 5 | Hid 3 constant columns (`EmployeeCount`, `Over18`, `StandardHours`) | They hold one value for every row, so they carry no information |
| 6 | Created `Attrited` (1 if the employee left, otherwise 0) | The average of `Attrited` is the attrition rate: 16.1% |
| 7 | Grouped age, tenure and income into bands | Easy to compare attrition across groups |
| 8 | Kept satisfaction and rating columns as coded 1 to 4 scales | Not used in the dashboard |
| 9 | Converted the range to an Excel Table, `tblHR` | One source for every pivot and slicer |

**Added columns:** `Attrited`, `Age Group` (18-24, 25-34, 35-44, 45+), `Tenure Band` (0-2, 3-5, 6-10, 11+ years) and `Income Band` (Under 3K, 3K-6K, 6K-10K, 10K+ per month).

## 📊 Headline numbers

| Total employees | Employees who left | Attrition rate | Average income (left) | Average income (stayed) |
|---|---|---|---|---|
| 1,470 | 237 | **16.1%** | $4,787 | $6,833 |

## 🔑 Key findings

| # | Finding | Evidence |
|---|---|---|
| 1 | **Overtime nearly triples the chance of leaving.** | 30.5% attrition with overtime vs 10.4% without; 127 of 237 leavers (54%) worked overtime |
| 2 | **The youngest employees are the most likely to leave.** | 18-24 year-olds leave at 39.2%; employees aged 34 or under make up 150 of 237 leavers (63%) |
| 3 | **The first two years are the danger zone.** | 29.8% of employees with 0-2 years of service leave, falling to 8.1% after 11 years |
| 4 | **Low pay drives exits.** | Under $3K earners leave at 28.6% vs 8.9% for $10K+; 113 of 237 leavers (48%) earned under $3K |
| 5 | **Sales Representatives leave at 4 in 10.** | 39.8% (33 of 83), then Laboratory Technicians (23.9%) and HR (23.1%) |
| 6 | **Frequent travel triples attrition.** | 24.9% for frequent travellers vs 8.0% for non-travellers |
| 7 | **Single employees leave twice as often as married ones.** | 25.5% for single vs 12.5% for married |

## 💡 Recommendation

**Reduce overtime and strengthen pay and onboarding for early-career and sales staff, the groups where exits are concentrated.**

## ⚠️ Limitations

- The dataset is **fictional** and a **snapshot**. It has no exit dates or reasons for leaving, so the attrition rate is the share of employees who left, not a yearly rate.
- The findings show **association, not cause**. Overtime, age, tenure and pay overlap (for example, younger staff are often newer and paid less), so each effect is not independent of the others.
- Some groups are small: 83 Sales Representatives, 97 employees aged 18-24. Their rates can move a lot with a few exits.
- The job role chart shows the **top 5 of 9 roles** only.
- The KPI tiles and insights show **all employees** and do not change with the slicers. The charts do.

## 🛠️ What's inside the workbook

| Sheet | Purpose |
|---|---|
| `Dashboard` | Interactive dashboard: 3 slicers, 5 KPI tiles, 6 charts, key insights |
| `Calc` | Formulas that power the KPI tiles |
| `Data` | Cleaned dataset (Excel Table `tblHR`) |
| `Cleaning_Log` | Record of every cleaning step |
| `Pivot_OverTime`, `Pivot_Age`, `Pivot_Tenure`, `Pivot_Income`, `Pivot_Role`, `Pivot_Travel` | Pivot tables, charts and insights behind the dashboard |

**Excel skills used:** Tables, PivotTables and PivotCharts, Slicers with Report Connections, IF, IFS, Go To Special, Remove Duplicates, Conditional Formatting, navigation buttons, dashboard design.

## ▶️ How to use

1. Download `HR_Attrition_Analysis.xlsx`
2. Open the `Dashboard` sheet
3. Click the **Department**, **Gender** and **Marital Status** slicers to filter the charts
4. Use the funnel icon with the **X** on a slicer to clear a filter
5. Use the sidebar buttons to jump to each analysis sheet, and **Back to Dashboard** to return

## 👩‍💻 Author

**Imanathul Reyyan**: BSc Applied Data Analytics, University of Colombo
🔗 [LinkedIn](https://www.linkedin.com/in/imanathul-reyyan) · 🌐 [Portfolio](https://imanathulreyyan.github.io) · ✉️ imanareyyan@gmail.com

*Project 4 in my data analytics portfolio (Excel, then SQL and Power BI).*
