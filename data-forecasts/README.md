Forecast submission instructions
============================

This page is intended to provide teams with all the information they
need to submit forecasts. 

*Update:* All forecasts should be emailed to <dha.ncr.health-surv.mbx.dodflucontest@health.mil>. 

These instructions provide detail about the [data
format](#Data-formatting) as well as [validation](#Forecast-validation) that
you can do prior to this pull request. In addition, we describe
[metadata](https://github.com/cdcepi/DoD-CLI-forecast-data/blob/master/data-forecasts/METADATA.md) that each model should provide either through email or submitted in a pull request to [data-forecasts/](data-forecasts/).

See the [guidelines](https://github.com/cdcepi/DoD-CLI-forecast-data/blob/main/collaboration-guidelines.docx) and [data-surveillance/](https://github.com/cdcepi/DoD-CLI-forecast-data/tree/main/data-surveillance) folder for 
the ESSENCE CLI case definition and an example data file. 

*Table of Contents*

-   [Data formatting for submission](#Data-formatting)
-   [Forecast file format](#Forecast-file-format)
-   [Making a submission](#Making-a-submission)
-   [Forecast data validation](#Forecast-validation)
-   [Policy on late submissions](#policy-on-late-or-updated-submissions)


Data formatting
---------------

Forecast files submitted to this collaboration should adhere to the below formatting instructions  
to ensure the file can be used in the visualization and ensemble forecasting.

### Subdirectory

Each subdirectory within the [data-forecasts/](data-forecasts/)
directory has the format

    team-model

where

-   `team` is the name of your team and
-   `model` is the name of your model.

Both team and model should be less than 15 characters and not include
hyphens. The `model` should be unique from any other model in the project.

Within each subdirectory, there should be a metadata file, a license
file (optional), and a set of forecasts.

### Metadata

The metadata file should have the following format

    metadata-team-model.txt

and here is [the structure of the metadata
file](https://github.com/cdcepi/DoD-CLI-forecast-data/blob/master/data-forecasts/METADATA.md).

### License (optional)

By default, forecasts are released under a CC-BY 4.0 license. If you would like to release your forecasts under a different license, please specify a [standard
license](../accepted-licenses.csv) in the `license` field of your metadata file. Alternatively, if you wish to use a license that is not in the list of [standard
licenses](../accepted-licenses.csv), you may include a 

    LICENSE.txt

file in your model directory. 

### Forecasts

Each forecast file should have the following
format

    YYYY-MM-DD-team-model.csv

where

-   `YYYY` is the 4 digit year,
-   `MM` is the 2 digit month,
-   `DD` is the 2 digit day,
-   `team` is the name of your team, and
-   `model` is the name of your model.

The date YYYY-MM-DD is the [`forecast_date`](#forecast_date). For this project, the `forecast_date` should always 
be the date that the submission is due.

The `team` and `model` in this file must match the `team` and `model` in
the directory this file is in. Both `team` and `model` should be less
than 15 characters, alpha-numeric and underscores only, with no spaces
or hyphens.

Forecast file format
--------------------

The file must be a comma-separated value (csv) file with the following
columns (in any order):

-   `forecast_date`
-   `target`
-   `target_end_date`
-   `location`
-   `type`
-   `quantile`
-   `value`

No additional columns are allowed.

Each row in the file is a single quantile forecast for a specific location. See the 
[template](./AFHSD_IB_CLI_forecasting_template.csv) for an example.


### `forecast_date`

Values in the `forecast_date` column must be a date in the format

    YYYY-MM-DD

This is the date on which the forecasts were due to be submitted. Note that all due dates fall on Wednesdays.  `forecast_date` should correspond
and be redundant with the date in the filename, and is included here for internal completeness. 

### `target`

Values in the `target` column must be the following character (string):

     "N wk ahead CLI pct" where N is a number between 1 and 4


### `target_end_date`

Values in the `target_end_date` column should be the date in the format 

    YYYY-MM-DD 

This is the date corresponding to the Saturday of the MMWR week of the forecasted value.

### `location`

Values in the `location` column consist of the MHS market name. Name should appear exactly how it appears according to the guidelines Table A.2. column MARKET NAME (For Files). The required location name format can also be found in the [location file](../data-locations/locations.csv).

(Examples: National_Capital_Region, Lejeune_Cherry_Point)


### `type`

Values in the `type` column should all be either the character string "point" or "quantile".

### `quantile`

Values are either "NA" if type="point", or a quantile in the format 0.### if type="quantile". 

This value indicates the quantile for the `value` in this row.

Teams must provide the following 23 quantiles:

    c(0.01, 0.025, seq(0.05, 0.95, by = 0.05), 0.975, 0.99)

    ##  [1] 0.010 0.025 0.050 0.100 0.150 0.200 0.250 0.300 0.350 0.400 0.450 0.500
    ## [13] 0.550 0.600 0.650 0.700 0.750 0.800 0.850 0.900 0.950 0.975 0.990


### `value`

Values in the `value` column are non-negative real numbers indicating the "point" or "quantile" prediction for this row.


Making a submission
---------------

### Initial submission

Contact <dha.ncr.health-surv.mbx.dodflucontest@health.mil> to submit your initial forecast file submission. Metadata and optional license files can be emailed directly or added to this repository using a pull request (see instructions below). 

To prepare for the initial submission, fork this repository and clone it to your computer/work station/etc. In the
forked repository you created, make a [subdirectory](https://github.com/cdcepi/DoD-CLI-forecast-data/blob/main/data-forecasts/README.md#subdirectory) 
for your team in the [data-forecasts/](./) folder following the subdirectory [naming convention](https://github.com/cdcepi/DoD-CLI-forecast-data/blob/main/data-forecasts/README.md#subdirectory). This is where you will place all your metadata, and 
optional license files.

Use a [pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request) 
to create your submission. Open a pull request from your forked repository to the original repo. This will initiate merging your changes into the main repo.
With the pull request, automatic validation checks on file format and content are run. More information on making a pull request can be found 
[here](https://www.freecodecamp.org/news/how-to-make-your-first-pull-request-on-github-3/).



When a pull request is open, you can add/modify files in the pull request by pushing changes from your forked repo. 
This will allow you to address any problems found during the validation checks. Automatic checks run after each push 
so you can check if you were able to resolve the problems listed.

Common reasons for a failed pull request: Excel changing the date format upon saving the .csv, misspelled column headers or keys in the metadata
While pull requests through this repository will not be required for this collaboration, ensuring that these formatting features are correct will aid in forecast interpretation and ensembling.

Pull requests including metadata or license files will be merged as submitted. However, forecast files should be emailed directly to <dha.ncr.health-surv.mbx.dodflucontest@health.mil>.



Forecast validation
-------------------

To ensure proper data formatting, automatic validations are run on all pull requests to
`data-forecasts/`. 

### Pull request forecast validation

When a pull request is submitted, the data are validated through [Github Actions](https://docs.github.com/en/actions) 
which runs the tests present in [the validations repository](https://github.com/reichlab/covid19-forecast-hub-validations). The intent
for these tests are to validate the requirements above. Due to differences between the DOD-CLI forecasting collaboration and other forecasting challenges, forecast files for this collaboration will now be submitted by email <dha.ncr.health-surv.mbx.dodflucontest@health.mil>. Questions and concerns can also be emailed directly. 


Policy on late or updated submissions
------------------

In order to ensure that forecasting is done in real-time, all forecasts are requested to be emailed by the listed [deadlines](https://github.com/cdcepi/DoD-CLI-forecast-data2#timeline). 
