# 🚀 Car Metrics Data Pipeline Project

An end-to-end data engineering solution using Azure services to process vehicle metrics data, following the medallion architecture pattern.

![Azure Architecture]([[https://via.placeholder.com/800x400?text=Azure+Architecture+Overview](https://raw.githubusercontent.com/Naman2206/CarMetrics/main/assets/images/1.jpg](https://github.com/user-attachments/assets/9748e7db-cfba-4bc3-9faf-aee82e6bbf60)))

## 📋 Project Overview

This project implements a comprehensive data pipeline for car metrics data using Microsoft Azure services. The solution follows the medallion architecture pattern (Bronze → Silver → Gold) and includes incremental data loading, transformation, and analytics capabilities.

## 🏗 Azure Resources Setup

### 1. Resource Group Creation

We've provisioned a resource group in Microsoft Azure containing:

- *Car Metrics Data Lake* - For raw and processed data storage
- *Databricks Access Connector* - To securely connect Databricks with other services
- *CarMetric_ADF* - Azure Data Factory instance for orchestration
- *CarMetricServer* - SQL Server for relational data storage
- *Azure_Databricks* - For data processing and transformation

![Resource Group](https://via.placeholder.com/700x300?text=Azure+Resource+Group)

<details>
<summary>📌 View Resource Group Configuration</summary>

Resource group "CarMetricsRG" containing all the necessary Azure resources for the data pipeline implementation.
</details>

## 🔄 Data Pipeline Components

### 2. Linked Services

Created multiple linked services to connect data sources and destinations:

- GitHub repository connection
- Azure Data Lake Storage connection
- SQL Server connection
- Databricks workspace connection

![Linked Services](https://via.placeholder.com/700x300?text=ADF+Linked+Services)

<details>
<summary>📌 View Linked Services Setup</summary>

Configuration details for connecting to GitHub repository, data lake storage, SQL server, and the Databricks workspace.
</details>

### 3. Data Pipelines

#### i. Copy Data Pipeline
Extracts data from GitHub source to SQL Server:

![Copy Pipeline](https://via.placeholder.com/700x300?text=GitHub+to+SQL+Copy+Pipeline)

<details>
<summary>📌 View Copy Pipeline Configuration</summary>

Pipeline configuration that copies car metrics data from the GitHub repository to the SQL Server database.
</details>

#### ii. Incremental Pipeline
Captures only new or changed records added to the source:

![Incremental Pipeline](https://via.placeholder.com/700x300?text=Incremental+Data+Pipeline)

<details>
<summary>📌 View Incremental Pipeline Logic</summary>

Pipeline configuration that identifies and processes only new or changed records since the last pipeline run.
</details>

## 🗄 Medallion Architecture

### 4. Storage Layers & Stored Procedures

Implemented the medallion architecture with three container layers:

![Medallion Architecture](https://via.placeholder.com/700x400?text=Bronze-Silver-Gold+Architecture)

#### Bronze Layer
- Raw data ingestion
- No transformations
- Historical preservation

#### Silver Layer
- Cleansed and validated data
- Applied transformations
- Standardized format

#### Gold Layer
- Dimensional model implementation
- Business logic applied
- Analytics-ready datasets

<details>
<summary>📌 View Storage Container Setup</summary>

Details about the stored procedures used to move and transform data between the Bronze, Silver, and Gold layers.
</details>

## 🔄 Integration & Analytics

### 5. Databricks Pipeline Integration

Created Databricks notebooks for advanced transformations and dimensional modeling:

![Databricks Integration](https://via.placeholder.com/700x300?text=Databricks+Integration)

<details>
<summary>📌 View Databricks Implementation</summary>

Overview of the Databricks notebooks used to create dimensional models from the silver layer data, including time dimension, vehicle dimension, and metrics fact tables.
</details>

### 6. Power BI Dashboard

Created interactive dashboards using the gold layer fact tables:

![Power BI Dashboard](https://via.placeholder.com/700x400?text=Car+Metrics+Power+BI+Dashboard)

## 🛠 How to Use This Repository

1. Clone this repository
2. Set up Azure resources using the provided ARM templates
3. Configure linked services with your credentials
4. Run the pipelines in the correct order:
   - Copy pipeline first
   - Incremental pipeline for ongoing updates
5. Monitor data flow through the medallion architecture
6. Connect Power BI to the gold layer for analytics

## 📊 Results and Insights

The implemented solution provides:
- Near real-time vehicle metrics monitoring
- Historical data analysis capabilities
- Performance trend identification
- Anomaly detection for preventive maintenance

![Results](https://via.placeholder.com/700x300?text=Key+Metrics+and+Results)

## 🧪 Future Improvements

- Add machine learning models for predictive maintenance
- Implement real-time streaming with Event Hubs
- Enhance security with Azure Key Vault integration
- Add automated testing for data quality

---

## 📬 Contact

Feel free to reach out for any questions or collaborations!
