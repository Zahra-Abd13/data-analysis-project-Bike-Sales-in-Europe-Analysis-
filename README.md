 🚲 Bike Sales in Europe — Exploratory Data Analysis

![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2.x-150458?logo=pandas&logoColor=white)
![Plotly](https://img.shields.io/badge/Plotly-Interactive-3F4F75?logo=plotly&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)
![Status](https://img.shields.io/badge/Status-Complete-2ea44f)

> End-to-end exploratory data analysis of European bike retail sales — uncovering revenue trends, customer demographics, product profitability, and the hidden cost of discounting.

---

## 📌 Project Description

This project analyses a global bike sales dataset, filtered to three European markets — **Germany**, **France**, and the **United Kingdom** — covering transactions from 2011 to 2016.

The analysis follows a full EDA pipeline: data loading, cleaning, feature engineering, outlier handling, and multi-angle business analysis across five dimensions — sales performance, customer demographics, geography, time series, and discounting behaviour.

All visualisations are built with **Plotly** and are fully interactive when run in Jupyter.

---

## 🗂️ Repository Structure

```
├── Bike_Sales_Europe_Analysis_Improved.ipynb   # Main analysis notebook
├── sales.csv                                    # Source dataset (18 columns)
├── requirements.txt                             # Python dependencies
└── README.md                                    # This file
```

---

## 🔑 Key Questions Answered

| # | Business Question |
|---|-------------------|
| 1 | What are the total sales and profit margins across European markets? |
| 2 | Which products, sub-categories, and categories drive the most revenue? |
| 3 | Who are the core customers — by age group and gender? |
| 4 | How do sales trend over time, by year and by month? |
| 5 | What is the real impact of discounting on profit? |

---

## 📊 Key Findings

| Finding | Detail |
|---------|--------|
| 🇬🇧 **UK dominates** | The United Kingdom accounts for ~52% of total European revenue, outperforming Germany and France in every year analysed |
| 🚵 **Bikes lead revenue** | The Bikes category drives the highest sales value; Accessories lead in order volume |
| 👥 **Core customer: Adults 35–64** | This age segment accounts for the largest share of orders and revenue across all three markets |
| 💸 **97% of orders are discounted** | Unit Price is a list price — nearly all transactions include a pricing adjustment, making effective margin management critical |
| 📉 **Two loss-making SKUs** | *AWC Logo Cap* and *Short-Sleeve Classic Jersey* generate negative profit due to cost-price parity |
| 📅 **Strong seasonal peaks** | June and November consistently outperform — clear signals for inventory and campaign planning |

---

## 🧹 Data Cleaning Steps

- Removed exact duplicate rows (identified as data entry errors)
- Filtered dataset to European countries only (Germany, France, United Kingdom)
- Converted `Date` column to `datetime` format
- Verified and documented revenue calculation discrepancies (discount engineering)
- Consolidated product variants with identical unit cost/price into single product names
- Detected and capped profit outliers using the Tukey IQR method; flagged rows retained via `is_outlier` column

---

## 🛠️ Tech Stack

| Library | Purpose |
|---------|---------|
| `pandas` | Data loading, wrangling, aggregation |
| `numpy` | Numerical operations |
| `plotly.express` / `plotly.graph_objects` | Interactive charts and annotations |
| `matplotlib` | Supporting static plots |
| `seaborn` | Statistical visualisation |

---

## ▶️ How to Run

**1. Clone the repository**
```bash
git clone https://github.com/Zahra-Abd13/bike-sales-europe-eda.git
cd bike-sales-europe-eda
```

**2. Install dependencies**
```bash
pip install -r requirements.txt
```

Or manually:
```bash
pip install pandas numpy plotly matplotlib seaborn jupyter
```

**3. Launch the notebook**
```bash
jupyter notebook Bike_Sales_Europe_Analysis_Improved.ipynb
```

> ⚠️ Make sure `sales.csv` is in the same directory as the notebook before running all cells.

---

## 📈 Visualisations Included

The notebook contains **15+ fully interactive Plotly charts**, including:

- Total Sales vs Profit overview bar chart with profit margin annotation
- Top 10 best-selling products (horizontal bar, sorted)
- Sales breakdown by product category and sub-category
- Customer distribution by age group
- Sales by country and top-performing state per country
- Year-over-year and month-by-month sales trend
- Profit distribution before and after outlier capping (box plots)
- Sales and profit by discount amount band

---

## 💡 Business Recommendations

1. **Fix loss-making products** — Raise unit prices on *AWC Logo Cap* and *Short-Sleeve Classic Jersey*, or discontinue if margin recovery is not feasible.
2. **Leverage seasonal peaks** — Align inventory build-up and marketing campaigns with the high-demand months (June, November) identified in the time series analysis.
3. **Rethink the discount strategy** — With ~97% of transactions discounted, introduce targeted discounting by customer segment, region, or product category to protect margins without sacrificing volume.
4. **Double down on the UK market** — The UK's outsized contribution suggests room to deepen penetration further before scaling investment in Germany and France.

---

## 📄 Dataset

- **Source:** Global bike retail sales (publicly available on Kaggle)
- **Scope after filtering:** 3 European countries across multiple years
- **Original columns (18):** `Date`, `Year`, `Month`, `Customer_Age`, `Age_Group`, `Customer_Gender`, `Country`, `State`, `Product_Category`, `Sub_Category`, `Product`, `Order_Quantity`, `Unit_Cost`, `Unit_Price`, `Revenue`, `Cost`, `Profit`
- **Engineered columns:** `Sales` (list price × qty), `discount` (revenue adjustment), `Base_Product`, `is_outlier`

---

## 📜 License

This project is open source under the [MIT License](LICENSE).
.
