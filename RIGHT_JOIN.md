![right_join](https://github.com/user-attachments/assets/53f7bb41-7824-453b-b3b5-ae8951a677fe)

# Employee and Department Analysis using SQL (RIGHT JOIN Example)

## Overview
This project highlights the use of a `RIGHT JOIN` in SQL within Google BigQuery to combine data from two datasets:
- `Employee_info`: Contains employee details.
- `Department_info`: Contains department details.

The `RIGHT JOIN` ensures all department records are displayed, even if no employees are associated with them.

## Query
The SQL query used:
```sql
SELECT 
    Employee_info.name AS Employee_Name,
    Employee_info.role AS Employee_role,
    Department_info.name AS Department_name
FROM 
    mohanaproject.Employee_Data.Employee_info AS Employee_info
RIGHT JOIN 
    mohanaproject.Employee_Data.Department_info AS Department_info
ON 
    Employee_info.department_id = Department_info.department_id;
