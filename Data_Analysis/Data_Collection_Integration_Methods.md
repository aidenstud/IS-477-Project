# Data Collection and Integration Methods

**Data Collection:** 

To retrieve the data, we generated an API token by creating an account on the DATA.NY.GOV website. To keep our app token, email, and password private when pushing the project to GitHub, we stored this information in the ".env" and "gitignore" files so it would not be publicly visible.

Before putting the data into dataframes, we made sure to filter out the months/date columns to only include data from 2024 which would be relevant for our analysis. 

After that, we created the SHA256 Integrity Checksum for each dataset to ensure there was no data manipulation in the process. 

The dataset URLs can be located throughout the Directory Structure; the raw data in csv format can be found in the raw_data folder (after running the Data_Collection_Cleaning file) or in the Data_Analysis folder, under the Reproduct_Transparency file (citations). 

The GitHub repository link to find dataset URLs: https://github.com/aidenstud/IS-477-Project/blob/main/Data_Analysis/Reproduct_Transparency.md 

Dataset 1 URL- MTA Subway Delay-Causing Incidents: Beginning 2020: https://data.ny.gov/Transportation/MTA-Subway-Delay-Causing-Incidents-Beginning-2020/g937-7k7c/about_data

Dataset 2 URL- MTA Subway Customer Journey-Focused Metrics: 2020-2024: https://data.ny.gov/Transportation/MTA-Subway-Customer-Journey-Focused-Metrics-2020-2/4apg-4kt9/about_data 

**Data Integration:**

We used duckdb to be able to do SQL integration.
