# Metadata and Data Documentation

**Dataset 1 SCHEMA: MTA Subway Delay-Causing Incidents: Beginning 2020**

| Column Name         | Description                                                                                                                             | Data Type             |
|---------------------|-----------------------------------------------------------------------------------------------------------------------------------------|------------------------|
| month               | The month in which delay-causing incidents are being calculated (yyyy-mm-dd).                                                           | Floating Timestamp     |
| division            | Represents the A Division (numbered subway lines) and B Division (lettered subway lines).                                               | Text                   |
| line                | Represents each subway line (1, 2, 3, 4, 5, 6, 7, A, C, E, B, D, F, M, G, JZ, L, N, Q, R, S 42nd, S Rock, S Fkln).                      | Text                   |
| day_type            | Represents weekday as 1 and weekend as 2.                                                                                               | Number                 |
| reporting_category  | The six categories that delays are reported under: Crew Availability, External Factors, Infrastructure & Equipment, Operating Conditions, Planned ROW Work, and Police & Medical. | Text                   |
| Incidents           | The number of train incidents that caused one or more delays, per reporting category, line, and month.                                  | Number                 |

<br>

Under the MTA Subway Delay-Causing Incidents Overview the reporting categories are defined as: 
- Crew Availability: Delays caused by lack of crew (train operator, conductor, and/or tower
operator).
- Planned ROW Work: Delays due to planned right-of-way work for maintenance and capital
projects.
- Infrastructure & Equipment: Delays due to infrastructure and equipment failures on the system.
These failures may include issues with signaling, track, car equipment, stations, and more—
provided that it is found that a group within the Department of Subways was responsible for the
problem. This category also includes any delays that resulted from the activities of internal
personnel
- Police & Medical: Delays resulting from actions taken by the public. This category encompasses
delays that relate to customer misconduct, the police response to incidents, sick and injured
passengers, unauthorized persons on the roadbed, or persons come in contact with trains.
- Operating Conditions: Delays due to congestion, crowding, and from trains skipping stops to
manage other delays.
- External Factors: Delays caused by factors outside the agency’s control, such as power outages,
fires outside MTA property, bridge openings, external debris that fall on our tracks, and
inclement weather

<br><br>

**Dataset 2 SCHEMA: MTA Subway Customer Journey-Focused Metrics: 2020-2024**

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