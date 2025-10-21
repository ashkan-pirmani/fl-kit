---
title: Clinical Researcher / Data Generator
description: Guidance for clinical researchers and data generators working with federated learning in healthcare settings.
contributors: [Ashkan Pirmani]
page_id: clinical_researcher
related_pages:
  your_tasks: [data_steward, researcher, principal_investigator]
  tool_assembly: [governance, wrangling, analysis]
training:
  - name: Clinical Data Management Training
    registry: TeSS
    url: https://tess.elixir-europe.org/search?q=clinical+data+management#materials
dsw:
- name: Do you have clinical data quality standards in place?
  uuid: 49c009cb-a38c-4836-9780-8a8b3dd1cbac
- name: Have you established data harmonization protocols?
  uuid: 8915bd25-db22-4ed6-bcc8-b1bbdc52989e
faircookbook:
- name: Clinical Data Standards
  url: https://w3id.org/faircookbook/FCB034
- name: Data Quality Assessment
  url: https://w3id.org/faircookbook/FCB035
- name: Clinical Data Harmonization
  url: https://w3id.org/faircookbook/FCB074
---

## Introduction

The Clinical Researcher (or Data Generator) is central to federated learning in health: they are the source of both domain knowledge and high-quality data. Whether through clinical trials, hospital records, registries, or cohort studies, they produce the data that FL systems rely on — and they help interpret what trained models actually mean in real-world settings.

In federated learning, clinical researchers often retain custody of data at their institution and play a key role in shaping use cases, validating model outputs, and ensuring ethical and meaningful use of shared insights.

This role demands a strong understanding of the research context, ethical obligations, and the nuances of clinical data quality, bias, and interpretability.

## Key Responsibilities

* **Define clinically relevant research questions** that can be addressed through FL
* **Ensure collected data meets quality** and consistency standards
* **Collaborate on mapping and harmonizing** local data to shared models or schemas (e.g. [OMOP](https://www.ohdsi.org/data-standardization/the-common-data-model/), [FHIR](https://www.hl7.org/fhir/))
* **Act as a local custodian** of patient data — managing access, consent, and compliance
* **Validate outputs of trained models** and ensure clinical plausibility
* **Communicate risks, limitations, and potential impact** of federated models
* **Bridge communication** between technical teams and healthcare stakeholders

## Common Challenges

* **Understanding technical aspects of FL** without direct involvement in engineering
* **Dealing with fragmented, inconsistent, or poorly annotated** local data
* **Managing ethical risks**: bias, misinterpretation, and unintended consequences
* **Ensuring alignment** between clinical needs and model goals
* **Participating in FL projects** with limited local infrastructure or support
* **Making sense of global model results** without access to full data

## Recommended Tools & Resources

### Common Data Models & Standards

* [OMOP CDM (OHDSI)](https://www.ohdsi.org/data-standardization/the-common-data-model/)
* [HL7 FHIR](https://www.hl7.org/fhir/)

### Quality & FAIRness

* [FAIRification Framework](https://fairplus-project.eu/)
* [Data Quality Dashboard (OHDSI)](https://www.ohdsi.org/analytic-tools/)

### Interpretability Tools

* [SHAP or LIME](https://shap.readthedocs.io/) for model explainability
* [Model cards](https://modelcards.withgoogle.com/about) or use-case summaries adapted to clinical end users

### Ethics

* [Local ethics board materials](https://www.wma.net/policies-post/wma-declaration-of-helsinki-ethical-principles-for-medical-research-involving-human-subjects/), consent form templates, incidental findings protocols

## Relevant FLKit Sections

* **Plan & Govern**: define use case, consent, ethical framing
* **Enhance & Wrangle Data**: clinical data curation, harmonisation
* **Analyse Shared Data**: interpretation, evaluation, impact analysis

## Training & Further Reading

* [FAIR Cookbook for Health Data](https://faircookbook.elixir-europe.org/)
* [Bias in ML and Clinical AI – Nature Reviews](https://www.nature.com/articles/s41591-021-01614-0)
* [OHDSI Training Material](https://www.ohdsi.org/education/)

## Solution

* [European Data Protection Supervisor's "Preliminary opinion on Data Protection and Scientific Research"](https://edps.europa.eu/sites/edp/files/publication/20-01-06_opinion_research_en.pdf)
* [BBMRI-ERIC ELSI Knowledge Base](https://www.bbmri-eric.eu/services/elsi-knowledge-base/) contains governance templates and guidance for federated learning projects.
* [Data Stewardship Wizard (DSW)](https://ds-wizard.org/) can help establish governance frameworks for federated learning projects.
* [FAIR Cookbook](https://faircookbook.elixir-europe.org/) provides step-by-step recipes for data governance tasks.
* [TeSS Training Portal](https://tess.elixir-europe.org/) offers training materials on data governance and management.
