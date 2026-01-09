Dataset


Additional Research


*Data Preprocessing*

This section documents the preprocessing steps applied to each dataset in the project.
All preprocessing scripts were implemented in Python and designed to ensure consistency, reliability, and compatibility across datasets before analysis.

*📄 Missing_Values_Analysis_for_Gold_import.py*

Purpose:
To analyze and interpret missing values in the gold import trade dataset.

Preprocessing Steps:

Loaded multi-year gold import trade data.

Calculated column-wise missing value ratios.

Identified structurally missing fields (e.g. export-related variables in import data).

Interpreted missing values based on domain knowledge instead of applying automatic imputation.

Used results to guide subsequent cleaning decisions.

*📄 Cleandata_Gold_import_2019_2024.py*

Purpose:
To clean, standardize, and merge gold import data from 2019–2024.

Preprocessing Steps:

Merged yearly datasets into a single consolidated dataframe.

Standardized column names and ensured schema consistency.

Converted monetary and quantity fields to numeric data types.

Standardized date values to monthly frequency (YYYY-MM-01).

Removed duplicate records and invalid entries.

Generated a clean, analysis-ready gold import dataset.

*📄 US_Dollar_Index_Cleaning.ipynb*

Purpose:
To prepare US Dollar Index (DXY) data for time-series and macroeconomic analysis.

Preprocessing Steps:

Loaded raw DXY data.

Removed unnecessary columns and renamed variables for clarity.

Converted date columns to datetime format.

Resampled and standardized data to monthly frequency.

Prepared the dataset for merging with trade and financial indicators.

*📄 Swift_Rmb_tracker.py*

Purpose:
To clean and standardize SWIFT RMB Tracker data.

Preprocessing Steps:

Loaded SWIFT RMB Tracker reports.

Extracted relevant indicators related to RMB usage in global transactions.

Cleaned formatting issues and removed non-data rows.

Standardized reporting dates to datetime format.

Ensured consistency with other monthly macroeconomic datasets.

*📁 Preprocessing Outputs*

All cleaned datasets are saved in a structured format and reused across the project.

Preprocessed data is directly consumed in analysis and modeling stages.

The preprocessing workflow ensures reproducibility, consistency, and data integrity.


Data Analysis
