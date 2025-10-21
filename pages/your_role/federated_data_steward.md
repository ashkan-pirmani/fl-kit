---
title: Federated Data Steward
description: Data stewardship guidance for federated learning environments in healthcare settings.
contributors: [Ashkan Pirmani]
page_id: federated_data_steward
related_pages:
  your_tasks: [data_steward, researcher]
  tool_assembly: [wrangling, governance, infrastructure]
training:
  - name: Federated Data Stewardship Training
    registry: TeSS
    url: https://tess.elixir-europe.org/search?q=federated+data+stewardship#materials
dsw:
- name: Do you have federated data stewardship protocols in place?
  uuid: 49c009cb-a38c-4836-9780-8a8b3dd1cbac
- name: Have you established data harmonization workflows?
  uuid: 8915bd25-db22-4ed6-bcc8-b1bbdc52989e
faircookbook:
- name: Federated Data Stewardship
  url: https://w3id.org/faircookbook/FCB034
- name: Data Harmonization
  url: https://w3id.org/faircookbook/FCB035
- name: Metadata Management
  url: https://w3id.org/faircookbook/FCB074
---

## Introduction

The Federated Data Steward plays a key supporting role in ensuring that health data used in federated learning (FL) is high quality, well-documented, legally compliant, and FAIR — even when it remains distributed across multiple institutions.

Building on the evolving profession of research data stewardship, this role adapts to the specific needs of secure, privacy-preserving, and cross-site data sharing. Federated data stewards act as local or central points of contact who bridge research, infrastructure, and governance efforts.

They help translate policies into practice, ensure datasets are harmonised and well-annotated, and support institutions in aligning with federated learning protocols and standards.

## Key Responsibilities

* **Assist with mapping and transforming** local data into harmonised formats or common data models (e.g. [OMOP](https://www.ohdsi.org/data-standardization/the-common-data-model/), [FHIR](https://www.hl7.org/fhir/))
* **Ensure metadata completeness and consistency** to support interoperability
* **Guide researchers and IT teams** on [FAIR principles](https://www.go-fair.org/fair-principles/) and legal requirements
* **Support the documentation** of data flows, wrangling pipelines, and data provenance
* **Coordinate with legal teams** on data access permissions, pseudonymisation, and retention policies
* **Help validate and test** data readiness for FL training rounds
* **Act as a knowledge hub** for tools, standards, and training in FL data stewardship

## Common Challenges

* **Supporting multiple departments or projects** with diverse data formats and quality
* **Translating FAIR and legal principles** into operational workflows
* **Working across silos** (research, IT, legal) without formal authority
* **Managing uncertainty** about roles, responsibilities, and technical expectations in FL
* **Ensuring sustainability and documentation** beyond the project lifecycle

## Recommended Tools & Resources

### Data Models & FAIR Alignment

* [OMOP CDM](https://www.ohdsi.org/data-standardization/the-common-data-model/)
* [HL7 FHIR](https://www.hl7.org/fhir/)
* [FAIRification Framework](https://fairplus-project.eu/)

### Data Stewardship Tools

* [Data Stewardship Wizard (DSW)](https://ds-wizard.org/)
* [FAIR Cookbook](https://faircookbook.elixir-europe.org/)
* [FAIRsharing](https://fairsharing.org/)

### Metadata & Validation

* [RO-Crate](https://www.researchobject.org/ro-crate/)
* [Data Quality Dashboard (OHDSI)](https://www.ohdsi.org/analytic-tools/)

## Relevant FLKit Sections

* **Enhance & Wrangle Data**: data cleaning, harmonisation, metadata
* **Plan & Govern**: local policy support, permissions, documentation
* **Enable Infrastructure**: aligning local systems with FL pipelines

## Training & Further Reading

* [ELIXIR Data Stewardship Competency Framework](https://competency.ebi.ac.uk/framework/datasteward/1.0)
* [Dutch Roadmap to Professionalising Data Stewardship](https://doi.org/10.5281/zenodo.4623713)
* [RDA Interest Group on Professionalising Data Stewardship](https://www.rd-alliance.org/groups/professionalising-data-stewardship-interest-group)

## Solution

* [European Data Protection Supervisor's "Preliminary opinion on Data Protection and Scientific Research"](https://edps.europa.eu/sites/edp/files/publication/20-01-06_opinion_research_en.pdf)
* [BBMRI-ERIC ELSI Knowledge Base](https://www.bbmri-eric.eu/services/elsi-knowledge-base/) contains governance templates and guidance for federated learning projects.
* [Data Stewardship Wizard (DSW)](https://ds-wizard.org/) can help establish governance frameworks for federated learning projects.
* [FAIR Cookbook](https://faircookbook.elixir-europe.org/) provides step-by-step recipes for data governance tasks.
* [TeSS Training Portal](https://tess.elixir-europe.org/) offers training materials on data governance and management.
