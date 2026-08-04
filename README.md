# Housing Value Growth Prediction

An end-to-end housing analytics project that integrates Zillow Home Value Index data with Redfin market indicators to predict monthly home-value growth across U.S. states.

## Project overview

The analysis reshapes and joins two housing datasets, engineers supply-and-demand features, explores market relationships, and compares six regression models. The target is the monthly percentage change in Zillow Home Value Index (ZHVI).

Key results from the completed analysis:

- Built a modeling dataset with 1,326 state-month observations.
- Compared Linear Regression, Ridge, Lasso, SGD, Gradient Boosting, and Random Forest models.
- Random Forest achieved a mean cross-validation R² of 0.786 and a held-out test R² of 0.757.
- Lasso achieved a time-based validation R² of 0.789, supporting the stability of the main findings.

## Methods

- Data cleaning and wide-to-long transformation
- Cross-source state and date alignment
- Feature engineering for inventory, sales activity, and supply-demand ratios
- Exploratory data analysis and correlation review
- Reproducible preprocessing with scikit-learn pipelines
- Cross-validation, held-out testing, and time-based validation
- Feature-importance and coefficient interpretation

## Repository contents

- `housing_value_growth_analysis.ipynb` — complete analysis and modeling workflow
- `housing_project_data/` — Zillow and Redfin course-project data snapshots
- `PROJECT_REPORT.md` — concise findings and interpretation
- `requirements.txt` — Python dependencies

## Run the analysis

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook housing_value_growth_analysis.ipynb
```

The notebook writes generated tables and figures to `housing_project_outputs/`.

## Data sources

- Zillow Research housing data
- Redfin Data Center housing market data

The included files are course-project snapshots used to make the analysis reproducible. For current data, download updated files from the original providers and preserve the filenames expected by the notebook.

## Attribution

This project was completed as an OMIS 114 course team project. This portfolio repository is maintained by Zhiyi Li and presents the team's submitted analysis with its original notebook outputs.

