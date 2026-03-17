# Superstore-Analytics
Sales Analystics, Profitability modelling and Customer Segmentaion based RFM (Recency, Frequency and Montary) method.

Superstore Retail Analytics
An end-to-end Python data analysis project exploring sales performance, profitability, and customer behaviour using the Sample Superstore dataset.

📌 Project Overview
This project answers three core business questions using real retail transaction data:

Sales Analysis: Where is the money coming from?groupby, pivot tables, time series resampling2 

Profitability Modelling: Are discounts hurting the business?Feature engineering, pd.cut binning, scatter plots3 

Customer Segmentation: Who are the most valuable customers?RFM analysis, StandardScaler, K-Means clustering

📁 Repository Structure

superstore-analytics/

Superstore_Analytics.ipynb     # Main notebook — all 3 phases

Sample - Superstore.csv        # Dataset (place in same folder as notebook)

README.md

📊 Dataset
Source: Sample Superstore (Tableau public dataset)
Size: 9,994 rows × 21 columns
Coverage: US retail orders across 4 regions
Key columns used in this analysis:
ColumnUsed ForOrder Date, Ship DateDate parsing, Days to Ship feature derivationSegment, Region, Category, Sub-CategorySales grouping and aggregationSales, Profit, DiscountProfitability analysis, Profit Margin featureCustomer ID, Order IDRFM customer scoring

🔍 Key Findings
Sales

The Consumer segment generates the highest revenue
The West region leads all four regions in total sales
Revenue shows a clear upward trend with strong year-end spikes

Profitability

There is a clear negative relationship between discount rate and profit margin
Orders discounted above 20% are frequently loss-making
Tables and Bookcases are the most consistently unprofitable sub-categories

Customer Segmentation

Champions are only 64 customers but average $9,480 in spend — nearly 3× any other group
At Risk customers last purchased 559 days ago on average — a re-engagement campaign is warranted
Casual Customers are the largest group (335) and represent the biggest growth opportunity

🚀 How to Run

Clone the repository

bash   git clone https://github.com/your-username/superstore-analytics.git
   cd superstore-analytics

Install dependencies

bash   pip install pandas numpy matplotlib seaborn scikit-learn jupyter itables

Place Sample - Superstore.csv in the project root
Open and run the notebook

bash   jupyter notebook Superstore_Analytics.ipynb
Run all cells top to bottom via Kernel → Restart & Run All
