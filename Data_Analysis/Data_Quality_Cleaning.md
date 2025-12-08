# Data Quality:
Code for Data Quality and Cleaning can be found under the file Data_Collection_Cleaning.ipynb.

**Dataset 1: MTA Subway Delay-Causing Incidents: Beginning 2020**

URL: https://data.ny.gov/Transportation/MTA-Subway-Delay-Causing-Incidents-Beginning-2020/g937-7k7c/about_data --> MTA_SubwayDelayCausingIncidents_Overview.pdf  

Accuracy: Amongst all 6 columns, the columns were both syntactically and semantically accurate. We validated the “ground truth” relationships between the division and line columns, confirming that every subway line listed exists in the real NYC subway system and is correctly assigned to its division. All incident counts were non-negative, the "day_type" column correctly used only the two valid categories (weekday = 1, weekend = 2), and all "reporting_category" values matched the definitions provided in the data dictionary. Overall, there were no discrepancies according to the “ground truth”. 

Completeness: The dataset had 538 rows containing missing data. This was because the first row for each train line for each day (either weekend or weekday) always starts off with a blank under the Reporting Category Col and a 0 in the incidents column. While this is intentional and not an indicator of missing data, it is still something to be aware of. 

Timeliness: According to the Data.NY.Gov website, this dataset was just recently updated on October 24, 2025. As stated in documentation, this dataset is updated each month. Both the data and the meta data were uploaded on the same day. The dataset provides content for each line for each month starting from 20-01-01. 

Consistency: The dataset is consistent. Under the Reporting Category, there are 6 options to choose from and no other variations so it is easy to categorize the types of incidents. While these 6 options help with consistency, it does limit true understanding of what actual incident is. The other columns are consistent as well: The Month column follows the same syntax of Year-Month-Day, the Division column only has options from A Division or B Division, the Line column only contains numbers or letters of real train lines in the MTA, and the Incidents column only has numbers.  

DATA.NY.GOV also provides a MTA Subway Delay-Causing Incident report that presents an overview of the data. Some limitations noted relate to impacting Accuracy, Timeliness, Completeness, and Consistency:
- Automated ATS data generally provides more reliable tracking for numbered lines, while manual I-TRAC entry for lettered lines introduces more human error and inconsistency.
- The (6) reporting categories are broad, which reduces precision.
- Trains delayed by multiple events are recorded only under the most significant incident, leaving secondary causes uncounted.
- Classification rules for delay reporting categories have changed over time, affecting the comparability of trends. Example: In Sept 2021, Crew Availability delays were grouped into a single incident category, lowering incident counts. In mid-2023, Operating Conditions delays were reassigned to more specific root causes, decreasing that category but increasing others.
- Data for the J and Z lines are combined and show up under JZ, and data for the N and W lines are combined and show up under N. 
- March and April 2020 have incomplete delay data due to COVID schedule changes, so the MTA estimated full-month totals based on limited days of data. A similar issue occurred during the Omicron surge in 2021–2022, when performance was measured against the temporary schedules in place. Although these events did not occur during 2024 (2024 data is only important for our research questions), it is still important to take note of.  

<br> 

**Dataset 2: MTA Subway Customer Journey-Focused Metrics: 2020-2024**

URL: https://data.ny.gov/Transportation/MTA-Subway-Customer-Journey-Focused-Metrics-2020-2/4apg-4kt9/about_data --> MTA_SubwayCustomerJourneyMetrics_Overview.pdf 

Accuracy: The dataset is accurate. Amongst all 12 columns, the columns were both syntactically and semantically accurate.  We validated the “ground truth” relationships between the division and line columns, confirming that every subway line listed exists in the real NYC subway system and is correctly assigned to its division. We also checked that the "period" column correctly used only the two valid categories (peak or offpeak), that all numeric columns were contextually valid (even in cases where values were negative), and made sure each followed the same syntax (such as the month column Year-Month-Day). Overall, there were no discrepancies according to the “ground truth”. 

Completeness: The dataset has no rows containing missing data.  

Timeliness: According to the Data.NY.Gov website, this dataset was updated January 24, 2025 and the meta data was updated July 14, 2025. Although it is not updated as frequently as the other datasets, it is not relevant in our case because we are only looking at 2024 data for our research questions and there is data for each month for each line in this dataset. 

Consistency: The dataset is consistent. The Month column follows the same syntax of Year-Month-Day, the Line column only contains numbers or letters of real train lines in the MTA,  the Division column only has options from A Division or B Division, the Period column only has options from Peak or Offpeak, and the Num_passengers column only has numbers, columns Additional Platform Time, Additional Train Time, Total_apt, Total_att, and Over_five_mins are all in minutes, and the Over_five_mins_perc and Customer journey time performance columns are all in percentages. 

DATA.NY.GOV also provides a MTA Subway Customer Journey-Focused Metrics report that presents an overview of the data. Some limitations noted relate to impacting Accuracy, Timeliness, Completeness, and Consistency:
- Train movement data can contain errors or missing records, requiring interpolation or backup data sources. 
- Manual dispatcher (I-TRAC) entries may include typos or inconsistent reporting.
- Beacon and PLC systems sometimes misidentify trains or fail to capture accurate arrival/departure times.
- Some days, stations, or entire lines must be excluded when data quality is too poor to use.
- Metrics are only calculated for weekdays between 6 AM–11 PM, leaving gaps for late nights and weekends.
- Only one “representative” weekday per month is modeled, which may not capture daily variation.
- Months affected by disruptions (ex: COVID, Omicron) contain partial data and require estimation.
- Changes to the data-processing pipeline (e.g., in 2024) make metrics not fully consistent with earlier years.

<br><br>

# Data Cleaning:
**Dataset 1: MTA Subway Delay-Causing Incidents: Beginning 2020**

Missing values: we started cleaning by dropping NaN values. By doing this, it removed 538 rows. 


Data Types: we used the dtypes function to check for data types. Because all the data types were objects at first, we converted them to their respective data types (datetime, integers, strings) so we can properly do data analysis on the columns. 


Duplicate rows: we checked for duplicate rows across the entire data set; there was no duplicate rows found. We did not check for duplicates based on specific columns because repeated values still had unique information in the other fields. 


Syntactic Check: 
- We accounted for white spaces and capitalization for all string columns to make sure everything is consistent. 
- Checked to make sure the months column was all following the same syntax so there is no data left out later in our analysis and integration; after checking, they all followed the same syntax. 


Semantic Check: 
- For the "incidents" column, we checked for negative values, since a negative number of "incidents" is not logically possible; there were no negative values so there was no additional cleaning needed. 
- Checked semantics between the "division" and "line" columns, since Division A is associated with numbered subway lines and Division B is associated with lettered subway lines; after, checking, all entries were correctly matched.


We also used the unique() function to check for any additional syntactic or semantic inconsistencies such as text-only columns containing numbers, or potential misspellings. No additional issues were found, so no further cleaning was necessary.


Overall, the only cleaning required involved handling missing values, correcting data types, and standardizing whitespace and capitalization (just incase).

<br>

**Dataset 2: MTA Subway Customer Journey-Focused Metrics: 2020-2024**

Similar cleaning done on dataset 2!

Missing values: we started cleaning by dropping NaN values. There are no missing values in this dataset. 

Data Types: like for dataset 1, we used the dtypes function to check for data types. Because all the data types were objects at first, we converted them to their respective data types (datetime, floats, strings). 

Duplicate rows: we checked for duplicate rows across the entire data set; there was no duplicate rows found.

Syntactic Check: 
- We accounted for white spaces and capitalization for all string columns to make sure everything is consistent.
- Checked to make sure the months column was all following the same; after checking, they all followed the same syntax.

Semantic Check: 
- *For the float columns, we checked for negative values. Although there was 77 rows containing negative values under the "additional_train_time" and "total_att" columns, it makes sense to keep these values, since negative numbers indicate that riders actually spent less additional time on the train.*
- Checked semantics between the "division" and "line" columns, since Division A is associated with numbered subway lines and Division B is associated with lettered subway lines; after, checking, all entries were correctly matched.


We also used the unique() function to check for any additional syntactic or semantic inconsistencies. No additional issues were found, so no further cleaning was necessary.


Like for dataset 1, the only cleaning required involved handling missing values, correcting data types, and standardizing whitespace and capitalization (just incase).
