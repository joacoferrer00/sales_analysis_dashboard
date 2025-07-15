# 📂 Data Sources Overview

This project integrates multiple datasets sourced from the company's internal systems to create an automated and dynamic sales analysis dashboard. The core structure relies on fact tables enriched by custom dimension tables and auxiliary data sources. All files are stored and maintained via SharePoint, ensuring traceability and version control.

---

## 📦 1. Fact Tables

### 🔹 Sales Transactions (ERP Export)

The primary fact table contains transactional sales data exported from the company's ERP system in Excel format. This export includes billing data for the last two commercial seasons.

**Raw columns included:**
- Emission date
- Document type
- Client code and name
- Product code and description
- Quantity sold
- Unit price
- Net amount (local currency)
- Discounts and conditions (commercial and financial)
- Price list and payment method

**Transformation pipeline:**
This dataset is heavily cleaned and pre-processed using Power Query. Only the relevant fields are retained (e.g., date, quantity, value, product, and client identifiers), and the structure is standardized to ensure compatibility across the data model.

---

## 🎯 2. Objectives Table

A static Excel table is used to store commercial objectives, defined **at the start of the season**. It maps KPI targets by:
- Product group
- Geographic zone
- Month (within the season)

This file is manually curated but integrated into the model for automatic comparison between actual results and expected performance.

---

## 🧩 3. Dimension Tables

The model includes three main dimension tables:

### 🏷️ Product Dimension
- Product category and classification
- Family hierarchy (used for KPI grouping)
- Flags for custom logic and filtering

### 🌍 Client & Branch Mapping
- Internal client codes and branch IDs
- Geolocation and region tags for slicing KPIs by area

### 📅 Custom Calendar Table
- Season-based logic (March to February)
- Custom columns for `Season`, `Month in Season`, and `Closed Month Flag`

All dimension tables are standardized and cleaned prior to loading into Power BI, with consistent keys and formats for smooth relationships.

---

## 🔧 4. Integration & Refresh Logic

All files are stored on **SharePoint** and connected to Power BI via **URL-based web connectors**. The data loading is automated through Power Query transformations.

**Key aspects:**
- Manual refresh on demand (typically monthly or before key reporting events)
- One-click refresh process inside Power BI Desktop or Service
- No local files needed — all data resides in cloud storage
- Seamless merge of updated sales files with historical targets and dimensions

---

## 🛠️ Auxiliary Sources

Additional supporting tables include:
- 📈 **Historical FX rates** (for converting sales to USD)
- 📌 **KPI definitions** and auxiliary mapping tables (used in slicers and visuals)

These enable advanced calculations and maintain model integrity across different dashboards (product, zone, client).

---
