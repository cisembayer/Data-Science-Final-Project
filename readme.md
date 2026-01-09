Dataset


Additional Research


Data Preprocessing

This section summarizes the preprocessing steps performed per script / notebook. Each file focuses on cleaning, validating, and standardizing a specific dataset before analysis.

Missing_Values_Analysis_for_Gold_import.py

Loaded gold import trade data covering multiple years.

Calculated missing value ratios for all columns.

Identified structurally missing fields (e.g. export-related values in import data).

Provided column-level interpretation of missing values to distinguish expected vs. problematic NaNs.

Used this analysis to guide downstream cleaning decisions instead of applying blind imputation.

Cleandata_Gold_import_2019_2024.py

Combined gold import datasets from 2019 to 2024 into a single, consistent dataset.

Standardized column names and ensured schema consistency across years.

Converted monetary and quantity-related fields to numeric data types.

Standardized date fields to monthly frequency (YYYY-MM-01).

Removed duplicate records and ensured logical consistency in trade values.

Produced a cleaned and analysis-ready gold import dataset.

US_Dollar_Index_Cleaning.ipynb

Loaded raw US Dollar Index (DXY) data.

Cleaned unnecessary columns and renamed fields for clarity.

Converted date columns to datetime format.

Standardized the dataset to monthly frequency to match other macroeconomic datasets.

Prepared the dataset for time-series analysis and merging with trade and financial data.

Swift_Rmb_tracker.py

Processed SWIFT RMB Tracker data containing monthly indicators.

Extracted relevant metrics related to RMB usage in international transactions.

Cleaned formatting issues and removed non-data rows.

Converted reporting dates to a consistent datetime format.

Ensured compatibility with other monthly macroeconomic datasets used in the project.

Output Structure

All cleaned datasets are saved in a structured and reusable format.

Preprocessed data is used directly in the analysis and modeling stages without further manual intervention.

The preprocessing pipeline ensures reproducibility and consistency across all datasets.


Data Analysis
