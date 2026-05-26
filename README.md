# Walmart Retail Sales Forecast

## Project Overview

Walmart operates thousands of retail locations across the United States, making accurate sales forecasting critical for efficient operational planning. This project focused on forecasting retail sales at the store-department level using historical transaction and regional shopping pattern data.

The objective of the analysis was to better understand how retail demand fluctuates across time and departments in order to support operational decision making. Accurate forecasting can help retailers anticipate periods of increased or decreased demand, improving inventory allocation, staffing efficiency, pricing strategy, and overall customer experience.

<br>

Full R code rmd file can be found [here](https://github.com/darianmiranda/Walmart-Retail-Sales-Forecast/blob/main/Walmart-Retail-Sales-Forecast.Rmd)

Full R code html file can be found [here](https://github.com/darianmiranda/Walmart-Retail-Sales-Forecast/blob/main/Walmart-Retail-Sales-Forecast.html)

View the data [here](https://www.kaggle.com/datasets/aslanahmedov/walmart-sales-forecast)


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

<img width="2000" height="1200" alt="predictions_plot" src="https://github.com/user-attachments/assets/75d7d51a-70d7-4dc6-9e38-43f372b8c38a" />

Key findings from the analysis included:

* Specific periods of the year showed noticeably lower operational demand, particularly during late April, late July, and mid to late September
* Demand increased sharply before major US holiday Independence Day, suggesting strong seasonal or event driven purchasing behavior
* Forecast performance demonstrates that historical sales behavior can be used effectively to anticipate short term future demand patterns

The analysis also highlighted the importance of department level forecasting, as demand variability may differ substantially across retail categories. The most difficult departments to forecast are shown below, with no reference table only department ID can be provided.

<img width="2000" height="1200" alt="difficult_depts_plot" src="https://github.com/user-attachments/assets/85820436-dc86-44e6-91e4-570ef8ba7bdc" />

One important limitation of the dataset was the relatively limited forecasting horizon. Because the analysis did not span multiple full annual seasonal cycles, the model had limited ability to fully capture long term holiday behavior and broader year over year demand dynamics.

---

## Recommendations

The forecasting results suggest that machine learning driven demand forecasting can support more proactive retail planning decisions across staffing, inventory allocation, and operational resource management. While the model demonstrated strong overall predictive performance, forecast variability across departments highlights opportunities for more targeted planning strategies and future forecasting improvements.

### Short Term Staffing and Inventory Planning

Observed lower demand periods present opportunities to:

* Reduce staffing levels strategically
* Adjust inventory purchasing schedules
* Reallocate operational resources more efficiently

Conversely, periods with elevated demand could be used to proactively:

* Increase staffing coverage
* Expand inventory allocation
* Improve supply chain readiness

These adjustments may help reduce excess inventory costs while improving operational responsiveness during peak demand periods.

### Department Specific Forecast Monitoring

Departments with consistently higher forecast error may benefit from additional operational oversight and more adaptive forecasting strategies. Elevated forecast variability may indicate departments that are more sensitive to seasonal demand shifts, promotions, or irregular purchasing behavior.

Potential operational responses could include:

* More frequent forecast updates for volatile departments
* Department specific inventory safety stock policies
* Additional monitoring during seasonal demand periods
* Separate forecasting approaches for highly variable product categories

Targeted forecasting strategies may improve planning accuracy while reducing the operational risk associated with unpredictable demand patterns.

### Expand Forecasting Capabilities

Future forecasting improvements could include:

* Additional years of historical data
* Multi year seasonal trend analysis

These additions could improve the model’s ability to capture long term retail behavior and strengthen forecasting reliability during major shopping events.



