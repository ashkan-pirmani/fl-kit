---
title: Federated Model Developer / Data Scientist
description: Technical guidance for federated model developers and data scientists working with distributed machine learning systems.
contributors: [Ashkan Pirmani]
page_id: federated_model_developer
related_pages:
  your_tasks: [researcher, research_software_engineer]
  tool_assembly: [infrastructure, analysis]
training:
  - name: Federated Learning Training
    registry: TeSS
    url: https://tess.elixir-europe.org/search?q=federated+learning#materials
dsw:
- name: Do you have federated learning infrastructure in place?
  uuid: 49c009cb-a38c-4836-9780-8a8b3dd1cbac
- name: Have you established model evaluation protocols?
  uuid: 8915bd25-db22-4ed6-bcc8-b1bbdc52989e
faircookbook:
- name: Federated Learning Frameworks
  url: https://w3id.org/faircookbook/FCB034
- name: Model Evaluation and Validation
  url: https://w3id.org/faircookbook/FCB035
- name: Privacy-Preserving Techniques
  url: https://w3id.org/faircookbook/FCB074
---

## Introduction

The Federated Model Developer or Federated Data Scientist is responsible for designing, training, evaluating, and refining machine learning models in distributed, privacy-preserving environments. Unlike traditional data scientists, they work without direct access to raw data — instead orchestrating model development across multiple, siloed datasets hosted by data partners.

This role requires a combination of ML expertise, creativity, and adaptability. Developers must navigate technical limitations (non-IID data, communication constraints), ensure convergence and performance, and work closely with clinicians, infrastructure teams, and governance leads to ensure models are interpretable, ethical, and compliant.

## Key Responsibilities

* **Design model architectures** suitable for FL use cases (e.g. [FedAvg](https://arxiv.org/abs/1602.05629), [FedProx](https://arxiv.org/abs/1812.06127), [FedBN](https://arxiv.org/abs/2102.07624))
* **Select or implement federated learning algorithms** that handle heterogeneous data
* **Coordinate training across sites** using orchestration platforms (e.g. [Flower](https://flower.dev/), [Substra](https://substra.ai/))
* **Tune hyperparameters**, monitor convergence, and manage model versioning
* **Apply privacy-preserving techniques** (e.g. differential privacy, secure aggregation)
* **Validate and benchmark models**, both locally and globally
* **Document training setups**, evaluation procedures, and assumptions
* **Collaborate with clinical researchers** to interpret outputs and assess impact

## Common Challenges

* **Limited observability** into local data (no access to raw datasets)
* **Non-IID distributions** leading to biased or unstable models
* **Communication constraints** and system failures across nodes
* **Difficulty debugging training** without full visibility
* **Aligning ML goals** with clinical or institutional requirements
* **Explaining model behavior** to non-technical stakeholders
* **Ensuring reproducibility** and ethical use of models

## Recommended Tools & Resources

### FL Frameworks

* [Flower](https://flower.dev/) - Federated learning framework
* [Fed-BioMed](https://fedbiomed.org/) - Biomedical federated learning
* [Substra](https://substra.ai/) - Enterprise federated learning platform
* [FedML](https://fedml.ai/) - Research and production federated learning

### Privacy-Preserving Tools

* [PySyft](https://github.com/OpenMined/PySyft) - Privacy-preserving machine learning
* [TensorFlow Federated](https://www.tensorflow.org/federated) - Federated learning for TensorFlow
* [TenSEAL](https://github.com/OpenMined/TenSEAL) - Homomorphic encryption for TensorFlow

### Evaluation & Explainability

* [SHAP, LIME](https://shap.readthedocs.io/) - Model interpretability
* Custom dashboards for federated validation and metrics aggregation

### Benchmark Datasets & Challenges

* [Federated Tumor Segmentation (FeTS)](https://www.med.upenn.edu/cbica/fets/)
* [PATE, LEAF](https://leaf.cmu.edu/), and other synthetic or split datasets for prototyping

## Relevant FLKit Sections

* **Enable Infrastructure**: deployment and orchestration
* **Enhance & Wrangle Data**: input schema and harmonisation
* **Analyse Shared Data**: training, evaluation, reporting
* **Plan & Govern**: privacy risks, model sharing policies

## Training & Further Reading

* [OpenMined Courses on Privacy-Preserving ML](https://courses.openmined.org/)
* [FL Benchmark Papers & Challenges](https://federated.withgoogle.com/)
* [Nature Communications: The future of Federated Learning in Healthcare](https://www.nature.com/articles/s41467-021-27577-x)

## Solution

* [European Data Protection Supervisor's "Preliminary opinion on Data Protection and Scientific Research"](https://edps.europa.eu/sites/edp/files/publication/20-01-06_opinion_research_en.pdf)
* [BBMRI-ERIC ELSI Knowledge Base](https://www.bbmri-eric.eu/services/elsi-knowledge-base/) contains governance templates and guidance for federated learning projects.
* [Data Stewardship Wizard (DSW)](https://ds-wizard.org/) can help establish governance frameworks for federated learning projects.
* [FAIR Cookbook](https://faircookbook.elixir-europe.org/) provides step-by-step recipes for data governance tasks.
* [TeSS Training Portal](https://tess.elixir-europe.org/) offers training materials on data governance and management.
