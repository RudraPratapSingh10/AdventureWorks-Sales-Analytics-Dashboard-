# 🚴 AdventureWorks Sales Analytics Dashboard
The raw data went through a proper ETL process — 3 tables (dim_customers, dim_products, fact_sales) were cleaned, transformed, and loaded into a Star Schema Data Warehouse. The dashboard consumes the final aggregated output from that warehouse — just like real-world BI tools do.

> A fully interactive, single-file Sales Analytics Dashboard built on the **AdventureWorks dataset (2010–2014)**, consuming final aggregated data from a **Star Schema Data Warehouse** — just like real-world BI tools.

🔗 **Live Demo:** [https://playful-bubblegum-9be42d.netlify.app/adventureworks_dashboard.html](https://playful-bubblegum-9be42d.netlify.app/)

---

## 📌 Project Overview

This project follows a complete **end-to-end data pipeline**:

```
Raw CSV Files →  Star Schema Data Warehouse  →  Dashboard
(dim_customers   (fact_sales joined with         
 dim_products    dim tables, aggregated)       
 fact_sales)
```

The dashboard does **not** query raw data directly. Instead, it uses **pre-aggregated results** from the Data Warehouse layer — mirroring how enterprise BI tools like Power BI and Tableau consume data.

---

## 📊 Dashboard Features

### KPI Cards (6 Total)
| KPI | Value |
|-----|-------|
| 💰 Total Revenue | $29.35M |
| 📈 Total Profit | $11.68M |
| 🛒 Total Orders | 27,659 |
| 👥 Total Customers | 18,484 |
| % Profit Margin | 39.8% |
| ⚡ Avg Order Value | $1,062 |

### Charts (8 Total)
| # | Chart Type | Metric |
|---|-----------|--------|
| 1 | Area Line Chart | Monthly Revenue Trend (38 months) |
| 2 | Grouped Bar Chart | Revenue by Year |
| 3 | Donut Chart | Category Split (Bikes / Accessories / Clothing) |
| 4 | Horizontal Bar | Top 10 Products by Revenue |
| 5 | Combo Chart | Country Revenue (bar) + Customers (line, dual axis) |
| 6 | Donut Chart | Product Line Distribution |
| 7 | Donut Chart | Gender Revenue Split |
| 8 | Stacked Bar Chart | Revenue by Year × Category |

### Global Filters (3 Slicers)
- 📅 **Year** — All / 2011 / 2012 / 2013 / 2014
- 🏷️ **Category** — All / Bikes / Accessories / Clothing
- 🌍 **Country** — All / USA / Australia / UK / Germany / France / Canada

> All 3 filters work together with **AND logic** — every filter change updates all 8 charts and all 6 KPI cards simultaneously.

---

## 🗃️ Dataset

**Source:** AdventureWorks (Microsoft Sample Database)  
**Period:** 2010 – 2014  
**Total Records:** 60,379 rows

### Tables Used
```
dim_customers   →  18,484 unique customers (Country, Gender, Marital Status)
dim_products    →  130 unique products (Category, Subcategory, Product Line)
fact_sales      →  60,379 sales transactions (Revenue, Quantity, OrderDate)
```

### Data Warehouse Schema (Star Schema)
```
                    ┌─────────────────┐
                    │   fact_sales    │
                    │─────────────────│
               ────▶   ProductKey     ◀───|
              │     │  CustomerKey    │     │
              │     │  OrderDate      │     │
              │     │  SalesAmount    │     │
              │     │  Quantity       │     │
              │     └─────────────────┘     │
              │                             │
   ┌──────────────────┐        ┌────────────────────┐
   │  dim_products    │        │   dim_customers    │
   │──────────────────│        │────────────────────│
   │  ProductID       │        │  CustomerID        │
   │  ProductName     │        │  Country           │
   │  Category        │        │  Gender            │
   │  Subcategory     │        │  MaritalStatus     │
   │  ProductLine     │        └────────────────────┘
   │  ListPrice       │
   └──────────────────┘
```

---

## 📁 Project Structure

```
adventureworks-dashboard/
│
├── data/
│   ├── dim_customers.csv       # Customer dimension table
│   ├── dim_products.csv        # Product dimension table
│   └── fact_sales.csv          # Sales fact table
│
├── adventureworks_dashboard.html   # Main dashboard (single file)
├── README.md                       # This file
```

---

## 🚀 Getting Started

### Open Directly
Just open `adventureworks_dashboard.html` in any modern browser. No server needed!
```

---

## 📈 Key Insights from Data

- 🚴 **Bikes** dominate revenue at **96.4%** of total sales ($28.3M)
- 🇺🇸 **USA & Australia** are top markets — together account for **62%** of revenue
- 📅 **2013** was the best year — $16.34M revenue (56% of total)
- 🏆 **Mountain-200** series holds 6 of the Top 10 product slots
- ♀️ Nearly **50/50 gender split** — Female: $14.8M vs Male: $14.5M

---

## 👤 Author

**Rudra Pratap Singh**

[![GitHub](https://img.shields.io/badge/GitHub-RudraPratapSingh10-black?logo=github)](https://github.com/RudraPratapSingh10)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Rudra%20Pratap%20Singh-blue?logo=linkedin)](https://www.linkedin.com/in/rudra-pratap-singh10)

---

## 📄 License

This project is licensed under the **MIT License** — feel free to use, modify, and share!

---

⭐ **If you found this useful, please give it a star!** ⭐
