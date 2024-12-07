![inner join](https://github.com/user-attachments/assets/2d464eb5-aa5d-4d13-aebc-2f05551687a9)

# Employee and Department Analysis using SQL in Google BigQuery

## Overview
This project demonstrates how to use SQL to analyze and combine data from two relational tables in Google BigQuery:
- `Employee_info`: Contains details about employees.
- `Department_info`: Contains department details.

The query performs an inner join to fetch employee names, roles, and their respective department names.

## Query
The SQL query used:
```sql
SELECT 
    Employee_info.name AS Employee_Name,
    Employee_info.role AS Employee_role,
    Department_info.name AS Department_name
FROM 
    mohanaproject.Employee_Data.Employee_info AS Employee_info
INNER JOIN 
    mohanaproject.Employee_Data.Department_info AS Department_info
ON 
    Employee_info.department_id = Department_info.department_id;
