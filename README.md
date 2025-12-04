# City-Hosptial-Transaction  
City Hospital leadership team recognised a growing need to leverage data for better decision-making. Traditionally, financial and operational decisions were made based on intuition and historical trends, which left room for inefficiencies and missed opportunities.  
# 🏪City Hospital:Data-driven decisions on finance and Operations  
### *Exploratory Data Analysis using Power BI*

---

## 🧭 PROBLEM STATEMENT 
City Hospital is a **well-respected institution in its community** She lacked a centralized view of their financial performance.  
This made it difficult to identify trends, optimize resource allocation, and make data-driven decisions.  
This project applies **Power Query** and **Power BI visualisation** to reveal:  
- What is trend of revenue generation over the given time? 💰  
- How discounts impact total revenue 💸  
- Which loyalty tiers drive long-term value 👑  
- What customer issues affect satisfaction 📉  
By merging data cleaning, SQL/PostgreSQL analysis, and dashboard storytelling, this project transforms raw data into a roadmap for smarter growth and retention.  

---

## 🎯 Objectives to be uncovered
1. Identify top-performing and underperforming bundles  
2. Analyse customer spending by loyalty tier  
3. Assess payment success and failure trends  
4. Determine total revenue by product category  
5. Explore issue types with the lowest customer ratings  

---

## 🗂️ Data Description  

| Table | Description |
|--------|--------------|
| `customers` | Customer demographics and loyalty details |
| `subscriptions` | Order history: quantity, discount, total value |
| `bundles` | Bundle category, size, and active status |
| `payments` | Payment method, outcome, and status |
| `support_tickets` | Customer complaints, issue types, and ratings |

📄 *Raw data sourced from CSV files was well formatted/normalised and loaded into PostgreSQL for analysis.*

---

## ⚙️ Project Workflow  

1. **Database Restoration** – Imported and normalised CSV data into PostgreSQL  
2. **SQL Exploration** – Wrote analytical queries to extract business KPIs  
3. **Data Integration** – Exported query results into Power BI  
4. **Dashboard Development** – Created KPIs, filters, and data relationships  
5. **Insights & Recommendations** – Summarized findings for decision-making  

---

## 🧩 PostgreSQL Analysis  

### 1️⃣ Top 3 Bundles by Subscription Count
**PostgreSQL Query**
SELECT b.bundle_name, b.category, COUNT(s.subscriptionid) AS subscription_count
FROM subscriptions s
JOIN bundles b ON s.bundle_id = b.bundleid
GROUP BY b.bundle_name, b.category
ORDER BY subscription_count DESC
LIMIT 3;
 
<img width="647" height="262" alt="image" src="https://github.com/user-attachments/assets/aeeba877-4090-400d-b37a-28c41391e20f" />
💡 Insight: Wellness and Essential bundle-categories are dominating the lists of bundle categories, while wellness comes first and second with 2,232 and 2,141 subscription counts, respectively - this shows huge demand in health and lifestyle.

 
### 2️⃣ Average Spend by Loyalty Tier (Successful Payments Only)
**PostgreSQL Query**
SELECT c.loyalty_tier, ROUND(AVG(s.total_value), 2) AS avg_spend
FROM payments p
JOIN subscriptions s ON p.subscription_id = s.subscriptionid
JOIN customers c ON s.customer_id = c.customerid
WHERE p.is_successful = 'TRUE'
GROUP BY c.loyalty_tier
ORDER BY avg_spend DESC;

<img width="665" height="268" alt="image" src="https://github.com/user-attachments/assets/216e6467-d057-4fff-a94a-0c27215b525b" />
💡 Insight: Gold-tier customers have the highest spend per order, with an average spend of 15,288.55, suggesting strong engagement and loyalty potential. Others, such as Platinum and Silver, are coming close.


### 3️⃣ Failed Payments by Method
**PostgreSQL Query**
SELECT payment_method, COUNT(*) AS failed_count
FROM payments
WHERE LOWER(payment_status) = 'failed'
GROUP BY payment_method
ORDER BY failed_count DESC;

<img width="648" height="266" alt="image" src="https://github.com/user-attachments/assets/4233d30f-bba6-42e7-ac6a-6cc18f295974" />
💡 Insight: Card, bank transfer, and wallet are topping the list of payment methods with failed transaction counts of 345, 238 and 145, respectively. Identifying the payment methods with high failure rates helps reduce revenue leakage and improve checkout reliability.


### 4️⃣ Total Revenue by Bundle Category
**PostgreSQL Query**
SELECT b.category, SUM(s.total_value) AS total_revenue
FROM subscriptions s
JOIN bundles b ON s.bundle_id = b.bundleid
JOIN payments p ON p.subscription_id = s.subscriptionid
WHERE b.is_active = TRUE AND p.is_successful = TRUE
GROUP BY b.category
ORDER BY total_revenue DESC;

<img width="638" height="298" alt="image" src="https://github.com/user-attachments/assets/e822c3e1-3426-43fc-a44c-346d84096aef" />
💡 Insight: Wellness and Essentials drive ~80% of NovaMart’s total revenue — prime targets for bundle-categpro expansion and campaign investment.


**PostgreSQL Query**
### 5️⃣ Issue Types with Lowest Ratings
SELECT issue_type, ROUND(AVG(rating), 2) AS avg_rating
FROM support_tickets
GROUP BY issue_type
ORDER BY avg_rating ASC;

<img width="642" height="300" alt="image" src="https://github.com/user-attachments/assets/f1385168-3494-4e8c-8ed4-1d8c15d4029f" />
💡 Insight: Out of the four issue types with the lowest rating, product quality and billing issues have the lowest satisfaction ratings. These are direct opportunities to improve service experience.

---

### Power BI Dashboard
**Main Dashboard**
<img width="1280" height="692" alt="image" src="https://github.com/user-attachments/assets/6fec3318-b061-4b76-915f-73815ab95ec2" />

**Filtered Dashboards**
Filtered according to Gender
<img width="1280" height="691" alt="image" src="https://github.com/user-attachments/assets/a9c8717b-72ad-43f2-9618-b34ddf0c6312" />
Female
<img width="1280" height="691" alt="image" src="https://github.com/user-attachments/assets/cf41cf1b-bbd9-40e9-9ab3-fd3a7597f01d" />
Female

Filtered according to city
<img width="1280" height="694" alt="image" src="https://github.com/user-attachments/assets/a090a41d-cd3a-4dd0-b3dd-410874695760" />
Abuja
<img width="1280" height="689" alt="image" src="https://github.com/user-attachments/assets/cd22a5aa-8e20-4281-88a3-fc15d3538b38" />
Enugu
<img width="1280" height="695" alt="image" src="https://github.com/user-attachments/assets/7a2a4b6d-a55c-4221-98c0-416b8a159641" />
Ibadan
<img width="1280" height="695" alt="image" src="https://github.com/user-attachments/assets/164831c9-f960-4796-94e3-3eec96759b78" />
Port Harcourt

Filtered according to year, quarter and month
<img width="1280" height="690" alt="image" src="https://github.com/user-attachments/assets/2f160d7f-e575-4939-ab7c-6159531714d2" />
<img width="1280" height="696" alt="image" src="https://github.com/user-attachments/assets/9c2c55f8-1a3d-433d-8dcd-08b24abd23d7" />
<img width="1280" height="696" alt="image" src="https://github.com/user-attachments/assets/cda64ec1-d71a-4ebf-971f-f8cc0fa1f6a5" />
<img width="1280" height="688" alt="image" src="https://github.com/user-attachments/assets/8c8a7442-6ca9-4ac9-9a78-9c8d8afce2eb" />


### Dashboard KPIs
Total Revenue: 190.3M
Active Subscriptions: ~15K
Unsuccessful Payments: 728
Discount Impact: 14.35%

### Trends & Insights
1️⃣ Revenue peaked in October (17.4M), dipped in June (12.6M)
2️⃣ Top Bundles: J, I, and H — primarily in Wellness & Essentials
3️⃣ City Leaders: Port Harcourt and Enugu have the most active customers
4️⃣ 2024 vs 2025: 110.4M vs 79.9M (Although YTD decline in 2025)
5️⃣ Lowest Ratings: Product Quality & Billing Issues

### Focus Areas and Key Insights
1️⃣ Revenue Drivers - 80% of revenue from Wellness & Essentials
2️⃣ Customer Spend - Gold-tier customers lead average spend
3️⃣ Payment Performance - 728 failed payments (payment system improvements needed)
4️⃣ Discount Impact - 14% discount — requires optimisation for profitability
5️⃣ Feedback Focus - Product quality and billing issues drive dissatisfaction
6️⃣ Regional Growth - Port Harcourt & Enugu have the strongest engagement


### 📈 Recommendations
1️⃣ Double down with more commitment on Top Categories by investing in Wellness & Essentials product innovation.
2️⃣ Optimise discount strategy by capping at ≤15% for sustainable margins.
3️⃣ Reduce failed payments by auditing payment gateways and retry logic.
4️⃣ Enhance product quality by strengthening supplier and quality control processes.
5️⃣ Reward loyal customers through personalised offers for Gold and Platinum tiers.
6️⃣ Scale regional campaigns by prioritising Port Harcourt & Enugu for local outreach.


### 🧰 Tools & Technology
Tools used and their purposes
1️⃣ CSV Files - Raw data source
2️⃣ Excel - To effectively format the dataset before converting to CSV and subsequently importing it into PostgreSQL for analysis
3️⃣ PostgreSQL - Data exploration and querying
4️⃣ Power BI - Dashboard design and KPI visualisation
5️⃣ DAX - Custom measures (example, Discount Impact% and more)


⚠️ Disclaimer

This project is for educational and portfolio demonstration only. Data is simulated and does not represent any real organisation.

### 🔗 Connect With Me
Sunday A. Adedeji
📧 sundayadedeji001@gmail.com
🔗 [LinkedIn](https://www.linkedin.com/in/sunday-adedeji/)
💻 [GitHub](https://github.com/Sunday-Adedeji) 
📊 [Power BI](https://app.powerbi.com/links/PrBGT_RN4u?ctid=009b81c9-9d54-4181-bd95-cf7f6d431b86&pbi_source=linkShare)



