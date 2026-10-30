# Refugees and Migration — Predictive Modeling

Exploratory analysis and predictive modeling of refugees and asylum seekers, based on the five main countries of origin and six socioeconomic and political indicators (2020). The goal is to explore correlations between variables and predict migration decisions using regression models.

![Python](https://img.shields.io/badge/Python-3.x-blue)
![pandas](https://img.shields.io/badge/pandas-EDA-green)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-orange)
![License](https://img.shields.io/badge/License-MIT-yellow)

📄 **[View the full report (PDF)](.Final%20Project.pdf)**

---

## 📌 Project Overview

This project applies a full data science workflow —following the CRISP-DM methodology— to a forced migration problem: which socioeconomic and political factors are associated with a person's decision to seek asylum or refugee status?

The analysis focuses on the **five main countries of origin** of asylum seekers and refugees, and on **six indicators** that may influence the decision to migrate:

- Unemployment rate (%).
- Conflicts (number of fatalities per year).
- Food supply (kcal, protein and fat per capita per day).
- Homicides (rate per 100,000 population).
- Happiness and life satisfaction (Cantril ladder, 0–10).
- Public spending on education (% of GDP).

The goal is to identify correlations between indicators and build regression models to predict migration decisions.

> ⚠️ **Disclaimer:** this project is educational and exploratory. It is not a migration forecasting or public policy tool.

---

## 📊 Data

| Source | Description |
|--------|-------------|
| **UNHCR** | Refugee and asylum seeker population by country of origin, country of asylum and gender (main dataset) |
| **Our World in Data** | Socioeconomic indicators: unemployment, food supply, homicides, happiness, education spending |
| **UCDP** (Uppsala Conflict Data Program) | Conflicts and number of fatalities per year |

**Time coverage:** 2012–2022 (the analysis is restricted to 2020, the year with complete information across all datasets).

**Countries analyzed:** the five main countries of origin with the highest refugee and asylum seeker population.

---

## 🛠️ Tech Stack

| Category | Tools |
|----------|-------|
| Language | Python 3.x |
| Data manipulation | pandas, numpy |
| Visualization | matplotlib, seaborn |
| Modeling | scikit-learn (LinearRegression, Ridge, Lasso) |
| Metrics | MAE, R² |
| Methodology | CRISP-DM |

---

## 🔬 Methodology

### 1. Business Understanding
Identify the factors in countries of origin that are associated with the decision to seek asylum or refugee status, using the refugee and asylum seeker population by gender as the fact table.

### 2. Data Understanding
Integration of multiple sources (UNHCR, OWID, UCDP) with data from 2012 to 2022. Initial exploration of structure, data types, missing values and descriptive statistics.

### 3. Data Preparation
- Handling missing values (`fillna(0)`).
- Renaming and normalizing columns.
- Filtering the five main countries of origin and the year 2020.
- Merging all datasets using `country` as the key.
- Train/test split for modeling.

### 4. Modeling
Training and comparison of three regression models:
- **Linear regression** (baseline).
- **Ridge** (L2 regularization).
- **Lasso** (L1 regularization).

### 5. Evaluation
Evaluation with **MAE** (mean absolute error) and **R²** (coefficient of determination). The best model reached **R² ≈ 0.82 on test**.

### 6. Deployment
The workflow is reproducible and can be adapted to studies projecting migration movements.

---

## 📈 Visualizations

The analysis includes visualizations with **matplotlib** and **seaborn**:

- **Gender distribution** of the migrant population by country (stacked bars).
- **Correlation heatmap** across the six indicators.
- **Time series** of conflict fatalities, caloric supply and unemployment by country.
- **Boxplots** of happiness (Cantril scale) by country and year.
- **Histograms** of numerical variables (univariate analysis).
- **Bivariate plots** (heatmap and line plots) to explore associations.

---

## 📊 Key Results

| Metric | Value |
|--------|-------|
| R² (test) — linear regression | ≈ 0.82 |
| MAE | Low (good model fit) |
| Highest correlation | Unemployment ↔ Homicides (r ≈ 0.94) |
| Food supply ↔ happiness | Protein (r ≈ 0.93) · Fat (r ≈ 0.92) |

**Key findings:**
- Most female refugees come from South Sudan, while most male refugees come from Syria.
- South Sudan has the highest unemployment rate (12% average, 14% peak in 2020).
- Syria recorded the highest number of fatalities in 2017, linked to IS-related events.
- Myanmar has the highest per capita caloric supply and the highest happiness score (≈ 4.5).
- There is a strong correlation between unemployment and homicides (0.94), and between food supply and happiness (0.92–0.93).

---
## 📁 Repository Structure

```
refugees-migration-predictive-modeling/
├── README.md
├── Final Project.pdf
├── Final_Project_Data_Analytics.ipynb       
├── data/
│ ├── unhcr_refugees.csv
│ ├── owid_indicators.csv
│ └── ucdp_conflicts.csv
├── img/                                   
├── requirements.txt
├── LICENSE
└── .gitignore

```
- `Final Project.pdf` — full rendered report.
- `Final_Project_Data_Analytics.ipynb` — source notebook with the analysis.
- `data/` — input datasets.
- `img/` — exported charts.



## ▶️ How to Reproduce the Analysis

1. Clone the repository:

   ```bash
   git clone https://github.com/Siguax/refugees-migration-predictive-modeling.git 
   cd refugees-migration-predictive-modeling
   ```
   
2. Install dependencies

   ```bash
   pip install -r requirements.txt
   ```
   
3. Open the notebook:

   ```bash
   jupyter notebook Final_Project_Data_Analytics.ipynb
   ```
  
4. Run the cells in order.

---

## 📚 References
- UNHCR. Refugee Statistics. https://www.unhcr.org/refugee-statistics/
- Our World in Data. https://ourworldindata.org/
- Uppsala Conflict Data Program (UCDP). https://ucdp.uu.se/
- CRISP-DM. Cross Industry Standard Process for Data Mining.

---

## 📄 License
MIT License. See LICENSE for details.

---

## ✉️ Contact
**Silvia Prevettoni**

- 🐙 GitHub: [@Siguax](https://github.com/Siguax)
- 💼 LinkedIn: [silvia-prevettoni](https://www.linkedin.com/in/silvia-prevettoni)
- 📧 Email: [silvia.prevettoni@gmail.com](mailto:silvia.prevettoni@gmail.com)
