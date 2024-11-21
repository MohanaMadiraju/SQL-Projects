![Movie](https://github.com/user-attachments/assets/ffc1edc7-8aac-44ef-b0b6-c71aaba77f1b)

# Movie Dataset Exploration Using SQL

## Objective
This project demonstrates the use of SQL to query a movie dataset. The objective was to filter and retrieve all movies categorized under the "Comedy" genre.

## Tools Used
- Google BigQuery
- SQL

## Dataset
The dataset was sourced from the [BigQuery Public Dataset](https://cloud.google.com/bigquery/public-data).

## Steps Taken
1. Queried the movie dataset using SQL in Google BigQuery.
2. Filtered movies where the "Genre" column contained the value "Comedy."
3. Retrieved relevant columns, such as movie titles, release dates, and directors.

## SQL Query
```sql
SELECT *
FROM mohanaproject.movie_data.movies
WHERE Genre = 'Comedy';
