# WGU D211: Customer Churn Analysis with Tableau and SQL

This project combines internal and external telecom customer data sources to explore churn behavior across California using PostgreSQL and Tableau. The analysis integrates data from company databases and a public Kaggle dataset, transforming and unifying it for visualization and insight generation.

## 🎯 Objective

**Business Problem:**  
Customer churn has a direct impact on revenue. Understanding churn patterns can help prioritize customer retention efforts and improve service offerings.

**Goal:**  
Clean, merge, and visualize churn data using Tableau to compare trends in customer behavior from both internal and external data sources.

## 📁 Project Files

- `external_churn_data.zip`: External dataset (from Kaggle)
- `internal_churn_data_tables.zip`: Internal company data (PostgreSQL format)
- `pgadmin_code.txt`: Full SQL code for cleaning, merging, and preparing data for Tableau
- `D211_Jeremy_Dorrough_Performace_Assessment.docx`: Performance assessment and written summary of findings
- `D211_Jeremy_Dorrough_Tableau_Presentation.twbx`: Tableau dashboard used for final visualizations

## 🧰 Tools Used

- **PostgreSQL / pgAdmin 4** – For SQL querying and data preparation
- **Tableau** – For data visualization
- **Python (optional)** – For supplemental EDA and preprocessing

## 🗃️ Data Sources

### Internal Company Data
- Contains customer IDs, churn status, contract duration, tenure, monthly charges, location (ZIP, Lat/Lng)
- Limited to California customers

### External Kaggle Dataset
- Contains broader customer features such as age, internet service, number of dependents, payment method, churn category
- Filtered and normalized to match internal data structure

## ⚙️ Data Cleaning and Processing Steps

1. **Extract California data only** from internal tables
2. **Normalize and rename columns** (e.g., tenure → Tenure, Monthly_Charge, Bandwidth_GB_Month)
3. **Unify column types** (e.g., round numeric values)
4. **Add Source column** to differentiate internal (`wgu`) vs external (`kaggle`) data
5. **Remove irrelevant rows** (e.g., customers using unlimited data)
6. **Merge datasets** into `data_for_tableau` using `UNION ALL`

SQL code for all transformations is located in `pgadmin_code.txt`.

## 📊 Tableau Dashboard

Final Tableau visualizations answer key business questions such as:

- What are the differences in churn rate between contract types?
- Are higher-bandwidth users more or less likely to churn?
- Do certain ZIP codes show higher concentrations of churn?

The dashboard is interactive and allows filtering by contract type, ZIP code, and data source (internal vs external).

## 🔍 Insights & Recommendations

- **Churn is highest among customers with month-to-month contracts**
- **External data showed more geographic churn concentration**
- **Higher bandwidth does not directly correlate to lower churn—price sensitivity likely plays a stronger role**

**Recommendations:**
- Target high-bandwidth users with expiring monthly contracts for retention offers
- Investigate pricing sensitivity and regional service issues in high-churn ZIPs
- Incorporate predictive churn modeling in future phases

## 👤 Author

Jeremy Dorrough  
Western Governors University  

## 📚 References

- [Kaggle Telecom Dataset](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)
- PostgreSQL Official Docs: [postgresql.org](https://www.postgresql.org/docs/)
- Tableau Public: [tableau.com](https://www.tableau.com/)
