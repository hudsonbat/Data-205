# Predicting Crime in Montgomery County, MD

The following analysis of crime in Montgomery County, MD is based on a dataset from Data Montgomery entitled, “Crimes”, as well as data obtained from the U.S. Census Bureau and the Federal Communications Commission (FCC). While the “Crimes” dataset was downloaded as a comma-separated values (CSV) file directly from the Data Montgomery data catalog, the FCC data was obtained through the FCC Application Programming Interface (API) and the Census Bureau data was obtained through the Census API. The analysis can be broadly separated into two modeling tasks: A multi-class classification task in which the goal was to predict the 3 general NIBRS crime categories based on census data and crime data, and a time-series regression task in which the objective was to predict the number of crimes that would occur the following day and week based on historical crime data and according to location if possible.

Datasets
1. Crimes Dataset Link: https://data.montgomerycountymd.gov/Public-Safety/Crime/icn6-v9z3
2. Census Bureau ACS Data Link: https://api.census.gov/data/2019/acs/acs5?get=NAME,B01001_001E,B01002_001E,B19013_001E,B08301_001E,B08301_010E,B15003_001E,B15003_017E,B15003_022E,B23025_003E,B23025_005E&for=block%20group:*&in=state:24&in=county:031&in=tract:*
3. Census Bureau Shapefile Link: https://www2.census.gov/geo/tiger/GENZ2018/shp/
4. FCC Data Link: https://geo.fcc.gov/api/census/#!/area/get_area

Files/Notebooks
1. MCCrime_Block.ipynb: Fetches data from Census API and from FCC API and merges the crimes dataset with the census data on the basis of the geocode (block ID) obtained from the latitude and longitude coordinates of each crime. Does so in batches of 20,000 crimes.
2. CapstoneEDA.ipynb: Exploratory Data Analysis of the merged crimes and census data datasets
3. Crime_Clean.csv: CSV file of the merged data (* Note that this is the original merged CSV file but the subsequent one was too large to upload to github)
4. CapstoneMaps.ipynb: Notebook exploring census variables using maps of Montgomery, County.
5. Crime_Forecasts_Day.ipynb: Forecasting models of crime numbers by crime type by day.
6. Crime_Forecasts_Location.ipynb: Forecasting models of crime numbers by crime type by week.
7. Crime_Forecasts_Total.ipynb: Forecasting models of crime numbers by crime type and location by week.
8. FINAL! Capstone Presentation.pptx: Final presentation of project
9. MCCrime_NN.ipynb: Multi-input neural network model of general NIBRS crime classes using class balanced data. Includes metrics as well.
10. MCCrime_NN2.ipynb: Multi-input neural network model of general NIBRS crime classes using class imbalanced data. Includes metrics as well.
11. MCCrime_Trees.ipynb: Comparison of models of the general NIBRS crime categories using class balancing and ommitting class balancing. Contains hyperparameter-optimized Random Forest and Gradient Boosted Tree models along with corresponding classification metrics.


