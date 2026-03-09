# Fabric Learning Management System

This repository contains resources for a Fabric Learning Management System (LMS) data pipeline. It includes notebooks for exploring and configuring the system, as well as pipeline definitions in JSON format.

## Directory Structure

- `notebooks/` – Jupyter notebooks demonstrating configuration and incremental ETL steps.
- `pipelines/` – JSON definitions of pipelines used to orchestrate data flow.

## Notebooks

The notebooks cover different stages of the LMS ETL process:

| Notebook | Description |
|----------|-------------|
| `ms_lms_config.ipynb` | Configuration and setup for the LMS environment. |
| `ms_lms_nb_raw_to_landing.ipynb` | ETL from raw ingestion to landing zone. |
| `ms_lms_nb_landing_to_100_bronze.ipynb` | Process landing data into the bronze zone (first 100 rows or initial batch). |
| `ms_lms_nb_100_bronze_to_200_silver.ipynb` | Transform bronze data into silver zone (rows 101–200). |
| `ms_lms_nb_200_silver_to_300_gold.ipynb` | Further processing from silver to gold zone (rows 201–300). |

## Pipelines

Pipeline JSON files correspond to the notebooks and orchestrate the workflows in Fabric:

| Pipeline | Description |
|----------|-------------|
| `ms_lms_pl_raw_to_landing.json` | Automates the raw-to-landing ETL process. |
| `ms_lms_pl_landing_to_100_bronze.json` | Runs landing-to-bronze transformation for initial data. |
| `ms_lms_pl_100_bronze_to_200_silver.json` | Bronze-to-silver processing pipeline. |
| `ms_lms_pl_200_silver_to_300_gold.json` | Silver-to-gold pipeline for later batches. |
| `ms_lms_pl_master_etl.json` | Master pipeline that likely chains the above steps into a full ETL flow. |

## Lakehouses

Data landing and transformation results are stored in Azure Fabric lakehouses named:

- `ms_lms_lh_100_bronze`
- `ms_lms_lh_200_silver`
- `ms_lms_lh_300_gold`

## Usage

Use the notebooks interactively to understand and modify the ETL logic, then export or deploy the pipelines via the Fabric UI or CLI using the JSON definitions.

## Contributing

Feel free to add more notebooks, pipelines, or documentation as the project evolves.

---

*Generated on 9 March 2026.*