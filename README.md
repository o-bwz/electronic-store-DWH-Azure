# Electronic Store Data Warehouse (Azure Synapse Analytics)

## 📌 Project Overview
This repository contains the architecture and codebase for an enterprise-level **Data Warehouse** designed for an Electronic Store. Built natively on **Azure Synapse Analytics**, this project implements a modern data warehousing approach utilizing the **Medallion Architecture** (Silver and Gold layers) to process, transform, and serve retail data for advanced business intelligence and reporting.

## 🏛️ Data Architecture (Medallion Pattern)
The data model is designed to ensure data quality, structure, and query performance.

### 🥈 Silver Layer (Cleansed & Conformed Data)
This layer acts as the enterprise single source of truth, containing cleansed, filtered, and integrated data ready for dimensional modeling.
- **`silver.Silvertable`**: A consolidated transactional table containing flat, cleaned data encompassing Orders, Customers, Products, and Geography details.

### 🥇 Gold Layer (Dimensional Model - Star Schema)
The presentation layer is structured as a **Star Schema**, optimized for read-heavy analytical workloads, ML models, and dashboarding tools (e.g., Power BI).

**Fact Table:**
- `gold.FactOrders`: The central fact table storing quantitative business metrics (Quantity, Unit Price, Total Amount) and foreign keys linking to the dimensions.

**Dimension Tables:**
- `gold.Dimcustomer`: Customer demographics and contact details (Customer Name, Email).
- `gold.Dimproduct`: Product catalog information (Product Name, Category).
- `gold.DimGeography`: Spatial and geographical data (Region Name, Country).
- `gold.DimOrders`: Specific transactional and order-level attributes.

## 🛠️ Technology Stack
- **Azure Synapse Analytics**: Unified data analytics platform.
- **Azure Data Lake Storage Gen2 (ADLS Gen2)**: Underlying scalable storage for the data lakehouse.
- **SQL Serverless / Dedicated SQL Pools**: For querying, transforming, and serving data across layers.
- **T-SQL**: For table definitions, views, and data manipulation.

## 🚀 Setup & Deployment
1. Connect your Azure Synapse Workspace to this GitHub repository.
2. Ensure the System-Assigned Managed Identity has `Storage Blob Data Contributor` access to the underlying ADLS Gen2.
3. Execute the initial SQL scripts to create the schemas (`CREATE SCHEMA silver;`, `CREATE SCHEMA gold;`).
4. Run the Synapse pipelines to ingest data into the Silver layer and subsequently transform it into the Gold dimensional model.

## 👨‍💻 Author
**Omar Abobakr Omar Bawazir**
- *Information Technology & Data Engineering*
- Google-Certified Data Analyst
