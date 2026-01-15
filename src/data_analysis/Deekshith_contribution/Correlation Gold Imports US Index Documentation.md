# Correlation Gold Imports US Index Documentation

This document provides an overview of the Correlation Gold Imports US Index project, detailing the methodologies, data sources, and expected outcomes.

## Introduction

The Correlation Gold Imports US Index project aims to analyze the relationship between gold imports and the US dollar index. This is achieved through the application of various data analysis and machine learning techniques.

## Data Sources

The primary data sources for this project include:
- Historical data on gold imports, including various attributes such as:
  - Year of import
  - Reporter country
  - Quantity of gold imported
  - CIF (Cost, Insurance, and Freight) value
  - FOB (Free on Board) value
- Historical data on the US dollar index.

The data is processed and analyzed using Python libraries such as Pandas, NumPy, and Scikit-learn.

## Methodology

The project follows these key steps:
1. **Data Import**: Load the dataset using Pandas.
   ```python
   gold = pd.read_csv('path/to/Gold_Import_TradeData.csv')
   dxy = pd.read_csv('path/to/US_Dollar_Index.csv')
   ```
2. **Data Exploration**: Analyze the dataset to understand its structure and identify any missing values or anomalies.
   ```python
   print(gold.info()) # Check data types and non-null counts
   print(gold.describe()) # Summary statistics
   ```
3. **Data Cleaning**: Handle missing values and duplicates to ensure data integrity.
   ```python
   missing_values = gold.isnull().sum()
   duplicates = gold.duplicated().sum()
   ```
4. **Feature Engineering**: Create new features that may help improve the model's performance.
5. **Model Selection**: Choose appropriate machine learning models for forecasting, such as Linear Regression.
   ```python
   from sklearn.linear_model import LinearRegression
   model = LinearRegression()
   ```
6. **Model Training**: Split the data into training and testing sets, and train the model.
   ```python
   X_train, X_test, y_train, y_test = train_test_split(features, target, test_size=0.2)
   model.fit(X_train, y_train)
   ```
7. **Model Evaluation**: Evaluate the model's performance using metrics such as Mean Absolute Error (MAE) and R-squared.
   ```python
   from sklearn.metrics import mean_absolute_error, r2_score
   predictions = model.predict(X_test)
   print(mean_absolute_error(y_test, predictions))
   print(r2_score(y_test, predictions))
   ```
8. **Correlation Analysis**: Analyze the correlation between gold imports and the US dollar index.
   ```python
   correlation = gold['cifvalue'].corr(dxy['Price'])
   print(f'Correlation: {correlation}')
   ```

## Expected Outcomes

The expected outcomes of this project include:
- A comprehensive analysis of the correlation between gold imports and the US dollar index.
- Insights into how fluctuations in the US dollar index may impact gold imports.
- A predictive model that can forecast future trends in gold imports based on changes in the US dollar index.
