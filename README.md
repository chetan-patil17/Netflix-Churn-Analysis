# 🎬 Netflix Customer Churn Analysis

An end-to-end data analysis project that dives into **why Netflix-style customers churn** 📉 — cleaning raw data, engineering new features, storing everything in a SQL database, and uncovering churn & revenue insights through SQL queries and visualizations.

---

## 🚀 Project Overview

This notebook walks through a complete analytics workflow:

1. 🧹 **Data Cleaning** — remove duplicates, fix column names, validate ranges, detect outliers
2. 🛠️ **Feature Engineering** — create age groups, activity levels, login status, revenue metrics
3. 🗄️ **Database Loading** — push the cleaned data into a local SQLite database
4. 🔍 **SQL Business Analysis** — churn & revenue breakdowns using `GROUP BY`, `CASE`, subqueries
5. 📊 **Visualization** — bar charts & correlation heatmap
6. 📈 **Summary Report** — final churn & revenue KPIs printed to console

---

## 🧰 Tech Stack & Tools

| Category | Tool / Library | Purpose |
|---|---|---|
| 🐍 Language | **Python 3** | Core language for the whole analysis |
| 📓 Environment | **Jupyter Notebook** | Interactive notebook environment |
| 🐼 Data Handling | **pandas** | Data loading, cleaning, transformation |
| 🔢 Numerical Computing | **NumPy** | Array/numeric operations |
| 📊 Visualization | **Matplotlib** | Bar charts and plots |
| 🎨 Visualization | **Seaborn** | Correlation heatmap & styled charts |
| 🗃️ Database | **SQLite3** | Lightweight relational database (via Python's built-in `sqlite3` module) |
| 🧮 Query Language | **SQL** | Aggregations, `CASE` logic, subqueries, business KPIs |
| 📁 File Format | **CSV** | Raw input dataset |

---

## 🗄️ Database & Connections

| Item | Detail |
|---|---|
| 🏷️ Database Engine | SQLite (file-based, no server required) |
| 📍 Database Path | `../database/netflix_churn.db` |
| 🔌 Connection Method | `sqlite3.connect(db_path)` (via Python's built-in `sqlite3` library) |
| 📋 Table Created | `netflix_customers` |
| 🔄 Load Method | `df_clean.to_sql("netflix_customers", conn, if_exists="replace", index=False)` |
| 🔎 Query Method | `pd.read_sql_query(query, conn)` — SQL results loaded straight into pandas DataFrames |

> 💡 No external database server, credentials, or cloud connection needed — SQLite runs locally as a single `.db` file, making the project fully self-contained and easy to run anywhere.

---

## 📂 Dataset

Expected input: `data/netflix_customer_churn.csv`

| Column | Description |
|---|---|
| 🆔 `customer_id` | Unique customer identifier |
| 🎂 `age` | Customer age |
| 🚻 `gender` | Customer gender |
| 💳 `subscription_type` | Plan (Basic / Standard / Premium) |
| 🌍 `region` | Customer's region |
| 📱 `device` | Primary streaming device |
| 💰 `payment_method` | Payment method on file |
| 🎭 `favorite_genre` | Preferred content genre |
| ⏱️ `watch_hours` | Total hours watched |
| 📺 `avg_watch_time_per_day` | Average daily watch time |
| 📅 `last_login_days` | Days since last login |
| 💵 `monthly_fee` | Monthly subscription fee |
| 👥 `number_of_profiles` | Number of profiles on account |
| ❌ `churned` | Churn flag (0 = active, 1 = churned) |

---

## 📁 Project Structure

```
.
├── 📂 data/
│   └── 📄 netflix_customer_churn.csv    # Raw input dataset
├── 📂 database/
│   └── 🗄️ netflix_churn.db              # SQLite database (auto-created)
├── 📓 netflix_churn_analysis.ipynb      # Main analysis notebook
└── 📘 README.md
```

---

## ⚙️ Requirements

- 🐍 Python 3.x
- 📓 Jupyter Notebook / JupyterLab
- 📦 Packages:
  - `pandas`
  - `numpy`
  - `matplotlib`
  - `seaborn`
  - `sqlite3` *(built into Python — no install needed)*

Install everything with:

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

---

## ▶️ How to Run

1. 📥 Clone or download this repository
2. 📂 Place the dataset at `data/netflix_customer_churn.csv`
3. 🗄️ Make sure a `database/` folder exists at the project root
4. 🚀 Launch Jupyter:
   ```bash
   jupyter notebook netflix_churn_analysis.ipynb
   ```
5. ▶️ Run all cells top to bottom

---

## ❓ Key Business Questions Explored

- 📉 What is the overall customer churn rate?
- 💳 Which subscription type churns the most?
- 🌍 Does churn vary by region, device, or payment method?
- 🎂 Do age and 🔥 activity level correlate with churn?
- 💰 How much monthly/annual revenue is at risk from churned customers?
- 🏆 Which customer segments (High/Medium/Low value) are most valuable — and most at risk?
- 🎭 Which genres are most popular, and do they churn differently?

---

## 🧪 Techniques Used

- ✅ Duplicate removal & missing value checks
- ✅ Range/validity checks (age, fees, watch hours, profile counts)
- ✅ IQR-based outlier detection
- ✅ Feature binning with `pd.cut` (age groups, activity levels, login status)
- ✅ SQL aggregations, `CASE` expressions, subqueries, filtering & sorting
- ✅ Bar charts for churn/revenue breakdowns
- ✅ Correlation heatmap for numeric features

---

## 📈 Output

A final console summary reporting:

- 👥 Total customers & churned customers
- 📉 Overall churn rate (%)
- 💵 Total monthly & annualized revenue
- ⚠️ Annualized revenue at risk
- 🏆 Subscription type with the highest churn rate


