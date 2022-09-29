## DoD CLI surveillance data

This page provides teams with information on the surveillance data provided to participating teams.


## Data use

All participants must sign a [Memorandum of Agreement (MOA)](https://github.com/cdcepi/DOD-CLI-forecast-data-blob/data-surveillance/Disease_Forecasting_Challenge_MOA_23AUG2022.docx) to receive the aggregated data elements weekly during the forecasting period. Questions and correspondence, including submitting the MOA, should be sent to <dha.ncr.health-surv.mbx.dodflucontest@health.mil>. Once the MOA is in place, AFHSD-IB will notify participants by email to download the DoD data from GitHub. Once the MOA is signed and executed, historical ESSENCE surveillance data may be used for training and model development. Teams are welcome and encouraged to utilize additional data beyond the provided ESSENCE data.


## Data Dictionary
Data consist of weekly aggregate counts of CLI medical encounters for the 15 largest MHS markets based on DoD service member and beneficiary data. CLI forecasts should be based on the ESSENCE CLI definition as specified in Table A.1 of the [guidelines](https://github.com/cdcepi/DoD-CLI-forecast-data/blob/main/collaboration-guidelines.docx). The short-term targets are the percent of outpatient, MTF encounters experiencing CLI one week, two weeks, three weeks, and four weeks ahead from the week of most recently provided data. A detailed description of the 
fields included in the csv file is included below.

### `forecast_date`
Date in the format YYYY-MM-DD corresponding to the Wednesday of the forecast submission.

### `target`
Character string of "N wk ahead CLI pct" where N is a number between 1 and 4.

### `target_end_date`
Date in the format YYYY-MM-DD corresponding to the Saturday of the MMWR week of the forecasted value.

### `location`

MHS market name. Name should appear exactly how it appears in the [guidelines](https://github.com/cdcepi/DoD-CLI-forecast-data/blob/main/collaboration-guidelines.docx) Table A.2. column MARKET NAME (For Files).

(Examples: National_Capital_Region, Lejeune_Cherry_Point)


### `type`

Character sting of "point" or "quantile".

### `quantile`

Values are either "NA" if type="point", or a quantile in the format 0.### if type="quantile". Quantiles to be provided by each team: {0.01, 0.025, 0.05, 0.10, 0.15, 0.20, 0.25, 0.30, 0.35, 0.40, 0.45, 0.50, 0.55, 0.60, 0.65, 0.70, 0.75, 0.80, 0.85, 0.90, 0.95, 0.975, 0.99}

### `value`
Non-negative number indicating the "point" or "quantile" prediction.

