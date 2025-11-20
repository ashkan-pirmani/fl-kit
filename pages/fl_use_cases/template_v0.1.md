---
title: federated analytics life cycle template
version: 1.1
search_exclude: true
description: Template to document federated analytics projects across stages in a clear, comparable way
page_id: new_template
---

## Introduction
Briefly describe the project in plain language.
- Problem and domain:
- Why federated analytics suits this problem:
- Who will use the results:

---

## Scope and objectives
Define the project boundaries and goals.
- Primary objective:
- Population and setting:
- Outputs to produce:
  - Predictive model, or
  - Descriptive / inferential statistics, or
  - Privacy preserving dashboards or studies
- Out of scope:

---

## Assumptions and constraints
Make assumptions explicit to avoid hidden risks.
- Key assumptions:
- Constraints (technical, organizational, regulatory):
- How assumptions will be validated or monitored:

---

## Governance
Policies and roles guiding responsible data and model use.
(*Note: governance covers oversight and policy; technical controls belong in the Privacy, security, and risk section.*)
- Stakeholders and roles:
- Approvals and oversight:
- Legal basis, consent, and agreements:
- Access and sharing policy for data, models, or results:
- Publication and dissemination rules:

---

## Data landscape
Describe the data available and site level differences.
- Clients and data sources:
- Inclusion and exclusion rules:
- Feature families and link to data dictionary:
- Label or outcome definitions (if applicable):
- Dataset size, class balance, and known biases:
- Data quality issues:

### Standards and harmonization
List conventions that ensure semantic alignment.
- Vocabularies, ontologies, or coding systems:
- Unit conventions and mapping rules:
- Versioning and updates:

---

## Infrastructure
How the federation is run and secured.
- Federation topology and orchestration:
- Frameworks and libraries:
- Client participation policy:
- Compute, storage, and networking:
- Monitoring and failure recovery:
- Simulation or live clients:
- Security baseline for transport and authentication:

---

## Wrangling
How data are prepared locally.
- Preprocessing steps and provenance:
- Train, validation, and test splits (if modeling):
- Normalization strategy and source of stats:
- Missing data handling:
- Class imbalance handling (if modeling):
- Validation checks and data QA:

---

## Computation plan
Describe methods to be run.

- **If predictive modeling**
  - Baselines and algorithms:
  - Personalization or adaptation strategy:
  - Model architectures:
  - Training schedule and early stopping:
  - Hyperparameters and search plan:

- **If analytics without modeling**
  - Statistical methods and estimators:
  - Aggregations and query design:
  - Hypothesis tests and assumptions:
  - Privacy budgets (if using differential privacy):

- Random seeds and reproducibility notes:

---

## Evaluation and success criteria
How results will be judged.

- **If modeling**
  - Primary and secondary metrics:
  - Client side evaluation plan:
  - Aggregation across clients:
  - Calibration and threshold selection:
  - Runtime and cost reporting:
  - Statistical tests and uncertainty:

- **If analytics without modeling**
  - Estimator accuracy and precision:
  - Coverage or confidence intervals:
  - Agreement with a centralized reference (if feasible):
  - Sensitivity analyses for assumptions:
  - Robustness checks across clients:
  - Runtime and cost reporting:

- Fairness and subgroup checks when applicable:

---

## Privacy, security, and risk
Technical and procedural safeguards.
(*Note: this section describes how governance policies are implemented.*)
- Threat model:
- Controls in use:
  - Secure aggregation
  - Encryption in transit and at rest
  - Differential privacy or k-anonymity if applicable
  - Access logging and audit trail
- Privacy budget accounting for repeated queries:
- Incident response and contacts:

---

## Reproducibility and sharing
Make it possible for others to rerun or extend the work.
- Code repository and commit tag:
- Environment capture and seeds:
- Artifacts to release (configs, metrics, models if allowed):
- Artifact registry or index for traceability:
- Synthetic samples or data access process:
- Known limitations and caveats:

---

## Operationalization and maintenance
Plan for use beyond the study.
- Deployment target and owner:
- **If modeling**
  - Monitoring for drift and performance:
  - Update and retraining policy:
- **If analytics without modeling**
  - Schedule for recurring queries or dashboards:
  - Change control for query definitions:
- Site playbooks and operator training:
- Sunset or rollback plan:

---


## Technology readiness level (TRL)
Describe maturity and supporting evidence.
- Claimed TRL:
- Evidence and references:
- Gaps to reach the next TRL:
- Target deployment setting:


---
## Wrap up
Summarize the key outcomes and next steps.
- Key learning:
- Decisions made and why:
- Next step to raise TRL:

