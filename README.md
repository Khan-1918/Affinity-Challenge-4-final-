Project Objective
The objective of this project is to develop a predictive model that forecasts:

Weekly incoming orders.
In-flight campaigns for the next weeks, segmented by teams.
These forecasts aim to optimize resource allocation, team management, and operational planning.

Dataset Overview
Orders Dataset:

Contains historical data of orders, including team and time-related fields.
Key fields: startdate, enddate, dim_team_key, and dim_order_key.
C4 Submission Form:

Template to populate predictions for incoming_orders and in_flight_campaigns fields based on weekly periods starting on Sunday.
Methodology
1. Data Preprocessing
Converted startdate and enddate to datetime objects for temporal analysis.
Generated week_start (start of the weekly period) and aggregated data by week and team.
Created key features for modeling:
Temporal features: week_of_year, month, year.
Team-based categorical features.
2. Feature Engineering
Incoming Orders:
Counted the total number of orders per team for each week.
In-Flight Campaigns:
Counted campaigns active during each week by evaluating overlaps between the campaign’s startdate and enddate with the weekly period.
3. Model Selection
Used XGBoost Regressor, a high-performance gradient boosting algorithm, for its ability to handle:
Non-linear relationships.
Mixed data types (categorical and numerical).
Missing values in the dataset.
4. Evaluation Metrics
Mean Absolute Error (MAE) was used to evaluate model performance, as it provides an intuitive measure of average prediction error and is robust to outliers.
Results
Model Performance:
MAE for Incoming Orders: 18.59
MAE for In-Flight Campaigns: 18.38
Feature Importance:
Temporal features like week_of_year and month were significant predictors.
Team-specific categorical features (dim_team_key) also contributed notably.
Key Insights
Feature Contributions:

Temporal features (week_of_year, month, year) showed high predictive power, indicating seasonal trends.
Team-level features captured team-specific variations in orders and campaigns.
Importance of Preprocessing:

Accurately aligning weekly periods and handling missing or erroneous date values were critical to building reliable models.
Conclusion
The XGBoost model demonstrated strong performance and was the best choice for predicting weekly incoming orders and in-flight campaigns. It provides robust, interpretable, and scalable solutions aligned with business goals, ensuring reliable forecasts for effective decision-making.

The predictions for unlabeled data will be evaluated using RMSE.Which scientific or business loss function could be a better evaluation metric for this problem?

The best-performing model in the analysis was XGBoost. It achieved the lowest Mean Absolute Error (MAE) for both targets:

Incoming Orders: MAE = 18.59
In-Flight Campaigns: MAE = 18.38
XGBoost outperformed other models due to its ability to:

Capture non-linear relationships effectively.
Handle categorical and numerical features robustly.
Manage missing values and large datasets efficiently.
Other models like SARIMA, ETS, and AdaBoost underperformed due to dataset complexity and categorical data


In your analysis, which were the best performing models?

The best-performing model in the analysis was XGBoost. It achieved the lowest Mean Absolute Error (MAE) for both targets:

Incoming Orders: MAE = 18.59
In-Flight Campaigns: MAE = 18.38
XGBoost outperformed other models due to its ability to:

Capture non-linear relationships effectively.
Handle categorical and numerical features robustly.
Manage missing values and large datasets efficiently.
Other models like SARIMA, ETS, and AdaBoost underperformed due to dataset complexity and categorical data.






