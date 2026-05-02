# 📱 Teen Social Media Usage & Mental Health Analysis

![Python](https://img.shields.io/badge/Python-3.8+-blue?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2.0+-150458?logo=pandas&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/ScikitLearn-1.3+-F7931E?logo=scikit-learn&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.7+-11557c)
![Seaborn](https://img.shields.io/badge/Seaborn-0.12+-4c72b0)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

> Exploring how teen social media usage patterns relate to mental health outcomes
> — depression risk, stress, anxiety and academic performance —
> using EDA, encoding, correlation analysis and Random Forest classification.

---

## 📌 Table of Contents
- [Project Overview](#-project-overview)
- [Objectives](#-objectives)
- [Dataset](#-dataset)
- [What Was Done](#-what-was-done)
- [Key Findings](#-key-findings)
- [Model Performance](#-model-performance)
- [Tech Stack](#-tech-stack)
- [How to Run](#-how-to-run)
- [About the Author](#-about-the-author)

---

## 📖 Project Overview

Social media has become central to teenage life — but what does the data say
about its relationship with mental health?

This project uses a teen mental health dataset to:
- Explore distributions of depression risk, stress, anxiety and platform usage
- Identify correlations between social media behaviour and mental health indicators
- Build a **Random Forest classifier** to predict depression risk
- Identify the most important predictors of mental health outcomes

---

## 🎯 Objectives

| # | Objective |
|---|-----------|
| 1 | Perform EDA on categorical and numerical variables |
| 2 | Apply label encoding for ordinal variables (depression risk, social interaction level) |
| 3 | Apply one-hot encoding for nominal variables (gender, platform usage) |
| 4 | Analyse correlation between all features using a heatmap |
| 5 | Explore relationships: stress vs anxiety, screen time vs academic performance |
| 6 | Build a Random Forest classifier to predict depression risk |
| 7 | Identify the most important features driving depression risk |

---

## 📊 Dataset

| Property | Details |
|----------|---------|
| File | `Teen_Mental_Health_Dataset.csv` |
| Target variable | `depression_risk` (low / medium / high) |
| Key features | gender, platform_usage, screen_time_before_sleep, stress_level, anxiety_level, academic_performance, social_interaction_level |

---

## 🔧 What Was Done

### 1. Data Loading and Inspection
- Loaded CSV with `pd.read_csv()`
- Checked structure with `.info()`, `.isnull().sum()`, `.describe()`

### 2. Exploratory Data Analysis (EDA)
- **Categorical EDA:** countplots for gender, platform_usage, social_interaction_level, depression_risk
- **Numerical EDA:** histograms for all numeric columns using a loop

### 3. Encoding
- **Label encoding** (ordinal): mapped low→0, medium→1, high→2 for depression_risk and social_interaction_level using `.map()`
- **One-hot encoding** (nominal): used `pd.get_dummies()` for gender and platform_usage
- Converted boolean dummy columns to int using `.astype(int)`

### 4. Correlation Analysis
- Built full correlation matrix using `.corr(numeric_only=True)`
- Visualised with `sns.heatmap()` with annotations

### 5. Scatter Plot Analysis
- stress_level vs anxiety_level
- screen_time_before_sleep vs academic_performance

### 6. Machine Learning — Random Forest
- Split data: 80% train, 20% test using `train_test_split(random_state=42)`
- Trained `RandomForestClassifier`
- Evaluated with `classification_report`
- Extracted and plotted `feature_importances_`

---

## 🔍 Key Findings

### 📊 EDA Insights
- Depression risk is distributed across low, medium, and high — not heavily skewed
- Multiple platform usage types (Instagram, TikTok, Both, Other) show different risk patterns

### 🔗 Correlation Insights
- **Stress and anxiety** show a positive relationship — as expected
- **Screen time before sleep** shows little to no relationship with academic performance
  > *"We can infer that there is little to no relation between these two aspects"*

### 🤖 Random Forest — Feature Importance
- The model identified the most important predictors of depression risk
- Stress level and anxiety level rank as top predictors
- Platform type and screen time are secondary predictors

---

## 🤖 Model Performance

| Metric | Details |
|--------|---------|
| Model | Random Forest Classifier |
| Train/Test split | 80% / 20% |
| Evaluation | Classification report (precision, recall, F1) |
| Target classes | Low (0) / Medium (1) / High (2) depression risk |

---

## 🛠️ Tech Stack

| Tool | How it was used |
|------|----------------|
| Pandas | Data loading, filtering, encoding, mapping |
| Matplotlib | Histograms, subplots, bar charts |
| Seaborn | Countplots, heatmap, scatterplots, barplot |
| Scikit-learn | train_test_split, RandomForestClassifier, classification_report |
| NumPy | Array operations |

---

## ▶️ How to Run

```bash
# 1. Clone the repo
git clone https://github.com/yourusername/teen-socialmedia-mentalhealth.git
cd teen-socialmedia-mentalhealth

# 2. Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn jupyter

# 3. Place dataset: Teen_Mental_Health_Dataset.csv

# 4. Launch notebook
jupyter notebook Teen_Social_media_usage_mental_health.ipynb
```

---

## 👤 About the Author

**BBIS Student — Kathmandu University**
- 🎓 Bachelor of Business Information Systems — 2nd Semester
- 📍 Kathmandu, Nepal
- 🔗 LinkedIn: [your-linkedin-url]
- 🐙 GitHub: [your-github-url]

### Skills demonstrated
- Univariate and bivariate EDA
- Ordinal label encoding with `.map()`
- Nominal one-hot encoding with `pd.get_dummies()`
- Correlation matrix and heatmap
- Machine learning with Random Forest
- Feature importance extraction and visualization

---

## 💡 What I Learned
- Difference between ordinal and nominal encoding — and when to use each
- How to build and evaluate a Random Forest classifier end-to-end
- How to extract and visualize feature importances from a trained model
- How correlation heatmaps reveal hidden relationships in data

---

> *"Social media's relationship with mental health is complex —
> but data helps us see which factors actually matter."* 📱🧠
