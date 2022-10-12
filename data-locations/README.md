Locations
============================

This folder contains a comma-separated file `locations.csv` that contains location-specific data for the 15 Military Health System (MHS) markets included in the DoD CLI forecasting collaboration.

Columns:

- `MARKET NAME (FORMAL)` is the formally recognized MHS market name.
- `MARKET NAME (FOR FILES)` is an adapted version of the MHS market name using "_" in place of other special characters.
- `location` is a character string matching `MARKET NAME (FOR FILES)`. This is the variable that should be included in forecast submissions. 
For example, "San_Antonio" or "Lewis_McChord". Forecast submissions will be 
checked to ensure that location names match those found in this csv file.
- `population` is a variable used in the submission validation process. Since forecasting targets for this collaboration are % CLI values, the validation process will check that submitted values are less than or equal to 100. 

Additionally, the [MHS-Markets_Counties spreadsheet](https://github.com/cdcepi/DOD-CLI-forecast-data/blob/master/data-locations/MHS-Markets_Counties-within-30-miles.xlsx) provided in this folder documents the counties that are located within 30 miles of each of the MHS Market forecasting locations. Corresponding states and FIPS codes are also included.  
