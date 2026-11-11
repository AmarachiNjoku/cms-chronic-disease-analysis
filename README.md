# CMS Chronic Disease Analysis

Exploratory analysis of the CMS chronic conditions dataset: how common chronic diseases are among Medicare beneficiaries, what Medicare pays per person for each condition, and how Texas, New York, California and Florida compare with the national picture. Written for a non-technical hospital leadership audience.

**Tools:** Python, pandas, NumPy, matplotlib, seaborn, Jupyter

## Goals

1. **Chronic disease prevalence by race (and age):** national prevalence for each condition, broken out by race, with a state versus national comparison.
2. **Medicare utilization and payments:** per-capita total and standardized Medicare payments by condition, and for the national level versus the four target states.
3. **State-level differences:** state rankings by condition, gender breakdowns, and each target state's deviation from the national average.

Every analysis in the notebook has a markdown explanation, the code that produces the chart, and the chart itself (9 visualizations in total).

## Data

- Source: [CMS Data](https://data.cms.gov/), Medicare chronic conditions data
- Not included in this repo. Download the CSV, save it as `data/chronic-disease-data.csv`, and update the path in the loading cell if needed.
- Records are filtered to `Bene_Geo_Lvl` of State or National. Rows with missing prevalence or payment values are dropped for the relevant analysis. Payment fields are only populated for a small subset of rows (about 1,100 of 32,000).

## How to run

```bash
pip install -r requirements.txt
jupyter notebook "Amarachi Njoku_CMS Chronic diseas data analysis.ipynb"
```

## Selected findings

- **Most common conditions nationally:** hypertension (about 57% of beneficiaries), hyperlipidemia (48%), arthritis (33%) and diabetes (27%).
- **Racial differences:** diabetes prevalence is roughly 35 to 39% among Asian Pacific Islander, Hispanic, Native American and non-Hispanic Black beneficiaries, compared with about 24% for non-Hispanic White beneficiaries. Hypertension is highest for non-Hispanic Black beneficiaries (about 63%).
- **Highest-cost conditions:** stroke ($31.9K standardized per-capita payment), heart failure ($28.6K) and COPD ($25.4K).
- **State comparison:** Florida sits above the national figure on all four leading conditions (hyperlipidemia 59% versus 48%), while California sits below it on all four. Texas has the highest average standardized payment of the four target states.

## Limitations

- Covers Medicare beneficiaries only, so it does not describe the general population.
- Prevalence reflects diagnosed conditions, which depends on access to care.
- State and national payment figures are simple averages across conditions, not weighted by the number of beneficiaries.
- The age-group comparison depends on the age levels available in the file. If only an "All" level is present, age patterns are not shown.

## Repository layout

```
.
├── Amarachi Njoku_CMS Chronic diseas data analysis.ipynb
├── README.md
├── requirements.txt
├── figures/
└── data/            (add the CSV locally, it is git-ignored)
```
