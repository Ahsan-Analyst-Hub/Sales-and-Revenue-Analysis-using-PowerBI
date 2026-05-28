# 📊 Sales and Revenue Analysis using Power BI

## 📌 Project Overview

This repository contains a **Sales Analytics Dashboard Project** developed using relational sales datasets and visualized in **Power BI**. The project transforms raw transactional data into actionable business insights through data modeling, KPI analysis, and interactive dashboard design.

The solution is built using three connected datasets:

* Customers
* Orders
* Products

The dashboard helps stakeholders monitor:

* Revenue performance
* Customer purchasing behavior
* Product sales trends
* Country-wise business performance
* Customer retention and loyalty

---

# 🎯 Objective

The primary objective of this project is to demonstrate how relational sales data can be transformed into meaningful business intelligence using **Power BI** and **DAX measures**.

This project aims to answer key business questions such as:

* How much total revenue is generated?
* Which products generate the highest sales?
* Which countries contribute the most revenue?
* Are customers returning for repeat purchases?
* What are the monthly sales trends?
* Which customers contribute the highest revenue?

---

# 🗂️ Dataset Description

The project uses three relational datasets connected through primary and foreign keys.

## 1️⃣ Customers Table

Contains customer-related information.

| Column Name  | Description                |
| ------------ | -------------------------- |
| CustomerID   | Unique customer identifier |
| CustomerName | Customer full name         |
| Country      | Customer country           |

---

## 2️⃣ Orders Table

Contains transactional sales data.

| Column Name | Description             |
| ----------- | ----------------------- |
| OrderID     | Unique order identifier |
| CustomerID  | Customer reference      |
| ProductID   | Product reference       |
| OrderDate   | Date of purchase        |

---

## 3️⃣ Products Table

Contains product details and pricing information.

| Column Name | Description               |
| ----------- | ------------------------- |
| ProductID   | Unique product identifier |
| ProductName | Product name              |
| Price       | Product selling price     |

---

# 🔗 Data Model Relationships

The datasets are connected using the following relationships:

```text
Customers[CustomerID] → Orders[CustomerID]
Products[ProductID] → Orders[ProductID]
```

This relational structure creates a clean **star-schema data model** suitable for Power BI analytics.

---

# 🛠️ Tools & Technologies Used

| Tool        | Purpose                              |
| ----------- | ------------------------------------ |
| SQL         | Data preparation and analysis        |
| Power BI    | Dashboard creation and visualization |
| DAX         | KPI calculations and measures        |
| Excel / CSV | Source dataset storage               |

---

# 📈 Key Performance Indicators (KPIs)

The dashboard includes several business KPIs to evaluate sales performance.

## ✅ Total Revenue

Measures overall sales generated from all orders.

## ✅ Total Orders

Counts the total number of transactions completed.

## ✅ Unique Customers

Calculates the number of distinct customers who placed orders.

## ✅ Average Order Value (AOV)

Shows the average revenue generated per order.

## ✅ Repeat Customer Rate

Measures customer loyalty by identifying repeat buyers.

## ✅ Revenue by Country

Analyzes country-wise sales contribution.

## ✅ Top-Selling Products

Identifies the highest-performing products based on revenue or order count.

## ✅ Product Revenue Mix

Shows revenue distribution across products.

## ✅ Monthly Sales Trend

Tracks revenue performance over time.

## ✅ Customer Concentration

Measures dependency on top customers for revenue generation.

---

# 🧮 DAX Measures

Below are the core DAX measures used in the Power BI dashboard.

## Total Revenue

```DAX
Total Revenue =
SUMX(
    Orders,
    RELATED(Products[Price])
)
```

---

## Total Orders

```DAX
Total Orders =
COUNTROWS(Orders)
```

---

## Unique Customers

```DAX
Unique Customers =
DISTINCTCOUNT(Orders[CustomerID])
```

---

## Average Order Value

```DAX
Average Order Value =
DIVIDE([Total Revenue], [Total Orders])
```

---

## Repeat Customers

```DAX
Repeat Customers =
COUNTROWS(
    FILTER(
        VALUES(Orders[CustomerID]),
        CALCULATE(COUNTROWS(Orders)) > 1
    )
)
```

---

## Repeat Customer Rate

```DAX
Repeat Customer Rate =
DIVIDE([Repeat Customers], [Unique Customers])
```

---

## Revenue per Customer

```DAX
Revenue per Customer =
DIVIDE([Total Revenue], [Unique Customers])
```

---

## Orders per Customer

```DAX
Orders per Customer =
DIVIDE([Total Orders], [Unique Customers])
```

---

## Product Revenue

```DAX
Product Revenue =
SUMX(
    Orders,
    RELATED(Products[Price])
)
```

---

# 📊 Dashboard Design

The dashboard is designed to be:

* Interactive
* Easy to interpret
* Business-focused
* Visually clean

---

## 📍 Recommended Dashboard Layout

### 🔹 Top Section — KPI Cards

* Total Revenue
* Total Orders
* Unique Customers
* Average Order Value
* Repeat Customer Rate

---

### 🔹 Middle Section — Trend Analysis

* Monthly Revenue Trend (Line Chart)
* Monthly Orders Trend (Column Chart)

---

### 🔹 Bottom Section — Business Insights

* Revenue by Product
* Revenue by Country
* Top Customers Table
* Product Revenue Mix

---

# 🎛️ Recommended Slicers

The following slicers improve dashboard interactivity:

* Order Date
* Country
* Customer Name
* Product Name

---

# ✅ Dashboard Best Practices

* Use consistent color themes
* Keep visuals clean and uncluttered
* Apply conditional formatting for KPIs
* Use drill-through pages for detailed analysis
* Add filters for monthly and yearly trends
* Ensure mobile-friendly report design

---

# 📌 Business Insights Generated

This dashboard helps businesses:

* Track sales growth
* Identify high-performing products
* Monitor customer retention
* Understand market performance by country
* Analyze purchasing behavior
* Support strategic business decisions

---

# 🚀 Future Improvements

Potential future enhancements include:

* Profit and cost analysis
* Forecasting and predictive analytics
* Customer segmentation
* Inventory optimization
* Real-time dashboard integration
* SQL-based ETL automation

---

# 📷 Dashboard Preview

> *(Add Power BI dashboard screenshots here)*

---

# 📁 Repository Structure

```text
Sales-Analytics-PowerBI/
│
├── Dataset/
│   ├── Customers.csv
│   ├── Orders.csv
│   └── Products.csv
│
├── PowerBI/
│   └── Sales_Analytics.pbix
│
├── Images/
│   └── dashboard-preview.png
│
└── README.md
```

---

# 📚 Learning Outcomes

Through this project, the following skills were demonstrated:

* Relational data modeling
* SQL-based analytics
* Power BI dashboard design
* DAX measure creation
* KPI analysis
* Data storytelling
* Business intelligence reporting

---

# 🏁 Conclusion

This project demonstrates how relational sales datasets can be transformed into a professional business intelligence solution using Power BI.

By combining customer, order, and product data into an interactive dashboard, organizations can gain valuable insights into:

* Sales performance
* Customer loyalty
* Product trends
* Regional business growth

The dashboard not only reports business metrics but also supports strategic decision-making and performance optimization.

---

# 👤 Author

**Ahsan ul Haq**

Data Analytics | SQL | Power BI | Business Intelligence
