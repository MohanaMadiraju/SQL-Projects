![left_join](https://github.com/user-attachments/assets/bf57d15c-d86b-4333-8cd9-b5b2f17d2a39)

# Employee and Department Analysis using SQL (LEFT JOIN Example)

## Overview
This project highlights how to use a `LEFT JOIN` in SQL within Google BigQuery to combine data from two datasets:
- `Employee_info`: Contains employee details.
- `Department_info`: Contains department details.

The `LEFT JOIN` ensures all employee records are displayed, even if they lack a matching department.

## Query
The SQL query used:
```sql
SELECT 
    Employee_info.name AS Employee_Name,
    Employee_info.role AS Employee_role,
    Department_info.name AS Department_name
FROM 
    mohanaproject.Employee_Data.Employee_info AS Employee_info
LEFT JOIN 
    mohanaproject.Employee_Data.Department_info AS Department_info
ON 
    Employee_info.department_id = Department_info.department_id;
