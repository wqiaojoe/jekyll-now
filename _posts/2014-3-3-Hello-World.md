---
layout: post
title: Chicago Crime Data and Census Data Insight
published: true
---

## Table of contents
* [Introduction](#introduction)
* [Data](#data)
* [Methodology](#method)

## Introduction <a name="introduction"></a>
Crime rate is believed to be highly related to economy. The economic crisis that happened in 2008 is the turning point of the world’s economy. Therefore, it is meaningful to study whether this turning point has affected the crime rate from the real data and how crime rate may affect the local economy.
This project has chosen one of the metropolises in the US, Chicago as the investigation object. The time span of interest is 9 years spanning the year of 2008. The objective of the project is to provide an insight of the crime data scraped from Chicago Data Portal and conclude the impact of 2008 crisis on Chicago's crime rate. Additionally, the census data of Chicago from 2008 to 2012 will be studied to find out the impact of crime on the households’ financial situation of individual community. 
The target audience of the project with its elaborate visualisation results will benefit any groups of audiences who are interested in economy-crime topic or those who are concerned about crime rate when doing investment or business such as real estate and small business.
The rest of the report consists of the following parts. Data section includes data collection and data preparation. In Methodology section, the detailed data analysis methods adopted in the project will be demonstrated. An analysis of the results obtained as well as some discussion and findings will be discussed in the Results and Discussion section followed by the Conclusion section.

## Data <a name="data"></a>
This section will introduce what the required data is, where and how the data is collected and how it has been cleaned and prepared for later use.
### Understanding the Datasets

This project will be using two datasets that are available on the city of Chicago's Data Portal:

+ [Chicago Crime Data](https://data.cityofchicago.org/Public-Safety/Crimes-2001-to-present/ijzp-q8t2)

This dataset reflects reported incidents of crime (with the exception of murders where data exists for each victim) that occurred in the City of Chicago from 2001 to present, minus the most recent seven days. Data is extracted from the Chicago Police Department's CLEAR (Citizen Law Enforcement Analysis and Reporting) system.
    
Chicago Crime Data will be used to obtain a comprehensive understanding of crime rate from 2004 to 2012 including the trend, types of crimes, crime rate of different communities and so on. Data visualization will help to achieve this goal. Census data of all the communities of Chicago will be jointly considered to give a clear picture of the connection of community population and income to crime rate of that area.

The Chicago Crime Data contains 22 features as shown in the results of the following Python code. The primary features we are interested in are listed below:
	
- **YEAR** Year the incident occurred.
- **PRIMARY_TYPE** The primary description of the IUCR code.
- **COMMUNITY_AREA_NUMBER** Indicates the community area where the incident occurred. Chicago has 77 community areas.
- **LOCATION_DESCRIPTION** Description of the location where the incident occurred.
- **LATITUDE** The latitude of the location where the incident occurred.
- **LONGITUDE** The longitude of the location where the incident occurred.

+ [Census Data - Socioeconomic Indicators in Chicago](https://data.cityofchicago.org/Health-Human-Services/Census-Data-Selected-socioeconomic-indicators-in-C/kn9c-c2s2)

This dataset contains a selection of six socioeconomic indicators of public health significance and a “hardship index,” by Chicago community area, for the years 2008 – 2012. The indicators are the percent of occupied housing units with more than one person per room (i.e., crowded housing); the percent of households living below the federal poverty level; the percent of persons in the labor force over the age of 16 years that are unemployed; the percent of persons over the age of 25 years without a high school diploma; the percent of the population under 18 or over 64 years of age (i.e., dependency); and per capita income. Indicators for Chicago as a whole are provided in the final row of the table.

The Census Data has 9 features and the following are essential to this project:
- **COMMUNITY_AREA_NUMBER** Indicates the community area where the incident occurred. Chicago has 77 community areas.
- **COMMUNITY_AREA_NAME** Community actual name
- **PERCENT HOUSEHOLDS BELOW POVERTY** Percent of households living below the federal poverty level
- **PER_CAPITA_INCOME** Community Area Per capita income is estimated as the sum of tract-level aggregate incomes divided by the total population

### Data Collection and Data Preparation

Both datasets are available in Chicago Data Portal. To get the full dataset, one is able to extract it through Chicago API, powered by Socrata. As the project is interested in a certain period (9 years spanning 2008), crime data of year 2004 to 2012 has been extracted from the database, which contains 3686677 rows and 22 columns. In contrast, Census Data available officially is only from 2008 to 2012 and is relatively small.

The first step of the preparation of both datasets is to filter the interested features which has been introduced in the beginning of the section. After filtering, NaN rows in Chicago Crime Data have been dropped and proper data types have been redefined for features such as community area number, latitudes and longitudes. Similar cleaning work was done to Census Data. For convenience, the names of common features of both datasets are kept consistent.

![Figure1.PNG]({{site.baseurl}}/_posts/Figure1.PNG)
![Figure2.PNG]({{site.baseurl}}/_posts/Figure2.PNG)









