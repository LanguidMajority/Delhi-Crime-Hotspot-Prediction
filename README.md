# 🚨 Delhi Crime Hotspot Prediction
### AI-Based Urban Crime Risk Prediction System | B.Tech CSE – Data Science

---

## 📌 About the Project

Crime prediction is one of the most impactful applications of machine learning in public safety. Delhi, being India's most crime-affected city with a crime rate of **1,906.8 per lakh population (2019)**, presents a critical need for data-driven tools that help law enforcement agencies identify high-risk zones proactively.

This project builds an **AI-based predictive model** that classifies the crime risk level of Delhi's **15 police districts** as **LOW**, **MEDIUM**, or **HIGH** using historical crime data, demographic indicators, and weather patterns.

---

## 🗂️ Repository Structure

```
delhi-crime-hotspot-prediction/
│
├── Delhi_Crime_Prediction_Simple.ipynb   ← Main project notebook (Google Colab)
├── delhi_crime_dataset.csv               ← Dataset (1,260 records × 35 columns)
└── README.md                             ← This file
```

---

## 📊 Dataset Details

| Property | Details |
|---|---|
| **Records** | 1,260 rows |
| **Columns** | 35 features |
| **Coverage** | 15 Delhi Police Districts × 7 Years (2016–2022) × 12 Months |
| **Target Variable** | `risk_level` → LOW / MEDIUM / HIGH |

### Data Sources
- 🏛️ **Delhi Police Official Statistics (2016–2022)** — Crime counts for 11 IPC categories
- 📋 **Census of India 2011** — Population density, literacy rate, unemployment rate
- 🌦️ **India Meteorological Department (IMD)** — Monthly temperature and rainfall data

### Key Features Used
```
district_encoded     → Label-encoded Delhi Police district (15 districts)
month, year          → Time period
population_density   → People per sq km
literacy_rate        → % literate population
unemployment_rate    → % unemployed population
avg_temperature_C    → Monthly average temperature
avg_rainfall_mm      → Monthly average rainfall
is_summer            → Flag: April–July (crime peak season)
is_festive_month     → Flag: Oct, Nov, Mar, Apr (festive seasons)
prev_month_crimes    → Total crimes in previous month (lag feature)
rolling_3m_avg       → 3-month rolling average of crimes (lag feature)
crime_density        → Crimes per sq km
```

---

## 🤖 Models Used

|            Model             |                  Description                  |
|------------------------------|-----------------------------------------------|
| **Decision Tree Classifier** | Baseline model — interpretable and easy to explain |
| **Random Forest Classifier** | Ensemble model — higher accuracy, more robust |

Both models were trained on 80% of the data and tested on the remaining 20%, with `random_state=42` for reproducibility.

---

## 📈 Results

|     Model     |Accuracy |
|---------------|---------|
| Decision Tree | 76.19 % |
| Random Forest | 96.43 % |

---

## 🔍 Key Findings from EDA

- 📍 **North East Delhi, South Delhi, and Outer Delhi** are the highest-risk zones by crime volume
- ☀️ **Summer months (May–June)** consistently show peak crime activity across all districts
- 📉 **2020** shows a visible crime dip due to COVID-19 lockdown restrictions
- 📊 **Unemployment rate and population density** have a strong positive correlation with crime rate
- ⏱️ **prev_month_crimes** (lag feature) is the most influential predictor — crime is temporally persistent

---

## 🛠️ Libraries and Tools

```python
pandas        # Data loading, cleaning, analysis
numpy         # Numerical operations
matplotlib    # Charts and visualizations
seaborn       # Statistical visualizations
scikit-learn  # ML models, encoding, evaluation
```

**Environment:** Google Colab (no local installation required)

---

## 🚀 How to Run

1. Open [Google Colab](https://colab.research.google.com)
2. Click **File → Upload Notebook** and upload `Delhi_Crime_Prediction_Simple.ipynb`
3. Upload `delhi_crime_dataset.csv` using the **Files panel** (folder icon on the left sidebar)
4. Click **Runtime → Run All**
5. Fill in the Results table above with your output accuracy values

---

## 📓 Notebook Structure

| Step | Description |
|---|---|
| Step 1 | Import Libraries |
| Step 2 | Load Dataset |
| Step 3 | Dataset Info and Statistical Summary |
| Step 4 | Data Cleaning (missing values, duplicates) |
| Step 5 | Univariate Analysis (bar chart, pie chart, histogram) |
| Step 6 | Bivariate Analysis (scatter plots, heatmaps, trend charts) |
| Step 7 | Feature Preparation and Label Encoding |
| Step 8 | Model 1 — Decision Tree (train, predict, evaluate) |
| Step 9 | Model 2 — Random Forest (train, predict, evaluate) |
| Step 10 | Model Accuracy Comparison Chart |
| Step 11 | Feature Importance Chart |
| Step 12 | Sample Prediction (input district + month → output risk level) |
| Step 13 | Final Project Summary |

---

## 👤 Author

Name : Ashish Jakhmola
currently pursuing B.Tech Computer Science & Engineering – Data Science
Collage : Guru Tegh Bahadur Institute of Technology
📧 Email : ashishjkhml@gmail.com

---

## 📚 References

- Delhi Police Official Crime Statistics — [delhipolice.gov.in](https://delhipolice.gov.in/statistics)
- National Crime Records Bureau (NCRB) — [ncrb.gov.in](https://ncrb.gov.in)
- Census of India 2011 — [censusindia.gov.in](https://censusindia.gov.in)
- Scikit-learn Documentation — [scikit-learn.org](https://scikit-learn.org)

---

*This project was developed as part of the Industrial Training / Project course for B.Tech CSE Data Science.*
