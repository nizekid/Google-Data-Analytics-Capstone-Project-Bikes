# Cyclistic Bike-Sharing Project Analysis 
## Introduction 
this is a capstone project for Google data analytics course from coursera 
took me awhile to actually share my work and edit. Here's my take on this analysis 


## Background 
* I'll be acting as a junior data analyst for a fictionaly company using real-world data.
* Tasks are collecting, analyzing, and reporting data that helps guide the fictional company.
* tools used for this project:
  * Mysql
  * Tableau

## Ask Phase 
### Business task 
- Cyclistic aims to convert the casual riders into members by looking the difference between casual riders adn casual riders. By analysing their differences the marketing team can make a data-driven decision in creating a marketing campaign targeting casual riders.
### Key Questions 
1. How do annual members and casual riders use Cyclistic bikes differently?
2. Why would casual riders buy Cyclistic annual memberships?
3. How can Cyclistic use digital media to influence casual riders to become members?

## Prepare Phase 
- Downloading the historical data from https://divvy-tripdata.s3.amazonaws.com/index.html. 
- The data is separated in YYYYMM title format. the data consist of 12 separated CSV files. the downloaded files is from 2023
- The data was stored in a folder with apporiate name.
- according to the [license](https://divvybikes.com/data-license-agreement) provided by Motivate International Inc. it is stated under the [license](https://divvybikes.com/data-license-agreement)
  - THE DATA IS PROVIDED “AS IS,” AS AVAILABLE (AT BIKESHARE’S SOLE DISCRETION) AND AT YOUR SOLE RISK. TO THE MAXIMUM EXTENT PROVIDED BY LAW BIKESHARE DISCLAIMS ALL WARRANTIES, EXPRESS OR IMPLIED, INCLUDING THE IMPLIED WARRANTIES OF MERCHANTABILITY FITNESS FOR A PARTICULAR PURPOSE, AND NON-INFRINGEMENT. BIKESHARE FURTHER DISCLAIMS ANY WARRANTY THAT THE DATA WILL MEET YOUR NEEDS OR WILL BE OR CONTINUE TO BE AVAILABLE, COMPLETE, ACCURATE, TIMELY, SECURE, OR ERROR FREE.
  - Bikeshare hereby grants to you a non-exclusive, royalty-free, limited, perpetual license to access, reproduce, analyze, copy, modify, distribute in your product or service and use the Data for any lawful purpose (“License”).
 
## Process Phase
### Excel
After downloading the dataset for analysis. I first examine each data set which in this case, each CSV file is titled with the date formatted in (YYYY/MM). After examining that they all have the same column names, I proceeded in combining and exploring the data in SQL (MySQL) due to Excel's limited capacity in handling large amounts of data .
### SQL: MySQL 
Data Exploration:  


