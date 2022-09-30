## DoD AFHSD-IB CLI Forecasting Collaboration 

The Armed Forces Health Surveillance Division, Integrated Biosurveillance Branch (AFHSD-IB) is hosting a COVID-like Illness (CLI) forecasting collaboration, in order to provide forecasts for an indicator of COVID-19 disease activity in the DoD population in select US Military Health Service (MHS) markets. The collaboration will utilize ICD coded medical encounters for CLI provided by AFHSD-IB. Each Wednesday, starting October 12th, 2022, participants will provide US market-level forecasts for specific targets related to the burden and trajectory of CLI.

This is the data repository for the DoD AFHSD-IB CLI Forecasting Collaboration (2022-2023).

### Eligibility
All are welcome to participate in this challenge. Participants must complete a Defense Health Agency (DHA) [Memorandum of Agreement (MOA)](https://github.com/cdcepi/DOD-CLI-forecast-data/blob/master/data-surveillance/Disease_Forecasting_Challenge_MOA_23AUG2022.docx) to receive weekly datasets. All datasets will be de-identified and aggregated to the MHS market-level and contain data from January 2020 through the current week. Participants do not need to provide forecasts for all locations or targets to participate. Historical and weekly datasets will be available on Github. An example of the weekly dataset along with a data dictionary have been provided along with this guideline.

### Participation
To participate in the Challenge, please follow these steps:
1. [Request DoD CLI data](./data-surveillance/README.md) by sending a signed Defense Health Agency (DHA) Memorandum of Agreement (MOA) to <dha.ncr.health-surv.mbx.dodflucontest@health.mil>.
2. Prepare [metadata](./data-forecasts/README.md#Data-formatting) for your model.
3. [Submit the forecast](./data-forecasts/README.md#Making-a-submission) by the deadlines.

For information on submitting forecasts to this project, please see the 
[submission instructions](./data-forecasts/README.md). Participating teams provide their 
[forecasts](./data-forecasts/) in [point and quantile-based formats](./data-forecasts/README.md#Data-formatting) that will
be internally evaluated by DoD according to [these specifications](./Evaluation.md). 

### Timeline
- Project announcement and historical data release: Fall 2022.
- Initial forecast due: October 12, 2022.
- Additional forecasts due: following Wednesdays by 11:59pm ET through May 24, 2023.


## Background
COVID-19 disease, caused by the novel 2019 coronavirus, SARS-CoV-2, was declared a pandemic by the WHO on March 11, 2020, with known global spread since January 2020. To provide insight on the burden and trajectory of COVID-19 outbreaks in DoD-relevant locations in the US and globally, AFHSD will undertake a collaborative comparison of CLI medical encounter forecasts. For each week, participants will provide forecasts for the 15 largest MHS markets using DoD service member and beneficiary data. The short-term targets are the percent of outpatient, MTF encounters experiencing CLI one week, two weeks, three weeks, and four weeks ahead from the week of most recently provided data. Forecast results will be compared to the observed weekly CLI percent based on data from the Electronic Surveillance System for the Early Notification of Community-based Epidemics (ESSENCE).


## Data license and reuse
We are grateful to the teams who have generated these forecasts and made their forecast data publicly available under different terms 
and licenses. By default, forecasts are available under the CC-BY 4.0 license, although teams may specify release 
under a different license in their metadata. You will find the licenses (when provided) within the metadata 
contained within model-specific folders in the [data-forecasts](./data-forecasts/) directory. Please consult these 
licenses before using these data to ensure that you follow the terms under which these data were released.
