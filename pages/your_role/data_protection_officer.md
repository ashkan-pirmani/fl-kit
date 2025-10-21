---
title: Data Protection Officer (DPO) / Legal Advisor
description: Legal and regulatory guidance for Data Protection Officers and Legal Advisors working with federated learning in healthcare.
contributors: [Ashkan Pirmani]
page_id: data_protection_officer
related_pages:
  your_tasks: [data_steward, researcher, principal_investigator]
  tool_assembly: [governance, infrastructure, wrangling, analysis]
training:
  - name: GDPR and Health Data Training
    registry: TeSS
    url: https://tess.elixir-europe.org/search?q=GDPR+health+data#materials
dsw:
- name: Do you have data protection policies in place for federated learning?
  uuid: 49c009cb-a38c-4836-9780-8a8b3dd1cbac
- name: Have you conducted a Data Protection Impact Assessment (DPIA)?
  uuid: 8915bd25-db22-4ed6-bcc8-b1bbdc52989e
faircookbook:
- name: Data Protection Impact Assessment
  url: https://w3id.org/faircookbook/FCB074
- name: Legal Basis for Data Processing
  url: https://w3id.org/faircookbook/FCB035
- name: Data Sharing Agreements
  url: https://w3id.org/faircookbook/FCB034
---

## Introduction

The Data Protection Officer (DPO) or Legal Advisor is responsible for ensuring that federated learning activities comply with legal, regulatory, and ethical requirements — particularly those related to health data protection, such as the [General Data Protection Regulation (GDPR)](https://gdpr.eu/).

In a federated learning context, personal data never leaves its source, but legal risks and responsibilities still exist. This role guides the interpretation and implementation of legal frameworks, conducts [Data Protection Impact Assessments (DPIAs)](https://ico.org.uk/for-organisations/guide-to-data-protection/guide-to-the-general-data-protection-regulation-gdpr/accountability-and-governance/data-protection-impact-assessments/), and helps define the legal bases for data processing and model use.

Whether embedded in a healthcare institution, research consortium, or project governance team, the DPO/legal advisor ensures that privacy and accountability are built into the design of federated systems.

## Key Responsibilities

* **Interpret data protection regulations** in the context of federated learning
* **Define the legal basis** for data use (e.g. public interest, research exemption)
* **Conduct or advise on DPIAs** and ethics approvals
* **Draft or review data use agreements**, consortium agreements, and model sharing terms
* **Ensure data sovereignty principles** are respected (data remains local)
* **Monitor legal compliance** over time, including partner responsibilities
* **Advise on handling incidental findings**, withdrawal of consent, or data access requests
* **Collaborate with governance leads** and infrastructure teams to align legal and technical safeguards

## Common Challenges

* **Translating GDPR principles** to distributed, non-centralised processing models
* **Determining when federated learning** constitutes personal data processing
* **Navigating differences in national laws** and interpretations (especially in cross-border projects)
* **Ensuring transparency, accountability, and auditability** without breaching data minimisation
* **Managing joint controllership**, processor roles, and liability between partners
* **Establishing durable governance** once project funding ends

## Recommended Tools & Resources

### Legal Frameworks

* [GDPR text (EU)](https://eur-lex.europa.eu/eli/reg/2016/679/oj)
* [European Data Protection Board (EDPB) Guidelines](https://edpb.europa.eu/our-work-tools/general-guidance/gdpr-guidelines-recommendations-best-practices_en)
* [OECD Recommendation on Health Data Governance](https://www.oecd.org/health/health-data-governance.htm)

### Templates & Checklists

* [DPIA templates tailored to FL](https://www.ehden.eu/) (e.g. from EHDEN, TEHDAS, OpenMined)
* [Federated participation and data transfer agreements](https://www.openmined.org/)

### Ethics & Governance

* [AI Act (draft) relevance for FL](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:52021PC0206)
* [Institutional Ethics Boards or Data Access Committees (DACs)](https://www.rd-alliance.org/groups/data-access-committees-dac-interest-group)

## Relevant FLKit Sections

* **Plan & Govern**: consent models, roles & responsibilities
* **Enable Infrastructure**: security and auditability
* **Enhance & Wrangle Data**: anonymisation, pseudonymisation
* **Analyse Shared Data**: compliance in model use and reuse

## Training & Further Reading

* [Legal Challenges of FL (OpenMined Blog)](https://blog.openmined.org/legal-challenges-federated-learning/)
* [Sitra's Guide to GDPR & Health Data Use](https://www.sitra.fi/en/publications/gdpr-and-health-data-use/)
* [DPIA guidance by UK ICO](https://ico.org.uk/for-organisations/guide-to-data-protection/guide-to-the-general-data-protection-regulation-gdpr/accountability-and-governance/data-protection-impact-assessments/)

## Solution

* [European Data Protection Supervisor's "Preliminary opinion on Data Protection and Scientific Research"](https://edps.europa.eu/sites/edp/files/publication/20-01-06_opinion_research_en.pdf)
* [BBMRI-ERIC ELSI Knowledge Base](https://www.bbmri-eric.eu/services/elsi-knowledge-base/) contains governance templates and guidance for federated learning projects.
* [Data Stewardship Wizard (DSW)](https://ds-wizard.org/) can help establish governance frameworks for federated learning projects.
* [FAIR Cookbook](https://faircookbook.elixir-europe.org/) provides step-by-step recipes for data governance tasks.
* [TeSS Training Portal](https://tess.elixir-europe.org/) offers training materials on data governance and management.
