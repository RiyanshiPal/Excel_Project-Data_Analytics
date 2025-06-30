
# 📊 Excel Salary Dashboard – Data Science Jobs in India

## 👋 Introduction

As someone starting out in the data field, I found the job market to be both exciting and overwhelming. With so many titles, salary ranges, and required skills, I wanted to build something that would make sense of it all—for myself and others at a similar stage.

Inspired by [Luke Barousse’s Excel for Data Analytics course](https://www.lukebarousse.com), I followed his guidance to build a powerful and customizable salary dashboard. But I also added my own perspective as a beginner and tailored it specifically for **aspiring data professionals in India**.

### Questions to Analyze

To understand the data science job market, I asked the following:

1. **Do more skills get you better pay?**
2. **What’s the salary for data jobs in different regions?**
3. **What are the top skills of data professionals?**
4. **What’s the pay for the top 10 skills?**

### Excel Skills Used

The following Excel skills were utilized for analysis:

- **Pivot Tables**
- **Pivot Charts**
- **DAX (Data Analysis Expressions)**
- **Power Query**
- **Power Pivot**

### Data Jobs Dataset

The dataset used for this project contains real-world data science job information from 2023. The dataset is available via my Excel course, which provides a foundation for analyzing data using Excel. 

It includes detailed information on:

- **Job titles**
- **Salaries**
- **Locations**
- **Skills**

## 1️⃣ Do more skills get you better pay?

###  Skill: Power Query (ETL)

#### 📥 Extract

- I first used Power Query to extract the original data (`data_salary_all.xlsx`) and create two queries:
    -  First one with all the data jobs information.
    -  The second listing the skills for each job ID.

#### 🔄 Transform

- Then, I transformed each query by changing column types, removing unnecessary columns, cleaning text to eliminate specific words, and trimming excess whitespace.
    
        
#### 🔗 Load

- Finally, I loaded both transformed queries into the workbook, setting the foundation for my subsequent analysis.
    
      

### 📊 Analysis

#### Insights

-  There is a positive correlation between the number of skills requested in job postings and the median salary, particularly in roles like Senior Data Engineer and Data Scientist.
-  Roles that require fewer skills, like Business Analyst, tend to offer lower salaries, suggesting that more specialized skill sets command higher market value.

    ![2_Project_Analysis_Chart1.png](/data/Resourses/2_Project_Analysis_Chart1.png)


- This trend emphasizes the value of acquiring multiple relevant skills, particularly for individuals aiming for higher-paying roles.

## 2️⃣ What’s the salary for data jobs in different regions?

### 🧮 Skills: PivotTables & DAX

#### Pivot Table

-  I created a PivotTable using the Data Model I created with Power Pivot.
-  I moved the `job_title_short` to the rows area and `salary_year_avg` into the values area.
-  Then I added new measure to calculate the median salary for United States jobs.
    ```
    =CALCULATE(
        MEDIAN(data_jobs_all[salary_year_avg]),
        data_jobs_all[job_country] = "United States")
    ```

#### 🧮 DAX

- To calculate the median year salary I used DAX.

    ```
    Median Salary := MEDIAN(data_jobs_all[salary_year_avg])
    ```

### 📊 Analysis

#### Insights

-  Job roles like Senior Data Engineer and Data Scientist command higher median salaries both in the US and internationally, showcasing the global demand for high-level data expertise.
-  The salary disparity between US and Non-US roles is particularly notable in high-tech jobs, which might be influenced by the concentration of tech industries in the US.

    ![2_Project_Analysis_Chart2.png](/data/Resourses/2_Project_Analysis_Chart2.png)


- These salary insights are important for planning and salary negotiations, helping professionals and companies align their offers with market standards while considering geographical variations.

## 3️⃣ What are the top skills of data professionals?

### Skill: Power Pivot

#### Power Pivot

-  I created a data model by integrating the `data_jobs_all` and `data_jobs_skills` tables into one model.
-  Since I had already cleaned the data using Power Query; Power Pivot created a relationship between these two tables.


#### 📃 Power Pivot Menu

- The Power Pivot menu was used to refine my data model and makes it easy to create measures.


### Analysis

#### Insights

- 💻 SQL and Python dominate as top skills in data-related jobs, reflecting their foundational role in data processing and analysis.
- ☁️ Emerging technologies like AWS and Azure also show significant presence, underlining the industry's shift towards cloud services and big data technologies.

    ![2_Project_Analysis_Chart3.png](/data/Resourses/2_Project_Analysis_Chart3.png)


- Understanding prevalent skills in the industry not only helps professionals stay competitive but also guides training and educational programs to focus on the most impactful technologies.

## 4️⃣ What’s the pay of the top 10 skills?

### Skill: Advanced Charts (Pivot Chart)

#### PivotChart

- I created a combo PivotChart to plot median salary and skill likelihood (%) from my PivotTable.
    -  **Primary Axis:** Median Salary (as a Clustered Column)
    -  **Secondary Axis:** Skill Likelihood (as a Line with Markers)
- To customize the chart, I added a title axis title, removed the lines (skill likelihood), and changed the markers to diamonds.

### 📊 Analysis

#### Insights

-  Higher median salaries are associated with skills like Python, Oracle, and SQL, suggesting their critical role in high-paying tech jobs.
-  Skills like PowerPoint and Word have the lowest median salaries and likelihood, indicating less specialization and demand in high-salary sectors.

    ![2_Project_Analysis_Chart4.png](/data/Resourses/2_Project_Analysis_Chart4.png)


- This chart highlights the importance of investing time in learning high-value skills like Python and SQL, which are evidently tied to higher paying roles, especially for those looking to maximize their salary in the tech industry.

## Conclusion

Even though I closely followed Luke's course, I learned how to think like a **data analyst**—asking better questions, experimenting with formulas, and building something useful for others.

---

## 💬 Final Thought

> _“The job market is vast, but with the right tools and understanding, it becomes navigable.”_

This project gave me those tools, and I hope it helps others on the same path.
