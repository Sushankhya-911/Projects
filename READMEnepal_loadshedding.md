
# ⚡ Nepal Load Shedding Analysis (2012–2023)

![Python](https://img.shields.io/badge/Python-3.8+-blue?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2.0+-150458?logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-1.24+-013243?logo=numpy&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.7+-11557c)
![Seaborn](https://img.shields.io/badge/Seaborn-0.12+-4c72b0)
![Status](https://img.shields.io/badge/Status-In%20Progress-orange)

> Analysing Nepal's historical load shedding patterns from 2012 to 2023
> across 10 districts, 7 NEA groups, and 4 seasons —
> built independently by a 2nd semester BBIS student at Kathmandu University.

---

## 📌 Table of Contents
- [Project Overview](#-project-overview)
- [Objectives](#-objectives)
- [Dataset](#-dataset)
- [What Was Done](#-what-was-done)
- [Project Structure](#-project-structure)
- [Tech Stack](#-tech-stack)
- [How to Run](#-how-to-run)
- [Upcoming Analysis](#-upcoming-analysis)
- [About the Author](#-about-the-author)

---

## 📖 Project Overview

Nepal faced one of South Asia's worst electricity crises between 2012 and 2016,
with some areas losing power for **14–16 hours per day**.

This project independently analyses load shedding patterns across Nepal's
districts, NEA groups and seasons — and tracks Nepal's remarkable recovery
from crisis to near-zero load shedding by 2023.


---

## 🎯 Objectives

| # | Objective |
|---|-----------|
| 1 | Load and explore the Nepal load shedding dataset |
| 2 | Extract and analyse unique districts, NEA groups, years and seasons |
| 3 | Apply correct month ordering using Pandas Categorical |
| 4 | Split data by year for year-wise analysis |
| 5 | Analyse load shedding trends across time, districts and seasons |
| 6 | Quantify economic impact on households and businesses |

---

## 📊 Dataset

| Property | Details |
|----------|---------|
| File | `nepal_loadshedding_2012_2023.csv` |
| Rows | 10,080 |
| Columns | 15 |
| Years | 2012–2023 |
| Districts | Kathmandu, Lalitpur, Bhaktapur, Pokhara, Chitwan, Biratnagar, Birgunj, Butwal, Dharan, Hetauda |
| NEA Groups | Group 1 – Group 7 |

### Column Description

| Column | Description |
|--------|-------------|
| `year` | Year (2012–2023) |
| `month` | Month number (1–12) |
| `month_name` | Month name — set as ordered Categorical |
| `season` | Season (Winter/Spring/Summer/Monsoon/Autumn) |
| `group` | NEA load shedding group (Group 1–7) |
| `district` | District name |
| `population` | District population |
| `num_businesses` | Number of businesses in district |
| `daily_hours` | Average daily load shedding hours |
| `weekly_hours` | Average weekly load shedding hours |
| `monthly_hours` | Average monthly load shedding hours |
| `household_loss_npr` | Monthly loss per household (NPR) |
| `business_loss_npr` | Monthly loss per business (NPR) |
| `total_household_loss_npr` | District-wide monthly household loss (NPR) |
| `total_business_loss_npr` | District-wide monthly business loss (NPR) |

---

## 🔧 What Was Done

### ✅ Completed Steps

**1. Library Setup**
```python
import pandas as pd
import matplotlib as pyplot
import seaborn as sns
import numpy as np
```

**2. Data Loading and Inspection**
- Loaded CSV with `pd.read_csv()`
- Inspected structure with `.info()`
- Checked for null values with `.isna()`

**3. Unique Value Extraction**
```python
district = data["district"].unique()   # 10 districts
grp      = data["group"].unique()      # 7 NEA groups
year     = data["year"].unique()       # 2012–2023
seasons  = data["season"].unique()    # 4 seasons
```

**4. Month Ordering — Pandas Categorical**
```python
month_order = ['January', 'February', ..., 'December']
data["month_name"] = pd.Categorical(
    data["month_name"], categories=month_order, ordered=True
)
```
> This ensures months sort correctly in charts (Jan→Dec) instead of alphabetically.
> Smart use of `pd.Categorical` — not something most beginners think to do.

**5. Year-wise Data Splitting**
```python
yearly_datasets = {}
for yr in year:
    yearly_datasets[yr] = data[data["year"] == yr].copy()
```
> Created a dictionary of DataFrames — one per year — for year-specific analysis.

---

## 📁 Project Structure

```
nepal-loadshedding-analysis/
│
├── data/
│   └── nepal_loadshedding_2012_2023.csv
│
├── notebooks/
│   └── Loadshedding_analysis.ipynb
│
├── outputs/
│   └── (charts will go here)
│
└── README.md
```

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| Python 3.8+ | Core language |
| Pandas | Data loading, filtering, Categorical ordering |
| NumPy | Numerical operations |
| Matplotlib | Visualization |
| Seaborn | Statistical charts |

---

## ▶️ How to Run

```bash
# 1. Clone the repository
git clone https://github.com/yourusername/nepal-loadshedding-analysis.git
cd nepal-loadshedding-analysis

# 2. Install dependencies
pip install pandas numpy matplotlib seaborn jupyter

# 3. Launch notebook
jupyter notebook notebooks/Loadshedding_analysis.ipynb
```

---

## 🔜 Upcoming Analysis

The following steps are planned to complete the project:

- [ ] Yearly trend bar chart (2012–2023)
- [ ] District × Year heatmap
- [ ] Seasonal pattern analysis
- [ ] NEA group comparison
- [ ] Economic impact — NPR loss for households and businesses
- [ ] Nepal's electricity recovery story — line chart

---


### Skills demonstrated
- Independent data loading and exploration
- Correct use of `pd.Categorical` for ordered month sorting
- Year-wise data segmentation using dictionary comprehension
- Null value detection and data inspection

---

## 💡 What I Learned
- How to use `pd.Categorical` to enforce correct ordering in time data
- How to split a DataFrame into year-wise segments using a loop
- How to extract unique categories for analysis dimensions
- Why `.copy()` matters when slicing DataFrames — avoids modifying original data

---
