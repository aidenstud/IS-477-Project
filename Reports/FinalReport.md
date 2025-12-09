# Final Report 

## <p align="center"> NYC MTA Delays 2024</p>

### Contributors:

Victoria: Data Acquisition & Integration Lead
* Leads dataset collection and acquisition
* Oversees dataset integration and merging
* Handles data quality evaluation
* Manages storage, file organization, and GitHub structure
* Leads metadata creation and documentation
* Oversees final report writing and release 

Aiden: Data Cleaning & Research Lead
* Leads dataset cleaning and preprocessing
* Develops and refines research questions
* Identifies initial constraints and timeline development
* Handles data enrichment, workflow automation, and provenance tracking
* Leads reproducibility and transparency tasks
* Creates reproducible package and supports final report delivery

<br>

### Summary:

New York City is one of the most densely populated cities in the world, with millions of people relying on public transportation every day to get to work, school, and other destinations. Because of this, reliable public transit is crucial -- even the smallest delays can throw someone off course, and put them behind schedule. For this project, we will specifically be focusing on the MTA subway delays in 2024, analyzing patterns, causes, and passenger impacts to improve subway reliability and passenger experience.  

We were interested in studying the NYC subway system because we currently live in Chicago, a city with a comparable public transit system, and may potentially want to move to New York. In a bustling environment, being late can have real consequences, so understanding how well the subway operates—and how delays affect riders—felt meaningful and relevant.

The research questions that guided this project were:

>>Question 1: What are the most common delays? Do they occur often?
>>
>>Question 2: For each subway line and month, how many delay-causing incidents occurred, and how did it impact additional wait time for riders?
>>
>>Question 3: Do peak (rush-hour) riders experience longer travel times than non-peak riders?

<br>

### Data profile:

This section discusses descriptions of the datasets, and ethical/legal constraints.

*Datasets and Ethics*

Dataset 1: Our primary dataset was “MTA Subway Trains Delayed: Beginning 2020”. This dataset is organized by month, with each month (row) giving the reason for delays on each train line, whether the delays occurred on a weekday or weekend, and how many times each delay happened within the month. This dataset contains 6 columns and 21,800 rows, of which 3,766 correspond specifically to 2024 data.

The data from Dataset 1 is collected automatically by ATS system, or manually into the into the I-TRAC system depending on train line. There are are no ethical concerns besides possibilities of bias, misinterpretation of manually entered data, or human error.

Dataset 2: "MTA Subway Customer Journey-Focused Metrics: 2020-2024”. This dataset is organized by month, with each month (row) giving us the number of passengers, various wait time metrics, and peak vs non-peak rush hour periods for each train line. This dataset will be integrated with our primary dataset to show the relationship between delays and wait times for each train line. This dataset contains 12 columns and 2,856 rows, of which 576 correspond specifically to 2024 data.

The data from Dataset 2 is collected from MetroCard and OMNY swipe data to estimate each rider’s origin and destination. Since riders do not tap out, the MTA infers their exit station by looking at their next swipe within the same day or the following five days. These inferred trips are cleaned, scaled to match total ridership, and then compared against actual train movement data from systems like ATS, CBTC, and manual dispatcher inputs. Using this combined information, the MTA calculates metrics such as additional platform time, additional train time, and overall journey performance.

The MTA does not collect individual consent because MetroCard and OMNY data are tied to anonymous card IDs, not identifiable people. This reduces privacy concerns, but ethical issues remain, including the use of rider data without explicit permission and the potential risk of re-identification.

*Legal Topics*

Since both of these datasets come from the same governmental website (DATA.NY.GOV), they follow the same legal constraints for data usage and reproduction. The MTA Open Data Program, established under the 2021 MTA Open Data Act, requires the agency to publish a wide range of operational, financial, ridership, and performance datasets in open, machine-readable formats on DATA.NY.GOV. Open NY provides an open, non-exclusive, revocable license that allows the public to freely download, reuse, analyze, modify, publish, and share these datasets without attribution, share-alike requirements, redistribution restrictions, or pre-approval.

Although raw data is not copyrighted and may be reused freely, certain materials—such as images, logos, or proprietary content—may still be protected and require separate permission. Users may copyright their own analyses or visualizations but cannot claim ownership over the underlying DATA.NY.GOV data.

DATA.NY.GOV also reserves the right to revoke this license if a user violates the Terms of Use, such as through misuse of the site or infringement of protected content.

For more detail over ethical data handeling and the datasets, look in the Ethical_Data_Handeling file and Metadata_Documentation file. 

<br>

### Data quality:

This section summarizes quality assessment for each dataset. Data Quality assessments were performed using code, as shown in the Data_Collection_Cleaning.ipynb file, utilizing the metadata on the websites, and utilizing the Overview Reports for each dataset (pdfs over the overview reports on the websites as well).

*Dataset 1:* 

Overall, the dataset demonstrates strong data quality across accuracy, completeness, timeliness, and consistency. The data is highly accurate: subway lines are correctly matched to their divisions, incident counts are valid and non-negative values, day types use only the correct categories, and reporting categories align with the data dictionary, with no discrepancies found against “ground truth.” Completeness issues are minimal—538 rows appear "blank", but these rows are intentionally included as placeholders for each line and day type rather than true missing data; this was cleaned up before answering research questions. The dataset is also timely, updated monthly, with the most recent update on November 14, 2025, and includes complete coverage starting from January 2020 onward. Consistency is strong across all columns, with standardized date formats, valid division labels, correct train line identifiers, and numeric incident values.  

The MTA’s overview report highlights several limitations affecting data quality. Some line data is collected automatically via the Automated ATS system while other line data is manually collected via the I-TRAC system; the reporting categories are broad; delays with multiple causes are recorded only under the primary incident; classification rules for delay reporting categories have changed over time; some lines are combined, such as J/Z and N/W; COVID and Omicron schedule changes caused incomplete data in 2020–2022.

*Dataset 2:* 

Overall, the dataset demonstrates strong data quality across accuracy, completeness, timeliness, and consistency. The data is highly accurate:  subway lines are correctly matched to their divisions and exist in the real NYC subway system, period values use only valid categories (peak or off-peak), and all numeric fields are valid (even if negative values).  Completeness is excellent, as the dataset contains no missing rows and provides full monthly coverage for every line in 2024. For timeliness, the data set was last updated January 24, 2025; Although the dataset is not updated as frequently, it is not relevant in our case because we are only looking at 2024 data. Consistency is also strong, with standardized date syntax, valid line and division labels, correct peak/off-peak categories, numeric passenger counts, time metrics in minutes, and performance metrics in percentages.

The MTA’s overview report highlights several limitations affecting data quality. Train movement data may contain gaps or errors; some data is entered manually; some recording systems may misidentify trains or fail to capture their arrivals/departures; some days/stations/lines are excluded if poor data quality; metrics are only calculated on weekdays 6AM–11PM; Only one “representative” weekday per month is modeled; COVID and Omicron schedule changes caused incomplete data in 2020–2022; updates to the data-processing pipelines. 

More detail on the Data Quality Assessment can be found under the Data_Quality_Cleaning file. 

<br>

### Findings:

From our first research question, we found that “Police & Medical” was the most common source of delays in 2024, occurring 22,197 times. However, this pattern shifts month to month: “Operating Conditions” is the leading cause in March, while “Infrastructure & Equipment” and “Operating Conditions” dominate in July and August. “Crew Availability” and “External Factors” remain the least common causes throughout the year. The time-series visualization shows that most categories stay relatively stable, except “Police & Medical,” which dips in the summer, and “Operating Conditions,” which gradually declines across 2024. Although the categories are defined, the dataset does not provide detail on why these fluctuations occur.

From our second research question, we found that there is a weak relationship between the number of incidents and additional platform wait times. The correlation between total incidents and average additional platform time is approximately 0.38, indicating that incident counts explain very little of the variation in wait times. We also examined the range of average wait times in the integrated dataset, which spans from about 0.25 to 2.43 minutes—a difference of only about two minutes. Even in the original metrics dataset (without average the additional platform wait times by month and line) the range remains the same, the minimum and maximum values ebing 0.22 to 2.9 minutes respectively. These results were surprising because real delays can last much longer. After looking at the documentation, the "additional_platform_time" column is "an average estimated additional time in minutes", these averages potentially hiding super long wait times. 

From our third research question, we found that not all peak rush-hour riders experience longer travel times than non-peak riders; however, 13 out of 24 subway lines did show worse performance for peak riders. To measure this, we used the customer_journey_time column, which reports the percentage of riders completing their trip within five minutes of the scheduled time. This metric provided a clearer indicator of service quality than raw wait-time columns. When comparing peak and non-peak performance, negative values in the peak_nonpeak_diff % column signaled that peak riders experienced longer travel times. Line 6 showed the highest number of negative differences (12), suggesting heavier rush-hour strain, likely due to serving dense, high-traffic areas in Manhattan. January and November also had the highest counts of negative differences, indicating these months were particularly challenging for peak riders. We also found the largest difference to be –2.3%, meaning 2.3% fewer peak riders met the five-minute threshold. While small in percentage terms, this represents a meaningful impact given NYC’s extremely high ridership.

A more detailed set of findings, and supporting vizualizations can be found in the "Questions_Analysis_Vizualizations" folder.

<br>

### Future work:

This section addressed lessons learned and potential future work

When working on the first research question, we used only Dataset 1, MTA Subway Delay-Causing Incidents: Beginning 2020. From this analysis, we learned that Dataset 1 cannot reveal the true, specific causes of delays because it groups incidents into only six broad reporting categories. These categories are too general to explain what actually happened on a given day, line, or incident. For future work, a more detailed incident-level dataset could be integrated to uncover precise causes. One promising option is the “MTA Service Alerts: Beginning April 2020” dataset on DATA.NY.GOV, which records service disruptions by date and line and includes the full text of public alert messages. Merging this dataset with Dataset 1 could provide richer insight into what type of event truly occurred, how it was communicated to passengers, and how it aligns with the incident categories reported by the MTA. This integration may reveal new patterns, inconsistencies, or more granular explanations behind delay events.

When working on on the second research questionn, we used both dataset 1, MTA Subway Delay-Causing Incidents: Beginning 2020 and dataset 2, MTA Subway Customer Journey-Focused Metrics: 2020-2024. During this process, we learned that the “additional platform time” variable in Dataset 2 was not an ideal metric for evaluating rider wait times. According to the data dictionary, “additional platform time” is defined as "“The average estimated additional time in minutes (above scheduled time) customers wait for their train, reported each month and on each line." Because the dataset already reports this value as a monthly average per line and per period (peak vs. off-peak), any further averaging— such as the grouped column we created "avg_additional_platform_time" —may have masked meaningful variation.

Overall, many values in Dataset 2 are based on estimates or aggregated averages. While this is reasonable given the difficulty of measuring individual rider movements without tap-out data, it limits how precisely wait-time patterns can be evaluated. As a result, Dataset 2 may smooth out extreme values and potentially underrepresent severe delays, reducing its usefulness for analyzing riders' actual wait-time experiences. Future work could involve collecting more detailed wait-time data instead of relying on monthly averages. One option would be to run our own study: with rider consent, we could track tap-in and tap-out times from a sample of NYC subway users over a year to build a more accurate rider-level dataset for analyzing actual wait and travel times.

Lastly, when working on the third research question, we used only dataset 2, MTA Subway Customer Journey-Focused Metrics: 2020-2024. Because of the limitations identified in Q2, we chose to rely on the "customer_journey_time" variable for Question 3 to assess wait times. Based off the data dictionary, this metric is defined as "the estimated percentage of customers whose journeys are completed within 5 minutes of the scheduled time, reported each month and on each line". Even though this variable still uses estimates, it provides a more interpretable indicator of overall rider experience. While this dataset worked adequately for comparing peak vs. off-peak performance, future work could perhaps focus on uncovering why negative peak–non-peak differences occur. Since these differences are not directly explained in the customer-journey dataset, it may be useful to integrate this dataset with dataset 1, MTA Subway Delay-Causing Incidents, to explore potential causes— even if only through the six broad reporting categories available.

<br>

### Reproducing:

Follow these steps to reproduce our results

1. Open Visual Studio Code. In your Kernel, make sure you are using Python (specifically Python 3.11.4)
2. Open terminal and run "pip install -r requirements.txt" in your terminal. This installs all necessary libraries for this project
2. Create a new file and name it ".env"
3. Create an account on the DATA.NY.GOV website -->  https://data.ny.gov/
4. On the website, under your account username, click "Developer Settings", and create a New App Token
5. In the .env file, insert your App Token (regular, not Secret Token), Email and Password with these variable names:

    API_TOKEN = "APP TOKEN HERE"

    EMAIL = "EMAIL HERE"

    PASSWORD = "PASSWORD HERE"

    This ensure that your app token, email, and password are not publically visible when pushing out to github

6. Optional: if you want to push your results to github and not display your app token, username, and password, create a new file named ".gitignore". Insert this (without the \ in that file. \ used for illustrative purposes here):

    \# .gitignore 

    \# Ignore environment files 

    .env

7. Open the "Data_Collection_Cleaning" file and click "Run All" at the top of the notebook. Running this will pull in the datasets, create the "raw_data" and "SHA256" folders, and clean the datasets 
8. Open the "Questions_Analysis_Vizualizations" folder 
9. Open the "Q1" file and click "Run All" at the top of the notebook. This will load in the cleaned dataset, and run all the cells to get data analytics and data vizualizations for the first research question
10. Open the "Q2" file and repeat step 9
11. Open the "Q3" file and repeat step 9
12. Open the "Data_Analysis" folder to see writing components about the data lifecycle, cleaning, quality, ethical data handeling license and terms and conditions, metadata, reproduction transparancy, storage organization, and workflow. 
12. Open the "Reports" folder and open the "FinalReport" file to see the final report for the project

Check the Reproduct_Transparency file if need more guidance to reproduce project.

<br>

### References: 

*Citations:* 

In APA7 format

- *MTA Open Data Program*. MTA. (n.d). https://www.mta.info/open-data 

- *Open- NY terms of use: State of New York*. OPEN- NY Terms Of Use | State of New York. (n.d.). https://data.ny.gov/dataset/OPEN-NY-Terms-Of-Use/77gx-ii52/about_data 

- State of New York. (n.d.). MTA Subway Delay-Causing Incidents overview report [PDF]. https://data.ny.gov/TransportationMTA-Subway-Delay-Causing-Incidents-Beginning-2020/g937-7k7c/about_data

- State of New York. (n.d.). MTA Subway Customer Journey–Focused Metrics overview report [PDF]. https://data.ny.gov/Transportation/MTA-Subway-Customer-Journey-Focused-Metrics-2020-2/4apg-4kt9/about_data

*Datasets:*

- State of New York. (2025). MTA Subway Delay-Causing Incidents: Beginning 2020 [Data set]. State of New York. https://data.ny.gov/Transportation/MTA-Subway-Delay-Causing-Incidents-Beginning-2020/g937-7k7c/about_data

- State of New York. (2025). MTA Subway Customer Journey-Focused Metrics: 2020–2024 [Data set]. State of New York. https://data.ny.gov/Transportation/MTA-Subway-Customer-Journey-Focused-Metrics-2020-2/4apg-4kt9/about_data 

- Box link with Output dataframes: https://uofi.box.com/s/ev4tdq17g2mqs76ihxyxursu6xc60fua

*Softwares:*
- Visual Studio Code (VSC)
- Python
- Jupyter Notebook
- DuckDB (SQL)
- Python Libraries --> can be found in the requirements.txt file 

<br>

**Anything missing information in this report can be found in the Data_Analysis folders, where all detailed markdown files are located.** 

