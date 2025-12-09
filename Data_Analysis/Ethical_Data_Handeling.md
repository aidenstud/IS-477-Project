# Ethical Data Handeling

**Data Collection Process:**

URL for Dataset 1: https://data.ny.gov/Transportation/MTA-Subway-Delay-Causing-Incidents-Beginning-2020/g937-7k7c/about_data --> MTA_SubwayDelayCausingIncidents_Overview.pdf

URL for Dataset 2: https://data.ny.gov/Transportation/MTA-Subway-Customer-Journey-Focused-Metrics-2020-2/4apg-4kt9/about_data --> MTA_SubwayCustomerJourneyMetrics_Overview.pdf 

Dataset 1 - MTA Subway Delay-Causing Incidents: Beginning 2020: Delay data is collected automatically by ATS system, or manually into the into the I-TRAC system depending on train line. There are are no ethical concerns besides possibilities of bias, misinterpretation of manually entered data, or human error. 

Dataset 2 - MTA Subway Customer Journey-Focused Metrics: 2020-2024: Customer Journey Metric data is collected by using MetroCard/OMNY swipe and tap data to infer where riders enter and, algorithmically, where they likely exit, creating an origin–destination model. Because riders do not tap out, the MTA identifies each rider’s next swipe—later that day or within the next five days—and assumes that location is the rider’s exit for the previous trip. If no subsequent swipe is found, the model assumes the rider returned to their “home” station based on the first swipe of the period. Irrational or impossible trip pairings are removed, and the remaining inferred trips are scaled to match overall ridership totals. 

The MTA then matches these estimated trips to train schedule data and to actual train movement data collected from systems such as ATS, CBTC, PLC sensors, Beacon Bluetooth trackers, and manual dispatcher inputs. By comparing scheduled versus actual wait times and travel times for each inferred trip, they calculate metrics such as Additional Platform Time, Additional Train Time, and overall journey performance. 

The MTA does not obtain individual consent because it does not track identifiable people—MetroCard and OMNY taps are tied only to anonymous card IDs. While this reduces privacy concerns, there are still ethical considerations, such as the use of rider data without explicit consent and the potential risks if anonymized data were ever re-identified or misused.

<br>

**Legal Policy:**  

URL: https://www.mta.info/open-data 

The MTA Open Data Program, established under the 2021 MTA Open Data Act (Assembly Bill A1442B), requires the agency to make a wide range of operational, financial, ridership, and performance datasets publicly available in open, machine-readable formats. Today, the program includes more than 160 datasets on DATA.NY.GOV, with updates released annually to expand public access and strengthen transparency. In 2024, the MTA enhanced the program by cleaning and standardizing metadata and improving dataset categorization, making information more consistent and easier to locate through the catalog search tools.

<br>

**DATA.NY.GOV Terms and Conditions:** 

URL: https://data.ny.gov/dataset/OPEN-NY-Terms-Of-Use/77gx-ii52/about_data 

License and Permitted Uses: DATA.NY.GOV grants the public an *open, non-exclusive, revocable license* to freely use the datasets published on the platform. Under this license, you may download, reuse, analyze, share, publish, modify, and include the data in GitHub repositories, class reports, or academic research. The Terms explicitly state that Open NY does not impose attribution requirements, share-alike requirements, redistribution restrictions, or pre-approval for reuse.

Copyright: Raw datasets, tables, numbers, and any analyses you generate from them are not copyrighted. However, some components within certain datasets may still be protected and are not automatically licensed for reuse. These include photographs, videos, logos, graphical images, trademarks or service marks, software, or proprietary elements. If a dataset contains these types of materials, you must obtain permission from the agency that owns them before reuse. While the raw data remains open and publicly accessible, you can copyright your own contributions, including analysis, visualizations, cleaned or transformed datasets, code, and written reports. However, you cannot impose restrictions on the underlying Open NY data itself nor claim ownership over it, as it remains public and reusable. 

Revocation Rights: Although DATA.NY.GOV provides broad freedom to reuse its datasets, the State retains the right to revoke your license and restrict your use of the data if you violate the Terms of Use (Ex: , through illegal activity, misuse of the website, or infringement of protected materials).