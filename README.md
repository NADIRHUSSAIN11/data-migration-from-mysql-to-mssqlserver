# MySQL to SQL Server Migration with Talend

## Overview
This project demonstrates the complete migration of a MySQL database to Microsoft SQL Server using **Talend Cloud Data Management Platform**. The job efficiently migrates tables, data, and ensures transactional integrity with commit/rollback mechanisms in place.

## Features
- **Source**: MySQL

![Screenshot (305)](https://github.com/user-attachments/assets/9ffb97a1-4e0b-4c9a-9b14-8a1769379822)


- **Target**: MS SQL Server

![Screenshot (304)](https://github.com/user-attachments/assets/86300872-2d06-49db-9503-3ad96ecf5984)


- **ETL Tool**: Talend Cloud Data Management Platform

![Screenshot (307)](https://github.com/user-attachments/assets/8aa20bbc-6688-4a75-bb57-cc0057e2862b)


- **Job Components**:
  - `tDBConnection` (MySQL, SQL Server)
  - `tDBTableList` to iterate through all tables in MySQL
  - `tDBInput` to fetch data from MySQL
  - `tDBOutput` to write data into SQL Server
  - `tDBCommit` for successful transactions
  - `tDBRollback` for error handling and transaction rollback

## Process Flow
1. **Pre-job Setup**:
   - Establishes connections to both MySQL and SQL Server.
   
2. **Data Migration**:
   - Iterates over all MySQL tables using `tDBTableList` and retrieves table data using `tDBInput`.
   - Writes data to the corresponding SQL Server tables using `tDBOutput`.

3. **Error Handling**:
   - If any subjob fails, `tDBRollback` will revert the transaction.

4. **Commit**:
   - On successful completion of the job, `tDBCommit` ensures that the data is committed in SQL Server.

5. **Post-job Cleanup**:
   - Closes all database connections.

## Pre-requisites
- MySQL database
- SQL Server database
- Talend Cloud Data Management Platform 
