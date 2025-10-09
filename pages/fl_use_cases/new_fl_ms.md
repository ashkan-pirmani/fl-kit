---
title: federated learning life cycle in MSBase study
version: 1.1
contributors: [Ashkan Pirmani]
search_exclude: true
description: Example of documenting a federated learning project using the FA life cycle template
page_id: new_fl_ms
license: restricted
---

## Introduction
This project studied whether federated learning can predict two year disability progression in multiple sclerosis patients using routine clinical data.
Federated learning was chosen to respect privacy and data localization rules across countries. The results are intended for clinicians and researchers seeking better prognostic models without centralizing sensitive patient records.

---

## Scope and objectives
The primary objective was to assess whether personalized federated learning can match centralized performance in predicting disability progression.
The decision context is long term patient management and clinical research.
The population is patients with relapsing or progressive MS drawn from the MSBase registry.
The output is a predictive model of progression risk within two years.
Out of scope were exploratory analytics or federated statistics beyond this single prediction task.

---

## Assumptions and constraints
Key assumptions included:
- Disability progression can be reliably captured by EDSS scores following published criteria.
- Site level data are consistent enough to harmonize into comparable features.
- Simulated federation by country approximates real multi site federation.

Constraints:
- Only registry data from MSBase were used.
- Clients were simulated rather than run on live hospital servers.

Assumptions were checked against prior literature and through internal validation.

---

## Governance
Governance covered ethics, compliance, and oversight. KU Leuven granted PRET approval (G 2023 6771), and the Social and Societal Ethics Committee confirmed GDPR alignment.
MSBase served as the data provider. Researchers accessed harmonized datasets under agreements established with participating sites.
For transparency, all preprocessing and training code was made publicly available. According to the agreement with the data provider, the data access site (computing host) was clearly defined and approved. It was also agreed that all analyses would be conducted in a simulated manner, meaning the data would remain on its designated host and would not be physically transferred or split for training.


---

## Data landscape
Data came from the MSBase registry, a large international MS database.
Clients were defined at the country level, resulting in 32 federated sites.
Inclusion rules required at least three EDSS measures in the 3.25 years before baseline, plus sufficient follow up to assess two year outcomes.
The final dataset comprised 283,115 episodes from 26,246 patients.
Features included EDSS, KFS, relapse history, and therapies. Forty two tabular features were used for modeling.
Label definition followed published criteria for confirmed disability progression, with a six month confirmation period and exclusion of scores near relapses.
Class balance varied widely: some sites lacked positive cases altogether.

### Standards and harmonization
Data were harmonized using EDSS scoring conventions and MSBase’s existing coding rules. Relapse and therapy information followed registry definitions. Versioning and updates were managed within the MSBase framework.

---

## Infrastructure
The study simulated a server–client setup where each country acted as a client. All 32 clients participated in each round.
The system used PyTorch for modeling, Flower for orchestration, and scikit learn for metrics.
Experiments were run on the Flanders Supercomputer Center, using Intel Xeon Platinum CPUs.
Each run included 50 federation rounds, repeated 10 times for robustness.
Although simulated, the design mimicked real world federation with clear separation of client and server responsibilities.

---

## Wrangling
Preprocessing created episodes from longitudinal patient data. Each episode started at a baseline EDSS and included a history window with relapses, therapies, and function scores.
Labels were assigned based on confirmed EDSS worsening at two years.
Within each client, data were split 60–20–20 into train, validation, and test sets. Normalization was applied per client using training set statistics to avoid leakage.
Class imbalance was documented but not directly corrected in the main analysis loss function.
All preprocessing steps were captured in shared code with provenance.

---

## Computation plan
Two families of methods were evaluated.

**Modeling baselines** included centralized pooling, local only training, and federated algorithms such as FedAvg, FedProx, and FedOpt variants (FedYogi, FedAdam, FedAdagrad).

**Personalization strategies** included:
- AdaptiveDualBranchNet: a neural network with shared core layers and client specific extensions, scaled by client data size.
- Post federation fine tuning: local updates to the global model with reduced learning rates and batch size.

All models were implemented as multilayer perceptrons with 42 input features. Hyperparameters followed prior benchmarks. Runs were repeated with different seeds to check stability.

---

## Evaluation and success criteria
Evaluation was performed client side, with results aggregated using size weighted averages.
Metrics included ROC AUC, PR AUC, and total runtime.
Fairness was examined through client level performance, highlighting disparities for small or imbalanced sites.
Results showed:
- Centralized training achieved ROC AUC ~0.81 and PR AUC ~0.46.
- Personalized federated learning improved performance to ROC AUC ~0.84 and PR AUC ~0.52.
- Gains were largest in smaller or imbalanced clients.
Sensitivity analyses confirmed robustness across seeds.

---

## Privacy, security, and risk
Privacy was protected by simulating federation where raw data never left clients. Only model updates were shared.
Secure aggregation and encryption were assumed within the Flower framework.
Audit trails were maintained through reproducible code and logs.
Although differential privacy was not implemented, the design reduced risk by avoiding centralized test evaluation.

---

## Reproducibility and sharing
Preprocessing code, training pipelines, and environment files were released openly.
A public repository indexed all artifacts for traceability.
Data access requires agreements through MSBase, so synthetic examples were not provided.

---

## Operationalization and maintenance
Operationalization was not pursued in this study, but plans for future deployment include:
- Running true federated setups across real computing instances.
- Monitoring for model drift and updating periodically.
- Providing site playbooks and operator training to ensure consistent participation.
No dashboard or recurring analytics were scheduled for this phase. A rollback plan would rely on existing MSBase governance.

---

## Technology readiness level (TRL)
The work is best described as TRL 4–5: methods validated in simulation with realistic, multi country data.
Evidence comes from large scale experiments using the MSBase registry, with clients simulated by country. The gap to TRL 6 is live deployment across hospitals with true distributed governance and heterogeneous infrastructure.
The targeted setting is real world MS registries distributed across care centers.

---

## Wrap up
This study showed that personalized federated learning can approach centralized performance in predicting MS progression, despite strong site heterogeneity.
Key decisions included enforcing client side evaluation, simulating sites by country, and testing personalization strategies.
The next step toward higher TRL is deploying the system across live hospital clients with full governance and infrastructure support.

