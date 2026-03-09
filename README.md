# Learning Management System

  [![Fabric](https://img.shields.io/badge/Fabric-brightgreen)](https://learn.microsoft.com/en-us/fabric/)  [![Azure](https://img.shields.io/badge/Azure-lightblue)](https://azure.microsoft.com/)  [![PySpark](https://img.shields.io/badge/PySpark-orange)](https://spark.apache.org/docs/latest/api/python/)

This repository contains resources for a Learning Management System (LMS) data pipeline. It includes notebooks for exploring and configuring the system, as well as pipeline definitions in JSON format.

## Directory Structure

- `notebooks/` – Jupyter notebooks demonstrating configuration and incremental ETL steps.
- `pipelines/` – JSON definitions of pipelines used to orchestrate data flow.

## Data flow diagram

<img width="700" height="700" alt="image" src="https://github.com/maciejsss/fabric-learning-management-system/blob/main/img/data_flow_diagram.png?raw=true" />


## Notebooks

The notebooks cover different stages of the LMS ETL process:

| Notebook | Description |
|----------|-------------|
| `ms_lms_config.ipynb` | Configuration and setup for the LMS environment. |
| `ms_lms_nb_raw_to_landing.ipynb` | ETL from raw ingestion to landing zone. |
| `ms_lms_nb_landing_to_100_bronze.ipynb` | Process landing data into the bronze zone. |
| `ms_lms_nb_100_bronze_to_200_silver.ipynb` | Transform bronze data into silver zone. |
| `ms_lms_nb_200_silver_to_300_gold.ipynb` | Further processing from silver to gold zone. |

## Pipelines

Pipeline JSON files correspond to the notebooks and orchestrate the workflows in Fabric:

| Pipeline | Description |
|----------|-------------|
| `ms_lms_pl_raw_to_landing.json` | Automates the raw-to-landing ETL process. |
| `ms_lms_pl_landing_to_100_bronze.json` | Runs landing-to-bronze transformation for initial data. |
| `ms_lms_pl_100_bronze_to_200_silver.json` | Bronze-to-silver processing pipeline. |
| `ms_lms_pl_200_silver_to_300_gold.json` | Silver-to-gold pipeline for later batches. |
| `ms_lms_pl_master_etl.json` | Master pipeline that likely chains the above steps into a full ETL flow. |

## Lineage

<img width="1000" height="1000" alt="image" src="https://github.com/maciejsss/fabric-learning-management-system/blob/main/img/lineage_view.png?raw=true" />

## Lakehouses

Data landing and transformation results are stored in Azure Fabric lakehouses named:

- `ms_lms_lh_100_bronze`
- `ms_lms_lh_200_silver`
- `ms_lms_lh_300_gold`


