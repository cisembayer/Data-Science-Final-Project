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
MY Responsiblity involves doing research and downloading data from differenct sources and seggregatated all questions for given weblinks for research and explored further weblinks for further research for entire team followed by conducting a comparative, data-driven analysis of global financial and commodity trends, focusing on Bitcoin trading activity, gold imports, and crude oil imports across major economies. Using cleaned datasets from international trade statistics and cryptocurrency exchanges, the study examines volume dynamics, price trends, and geopolitical groupings such as BRICS versus US–EU economies.

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

## Santosh Doddaiah

### Purpose:

To analyze SWIFT global payment currency shares and compare USD vs BRICS (R5 proxy) using official SWIFT RMB Tracker PDFs.

### Data Source:

Raw SWIFT RMB Tracker reports stored in:
data/RAW/Swift/ (rmb-tracker_*.pdf)

### Method / Steps Used:

Extracted “Global payments by currency (%)” table from SWIFT PDFs using pdfplumber

Parsed currency share values (USD, EUR, GBP, JPY, CNY, etc.) using regex

Created a structured dataset (monthly shares) using pandas

Converted monthly data into quarterly averages

Computed the Herfindahl Index (HHI) to measure payment concentration

Identified the largest quarterly shift in USD share

Generated plots using matplotlib

### BRICS Assumption:

SWIFT reports do not provide a combined R5 (BRICS) currency share. Hence, the CNY share is used as an R5 proxy.

## Outputs Generated 
### Tables:

swift_currency_share_monthly_extracted.csv → Extracted monthly currency shares from SWIFT PDFs

swift_currency_share_quarterly.csv → Quarterly averages + HHI + USD shift

### Figures:

usd_share_quarterly.png → USD quarterly trend

eur_share_quarterly.png → EUR quarterly trend

r5_proxy_share_quarterly.png → BRICS (CNY proxy) quarterly trend

---------------------------------------------------------------------------------------------------------------------
### Ajay 

### Purpose:
To analyze BTC trading dynamics by examining USD dominance (proxy), identifying which trading gateways are gaining/losing relevance, and checking macro impact using DXY and interest rates.

### Data Source:
Processed datasets used:

data/processed/Gold and Crude_Petrol/bitcoinity_cleaned.csv

data/processed/USD_Index/US_Dollar_Index_cleaned.csv

data/processed/Micro Time Series/Interest Rate/interest_rate.csv

### Method / Steps Used:

Loaded weekly BTC trading volumes from bitcoinity_cleaned.csv

Computed total BTC volume across exchanges

Created USD proxy dominance using (Coinbase + Bitstamp share %)

Generated exchange/gateway relevance summary for 30 days / 6 months / 1 year

Resampled BTC dominance to monthly and merged with:

US Dollar Index (DXY)

Fed Funds Rate

Computed correlation matrix between BTC USD-proxy share, DXY, and Interest Rate

Generated plots using matplotlib

### Assumption:
The 
Bitcoinity dataset contains exchange-level BTC volumes (not direct fiat volume). Therefore, Coinbase + Bitstamp are used as a USD trading gateway proxy.

### Outputs Generated (Saved in data/outputs/BTC_Dynamics/)
### Tables:

btc_usd_proxy_dominance_timeseries.csv → USD proxy dominance time-series

gateway_share_windows_summary.csv → Gateway relevance (30d / 6m / 1y)

btc_macro_merged_monthly.csv → BTC dominance merged with DXY + Interest Rate

btc_macro_correlation_matrix.csv → Correlation results

### Figures:

usd_proxy_dominance_trend.png → USD proxy dominance trend over time

top5_gateways_share_trend.png → Top 5 gateway share trend

usd_share_vs_dxy.png → USD proxy dominance vs DXY trend

---------------------------------------------------------------------------------------------------------------------

### Deekshith Hunsur Shekar 

### Analysis 1:

### Purpose:
Gold Imports vs USD Index – Correlation and Forecasting:
To analyze the relationship between India’s gold import dynamics and the strength of the US Dollar by:
- Tracking trends in gold import CIF values over time
- Comparing gold imports with the US Dollar Index (DXY)
- Assessing whether gold imports rise when the USD weakens
- Building simple baseline forecasts for future gold (and crude oil) imports

### Data Source:
Processed datasets used:

data/processed/Gold_Imports/Gold_Import_TradeData_clean_final.csv

data/processed/USD_Index/US_Dollar_Index_cleaned.csv

(Optional, for forecasting) data/processed/Crude_Oil/Crude_Oil_TradeData_clean_final.csv

### Method / Steps Used:

Method / Steps Used:
- Loaded gold import data (CIF values) and DXY index data from cleaned CSVs
- Parsed date fields and converted numeric fields (cifvalue, Price) to appropriate types
- Aggregated gold imports:
	- Monthly: summed CIF values by month for descriptive trend plots
	- Yearly: summed CIF values by year for correlation with DXY
- Aggregated USD index:
	- Filtered data to 2019–2024
	- Monthly: computed average DXY per month
	- Yearly: computed average DXY per year
- Merged yearly gold imports and yearly DXY data on year
- Computed correlation between:
	- Yearly gold CIF sum
	- Yearly average USD index
- Visualized:
	- Monthly gold imports trend (CIF value over time)
	- Monthly USD index trend (2019–2024)
	- Dual-axis yearly chart: gold imports vs. USD index
- (Forecasting component)
	- Fitted simple linear trends / moving averages to yearly gold and crude oil imports
	- Extended trends into future years as baseline forecasts
	- Generated corresponding forecast charts for gold and crude oil imports

### Assumption:
The analysis treats:

Gold CIF values as a proxy for overall gold import intensity/demand.
US Dollar Index (DXY) as the primary measure of USD strength/weakness against a basket of major currencies.
It assumes that if gold imports systematically increase when DXY falls (and vice versa), this can be interpreted as evidence of an inverse relationship between USD strength and gold import demand, while recognizing that other macro and policy factors may also drive imports.

### Outputs Generated (Saved in data/outputs/BTC_Dynamics/)
### Tables:

data_analysis/Deekshith_contribution/Tables/gold_usd_index_corr_table.xlxs - Correlation between gold imports and USD index

### Figures:

data_analysis/Deekshith_contribution/Figures/gold_imports_by_year_fig.pdf
data_analysis/Deekshith_contribution/Figures/usd_index_by_year_fig.pdf
data_analysis/Deekshith_contribution/Figures/Gold_purchase_vs_USD_index_fig.pdf

### Conclusion:
- Gold imports show a steady increase from 2019 to 2024.
- The USD Index weakens from 2019–2021 and strengthens again from 2022–2024.
- 2019–2021: Gold imports rise while the USD weakens → consistent with the idea that gold buying increases when USD is weaker.
- 2021–2024: Gold imports keep rising even as the USD strengthens → other factors beyond USD strength are driving gold imports.
- Overall, with only six yearly data points, the correlation is weak/ambiguous, so USD movements alone cannot explain gold import trends.


### Analysis 2:

The methodology is same for both Gold imports and Crude oil petroleum imports forecasts.
### Purpose:
To build a simple baseline forecast for total gold import and crude oil Petroleum import of all countries combined CIF values by:
- Aggregating gold imports across all countries
- Fitting a linear regression on yearly totals
- Extrapolating the trend into the next 5 years
- Visualizing historical vs. fitted vs. forecasted values

### Data Source:
Processed datasets used:

data/processed/Gold_Imports/Gold_Import_TradeData_clean_final.csv
data/processed/Crude_Oil/crude_pertroleum_import.csv

### Method / Steps Used:

Method / Steps Used:
- Loaded cleaned gold import data (Gold_Import_TradeData_clean_final.csv)
- Grouped data by refYear, summing cifvalue across all countries to obtain yearly total CIF value
- Prepared:
	- Feature: X = refYear (year as numeric)
	- Target: y = cifvalue (total yearly CIF value)
- Fitted a linear regression model using refYear to predict cifvalue
- Generated future years for the next 5 years beyond the last available year in the dataset
- Used the fitted model to predict gold import CIF values for these future years
- Created a combined visualization showing:
	- Historical actual values (scatter, blue)
	- Fitted linear trend over the historical period (line, red)
	- Forecasted values for future years (dashed line, green)

### Assumption:
This forecasting approach assumes that:
- The historical linear growth in total gold/crude oil petroleum import CIF values will continue unchanged into the next 5 years.
- There are no structural breaks or major shocks (e.g., policy changes, crises, price spikes, or sudden demand shifts) that would significantly alter the trend.
- Using refYear alone as the predictor is sufficient for a baseline, directional forecast; it does not incorporate macroeconomic drivers, prices, or exchange rates.
Therefore, the resulting forecast should be interpreted as a simple trend-based baseline, not a precise prediction.

### Outputs Generated (Saved in data_analysis folder)
### Tables:

data_analysis/Deekshith_contribution/Tables/predicted_forecast_Crude_petrol_imports_table.xlxs
data_analysis/Deekshith_contribution/Tables/predicted_forecast_gold_imports_table.xlxs

### Figures:

data_analysis/Deekshith_contribution/Figures/Crude_oil_petrol_imports_forecast_by_year_fig.pdf
data_analysis/Deekshith_contribution/Figures/Gold_imports_forecast_by_year_fig.pdf

### Conclusion

Gold Imports – Forecast Conclusion
- Gold imports have been rising steadily in recent years.
- The simple trend forecast suggests they will continue to increase over the next few years.
- The expected yearly increase is roughly in the range of 4.5–5.0 × 10¹⁰ in CIF value.
- This is a basic, linear forecast and does not account for shocks or policy changes.
- Use it as a rough direction (upward trend), not as an exact prediction.

Crude Oil (Petroleum) Imports – Forecast Conclusion
- Crude oil imports also show a strong upward historical trend.
- The forecast indicates continued growth in crude oil import values.
- The expected yearly increase is about 1.0–1.1 × 10¹¹ in CIF value.
- The method is simple and ignores factors like global prices or geopolitical risks.
- Treat the results as a baseline indication of continued growth, not a precise forecast.


