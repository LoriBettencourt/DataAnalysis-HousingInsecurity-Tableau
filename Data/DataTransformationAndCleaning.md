# Data Transformation and Cleaning
## Data Sources

Kaggle: [Homelessness](https://www.kaggle.com/datasets/adamschroeder/homelessness)
* [2007-2016-Homelessness-USA.csv](https://www.kaggle.com/datasets/adamschroeder/homelessness?select=2007-2016-Homelessnewss-USA.csv)

    This data set contains data on housing insecurity for the years 2007 through 2016. It is provided in long format and has 86529 observations.
* [Population-by-state.csv](https://www.kaggle.com/datasets/adamschroeder/homelessness?select=Population-by-state.csv)  
    If I end up blending [Homelessness](https://www.kaggle.com/datasets/adamschroeder/homelessness) with [hud_pit_by_coc](bigquery-public-data.sdoh_hud_pit_homelessness.hud_pit_by_coc), I will need an additional file to supplement this data. 

Big Query Public Data
bigquery-public-data/sdoh_hud_pit_homelessness.hud_pit_by_coc: [Access from Google Cloud](https://console.cloud.google.com/bigquery)

* This source contains data on housing insecurity for the years 2012 through 2018. For the purpose of this study, providing both detail files contain comprable data, only data from 2017 and 2018 will be used from this data set. Will consider blending data from this set once Tableau dashboard is up and running. It is in wide format.

Confirmed that years data is reported on matches between both sources by comparing Total Homeless (Overall_Homeless) values for states and then drilling to to compare other values as well.

SELECT * 
FROM `bigquery-public-data.sdoh_hud_pit_homelessness.hud_pit_by_coc` 
WHERE Count_Year IN (2017, 2018)
ORDER BY Coc_Number

Returned 795 observations and these were all exported to [BigQueryData2017_2018.csv](BigQueryData2017_2018.csv) without failing due to download size.

## Cleaning using Excel
### Results will be stored Homeless tab of HousingInsecurityWorkbook.xlxs
From 2007-2016-Homelessness-USA.csv prepped in HomelessnessPrepped.xlxs
* No duplicate rows were found.
* Checked for missing values with conditional formatting.
* All observations are on January 1st of the year.
* Extracted and retained just the "Year" from the Year column containing the observations date. Kept "Year" heading.
* Removed observations for 2007, 2008, 2009
* Kept only observations with values of "Sheltered Homeless", "Totally Homeless", "Unsheltered Homeless"
* Checked for leading and trailing white space in State.  
    =TRIM([@[State_bef_Trim]])
* Count of unique state values is 54:
    50 U.S. States 
    DC - Disctric of Columbia (Washington D.C.) and the territories of 
    GU - Guam
    PR - Puerto Rico
    VI - Virgin Islands
    Deleted Guam, Puerto Rico, and Virgin Island rows to limit observations to the 50 U.S. states and D.C.
* 8322 observations remain.
* Pivot on measures 8322/3 = 2774 rows.

* Loaded 2007-2016-Homelessnewss-USA.csv file into Google Cloud Console.  
    * Checked for distinct "Measures" of homelessness. Found no values with leading or trialing white space. 
    SELECT DISTINCT Measures  
    FROM `green-link-358414.housing_insecurity.2007To2016`  
    ORDER BY Measures;  
    * Confirmed that for each CoC_Number, there is only one corresponding CoC_Name.  
    SELECT t1.CoC_Number, t1.CoC_Name  
    FROM `green-link-358414.housing_insecurity.2007To2016` t1  
    JOIN `green-link-358414.housing_insecurity.2007To2016` t2  
    ON t1.CoC_Number = t2.CoC_Number  
    AND t1.CoC_Name != t2.CoC_Name  
    GROUP BY t1.CoC_Number, t1.CoC_Name;  
    * Checked that all states where matched to an appropriate Coc_Number.  
    SELECT State, CoC_Number  
    FROM `green-link-358414.housing_insecurity.2007To2016`  
    WHERE State != SUBSTR(Coc_Number,1,2)  
    ORDER BY State, CoC_Number;  

### Results will be stored Population tab of HousingInsecurityWorkbook.xlxs
From Population-by-state.csv prepped in PopulationByStatePrepped.xlxs
* ID Column deleted as it add no values for us.
* "State ID" column deleted.
* "State Abbr" values copied to new column without VLOOKUP function code.
* "State Name" deleted. 
* Deleted "April 1, 2010 - Census" and "April 1, 2010 - Estimates Base" columns as we will be using the July population estimates for each year.
* Population estimates as of 7/1 of each year for that year. Changed column headings for fields with population counts to just the year of the estimate.
* Cast population values in aforementioned date columns as Number.
* Changed column headings to be more appropriate
* No duplicate observations were found
* "State abbr" sheet was created so that we can use state abbreviations when joining with Homelessness2007_2016.xlxs. Used VLOOKUP to populate a "State" column
* Count of unique state values is 52:
    50 U.S. States 
    DC - Disctric of Columbia (Washington D.C.) and the territory of 
    PR - Puerto Rico
    Deleted Puerto Rico row to limit observations to the 50 U.S. states and D.C.
* 51 observations remain.
* Changed table format to long with three columns: "Year", "State", "Population".
