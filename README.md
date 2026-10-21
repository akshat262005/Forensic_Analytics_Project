# Forensic Analytics: Sequential and Spatial Data Mining for Anti-Money Laundering

Developed as part of the **Forensic Analytics** course at **Vellore Institute of Technology (VIT), Chennai**.

- **Subject Code:** CSE4074
- **Semester:** Fall 2026–27
- **Professor:** Dr. S. Johanan Joysingh

## Project Overview

This project explores forensic analytics techniques for examining synthetic financial transaction data. It combines data generation, fraud-pattern analysis, sequential and spatial data mining, and transaction-level forensic analysis to investigate potentially suspicious financial activity.

The project includes data profiling, Benford's Law analysis, transaction anomaly analysis, temporal correlation analysis, sequential pattern mining, spatial analysis, integrated fraud detection, and forensic risk assessment.

The objective is to demonstrate how multiple analytical techniques can be combined to identify unusual transaction behaviour and generate risk indicators for further investigation.

**Important:** This is an academic project using synthetic data. An anomaly, fraud label, or risk score is not proof of actual fraud or criminal activity.

## Problem Statement

Potentially suspicious financial activity can be difficult to identify by examining individual transactions in isolation. Repeated transaction sequences, unusual geographical movements, temporal relationships, and deviations from expected transaction behaviour may provide additional context for forensic investigation.

This project explores how sequential mining, spatial data mining, and statistical forensic analysis can be combined to examine synthetic financial transactions and identify patterns that may warrant further investigation.

## Objectives

- Generate synthetic cities, customers, ATMs, merchants, and financial transactions.
- Introduce controlled, synthetic fraud-labelled transactions for experimental evaluation.
- Profile the generated dataset and examine its structure and quality.
- Apply sequential pattern mining techniques to identify recurring transaction patterns.
- Investigate geographical patterns, clusters, and potential spatial anomalies.
- Combine sequential and spatial indicators for integrated transaction risk analysis.
- Apply Benford's Law and statistical techniques to examine transaction data.
- Analyse transaction anomalies and temporal correlations.
- Integrate forensic risk indicators and evaluate the resulting outputs.
- Document the limitations of the methods and the results obtained from synthetic data.

## Project Workflow

The project contains 14 Jupyter notebooks organised into three stages. The order below reflects the intended data dependencies identified during notebook inspection. File paths and execution requirements should still be checked when running the notebooks.

### Stage 1: Synthetic Data Generation

1. **`01_generate_cities.ipynb`** — Generates city data used by downstream notebooks.
2. **`02_generate_customers.ipynb`** — Generates synthetic customer records.
3. **`03_generate_atms.ipynb`** — Generates ATM data.
4. **`04A_generate_merchants.ipynb`** — Generates merchant data.
5. **`04_generate_transactions.ipynb`** — Generates transaction records using the required entity datasets.

### Stage 2: Fraud Injection and Sequential-Spatial Analysis

6. **`05_fraud_injection.ipynb`** — Creates transaction datasets containing controlled synthetic fraud-labelled records.
7. **`06_sequential_mining.ipynb`** — Applies sequential pattern mining and compares the implemented mining approaches, including PrefixSpan and GSP.
8. **`07_spatial_data_mining.ipynb`** — Examines geographical transaction patterns, city hotspots, and spatial clustering.
9. **`08_sequential_spatial_fraud_detection.ipynb`** — Combines sequential and spatial indicators for integrated transaction risk analysis and generates `integrated_transaction_risk_results.csv` for downstream analysis.

### Stage 3: Forensic Analysis

10. **`FA_01_Data_Profiling.ipynb`** — Examines dataset structure, distributions, and data characteristics.
11. **`FA_02_Benford_Analysis.ipynb`** — Applies Benford's Law analysis to relevant numerical transaction fields.
12. **`FA_03_Transaction_Anomaly_Analysis.ipynb`** — Analyses unusual transaction behaviour and potential anomalies.
13. **`FA_04_Temporal_Correlation_Analysis.ipynb`** — Investigates time-based relationships and transaction correlations.
14. **`FA_05_Forensic_Risk_Integration.ipynb`** — Integrates forensic indicators to support an overall risk assessment.

## Repository Structure

```text
Forensic_Analytics_Project/
├── README.md
├── PROJECT_OVERVIEW.md
├── .gitignore
└── notebooks/
    ├── 01_generate_cities.ipynb
    ├── 02_generate_customers.ipynb
    ├── 03_generate_atms.ipynb
    ├── 04A_generate_merchants.ipynb
    ├── 04_generate_transactions.ipynb
    ├── 05_fraud_injection.ipynb
    ├── 06_sequential_mining.ipynb
    ├── 07_spatial_data_mining.ipynb
    ├── 08_sequential_spatial_fraud_detection.ipynb
    ├── FA_01_Data_Profiling.ipynb
    ├── FA_02_Benford_Analysis.ipynb
    ├── FA_03_Transaction_Anomaly_Analysis.ipynb
    ├── FA_04_Temporal_Correlation_Analysis.ipynb
    └── FA_05_Forensic_Risk_Integration.ipynb
```

## Dataset

The current project notes report the following synthetic dataset details:

- **Transactions:** 149,994
- **Controlled synthetic fraud-labelled transactions:** 1,450
- **Customers:** 500
- **Merchants:** 100
- **ATMs:** 50
- **Cities:** 20

These figures are reported project values and should be verified against the final data-generation code and generated datasets before the final review. The number of fraud-labelled records should not be assumed to equal the number of transactions ultimately flagged by a detection method.

The dataset is intended for academic experimentation and methodological evaluation. Do not commit restricted, confidential, or private data. If generated datasets are too large or cannot be shared, provide an appropriate permitted sample or instructions for reproducing them.

## Technologies and Tools

- Python
- Google Colab and Jupyter Notebook
- Pandas and NumPy, where used by the notebooks
- Data analysis and visualisation libraries used in the notebooks
- Statistical and forensic analysis techniques
- Sequential pattern mining
- Spatial data analysis and clustering

The exact package requirements should be confirmed from the notebook imports and installation cells. No separate dependency file is assumed to be complete unless one is added and verified.

## Reported Results

The current project notes report the following transaction-level comparison:

| Method | Alerts | Precision | Recall | F1-score |
|---|---:|---:|---:|---:|
| Sequential-only | 38,871 | 2.63% | 70.48% | 5.07% |
| Spatial-only | 3,447 | 2.79% | 6.62% | 3.92% |
| Integrated | 5,083 | 10.96% | 38.41% | 17.05% |
| Integrated v2 | 1,630 | 2.45% | 2.76% | 2.60% |

The project notes also report:

- **PrefixSpan patterns:** 75
- **GSP patterns:** 62

**Verification status:** These are reported figures from the current project notes, not independently verified final results. Re-run the relevant notebooks and confirm the evaluation logic, outputs, and metric calculations before presenting these values as final findings.

### Preliminary Interpretation

In the reported comparison, the integrated configuration has higher precision and F1-score than the listed sequential-only and spatial-only configurations, while sequential-only has higher recall. The reported integrated v2 configuration has lower precision, recall, and F1-score than the other listed configurations.

These comparisons describe the reported synthetic evaluation only. The number of alerts is not, by itself, a measure of detection quality. Precision, recall, F1-score, class imbalance, and the evaluation procedure should all be considered when interpreting performance.

## Setup and Execution

The notebooks are designed to be run in Google Colab or a compatible Jupyter Notebook environment. Some notebooks use Google Drive paths, so the required folders and input files must be available before execution.

### 1. Obtain the Repository

Clone or download the repository from GitHub, or obtain the notebook files locally.

### 2. Open the Notebooks

Open Google Colab and use **File → Upload notebook** to upload a notebook, or open the repository through an appropriate GitHub/Colab workflow.

### 3. Generate the Synthetic Data

Run the data-generation notebooks in this order:

1. `01_generate_cities.ipynb`
2. `02_generate_customers.ipynb`
3. `03_generate_atms.ipynb`
4. `04A_generate_merchants.ipynb`
5. `04_generate_transactions.ipynb`

Check each notebook's input paths and output locations. The downstream notebooks require the relevant generated datasets to be present.

### 4. Run Fraud Injection and Mining

Continue with:

6. `05_fraud_injection.ipynb`
7. `06_sequential_mining.ipynb`
8. `07_spatial_data_mining.ipynb`
9. `08_sequential_spatial_fraud_detection.ipynb`

The integrated detection notebook produces `integrated_transaction_risk_results.csv`, which is consumed by the forensic-analysis notebooks. Ensure this file is generated in the location expected by the downstream notebooks.

### 5. Run the Forensic Analysis

After the required datasets and integrated results are available, run:

10. `FA_01_Data_Profiling.ipynb`
11. `FA_02_Benford_Analysis.ipynb`
12. `FA_03_Transaction_Anomaly_Analysis.ipynb`
13. `FA_04_Temporal_Correlation_Analysis.ipynb`
14. `FA_05_Forensic_Risk_Integration.ipynb`

### 6. Configure Paths and Dependencies

Before running the notebooks:

- Check and update Google Drive paths where necessary.
- Mount Google Drive if the notebook requires it.
- Confirm that all required input CSV files exist at the expected paths.
- Install any missing Python packages specified by the notebooks.
- Run cells in sequence and resolve missing-file or dependency errors before continuing.

The notebooks have not necessarily been validated as one uninterrupted end-to-end execution. The recommended order is based on their intended dependencies; successful execution should be confirmed in the target environment.

### 7. Review and Verify Outputs

Review the generated tables, charts, mining results, anomaly indicators, and risk outputs. Recalculate or verify reported evaluation metrics against the final generated data before using them in a presentation or submission.

## Team Members and Contributions

| Team Member | Student ID |
|---|---|
| MS Tamanna | 23MIA1003 |
| Akshat Kumar | 23MIA1110 |
| Aman Brahma | 23MIA1156 |

The project is a collaborative academic submission for the Forensic Analytics course.

## Limitations and Responsible Use

- The project uses synthetic data unless explicitly stated otherwise in the relevant notebook.
- Synthetic fraud labels and patterns may not represent the complexity of real financial crime.
- An anomaly or risk indicator does not automatically establish fraud.
- Results depend on the generated data, selected methods, thresholds, and evaluation procedure.
- Performance on synthetic data does not establish validated real-world banking performance.
- Reported metrics should be confirmed against the final notebook outputs before being treated as final results.
- The project is intended for academic analysis and demonstration, not as a production anti-money-laundering system.

## Research Paper Status

The related research paper is intentionally not included in this repository at this stage, in accordance with the course review instructions. It should only be added when the applicable publication-submission condition has been satisfied.

## Acknowledgements

Developed for the **Forensic Analytics** course at **Vellore Institute of Technology (VIT), Chennai**, under the guidance of **Dr. S. Johanan Joysingh**.
