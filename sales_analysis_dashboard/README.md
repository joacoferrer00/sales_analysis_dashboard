# 📊 Sales Analysis Dashboard – Power BI Project

⚠️ **Confidentiality Disclaimer**

This project is part of my professional portfolio and was created for demonstration purposes only.

- The data has been anonymized or synthetically generated.
- KPIs are representative but do not reflect real or confidential business information.
- Field, table, and entity names were modified to protect company privacy.

---

## 🧠 Overview

This Power BI dashboard was designed to replace static Excel reports used by the commercial team to monitor sales performance across key dimensions.

The project delivers an **automated, dynamic, and clear** analytics panel, capable of tracking:

- **Sales in product units** (by product category)
- **Revenue in USD** (by zone of influence)
- **Revenue in USD** (by customer)

It integrates both **actual sales data** and **target objectives**, enabling strategic comparisons by product line, region, and customer segment.

---

## 🔍 Key Features

- 📈 Comparative KPIs (e.g. *Product Group A / Base Product*)
- 🎯 Target-based performance tracking by location
- 📊 Seasonal sales evolution with customized calendar logic
- 📟 Dynamic slicers for product, customer, and region
- 📁 Fully automated data source integration via SharePoint
- 🌐 Responsive navigation with interactive menus

---

## 🧩 Data Model

The solution is built on a **Galaxy Schema**: two fact tables (sales & targets) linked to shared dimensions:

- Product Classification
- Calendar (custom seasonal logic: March to February)
- Location Code
- Costumer Code

You can explore the data model and KPI logic in the [`metadata/`](./metadata/) folder.

---

## 🧮 Sample DAX Measures

You’ll find real DAX examples used to build this dashboard in [`dax-measures/`](./dax-measures/), including:

- Relative ratio between product groups
- Difference vs. target (absolute and %)
- Dynamic seasonal accumulation until today

Each file includes contextual comments to explain its use case and logic.

---

## 📷 Screenshots

See the [`images/`](./images/) folder for selected views:

- `main_dashboard.png`: Overview with KPIs, totals and slicers
- `data_model_1.png` / `data_model_2.png`: Entity relationship diagrams

---

## 📁 Structure

sales_analysis_dashboard/
├── README.md
├── images/
├── dax-measures/
└── metadata/

---

## 👨‍💻 About Me

**Joaquín Ferrer**  
Industrial Engineer · Data Analytics · Power BI · SQL  
[🔗 LinkedIn](https://www.linkedin.com/in/joaqu%C3%ADnferrer/)

---

Feel free to reach out for feedback, collaboration, or freelance opportunities!