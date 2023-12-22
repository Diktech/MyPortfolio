# DATA ANALYTICS
### SKILLS
###### Proficiency in cleaning, transforming, and organizing data from various sources.
###### Ability to apply statistical and analytical techniques to extract insights and draw meaningful conclusions
###### Proficiency in SQL and R, for data analysis and manipulation
###### Experience with tools like Tableau, Power BI for interactive data visualization and reporting
###### Ability to present data insights in a compelling and easily understandable narrative.
###### Ability to combine data from different sources to create a unified view
###### Understanding of data models and database design principles
###### Data Cleaning and Preprocessing: Knowledge of techniques to handle missing data and outliers.
###### Data Visualization: Skill in creating clear and compelling visualizations to communicate findings effectively.
###### Proficient in Excel, Power BI, Tableau for data analysis and visualization. 




## WORK EXPERIENCE
### BSMS LONDON, UK (IT) PART TERM
##### Junior Data Analyst  JULY 2023 till  DATE

•	Clean data and Conducted data analysis to identify trends and patterns in potential students’ behaviour in choosing universities of choice. 

•	Creating data visualization and dashboard for sales performance, providing real-time insights to sales teams for better decision making. 

•	Presenting findings to stakeholders and suggesting solutions to business problems. 

•	Collaborated with cross-functional teams to identify process inefficiencies and proposed data-driven solutions.



### TRADEVIEW MARKETS LONDON
##### Market Analyst 2023

•	Analyze the forex market to provide market insight to existing clients 

•	Using fundamental data to forecast potential price movement and predict market direction 

•	Organizing, cleaning and storing market data for future  market analysis and prediction 

•	Paying attention to details and drawing insight from analysis 

•	Creating visualization to bring derived insight to live and make it easy to understand. 

### CJC MARKETS NG CFD/FOREX
##### Sales Manager  August 2020 to January 2023

•	 Utilized data analysis to identify market segments and optimize sales approaches.

•	 Leverage statical models to forecast potential revenue streams 

•	 Monitor and analyse sales data, implementing data driven strategies to increase efficiency and productivity.

•	 Utilizing data analysis to identify markets segments and optimize sales approaches.

•	 Utilize data analytics tools to monitor markets trends and competitor’s activities


## EDUCATION 
### INCO ACADEMY TRAINING UK BUSINESS INTELLIGENCE AND DATA ANALYTICS  COURSE

Google Certified Data Analyst

BCS certified Business analyst-in view 

### Welup Digital training
Data analytics training and  internship 
Excel, Power BI, Tableau, SQL, R programming Data collection, analysing data, cleaning data, Data modelling, and Data visualization to arrive at a conclusion sharing of insight.

### Advanced Careers, UK
Business Analysis Training and Internship

Relevant Modules: Modelling Business Process, Requirement Engineering, Software Development Methodologies Agile Scrum & Waterfall, Project Management.

### Nexford University, Washington DC 2023

Master’s In Business Administration MBA

### NEXFORD UNIVERSITY, Washington DC (2022)
 Master’s in business administration (MBA) Foundation Course.

### Petroleum training institute, Warri (2006-2011)

HND Electrical Electronics Engineering.

## DATA ANALYTICS PROJECTS 
### Cyclistic Case study
The data analysis workflow is a follows: Ask, Prepare, Process, Analyze and Share (combined in this case), and Act.

Introduction
Business Task
In this case study Iworked as a junior data analyst working in the marketing analyst team at Cyclistic, a  bike-share company in Chicago. The Marketing director believes that if the company will record more success, the casual memebers must be converted to annual memebers. Therefore, my job is to draw insight on how casual riders and annual members use Cyclistic bikes differently.

The stakeholder is Lily Moreno, the director of marketing and my manager. The other stakeholders for this project are the executive team.

Through this data analysis I want to find out how do annual members and casual riders use Cyclistic bikes differently. After analysis, the goal is to make recommendations to the stakeholders.

#### Preparing the data
Data sources Used
Previous 12 months of Cyclistic trip data made available by Motivate International Inc. Link here: (https://divvy-tripdata.s3.amazonaws.com/index.html)

Data integrity: Can not be verified since I am not familiar with the company

Data Errors and Issues: Data has issues with duplicate data, Null values, and invalid data.

Tools Choosing to work with R due to it’s flexibility, and the fact that we have a large dataset.

Data should help me answer the question of “how do annual members and casual riders use Cyclistic bikes differently?” because I have access to a year’s worth of data for both casual and member riders. Data has over 4 million records which is a lot.

Libraries
library(tidyverse)  #helps wrangle data
## ── Attaching packages ─────────────────────────────────────── tidyverse 1.3.1 ──
## ✔ ggplot2 3.3.4     ✔ purrr   0.3.4
## ✔ tibble  3.1.2     ✔ dplyr   1.0.7
## ✔ tidyr   1.1.3     ✔ stringr 1.4.0
## ✔ readr   1.4.0     ✔ forcats 0.5.1
## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
## ✖ dplyr::filter() masks stats::filter()
## ✖ dplyr::lag()    masks stats::lag()
library(lubridate)  #helps wrangle date attributes
## 
## Attaching package: 'lubridate'
## The following objects are masked from 'package:base':
## 
##     date, intersect, setdiff, union
library(ggplot2)  #helps visualize data
library(readr) #read csv files
library(plyr) #bind function
## ------------------------------------------------------------------------------
## You have loaded plyr after dplyr - this is likely to cause problems.
## If you need functions from both plyr and dplyr, please load plyr first, then dplyr:
## library(plyr); library(dplyr)
## ------------------------------------------------------------------------------
## 
## Attaching package: 'plyr'
## The following objects are masked from 'package:dplyr':
## 
##     arrange, count, desc, failwith, id, mutate, rename, summarise,
##     summarize
## The following object is masked from 'package:purrr':
## 
##     compact
Load the 12 months of bike rides data, csv files
setwd("../input/cyclistic5")
data_2020_06 <- read.csv("202006-divvy-tripdata.csv")
data_2020_07 <- read.csv("202007-divvy-tripdata.csv")
data_2020_08 <- read.csv("202008-divvy-tripdata.csv")
data_2020_09 <- read.csv("202009-divvy-tripdata.csv")
data_2020_10 <- read.csv("202010-divvy-tripdata.csv")
data_2020_11 <- read.csv("202011-divvy-tripdata.csv")
data_2020_12 <- read.csv("202012-divvy-tripdata.csv")
data_2021_01 <- read.csv("202101-divvy-tripdata.csv")
data_2021_02 <- read.csv("202102-divvy-tripdata.csv")
data_2021_03 <- read.csv("202103-divvy-tripdata.csv")
data_2021_04 <- read.csv("202104-divvy-tripdata.csv")
data_2021_05 <- read.csv("202105-divvy-tripdata.csv")
Processing the data
Combine data sets to 1 dataframe that stores the entire year’s data
data_12_months <- rbind(data_2020_06,data_2020_07,data_2020_08,data_2020_09,data_2020_10,data_2020_11,data_2020_12,data_2021_01,data_2021_02,data_2021_03,data_2021_04,data_2021_05)
Add Ride_Length column for calculations
data_12_months$ride_length <- difftime(data_12_months$ended_at, data_12_months$started_at, units = "mins")
Add Day_of_week column for calculations
data_12_months$day_of_week <- wday(data_12_months$started_at)
Add columns that list the date, month, day, and year of each ride for further calculations

data_12_months_v2 <- data_12_months
data_12_months_v2$date <- as.Date(data_12_months_v2$started_at) #The default format is yyyy-mm-dd
data_12_months_v2$month <- format(as.Date(data_12_months_v2$date), "%m")
data_12_months_v2$day <- format(as.Date(data_12_months_v2$date), "%d")
data_12_months_v2$year <- format(as.Date(data_12_months_v2$date), "%Y")
data_12_months_v2$day_of_week <- format(as.Date(data_12_months_v2$date), "%A")
Remove rows with NA Values
data_12_months_v2 <- na.omit(data_12_months_v2)
Remove duplicate rows in the dataframe
data_12_months_v2 <- data_12_months_v2 %>% 
  distinct()
Remove columns (variables) not needed for this analysis: ride_id, start_station_id, end_station_id, start_lat, start_long, end_lat, end_lng
data_12_months_v2 <- data_12_months_v2 %>%  
  select(-c(ride_id, start_station_id, end_station_id,start_lat,start_lng,end_lat,end_lng))
Remove bad data where ride_length is 0 or negative <=0
data_12_months_v2 <- data_12_months_v2[!(data_12_months_v2$ride_length <=0),]
Convertion of ride length to numeric so calculations can be run on the data.
data_12_months_v2$ride_length <- as.numeric(as.character(data_12_months_v2$ride_length))
is.numeric(data_12_months_v2$ride_length)
## [1] TRUE
Analyzing and Visualizing the data
count of bike type, number of trips , member-casual
data_12_months_v2 %>%
  group_by(rideable_type, member_casual) %>%
  dplyr::summarize(count_trips = n()) %>%  
  ggplot(aes(x= rideable_type, y=count_trips, fill=member_casual, color=member_casual)) +
    geom_bar(stat='identity', position = 'dodge') +
    theme_bw()+
    labs(title ="Bicycle Type Number of trips", x = "Bicycle Type", y = "Count of Trips")
## `summarise()` has grouped output by 'rideable_type'. You can override using the `.groups` argument.


### Arranges the weekdays in order Sunday to Saturday.
data_12_months_v2$day_of_week <- ordered(data_12_months_v2$day_of_week, levels=c("Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"))

### Number bike rides per week BAR CHART
data_12_months_v2 %>%
  group_by(member_casual,day_of_week) %>%
  dplyr::summarize(count_trips = n()) %>%  
  ggplot(aes(x= day_of_week, y=count_trips, fill=member_casual, color=member_casual)) +
    geom_bar(stat='identity', position = 'dodge') +
    theme_bw()+
    labs(title ="Number of bike rides per Week", x = "Day", y = "Count of Trips")
## `summarise()` has grouped output by 'member_casual'. You can override using the `.groups` argument.


Number bike rides per month BAR CHART
library("dplyr")

data_12_months_v2$month <- ordered(data_12_months_v2$month, levels=c("01", "02", "03", "04", "05", "06", "07","08","09","10","11","12"))

data_12_months_v2 %>%
  group_by(member_casual,month) %>%
  dplyr::summarize(count_trips = n()) %>%  
  ggplot(aes(x= month, y=count_trips, fill=member_casual, color=member_casual)) +
    geom_bar(stat='identity', position = 'dodge') +
    theme_bw() +
    labs(title ="Number of bike rides per month", x = "Month", y = "Count of Trips")
## `summarise()` has grouped output by 'member_casual'. You can override using the `.groups` argument.


Popular Start Stations for Casual riders
data_12_months_v2 %>%
    group_by(member_casual,start_station_name) %>%
    dplyr::summarise(number_of_ride = n()) %>%
    filter(start_station_name != "", "casual"== member_casual) %>%
    arrange(-number_of_ride) %>%
    head(n=30) %>%
    select(-member_casual)
## `summarise()` has grouped output by 'member_casual'. You can override using the `.groups` argument.
## Adding missing grouping variables: `member_casual`
## # A tibble: 30 x 3
## # Groups:   member_casual [1]
##    member_casual start_station_name         number_of_ride
##    <chr>         <chr>                               <int>
##  1 casual        Streeter Dr & Grand Ave             36355
##  2 casual        Lake Shore Dr & Monroe St           28024
##  3 casual        Millennium Park                     24550
##  4 casual        Theater on the Lake                 18423
##  5 casual        Michigan Ave & Oak St               18181
##  6 casual        Lake Shore Dr & North Blvd          16741
##  7 casual        Indiana Ave & Roosevelt Rd          15725
##  8 casual        Shedd Aquarium                      13758
##  9 casual        Michigan Ave & Lake St              13747
## 10 casual        Clark St & Elm St                   13181
## # … with 20 more rows
Popular Start Stations for Member riders
data_12_months_v2 %>%
    group_by(member_casual,start_station_name) %>%
    dplyr::summarise(number_of_ride = n()) %>%
    filter(start_station_name != "", "member" == member_casual) %>%
    arrange(-number_of_ride) %>%
    head(n=30) %>%
    select(-member_casual)
## `summarise()` has grouped output by 'member_casual'. You can override using the `.groups` argument.
## Adding missing grouping variables: `member_casual`
## # A tibble: 30 x 3
## # Groups:   member_casual [1]
##    member_casual start_station_name         number_of_ride
##    <chr>         <chr>                               <int>
##  1 member        Clark St & Elm St                   22445
##  2 member        Wells St & Concord Ln               17503
##  3 member        Theater on the Lake                 17291
##  4 member        Broadway & Barry Ave                17179
##  5 member        Dearborn St & Erie St               17060
##  6 member        Kingsbury St & Kinzie St            16933
##  7 member        St. Clair St & Erie St              16696
##  8 member        Wells St & Elm St                   16386
##  9 member        Wells St & Huron St                 15979
## 10 member        Lake Shore Dr & North Blvd          15444
## # … with 20 more rows
Summary and Recommendations
Learned that a docked bicycle type is around 2 times as popular compared to casual and electric bikes. This applies to both casual and member bicycle users.

Learned that Saturday and Sunday are the most popular riding days for casual riders.

November through February have the least number of casual riders, perhaps due to cold winter months.

May, July, and August have a particularly high number of Casual riders.

The most popular stations for Casual riders in descending order are Streeter Dr & Grand Ave, Lake Shore Dr & Monroe St, Millennium Park, Theater on the Lake, Michigan Ave & Oak St.

Conclusion: Based on the data analyzed I would recommend we focus our marketing effors for Casual Riders with these parameters 1, Increase marketing for docket bicycles 2. Heavier marketing from May through August 3. Focus marketing on weekends 4. Invest in marketing at the top 5 stations as noted above. Top 10 station marketing would cover even more ground.
