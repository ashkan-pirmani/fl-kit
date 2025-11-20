---
title: Wrangling
description: This page describes the role, importance, and best practices of data wrangling in the data lifecycle, with a focus on FAIR principles.
contributors: [Ashkan Pirmani]
search_exclude: true
page_id: wrangling
related_pages:
  your_tasks: [<!---REPLACE THIS with the page ID of the your_tasks pages that you want to list here as related pages--->]
training:
  - name:
    registry:
    url:
---

## What is data wrangling?
Data wrangling, also known as data cleaning or data munging, is the process of preparing raw data for analysis by transforming it into a structured, consistent, and enriched format. In the context of **federated learning**, wrangling typically happens locally at each data partner site, making it a **decentralized process**. Wrangling in FL ensures that multi-site datasets are compatible, harmonized, and analysis-ready, without needing to pool the data centrally.

## Why is data wrangling important?
Real-world data is often messy, incomplete, or inconsistent. Effective wrangling is essential to ensure data quality and comparability across multiple sources. In federated learning, it also plays a critical role in aligning local datasets to enable model training across institutions without centralizing data. Wrangling helps to:

- Improve local data quality, completeness, and consistency

- Enable semantic and syntactic interoperability across partners

- Reduce technical variation that could bias federated models

- Support model generalizability and fairness

- Contribute to compliance with FAIR principles at the local level

- Prevent data errors or schema mismatches during training

- Minimize rework during model deployment or evaluation


## What should be considered for data wrangling?
To ensure high-quality, ethical, and interoperable data wrangling in federated settings, consider:

* **Local Preprocessing Pipelines**: Implement consistent wrangling pipelines across sites using shared protocols or scripts, even if the data stays local.

* **Common Data Models**: Map local data to shared schemas (e.g. OMOP CDM, FHIR, custom federated schemas) to ensure semantic alignment.

* **Data Quality Checks**: Address missing values, inconsistent units, outliers, duplicates, and errors at each node.

* **Transformation Transparency**: Document and version all wrangling steps to ensure reproducibility and trust.

* **Anonymization or Pseudonymization**: Remove or mask personally identifiable information to comply with privacy requirements.

* **Validation Across Sites**: Use distributed validation tools or federated QA dashboards to ensure harmonization and detect inconsistencies.

* **Script Sharing & Containerization**: Share reusable wrangling code (e.g. as Docker containers or Jupyter notebooks) while keeping raw data local.

* **Automation & Monitoring**: Automate where possible and monitor logs for pipeline errors or deviations.

* **FAIR-by-Design**: Align wrangling outputs (metadata, formats, units) with FAIR principles to ensure downstream usability.
