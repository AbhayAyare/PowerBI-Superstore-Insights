# 🌌 Power BI Superstore Sales Performance Dashboard

> **Author:** Abhay Ayare  
> **Tool:** Microsoft Power BI | **Dataset:** Sample Superstore (Kaggle)  
> **Goal:** Analyze regional, product-wise, and time-based sales trends with forecasting & insights.

---

## 🧠 Overview
The **Superstore Sales Performance Dashboard** transforms raw retail data into business intelligence.  
It visualizes revenue, profit, and category performance using **DAX-driven KPIs**, **AI forecasting**, and **interactive analytics**.

---

## 🎯 Objectives
- Track overall **sales, profit, and ROI**  
- Identify **top-performing regions, products, and categories**  
- Visualize **monthly trends and future forecasts**  
- Enable **dynamic drill-through and filtering**

---

## 📊 Dashboard Pages

### 1️⃣ Sales Overview
- **Cards:** Total Sales, Total Profit, ROI, Profit Margin  
- **Charts:** Line (Monthly Trend), Bar (Category Sales), Donut (Segment Sales), Map (Region Sales)  
- **Slicers:** Region, Category, Year  
🖼️ `screenshots/Page1_SalesOverview.png`

### 2️⃣ Product Insights
- **Bar:** Sub-Category vs Sales  
- **Tree Map:** Product Name vs Sales  
- **Matrix:** Product × Region → Sales & Profit  
- **KPI:** Top Product (Dynamic via DAX)  
🖼️ `screenshots/Page2_ProductInsights.png`

### 3️⃣ Forecasting
- **Line Chart:** Sales Forecast (6 Months, 95% CI)  
- **Decomposition Tree:** Total Sales → Region → Category → Sub-Category  
🖼️ `screenshots/Page3_Forecasting.png`

---

## 🧮 Key DAX Measures
```DAX
Total Sales = SUM('Sample - Superstore'[Sales])
Total Profit = SUM('Sample - Superstore'[Profit])
Profit Margin = DIVIDE([Total Profit], [Total Sales], 0)
ROI = DIVIDE([Total Profit], [Total Discount], 0)

Top Product Name =
VAR TopProduct =
    TOPN(1,
        SUMMARIZE('Sample - Superstore','Sample - Superstore'[Product Name],"Sales",[Total Sales]),
        [Total Sales],
        DESC)
RETURN MAXX(TopProduct,'Sample - Superstore'[Product Name])

Dynamic Title = "Sales Dashboard for " & SELECTEDVALUE('Sample - Superstore'[Region],"All Regions")
```
---

⚙️ Interactivity

🔍 Drill-through: Product → Region → Salesperson

🧭 Navigation Buttons: Page switching

🪄 Dynamic Titles & Tooltips: Context-aware visuals

⚡ What-If Parameter: Discount sensitivity analysis

📈 Insights

🏆 West Region contributes ~40% of sales

💼 Office Supplies has highest profit margin

🎁 December spikes due to holiday sales

📈 Forecast: +10% growth next quarter


🧰 Tools
Tool	Purpose
Power BI	Visualization & modeling
DAX	Calculated KPIs
Power Query	Data cleaning
CSV/Excel	Source dataset
Power BI Service	Cloud publishing

```📂 Folder Structure
PowerBI-Superstore-Insights/
├── Superstore.pbix
├── Sample-Superstore.csv
├── DAX-Measures.txt
├── README.md
└── /images
```
🚀 Usage

Clone this repo
```
git clone https://github.com/AbhayAyare/PowerBI-Superstore-Insights.git
```

Open Superstore.pbix in Power BI Desktop

Refresh dataset → Interact with filters and insights

💼 Author
```
Abhay Ayare
📊 Power BI | Data Analytics | DAX Modeling
```
