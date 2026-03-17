# Superstore-Analytics
Sales Analystics, Profitability modelling and Customer Segmentaion based RFM (Recency, Frequency and Montary) method.

# Superstore Retail Analytics 🛒

> *64 customers. $9,480 average spend. Nearly 3× everyone else.*  
> *This is what the data revealed — and how I found it.*

An end-to-end Python data analysis project that goes beyond surface-level charts to uncover **what's actually driving revenue, what's silently killing profit, and who the business cannot afford to lose.**

---

## The Business Problem

Retail businesses sit on mountains of transaction data but rarely ask the right questions. This project picks three that matter most:

| # | Question | Why It Matters |
|---|---|---|
| 1 | Where is the money coming from? | Knowing your best segment and region tells you where to double down |
| 2 | Are discounts hurting the business? | Discounts feel like growth — the data tells a different story |
| 3 | Who are the most valuable customers? | 8% of customers drive a disproportionate share of revenue |

---

## Key Findings

### 💰 Sales
- The **Consumer segment** generates the highest revenue, followed by Corporate and Home Office
- The **West region** outperforms all others — a potential model for underperforming regions
- Revenue trends **upward year-on-year**, with a consistent Q4 spike driven by seasonal demand

### 📉 Profitability — the discount problem
- There is a **clear negative relationship** between discount rate and profit margin
- Transactions discounted above **20% are frequently loss-making** — the business is paying customers to buy
- **Tables and Bookcases** are the most consistently unprofitable sub-categories regardless of discount

### 👥 Customer Segmentation — the hidden 8%

| Segment | Customers | Avg Days Since Purchase | Avg Orders | Avg Spend |
|---|---|---|---|---|
| 🏆 Champions | 64 | 124 days | 8 | **$9,480** |
| 💚 Loyal Customers | 298 | 73 days | 9 | $3,322 |
| 🔵 Casual Customers | 335 | 101 days | 5 | $1,670 |
| 🔴 At Risk | 96 | 559 days | 4 | $1,470 |

**Champions** represent just 8% of the customer base but spend nearly **3× more than any other group.**  
**At Risk** customers haven't purchased in over **1.5 years** — without intervention, they're gone.

---

## Project Structure

```
superstore-analytics/
│
├── Superstore_Analytics.ipynb   ← Main notebook — all 3 phases, fully documented
├── Sample - Superstore.csv      ← Raw dataset (9,994 rows × 21 columns)
└── README.md
```

---

## Methodology

### Phase 1 — Sales Analysis
Aggregated revenue by segment, region, and time using `groupby` and `resample`. A pivot table cross-tabulates segment × category to reveal which combinations drive the most value.

### Phase 2 — Profitability Modelling
Engineered a `Profit Margin` feature (profit ÷ sales) to normalise across transaction sizes. Used `pd.cut` to bin discount rates into four bands and compared average profit across bands — turning a scatter plot observation into a quantified business finding.

### Phase 3 — Customer Segmentation (RFM + K-Means)
Scored every customer on **Recency, Frequency, and Monetary** value — a well-established retail framework. Applied `StandardScaler` before clustering to prevent high-value monetary figures from dominating the distance calculations. Selected **k=4** using the elbow method, then profiled each cluster before assigning labels — the groups are data-driven, not assumed.

---

## Dataset

**Source:** [Sample Superstore — Tableau Public](https://community.tableau.com/)  
**Size:** 9,994 rows × 21 columns  
**Coverage:** US retail orders across 4 regions (West, East, Central, South)

| Column | Role in Analysis |
|---|---|
| `Order Date`, `Ship Date` | Date parsing · `Days to Ship` derivation |
| `Segment`, `Region`, `Category`, `Sub-Category` | Grouping and aggregation |
| `Sales`, `Profit`, `Discount` | Profitability analysis · `Profit Margin` feature |
| `Customer ID`, `Order ID` | RFM scoring (unique customers · unique orders) |

---

## Tools & Libraries

| Library | Purpose |
|---|---|
| `pandas` | Data loading, cleaning, groupby, pivot tables, resampling |
| `numpy` | Numerical operations |
| `matplotlib` + `seaborn` | All visualisations |
| `scikit-learn` | StandardScaler · KMeans clustering |
| `itables` | Interactive table display in notebook |

---

## How to Run

```bash
# 1. Clone the repo
git clone https://github.com/Oyiwoche/Superstore-Analytics.git
cd Superstore-Analytics

# 2. Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn jupyter itables

# 3. Launch the notebook
jupyter notebook Superstore_Analytics.ipynb
```

> Place `Sample - Superstore.csv` in the same folder as the notebook before running.  
> Use `Kernel → Restart & Run All` to execute all cells cleanly from top to bottom.



*If this project was useful or interesting, a ⭐ on the repo goes a long way.*
