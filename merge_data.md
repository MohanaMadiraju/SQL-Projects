![merge_data](https://github.com/user-attachments/assets/0dc0219b-0b46-4241-9abc-86ca7b4b34cc)


# BigQuery Analysis of Citi Bike Data

## Overview
This project demonstrates how to use Google BigQuery to analyze publicly available Citi Bike trip data. It includes SQL queries to calculate:
- Popular routes based on the number of trips.
- Average trip duration by user type.
- Insights into user behavior.

## Query
The SQL query calculates the most popular routes and their average duration:
```sql
SELECT 
    usertype,
    CONCAT(start_station_name, " to ", end_station_name) AS route,
    COUNT(*) AS num_trips,
    ROUND(AVG(CAST(tripduration AS INT64) / 60), 2) AS duration
FROM 
    `bigquery-public-data.new_york_citibike.citibike_trips`
GROUP BY 
    start_station_name, end_station_name, usertype
ORDER BY 
    num_trips DESC
LIMIT 10;
