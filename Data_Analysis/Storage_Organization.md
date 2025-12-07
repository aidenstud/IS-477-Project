# Storage and Organization

We utilized Git hub for version control while working on the project. It stores our work files remotely. 

**Folder/File Organization**

The project repository is broken up into files and folders (Logical File System): 

Driver File Data_Collection_Cleaning: a stand-alone ipynb file that documents data collection, data cleaning, and preparing data for integration and further analysis when answering our research questions. The naming convention follows a descriptive format where the file name directly states its function (data collection and cleaning). 

Folder SHA256: contains private SHA hashes for each dataset. The naming convention for the files in this folder were all "BLANK.sha", BLANK being the variable name for each dataset when we pulled them into VSC. 

Folder Reports: contains written reports submitted (Project Plan, Status Report, and Final Report). The naming convention for these files is descriptive of the report type and its purpose.

Folder raw_data: contains all the raw data imported. They are all stored as csv files. The naming convention for the csv files in this folder were all "BLANK.csv", BLANK being the variable name for each dataset when we pulled them into VSC. 

Folder Questions_Analysis_Vizualizations: contains 3 seperate ipynb files, answering our 3 questions for the project, and providing data analysis and vizualizations for support. The naming convention for the files in this folder were all "Q#.ipynb" reflecting research question (Questions 1-3) addressed in each notebook.

Folder Data_Analysis: contains 8 markdown files, covering all required writing components of the project (besides the reports). The naming convention reflects the specific topics covered in the markdown.

<br>

**Database**

In this project, we answered 3 questions, all of which were structured, relational databases (tables). 

Q1 Research Question: The first research question utilized dataset 1: MTA Subway Delay-Causing Incidents: Beginning 2020. For our purpose (only using 2024 data), the dataset has 3766 rows, and 6 columns. All the data in the table follow the same schema. 

Q2 Research Question: The second research question integrated both datasets 1 and 2 with DuckDB (SQL). No primary or foreign keys are formally defined in this query, but the fields (line, month) function as a composite key because they uniquely identify each aggregated row and are used to join the two datasets. After integration, the table has 276 rows, and 6 columns. 

The schema for the integrated dataset is outlined below:

| Column Name                     | Data Type      |
|---------------------------------|----------------|
| line                            | Text           |
| month                           | Floating Timetamp                                           |
| total_incidents                 | Number         |
| total_apt                       | Number         |
| total_passengers                | Number         |
| avg_additional_platform_time    | number         |

Q3 Research Question: The third research question utilized dataset 2: MTA Subway Customer Journey-Focused Metrics: 2020-2024. For our purpose (only using 2024 data), the dataset has 576 rows, and 12 columns. All the data in the table follow the same schema. 

<br><br>

Dataset 1 SCHEMA: MTA Subway Delay-Causing Incidents: Beginning 2020

| Column Name         | Description                                                                                                                             | Data Type             |
|---------------------|-----------------------------------------------------------------------------------------------------------------------------------------|------------------------|
| month               | The month in which delay-causing incidents are being calculated (yyyy-mm-dd).                                                           | Floating Timestamp     |
| division            | Represents the A Division (numbered subway lines) and B Division (lettered subway lines).                                               | Text                   |
| line                | Represents each subway line (1, 2, 3, 4, 5, 6, 7, A, C, E, B, D, F, M, G, JZ, L, N, Q, R, S 42nd, S Rock, S Fkln).                      | Text                   |
| day_type            | Represents weekday as 1 and weekend as 2.                                                                                               | Number                 |
| reporting_category  | The six categories that delays are reported under: Crew Availability, External Factors, Infrastructure & Equipment, Operating Conditions, Planned ROW Work, and Police & Medical. | Text                   |
| Incidents           | The number of train incidents that caused one or more delays, per reporting category, line, and month.                                  | Number                 |


<br><br>


Dataset 2 SCHEMA: MTA Subway Customer Journey-Focused Metrics: 2020-2024

| Column Name                  | Description                                                                                                                                                                             | Data Type            |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------|
| month                        | The month in which the metrics are being calculated (yyyy-mm-dd).                                                                                                                       | Floating Timestamp   |
| division                     | The A Division (numbered subway lines and S 42nd) and B Division (lettered subway lines).                                                                                               | Text                 |
| line                         | Each subway line (1, 2, 3, 4, 5, 6, 7, A, C, E, B, D, F, M, G, JZ, L, N, Q, R, W, S 42nd, S Rock, S Fkln).                                                                               | Text                 |
| period                       | Represents both the peak and off-peak service periods.                                                                                                                                  | Text                 |
| num_passengers               | Total number of estimated passengers reported each month and on each line.                                                                                                               | Number               |
| additional_platform_time     | The average estimated additional time in minutes (above scheduled time) customers wait for their train, reported each month and on each line.                                           | Number               |
| additional_train_time        | The average estimated additional time in minutes (above scheduled time) customers spend onboard a train, reported each month and on each line.                                           | Number               |
| total_apt                    | The total number of estimated additional time in minutes (above scheduled time) customers wait for their train, reported each month and on each line.                                    | Number               |
| total_att                    | The total number of average additional time in minutes (above scheduled time) customers spend onboard a train, reported each month and on each line.                                     | Number               |
| over_five_mins               | The estimated total number of customers whose journeys are not completed within 5 minutes of the scheduled time, reported each month and on each line.                                  | Number               |
| over_five_mins_perc          | The estimated percentage of customers whose journeys are not completed within 5 minutes of the scheduled time, reported each month and on each line.                                     | Number               |
| customer_journey_time        | The estimated percentage of customers whose journeys are completed within 5 minutes of the scheduled time, reported each month and on each line.                                         | Number               |

