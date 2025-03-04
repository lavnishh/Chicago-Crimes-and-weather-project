# Chicago Crime and Weather

**Author**: Lavnish Singh Bisht <br />


## Introduction
This project is a comprehensive analytical repository that examines crime patterns in Chicago alongside weather data from 2018 to 2023. The primary objective is to uncover insights into the dynamics of criminal activity by:

Analyzing Overall Trends:
Determining the total number of reported crimes, identifying the most common crime types (such as theft, battery, and assault), and calculating their percentage contributions.

Community-Level Insights:
Identifying both the communities with the highest and lowest crime counts, while considering additional demographic factors like current population and population density.

Temporal and Weather-Related Patterns:
Examining which months experience the highest crime rates and the corresponding weather conditions (e.g., average and median high temperatures). It also includes analysis of the relationship between weather conditions—such as precipitation and temperature—and crime occurrence.





* [Data Analysis Question & Answers](./questions_and_answers.md)

## Datasets used
Eight key [datasets](./source_data/csv/) for this case study
- <strong>chicago_areas.csv</strong>: Chicago neighborhoods and areas.
- <strong>chicago_temps_18-23.csv</strong>: City Weather 2018-2022.
- <strong>chicago_crime_2018.csv</strong>: Reported crimes in 2018.
- <strong>chicago_crime_2019.csv</strong>: Reported crimes in 2019.
- <strong>chicago_crime_2020.csv</strong>: Reported crimes in 2020.
- <strong>chicago_crime_2021.csv</strong>: Reported crimes in 2021.
- <strong>chicago_crime_2022.csv</strong>: Reported crimes in 2022.
- <strong>chicago_crime_2023.csv</strong>: Reported crimes in 2023.


## Entity Relationship Diagram

Entities:
---------
1. Crimes
   - crime_id (PK, int)
   - reported_crime_date (date)
   - reported_crime_time (time)
   - street_name (text)
   - crime_type (text)
   - crime_description (text)
   - location_description (text)
   - arrest (bool)
   - domestic (bool)
   - community_id (FK, int) -> References Community
   - latitude (float)
   - longitude (float)
   - crime_location (text)

2. Community
   - community_id (PK, int)
   - community_name (text)
   - population (int)
   - area_size (float)
   - density (float)

3. Weather
   - weather_id (PK, int)
   - weather_date (date)
   - temp_high (int)
   - temp_low (int)
   - average (float)
   - precipitation (float)

Relationships:
--------------
- Crimes (community_id) → Community (community_id) [Many-to-One]
- Crimes (reported_crime_date) → Weather (weather_date) [Many-to-One]



## Some insights on the findings from the analysis

Crime Types and Trends:
Theft, battery, and criminal damage are the most common crimes, with theft alone making up 22% of incidents. Violent crimes, particularly battery and assault, are also significant, while homicides, though less frequent, remain critical due to their severity.

Community Impact:
Crime is concentrated in areas like Austin, Near North Side, and Near West Side, whereas neighborhoods like Edison Park and Burnside experience much lower crime levels, suggesting socio-economic and demographic influences.

Weather and Crime:
Crime peaks in warmer months, particularly July, which also records the highest homicide numbers. Precipitation levels appear to influence daily crime rates, indicating weather conditions may play a role in crime occurrence.

This analysis highlights key factors influencing crime trends, offering valuable insights for urban safety and policy planning.
