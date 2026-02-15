# 📊 Telecom Customer Churn Analysis
**Customer Churn Analysis using SQL, Python, and Tableau**

## 📌 Project Overview
This project analyzes customer churn patterns in a telecom company using **SQL, Python, and Tableau**.  
The objective is to identify key churn drivers, quantify business impact, and build predictive models to proactively identify at-risk customers and improve retention strategies.

> ⚠️ **Disclaimer**  
> All datasets and reports used in this project are fictional and created solely to demonstrate proficiency in data analysis tools. They do not represent any real company, institution, or country.

---

## 🎯 Objectives
- Understand customer churn drivers and behavioral patterns  
- Build KPIs and dashboards to track churn metrics  
- Develop predictive models to identify high-risk customers  

---

## 🛠 Tools & Technologies
- **SQL (MySQL)** – Data extraction, cleaning, aggregation, and analysis  
- **Python** – Exploratory data analysis, statistical insights, predictive modeling  
- **Tableau** – Interactive dashboards and KPI visualization  

---

## 🧠 Skills & Concepts Demonstrated
- Data Cleaning & Validation  
- Exploratory Data Analysis (EDA)  
- Descriptive & Correlation Analysis  
- Customer Segmentation  
- Churn Analysis  
- Logistic Regression Modeling  
- Data Visualization & Storytelling  

---

## 🗄 SQL Analysis

### Workflow

#### 1. Database Setup
- Database: `TelecomChurn`  
- Table: `telecom_customer`  
- Schema validation using `DESCRIBE`

#### 2. Data Exploration
- Verified row counts and null values  
- Analyzed churn distribution  
- Explored categorical variables such as Gender, Contract, and Payment Method  

#### 3. Data Cleaning
- Standardized `Churn` column (`1 = Yes`, `0 = No`)  
- Validated `MonthlyCharges` and `TotalCharges`  
- Removed inconsistencies and invalid records  

#### 4. Descriptive Analytics
Calculated summary statistics (min, max, average, standard deviation) for:
- SeniorCitizen  
- Tenure  
- MonthlyCharges  
- TotalCharges  

#### 5. Correlation Analysis
- Pearson correlation between `MonthlyCharges` and `TotalCharges`

#### 6. Churn Analysis
- Churn by tenure, contract type, senior citizen status, and partner status  

---

### 📌 SQL Key Insights
- Higher churn among customers with **shorter tenure**  
- **Senior citizens** show a higher churn tendency  
- **Month-to-month contracts** have the highest churn rate  
- Moderate to strong positive correlation between monthly and total charges  

#### Sample SQL Query
```sql
SELECT
 (COUNT(*) * SUM(MonthlyCharges * TotalCharges) - 
  SUM(MonthlyCharges) * SUM(TotalCharges)) /
 (SQRT(COUNT(*) * SUM(POW(MonthlyCharges, 2)) - POW(SUM(MonthlyCharges), 2)) *
  SQRT(COUNT(*) * SUM(POW(TotalCharges, 2)) - POW(SUM(TotalCharges), 2)))
 AS Correlation
FROM telecom_customer;
View The Complete SQL Code Here: (MySQL Telocomm Project Analysis.sql)

The correlation between MonthlyCharges and TotalCharges is 0.6511, indicating a moderate to strong positive relationship. As MonthlyCharges increase, TotalCharges also tend to rise proportionally, It means that customers who pay higher monthly charges are likely to have higher total charges over time. This suggests a direct link between how much a customer is billed each month and their overall spending with the company.
🐍 Python Analysis
Exploratory Data Analysis (EDA)

Churn Rate: 26.54%

Strong correlations identified between:

Tenure & TotalCharges (0.83)

MonthlyCharges & TotalCharges (0.65)

Statistical Insights

Senior citizens are more likely to churn

Customers with dependents or partners churn less

Fiber optic users show higher churn rates

Add-on services (online security, tech support) reduce churn
| Model                        | Accuracy | Churn Recall |
| ---------------------------- | -------- | ------------ |
| Logistic Regression          | 81.9%    | 58%          |
| Balanced Logistic Regression | 74.5%    | **83%**      |
✔ Improved churn detection makes the model more actionable for retention strategies.

📓 Full Python Notebook:
https://github.com/Michael-Otebola/Teleco-Churn-Analysis

📊 Tableau Visualizations

🔗 Interactive Dashboard:
https://public.tableau.com/views/TelecomCustomerChurn_17326272284860

Key KPIs

Churn Rate

Total Churned Customers

Average Tenure of Churned Customers

Total Revenue

Revenue Lost Due to Churn

Key Dashboard Insights

Month-to-month contracts dominate churn

Fiber optic service users churn more frequently

Electronic check payment method shows higher churn

💡 Insights & Recommendations
Business Insights

Pricing sensitivity contributes significantly to churn

Contract flexibility increases churn risk

Service quality impacts customer loyalty

Recommendations

Incentivize long-term contracts with discounts or benefits

Bundle services to improve customer value perception

Improve fiber optic service experience

Encourage automatic payment methods

🚀 Future Work

Advanced models (Random Forest, Gradient Boosting)

Real-time churn prediction integration with CRM systems

Customer segmentation and CLV analysis

Sentiment analysis using customer feedback

Automated data pipelines for scalability

👤 Author

Botchu Karthik
Data Analyst | SQL | Python | Tableau

📩 Open to collaboration and feedback

🏁 Conclusion

This project demonstrates a full end-to-end churn analysis workflow using SQL, Python, and Tableau.
By addressing pricing, contracts, and service quality, businesses can significantly reduce churn and improve customer retention through data-driven decision-making.

Happy Analyzing! 🚀
