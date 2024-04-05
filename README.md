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
### 1. Combining Data 
- Combining the Monthly table to one Table called tripdate_2023. 
  - ![Combining union](https://github.com/nizekid/Google-Data-Analytics-Capstone-Project-Bikes/assets/146612858/b1934241-ef1f-4a4c-9cb5-4bc6432b46e4)
### 2. Data Exploration  
- Checking the total number of rows in the tripdata_2023
  - ![combining data](https://github.com/nizekid/Google-Data-Analytics-Capstone-Project-Bikes/assets/146612858/9e999af2-6b32-46b4-a27d-e0f907fc87cd)
- Checking the length of the [ride_id].
  - ![lens](https://github.com/nizekid/Google-Data-Analytics-Capstone-Project-Bikes/assets/146612858/b2a48535-64ef-468a-9df8-d996aaa8d988)
- Checking how many nulls in each column of the tripdata_2023
  - ![null columns](https://github.com/nizekid/Google-Data-Analytics-Capstone-Project-Bikes/assets/146612858/7b3fce66-7f4e-4cca-8d6c-8a4ce3128af9)
- Checking the total number of nulls in the tripdata_2023
  - ![nulls](https://github.com/nizekid/Google-Data-Analytics-Capstone-Project-Bikes/assets/146612858/555bd015-16d5-4bd9-9a79-a69f6ce0e134)
- Checking the total number of outliers in the combined_Table (Ride duration more than 1 day and ride duration less than 1 minute) 
  - ![outliers](https://github.com/nizekid/Google-Data-Analytics-Capstone-Project-Bikes/assets/146612858/694b5243-e7c1-42a4-88cc-68a277140ea7)
- Total number of nulls values and outlier values in the combined_Table (Ride duration more than 1 day and ride duration less than 1 minute)  the result of this query is not adding up to the queries above due to some are falling under the same row as the null values with the outliers
   - ![total inconsistent data](https://github.com/nizekid/Google-Data-Analytics-Capstone-Project-Bikes/assets/146612858/c2e441b6-9ebc-4011-9e5a-935175c640f2)
### 3. Data Cleaning  
- Deleting the outliers in the data
  - ![Outliers](https://github.com/nizekid/Google-Data-Analytics-Capstone-Project-Bikes/assets/146612858/9158977e-41fe-4fe8-90b6-2b91935c72a7)
- Total number of rows after deleting outliers 
  - ![Total after delete outlier](https://github.com/nizekid/Google-Data-Analytics-Capstone-Project-Bikes/assets/146612858/d1765bbc-e8d6-4b6f-9962-d0106790cd06)
- Deleting different number of characters used in the [ride_id] that is not 16 in characters 
  - ![Deleting len](https://github.com/nizekid/Google-Data-Analytics-Capstone-Project-Bikes/assets/146612858/eae35836-02aa-43ce-9843-e7977c2e9d63)
- Deleting the null values in the data 
  - ![deleting nulls](https://github.com/nizekid/Google-Data-Analytics-Capstone-Project-Bikes/assets/146612858/7ef23ee6-92ab-464f-83c1-68268546a5d7)
- Total number of rows after deleting null values
  - ![total number after deleting inconsistent](https://github.com/nizekid/Google-Data-Analytics-Capstone-Project-Bikes/assets/146612858/7e4ea95e-45d6-4c1d-92f6-6da896f3e057)
### 4. Data Transformation   
- Adding column name Month into the Combine data and inserting values 
- Adding column name days into the Combine data and inserting values 

## Analyze Phase 
For this phase i extracted some of the following data to answer the business questions: 
- Total Number of Members vs Casual
- Number of Rideable bikes used by Members and Casual
- Volumes of Members and Casual riders per Month/Season/days
- Volumes of Members and Casual Riders per Hour
- Average Trip Duration of Members per Month/Days/Days
- Top Start Startion and End Station of Members and Casual

## Share Phase 

![Member vs Casual](https://github.com/nizekid/Google-Data-Analytics-Capstone-Project-Bikes/assets/146612858/cad074a2-35b0-492f-9434-a603b2c226de)
- there are 35% of casual rider
  - there's a lot of potential members that the Cyclistic Company 
 
![Rideable bikes](https://github.com/nizekid/Google-Data-Analytics-Capstone-Project-Bikes/assets/146612858/91b8f06f-681c-4d9c-9766-13bf6239f3ca)
- Classic Bikes are the most used in both Member riders and Casual riders
- Docked Bike are the least popular and only the Casual riders are the ones using it 

![MVC Volume of Riders](https://github.com/nizekid/Google-Data-Analytics-Capstone-Project-Bikes/assets/146612858/1f0da8cf-a88b-4d81-90d9-126c8c07a83d)
- Both Members and Casual riders have a peak  in the **Summer** season which are in the month of **June**, **July**,** August**.
- Both Members and Casual riders have a low count in the **Winter** season which are **December**, **January**, **Febraury**.
- According to this there are effects in the number of Riders in both Members and Casual in terms of Temperature

![MVC Volume per day](https://github.com/nizekid/Google-Data-Analytics-Capstone-Project-Bikes/assets/146612858/09175fbb-d2b5-4958-bc25-0f4ff11c0203)
![MVC per hours](https://github.com/nizekid/Google-Data-Analytics-Capstone-Project-Bikes/assets/146612858/10e468a6-1c2b-43bf-8ad5-aa9c9d02f5dd)
Members: 
- There's a constant peak in **Weekdays** for the Member riders
- There's a peak usage in the time between ****7am** to **6pm**** from the Member riders.
  - Indicating that the Member riders using the Bikes for communiting to work
Casual: 
- The Casual riders are in peak on **Weekends**
- There's a peak usage in the time between **11am to 6pm** from the Casual riders.
  - Indicating the Casual riders are using the bikes for possible lunch or other leisure activities
![Trip Duration](https://github.com/nizekid/Google-Data-Analytics-Capstone-Project-Bikes/assets/146612858/76475c47-f512-449a-a19e-1383c2a879a1)
- Members: 
  - The Members in all instances in the Trip duration per Month/Day/Hour are faster than casual riders
- Casual:
  - Casual riders are slower in all instances in trip duration per Month/Day/Hour Compare to the Member riders
  - Casual riders have the longest trip duration in **weekdays**
  - Casual riders have the longest trip duration between the time of **9am to 3pm**

![Dashboard 7](https://github.com/nizekid/Google-Data-Analytics-Capstone-Project-Bikes/assets/146612858/d8ed1de0-e9e6-4a1d-94c3-bad25336179d)
- the top Stations for the Member riders are near in possible workplaces, schools, post office, banks and other similar building

![Casual popular Start and End Station](https://github.com/nizekid/Google-Data-Analytics-Capstone-Project-Bikes/assets/146612858/d6441a4c-302e-4366-8bd1-7c99c980454d)
- The top Stations for the Casual riders are near on parks, museum, beach, and other leisure activities

### Key Summary 
- Member
  - More active in **Weekdays** especially in the time of ****7am** to **6pm****. Work day/hours
  - The Average trip duration are constant in Month/Days/Hours which usually 12 minutes or lower.
  - Top Startions are near in  workplaces, schools, post office, banks and other similar building
- Casual
  - More active in **Weekends** especially in between **11am to 6pm**.
  - The Average trip duration are much longer than Member riders in Month/Day/Hours which usually 20minutes or longer.
  - top Stations near on parks, museum, beach, and other leisure activities.
- Similarities
  - Both are Active in **Summer** season.
  - Both are Inactive in **Winter** season. 
  - Classic Bikes are the most used in both Member riders and Casual riders.

## Act Phase 
### Recommendation 
- Seaonal Discount
  - Having discounted prices in membership fee per season.
  - Bigger discoun in Winter season.
- Duration Incentive
  - Give incentives for members who uses bikes longer.
- Customazation Options 
  -  Catering for different options for a members. more control about their membership can do.
- Collaboration of stores near the top stations
  - Surverying the Stores near the top stations like parks and other leisure activities.

