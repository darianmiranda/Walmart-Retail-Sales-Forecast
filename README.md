# Walmart Retail Sales Forecasting

## Project Overview

Walmart operates thousands of retail locations across the United States, making accurate sales forecasting critical for efficient operational planning. This project focused on forecasting retail sales at the store-department level using historical transaction and regional shopping pattern data.

The objective of the analysis was to better understand how retail demand fluctuates across time and departments in order to support operational decision making. Accurate forecasting can help retailers anticipate periods of increased or decreased demand, improving inventory allocation, staffing efficiency, pricing strategy, and overall customer experience.




### Project Links

Full R code rmd file can be found [here](https://github.com/darianmiranda/Walmart-Retail-Sales-Forecast/blob/main/predictionportfolio.Rmd)

Full R code html file can be found [here](https://github.com/darianmiranda/Walmart-Retail-Sales-Forecast/blob/main/predictionportfolio.html)

View the data [here](https://www.kaggle.com/datasets/yasserh/walmart-dataset)


---

## Methodology

The analysis was conducted using historical Walmart store and department-level sales data obtained. The dataset included time based retail sales observations across multiple store locations and departments.

The forecasting workflow includes:

* Feature engineering
* Time aware train/test splitting
* Forecast accuracy evaluation using WAPE (Weighted Absolute Percentage Error)

To maintain computational efficiency on a local machine, lagged test features were precomputed using only historically available information and train derived baselines. This approach approximates one step ahead forecasting behavior while avoiding information leakage.

While the workflow captures forecasting structure, a fully recursive multi step forecasting simulation would sequentially recompute lagged variables using prior model predictions at each future step. This limitation reflects a tradeoff between computational efficiency and full production style forecasting.


---

## Findings

The final forecasting model achieved approximately <strong>8.4% WAPE</strong> on the test dataset, demonstrating strong predictive performance on unseen future sales observations.

Key findings from the analysis included:

* Certain periods of the year showed noticeably lower operational demand, particularly during late April, late July, and mid to late September
* Demand increased sharply before major US holidays, suggesting strong seasonal or event driven purchasing behavior
* Forecast performance demonstrated that historical sales behavior can be used effectively to anticipate short term future demand patterns

The analysis also highlighted the importance of department level forecasting, as demand variability may differ substantially across retail categories.

One important limitation of the dataset was the relatively limited forecasting horizon. Because the analysis did not span multiple full annual seasonal cycles, the model had limited ability to fully capture long-term holiday behavior and broader year over year demand dynamics.


---

## Recommendations

Based on the findings, several operational recommendations could be explored to improve retail planning and forecasting insights:

### Department-Level Operational Analysis

Future analysis could include department-specific visualizations to identify:

* Which departments require the highest inventory allocation
* Which departments experience the greatest seasonal variability
* Which product categories are most sensitive to demand fluctuations

This would allow forecasting insights to support more targeted operational decision-making.

### Staffing and Inventory Planning

Observed lower-demand periods may present opportunities to:

* Reduce staffing levels strategically
* Adjust inventory purchasing schedules
* Reallocate operational resources more efficiently

Conversely, periods with elevated demand could be used to proactively:

* Increase staffing coverage
* Expand inventory allocation
* Improve supply chain readiness

### Expand Forecasting Horizon

Future forecasting improvements could include:

* Additional years of historical data
* Multi-year seasonal trend analysis
* More advanced recursive forecasting frameworks
* Incorporation of external variables such as holidays, promotions, or economic indicators

These additions could improve the model’s ability to capture long-term retail behavior and strengthen forecasting reliability during major shopping events.
