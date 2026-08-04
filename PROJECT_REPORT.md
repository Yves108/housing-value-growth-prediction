# Project Report

## Business question

Can state-level housing-market indicators help explain and predict short-term changes in home values?

## Data preparation

The project combines a Zillow Home Value Index snapshot with Redfin state-level monthly market indicators. Zillow's wide monthly format is reshaped into a state-month panel before the sources are aligned by geography and date. The workflow also resolves naming differences such as Washington, D.C. and excludes regions that cannot be matched consistently.

The final modeling table contains 1,326 state-month observations. Features cover transaction activity, median sale price, days on market, new listings, active listings, and engineered supply-and-demand ratios. The target is the monthly percentage change in ZHVI.

## Modeling approach

Six regression approaches are evaluated with consistent preprocessing:

1. Linear Regression
2. Ridge Regression
3. Lasso Regression
4. Stochastic Gradient Descent Regression
5. Gradient Boosting Regression
6. Random Forest Regression

The evaluation includes cross-validation, a held-out test set, and a chronological validation split. This combination helps compare predictive accuracy while checking whether conclusions remain stable when the model is asked to predict later periods.

## Results

- Random Forest produced the strongest average cross-validation result, with mean R² of 0.786.
- Its held-out test R² was 0.757.
- Lasso achieved a chronological validation R² of 0.789.

These results indicate that market activity and inventory features contain meaningful information about short-term home-value changes. The competitive Lasso time-split result also shows that a more interpretable linear model can remain useful when validation follows the real sequence of time.

## Limitations

- The data covers a limited time window and uses state-level aggregation.
- Housing relationships may vary across local markets and economic regimes.
- Provider revisions or new observations can change the measured relationships.
- Predictive association should not be interpreted as causal impact.

## Next steps

- Extend the panel across a longer economic cycle.
- Add mortgage-rate, employment, income, and construction indicators.
- Compare state-specific or hierarchical models.
- Track model performance with rolling-origin validation.
