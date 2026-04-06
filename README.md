# 🏅 Tokyo Olympics Azure Data Engineering Project
## Project Overview
This project focuses on building an Azure-based data pipeline to process Tokyo Olympics data efficiently. The pipeline extracts multiple CSV files from GitHub, loads them into Azure Data Lake Storage Gen2 (ADLS Gen2) using ADF's ForEach and Copy activities, performs data transformations in Databricks, and later creates a Lake Database and tables in Azure Synapse Analytics for analysis.

## Technologies Used
Azure Data Factory (ADF) → Orchestrates the ETL pipeline Azure Data Lake Storage Gen2 (ADLS Gen2) → Stores raw & transformed data Azure Databricks → Performs data transformations Azure Synapse Analytics → Creates Lake Database & tables for querying GitHub → Source for raw CSV files Azure Key Vault (Alternative: SAS Tokens) → Secure connection management

## Project Workflow
1️⃣ Data Ingestion (Using ADF) Used Azure Data Factory (ADF) to load multiple CSV files from GitHub into ADLS Gen2. Implemented a parameterized pipeline with: ForEach activity → Iterates over multiple files. Copy activity → Reads each file and loads it into ADLS Gen2.
2️⃣ Data Transformation (Databricks) Mounted ADLS Gen2 to Azure Databricks. Cleaned and transformed data using PySpark. Stored transformed data back into ADLS Gen2 in Parquet format.
3️⃣ Lake Database & Table Creation (Synapse Analytics) Created a Lake Database in Azure Synapse Analytics. Defined external tables using data stored in ADLS Gen2. Performed SQL-based analytics directly on Synapse.

## Challenges Faced & Solutions
Challenge Solution Implemented Difficult to connect to GitHub using REST Connector in ADF Switched to HTTP Connector to extract data from GitHub No access to create Azure Key Vault for secure credentials Used SAS tokens to authenticate ADLS Gen2 in Databricks Databricks mounting issues with ADLS Gen2 Configured temporary SAS-based access to read/write data Reading multiple files in ADF Copy activity Used ForEach activity to iterate through file list dynamically 

## Results & Insights 
Successfully processed Tokyo Olympics data using an end-to-end Azure pipeline. Efficient data ingestion using ForEach and Copy activity in ADF. Transformed data is stored in ADLS Gen2, allowing flexibility in further processing. Created a Lake Database & external tables in Azure Synapse Analytics for efficient querying. Enabled scalable SQL-based analysis on Synapse.
