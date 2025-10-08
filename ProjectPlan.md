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

Dataset 1: Our primary dataset will be “MTA Subway Trains Delayed: Beginning 2020”. This dataset is organized by month, with each month (row) giving the reason for delays on each train line, whether the delays occurred on a weekday or weekend, and how many times each delay happened within the month.

Dataset 2: "MTA Subway Customer Journey-Focused Metrics: 2020-2024”. This dataset is organized by month, with each month (row) giving us the number of passengers, various wait time metrics, and peak vs non-peak rush hour periods for each train line.  This dataset will be integrated with our primary dataset to show the relationship between delays and wait times for each train line. 

Dataset 3: “MTA Subway Service Delivered: 2020-2024”. This dataset is organized by month, with each month (row) comparing how many trains were scheduled vs how many trains actually showed up during the weekday vs weekends. This dataset will be integrated with our primary dataset to see which trainlines are most reliable even if delays occur. 

Dataset 4: “MTA Service Alerts: Beginning April 2020”.This dataset is organized by date and records which train lines experienced delays, the content of the public service announcements for each delay, and how many times passengers were updated. This dataset will be integrated with our primary dataset to provide detailed insights into delays since the primary dataset groups “reasons for delays” into six broad categories.

Timeline: Document the plan and timeline for implementing your project including who will complete each task. Your plan must clearly address each of the requirements described above.

Project Planning and Data Acquisition - Aiden & Victoria
    Dataset cleaning and Preprocessing
    Clean and standardize delay codes- Both
    Process large data sets- Aiden
    Merge datasets into analysis set- Victoria
    Exploratory Data Analysis
    Analyze delay reasons, frequencies, and distributions- Victoria
    Create visualizations of delayed lines/other exploratory visuals- Aiden
    Advanced Analysis and Impact Modeling
    Compare peak vs off ride impact- Victoria
    Calculate time lost per line- Aiden
    Determine other helpful metrics and create visualizations to represent findings- Both
    Interim Status Report- Both
    Create Final Visualizations and Reporting
    Create final visualizations and summary stats- Victoria
    Draft final paper- Aiden
    Final Submission and Release- Aiden & Victoria
    Final review of code
    Final review of paper
    Release on GitHub


Constraints: Describe any known constraints.
Some of the datasets are large and may require memory-efficient processing techniques.
We may need to bolster our current selection of data with additional sets if we cannot answer our research questions. 
The “reporting_category” column is broken up into six categories: Crew Availability, External Factors, Infrastructure & Equipment, Operating Conditions, Planned ROW Work, and Police & Medical. These are not super detailed and there is room for interpretation by the reader. 
The first three datasets are broken up into months whereas the last dataset is broken up by data. We will need to group the data or manipulate the data column in the dataset 4 so we can seamlessly integrate this dataset with the others to make useful comparisons. 

Gaps: Identify any known gaps or areas where you need additional input.
Your plan should anticipate later course topics even if you don’t yet know all the details. It is expected that your plan will evolve over time.
Our model and project will simplify passenger journeys. We cannot account for transfers or the ripple effects of one delay on other trains/lines. 
We anticipate that we will want to expand the scope and components of our project as the course continues. We will evaluate what other concepts we want to include as we come across them. The modules on reproducibility and data documentation will likely influence the scope and nature of our project in the coming weeks.
Our knowledge of public transport is limited, and we are not from NYC, so our conclusions may not completely be accurate or truly represent the causes of delays and their effects. We hope to provide meaningful analysis and insight into the issue, despite not being professionals in this field.










