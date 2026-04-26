# 🛍️ Customer Shopping Behavior Analysis

A comprehensive end-to-end data analysis project exploring customer shopping patterns, spending habits, and product preferences across 3,900 transactions — using Python, PostgreSQL, and Power BI.

---

## 📌 Project Overview

This project uncovers actionable insights into:
- Customer spending patterns and segment behavior
- Product preferences and top-rated items
- Subscription trends and their revenue impact
- Discount dependency across product lines
- Revenue distribution by gender, age group, and shipping type

---

## 🗂️ Dataset

| Property | Details |
|---|---|
| Total Records | 3,900 transactions |
| Columns | 18 features |
| Missing Data | 37 values in `Review Rating` (imputed) |

**Key Features:**
- **Demographics** — Age, Gender, Location, Subscription Status
- **Purchase Details** — Item, Category, Amount (USD), Season, Size, Color
- **Behavior** — Discount Applied, Previous Purchases, Purchase Frequency, Review Rating, Shipping Type

---

## 🛠️ Tech Stack

| Layer | Tool |
|---|---|
| Data Cleaning & EDA | Python (pandas) |
| Database | PostgreSQL |
| Visualization | Power BI |

---

## 🔄 Workflow

### 1. Data Preparation (Python)
- Loaded dataset with `pandas`
- Explored structure with `df.info()` and `.describe()`
- Imputed missing `Review Rating` values using **median per product category**
- Renamed columns to `snake_case` for consistency
- **Feature Engineering:**
  - `age_group` — binned customer ages into segments
  - `purchase_frequency_days` — derived from purchase history
- Dropped redundant `promo_code_used` column (correlated with `discount_applied`)
- Loaded cleaned DataFrame into PostgreSQL

### 2. SQL Analysis (PostgreSQL)

Ten business questions were answered using structured queries:

| # | Analysis |
|---|---|
| 1 | Revenue by Gender |
| 2 | High-Spending Discount Users |
| 3 | Top 5 Products by Average Rating |
| 4 | Shipping Type vs. Avg Purchase Amount |
| 5 | Subscribers vs. Non-Subscribers |
| 6 | Most Discount-Dependent Products |
| 7 | Customer Segmentation (New / Returning / Loyal) |
| 8 | Top 3 Products per Category |
| 9 | Repeat Buyers & Subscription Likelihood |
| 10 | Revenue by Age Group |

### 3. Power BI Dashboard
An interactive dashboard with slicers for Subscription Status, Gender, Category, and Shipping Type, displaying:
- KPI cards: Total Customers, Avg Purchase Amount, Avg Review Rating
- Revenue & Sales by Category and Age Group
- Subscription breakdown (donut chart)

---

## 📊 Key Findings

- **Male customers** generated nearly **2× the revenue** of female customers ($157,890 vs $75,191)
- **839 discount users** still spent above the average purchase amount — they're high-value even with discounts
- **Top-rated products:** Gloves (3.86), Sandals (3.84), Boots (3.82), Hat (3.80), Skirt (3.78)
- **Express shipping** users spend slightly more on average ($60.48) than Standard ($58.46)
- **Subscribers** (27% of customers) have comparable avg spend to non-subscribers (~$59.49 vs $59.87)
- **Hat, Sneakers, and Coat** have the highest discount dependency (≈50% of purchases discounted)
- **80% of customers** are in the Loyal segment (3,116 out of 3,900)
- **Young Adults** are the top revenue-generating age group ($62,143), followed by Middle-aged ($59,197)

---

## 💡 Business Recommendations

1. **Boost Subscriptions** — Only 27% of customers subscribe; promote exclusive member benefits to grow this segment
2. **Loyalty Programs** — Reward repeat buyers to solidify Loyal customer retention
3. **Review Discount Policy** — Products like Hat and Sneakers have ~50% discount rates; assess margin impact
4. **Product Positioning** — Feature top-rated items (Gloves, Sandals, Boots) prominently in marketing campaigns
5. **Targeted Marketing** — Prioritize Young Adults and Express-shipping users, who show higher spending

---

## 📁 Project Structure

```
customer-shopping-behavior-analysis/
│
├── data/
│   └── shopping_behavior.csv          # Raw dataset
│
├── notebooks/
│   └── eda_cleaning.ipynb             # Python EDA & data cleaning
│
├── sql/
│   ├── revenue_by_gender.sql
│   ├── top_products_by_rating.sql
│   ├── customer_segmentation.sql
│   └── ...                            # All 10 SQL queries
│
├── dashboard/
│   └── customer_behavior.pbix         # Power BI dashboard file
│
└── README.md
```

---

## 🚀 Getting Started

### Prerequisites
```bash
pip install pandas psycopg2 sqlalchemy
```

### Run the Python Script
```bash
jupyter notebook notebooks/eda_cleaning.ipynb
```

### Load Data into PostgreSQL
The notebook handles the connection and data loading automatically via `sqlalchemy`. Update the connection string in the notebook:
```python
engine = create_engine("postgresql://user:password@localhost:5432/shopping_db")
```

### SQL Queries
Run individual `.sql` files from the `sql/` folder in pgAdmin or any PostgreSQL client.

---

## 📬 Contact

**Akshaya Vallabhaneni**
- 📧 Email: akshayavallabhaneni68@gmail.com
- 💼 LinkedIn: [linkedin.com/in/akshaya-vallabhaneni-615056320](https://www.linkedin.com/in/akshaya-vallabhaneni-615056320)
- 🐙 GitHub: [github.com/akshayavallabhaneni68-lab](https://github.com/akshayavallabhaneni68-lab)

