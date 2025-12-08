# Elements for Reproducible Computational Research

Manuscript: all written reports (Project Plan, Status Report, Final Report) are located in the Reports folder. Starting from Project Plan, you can see the evolution of the project, any changes made through-out, and final results.

Data: all raw data used in the project is stored in the raw_data folder. Cleaned and analysis ready datasets are generated in Data_Collection_Cleaning file

Code: the code for data acquisition/collection and cleaning is under the file name Data_Collection_Cleaning. Code for data analysis and data vizualizations would be found in the Questions_Analysis_Vizualizations folder

Results: look in the Questions_Analysis_Vizualizations folder. In Q1, Q2, and Q3 files, you will see the code, data analysis and data vizualiazations for questions 1-3 

Workflow:

1. Run "pip install -r requirements.txt" in your terminal. This installs all necessary libraries for this project
2. Click data-colelction-cleaning
3. q1
4. q2
5. q3
6. look at the data_analysis folder in these steps: 
7. 

Provenance: Data was found on the DATA.NY.GOV, an official NY State Government Website; data was acquired by MTA subway services. Data was pulled from the website via a personlizaed API Token, email, and password; the pandas, python-dotenv, and sodapy libraries were utilized during this process. To make sure data was not manipulated in the process, we used SHA256 for our integrity check-point. These lines of code (in the Data_Collection_Cleaning file) output files in the SHA256 and raw_data folders. Data cleaning was also done at the end.  

Environment: base(Python 3.11.4), Jupyter Notebook, Visual Studio Code, DuckDB, and required Python libraries listed in requirements.txt. Analysis was run on Windows 10

License: open source (non-exclusive, revocable license)

Citations: 
- URL for Dataset 1: https://data.ny.gov/Transportation/MTA-Subway-Delay-Causing-Incidents-Beginning-2020/g937-7k7c/about_data --> this URL also links to the overview pdf:  MTA_SubwayDelayCausingIncidents_Overview.pdf 

- URL for Dataset 2: https://data.ny.gov/Transportation/MTA-Subway-Customer-Journey-Focused-Metrics-2020-2/4apg-4kt9/about_data --> this URL also links to the overview pdf: MTA_SubwayCustomerJourneyMetrics_Overview.pdf 

- https://www.mta.info/open-data 

- https://data.ny.gov/dataset/OPEN-NY-Terms-Of-Use/77gx-ii52/about_data 







