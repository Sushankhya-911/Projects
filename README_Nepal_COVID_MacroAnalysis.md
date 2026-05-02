# 🇳🇵 Nepal COVID-19 Macro Economic Analysis

![Python](https://img.shields.io/badge/Python-3.8+-blue?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2.0+-150458?logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.7+-11557c)
![Seaborn](https://img.shields.io/badge/Seaborn-0.12+-4c72b0)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

> Analysing how the COVID-19 pandemic impacted Nepal's excess mortality
> and macroeconomic indicators — GDP and Inflation — from 2018 to 2024.

---

## 📌 Table of Contents
- [Project Overview](#-project-overview)
- [Objectives](#-objectives)
- [Datasets Used](#-datasets-used)
- [What Was Done](#-what-was-done)
- [Key Findings](#-key-findings)
- [Visualizations](#-visualizations)
- [Tech Stack](#-tech-stack)
- [How to Run](#-how-to-run)
- [About the Author](#-about-the-author)

---

## 📖 Project Overview

This project explores the real-world impact of COVID-19 on Nepal through two lenses:

1. **Epidemiological** — Estimated excess deaths per 100,000 people with 95% confidence intervals
2. **Macroeconomic** — How Nepal's GDP and Inflation behaved during and after the pandemic

The analysis connects public health data with economic indicators to answer:
> *"Why did Nepal's GDP grow even when COVID deaths were rising?"*

---

## 🎯 Objectives

| # | Objective |
|---|-----------|
| 1 | Analyse Nepal's estimated cumulative excess deaths during COVID-19 |
| 2 | Visualise uncertainty ranges in death estimates over time |
| 3 | Track Nepal's GDP trend before, during, and after the pandemic |
| 4 | Analyse Nepal's inflation rate during the COVID period |
| 5 | Connect macroeconomic trends with the pandemic timeline |
| 6 | Explain the paradox of GDP growth during a health crisis |

---

## 📊 Datasets Used

| Dataset | Source | Description |
|---------|--------|-------------|
| `estimated-cumulative-excess-deaths-per-100000-people-during-covid-19.csv` | Our World in Data | Excess deaths per 100K with 95% CI bounds |
| `Nepal_covid_span_data/Macroeconomics_Data.csv` | World Bank | GDP, GDP growth, inflation rate for Nepal |

---

## 🔧 What Was Done

### Data Loading and Filtering
- Loaded excess deaths dataset and filtered for Nepal only using boolean indexing
- Loaded macroeconomic CSV and selected relevant rows using `.iloc[]`

### Data Cleaning
- Used `.interpolate()` to fill missing values in Central estimate, Lower bound, Upper bound columns
- Converted columns to numeric using `pd.to_numeric(errors='coerce')`
- Dropped unnecessary columns (Country Name, Country Code, Series Code)

### Analysis and Visualization
- Plotted excess deaths with **95% confidence interval shading** using `plt.fill_between()`
- Plotted GDP trend over years
- Plotted Inflation rate over years
- Combined all 3 charts into a single dashboard using `plt.subplot()`

---

## 🔍 Key Findings

### 📉 Excess Deaths
- **Early 2020:** Nepal was minimally affected — excess deaths near zero
- **2020–2021:** Gradual rise in excess deaths with widening uncertainty
- **2021–2022:** Steepest rise — the Delta wave hit Nepal severely
- **2022–2024:** Death rate declined — vaccination effect visible in flattening slope
- **Mid-2024:** Pandemic impact on Nepal mortality effectively ended

### 📈 GDP Paradox
> *"Why did GDP rise even when COVID deaths spiked?"*

- Massive **healthcare spending** by government increased government purchases → raised Real GDP
- **Resource reallocation** to essential sectors maintained economic activity
- Post-lockdown **pent-up demand** increased consumption → further GDP boost

### 💰 Inflation
- **Peak inflation: ~8%** — demand outpacing supply after lockdown ended
- **Cost-push inflation:** Supply chain disruption, logistics problems raised prices
- **Demand-pull inflation:** People who saved during lockdown began spending aggressively
- The 8% peak signals economy recovering — production costs rising, unemployment falling

---

## 📈 Visualizations

| Chart | What it shows |
|-------|--------------|
| `Estimated_excess_death.png` | Cumulative excess deaths with 95% uncertainty shading |
| `GDP.png` | Nepal GDP trend 2018–2024 |
| `Inflation.png` | Nepal inflation rate during COVID span |
| Combined dashboard | All 3 charts in one figure using subplots |

---

## 🛠️ Tech Stack

| Tool | How it was used |
|------|----------------|
| Pandas | Data loading, filtering, interpolation, column operations |
| Matplotlib | Line charts, fill_between for CI, subplots dashboard |
| Seaborn | Styling and aesthetics |
| NumPy | Numeric operations |

---

## ▶️ How to Run

```bash
# 1. Clone the repo
git clone https://github.com/yourusername/nepal-covid-macroanalysis.git
cd nepal-covid-macroanalysis

# 2. Install dependencies
pip install pandas numpy matplotlib seaborn jupyter

# 3. Place datasets in correct paths:
#    - estimated-cumulative-excess-deaths-per-100000-people-during-covid-19.csv
#    - Nepal_covid_span_data/Macroeconomics_Data.csv

# 4. Launch notebook
jupyter notebook Nepal_covid_macroanalysis.ipynb
```

---

## 👤 About the Author

**BBIS Student — Kathmandu University**
- 🎓 Bachelor of Business Information Systems — 2nd Semester
- 📍 Kathmandu, Nepal
- 🔗 LinkedIn: [your-linkedin-url]
- 🐙 GitHub: [your-github-url]

### Skills demonstrated
- Real-world dataset filtering and cleaning
- Interpolation for missing values
- Confidence interval visualization
- Macroeconomic data analysis
- Multi-chart dashboard with subplots
- Connecting health data with economic indicators

---

## 💡 What I Learned
- How to use `plt.fill_between()` for uncertainty/confidence interval plots
- How to filter and reshape World Bank macroeconomic data using `.iloc[]`
- How to combine multiple charts into one dashboard using `plt.subplot()`
- How to explain real-world economic paradoxes using data

---

> *"Data doesn't just show numbers — it explains why GDP rose while people were dying.
> That's the power of connecting datasets."* 🇳🇵
