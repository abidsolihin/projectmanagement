# 📊 Project Management Dashboard | Power BI

A comprehensive and interactive dashboard that visualizes key metrics from a project management dataset. This dashboard helps stakeholders monitor project statuses, task completion, durations, and overall performance.

---

## 📁 Dataset

- **Source**: [Kaggle - Project Management Dataset by Derrick Kuria](https://www.kaggle.com/datasets/derrickkuria/project-management-dataset)
- **File**: `project Management.xlsx`
- **Fields**: Project ID, Project Name, Entry Date, Completion Date, Duration, Status, Priority, Assigned Team, and more.

---

## 🛠️ Tools Used

- **Power BI Desktop**
- Power Query for data transformation
- DAX (Data Analysis Expressions) for calculated measures

---

## 📐 Data Cleaning & Transformation

Performed using Power Query:

- Converted `EntryDate` and `CompleteDate` to proper Date types
- Handled missing values (especially in `CompleteDate`)
- Calculated `Duration` where necessary
- Ensured consistency in `IsCompleted` status (e.g., "Completed", "Ongoing")

---

## 📈 Dashboard Features

### 🧮 KPI Cards

- **Total Projects**  
  `= DISTINCTCOUNT(data[Project ID])`
  
- **Completed Tasks**  
  `= CALCULATE(COUNTROWS(data), data[IsCompleted] = "Completed")`

- **Ongoing Tasks**  
  `= CALCULATE(COUNTROWS(data), data[IsCompleted] = "Ongoing")`

- **Average Duration (Completed Only)**  
  `= AVERAGEX(FILTER(data, data[IsCompleted] = "Completed"), data[Duration])`

- **Completion Rate (%)**  
  `= DIVIDE(CALCULATE(COUNTROWS(data), data[IsCompleted] = "Completed"), COUNTROWS(data), 0)`

---

### 📊 Visualizations

- Project Status Breakdown (Bar / Donut Chart)
- Task Progress Over Time (Line Chart)
- Average Duration by Team / Priority
- Completed vs Ongoing Trend (Stacked Area Chart)
- Filters by Team, Priority, Date Range

---

## 🧠 Insights

- Identify bottlenecks in project completion
- Monitor overdue or long-duration projects
- Understand team workload and efficiency
- Track how task duration varies by priority level

---

## 📂 File Structure

```plaintext
📁 Project-Management-Dashboard
├── project Management.xlsx      # Raw data
├── projectmanagement.pbix       # Power BI dashboard
└── README.md                    # Documentation
🚀 How to Use
Download the .pbix file

Open with Power BI Desktop

Explore, customize, and interact with the visuals

📌 Author
A'bid Solihin
Data Analyst | Power BI Enthusiast
📧 abidsolihin1@gmail.com
🔗 https://www.linkedin.com/in/abidsolihin/
