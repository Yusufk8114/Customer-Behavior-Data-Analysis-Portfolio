# Customer-Behavior-Data-Analysis-Portfolio
# Customer Shopping Behavior Analysis

An end-to-end data analytics project covering data cleaning, exploratory analysis, SQL-based business querying, and dashboard/report creation — built to answer real customer and revenue questions from a retail shopping dataset.

## Overview

This project analyzes customer shopping behavior to uncover insights around revenue, discounts, subscriptions, product performance, and customer segmentation. It follows a complete analytics workflow: starting from raw data in Python, cleaning and transforming it, loading it into a relational database for SQL analysis, and finally presenting findings through an interactive Power BI dashboard, a written report, and a presentation deck.

**Key business questions answered:**
- How does revenue differ between male and female customers?
- Do discounts and subscriptions actually drive higher spending?
- Which products and categories perform best?
- How can customers be segmented into New, Returning, and Loyal groups?
- Which age groups and shipping types contribute most to revenue?

## Dataset

- **File:** `customer_shopping_behavior.csv`
- **Contents:** Customer-level shopping transaction data including demographics, purchase details, and behavioral attributes such as:
  - `age`, `gender`, `item_purchased`, `category`, `purchase_amount`
  - `review_rating`, `subscription_status`, `discount_applied`, `promo_code_used`
  - `shipping_type`, `previous_purchases`, `frequency_of_purchases`
- **Derived fields created during cleaning:**
  - `age_group` — customers segmented into Young Adult, Adult, Middle-aged, and Senior using quartile binning
  - `purchase_frequency_days` — purchase frequency labels (Weekly, Monthly, etc.) converted into numeric day intervals

## Tools & Technologies

| Category | Tools |
|---|---|
| Data Handling & EDA | Python, Pandas |
| Database | PostgreSQL / MySQL / SQL Server |
| DB Connectivity | SQLAlchemy, psycopg2 |
| Querying | SQL (aggregations, CTEs, window functions) |
| Visualization | Power BI |
| Reporting | Microsoft Word |
| Presentation | Gamma (AI-assisted PPT generation) |

## Project Workflow

1. **Data Loading** — Imported the raw CSV dataset into Python using Pandas.
2. **Exploratory Data Analysis (EDA)** — Reviewed data structure, summary statistics, and value distributions using `.info()` and `.describe()`.
3. **Data Cleaning & Transformation**
   - Checked for and imputed missing values (e.g., `review_rating` filled using category-wise median)
   - Standardized column names to snake_case for consistency
   - Engineered new features: `age_group`, `purchase_frequency_days`
   - Removed redundant columns (e.g., `promo_code_used`, which duplicated `discount_applied`)
4. **Database Loading** — Connected Python to PostgreSQL using SQLAlchemy and loaded the cleaned dataset into a database table for SQL-based analysis.
5. **SQL Analysis** — Wrote and executed business-focused SQL queries covering revenue breakdowns, discount behavior, product performance, customer segmentation, and subscription trends (see `Customer_Behavior.sql`).
6. **Dashboard Development** — Built an interactive Power BI dashboard to visualize key metrics and trends for stakeholders.
7. **Reporting** — Summarized findings and business recommendations in a formal Word document.
8. **Presentation** — Created a stakeholder-ready PPT summarizing the project and key insights using Gamma.

## SQL Analysis Highlights

The SQL script (`Customer_Behavior.sql`) answers 10 business questions, including:

- Revenue by gender
- Customers who spent above average despite using a discount
- Top 5 products by average review rating
- Standard vs. Express shipping — average purchase comparison
- Subscriber vs. non-subscriber spending comparison
- Products with the highest discount usage
- Customer segmentation (New / Returning / Loyal) based on purchase history
- Top 3 most purchased products per category
- Repeat buyer subscription likelihood
- Revenue contribution by age group

## Dashboard

The Power BI dashboard (`Customer_Behavior_Dashboard.pbix`) brings the analysis to life with interactive visuals, including:
- Revenue breakdown by gender, age group, and category
- Subscription vs. non-subscription spending comparison
- Discount usage trends across top products
- Customer segmentation view (New / Returning / Loyal)
- Filters/slicers for dynamic, self-service exploration

## Results & Key Insights

- Clear differences observed in spending patterns between subscribed and non-subscribed customers
- Certain product categories consistently drive higher revenue and review ratings
- A meaningful share of customers use discounts while still spending above average, indicating discounts aren't purely price-driven behavior
- Customer segmentation reveals actionable groups (New, Returning, Loyal) for targeted marketing
- Age group and shipping type analysis highlight where revenue is concentrated

*(Full detailed findings and recommendations are available in the project report.)*

## Project Files

| File | Description |
|---|---|
| `Customer_Shopping_Behavior_Analysis.ipynb` | Python notebook — data loading, EDA, cleaning, and database connection |
| `Customer_Behavior.sql` | SQL script with 10 business analysis queries |
| `Customer_Behavior_Dashboard.pbix` | Power BI dashboard file |
| `Customer_Shopping_Behavior_Analysis.docx` | Written analysis report |
| `Customer_Shopping_Behavior_Analysis.pptx` | Presentation deck (built with Gamma) |

## How to Run

1. **Clone/download the project files** to your local machine.
2. **Set up the Python environment:**
   ```bash
   pip install pandas sqlalchemy psycopg2-binary
   ```
3. **Run the notebook** (`Customer_Shopping_Behavior_Analysis.ipynb`) to load, clean, and prepare the dataset.
4. **Load data into your database** (PostgreSQL / MySQL / SQL Server) using the provided SQLAlchemy connection code, updating credentials as needed.
5. **Run the SQL queries** in `Customer_Behavior.sql` against your database to reproduce the analysis.
6. **Open the dashboard** — Launch `Customer_Behavior_Dashboard.pbix` in Power BI Desktop and refresh the data connection to your database.
7. **Review the report and presentation** — Open the `.docx` report and `.pptx` deck for a summarized view of findings.


*This project demonstrates an end-to-end analytics workflow — from raw data to business-ready insights — using Python, SQL, and Power BI.*
