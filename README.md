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
  - By gender description give the total No.Doctors and patients in the hospital.
    
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
| `Calendar Dimesion` |month, day, and year|

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
## Data Cleaning  
<img width="1208" height="378" alt="image" src="https://github.com/user-attachments/assets/37a0884d-7d97-419f-b004-bce27d1774d5" />  
*PS: Please note that this is just a portion of the data table imported from excel*

## Creation of Dimension tables 
**Doctor's Dimension** - with Doctor's ID as the unique identifier  
<img width="626" height="322" alt="image" src="https://github.com/user-attachments/assets/618c31dc-94bf-4327-8f00-bf27ca1c1b01" />  
*PS: Null values and duplicates were removed from the Primary key* 

**Patient's Dimension** - with Patient's ID as the unique identifier  
<img width="631" height="288" alt="image" src="https://github.com/user-attachments/assets/8f64ef08-7c7d-4d15-90b1-285870cfb217" />  
*PS: Null values and duplicates were removed from the Primary key*  

 **Procedure Dimension** - with Procedure ID as the unique identifier  
 <img width="637" height="274" alt="image" src="https://github.com/user-attachments/assets/e8256fd5-26d3-4e3d-ae19-7f57bf171279" />  
 *PS: Null values and duplicates were removed from the Primary Key*  

 **Location Dimension** - with Location ID as the unique identifier  
 <img width="628" height="279" alt="image" src="https://github.com/user-attachments/assets/31f19836-4ad5-4f8d-86e7-a3aa01d5e62b" />  
 *PS: Null values and duplicates were removed from the Primary Key*  
 
 **Calendar Dimension**  
 <img width="635" height="275" alt="image" src="https://github.com/user-attachments/assets/5f3d0ddb-ad11-40c9-a63e-b14f36485e69" />    
 *PS: The calendar dimesion was created using dax formula and taking note*    
 - Start date: first date of the data set   
 - End date: Last date in the data set    
 - Date format: Date format accoring to the country region of the data collected  

 Here is an  example of Null values in power query
<img width="740" height="193" alt="image" src="https://github.com/user-attachments/assets/ee21f911-2e92-40b6-9028-c63a10b5e77a" />

## Data modelling - Using Schemas model to connect all the Primary Keys in the various dimesion table to the Fact sheet to exist as Foreign keys 
<img width="440" height="255" alt="image" src="https://github.com/user-attachments/assets/e66e12f2-c42c-48cf-aa75-429f7bb267aa" />  

## DAX Calculation for Measures
*Total Revenue*  
<img width="624" height="277" alt="image" src="https://github.com/user-attachments/assets/320c66d2-9b49-49e6-a6f6-e82a091b0784" />  

*TotalExpenses*  
<img width="638" height="272" alt="image" src="https://github.com/user-attachments/assets/8511e225-e372-4e02-bb3c-b579b9c95ba6" />  

*Total Profit*  
<img width="630" height="277" alt="image" src="https://github.com/user-attachments/assets/3df15bc5-de0d-484d-afc6-bc2a25339a9c" />  

## Dashboard 1  
<img width="618" height="396" alt="image" src="https://github.com/user-attachments/assets/b4ebbf51-03cf-4aa5-b6f6-4a121e169f0c" />  

## Dashboard 2  
<img width="610" height="395" alt="image" src="https://github.com/user-attachments/assets/d17f2ab1-c112-4dc1-8a6b-23e2a2abae8e" />  

---
### Trends & Insights of Dashboard 1
1️⃣ Revenue peaked in 2022 ($44k), dipped in 2023 ($9k)
2️⃣ Specialty:Dermatologist yielded highest revenue ($68K), Peadiatricians yielded lowest ($24K)
3️⃣ Total Revenue:$274k
4️⃣ Total Expenses:$189k
5️⃣ Profit Margin: 30.8%
6️⃣ Revenue generated by each procedure revenue  
<img width="214" height="148" alt="image" src="https://github.com/user-attachments/assets/3e72f749-d775-4505-924c-05f6179dd945" />  


### Trends and Insights of Dashboard 2
1️⃣ Top 5 Revenue Doctors - Ava Adams ($25K), Liam Turner ($20K), Benjamin ($16K), Emma ($13k), Williams ($12K) 
2️⃣ Top 5 Patients - Harper ($17K), Ethan ($15K), Mia wills ($13K), Mia Ada ($12k), Olivia ($12k)
3️⃣ Nos of doctors in each specialty and number of patients patronize each of these specialities  
<img width="309" height="159" alt="image" src="https://github.com/user-attachments/assets/7852d350-27cf-4aa4-bc4a-781b3f30c8c7" />  
4️⃣ Trend of patients visits to the hospital over time  
<img width="450" height="199" alt="image" src="https://github.com/user-attachments/assets/1e848cf3-2cda-4502-89ef-01aaea2c064d" />  
5️⃣  By gender description the total No.Doctors and patients in the hospital  
<img width="252" height="218" alt="image" src="https://github.com/user-attachments/assets/e0150fb3-01ac-4081-929d-aef196a27acc" /> 


### 📈 Recommendations  
1️⃣**Expand high-performing Dermatology services** by adding more procedures, equipment, or marketing focus to maximize the specialty generating the highest revenue.
2️⃣**Investigate the sharp revenue drop from 2022 to 2023** to identify causes (reduced patient volume, pricing issues, staffing gaps) and implement corrective actions to restore growth.
3️⃣**Reassess low-performing Pediatrics services**, adjusting pricing, reducing resource allocation, or redesigning offerings to improve contribution or eliminate inefficiencies.
4️⃣**Improve profit margin by reducing operational expenses** (supplies, overhead, scheduling inefficiencies) and introducing higher-value or bundled service packages to lift revenue without major cost increases.



### 🧰 Tools & Technology
Tools used and their purposes
1️⃣ Excel - To effectively format the dataset before converting to CSV and subsequently importing it into PostgreSQL for analysis
2️⃣ Power BI - Dashboard design and KPI visualisation
3️⃣ DAX - Custom measures (example, Discount Impact% and more)


⚠️ Disclaimer

This project is for educational and portfolio demonstration only. Data is simulated and does not represent any real organisation.  

### 🔗 Connect With Me  
Ifunanya R. Uzokwe
📧 Uzokweifunaya10@gmail.com  
🔗 [LinkedIn](https://www.linkedin.com/in/Ifunanya-Uzokwe/)  
💻 [GitHub](https://github.com/fumnanya-secret)     












