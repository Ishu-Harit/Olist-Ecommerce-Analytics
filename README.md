# Olist E-Commerce Analytics Dashboard

An end-to-end data analytics project analyzing 100,000+ orders from Brazil's largest e-commerce platform using Python, SQL, MySQL, and Power BI.

---

## Project Overview

This project answers key business questions about Olist's operations:
- Which states and product categories drive the most revenue?
- How does delivery performance impact customer satisfaction?
- What are the payment preferences of customers?
- How has the business grown month over month?

---

## Tools & Technologies

| Tool | Purpose |
|---|---|
| Python (Pandas) | Data cleaning and feature engineering |
| MySQL | Data storage and SQL analysis |
| Power BI | Interactive dashboard |
| Jupyter Notebook | Development environment |

---

## Dataset

- **Source:** [Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)
- **Size:** 100,000+ orders across 9 CSV files
- **Period:** 2016 - 2018

---

## Data Cleaning (Python)

- Converted 5 date columns from text to datetime format
- Engineered `delivery_days` column (delivered date - purchase date)
- Created `is_late` flag comparing actual vs estimated delivery
- Translated 70+ product categories from Portuguese to English
- Aggregated multi-item orders into single rows
- Merged 8 tables into one master table of 96,469 delivered orders
- Exported 5 clean tables to MySQL database

---

## SQL Analysis

Written in MySQL covering 3 complexity levels:

**Basic**
- Total revenue, orders, average order value
- Monthly revenue trend
- Revenue by state and product category

**Intermediate**
- Average delivery days by state
- Late delivery percentage
- Repeat customer rate (only 3% ever reordered)
- Payment method analysis

**Advanced (Window Functions)**
- Month over month revenue growth using LAG()
- Top category per state using RANK() OVER (PARTITION BY)
- Cumulative revenue using SUM() OVER()

---

## Key Insights

1. **R$15.4M total revenue** across 96,469 delivered orders (2016-2018)
2. **SP state dominates** — 42% of all orders, R$5.7M revenue
3. **Health Beauty is #1 category** — R$1.23M revenue, 4.16 avg review score
4. **Late deliveries cause 41% drop in review scores** — 4.27 (on time) vs 2.51 (late)
5. **97% of customers never reordered** — major retention problem
6. **Credit card = 75% of payments** — avg order value 15% higher than other methods
7. **November 2017 Black Friday spike** — 53% revenue jump, biggest single month growth

---

## Business Recommendations

1. **Prioritize logistics in high-latency states** — PA, AM, RR average 23-27 day delivery and have lowest review scores. Warehouse expansion needed.
2. **Launch a loyalty program** — 97% one-time customer rate signals poor retention. Cohort data shows drop-off after 60 days.
3. **Investigate Office Furniture category** — lowest review score (3.48) despite decent revenue. Likely packaging damage during delivery.

---

## Dashboard Preview

[View Dashboard PDF](Olist_Dashboard.pdf)

---

## Project Structure

- `olist_cleaning.ipynb` — Python data cleaning and feature engineering
- `olist_analysis.ipynb` — SQL analysis queries
- `Olist_Dashboard.pbix` — Power BI dashboard file
- `dashboard_preview.png` — Dashboard screenshot
- `README.md` — Project documentation

---

## How to Run

1. Download dataset from Kaggle (link above)
2. Open `olist_cleaning.ipynb` in Jupyter Notebook and run all cells
3. Ensure MySQL is running locally on port 3306
4. The notebook automatically loads cleaned data into MySQL
5. Open `Olist_Dashboard.pdf` to view the dashboard
6. To interact with the dashboard, open `Olist_Dashboard.pbix` in Power BI Desktop and reconnect to your local MySQL instance
