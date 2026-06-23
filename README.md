# Customer Behavior Analysis

## Overview
This project analyzes a retail company's consumer shopping data to uncover purchasing patterns, customer segments, and the factors that drive consumer decisions and repeat purchases. The goal is to help the business understand how it can leverage shopping data to improve customer engagement and optimize marketing and product strategies.

**Business question:** How can the company leverage consumer shopping data to identify trends, improve customer engagement, and optimize marketing and product strategies?

## Dataset
- **Source:** Public dataset — `customer_shopping_behavior.csv`
- **Key features:** Age, Gender, Category, Purchase Amount, Review Rating, Subscription Status, Payment Method, Frequency of Purchases, Discount Applied, Season, and more
- **Derived features:**
  - `age_group` — customers segmented into Young Adult / Adult / Middle-aged / Senior quartiles
  - `purchase_frequency_days` — purchase frequency labels (Weekly, Monthly, etc.) converted into numeric days for easier analysis

## Objectives
- Clean and prepare raw shopping data for analysis
- Engineer features that make customer behavior easier to segment and compare (age groups, purchase frequency in days)
- Structure the data into a database for SQL-based querying of customer segments, loyalty, and purchase drivers
- Build an interactive Power BI dashboard to visualize key trends for stakeholders
- Translate findings into actionable business recommendations

## Tools & Technologies
- **Python** (pandas) — data cleaning, transformation, feature engineering
- **MySQL Workbench** (SQLAlchemy + PyMySQL) — structured storage and querying of cleaned data
- **Power BI** — interactive dashboard and visualization
- **Jupyter Notebook** — analysis workflow

## Project Structure
```
Customer_Behavior_Analysis/
│
├── data/
│   └── customer_shopping_behavior.csv
├── notebooks/
│   └── Customer_Behavior.ipynb          # data cleaning & feature engineering
├── sql/
│   └── queries.sql                       # SQL analysis queries
├── dashboard/
│   └── Customer_Behavior_Analysis_Dashboard.pbix
├── report/
│   └── Business_Problem_Document.pdf
├── images/                               # exported dashboard screenshots
├── README.md
└── requirements.txt
```

## Data Cleaning & Preparation
Key steps performed in the notebook:
1. Loaded the raw dataset and reviewed structure with `.info()` and `.describe()`
2. Identified missing values in the `Review Rating` column and imputed them using the **median rating per product category**
3. Standardized column names to snake_case for consistency (e.g. `Purchase Amount (USD)` → `purchase_amount`)
4. Created `age_group`, a quartile-based segmentation of customer age
5. Created `purchase_frequency_days`, mapping purchase frequency labels (e.g. "Weekly", "Monthly") to numeric day values
6. Identified that `discount_applied` and `promo_code_used` were identical columns and removed the redundant `promo_code_used` column
7. Loaded the cleaned dataset into a MySQL database (managed via **MySQL Workbench**) for structured querying

## How to Run
```bash
git clone https://github.com/Sakshi0523/Customer_Behavior_Analysis.git
cd Customer_Behavior_Analysis
pip install -r requirements.txt
jupyter notebook notebooks/Customer_Behavior.ipynb
```

To explore the dashboard, open `dashboard/Customer_Behavior_Analysis_Dashboard.pbix` in [Power BI Desktop](https://www.microsoft.com/en-us/power-platform/products/power-bi/downloads).

## Key Findings
*(Fill in once your SQL analysis and dashboard are finalized — these are the most important takeaways for stakeholders)*
- Finding 1 — e.g. which customer segment drives the most revenue
- Finding 2 — e.g. impact of discounts/promo codes on repeat purchases
- Finding 3 — e.g. seasonal or category-level purchasing trends

## Results / Visualizations
*(Add 2-3 screenshots of your Power BI dashboard here once exported as images)*

## Project Deliverables
- [x] Data cleaning & feature engineering (Python)
- [x] Structured data storage (MySQL)
- [ ] SQL analysis queries
- [x] Interactive Power BI dashboard
- [ ] Final report and presentation

## Author
Sakshi — [GitHub](https://github.com/Sakshi0523)
