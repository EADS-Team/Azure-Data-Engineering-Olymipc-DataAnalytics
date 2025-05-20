# Azure-Data-Engineering-Olymipc-DataAnalytics

## Project Overview

The goal of this project is to build a fully automated data pipeline on Azure, enabling the extraction, transformation, and visualization of data. The project involves ingesting data from GitHub, processing it using Azure Databricks, and storing it for analytics in Azure Storage. Finally, the transformed data is made available for reporting and insights generation.

## Business Requirements

The project is designed to process and analyze data efficiently while ensuring scalability and automation. The primary objectives include:

* **Data Ingestion** – Extracting raw data from GitHub and storing it in Azure Storage.
* **Data Transformation** – Cleaning and structuring the data using Azure Databricks.
* **Data Storage** – Storing raw and processed data in separate Azure Storage containers.
* **Automation** – Ensuring an end-to-end pipeline that updates the transformed dataset automatically.
  
![GitHub Workflow](Screenshots/Github%20Workflow%20Image.png)

## Solution Overview

The project workflow consists of the following major steps:

## 1. Data Ingestion

* Downloaded a dataset from Kaggle and stored it in a GitHub repository under the data folder.
* Created an Azure Storage Account and set up two containers:
    * **Raw Data Container** – To store the ingested raw files.
    * **Transformed Data Container** – To store the processed data.
* Created an Azure Data Factory (ADF) pipeline with five Copy Data activities:
    * **Source**: GitHub
    * **Sink**: Raw Data container in Azure Storage

## 2. Data Transformation

* Created an **Azure Databricks workspace** for data processing.
* Mounted the **Raw Data** and **Transformed Data** containers to Databricks.
* Performed transformations on the five files, including:
    * Data cleaning
    * Standardizing formats
    * Removing null values
    * Aggregating relevant information
* Wrote the transformed data to the **Transformed Data Container** in Azure Storage.

## 3. Pipeline Integration and Execution

* Connected the Databricks Notebook to the ADF pipeline.
* Triggered the pipeline in ADF, ensuring that the transformed files were successfully moved to the transformed dataset 
  container in Azure Storage.

## Technology Stack

* **Azure Data Factory (ADF)** – To orchestrate data ingestion and movement.
* **Azure Storage Account** – To store raw and processed data.
* **Azure Databricks** – To perform data transformations.
* **GitHub** – As the source for raw data files.

## Setup Instructions

## Prerequisites

* Active **Azure account** with sufficient credits.
* GitHub repository containing the dataset.

## Step 1: Set Up Azure Environment

* Create a **Resource Group** to manage all resources.
* Deploy an **Azure Storage Account** and create two containers: **rawdata** and **transformeddataset**.
* Create an **Azure Data Factory** instance.
* Set up an **Azure Databricks** workspace.

## Step 2: Data Ingestion

* Create an **ADF pipeline** with five **Copy Data** activities.
* Set **GitHub as the source** and the **Raw Data container as the sink**.

## Step 3: Data Transformation

* Mount both containers in **Databricks**.
* Perform necessary transformations and write the output to the **transformeddataset** container.

## Step 4: Pipeline Execution

* Link the **Databricks Notebook** to the **ADF pipeline**.
* Trigger the pipeline and validate that transformed data is stored correctly.

![GitHub Flow](Screenshots/Github%20-%20Flow.png)

## Conclusion

This project demonstrates a streamlined **Azure Data Engineering** pipeline, integrating **Azure Data Factory**, **Azure Databricks**, and **Azure Storage or Azure Datalake gen2**. By automating data ingestion and transformation, the solution ensures efficient data processing, allowing businesses to derive meaningful insights seamlessly.
