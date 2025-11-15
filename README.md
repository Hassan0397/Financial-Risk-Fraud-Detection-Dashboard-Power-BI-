# 📊 Financial Risk & Fraud Detection Dashboard (Power BI)

An interactive **Financial Risk & Fraud Detection Dashboard** built in **Power BI** to analyze financial transactions, detect suspicious patterns, and provide executives with a real-time overview of fraud risk.

This project covers:  
**Data Prep → Data Load → Data Modeling → Transformations → DAX Measures → Executive Dashboard**

---

## 🚀 Project Workflow

### 🟦 1. Data Preparation
Created realistic CSV datasets:
- `fact_Transactions.csv` → Transaction details  
- `dim_Customers.csv` → Customer profile data  
- `dim_Date.csv` → Calendar table  
- `fact_Alerts.csv` → Fraud alert activity  

Preparation included:
- Clean column names  
- No duplicates in dimensions  
- Business-relevant fields (CustomerID, RiskScore, FraudFlag, Amount)

---

### 🟩 2. Data Load
Imported CSV files into **Power BI Desktop (Get Data → Text/CSV)**.

Verified and corrected data types:
- IDs → *Whole Number*  
- Amount → *Currency (Decimal)*  
- Date → *Date*  
- Flags (FraudFlag, AlertStatus) → *Text/Boolean*

---

### 🟨 3. Data Modeling
Built a **Star Schema** in Model View.

**Fact Tables**
- `fact_Transactions`
- `fact_Alerts`

**Dimension Tables**
- `dim_Customers`
- `dim_Date`

Relationships:
- fact_Transactions → dim_Customers (CustomerID)  
- fact_Transactions → dim_Date (Date)  
- fact_Alerts → fact_Transactions (TransactionID)  
- fact_Alerts → dim_Date (AlertDate)

Marked `dim_Date[Date]` as the official **Date Table**.

---

### 🟧 4. Transformations (Power Query)
- Renamed columns to meaningful business labels  
- Standardized text casing (Country, Channel, Segment)  
- Removed duplicates  
- Replaced nulls with defaults  
- Ensured accurate data types  

---

### 🟥 5. Core DAX Measures
Created reusable KPIs inside fact tables.

#### **Transaction KPIs**
- Total Transactions  
- Total Transaction Amount (USD)  
- Avg Risk Score  

#### **Fraud KPIs**
- Total Fraud Transactions  
- Total Fraud Amount (USD)  
- Fraud Rate %  
- High-Risk Transactions  
- Distinct Customers with Fraud  

#### **Time Intelligence**
- Transactions Last 30 Days  
- Fraud Last 30 Days  
- Fraud Rate Last 30 Days %  

#### **Alert Metrics**
- Total Alerts  
- Open Alerts  
- High Severity Alerts  
- Alert Resolution Rate %  

All measures formatted (Currency, %, Decimal) with consistent naming.

---

## 🖥️ Executive Dashboard — Fraud Overview

### 📸 Dashboard Screenshot  
[Fraud Overview](https://github.com/Hassan0397/Financial-Risk-Fraud-Detection-Dashboard-Power-BI-/blob/main/Financial%20Risk%20%26%20Fraud%20Detection%20Overview.png)  
*(Replace with your actual screenshot)*

### Dashboard Components
- **Title:** Executive Overview — Financial Risk & Fraud Detection  
- **KPI Cards:**  
  - Total Transactions  
  - Fraud Amount  
  - Fraud Rate %  
  - Customers with Fraud  
- **Slicers:** Year, Channel, Country, Segment  
- **Line Chart:** Transactions vs Fraud Amount trend  
- **Bar Chart:** Top 10 Fraud Customers  
- **Table:** Recent Fraud Transactions (RiskScore, Amount formatting)  
- **Map (Optional):** Fraud Amount by Country  

### Formatting Applied
- Blue → Safe  
- Red → Fraud / High Risk  
- Amber → Warning  
- Clean alignment, spacing, and labeling

---

## 📈 Key Metrics Explained
- **CLV — Customer Lifetime Value**  
- **NPS — Net Promoter Score**  
- **CSAT — Customer Satisfaction Score**  
- **Fraud Rate % = Fraud Transactions ÷ Total Transactions × 100**  
- **Alert Resolution Rate % = Resolved Alerts ÷ Total Alerts × 100**

---

## 🛠 Tools Used
- Microsoft Power BI Desktop  
- Power Query  
- DAX (Data Analysis Expressions)  
- CSV Data Files  

---

## ✅ Outcome
With this dashboard, executives can:
- Monitor fraud trends over time  
- Identify high-risk customers & regions  
- Track financial losses from fraud  
- Review open alerts & resolution rate  
- Slice data by Year, Country, Channel, Segment  

