# 📊 Regional Sales Optimization

![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Wrangling-150458?logo=pandas&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?logo=powerbi&logoColor=black)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)
![Excel](https://img.shields.io/badge/Excel-Data%20Source-217346?logo=microsoftexcel&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

---

## 📌 Problem Statement

Sales teams often have a gut feeling about what is working — but gut feelings do not scale. Acme Co. had five years of transactional sales data sitting across spreadsheets with no clear picture of which regions were actually growing, which products were carrying the business, or why some channels were quietly outperforming others.

This project was built to answer one central question:

> **"How can Acme Co. leverage 5 years of historical sales data to identify revenue and profit drivers, uncover seasonal trends, and optimize pricing, channel, and market expansion strategies?"**

**The core business problems this tackles:**
- Inconsistent revenue and profit performance across U.S. regions with no visibility into root causes
- No clear understanding of seasonal demand cycles, making inventory and promotional planning reactive instead of proactive
- Lack of insight into which sales channels and SKUs are truly driving margin — not just volume
- Budget vs. actual performance gaps that were not being tracked or explained

---

## 🎯 What This Project Covers

- End-to-end analysis of **64,000+ transactions** across **5 years (2014–2018)**
- Revenue, profit, and margin breakdowns by **product, channel, region, state, and customer**
- Seasonal trend detection and monthly rhythm analysis
- Channel profitability comparison (Wholesale vs. Distributor vs. Export)
- Geographic performance mapping across **47 U.S. states and 4 regions**
- Budget vs. actual performance tracking
- A 3-page interactive Power BI dashboard for executive and operational stakeholders

---

## 🗂️ Project Structure

```
regional-sales-optimization/
│
├── 📁 data/
│   └── dataset.xlsx                  # Raw multi-sheet sales dataset (2014–2018)
│
├── 📁 notebooks/
│   └── notebook.ipynb                # Full EDA — 80 cells of analysis and insights
│
├── 📁 exports/
│   └── data_EDA_Exported.csv         # Cleaned and engineered dataset exported from Python
│
├── 📁 dashboard/
│   ├── dashboard.pbix                # 3-page interactive Power BI dashboard
│   ├── Executive_Overview_trends.png          # Dashboard page 1 screenshot
│   ├── Product_Channel_Performance.png        # Dashboard page 2 screenshot
│   └── Geographic_Customer_Insights.png       # Dashboard page 3 screenshot
│
├── 📁 reports/
│   ├── Analysis_Report.docx          # Full project write-up with EDA findings and recommendations
│   └── Business_Problem.docx         # Project brief — problem statement, scope, and objectives
│
├── README.md                         # You're reading it!
└── requirements.txt                  # Python dependencies
```

---

## 📊 About the Dataset

| Property | Detail |
|---|---|
| Company | Acme Co. (anonymized U.S. retailer) |
| Period | January 2014 — February 2018 |
| Total Transactions | 64,104 orders |
| Features | 21 columns |
| Channels | Wholesale, Distributor, Export |
| Regions | Midwest, Northeast, South, West |
| States Covered | 47 U.S. states |
| Unique Products | 30 SKUs |
| Unique Customers | 175 accounts |

**Key columns in the dataset:**
`order_date`, `customer_name`, `channel`, `product_name`, `quantity`, `unit_price`, `revenue`, `cost`, `profit`, `profit_margin_pct`, `state`, `us_region`, `budget`, `order_month`

---

## 🔧 Tech Stack

| Tool | What I Used It For |
|---|---|
| **Python + Pandas** | Data profiling, cleaning, wrangling, and EDA |
| **Matplotlib & Seaborn** | Visualization during exploratory analysis |
| **Jupyter Notebook** | Interactive 80-cell analysis environment |
| **Microsoft Excel** | Source data format (multi-sheet workbook) |
| **Power BI Desktop** | 3-page interactive executive dashboard |

---

## 🐍 Python — Data Profiling, Cleaning & EDA

Everything lives in `notebooks/notebook.ipynb` — 80 cells covering the full journey from raw data to polished insights. Here is what was done at each stage:

**Data Profiling & Initial Inspection:**
- Verified schema, checked column data types, and flagged structural issues
- Identified missing values in the `budget` column and resolved them before analysis
- Corrected date formats and standardized column naming conventions

**Data Cleaning & Wrangling:**
- Handled null budget records without distorting the overall financial picture
- Joined and normalized tables from multi-sheet Excel source
- Engineered new time-based columns: `order_month_name`, `order_month_num`, and `order_month` for cleaner temporal analysis
- Computed `profit`, `profit_margin_pct`, and `total_cost` as derived features
- Added geographic enrichment: `lat`, `lon`, `us_region` for spatial analysis

**Exploratory Data Analysis (12+ visualizations):**

| # | Analysis | Chart Type | Key Finding |
|---|---|---|---|
| 1 | Monthly Sales Trend Over Time | Line chart | Consistent seasonal peaks in May–June; sharp 2017 dip warrants investigation |
| 2 | Monthly Seasonality (All Years) | Line chart | Jan starts strong (~$99M), dips in spring, rebounds mid-summer |
| 3 | Top 10 Products by Revenue | Horizontal bar | Products 26 ($117M) and 25 ($109M) dominate; sharp drop to #3 |
| 4 | Top 10 Products by Avg Profit Margin | Horizontal bar | Products 18 and 28 lead with ~$8.3K avg margin |
| 5 | Sales by Channel | Pie chart | Wholesale = 54%, Distributor = 31%, Export = 15% |
| 6 | Order Value Distribution | Histogram | Right-skewed; mode at $50K–$60K; long tail to $500K |
| 7 | Profit Margin % vs Unit Price | Scatter plot | No price-margin correlation; consistent margin bands across all price ranges |
| 8 | Unit Price Distribution per Product | Box plot | Pricing variability reveals outlier transactions per SKU |

---

## 📈 Key Findings

Here is what the data actually revealed:

| Area | Finding |
|---|---|
| 💰 **Total Revenue** | $1.2B across 5 years across 64K+ orders |
| 📈 **Total Profit** | $461.8M at a 37.36% overall profit margin |
| 🛒 **Revenue per Order** | $19.3K average order value |
| 🏆 **Top Product** | Product 26 at $117M revenue — more than double the median SKU |
| 🌍 **Top Channel** | Wholesale drives 54% of revenue ($668M) but Export has room to grow |
| 🗺️ **Top Region** | West leads with $372M (30%), but Midwest is the most consistent |
| 📍 **Top State** | Wyoming tops state revenue at $1.8M |
| 📅 **Seasonality** | Strong May–June peaks annually; January drop is the most predictable trough |
| ⚠️ **Risk Flag** | Wholesale concentration at 54% creates channel dependency risk |
| 💡 **Margin Insight** | Profit margins are consistent across price bands — no pricing power premium detected |

---

## 💡 Business Recommendations

Based on what the data showed, here is what Acme Co. should consider:

**1. Reduce Wholesale Concentration Risk**
With 54% of revenue tied to a single channel, a disruption in wholesale relationships could significantly impact the business. Growing the Distributor and Export channels — currently at 31% and 15% respectively — would create a more resilient revenue mix.

**2. Investigate the 2017 Revenue Dip**
A sharp revenue drop in early 2017 stood out as an anomaly against the otherwise stable seasonal pattern. This could reflect a lost account, supply chain issue, or market disruption. Understanding the root cause prevents a repeat.

**3. Double Down on Products 26 and 25**
These two products generate $117M and $109M respectively — far ahead of anything else in the portfolio. They deserve priority in marketing spend, inventory management, and any new market expansion plans.

**4. Target the Export Channel for Growth**
Export is currently the smallest channel at 15%, but it shows comparable margin efficiency (37.02%) to Wholesale (38.01%). With the right international partnerships, there is meaningful upside here without cannibalizing existing domestic revenue.

**5. Fix Underperforming States Before Adding New Ones**
The bottom 5 states by revenue (including Delaware at $1.2M) are likely underserved, not unviable. Focused regional sales effort in these territories could generate quick revenue wins before expanding into new geographies.

**6. Use Seasonality for Smarter Planning**
May–June peaks and January troughs are consistent year after year. This predictability should be baked into inventory ordering, promotional calendars, and sales team target-setting — not treated as a surprise each cycle.

---

## ⚙️ How to Run This Project

**Clone the repo:**
```bash
git clone https://github.com/YOUR_USERNAME/regional-sales-optimization.git
cd regional-sales-optimization
```

**Install dependencies:**
```bash
pip install -r requirements.txt
```

**Open the notebook:**
```bash
jupyter notebook notebooks/notebook.ipynb
```

**For the dashboard:** Open `dashboard/dashboard.pbix` in Power BI Desktop

---

## 📦 Requirements

```
pandas
numpy
matplotlib
seaborn
openpyxl
jupyter
```

