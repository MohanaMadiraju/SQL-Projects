![order_by 1](https://github.com/user-attachments/assets/d5932a04-3768-42c7-95dc-3f5da935e802)
# Movie Data Analysis with Google BigQuery

This project demonstrates how to use Google BigQuery for querying and analyzing movie-related data stored in the dataset `Movie_Data.movie_info`. The example SQL query retrieves movie information sorted by their release dates.

## Prerequisites

- Access to Google Cloud Platform (GCP)
- A BigQuery sandbox project named `MohanaProject`
- A dataset named `Movie_Data` containing the `movie_info` table

## Query Details

The query fetches all columns from the `movie_info` table and sorts the results by the `Release_Date` column in ascending order.

### SQL Query:
```sql
SELECT *
FROM mohanaproject.Movie_Data.movie_info
ORDER BY Release_Date;
