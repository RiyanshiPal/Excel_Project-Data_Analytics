# 📊 Excel Salary Dashboard – Data Science Jobs in India

![Dashboard Snapshot]( data/Resourses/1_Salary_Dashboard_Final_Dashboard.gif)

##  Introduction

This project was created by following along with [Luke Barousse’s Excel for Data Analytics course]( https://www.lukebarousse.com). While the dashboard structure and techniques are based on the course, I’ve approached it from a **beginner’s perspective**, trying to understand the often overwhelming **data job market**—filled with a wide range of roles, skills, and salary expectations.

In this project, I took the role of a **curious job seeker** and analyst, aiming to personalize the dashboard for others like me. The dashboard allows users to explore:

- Different **data-related job titles**
- Corresponding **median salaries**
- Required **skills**
- Filters by **country**, **work schedule**, and **job type**

---

## In My Personal Focus: Data Science Roles in India

As someone based in India and exploring data science, I’ve tailored this dashboard to highlight insights **specific to Indian job seekers**:

- Filtered views focused on **data science roles in India**
- Median salary comparisons based on **country and schedule types**
- Usability features like **drop-down filters** to customize the view

---

## 🗂 Dataset Information

The dataset used in this dashboard is sourced from Luke Barousse’s platform [datanerd.tech](https://datanerd.tech/), which aggregates job postings across the globe. It contains **up to 3 million job listings** from 2023 and covers:

-  Job Titles  
-  Salary Averages (in USD)  
-  Country & Location  
-  Work Schedule  
- 🛠 Required Skills  

 **Dataset used in this project**: [Data](Excel_Project-Data_Analytics/data)  
 **Note**: All salaries are provided in USD.

---

##  Key Learnings

Though the dashboard is built step-by-step following the course, I spent time **understanding the ‘why’ behind the how**, and personalized the logic to align with my goals.

### 📊 Charts

- **Bar Chart** for Median Salary by Job Title  
![]( data/Resourses/1_Salary_Dashboard_Chart1.png)
  → Clear visualization of high-paying roles  
  → Sorted for better comparison  

- **Map Chart** for Country-wise Salary  
![]( data/Resourses/1_Salary_Dashboard_Country_Map.gif)
  → Highlights how location affects pay  
  → Helpful for global job seekers

### 🧮 Formulas

```excel
=MEDIAN(
  IF(
    (jobs[job_title_short]=A2)*
    (jobs[job_country]=country)*
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
    (jobs[salary_year_avg]<>0),
    jobs[salary_year_avg]
  )
)
```
Used this array formula to return **custom median salaries** filtered by job title, country, and job type.

💡 *This helped me understand multi-criteria filtering and the power of dynamic tables in Excel.*


### ❎ Data Validation

Implemented dropdowns to ensure clean filtering across:

<img src="data/Resourses/1_Salary_Dashboard_Data_Validation.gif" width="300" height="280" alt="Data Validation GIF">


- **Job Titles**

![]( data/Resourses/1_Salary_Dashboard_Screenshot1.png)  


#### ⏰ Count of Job Schedule Type

```
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
```

- 🔍 **Unique List Generation:** This Excel formula below employs the `FILTER()` function to exclude entries containing "and" or commas, and omit zero values.
- ** Formula Purpose:** This formula populates the table below, which gives us a list of unique job schedule types.

🍽️ Background Table

![1_Salary_Dashboard_Type.png](data/Resourses/1_Salary_Dashboard_Screenshot2.png)

📉 Dashboard Implementation:

<img src="data/Resourses/1_Salary_Dashboard_Type.png" width="350" height="500" alt="Salary Dashboard Type">

### ❎ Data Validation

####  Filtered List

-  **Enhanced Data Validation:** Implementing the filtered list as a data validation rule under the `Job Title`, `Country`, and `Type` option in the Data tab ensures:
    -  User input is restricted to predefined, validated schedule types
    -  Incorrect or inconsistent entries are prevented
    -  Overall usability of the dashboard is enhanced

<img src="data/Resources/1_Salary_Dashboard_Data_Validation.gif" width="425" height="400" alt="Salary Dashboard Data Validation">


### 📌 Use Case

This dashboard can be used by:

- **Students or early-career professionals** exploring data jobs  
- **Anyone comparing salary expectations** across roles or countries  
- **Career services or mentors** guiding candidates in data careers  

It provides a **quick overview of market trends** and simplifies decision-making for job seekers.

---

###  Conclusion

Through this project, I:

- Learned how to **build a structured dashboard** in Excel  
- Understood the **logic behind key formulas and filters**  
- Gained confidence in **data storytelling using visuals**  
- Customized insights for my target audience: **aspiring data professionals in India**

Even though I followed the tutorial closely, I now feel equipped to **create dashboards from scratch** and **analyze job market data independently**.

> 💬 *“The job market is vast, but with the right tools and understanding, it becomes navigable.”*

