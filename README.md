# cybersecurity-etl-pipeline
Cybersecurity ETL Pipeline for Risk Prioritization

📌 Project Overview

This project implements an end-to-end ETL (Extract, Transform, Load) pipeline to integrate and analyze cybersecurity vulnerability data from multiple open sources. The goal is to support data-driven risk prioritization in small and medium-sized enterprises (SMEs).

🎯 Objectives

- Integrate vulnerability data from NVD (CVE/CVSS) and ExploitDB
- Ensure data quality and consistency
- Generate a structured dataset for risk prioritization
- Support decision-making with data-driven insights

🧩 Data Sources

- NVD (National Vulnerability Database) – CVE and CVSS data
- Exploit Database (ExploitDB) – Public exploit availability

⚙️ Tech Stack

- Python
- Pandas
- JSON / CSV processing
- SQLite (data storage)

🔄 ETL Pipeline

1. Extract

- Automated ingestion of multiple NVD JSON files (v2.0 format)
- Extraction of CVE, description, publication date, and CVSS metrics
- Parsing of ExploitDB CSV and extraction of CVE references

2. Transform

- Data cleaning and normalization
- Integration of multiple data sources
- Feature engineering:
    - Exploit availability indicator
    - Vulnerability age
    - Severity classification
    - OWASP-like categorization (keyword-based)
- Creation of a custom risk prioritization score

3. Load

- Export of final dataset to CSV
- Storage in SQLite database
- Execution of analytical SQL queries

📊 Key Features

- Multi-source data integration
- Automated data processing pipeline
- Custom risk scoring model
- Queryable database for analysis

📁 Project Structure

<pre>
cybersecurity-etl-pipeline/
│
├── data/
│ ├── processed
│ │ ├── cve_data.csv
│ │ └── exploit_data.csv
│ │
│ ├── raw/
│ │ ├── files_exploits.csv
│ │ ├── nvdve-2.0-2023.json.gz
│ │ ├── nvdve-2.0-2024.json.gz
│ │ ├── nvdve-2.0-2025.json.gz
│ │ └── nvdve-2.0-2026.json.gz
│
├── notebooks/
│ ├── 01_extraccion.ipynb
│ ├── 02_transformacion.ipynb
│ └── 03_carga.ipynb
│
├── results/
│ ├── dataset_final.csv
│ └── vulnerabilidades.db
│
├── .gitignore
├── README.md
└── requirements.txt
</pre>

📈 Business Questions Addressed

- What percentage of vulnerabilities classified as critical (based on CVSS) have a publicly available exploit?
- Are there medium or low severity vulnerabilities that show evidence of active exploitation according to sources such as ExploitDB?
- Which vulnerability categories (e.g., OWASP-related) concentrate the highest frequency or the highest availability of exploits?
- What criteria can be used to build an alternative ranking that optimizes resource allocation under constrained environments?
- What gaps exist between traditional CVSS-based prioritization and a data-driven approach that integrates multiple data sources?

🚀 Results

The pipeline produces a consolidated dataset and a prioritization model that enhances traditional CVSS-based approaches by incorporating exploit availability and contextual factors.

Author:
Cjay Zambrano
Data Analyst | Data Scientist | Cybersecurity Enthusiast
