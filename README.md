Google Data Analytics Capstone Project: Cyclist Bike Share Data Analysis

**#Introduction**
In this Cyclistic bike-share analysis case study! I'll act as a junior data analyst working on the marketing analyst team at fictional Cyclistic, a bike-share
company in Chicago. In order to answer the key business queestions. I'll follow the steps of the data analysis process: Ask, Prepare, Process, Analyze, Share, and Act. 

#Quick links

#Data Source: [divy_tripdata] (https://divvy-tripdata.s3.amazonaws.com/index.html)



#SQL Queries :

#Data Visulaizations: 


**#BACKGROUND**

In 2016, Cyclistic launched a successful bike-share offering. Since then, the program has grown
to a fleet of 5,824 bicycles that are geotracked and locked into a network of 692 stations
across Chicago. The bikes can be unlocked from one station and returned to any other station
in the system anytime.
Until now, Cyclistic’s marketing strategy relied on building general awareness and appealing to
broad consumer segments. One approach that helped make these things possible was the
flexibility of its pricing plans: single-ride passes, full-day passes, and annual memberships.
Customers who purchase single-ride or full-day passes are referred to as casual riders.
Customers who purchase annual memberships are Cyclistic members.
Cyclistic’s finance analysts have concluded that annual members are much more profitable
than casual riders. Although the pricing flexibility helps Cyclistic attract more customers,
Moreno believes that maximizing the number of annual members will be key to future growth.
Rather than creating a marketing campaign that targets all-new customers, Moreno believes
there is a solid opportunity to convert casual riders into members. She notes that casual riders
are already aware of the Cyclistic program and have chosen Cyclistic for their mobility needs.
Moreno has set a clear goal: Design marketing strategies aimed at converting casual riders into
annual members. In order to do that, however, the team needs to better understand how
annual members and casual riders differ, why casual riders would buy a membership, and how
digital media could affect their marketing tactics. Moreno and her team are interested in
analyzing the Cyclistic historical bike trip data to identify trends.


**#Scenario**

I am a junior data analyst working on the marketing analyst team at Cyclistic, a bike-share
company in Chicago. The director of marketing believes the company’s future success
depends on maximizing the number of annual memberships. Therefore, my team wants to
understand how casual riders and annual members use Cyclistic bikes differently. From these
insights, my team will design a new marketing strategy to convert casual riders into annual
members. But first, Cyclistic executives must approve my recommendations, so they must be
backed up with compelling data insights and professional data visualizations.

**#Ask Phase**: Business Questions
The following three questions will guide the future Marketing programs
1. How do annual members and casual riders use Cyclistic bikes differently?
2. Why would casual riders buy Cyclistic annual memberships?
3. How can Cyclistic use digital media to influence casual riders to become members?

**Prepare**
For this case estudy, I have taken Cyclistic dataset from Jan 2023 to May 2023 to analyse and identify the trends. The data has been made available by Motivate International Inc. under this [license] (https://divvybikes.com/data-license-agreement).
This is public data that can be used to explore how different customer types are using Cyclistic bikes. But note that data-privacy issues prohibit from using riders’ personally identifiable information. This means that we won’t be able to connect pass purchases to credit card numbers to determine if casual riders live in the Cyclistic service area or if they have purchased multiple single passes.

Tools Used in this analysis:

Data cleaning & processing - SQL on Google Big Query
Data visualization - Tableau

1. I have used jan 2023 to May 2023 data for this analysis. Since Local uploads were limited to 100 mb on Bigquery.
2. Each files were saved individually as .csv files
3. Upon analyzing they have the following corresponding column names are ride_id, rideable_type, started_at, ended_at, start_station_name, start_station_id, end_station_name, end_station_id, start_lat, start_lng, end_lat, end_lng and member_casual.
4. Now, I have combined all the tables into combined_tripdata

**#Data Collection and Combining process**


1.--COMBINING ALL ROWS


CREATE TABLE IF NOT EXISTS `bicycle-436922.bicycle_trip.Combined_tripdata` AS (
SELECT *
FROM `bicycle-436922.bicycle_trip.jan2023`
UNION ALL
SELECT * 
FROM `bicycle-436922.bicycle_trip.feb2023`
UNION ALL
SELECT * 
FROM `bicycle-436922.bicycle_trip.mar2023`
UNION ALL
SELECT * 
FROM `bicycle-436922.bicycle_trip.apr2023`
UNION ALL
SELECT * FROM `bicycle-436922.bicycle_trip.may2023`
)


2. View the table
   
SELECT *
FROM bicycle-436922.bicycle_trip.Combined_tripdata
LIMIT 10;

<img width="935" alt="Screen Shot 2024-09-28 at 7 19 03 PM" src="https://github.com/user-attachments/assets/b2401fe1-2654-44e0-a09d-be1eb80ee73b">


