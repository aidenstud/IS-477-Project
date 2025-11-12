# IS477 Project

**Overview:**

New York City is one of the most densely populated cities in the world, with millions of people relying on public transportation every day to get to work, school, and other destinations. Because of this, reliable public transit is crucial -- even the smallest delays can throw someone off course, and put them behind schedule. For this project, we will specifically be focusing on the MTA subway delays in 2024, analyzing patterns, causes, and passenger impacts to improve subway reliability and passenger experience. 

**Research Question(s):**

What are the most common delays? Do they occur often? 

Which train line has the most delays? Is the cause for the delay the same each time? Are delays frequent? 

Which train line (delays) have the longest wait times? 

Do peak (rush-hour) riders experience more delays than non-peak riders? Are wait times longer peak vs non-peak?

Which months (in 2024) had the worst customer experience overall, such as longer wait times? 

Do planned maintenance activities (Planned ROW Work delays) correspond to improved service delivered in later months? 


**Team:**

Victoria - organization, research, coding 

Aiden - Research, coding, paper drafting

**Dataset(s):**

We will be working with 4 datasets, all coming from the New York State government website.

Dataset 1: Our primary dataset will be “MTA Subway Trains Delayed: Beginning 2020”. This dataset is organized by month, with each month (row) giving the reason for delays on each train line, whether the delays occurred on a weekday or weekend, and how many times each delay happened within the month. URL: https://data.ny.gov/Transportation/MTA-Subway-Delay-Causing-Incidents-Beginning-2020/g937-7k7c/about_data 

Dataset 2: "MTA Subway Customer Journey-Focused Metrics: 2020-2024”. This dataset is organized by month, with each month (row) giving us the number of passengers, various wait time metrics, and peak vs non-peak rush hour periods for each train line.  This dataset will be integrated with our primary dataset to show the relationship between delays and wait times for each train line. URL: https://data.ny.gov/Transportation/MTA-Subway-Customer-Journey-Focused-Metrics-2020-2/4apg-4kt9/data_preview 

Dataset 3: “MTA Subway Service Delivered: 2020-2024”. This dataset is organized by month, with each month (row) comparing how many trains were scheduled vs how many trains actually showed up during the weekday vs weekends. This dataset will be integrated with our primary dataset to see which trainlines are most reliable even if delays occur. URl: https://data.ny.gov/Transportation/MTA-Subway-Service-Delivered-2020-2024/bg59-42xi/data_preview 

Dataset 4: “MTA Service Alerts: Beginning April 2020”.This dataset is organized by date and records which train lines experienced delays, the content of the public service announcements for each delay, and how many times passengers were updated. This dataset will be integrated with our primary dataset to provide detailed insights into delays since the primary dataset groups “reasons for delays” into six broad categories. URL: https://data.ny.gov/Transportation/MTA-Service-Alerts-Beginning-April-2020/7kct-peq7/data_preview 

**Timeline:**

1. Project Planning and Data Acquisition - Aiden & Victoria
2. Dataset cleaning and Preprocessing
    - Clean and standardize delay codes- Both
    - Process large data sets- Aiden
    - Merge datasets into analysis set- Victoria
3.  Exploratory Data Analysis
    - Analyze delay reasons, frequencies, and distributions- Victoria
    - Create visualizations of delayed lines/other exploratory visuals- Aiden
4.  Advanced Analysis and Impact Modeling
    - Compare peak vs off ride impact- Victoria
    - Calculate time lost per line- Aiden
    - Determine other helpful metrics and create visualizations to represent findings- Both
    - Interim Status Report- Both
5.  Create Final Visualizations and Reporting
    - Create final visualizations and summary stats- Victoria
    - Draft final paper- Aiden
6.  Final Submission and Release- Aiden & Victoria
    - Final review of code
    - Final review of paper
    - Release on GitHub


**Constraints:** 
1. Some of the datasets are large and may require memory-efficient processing techniques.
2. We may need to bolster our current selection of data with additional sets if we cannot answer our research questions. 
3. The “reporting_category” column is broken up into six categories: Crew Availability, External Factors, Infrastructure & Equipment, Operating Conditions, Planned ROW Work, and Police & Medical. These are not super detailed and there is room for interpretation by the reader. 
4. The first three datasets are broken up into months whereas the last dataset is broken up by data. We will need to group the data or manipulate the data column in the dataset 4 so we can seamlessly integrate this dataset with the others to make useful comparisons. 

**Gaps:**
1. Our model and project will simplify passenger journeys. We cannot account for transfers or the ripple effects of one delay on other trains/lines. 
2. We anticipate that we will want to expand the scope and components of our project as the course continues. We will evaluate what other concepts we want to include as we come across them. The modules on reproducibility and data documentation will likely influence the scope and nature of our project in the coming weeks.
3. Our knowledge of public transport is limited, and we are not from NYC, so our conclusions may not completely be accurate or truly represent the causes of delays and their effects. We hope to provide meaningful analysis and insight into the issue, despite not being professionals in this field.


**Victoria's Update Summary and Contribution**

Updates: For this status report, I added in the URLS to the respective datasets I found initially. Updates can be seen above! 

For this Status report, we primarily worked on the Dataset Cleaning and Processing. I specifically uploaded the datasets into VSC and integrated them. When uploading the datasets onto here, created an API Token to pull all the rows from each dataset; before putting the data into a dataframe, I made sure to filter out the months/date columns to only include data from 2024 which would be relevant for our analysis. 

INTEGRATION: FINISH! Only included the columns needed for our research questions. 


**Aidan's Update Summary and Contribution**
