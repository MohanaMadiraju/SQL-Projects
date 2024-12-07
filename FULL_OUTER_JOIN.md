![full_outer_join](https://github.com/user-attachments/assets/69e2ae85-98e4-4dac-8078-92a5f77b3bbf)

# Employee and Department Analysis using SQL (FULL OUTER JOIN Example)

## Overview
This project demonstrates how to use a `FULL OUTER JOIN` in SQL with Google BigQuery. The `FULL OUTER JOIN` combines data from two datasets:
- `Employee_info`: Contains employee details.
- `Department_info`: Contains department details.

With a `FULL OUTER JOIN`, all records from both tables are included in the output, even if there is no match between them.

## Query
The SQL query used:
```sql
SELECT 
    Employee_info.name AS Employee_Name,
    Employee_info.role AS Employee_role,
    Department_info.name AS Department_name
FROM 
    mohanaproject.Employee_Data.Employee_info AS Employee_info
FULL OUTER JOIN 
    mohanaproject.Employee_Data.Department_info AS Department_info
ON 
    Employee_info.department_id = Department_info.department_id;
