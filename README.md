
# UK Road Collision Analysis 2019-2022

This data analysis project aims to provide insights into the collision rate on UK roads from 2019 to 2022. By analyzing various parts, we seek to identify trends, make data-driven
reccomendations and gain a deeper understanding of the use of transport.

## Data Source

The datasets I used were from the GOV UK data sets, I used the road casualty COLLISIONS dataset, I downloaded from 2019-2022

### Tools
- Excel - Data cleaning
- PostgreSQL - Data analysis
- Tableau - Data visualization and reports

#### Data Cleaning/Preparation

In the initial stage, I prepared the data in Excel, the following tasks I did were:

- Data loading, combining and transforming.
- Giving each column its correct format.
- Removed any duplicates and dealt with missing values.
- Formatted the data.

#### Exploratory Data Analysis

I will now involve EDA in the casualty data to answer key questions such as:

- How has the total number of road collisions changed from 2019 to 2022?
- Are there any seasonal patterns or spikes in specific months?
- What is the impact of road surface conditions (e.g., wet, dry) on collisions?


#### Data Analysis

Here are the code I have used in PostgreSQL

    SELECT accident_year, COUNT(number_of_casualties)
    from roadc
    GROUP BY accident_year

    SELECT
    EXTRACT(YEAR FROM date) AS year,
    EXTRACT(MONTH FROM date) AS month,
    COUNT(*) AS collision_count
    FROM
    roadc
    GROUP BY
    year, month
    ORDER BY
    year, month;

    SELECT
    road_surface_conditions,
    COUNT(*) AS collision_count
    FROM
    roadc
    GROUP BY
    road_surface_conditions
    ORDER BY
    collision_count DESC;



#### Results/Findings

1. The number of collisions has increased, with a decrease only during 2019-2020 due to COVID-19. However, in 2022, total collisions are similar to those in 2019.

2. There is a clear seasonal pattern in collisions. It tends to decrease after January, possibly due to post-holiday factors, but then rises around March and continues increasing up to November before declining. This seasonal variation suggests that certain months may require heightened safety measures.

3. According to the analysis of road collision data from 2019 to 2022, dry road conditions have recorded a higher number of collisions compared to wet road conditions. This suggests that drivers may encounter more collisions on dry roads due to factors such as higher speeds and decreased caution compared to wet roads.

#### Reccomendations

Based on the analysis, I would reccomend the actions:

- Deploy more additional resources during peak months to reduce risks
- Implement safety initiatives during high incident months
- Enhance road maintenance during rainy seasons to improve surface conditions
- Consider implementing more road safety measures that respond to weather conditions
- Increase fines for violations during dry weather conditions to encourage safer driving behavior, potentially reducing the number of collisions.

#### Limitations

One of the primary limitations encountered was a high number of missing values in the dataset. The absence of these values limited my ability to draw definitive conclusions on years or road types. To address this, I used Excel to handle missing data. Moving forward, improving data collection protocols and ensuring data completeness will be essential for enhancing the accuracy and reliability of future analyses.

