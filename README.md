# Google-Data-Analytics-CaseStudy
Course: https://www.coursera.org/learn/google-data-analytics-capstone

## Introduction
In this case study, I will be performing several real-world tasks of a junior data analyst at a fictional company called Cyclistic. I will be implementing steps of the data analysis processs:[Ask,Prepare,Process,Analyze,Share,Act] which I have learned throughout the course and applying it into this project

 ## Scenario
 Cyclistic, a bike-share program operating in Chicago, boasts a fleet of more than 5,800 bicycles stationed at 600 docking stations. Its unique feature lies in its commitment to inclusivity, offering reclining bikes, hand tricycles, and cargo bikes to cater to individuals with disabilities and those who cannot use conventional two-wheeled bikes. While the majority of riders prefer traditional bicycles, approximately 8% opt for assistive options. Cyclistic serves both recreational riders and a significant 30% who use it for daily commuting.

Cyclistic's marketing strategy has traditionally revolved around creating general awareness and appealing to a wide consumer base. This was made possible through versatile pricing plans, including single-ride passes, full-day passes, and annual memberships. Casual riders are those who purchase single-ride or full-day passes, while Cyclistic members are annual membership holders.

A thorough financial analysis has revealed that annual members yield significantly higher profits compared to casual riders. In light of this, our marketing director, Moreno, is convinced that the future success of Cyclistic hinges on maximizing the annual membership base. Rather than targeting entirely new customers, Moreno envisions an opportunity to convert casual riders into members, given their existing familiarity with the Cyclistic program.

Moreno has outlined a clear objective: Formulate marketing strategies with the specific aim of transitioning casual riders into annual members. To achieve this, our marketing analyst team needs to gain a deeper understanding of the differences between annual members and casual riders, uncover the motivations behind casual riders opting for membership, and explore the role of digital media in influencing our marketing tactics. Moreno and her team are eager to dive into Cyclistic's historical bike trip data to uncover meaningful trends.

## Task
I have been tasked by Moreno to address the first question: "What are the distinctions in how annual members and casual riders utilize Cyclistic bikes?" My objective is to generate this report and come up with a new marketing strategy to convert casual riders into annual members.


## Data Analysis Process

## 1.Ask
### Analysis Questions
Three questions will guide the future marketing program:  
1. How do annual members and casual riders use Cyclistic bikes differently?  
2. Why would casual riders buy Cyclistic annual memberships?  
3. How can Cyclistic use digital media to influence casual riders to become members?

Moreno has assigned me the first question to answer: How do annual members and casual riders use Cyclistic bikes differently?
## 2.Prepare
### Data Source
I will use Cyclistic’s historical trip data to analyze and identify trends from Jan 2022 to Dec 2022 which can be downloaded from [divvy_tripdata](https://divvy-tripdata.s3.amazonaws.com/index.html). The data has been made available by Motivate International Inc. under this [license](https://www.divvybikes.com/data-license-agreement)  

I intend to utilize Cyclistic's historical trip data to examine and uncover patterns spanning from January 2022 to December 2022, accessible for download through the divvy_tripdata source. The dataset is publicly available, enabling the investigation of how various customer categories utilize Cyclistic bicycles. The dataset comprises 12 files following the naming convention YYYYMM-divvy-tripdata, with each file containing data for a single month. This data includes ride IDs, bike types, start and end times, start and end stations, geographic coordinates, and rider categorization as a member or casual rider.

## 3.Proces
I am using BigQuery to perform my data cleaning & data analysis. The main reason is because the total number of rows inside the combined dataset has around 5.6 million rows, and BigQuery has the capability & capacity to support this huge volume of data, wherelse Microsoft Excel only has a limit of around 1 million rows.

### Combined Dataset
SQL Query: [Data Combining](https://github.com/yanteing/Google-Data-Analytics-CaseStudy/blob/main/Data_Combining.sql)
12 csv files are uploaded into this table and apended, containing around 5.6 million rows of data for the year 2022

### Data_Cleaning
SQL Query: [Data Cleaning](https://github.com/yanteing/Google-Data-Analytics-CaseStudy/blob/main/Data_Cleaning.sql)
1. All the rows that are having missing values have been removed
2. 3 self derived columns have been added: ride_length for duration of the trip, day_of_week and month
3. Trips with duration less than a minute and longer than a day are excluded
4. Total of around 1.3 million rows are removed in this step

## 4.Analyze & Share
SQL Query: [Data Analysis](https://github.com/yanteing/Google-Data-Analytics-CaseStudy/blob/main/Data_Analysis.sql)
Data Visualization: Tableau (Link website)

![image](https://github.com/yanteing/Google-Data-Analytics-CaseStudy/blob/main/Images/Type%20of%20Bikes.png)


I have prepared my analysis and now I would like to visualize this in Tableau. The first analysis question is: How do annual members and casual riders use Cyclistic bikes differently?

To start this off,  the comparison between member and casual riders are shown based on the types of bicycles they use

