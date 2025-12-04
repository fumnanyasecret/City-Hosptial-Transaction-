# City Hospital
City Hospital is a well-respected institution in its community. However, the leadership team recognised a growing need to leverage data for better decsion-making.  
Traditionally, financial and operational decisions were made based on intuition and historical trends, which left room for inefficiences and missed oppurtunities.  

# 🏪 City Hospital: Data-driven decisions on finance and operations.  
### *Exploratory Data Analysis using Power BI*   

---

## 🧭 PROBLEM STATEMENT   
City Hospital is a **well-respected institution in the community** that lacks centralized view of their financial perfomance.  
This made it difficult to identify trends, optimize resource allocation, and make data-driven decisions.  
This project applies **Power Query** and **Power BI visualisation** to reveal:  

## Dashboard 1
-  What is the trend of revenue generation over the given time period 💰  
-  Which Specialties yielded thehighest and lowest revenue 💸  
-  How much revenue does each procedure category make in hospital  👑  
-  What is the total revenue, expenses and profit margin and how many transaction was this achieved 📉

  ## Dashboard 2
  - Who are the top revenue generating doctor in the hospital
  - Who are the top 5 Patients that impacted on Revenue generation
  - How many doctors are in each specialty and how many patients patronize each of these specialities
  - What is the trend of patients visits to the hospital over time
  - By gender description ive the total No.Doctors and patients in the hospital.
    
By merging data cleaning,Power query, Data modelling and dashboard storytelling, this project transforms raw data into a roadmap for smarter growth and retention.  

---

## 🎯 Steps to take 
1. **Data cleaning and integration** : This process involves identifying and correcting inconsistencies, missing/null values, and duplicates within the data set. 
2. **Data Modelling**: This will establish a logical structure for the hospital's data. The model defined the relationships between different data points, allowing for efficient querying and analysis.   
3. **DAX Calculations and Dashboard Building**: DAX calculations were created to Analyze key performance indicator (KPIs). The dashboard will provide real insights into the hospital's perfomance. 
4. **Insights and Recommendations** : After analyzing the data, you will identify several key insights that will help you generate data-driven recommendations.

---

## 🗂️ Data Description  

| Table | Description |
|--------|--------------|
| `Doctor's Dimension` |Doctor's ID and demographics |
| `Patient's Dimension` | Patient's ID and demographics |
| `Procedure's Dimension` | Procedure ID, name, category and description |
| `Location's Dimension` |Location ID,country, city, state and zip code |
| `Date` |month, day, and year|

| Table | Description |
|--------|--------------|
| `Calculated Measures` |Transaction ID, Revenue and Expenses |

📄 *Raw data sourced from EXcel file was imported into Power query for analysis and  modelling first, before visualization*   

---


## ⚙️ KPIs

1. **Total Revenue** – =SUM(revenue amount) 
2. **Total Expenses** – =SUM(expenses amount) 
3. **Total Profit** – =(Total Revenue - Total Expenses Amount) 
4. **Profit Margin** – 
5. **How many Doctors and patients does the hospital have on record** – Summarized findings for decision-making  

---

