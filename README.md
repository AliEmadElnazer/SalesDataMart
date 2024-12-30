# Sales Data Mart Project

## Overview
This project involves creating a Sales Data Mart by extracting and transforming data from Microsoft's AdventureWorks2014 database using SQL Server Integration Services (SSIS). The goal is to load the transformed data into a destination database optimized for analytics and reporting. The project demonstrates skills in data integration, ETL processes, and data warehouse design.

## Key Components

### Source Database
- **AdventureWorks2014**: This is the source database containing transactional sales data.

### Destination Database
- **Sales Data Mart**: A structured database designed to support analytical queries for sales reporting.

### SSIS Packages
1. **01.Dim Product ETL.dtsx**
   - Extracts product data from the source database.
   - Transforms and loads data into the Product dimension table in the Sales Data Mart.

2. **02.Dim Customer ETL.dtsx**
   - Extracts customer data from the source database.
   - Transforms and loads data into the Customer dimension table in the Sales Data Mart.

3. **03.Dim Date ETL.dtsx**
   - Generates and loads date dimension data into the Sales Data Mart.

4. **04.Dim Territory ETL.dtsx**
   - Extracts territory data from the source database.
   - Transforms and loads data into the Territory dimension table in the Sales Data Mart.

5. **05.Fact Sales - Full Load.dtsx**
   - Extracts sales data from the Sales Order Header and Sales Order Details tables in the source database.
   - Merges the data and performs lookups on the Product, Customer, Date, and Territory dimension tables.
   - Performs transformations, including calculations and handling of null values, before loading data into the Fact Sales table in the Sales Data Mart.

6. **05.Fact Sales - Incremental Load.dtsx**
   - Handles the incremental loading of sales data to ensure the Fact Sales table is up to date.

### Data Flow Tasks
- **Sales Order Header** and **Sales Order Details** are merged using a Merge Join.
- Lookups are performed on the following dimensions:
  - Product
  - Customer
  - Date
  - Territory
- Transformations include:
  - Calculations (DRV - Calculation)
  - Null value replacements (DRV - Replace Null)
- The final data is loaded into the Fact Sales table.

## Connection Managers
- **Source Database**: Connects to the AdventureWorks2014 database.
- **Destination Database**: Connects to the Sales Data Mart.

## Tools Used
- **SQL Server Integration Services (SSIS)**: For ETL workflows.
- **Microsoft SQL Server**: As the database engine.
- **Visual Studio**: For developing SSIS packages.

## Steps to Execute the Project
1. Open the solution file in Visual Studio.
2. Configure connection strings for the source and destination databases in the Connection Managers.
3. Execute the SSIS packages in the following order:
   1. 01.Dim Product ETL.dtsx
   2. 02.Dim Customer ETL.dtsx
   3. 03.Dim Date ETL.dtsx
   4. 04.Dim Territory ETL.dtsx
   5. 05.Fact Sales - Full Load.dtsx
4. Verify that the data is correctly loaded into the destination database.
5. For incremental updates, use the 05.Fact Sales - Incremental Load.dtsx package.

## Project Highlights
- Efficiently designed ETL processes to handle both full and incremental data loads.
- Use of dimension tables to create a normalized schema for the Data Mart.
- Incorporation of data quality checks and transformations to ensure consistency.

## Future Enhancements
- Add more dimensions and facts to expand the Data Mart's analytical capabilities.
- Implement advanced incremental loading mechanisms to improve performance.
- Automate the execution of SSIS packages using SQL Server Agent.


