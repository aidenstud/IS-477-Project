# IS477 Project Status Report

### Research Question(s):

* Q1: What are the most common delays? Do they occur often? 

* Q2: For each subway line and each month, how many delay-causing incidents occurred, and what was the corresponding Total Additional Platform Time (total APT) experienced by all riders?

* Q3: Which train line has the most delays? Is the cause for the delay the same each time? Are delays frequent? 

* Q4: Which train line (delays) have the longest wait times? 

* Q5: Which months (in 2024) had the worst customer experience overall, such as longer wait times? 

* Q6: Do planned maintenance activities (Planned ROW Work delays) correspond to improved service delivered in later months? 


### Team:

Victoria – Data Acquisition & Integration Lead
* Leads dataset collection and acquisition
* Oversees dataset integration and merging
* Handles data quality evaluation
* Manages storage, file organization, and GitHub structure
* Leads metadata creation and documentation
* Oversees final report writing and release

Aiden – Data Cleaning & Research Lead
* Leads dataset cleaning and preprocessing
* Develops and refines research questions
* Identifies initial constraints and timeline development
* Handles data enrichment, workflow automation, and provenance tracking
* Leads reproducibility and transparency tasks
* Creates reproducible package and supports final report delivery


Both – Analysis & Visualization Leads
* Collaboratively conduct data analysis
* Develop visualizations to support findings
* Interpret results and connect them to research questions


### Dataset(s):

We will be working with 4 datasets, all coming from the New York State government website.

Dataset 1: Our primary dataset will be “MTA Subway Trains Delayed: Beginning 2020”. This dataset is organized by month, with each month (row) giving the reason for delays on each train line, whether the delays occurred on a weekday or weekend, and how many times each delay happened within the month. URL: https://data.ny.gov/Transportation/MTA-Subway-Delay-Causing-Incidents-Beginning-2020/g937-7k7c/about_data 

Dataset 2: "MTA Subway Customer Journey-Focused Metrics: 2020-2024”. This dataset is organized by month, with each month (row) giving us the number of passengers, various wait time metrics, and peak vs non-peak rush hour periods for each train line.  This dataset will be integrated with our primary dataset to show the relationship between delays and wait times for each train line. URL: https://data.ny.gov/Transportation/MTA-Subway-Customer-Journey-Focused-Metrics-2020-2/4apg-4kt9/data_preview 

Dataset 3: “MTA Subway Service Delivered: 2020-2024”. This dataset is organized by month, with each month (row) comparing how many trains were scheduled vs how many trains actually showed up during the weekday vs weekends. This dataset will be integrated with our primary dataset to see which trainlines are most reliable even if delays occur. URl: https://data.ny.gov/Transportation/MTA-Subway-Service-Delivered-2020-2024/bg59-42xi/data_preview 

Dataset 4: “MTA Service Alerts: Beginning April 2020”.This dataset is organized by date and records which train lines experienced delays, the content of the public service announcements for each delay, and how many times passengers were updated. This dataset will be integrated with our primary dataset to provide detailed insights into delays since the primary dataset groups “reasons for delays” into six broad categories. URL: https://data.ny.gov/Transportation/MTA-Service-Alerts-Beginning-April-2020/7kct-peq7/data_preview 

# Timeline: #

### Week 5-7: Project Planning and Data Acquisition

In the first section of the project, our main focus is selecting our datasets, developing potential research questions, and identifying any constraints or gaps within the data. This stage is about laying a clear foundation and organizing our work for the remainder of the project.

* Week 5 - Dataset Overview: Victoria
* Week 5 - Dataset Collection and Acquisition: Victoria
* Week 6 - Research Questions: Aiden
* Week 6 - Timeline: Aiden
* Week 7 - Constraints: Aiden
* Week 7 - Gaps: Victoria

### Week 8-11: Interim Status Report 

In this section of the project, our main focus is cleaning our datasets and analyzing the quality of the data, and organizing our github repository files as we begin to answer some of our research questions through integration.  

* Week 8 - Data Quality: Aiden
* Week 8 - Data Cleaning: Aiden
* Week 9-10 - Data Integration: Victoria 
* Week 10-11 - Storage and Organization: Victoria

### Week 12-16: Final Project Submissions

In this section of the project, our main focus is to finish up answering any remaining questions by continuing data integration and manipulation, provide detailed analysis and visualizations, complete any remaining tasks we were not able to finish earlier, and finalize the writing for the report.

* Week 12 - Continue Data Integration: Victoria
* Week 12 - Data analysis and/or visualization: Victoria 
* Week 13 - Data lifecycle: Victoria
* Week 13 - Ethical Data Handling: Victoria
* Week 13 - Extraction and Enrichment: Aiden
* Week 14 -  Workflow automation and provenance: Aiden
* Week 14 - Reproducibility and transparency: Aiden
* Week 15 - Metadata and data documentation: Victoria
* Week 15 - Reproducible package: Aiden
* Week 16 - Finalize Report and Release on Github: Victoria & Aiden

# Data Quality: #

### Dataset 1: 

Accuracy: The dataset is accurate. When checking for any syntax errors within the Line Column, which we are primarily merging on, there were no misspellings and no duplicates.There were no discrepancies in accords to the “ground truth”

Completeness: The dataset has no missing rows, except the first row for each train line for each day (either weekend or weekday) always starts off with a blank under the Reporting Category Col and a 0 in the incidents column. While this is intentional and not an indicator of missing data, it is still something to be aware of. 

Timeliness: According to the Data.NY.Gov website, this dataset was just recently updated on October 24, 2025. It seems like they are frequently updating it. Both the data and the meta data were uploaded on the same day. The dataset provides content for each line for each month starting from 01-01-20. 

Consistency: The dataset is consistent. Under the Reporting Category, there are 6 options to choose from and no other variations so it is easy to categorize the types of incidents. While these 6 options help with consistency, it does limit true understanding of what the detailed true incident is. The other columns are consistent as well: The Month column follows the same syntax of Year-Month-Day, the Division column only has options from A Division or B Division, the Line column only contains numbers or letters of real train lines in the MTA, and the Incidents column only has numbers.  

### Dataset 2: 

Accuracy: The dataset is accurate. When checking for any syntax errors within the Line Column, which we are primarily merging on, there were no misspellings and no duplicates.There were no discrepancies in accords to the “ground truth”

Completeness: The dataset has no missing rows. 

Timeliness: According to the Data.NY.Gov website, this dataset was updated January 24, 2025 and the meta data was updated July 14, 2025. Although it is not as frequent as the other datasets, it is not relevant in our case because we are only looking at 2024 data for our research questions and there is data for each month for each line in this dataset. 

Consistency: The dataset is consistent. The Month column follows the same syntax of Year-Month-Day, the Line column only contains numbers or letters of real train lines in the MTA,  the Division column only has options from A Division or B Division, the Period column only has options from Peak or Offpeak, and the Num_passengers column only has numbers, columns Additional Platform Time, Additional Train Time, Total_apt, Total_att, and Over_five_mins are all in minutes, and the Over_five_mins_perc and Customer journey time performance columns are all in percentages. 



### Victoria's Update Summary and Contribution

**Updates:** For this status report, I added in the URLS to the respective datasets I found initially. Updates can be seen above! 

**New Contributions:**

For this Status report, we primarily worked on the Dataset Cleaning and Processing. I specifically uploaded the datasets into VSC and integrated them. When uploading the datasets onto here, I created an API Token (hiding my email and password for security reasons) to pull all the rows from each dataset; before putting the data into a dataframe, I made sure to filter out the months/date columns to only include data from 2024 which would be relevant for our analysis. 

After that, I created the SHA256 Integrity Checksum for each dataset I pulled before any Data Analysis and Integration. 

We got started on answering two of the six research questions for this project thus far. I specifically worked on Q2, integrating the dataset 1 (“MTA Subway Trains Delayed: Beginning 2020”) and dataset 2 (“MTA Subway Customer Journey-Focused Metrics: 2020-2024”) together to find out if the number of incidents (accidents) on the train rails affected customers wait time for each line in each month. I used duckdb to be able to do SQL integration. 

So far, our work has been focused primarily on Datasets 1 and 2, so the majority of our cleaning, integration, and data quality checks have been completed on those datasets. If we decide to use Datasets 3 and 4 later in the project, we will perform additional cleaning and quality assessments on them at that time.

After we were all done, I started organizing the different files into folders for this project to make sure everything was well organized. 



### Aiden's Update Summary and Contribution**

**Updates:**  For this status report, I updated the team roles, and timeline to be more specific as noted by the TA’s in the Project Plan submission comments. I also updated the project question (specifically Q2), so we can more closely align our project focus with class content (the topic of integration). Updates can be seen above. 


**New Contributions:** 

For this portion of the project, I cleaned our datasets and tried to eliminate any inconsistencies in the Line column since we are primarily merging by this column. This initial cleaning did not take very long since the data is already fairly consistent, but this cleaning still helped standardize the data. 

We got started on answering two of the six research questions for this project thus far. I specifically worked on Q1. This question worked only within dataset 1 (“MTA Subway Trains Delayed: Beginning 2020”), grouping by reporting category to find the most common type of delay. 

I also did a Data Quality analysis on dataset 1 and dataset 2, noting the Accuracy, Completeness, Consistency, and Timeliness. There was nothing alarming noted in the datasets that would throw off our research and integration.

