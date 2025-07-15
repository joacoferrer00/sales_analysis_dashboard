# 📊 KPI Definitions

This project includes the definition and tracking of 14 core KPIs focused on product mix analysis.

## 🎯 KPI Logic

All KPIs follow a unified structure based on **relative product ratios**. The general formula is:

KPI = Sales of Product Group A / Sales of Reference Product Group

This approach enables the business to track the **sales penetration of strategic product families** in relation to a consistent baseline, helping to monitor commercial focus and product mix performance across different segments.

## 🧠 Analytical Purpose

The KPIs were designed to:

- Highlight deviations in sales composition across product families.
- Provide clear benchmarks with predefined targets per segment.
- Normalize sales behavior across heterogeneous product categories.

## 🧩 Granularity & Targets

Each KPI is evaluated at different levels of granularity:

- 🔹 **Global** (company-wide)
- 🏢 **By Branch** (sales office or point of sale)
- 🌎 **By Influence Zone** (geographic segmentation)
- 👤 **By Client** (selected KPIs only)

Each level may have **specific targets**, established based on historical performance, strategic focus, or seasonal expectations.

## 📦 Product Structure

KPIs are grouped by:

- **Main Families** (e.g., core products, premium lines)
- **Subfamilies** (e.g., accessories, maintenance tools)

These groupings were defined based on business relevance and commercial strategy.

## ⚙️ Implementation Notes

- KPIs are calculated in DAX using dynamic filters.
- Slicers and detached tables are used to allow flexible switching and comparison across KPIs.
- All values are evaluated on a seasonal basis (March to February logic).

See the [`dax-measures`](../dax-measures/) folder for full implementation examples.