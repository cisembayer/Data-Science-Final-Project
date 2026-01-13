# University of Europe - Data Science Master (60)
## Final Project for *Data Science & Business Lesson*

# Dataset


# Additional Research


# Data Preprocessing

This section documents the preprocessing steps applied to each dataset in the project.
All preprocessing scripts were implemented in Python and designed to ensure consistency, reliability, and compatibility across datasets before analysis.

## *📄 Missing_Values_Analysis_for_Gold_import.py*

Purpose:
To analyze and interpret missing values in the gold import trade dataset.

Preprocessing Steps:

Loaded multi-year gold import trade data.

Calculated column-wise missing value ratios.

Identified structurally missing fields (e.g. export-related variables in import data).

Interpreted missing values based on domain knowledge instead of applying automatic imputation.

Used results to guide subsequent cleaning decisions.

## *📄 Cleandata_Gold_import_2019_2024.py*

Purpose:
To clean, standardize, and merge gold import data from 2019–2024.

Preprocessing Steps:

Merged yearly datasets into a single consolidated dataframe.

Standardized column names and ensured schema consistency.

Converted monetary and quantity fields to numeric data types.

Standardized date values to monthly frequency (YYYY-MM-01).

Removed duplicate records and invalid entries.

Generated a clean, analysis-ready gold import dataset.

## *📄 US_Dollar_Index_Cleaning.ipynb*

Purpose:
To prepare US Dollar Index (DXY) data for time-series and macroeconomic analysis.

Preprocessing Steps:

Loaded raw DXY data.

Removed unnecessary columns and renamed variables for clarity.

Converted date columns to datetime format.

Resampled and standardized data to monthly frequency.

Prepared the dataset for merging with trade and financial indicators.

## *📄 Swift_Rmb_tracker.py*

Purpose:
To clean and standardize SWIFT RMB Tracker data.

Preprocessing Steps:

Loaded SWIFT RMB Tracker reports.

Extracted relevant indicators related to RMB usage in global transactions.

Cleaned formatting issues and removed non-data rows.

Standardized reporting dates to datetime format.

Ensured consistency with other monthly macroeconomic datasets.

---------------------------------------------------------------------------------------------------------
#### Structure of our processed data is as follows -

```tree
├── data/
│   ├── raw/  # Contain Raw Dataset
│   │       └── Bitcoin/
│   │       └── Crude and Petroleum Oils/
│   │       └── Gold/
│   │       └── Price and Micro Time Series/
│   │
│   ├── processed/    # Contain Cleaned Dataset
│       ├──  Gold and Crude_Petrol/    (Atul) 
│       │                 └──  bitcoinity_cleaned.csv 
│       │                 └──  crude_pertroleum_export.csv 
│       │                 └──  crude_pertroleum_import.csv 
│       │
│       ├──  Gold/   (Talatcan)   
│       │      └──  Gold_Import_TradeData_clean_final.csv 
│       │   
│       ├──  Micro Time Series/ (Atul)
│       │      ├── Bitcoin_Ethereum/
│       │      │                └── bitcoin_etherium.csv
│       │      ├── Brent_Crude_Price_and_WTI/
│       │      │                └── brent_crude_wti.csv
│       │      ├── Interest_Rate/
│       │      │                └── interest_rate.csv
│       │      └── USD_Index/
│       │                  └── usd_index.csv
│       ├──  Swift/ (Talatcan)
│       │       └── swift_rmb_tracker_clean.csv
│       └──  USD_Index/ (Talatcan)
│               └── US_Dollar_Index_cleaned.csv
│
├── README.md
```

### Gold and Crude_Petrol/
This repository contains three files - 
- bitcoinity_cleaned.csv
  - Loading the dataset with pd.read_csv()
  - Remove the NaN value from columns cex.io, coinbase.
  - Converted Time columns object data into datetime format via pd.to_datetime().
  - Saved the cleaned dataset into the processed repository.
  
- crude_pertroleum_export.csv
  - Loading the dataset with pd.read_csv()
  - dropping irrelevant columns from the dataset, i.e.
  'freqCode', 'refPeriodId', 'refMonth', 'typeCode', 'refYear', 'period', 'reporterCode', 'reporterISO', 'reporterDesc', 'flowCode', 'flowDesc', 'partnerCode', 'partnerISO', 'partnerDesc', 'partner2Code', 'partner2ISO', 'partner2Desc', 'classificationCode', 'classificationSearchCode', 'isOriginalClassification', 'cmdCode', 'cmdDesc', 'aggrLevel', 'isLeaf', 'customsCode', 'customsDesc', 'mosCode', 'motCode', 'motDesc', 'qtyUnitCode', 'qtyUnitAbbr', 'qty', 'isQtyEstimated', 'altQtyUnitCode', 'altQtyUnitAbbr', 'altQty', 'isAltQtyEstimated', 'netWgt', 'isNetWgtEstimated', 'grossWgt', 'isGrossWgtEstimated', 'cifvalue', 'fobvalue', 'primaryValue', 'legacyEstimationFlag', 'isReported', 'isAggregate'.
  - Remove the NaN value and replacing it with mean(), median(), mode() on columns altQtyUnitAbbr, netWgt, cifvalue.
  - Saved the cleaned dataset into the processed repository.
    
- crude_pertroleum_import.csv
  - Loading the dataset with pd.read_csv()
  - dropping irrelevant columns from the dataset, i.e.
    'typeCode', 'freqCode', 'refPeriodId', 'refMonth', 'period', 'flowCode', 'flowDesc', 'partnerCode', 'partnerISO', 'partnerDesc', 'partner2Code', 'partner2ISO', 'partner2Desc', 'classificationSearchCode', 'isOriginalClassification', 'aggrLevel', 'isLeaf', 'customsCode', 'customsDesc', 'mosCode', 'motCode', 'motDesc', 'isQtyEstimated', 'isAltQtyEstimated', 'isNetWgtEstimated', 'isGrossWgtEstimated', 'isReported', 'isAggregate'.
  - Remove the NaN value and replacing it with mean(), median(), mode() on columns qtyUnitAbbr, altQtyUnitAbbr, netWgt, fobvalue.
  - Saved the cleaned dataset into the processed repository.

### / Micro Time Series/
This repository contains a cleaned dataset, and during preprocessing, changes are made on the date format via pd.to_datetime() - 
- bitcoin_etherium.csv
- brent_crude_wti.csv
- interest_rate.csv
- usd_index.csv

## *📁 Preprocessing Outputs*

All cleaned datasets are saved in a structured format and reused across the project.

Preprocessed data is directly consumed in the analysis and modeling stages.

The preprocessing workflow ensures reproducibility, consistency, and data integrity.


# Data Analysis
UMESH SINGH
Matriculation No: 58326751
MY Resposiblity involves doing research and downloading data from differenct sources and seggregatated all questions for given weblinks for research and explored further weblinks for further research for entire team followed by conducting a comparative, data-driven analysis of global financial and commodity trends, focusing on Bitcoin trading activity, gold imports, and crude oil imports across major economies. Using cleaned datasets from international trade statistics and cryptocurrency exchanges, the study examines volume dynamics, price trends, and geopolitical groupings such as BRICS versus US–EU economies.

The analysis includes time-series transformation, data reshaping, aggregation, normalization, and visualization to identify structural shifts in global trade and financial behavior. Key insights include the dominance of USD-based Bitcoin exchanges, rising BRICS participation in global gold imports, comparative price movements of gold and crude oil, and a compound annual growth rate (CAGR) analysis of BRICS gold reserves. The results highlight changing patterns in commodity demand, monetary hedging behavior, and alternative asset adoption in the global economy.

⸻

 Key Analytical Components
	Q.How are global financial power shifts reflected across gold reserves, crypto transactions,
Q.Will USD still remain the dominant currency in the World post July 2027?”
• What is the average gold purchase per country per year? (BRICS Member vs US and EU
countries)• What is the trend? Increasing or decreasing or stable?
• How is this connected to USD dominance?
• Which country increased reserves - gold, oil (and BTC) the most in 2024–2025?
• Plot price trend charts for gold, oil and BTC
• What insights do you generate here?
• What is the CAGR of BRICS gold reserves since 2021?


⸻
 Tools & Libraries
	•	Python
	•	Pandas, NumPy
	•	Matplotlib
_____________________________________________________________________________________________________________________________
