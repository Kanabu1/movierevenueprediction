# movierevenueprediction


## Overview

This project focuses on predicting movie revenue using various machine learning models. The dataset used for this analysis is the 'imdb_movies.csv' file, which contains key information such as budget, revenue, genre, release dates, and crew details for each movie. The workflow involves multiple stages, including data cleaning, preprocessing, feature engineering, outlier detection, and model training, followed by model evaluation using regression metrics.

The goal is to build a model that can accurately predict the revenue of a movie based on its attributes, using both simple linear regression and more complex models like Random Forest and Support Vector Regressor. The project attempts to create an effective predictive model.

## Steps Taken

1. **Data Loading and Cleaning:**
   - The code begins by loading the 'imdb_movies.csv' dataset using pandas.
   - Missing values in the 'crew' column are removed.
   - Missing values in the 'genre' column are filled with 'Unknown'.
   - Duplicate rows are dropped.

2. **Feature Engineering:**
   - A new feature 'ROI' (Return on Investment) is calculated as (revenue - budget) / budget.
   - The 'date_x' column is converted to datetime format.
   - Year, month, and day of the week are extracted from the date.
   - A 'holiday_season' feature is created, indicating whether the movie was released during a holiday season (June, July, November, December).
   - 'day_of_year' and 'decade' features are added for temporal analysis.

3. **Outlier Handling:**
   - Box plots are used to visualize outliers in 'budget_x', 'revenue', and 'score'.
   - Outliers are removed using quantile-based filtering.

4. **Data Encoding and Scaling:**
   - One-hot encoding is applied to the 'genre' column.
   - Numerical features ('budget_x', 'revenue', 'score') are scaled using StandardScaler.

5. **Correlation Analysis:**
   - A correlation matrix is generated to visualize relationships between numerical features.
   - Scatter plots are created to explore the relationship between numerical features and revenue.

6. **Model Training and Evaluation:**
   - The dataset is split into training and testing sets (80% train, 20% test).
   - Several regression models are trained and evaluated, including Linear Regression, Random Forest Regressor, Decision Tree Regressor, and Support Vector Regressor.
   - Mean Squared Error (MSE) and R2 Score are used as evaluation metrics.

7. **Hyperparameter Tuning (Commented Out):**
   - The code includes a commented-out section for hyperparameter tuning of the Random Forest Regressor using GridSearchCV.

## Insights/Findings

- Outliers were identified and removed to improve model performance.
- One-hot encoding was used for the 'genre' feature to handle categorical data.
- Feature scaling was applied to numerical features to ensure they have equal impact on the models.
- Correlation analysis helped understand relationships between features.
- Linear Regression, Random Forest Regressor, Decision Tree Regressor and Support Vector Regressor were trained and evaluated for predicting movie revenue.
- MSE and R2 Score were used to assess model performance.
- Random Forest Regressor generally produced the best result in terms of R2 Score and Mean Square Error.
