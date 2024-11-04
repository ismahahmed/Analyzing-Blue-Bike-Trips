# Analysis of Boston Blue Bikes Data in 2019

Data for this project can be found on [kaggle](https://www.kaggle.com/datasets/jackdaoud/bluebikes-in-boston). 

## Introduction
### Data Origin and Overview
Blue Bikes, formerly known as Hubway, is a public bike-sharing system across the metropolitan areas of Boston. Participating individuals can either be Blue Bike members (including annual or monthly members) or casual single-trip day pass users. Blue Bikes publishes downloadable files of trip user data each quarter, and for this analysis, I will be using the compiled 2019 dataset from Kaggle in addition to the station dataset published by Blue Bikes.

The data set from Kaggle was originally retrieved from Blue Bikes and then compiled and collected for the year 2019. Blue Bikes also publishes downloadable files of station data, I will be joining the 2019 trip data from Kaggle with the station data to analyze municipality data. Both datasets used in this analysis was downloaded as CSV files and read as a dataframe in R.

## Goal of Analysis
By leveraging this comprehensive data set, I aim to uncover insightful patterns associated with bike rental usage in Boston. For this analysis, I am interested in taking a deeper look at short trips (trip duration of 2 hours or less). It’s noteworthy that the overwhelming majority of data in the Blue Bikes dataset for 2019 comprises trips lasting under 2 hours. Trips exceeding this threshold accounted for less than 1% of the data, specifically 0.649%.

This investigation will encompass various areas, including the examination of trip duration across different districts, the identification of key districts driving Blue Bike rental demand, and the assessment of the distribution of total trip volume throughout the year. Additionally, I have conducted an analysis of applying statistical principles such as the central limit theorem to gain a deeper understanding of the distribution of trip duration. I will also explore various sampling methods to determine which provides the most accurate representation of our population data.

In the ‘Analysis’ section of this document, you will encounter a variety of plots, visualizations, and analyses focusing on different aspects of the Blue Bikes dataset. Within this section, I delve into the intricacies of the dataset and uncover underlying patterns.

## Data Prep

The user trip dataset includes 17 columns and over 2 million rows while the Blue Bikes station dataset includes 5 columns and 421 rows. For this analysis, I am interested in understanding patterns for those individuals who rented a bike for short trips, specifically 2 hours or less. To ensure the integrity of our analysis, I will be excluding instances of longer rental durations from the dataset.

**New columns I will be adding:**

- `tripduration_minutes` :  The dataset currently only has a trip duration column in seconds, I will be creating a new column to get the duration in minutes
- `day` : The data only has month and year column. I will be creating a day column
- `date` : This will be the date of started trip without a time stamp

In order to provide a concise analysis of some of these attributes, cleaning up the data is necessary. This includes changing data types and removing unneeded rows (trips over 2 hours). I will also be adding a new column `tripduration_minutes` which uses the `tripduration` column (shown in seconds) to convert trip duration to minutes. Finally, I will be joining the 2019 trip data set with the station dataset using the station name variable from both tables. After the tables are joined, I will delete duplicate columns.

I used the following R libraries/packages to conduct this analysis: `readr`, `knitr`, `kableExtra`, `tidyverse`, `plotly`, `sampling` and `leaflet`

*Note: Some values may produce an NA value when joining. This may be because the station data is more recently updated than the trip data set (from 2019). When analyzing this data in our analysis, later on, we will omit NA.*

***
<details>
  <summary>Click here to learn more about the attributes in the data we will be analyzing</summary>
  
  *Source: Information on the attributes found on [Blue Bikes](https://bluebikes.com/system-data) and [Kaggle](https://www.kaggle.com/datasets/jackdaoud/bluebikes-in-boston)*
  
 - `tripduration` : duration of a bike trip in seconds
 - `tripduration_minutes` : column added for analysis. duration of bike trip in minutes
 - `starttime`: timestamp of start time of trip
 - `stoptime` : timestamp of end time of trip
 - `start station id` : unique stationID where trip started
 - `start station name` : name of the station at start of trip
 - `start station latitude` : latitude of start station
 - `start station longitude` : longitude of start station
 - `end station id` : unique stationID where trip ended
 - `end station name` : name of station at end of trip
 - `end station loatitude` : latitude of end station
 - `end station longitude` : longitude of end station
 - `bikeid` : unique ID of bike used for the trip
 - `usertype` : Customer (casual single trip or day pass user) or Subscriber (annual or monthly member)
 - `year` : year when trip took place, for our data, this will all be 2019
 - `month` : month when trip took place (numerical 1-12)
 - `day` : created column, day of month trip took place
 - `date` : created column, date of trip in YYYY-MM-DD format
 - `birth year` : birth year of user, this is self reported
 - `gender` : gender of user, this is self reported
 - `start_district` : district at start of trip. Boston, Brookline Cambridge, Everett, Somerville or NA
 - `start_total_docks` : total number of docs at start of trip 
 - `end_district` : district at end of trip. Boston, Brookline Cambridge, Everett, Somerville or NA
 - `end_total_docks` : total number of docs at end of trip 
 
</details>

***

Below I included some of the plots generated in the markdown file

![newplot](https://github.com/user-attachments/assets/785218aa-e13e-4a4f-9832-101aba71ef02)
![image](https://github.com/user-attachments/assets/1e2fa334-1c3c-4f66-b4ad-0321c0179371)
![newplot (2)](https://github.com/user-attachments/assets/ae0a2391-53c0-4936-aa3b-2a3a424d8ba9)



