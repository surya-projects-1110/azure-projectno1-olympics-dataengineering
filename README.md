# Tokyo Olympics Azure Data Engineering Project


!Azure Project Diagram


## Project Overview

This project demonstrates an end-to-end data engineering pipeline built on Microsoft Azure. The pipeline ingests, transforms, stores, and analyzes Tokyo Olympics data using a suite of Azure services. The objective is to showcase a modern data architecture that leverages scalable and cloud-native tools for efficient data processing and analytics.

## Architecture & Workflow

The following Azure services were used in the pipeline:

- **Azure Data Factory (ADF)**: Responsible for data ingestion from an external HTTPS API.
- **Azure Data Lake Storage (ADLS)**: Used as the centralized data lake to store raw and transformed datasets.
- **Azure Databricks (DBX)**: Used for data transformation and processing using PySpark.
- **Azure Synapse Analytics**: Used for querying and analyzing the transformed data using SQL-based analytics.

### Detailed Workflow

1. **Data Ingestion (ADF)**:
   - Data was ingested from an HTTPS API containing Tokyo Olympics datasets.
   - The ingested data was stored in ADLS under the `raw-data` container/folder in the ADLS.

2. **Data Transformation (Azure Databricks)**:
   - Azure Databricks was connected to ADLS using secure credentials.
   - Spark-based transformations were applied to clean, normalize, and enrich the raw data.
   - The processed data was then saved back to ADLS in the `transformed-data` folder in the ADLS.

3. **Data Analysis (Azure Synapse Analytics)**:
   - Azure Synapse was connected to the `transformed-data` in ADLS.
   - SQL queries and analytics were performed to derive insights from the cleaned data.

## Folder Structure

```
/raw-data             # Contains the original data ingested from the API
/transformed-data     # Contains the cleaned and transformed dataset
/notebooks            # Azure Databricks notebooks used for transformation
```

## Technologies Used

- Azure Data Factory
- Azure Data Lake Storage Gen2
- Azure Databricks
- Azure Synapse Analytics
- Python (in Databricks notebooks)
- SQL (in Synapse)
