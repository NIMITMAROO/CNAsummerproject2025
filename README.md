
# 📦 Solving Inventory Inefficiencies Using SQL

## 🧾 Project Overview

Urban Retail Co. is a growing retail chain that operates both physical outlets and online stores, offering over 5,000 SKUs ranging from groceries to electronics. As operations have scaled, managing optimal inventory levels has become a challenge, resulting in overstock, stockouts, and underutilized data.

This project aims to resolve inventory inefficiencies by building a SQL-powered analytical framework that integrates external factors like weather and seasonality, alongside internal metrics like inventory turnover and demand forecasting.

---

## 🎯 Project Goals

- Design and implement a **relational database schema** to structure inventory data efficiently.
- Use **SQL analytics** to derive key insights such as:
  - Inventory turnover
  - Stockout and overstock risks
  - Supplier performance
  - Seasonal demand trends
- Develop Power BI dashboards to visualize KPIs and support strategic decisions.

---

## 🗂️ Database Design

**Database Name:** `inventory_analysis_db`

### Core Tables and Description

| Table Name       | Purpose                                                                          |
|------------------|----------------------------------------------------------------------------------|
| `stores`         | Tracks daily inventory per store including region, product ID, and category     |
| `inventory`      | Contains inventory levels, sales data, pricing, demand forecasts, etc.          |
| `category`       | Maps products to specific categories                                              |
| `external_factor`| Links inventory with contextual factors like weather, season, promotions        |
| `seasonality`    | Encodes seasonal labels such as Summer, Autumn                                  |
| `weather`        | Stores weather condition tags like Sunny or Rainy                               |

### Key Relationships

- `stores.category_id` → `category.category_id`
- `stores.inventory_id` → `inventory.inventory_id`
- `external_factor.inventory_id` → `inventory.inventory_id`
- `external_factor.weather_id` → `weather.weather_id`
- `external_factor.season_id` → `seasonality.season_id`

---

## 🧮 Key SQL Analytics

SQL queries (see `Queries.sql`) enable various forms of analysis:

- **Stock Level Aggregation**: Sum of stock by region, store, and product
- **Low Inventory Detection**: Flag items with levels below dynamic reorder points
- **Inventory Turnover**: Measure sales efficiency using moving averages
- **Seasonal Forecasting**: Compare forecasted vs. actual demand across seasons
- **Stockout/Overstock Days**: Count days of insufficient or excess inventory
- **Product Classification**: Identify fast-selling vs slow-moving items

---

## 📊 Power BI Dashboard

The Power BI report (`Dashboard.pbix`) visually showcases:

- Inventory turnover trends
- Forecast accuracy vs actual sales
- Category-wise stockout analysis
- Seasonality-based demand spikes
- Supplier performance metrics

---

## 🔍 Executive Insights

From the analysis, the following insights were gathered:

- **Slow-Moving Items**: Identified by high average age (>900 days)
- **Stockouts**: Products like P0016 and P0175 frequently go out of stock
- **Overstocking**: Many SKUs are held longer than needed (>370 days)
- **Seasonality Gaps**: Autumn demand peaks not met by current inventory strategy

📌 **Recommendation Highlights**:

- Use rolling 3-month forecasts for purchasing decisions
- Increase restock frequency for fast-moving items
- Offload slow inventory through promotions or supplier returns
- Align supply plans with weather and seasonal patterns

---

## 📁 File Structure

```
.
├── Documentation.pdf          # ER diagram and schema documentation
├── ExecutiveSummary.pdf       # Summary of insights and business recommendations
├── Queries.sql                # SQL queries for analysis and KPIs
├── Dashboard.pbix             # Power BI dashboard (interactive visualizations)
├── README.md                  # This file
```

---

## 🚀 Business Impact

By implementing this solution, Urban Retail Co. can:

- Reduce excess inventory and free up working capital
- Improve stock availability, enhancing customer satisfaction
- Make data-driven procurement and promotion decisions
- Strengthen supplier performance tracking and accountability

---

