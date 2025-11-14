# IS477 Project Status Report

### Research Question(s):

* Q1: What are the most common delays? Do they occur often? 

* **Q2: For each subway line and each month, how many delay-causing incidents occurred, and what was the corresponding Total Additional Platform Time (total APT) experienced by all riders?**

* Q3: Which train line has the most delays? Is the cause for the delay the same each time? Are delays frequent? 

* Q4: Which train line (delays) have the longest wait times? 

* Q5: Which months (in 2024) had the worst customer experience overall, such as longer wait times? 

* Q6: Do planned maintenance activities (Planned ROW Work delays) correspond to improved service delivered in later months? 


### Team:

* Data Collection and Integration Lead - Victoria
* Data Integrity Check Lead - Victoria 
* Data Cleaning Lead - Aidan
* Data Research Lead - Aidan 
* Data Vizualization and Analysis Lead(s)- Aidan and Victoria

### Dataset(s):

We will be working with 4 datasets, all coming from the New York State government website.

Dataset 1: Our primary dataset will be “MTA Subway Trains Delayed: Beginning 2020”. This dataset is organized by month, with each month (row) giving the reason for delays on each train line, whether the delays occurred on a weekday or weekend, and how many times each delay happened within the month. URL: https://data.ny.gov/Transportation/MTA-Subway-Delay-Causing-Incidents-Beginning-2020/g937-7k7c/about_data 

Dataset 2: "MTA Subway Customer Journey-Focused Metrics: 2020-2024”. This dataset is organized by month, with each month (row) giving us the number of passengers, various wait time metrics, and peak vs non-peak rush hour periods for each train line.  This dataset will be integrated with our primary dataset to show the relationship between delays and wait times for each train line. URL: https://data.ny.gov/Transportation/MTA-Subway-Customer-Journey-Focused-Metrics-2020-2/4apg-4kt9/data_preview 

Dataset 3: “MTA Subway Service Delivered: 2020-2024”. This dataset is organized by month, with each month (row) comparing how many trains were scheduled vs how many trains actually showed up during the weekday vs weekends. This dataset will be integrated with our primary dataset to see which trainlines are most reliable even if delays occur. URl: https://data.ny.gov/Transportation/MTA-Subway-Service-Delivered-2020-2024/bg59-42xi/data_preview 

Dataset 4: “MTA Service Alerts: Beginning April 2020”.This dataset is organized by date and records which train lines experienced delays, the content of the public service announcements for each delay, and how many times passengers were updated. This dataset will be integrated with our primary dataset to provide detailed insights into delays since the primary dataset groups “reasons for delays” into six broad categories. URL: https://data.ny.gov/Transportation/MTA-Service-Alerts-Beginning-April-2020/7kct-peq7/data_preview 

### Timeline:

Week 5-6: Project Planning and Data Acquisition

* Dataset Overview: Victoria
* Dataset Collection: Victoria
* Research Questions: Aiden
* Timeline: Aiden
* Constraints: Victoria
* Gaps: Aiden

Week 7-11: Interim Status Report

* Week 7-8: (Data Processing)
    * Clean and standardize delay codes: Aiden
    * Process large data sets: Aiden
    * Merge datasets into analysis set: Victoria
* Week 10-12: (Exploratory Data Analysis)
    * Analyze delay reasons, frequencies, and distributions: Victoria
    * Create visualizations: Aiden

Week 12-15: Final Project Submissions

* Create final visualizations and summary stats: Victoria
* Workflow automation and provenance with snakemake: Aiden
* Draft final paper: BOTH
* Final review of code: BOTH
* Final review of paper: BOTH


### Victoria's Update Summary and Contribution

**Updates:** For this status report, I added in the URLS to the respective datasets I found initially. Updates can be seen above! 

**New Contributions:**

For this Status report, we primarily worked on the Dataset Cleaning and Processing. I specifically uploaded the datasets into VSC and integrated them. When uploading the datasets onto here, I created an API Token (hiding my email and password for security reasons) to pull all the rows from each dataset; before putting the data into a dataframe, I made sure to filter out the months/date columns to only include data from 2024 which would be relevant for our analysis. 

After that, I created the SHA256 Integrity Checksum for each dataset I pulled before any Data Analysis and Integration. 

We got started on answering two of the six research questions for this project thus far. I specifically worked on Q2, integrating the dataset 1 (“MTA Subway Trains Delayed: Beginning 2020”) and dataset 2 (“MTA Subway Customer Journey-Focused Metrics: 2020-2024”) together to find out if the number of incidents (accidents) on the train rails affected customers wait time for each line in each month. I used duckdb to be able to do SQL integration. 

So far, our work has been focused primarily on Datasets 1 and 2, so the majority of our cleaning, integration, and data quality checks have been completed on those datasets. If we decide to use Datasets 3 and 4 later in the project, we will perform additional cleaning and quality assessments on them at that time.

After we were all done, I started organizing the different files into folders for this project to make sure everything was well organized. 


### Aiden's Update Summary and Contribution**

**Updates:** Updated project timeline and cleaned datasets so they can be merged.

**New Contributions:** 

For this portion of the project, I cleaned our datasets and tried to eliminate any inconsistencies in the Line column. This initial cleaning did not take very long and helped standardize the data. I also updated the project question, so we can more closely align our project focus with class content. The project timeline was also updated to fit the course of the project. We also began answering our initial research questions.
