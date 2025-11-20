---
title: Governance
description: This page describes the role, importance, and best practices of data governance in the data lifecycle, with a focus on FAIR principles.
contributors: [Ashkan Pirmani]
search_exclude: true
page_id: governance
related_pages:
  your_tasks: [data_steward, researcher, principal_investigator]
  tool_assembly: [infrastructure, wrangling, analysis]
training:
  - name: Data Governance Training
    registry: TeSS
    url: https://tess.elixir-europe.org/search?q=data+governance#materials
dsw:
- name: Do you have data governance policies in place?
  uuid: 49c009cb-a38c-4836-9780-8a8b3dd1cbac
- name: Have you established data access control mechanisms?
  uuid: 8915bd25-db22-4ed6-bcc8-b1bbdc52989e
faircookbook:
- name: Data Governance Framework
  url: https://w3id.org/faircookbook/FCB034
- name: Data Access Control
  url: https://w3id.org/faircookbook/FCB035
- name: Data Stewardship Principles
  url: https://w3id.org/faircookbook/FCB074
---

## What is data governance?

Data governance is the framework of policies, roles, responsibilities, and processes that ensure the responsible, secure, and ethical management of data across its lifecycle. In **federated learning**, data governance extends beyond traditional practices to address cross-institutional collaboration, where data stays at its source but is still used to train shared models.

FL governance defines **who can do what with which data and models**, under which conditions, and with which safeguards. It governs both data access and model lifecycle management (e.g. training, sharing, retention, reuse) across all participating organizations, following established [data stewardship principles](https://www.dataversity.net/data-concepts/what-is-data-stewardship/).

## Why is data governance important?
Effective governance is foundational to building **trust** in federated learning environments. It provides clarity and accountability across sites, ensures legal and ethical compliance, and helps align diverse institutional practices.
In federated learning, governance enables:

- Secure and ethical collaboration between partners without centralizing data
- Compliance with data protection regulations (e.g. [GDPR](https://gdpr.eu/), [HIPAA](https://www.hhs.gov/hipaa/index.html))
- Clear roles and responsibilities for local and global decision-making
- Transparency in how data and models are handled
- Consistency and quality in local data preparation and model training
- Risk reduction related to data misuse, model drift, or misalignment
- Responsible deployment and monitoring of shared models

Without robust governance, federated learning efforts risk fragmentation, non-compliance, and loss of trust between stakeholders.

## What should be considered for data governance?
* To ensure good governance practices that support responsible federated learning and align with FAIR principles, consider:
* **Participation Agreements**: Formalize agreements that define responsibilities, rights, and liabilities of each partner.
* **Decision-Making Structures**: Establish clear processes for decisions related to model design, training strategy, access control, and model use.
* **Legal & Ethical Compliance**: Ensure activities comply with applicable laws (e.g. [GDPR](https://gdpr.eu/)), ethics approvals, and institutional data policies.
* **Data Sovereignty**: Respect the principle that data remains under the control of the data provider at all times.
* **Audit Trails & Logging**: Maintain detailed logs of data access, training rounds, and model usage for transparency and accountability.
* **Access Control**: Clearly define who can access, contribute to, or deploy models and infrastructure components.
* **Model Lifecycle Governance**: Decide when and how models are updated, shared, validated, retired, or reused.
* **Training & Awareness**: Support all participants with guidance on legal, ethical, and technical aspects of governance in FL.
* **Alignment with FAIR**: Ensure that metadata, decisions, and governance documents are findable, accessible, interoperable, and reusable. Follow the [FAIR Data Principles](https://www.go-fair.org/fair-principles/) for comprehensive data management.