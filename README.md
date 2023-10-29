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
I have been tasked by Moreno to address the first question: 
"What are the distinctions in how annual members and casual riders utilize Cyclistic bikes?" 
My objective is to generate this report and come up with a new marketing strategy to convert casual riders into annual members.


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

## 3.Process
I am using BigQuery to perform my data cleaning & data analysis. The main reason is because the total number of rows inside the combined dataset has around 5.6 million rows, and BigQuery has the capability & capacity to support this huge volume of data, wherelse Microsoft Excel only has a limit of around 1 million rows.

### Combined Dataset
SQL Query: [Data Combining](https://github.com/yanteing/Google-Data-Analytics-CaseStudy/blob/main/Data_Combining.sql)

12 csv files are uploaded into this table and apended, containing around 5.6 million rows of data for the year 2022

### Data_Cleaning
SQL Query: [Data Cleaning](https://github.com/yanteing/Google-Data-Analytics-CaseStudy/blob/main/Data_Cleaning.sql)
1. All the rows that are having missing values have been removed
2. Three self derived columns have been added: ride_length for duration of the trip, day_of_week and month
3. Trips with duration less than a minute and longer than a day are excluded
4. Total of around 1.3 million rows are removed in this step

## 4.Analyze & Share
SQL Query: [Data Analysis](https://github.com/yanteing/Google-Data-Analytics-CaseStudy/blob/main/Data_Analysis.sql)

Data Visualization: Tableau (Link website)

I have prepared my analysis and now I would like to visualize this in Tableau. 
The first analysis question is: How do annual members and casual riders use Cyclistic bikes differently?

To start this off,  the comparison between member and casual riders are shown based on the types of bicycles they use

![image](https://github.com/yanteing/Google-Data-Analytics-CaseStudy/blob/main/Images/Type%20of%20Bikes.png)

Of the total riders, members account for 59.7%, with casual riders making up the remaining 40.3%. Each bike type chart indicates the percentage relative to the total. The classic bike is the most frequently used, followed by the electric bike. Docked bikes, on the other hand, are used the least, predominantly by casual riders.

Next the number of trips distributed by the months, days of the week and hours of the day are examined.  

(Image 2)

**Months:** In terms of monthly trips, both casual riders and members demonstrate similar patterns, with higher trip frequencies during the spring and summer, and a decrease in the winter months. The closest the gap between casual riders and members becomes is in July, during the summer

**Days of Week**: When analyzing days of the week, it's evident that casual riders tend to embark on more journeys during the weekends, while members show a decline in weekend activity compared to the rest of the week

**Hours of Day:** Regarding the hours of the day, members display two peaks in trip numbers. One occurs in the early morning, roughly between 6 am and 8 am, and the other in the evening, from around 4 pm to 8 pm. In contrast, the number of trips for casual riders steadily increases throughout the day until the evening, after which it begins to decrease

From these observations, we can infer that members likely use the bikes for weekday commuting, while casual riders use them throughout the day, especially on weekends for leisure. Both groups are most active during the spring and summer seasons

The comparison of trip durations is carried out to identify variations in the riding behavior between casual and member riders 

(Image 3)

It's worth noting that casual riders typically have longer average trip durations compared to members. The average journey duration for members remains consistent throughout the year, week, and day. In contrast, casual riders exhibit variations in their trip durations. During the spring and summer, on weekends, and between 10 am and 2 pm, they cover longer distances, while they opt for shorter trips between 5 am and 8 am

These findings lead to the inference that casual commuters, on average, travel longer distances (approximately 2 times more) but less frequently compared to members. They embark on lengthier journeys during weekends and during daytime hours outside of typical commuting periods, particularly in the spring and summer, which suggests a recreational purpose

To gain a deeper understanding of the disparities between casual and member riders, an analysis of the starting and ending station locations can provide valuable insights. By applying filters to identify stations with the highest trip frequencies, we can draw further conclusions

(Image 4)

Casual riders often initiate their trips from stations situated near museums, parks, beaches, harbors, and aquariums, whereas members tend to commence their journeys from stations in proximity to universities, residential areas, restaurants, hospitals, grocery stores, theaters, schools, banks, factories, train stations, parks, and plazas

(Image 5)

A comparable pattern is evident in the ending station locations. Casual riders conclude their journeys near parks, museums, and other recreational destinations, whereas members finalize their trips in close proximity to universities, residential and commercial areas. This serves as compelling evidence that casual riders primarily utilize bikes for leisure activities, while members heavily depend on them for their daily commutes

**Summary:**
|Casual|Member|
|------|------|
|Opt for bike rides throughout the day, with a higher frequency on weekends during the summer and spring, primarily for leisure purposes|Tend to choose weekday rides during commuting hours (8 am / 5 pm) in the summer and spring seasons|
|Cover longer distances, around twice as much as members, but ride less frequently|Engage in more frequent bike rides, yet their trips are notably shorter, approximately half the duration of casual riders' trips|
|Commence and conclude their journeys in proximity to parks, museums, coastal areas, and other recreational venues|Initiate and conclude their trips in the vicinity of universities, residential neighborhoods, and commercial districts|

## Act 
After recognizing the distinctions between casual and member riders, the development of marketing strategies aimed at converting casual riders into members is a viable strategy.

Recommendations:
1.Consider implementing marketing campaigns during the spring and summer at tourist and recreational sites frequented by casual riders.
2.Since casual riders display heightened activity during weekends and the summer and spring seasons, consider introducing seasonal or weekend-only membership options tailored to their preferences.
3.Given that casual riders tend to ride for extended durations compared to members, explore the possibility of offering discounts for longer rides. This approach could serve as an incentive for casual riders and potentially encourage members to extend their ride durations as well.

