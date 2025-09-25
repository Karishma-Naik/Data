# Excel Salary Dashboard & Data Job Market Analysis | 2025

## Introduction

This project analyzes **real-world data science job postings from 2023** using **Microsoft Excel**. The goal is to help job seekers explore salary trends, regional differences, and in-demand skills, while providing an **interactive dashboard** for easy visualization.  

This repository demonstrates advanced Excel techniques including **Power Query, Power Pivot, PivotTables, DAX, charts, formulas, and data validation**.

---

## Questions Explored

1. **Do more skills get you better pay?**  
2. **What’s the salary for data jobs in different regions?**  
3. **What are the top skills of data professionals?**  
4. **What’s the pay for the top 10 skills?**  

---

## Excel Skills Used

- **📊 PivotTables** – Summarize and analyze data efficiently  
- **📈 Pivot Charts** – Visualize trends for better insights  
- **🧮 DAX (Data Analysis Expressions)** – Create custom measures like median salary  
- **🔍 Power Query** – Clean, transform, and prepare data  
- **💪 Power Pivot** – Build relationships between tables for advanced analysis  
- **📉 Charts & Formulas** – Bar charts, map charts, array formulas  
- **❎ Data Validation** – Restrict inputs for cleaner dashboards  

---

## Dataset Overview

The dataset contains detailed information about data-related roles:

- 👨‍💼 **Job Titles** – Data Scientist, Data Engineer, Analyst, etc.  
- 💰 **Salaries** – Average yearly salaries (USD)  
- 📍 **Locations** – Country-level job data  
- 🛠️ **Skills** – Technical and business skills required for each role  

---
📁 Download the dataset:[data_jobs_salary_all.xlsx](https://github.com/user-attachments/files/22531875/data_jobs_salary_all.xlsx)

---

## Dashboard Build

### 📉 Charts

#### 📊 Data Science Job Salaries - Bar Chart

<img width="562" height="329" alt="Salary Dashboard Chart1" src="https://github.com/user-attachments/assets/f80ac439-3676-4e94-88ad-702b05d8c7b8" />


- 🛠️ **Excel Features:** Horizontal bar chart with formatted salary values  
- 🎨 **Design Choice:** Sorted by descending median salary for clarity  
- 💡 **Insights:** Senior roles and engineers have higher pay than analysts  

#### 🗺️ Country Median Salaries - Map Chart

<img width="523" height="315" alt="Screenshot 2025-09-25 132623" src="https://github.com/user-attachments/assets/7383c478-db14-4cec-8e1e-d8e37bb5199a" />

- 🛠️ **Excel Features:** Map chart plotting median salaries by country  
- 🎨 **Design Choice:** Color-coded for visual clarity  
- 💡 **Insights:** Highlights global salary disparities  

### 🧮 Formulas and Functions

#### 💰 Median Salary by Job Titles
=MEDIAN(
IF(
    (jobs[job_title_short]=A2)*
    (jobs[job_country]=country)*
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
    (jobs[salary_year_avg]<>0),
    jobs[salary_year_avg]
)
)
I created this dashboard to showcase insights into salary trends across various data-related job titles. Utilizing data from my Excel course, this dashboard allows users to make informed decisions about their career paths. Exploring the functionalities to understand how location and job type influence salaries. 


## 1️⃣ Do More Skills Get You Better Pay?

### 🔍 Skill: Power Query (ETL)

#### 📥 Extract

- Extracted the raw dataset (`data_salary_all.xlsx`)  
- Created two queries:
  - All job postings  
  - Skills listed per job ID  

#### 🔄 Transform

- Cleaned text, removed unnecessary columns, trimmed whitespace  
- Prepared two tables:

#### 🔗 Load

- Loaded transformed tables into Excel for analysis
  
#### 💡 Insights

- 📈 There is a positive correlation between the number of skills requested in job postings and the median salary, particularly in roles like Senior Data Engineer and Data Scientist.
- 💼 Roles that require fewer skills, like Business Analyst, tend to offer lower salaries, suggesting that more specialized skill sets command higher market value.
!<img width="1109" height="434" alt="Screenshot 2025-09-25 130431" src="https://github.com/user-attachments/assets/79f11f63-060f-4d79-b5b8-74cdc505733e" />
#### 🤔 So What

- This trend emphasizes the value of acquiring multiple relevant skills, particularly for individuals aiming for higher-paying roles.
---

## 2️⃣ What’s the salary for data jobs in different regions?

### 🧮 Skills: PivotTables & DAX

- PivotTable created with **Power Pivot** data model  
- Rows: `job_title_short`  
- Values: `salary_year_avg`  

**DAX for Median Salary:**

excel
Median Salary := MEDIAN(data_jobs_all[salary_year_avg])


**US Median Salary DAX:**

US Median Salary := CALCULATE(MEDIAN(data_jobs_all[salary_year_avg]), data_jobs_all[job_country]="United States")

### 📊 Analysis

#### 💡 Insights

- 💼 Job roles like Senior Data Engineer and Data Scientist command higher median salaries both in the US and internationally, showcasing the global demand for high-level data expertise.
- 💰 The salary disparity between US and Non-US roles is particularly notable in high-tech jobs, which might be influenced by the concentration of tech industries in the US.

<img width="1123" height="445" alt="Screenshot 2025-09-25 133626" src="https://github.com/user-attachments/assets/a707b20f-78e2-415e-9859-7d21242661fa" />
#### **🤔 So What**

- These salary insights are important for planning and salary negotiations, helping professionals and companies align their offers with market standards while considering geographical variations.


## 3️⃣ What are the top skills of data professionals?

### 🔧 Skill: Power Pivot

#### 💪 Power Pivot

- 🔗 I created a data model by integrating the `data_jobs_all` and `data_jobs_skills` tables into one model.
- 🧹 Since I had already cleaned the data using Power Query; Power Pivot created a relationship between these two tables.

#### 🔗 Data Model

- I created a relationship between my two tables using the `job_id` column.
#### 📃 Power Pivot Menu

- The Power Pivot menu was used to refine my data model and makes it easy to create measures.

<img width="1826" height="576" alt="Screenshot 2025-09-25 130447" src="https://github.com/user-attachments/assets/76194bdb-2444-4126-81fc-c26e0dd5e80a" />
### 📊Analysis

#### 💡Insights

- 💻 SQL and Python dominate as top skills in data-related jobs, reflecting their foundational role in data processing and analysis.
- ☁️ Emerging technologies like AWS and Azure also show significant presence, underlining the industry's shift towards cloud services and big data technologies.
  
- Understanding prevalent skills in the industry not only helps professionals stay competitive but also guides training and educational programs to focus on the most impactful technologies.



## 4️⃣ What’s the pay of the top 10 skills?

### 📊 Skill: Advanced Charts (Pivot Chart)

#### 📈 PivotChart

- I created a combo PivotChart to plot median salary and skill likelihood (%) from my PivotTable.
    - 🪙 **Primary Axis:** Median Salary (as a Clustered Column)
    - 👍 **Secondary Axis:** Skill Likelihood (as a Line with Markers)
- To customize the chart, I added a title axis title, removed the lines (skill likelihood), and changed the markers to diamonds.

### 📊 Analysis

#### 💡Insights

- 💰 Higher median salaries are associated with skills like Python, Oracle, and SQL, suggesting their critical role in high-paying tech jobs.
- 📉 Skills like PowerPoint and Word have the lowest median salaries and likelihood, indicating less specialization and demand in high-salary sectors.
<img width="1647" height="486" alt="Screenshot 2025-09-25 130509" src="https://github.com/user-attachments/assets/e64cab0c-ef4f-41b6-9520-3d9b56c5f859" />

- This chart highlights the importance of investing time in learning high-value skills like Python and SQL, which are evidently tied to higher paying roles, especially for those looking to maximize their salary in the tech industry.


## Conclusion

As a data enthusiast and former job seeker, I embarked on this Excel-based project to uncover valuable insights about the data science job market. Using a dataset I've curated from real-world job postings, I analyzed job titles, salaries, locations, and essential skills. By leveraging Excel features like Power Query, PivotTables, DAX, and charts, I discovered key correlations between multiple skills and higher salaries, particularly in Python, SQL, and cloud technologies. 

I hope this project serves as a practical guide for data professionals and provides an overview of the skills needed for higher-paying roles.
