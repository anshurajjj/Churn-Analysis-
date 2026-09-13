# 📊 Customer Churn Analysis

## 🔍 Project Overview

Customer churn is one of the most important challenges for subscription-based businesses. Losing existing customers can directly impact recurring revenue, customer lifetime value, and overall business growth.

This project focuses on performing an **end-to-end Customer Churn Analysis** using customer, subscription, and support data stored in a **SQLite database**.

The analysis covers the complete data analytics workflow—from **data extraction and cleaning** to **data transformation, feature engineering, KPI calculation, exploratory data analysis, and visualization**.

The objective is to identify churn patterns, understand customer behavior, evaluate the impact of customer support interactions, and segment customers based on their churn risk.

---

# 🎯 Business Problem

Customer churn can result in significant revenue loss. Businesses need to understand:

- Which customers are more likely to churn?
- Which subscription plans have higher churn rates?
- Does customer support escalation influence churn?
- How much revenue is associated with churned customers?
- Which customer segments should be prioritized for retention?
- Are there geographical patterns in customer churn?

This project uses data analysis techniques to answer these questions and generate insights that can support **data-driven customer retention strategies**.

---

# 🎯 Project Objectives

- Calculate the overall customer churn rate
- Measure the customer retention rate
- Analyze churn across different subscription plans
- Identify churn patterns over time
- Calculate Average Revenue Per User (ARPU)
- Analyze average customer tenure
- Estimate revenue associated with churned customers
- Analyze customer support escalations
- Calculate average complaints per customer
- Examine the relationship between escalations and churn
- Segment customers based on churn risk
- Analyze churn across geographical locations

---

# 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| Python | Data Analysis & Feature Engineering |
| Pandas | Data Manipulation & Transformation |
| NumPy | Numerical Operations |
| SQLite | Data Storage & SQL Queries |
| Matplotlib | Data Visualization |
| Seaborn | Statistical Data Visualization |
| Jupyter Notebook | Analysis & Documentation |

---

# 🗂️ Data Sources

The project uses data stored in a **SQLite database**.

The analysis combines information from three major data areas:

### 👤 Customer Data
- Customer ID
- Customer Name
- Date of Birth
- Gender
- State
- Country

### 💳 Subscription Data
- Customer ID
- Plan Type
- Contract Type
- Subscription Start Date
- Renewal Date
- Cancellation Date
- Monthly Charges
- Churn Score

### 🎧 Customer Support Data
- Customer ID
- Complaint Date
- Escalation Status
- Customer Complaint Frequency

---

# ⚙️ Project Workflow

```text
SQLite Database
       │
       ▼
Data Extraction using SQL
       │
       ▼
Data Cleaning & Transformation
       │
       ▼
Data Integration
       │
       ▼
Feature Engineering
       │
       ▼
KPI Calculation
       │
       ▼
Exploratory Data Analysis
       │
       ▼
Data Visualization
       │
       ▼
Business Insights
```

---

# 🗄️ 1. Data Extraction

Data was extracted from the SQLite database using Python and SQL queries. Database tables were explored and imported into Pandas DataFrames for analysis.

---

# 🧹 2. Data Cleaning & Preparation

Key data preparation steps included:

- Renaming columns for better readability
- Removing irrelevant columns
- Converting date columns to datetime format
- Standardizing inconsistent gender values
- Handling missing country values using state-country relationships
- Cleaning support-related data
- Validating data types and dataset structure

---

# 🔗 3. Data Integration

Customer, subscription, and support datasets were merged using the customer identifier to create a unified customer-level analytical dataset.

A key challenge was handling multiple support records for individual customers. Complaint counts were calculated, support records were sorted by complaint date, and the latest support interaction was retained to avoid duplicate customer records.

---

# ⚡ 4. Feature Engineering

## 🔴 Churn Flag

A binary churn indicator was created based on cancellation status:

| Customer Status | Churn Flag |
|---|---:|
| Active Customer | 0 |
| Churned Customer | 1 |

## ⏳ Customer Tenure

Customer tenure was calculated using the subscription start date and:

- Cancellation date for churned customers
- Current date for active customers

## 🚨 Complaint Count

The total number of complaints associated with each customer was calculated.

## 🔥 Churn Risk Segmentation

Customers were segmented according to churn score:

| Churn Score | Risk Category |
|---|---|
| Below 50 | 🟢 Low Risk |
| 50–69 | 🟡 Medium Risk |
| 70 and Above | 🔴 High Risk |

---

# 📌 5. Key Performance Indicators (KPIs)

## 📉 Customer Churn Rate

Measures the percentage of customers who cancelled their subscription.

**Formula:**

```text
Churn Rate = (Churned Customers / Total Customers) × 100
```

## 🟢 Customer Retention Rate

Measures the percentage of customers who remain active.

```text
Retention Rate = 100 − Churn Rate
```

## 💰 Average Revenue Per User (ARPU)

Measures the average monthly revenue generated per customer.

```text
ARPU = Total Monthly Charges / Total Customers
```

## ⏳ Average Customer Tenure

Measures the average duration customers remain subscribed.

## 💸 Revenue at Risk

Calculates the monthly revenue associated with churned customers.

```text
Revenue at Risk = Sum of Monthly Charges for Churned Customers
```

## 🚨 Escalation Rate

Measures the percentage of customers with escalated support cases.

## 📞 Average Complaints Per User

Measures the average number of complaints raised by customers.

## 🔗 Escalation vs Churn Correlation

Analyzes the relationship between customer support escalations and customer churn.

---

# 📊 6. Exploratory Data Analysis

The project analyzes customer churn from multiple perspectives.

## 📈 Monthly Churn Trend

Analyzes churn patterns over time to identify periods with higher customer cancellations.

## 📊 Churn Rate by Plan Type

Compares churn rates across subscription plans to identify plans with higher customer attrition.

## 🗺️ Churn Analysis by State

Examines geographical differences in customer churn.

## 🔥 Correlation Analysis

Explores relationships between churn and variables such as:

- Plan Type
- Contract Type
- Churn Score
- Churn Flag
- Churn Risk
- Support Escalations

## 👥 Customer Segmentation

Analyzes customers across:

- Subscription plans
- Monthly charges
- Gender
- Churn risk categories

## 📋 Pivot Table Analysis

Creates business summaries using:

- Revenue
- Unique customer count
- Churn rate
- Subscription plans

---

# 📈 7. Visualizations

The project includes:

| Visualization | Purpose |
|---|---|
| 📈 Monthly Churn Trend | Identify churn patterns over time |
| 📊 Churn by Plan Type | Compare churn across subscription plans |
| 🗺️ Churn by State | Identify geographical churn patterns |
| 🔥 Correlation Heatmap | Analyze relationships between variables |
| 🔗 Pairwise Analysis | Explore relationships between multiple variables |
| 👥 Customer Segmentation | Compare customer groups and churn risk |
| 📋 Pivot Tables | Summarize revenue, customers, and churn |

---

# 💡 Key Business Questions

This analysis helps answer:

- What percentage of customers are churning?
- What percentage of customers are retained?
- Which subscription plans have higher churn?
- How long do customers typically remain subscribed?
- What is the average revenue generated per customer?
- How much revenue is associated with churned customers?
- Are customers with escalated support issues more likely to churn?
- Which customer segments are at the highest risk?
- Are there geographical patterns in churn?

---

# 🚀 Business Recommendations

Based on the analytical framework, businesses can consider:

### 1. 🎯 Prioritizing High-Risk Customers
Target high-risk customers with proactive retention campaigns, personalized offers, and improved support.

### 2. 📞 Investigating Support Escalations
Analyze common escalation reasons and resolution processes to identify customer experience issues.

### 3. 💳 Reviewing High-Churn Plans
Evaluate plans with higher churn for pricing, features, flexibility, and value proposition.

### 4. 🗺️ Developing Location-Specific Strategies
Investigate states with higher churn and implement targeted retention initiatives.

### 5. 💰 Protecting High-Value Revenue
Prioritize customers with high monthly revenue and elevated churn risk.

---

# 🧠 Skills Demonstrated

### Data Analysis
- Exploratory Data Analysis (EDA)
- Data Cleaning
- Data Transformation
- Data Aggregation
- Data Validation

### Python
- Pandas
- NumPy
- Feature Engineering
- Data Manipulation

### SQL & Databases
- SQLite
- SQL Queries
- Database Exploration

### Business Analytics
- KPI Development
- Customer Churn Analysis
- Revenue Analysis
- Customer Segmentation
- Retention Analysis

### Data Visualization
- Matplotlib
- Seaborn
- Line Charts
- Bar Charts
- Correlation Heatmaps
- Pairwise Analysis

---

# 📂 Project Structure

```text
Customer-Churn-Analysis/
│
├── Churn_Analysis_New.ipynb
├── customer_churn.db
├── README.md
└── requirements.txt
```

---

# 🔄 Analytical Process

```text
1️⃣ Extract Data
        ↓
2️⃣ Explore Database Tables
        ↓
3️⃣ Clean Customer Data
        ↓
4️⃣ Clean Subscription Data
        ↓
5️⃣ Clean Support Data
        ↓
6️⃣ Handle Missing Values
        ↓
7️⃣ Standardize Data
        ↓
8️⃣ Merge Datasets
        ↓
9️⃣ Create Analytical Features
        ↓
🔟 Calculate KPIs
        ↓
📊 Perform Exploratory Data Analysis
        ↓
📈 Create Visualizations
        ↓
💡 Generate Business Insights
```

---

# 🔮 Future Improvements

- 📊 Build an interactive Power BI dashboard
- 🤖 Develop a machine learning churn prediction model
- 📧 Create automated alerts for high-risk customers
- 📈 Perform cohort analysis
- 💰 Calculate Customer Lifetime Value (CLV)
- 🔍 Perform deeper root-cause analysis
- ⚡ Automate the data pipeline

---

# 🏆 Project Highlights

- Built an end-to-end customer churn analytics workflow
- Extracted and analyzed data from a SQLite database
- Cleaned and standardized multiple datasets
- Integrated customer, subscription, and support data
- Handled duplicate customer records
- Created customer-level analytical features
- Calculated business-focused KPIs
- Analyzed churn across plans and geographical locations
- Evaluated support escalations and complaints
- Created churn risk segmentation
- Developed visualizations using Matplotlib and Seaborn

---

# 👨‍💻 Author

**Anshu Raj**

📊 Data Analyst | SQL | Python | Power BI | Excel

---

⭐ **If you found this project interesting, feel free to star the repository!**
