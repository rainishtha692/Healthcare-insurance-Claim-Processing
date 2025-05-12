# 🏥 Healthcare Insurance Claim Processing Data Warehouse

## 📌 Project Overview

This project focuses on designing and implementing a **healthcare-specific data warehouse** tailored for analyzing insurance claim processing. Using a star schema architecture, the system captures patient, treatment, hospital, and insurance-related information to support advanced reporting and analytics across healthcare operations.

The warehouse is structured to answer key business questions, monitor performance, and generate insights into claim handling, revenue, and operational efficiency.

---

## 🎯 Objective

To build a scalable, optimized data warehouse that enables stakeholders—such as hospital administrators, insurance coordinators, and analysts—to:

- Track hospital revenue from insurance claims
- Evaluate insurance provider processing speeds
- Analyze claim outcomes (approved, rejected, pending)
- Understand treatment trends
- Segment claims based on demographics or geography

---

## 🧱 Schema Design

- **Model Type:** Star Schema
- **Fact Table:** `fact_insurance_claims` – Stores measurable claim data
- **Dimension Tables:**
  - `dim_claim_patient` – Patient demographics
  - `dim_claim_doctor` – Doctor specialization and department
  - `dim_claim_treatment` – Treatment type and category
  - `dim_claim_hospital` – Hospital and location info
  - `dim_insurance_provider` – Insurance provider and plan
  - `dim_claim_date` – Date-related attributes (day, month, year)

🧩 **ER Diagram:** One central fact table surrounded by six dimension tables (1:M relationships).

---

## 🧪 Sample Queries & Insights

- **Total Revenue by Hospital:**
  ```sql
  SELECT h.institution_name, SUM(f.claim_amount) AS total_revenue
  FROM fact_insurance_claims f
  JOIN dim_claim_hospital h ON f.claim_hospital_id = h.claim_hospital_id
  GROUP BY h.institution_name;

  💡 Business Questions Answered
Which hospitals generate the most revenue from insurance claims?

What’s the average approval time by insurance provider?

How are claims distributed across statuses (Approved, Pending, Rejected)?

What treatments are most frequently claimed?

How do claims vary across cities and demographics?

📈 Dashboard Integration
The schema is compatible with BI tools like Power BI, Tableau, or Excel to create:

KPI Cards (Revenue, Claims Approved, Avg. Approval Time)

Bar Charts (Claim status, Revenue per hospital)

Line Charts (Claim trend over time)

Filters by insurance company, hospital, or city

📂 Project Structure 
healthcare_dw_project/
├── sql_scripts/            # DDL and DML scripts
├── sample_queries/         # Analytical SQL queries
├── dashboard/              # Power BI or Tableau files
├── ERD/                    # Entity-Relationship Diagram
├── README.md               # Project documentation
└── requirements.txt        # (Optional) For dependencies if integrated with Python or BI tools

 Conclusion
This data warehouse solution provides a robust foundation for analyzing healthcare insurance claims, helping stakeholders drive better decision-making, financial oversight, and operational improvements.


