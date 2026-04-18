# data-breaches-analysis
 Analyse complète de 700+ fuites de données mondiales via l'API HaveIBeenPwned (2007–2024) — Python · Pandas · Matplotlib · Seaborn

## 📌 Project Overview

This project analyzes 700+ data breaches recorded on the HaveIBeenPwned platform between 2007 and 2024.
The goal is to understand the evolution of cyberattacks over time, identify the most vulnerable sectors, and determine which types of personal data are most frequently exposed.

**Key questions answered:**
- How have data breaches evolved over time?
- Which sectors are the most targeted?
- What types of personal data are most exposed?
- Which breaches caused the most damage?

---

## 📂 Dataset

| Property | Details |
|---|---|
| Source | [HaveIBeenPwned Public API v3](https://haveibeenpwned.com/API/v3) |
| Records | 700+ verified data breaches |
| Period | 2007 – 2024 |
| Format | JSON via API → CSV |
| Authentication | No API key required |

Main fields used: `Name`, `BreachDate`, `PwnCount`, `DataClasses`, `Domain`, `IsVerified`, `IsSensitive`


## 🛠️ Tools & Technologies

| Tool | Usage |
|---|---|
| Python 3.10 | Main language |
| Pandas | Data manipulation & cleaning |
| NumPy | Numerical computation (SeverityScore) |
| Matplotlib | Publication-ready visualizations |
| Seaborn | Exploratory visualizations |
| Requests | API data collection |
| Jupyter Notebook | Development environment |


## 🔄 Project Steps

Notebook 01 — Data Collection
- Connect to HaveIBeenPwned API v3
- Retrieve all public breaches in JSON format
- Inspect raw data and export to `breaches_raw.csv`

Notebook 02 — Data Cleaning & Feature Engineering
- Parse date columns (`BreachDate`, `AddedDate`)
- Remove duplicates and handle missing values
- Create new variables : `BreachSize`, `Sector`, `NbDataTypes`, `SeverityScore`, `Year`, `Quarter`, `Decade`

Notebook 03 — Exploratory Data Analysis
- Answer 8 analytical questions
- Generate 8 charts (trends, sectors, data types, correlations)

Notebook 04 — Publication-Ready Visualizations
- KPI banner, timeline, bubble chart, top 10 breaches
- Final 2×2 dashboard (dark background, high resolution)


## 🔑 Key Results & Insights

- 📈 +15 billion accounts compromised worldwide between 2007 and 2024
- 📅 2016–2018 was the most critical period in the history of data breaches
- 🏭 The Tech & Social Media sector accounts for more than 60% of compromised accounts
- 📧 Email addresses and passwords are present in over 90% of all breaches
- 🏆 Yahoo holds the record with 3 billion accounts exposed in a single breach
- 🔢 A custom SeverityScore was created to measure breach severity beyond raw volume : `log(PwnCount) × NbDataTypes × verification × sensitivity`


## ▶️ How to Run

```bash
# 1. Clone the repository
git clone https://github.com/esmelamari/data-breaches-analysis.git
cd data-breaches-analysis

# 2. Install dependencies
pip install -r requirements.txt

# 3. Run notebooks in order
jupyter notebook notebooks/01_data_collection.ipynb
jupyter notebook notebooks/02_data_cleaning.ipynb
jupyter notebook notebooks/03_eda_analysis.ipynb
jupyter notebook notebooks/04_visualizations.ipynb
```

> ⚠️ An internet connection is required for Notebook 01 (HIBP API call).


Author : Esmel — Data Analyst · Abidjan, Côte d'Ivoire
🔗 [esmel.netlify.app](https://esmel.netlify.app) · [LinkedIn](https://linkedin.com/in/esmelamari)
