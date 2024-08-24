# Xtage-Assignment

# Data Engineering Pipeline Project

## Overview
This project involves building a robust and scalable data engineering pipeline that integrates and processes data from multiple sources. The final deliverable is a standardized dataset that can be deployed in a cloud environment. This README file details the steps followed, tools used, and assumptions made during the implementation.

## Steps Followed

### Step 1: Data Ingestion
1. **Fetching Data from Flat Files (CSV)**
   - Used Python's `pandas` library to read and parse CSV files.
   - File: `sales_data.csv`

2. **Fetching Data from External API (Exchange Rates)**
   - Used Python's `requests` library to fetch data from the external API.
   - Endpoint: `/api/exchange_rates`
   - Implemented token-based authentication and error handling.

3. **Fetching Data from Internal API (Customer Demographics)**
   - Used Python's `requests` library to fetch data from the internal API.
   - Endpoint: `/api/customer_data`
   - Implemented token-based authentication and error handling.

4. **Fetching Data from Database**
   - Used SQLAlchemy to query data from PostgreSQL tables.
   - Tables: `products` and `transactions`

### Step 2: Data Standardization
1. **Designing a Data Model**
   - Standardized data from all sources into a consistent format.
   - Merged data from different sources based on common keys.

2. **Implementing the Logic**
   - Transformed and merged data into the standardized format.
   - Saved the standardized data for further processing.

### Step 3: Data Preprocessing Pipeline
1. **Handling Missing Data**
   - Used forward filling to handle missing values.

2. **Removing Duplicate Records**
   - Removed duplicate records to ensure data integrity.

3. **Handling Inconsistent Data Entries**
   - Filtered out abnormal values (e.g., prices less than 0).

4. **Feature Engineering**
   - Converted categorical variables to numerical values for analysis.

### Step 4: Cloud Architecture
1. **Designing the Architecture**
   - Used Google Cloud Platform (GCP) services for scalability, resilience, and cost-efficiency.
   - Components:
     - **Data Ingestion**: Cloud Functions for API data, Cloud Dataflow for CSV files.
     - **Data Storage**: Google Cloud Storage for raw data, Cloud SQL for relational data.
     - **Data Processing**: Cloud Dataflow for ETL jobs.
     - **Data Serving**: Cloud Endpoints to expose APIs, Cloud Functions for serverless functions.

2. **Deploying the Pipeline**
   - Deployed the pipeline in the cloud, ensuring it is scalable and resilient.

### Step 5: Documentation and Presentation
1. **Detailed Documentation**
   - Explained the data model, pipeline architecture, and steps taken during implementation.
   - Included diagrams and visual representations of the cloud architecture and data flow.

2. **Challenges and Solutions**
   - Faced issues with exposing the URL from Postman during Step 1.
   - Managed to resolve the issue by ensuring correct URL formatting and proper configuration in Postman.

## Tools Used
- **Python**: For scripting and data processing.
- **pandas**: For data manipulation and analysis.
- **requests**: For making HTTP requests to APIs.
- **SQLAlchemy**: For querying PostgreSQL databases.
- **Google Cloud Platform (GCP)**: For cloud deployment.
  - **Cloud Functions**: For serverless data ingestion.
  - **Cloud Dataflow**: For ETL processing.
  - **Google Cloud Storage**: For storing raw data.
  - **Cloud SQL**: For relational data storage.
  - **Cloud Endpoints**: For exposing APIs.

## Assumptions Made
- The provided CSV files and API endpoints are accessible and contain the expected data.
- Proper authentication tokens are available for accessing the APIs.
- The PostgreSQL database is set up and accessible with the provided credentials.
- Google Cloud Platform (GCP) services are configured and accessible for deployment.

## Conclusion
This project demonstrates the ability to design, implement, and deploy a data processing pipeline using industry best practices. The pipeline is robust, scalable, and suitable for further analysis or downstream applications.
