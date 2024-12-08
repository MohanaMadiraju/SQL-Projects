![sub_queries](https://github.com/user-attachments/assets/0efd6bfd-1b27-419b-b858-67589b6a9402)

# BigQuery Subqueries: CitiBike Data Analysis

## Overview
This project demonstrates how to use subqueries in SQL with Google BigQuery to analyze the CitiBike dataset. The query identifies the top stations in New York City based on the number of rides starting from each station.

## Objective
To find the top CitiBike stations where the highest number of rides start and sort them in descending order by ride count.

## Query Breakdown
- **Subquery**:
  - Aggregates the total number of rides starting from each station.
  - Converts `start_station_id` to string format for compatibility with station data.
- **Main Query**:
  - Joins the aggregated ride counts from the subquery with the station details to fetch station names.
  - Orders the stations by the number of rides in descending order.

### Key Query
```sql
SELECT
  station_id,
  name,
  number_of_rides AS number_of_rides_starting_at_station
FROM (
  SELECT
    CAST(start_station_id AS STRING) AS start_station_id_str,
    COUNT(*) AS number_of_rides
  FROM
    `bigquery-public-data.new_york.citibike_trips`
  GROUP BY
    CAST(start_station_id AS STRING)
) AS station_num_trips
INNER JOIN
  `bigquery-public-data.new_york.citibike_stations`
ON
  station_id = start_station_id_str
ORDER BY
  number_of_rides DESC;
