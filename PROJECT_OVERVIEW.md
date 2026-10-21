# Project Overview: Forensic Analytics

## 1. Academic Information

- **Project Title:** Forensic Analytics: Sequential and Spatial Data Mining for Anti-Money Laundering
- **Institution:** Vellore Institute of Technology (VIT), Chennai
- **Course:** Forensic Analytics
- **Subject Code:** CSE4074
- **Semester:** Fall 2026–27
- **Professor:** Dr. S. Johanan Joysingh

### Team Members

| Team Member | Student ID |
|---|---|
| MS Tamanna | 23MIA1003 |
| Akshat Kumar | 23MIA1110 |
| Aman Brahma | 23MIA1156 |

## 2. Project Background

Financial transaction datasets can contain patterns that are difficult to identify through individual transaction analysis alone. Repeated transaction sequences, unusual geographical movements, temporal relationships, and statistical irregularities can provide additional information for forensic examination.

This project explores the application of forensic analytics, sequential pattern mining, spatial data mining, and statistical analysis to synthetic financial transaction data. The notebooks generate the required datasets, introduce controlled synthetic fraud labels, analyse transaction behaviour, and combine risk indicators to support further investigation.

The project is an academic demonstration and does not constitute a production-ready anti-money-laundering system.

## 3. Problem Statement

Identifying potentially suspicious financial activity requires examining more than individual transaction values. Relationships between transactions over time, recurring transaction patterns, geographical locations, and deviations from expected behaviour may provide useful investigative context.

The project investigates how sequential and spatial analysis, together with statistical and temporal forensic techniques, can be applied to synthetic financial transactions to identify patterns that warrant further examination.

## 4. Project Objectives

1. Generate synthetic data for cities, customers, ATMs, merchants, and financial transactions.
2. Create controlled synthetic fraud-labelled transaction records for analytical evaluation.
3. Perform data profiling to understand the structure and characteristics of the generated datasets.
4. Apply sequential pattern mining to identify recurring transaction sequences.
5. Analyse spatial transaction patterns, geographical hotspots, and clusters.
6. Combine sequential and spatial indicators for integrated transaction risk analysis.
7. Apply Benford's Law analysis to relevant numerical transaction fields.
8. Examine transaction anomalies and temporal correlations.
9. Integrate forensic indicators to support risk assessment.
10. Evaluate analytical outputs and document the limitations of the findings.

## 5. Project Methodology

The workflow is divided into three stages.

### Stage 1: Synthetic Data Generation

The project begins by generating the entities and records needed for analysis.

- `01_generate_cities.ipynb` — Generates city data.
- `02_generate_customers.ipynb` — Generates customer records.
- `03_generate_atms.ipynb` — Generates ATM data.
- `04A_generate_merchants.ipynb` — Generates merchant data.
- `04_generate_transactions.ipynb` — Generates financial transaction records using the required entity datasets.

The generated files provide the input data for the subsequent analysis stages.

### Stage 2: Fraud Injection and Sequential-Spatial Analysis

This stage introduces controlled synthetic fraud labels and examines transaction patterns using sequential and spatial techniques.

- `05_fraud_injection.ipynb` — Creates transaction datasets containing controlled synthetic fraud-labelled records.
- `06_sequential_mining.ipynb` — Performs sequential pattern mining, including the implemented PrefixSpan and GSP approaches.
- `07_spatial_data_mining.ipynb` — Analyses geographical patterns, city hotspots, and spatial clusters.
- `08_sequential_spatial_fraud_detection.ipynb` — Combines sequential and spatial indicators to produce integrated transaction risk results.

The integrated detection notebook generates `integrated_transaction_risk_results.csv`, which serves as an input to the subsequent forensic-analysis notebooks.

### Stage 3: Forensic Analysis

The final stage examines the generated data and integrated results using statistical, temporal, and transaction-level techniques.

- `FA_01_Data_Profiling.ipynb` — Examines data structure, distributions, and characteristics.
- `FA_02_Benford_Analysis.ipynb` — Applies Benford's Law analysis to relevant numerical fields.
- `FA_03_Transaction_Anomaly_Analysis.ipynb` — Investigates unusual transaction behaviour.
- `FA_04_Temporal_Correlation_Analysis.ipynb` — Examines temporal relationships and correlations.
- `FA_05_Forensic_Risk_Integration.ipynb` — Integrates forensic indicators to support an overall risk assessment.

The intended execution order follows the dependencies identified during notebook inspection. Paths, package requirements, and end-to-end execution must be verified in the target environment.

## 6. Dataset Description

The current project notes report the following synthetic dataset characteristics:

| Entity or Measure | Reported Value |
|---|---:|
| Transactions | 149,994 |
| Controlled synthetic fraud-labelled transactions | 1,450 |
| Customers | 500 |
| Merchants | 100 |
| ATMs | 50 |
| Cities | 20 |

These figures are provisional until verified against the final generation code and outputs. The number of fraud-labelled transactions is distinct from the number of transactions flagged by a detection method.

The dataset is intended for experimentation with forensic analytics techniques. Only permitted, non-sensitive data should be included in the public repository.

## 7. Analytical Evaluation

The current project notes report the following transaction-level evaluation results:

| Method | Alerts | Precision | Recall | F1-score |
|---|---:|---:|---:|---:|
| Sequential-only | 38,871 | 2.63% | 70.48% | 5.07% |
| Spatial-only | 3,447 | 2.79% | 6.62% | 3.92% |
| Integrated | 5,083 | 10.96% | 38.41% | 17.05% |
| Integrated v2 | 1,630 | 2.45% | 2.76% | 2.60% |

The project notes additionally report 75 PrefixSpan patterns and 62 GSP patterns under the implemented settings.

**Result status:** The figures above are reported project values and have not been independently confirmed here. They must be checked against the final notebook outputs and evaluation calculations before being presented as verified results.

In the reported comparison, the integrated configuration has higher precision and F1-score than the listed sequential-only and spatial-only configurations, whereas sequential-only has higher recall. The reported integrated v2 configuration has lower precision, recall, and F1-score than the other listed configurations.

These observations apply only to the reported synthetic evaluation. They should not be interpreted as evidence of equivalent performance on real-world banking data.

## 8. Tools and Technologies

- Python
- Google Colab
- Jupyter Notebook
- Data processing and analysis libraries used in the notebooks
- Statistical and forensic analysis methods
- Sequential pattern mining
- Spatial analysis and clustering
- Data visualisation libraries used in the notebooks

The exact package dependencies should be determined from the notebook imports and installation instructions.

## 9. Expected Outputs

The notebooks are intended to produce analytical outputs such as:

- Synthetic entity and transaction datasets.
- Transaction datasets with controlled synthetic fraud labels.
- Sequential mining patterns and algorithm comparison results.
- Spatial analysis results, geographical hotspots, and cluster outputs.
- Integrated transaction-level risk results.
- Data profiling summaries and visualisations.
- Benford's Law analysis outputs.
- Transaction anomaly and temporal correlation results.
- Integrated forensic risk indicators.

Actual output files and their locations depend on the paths and configurations used in the notebooks.

## 10. Limitations and Responsible Use

- The project uses synthetic data and does not establish real-world banking performance.
- Synthetic fraud labels and patterns may not capture the full complexity of actual financial crime.
- Anomaly indicators and risk scores require interpretation and do not independently establish fraud.
- Results depend on the generated data, algorithm implementations, thresholds, and evaluation methods.
- Evaluation metrics must be confirmed against the final outputs.
- The project is intended for academic demonstration, not operational financial monitoring or automated enforcement.

## 11. Reproducibility

To reproduce the intended workflow:

1. Obtain the project notebooks.
2. Configure the required environment and any Google Drive paths.
3. Run the data-generation notebooks in dependency order.
4. Run fraud injection and sequential-spatial analysis.
5. Confirm that the integrated transaction risk output is generated.
6. Run the forensic-analysis notebooks.
7. Review the resulting outputs and verify the evaluation metrics.

Successful execution of the full workflow should be tested in the intended environment before claiming end-to-end reproducibility.

## 12. Research Paper Status

The related research paper is intentionally excluded from this repository at this stage, in accordance with the course review instructions. It should only be added once the applicable publication-submission condition has been satisfied.

## 13. Acknowledgements

This project is developed as part of the Forensic Analytics course at Vellore Institute of Technology (VIT), Chennai, under the guidance of Dr. S. Johanan Joysingh.
