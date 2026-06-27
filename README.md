# Customer Behavior Analysis

Analyzing retail customer shopping data to uncover purchasing patterns, customer segments, and the factors that drive consumer decisions and repeat purchases.

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
│   └── Customer_behavior.sql            # SQL analysis queries
├── dashboard/
│   └── Customer_Behavior_Analysis_Dashboard.pbix
├── report/
│   ├── Business_Problem_Document.pdf
│   └── Customer_Behavior_Analysis.pdf
├── presentation/
│   └── Customer-Behavior-Analysis.pptx
├── images/                               # exported dashboard screenshots
├── README.md
├── requirements.txt
└── LICENSE
```

> **Note:** if you're updating the live repo to match this structure, move each file into its folder and update any relative paths in the notebook/SQL file accordingly.

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

<!-- TODO: Replace with your actual findings before publishing.
     Pull these directly from your SQL queries / dashboard — use real numbers, not estimates. -->

- **Finding 1:** _e.g. "Customers aged 26–35 account for X% of total revenue despite making up Y% of the customer base."_
- **Finding 2:** _e.g. "Customers with an active subscription have a repeat-purchase rate of X%, compared to Y% for non-subscribers."_
- **Finding 3:** _e.g. "The [category] category sees the highest discount usage at X%, but the lowest average review rating."_
- **Finding 4:** _e.g. "[Season] shows a clear spike in purchase frequency for [category], suggesting a seasonal marketing opportunity."_

## Results / Visualizations

<!-- TODO: Export 2-3 screenshots from your Power BI dashboard as PNGs,
     save them to the images/ folder, and reference them below. -->

![Dashboard Overview](images/dashboard_overview.png)
*Overview of customer segments and purchase trends*

![Revenue by Segment](images/revenue_by_segment.png)
*Revenue breakdown by age group and category*

## Project Deliverables

- [x] Data cleaning & feature engineering (Python)
- [x] Structured data storage (MySQL)
- [x] SQL analysis queries
- [x] Interactive Power BI dashboard
- [x] Final report and presentation

## Author

Sakshi — [GitHub](https://github.com/Sakshi0523)

## License

This project is licensed under the MIT License — see [LICENSE](LICENSE) for details.
