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
