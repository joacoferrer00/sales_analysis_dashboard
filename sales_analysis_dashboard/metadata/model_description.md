# 📐 Data Model Description

The solution is built upon a **star schema architecture**, with two distinct fact tables and multiple shared dimensions. This dual-fact approach (Galaxy Schema) enables the comparison of actual performance versus commercial targets across different dimensions.

## 🔢 Fact Tables

- **SalesFact**: Contains transaction-level data extracted from the ERP, including quantities, net revenue (USD), customer codes, and product references. Cleaned and transformed in Power Query to remove unnecessary columns and ensure consistency.
- **Targets**: A static table loaded at the beginning of the season with predefined KPIs by product, region, and month. This table defines expected ratios or thresholds for each KPI and is joined by product, date, and store/region codes.

## 🧩 Shared Dimension Tables

- **Product Classification**: Central product taxonomy, used to group SKUs into families and segments for KPI calculations.
- **Calendar**: A custom date table with fiscal season logic (March to February), used for temporal alignment and dynamic filtering.
- **Store Codes**: Mapping between point-of-sale codes and business zones (used for KPI normalization by region).
- **Client Master** *(used in one dashboard)*: Enables slicing performance by customer segment. Includes inactive relationship for advanced filtering without double-counting.

## 🧠 Advanced Model Features

- **Inactive Relationships for Dynamic Segmentation**: One of the models includes an inactive relationship between the Sales and Client dimension. This is used for specific slicers and activated selectively within DAX measures using `USERELATIONSHIP()`, allowing flexible segment analysis without compromising total calculations.
- **Dual fact modeling**: Enables side-by-side comparisons of actual results vs targets by maintaining separate but connected data streams. All performance ratios are calculated from the intersection of these tables via shared keys.
- **Auxiliary Tables**:
  - **Comparative KPIs**: Unrelated helper table used for slicers and visual logic in KPI dashboards.
  - **Currency Table**: Used in dashboards that aggregate sales in USD and require historical exchange rates.

## 🔄 Data Refresh

The model is connected via **SharePoint URLs** to Excel source files exported from the ERP system. Refreshes are triggered manually or monthly, with full automation via Power BI Service once deployed. All transformations are handled in Power Query and measures are calculated with DAX, ensuring a fully automated and scalable process.

---

Let me know if you'd like to add a schema diagram reference or link to the images in `/images`. Otherwise, this `.md` is ready to go live.
