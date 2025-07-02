# 📅 Day 2 Log

🕒 Time Spent: 3.5 hours  
🎯 Focus: Power BI basics + Initial Data Exploration (Python + Pandas)

---

## ✅ What I Did
Power BI:
- Watched Power BI beginner tutorials
- Installed and explored Power BI Desktop
- Loaded “Data Science Salaries 2023” dataset
- Built my first bar chart: Job Count by Country
- Added slicer for experience level
- Saved and documented the dashboard
Pandas:
- Loaded the dataset into a Pandas DataFrame
- Used `df.head()`, `df.tail()`, and `df.columns` to understand the structure
- Viewed the first and last few rows of data
- Identified all column names and verified their types
- Inspected salary values, job titles, work years, and locations

---
### 🔍 Key Observations:
- The dataset has **3,755 rows and 11 columns**
- Common job titles include: `Data Scientist`, `ML Engineer`, and `Principal Data Scientist`
- Most job roles are from **2023**, but data ranges back to **2020**
- Salary is stored in both **local currency** and **USD** — this makes `salary_in_usd` the most reliable for comparison
- **Remote work ratio** is mostly `100`, suggesting most roles are fully remote
- Company locations include `US`, `CA`, `IN`, and `ES` — indicating a global dataset
- **Employment types** include `FT` (Full-Time), `CT` (Contract), etc.

---

## 📈 Screenshot saved to:
📁 `Global_Job_Trends_Data_Project/visuals/day2_job_by_country.png`

---

## 🧠 What I Learned
Power BI:
- The Power BI interface is very user-friendly
- You can analyze job trends visually without writing code
- Slicers make dashboards interactive and user-driven
Pandas:
- It's important to first understand the dataset structure before jumping to visuals
- Pandas is very effective for quick data inspection and helps spot potential cleaning tasks
- I now have a good foundation to clean and filter this data for visual analysis in Power BI and deeper insights in Python

