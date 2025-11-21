---
title: The Journey of Data Within a Global Data Sharing Initiative - A Federated 3-Layer Data Analysis Pipeline to Scale Up Multiple Sclerosis Research
contributors: [Axel Faes, Ashkan Pirmani]
page_id: gdsi
search_exclude: false

---

The Global Data Sharing Initiative (GDSI) {% cite Peeters2020-kb Pirmani2023GDSI %} was launched at the start of the COVID-19 pandemic to understand how SARS-CoV-2 infection affects people living with multiple sclerosis (MS), especially those treated with disease-modifying therapies (DMTs).

![Figure 1: The global data sharing initiative data streams](https://asset.jmir.pub/assets/befccbce730f8509cff804e043063808.png)

When we started GDSI, we quickly realized that a one-size-fits-all approach wouldn't work. Some registries could share patient-level files immediately, others needed weeks of legal review, and a few couldn't export identifiable records at all due to national policies. Figure 1 captures how we solved this by building three parallel pathways, all feeding into the same trusted central platform.

The first pathway, **direct entry**, sits on the right side of the diagram. Here, clinicians and people with MS themselves enter cases through a web form that's already aligned with our data dictionary. This was crucial during those early pandemic months when speed mattered more than perfect completeness. The form lives inside the trusted central platform, so records go straight into our integrated dataset without any intermediate processing. We designed it with privacy-by-design principles: no cookies, no trackers, no identifiers beyond what's clinically necessary. Because the form enforces validation rules at input time, these records typically don't need downstream quality checks.

The middle pathway, **core data set sharing**, represents the more traditional approach. Registries that had the legal clearance and technical capacity exported standardized CSV files matching our dictionary schema and uploaded them through the central platform's secure interface. You can see in the diagram how registries and cohorts within the trusted platform feed their data into separate storage layers before everything converges into the integrated dataset. Fourteen registries chose this route, contributing 6,374 records, more than half our cohort. Each upload happened under signed data transfer agreements, with role-based access controls ensuring that registry members could only view their own records.

The third pathway, **federated model sharing**, appears at the top of Figure 1. This was our innovation for registries that couldn't send patient-level files but still wanted to participate. Instead of asking them to change their policies, we shipped Docker containers to their local infrastructure. These containers read their standardized data, ran the same PASS/FAIL quality checks we used everywhere else, and computed aggregated "buckets", multivariate contingency tables where similar patients are grouped together. Only those bucket counts traveled back to the central platform, never individual records. Four registries used this approach, and because each bucket can represent many patients, they still contributed 3,527 records, about a third of our total cohort.

What makes Figure 1 powerful is how it shows all three streams converging into a single integrated dataset. The trusted central platform becomes the meeting point where direct entry, core uploads, and federated aggregates are harmonized into one analysis-ready table. This hybrid architecture meant we never had to turn away a willing contributor just because their governance model didn't match our ideal.

![Figure 2: The global data sharing initiative's end-to-end real-world data analysis pipeline](https://asset.jmir.pub/assets/e13d87f0608944f8ccbc22e11f543938.png)

Figure 2 zooms in on the complete journey from raw registry data to published insights. If Figure 1 shows the "what," Figure 2 shows the "how", the seven-step pipeline that transformed fragmented MS registries into a unified evidence base.

**Step I** is where everything begins: standardization. Data custodians at each registry map their local variables to the "COVID-19 in MS Core Data Set," our shared dictionary. This step only applies to core data set sharing and federated model sharing registries because direct entry already embeds the dictionary in its web form. We learned early on that skipping this harmonization phase led to incompatible schemas downstream, so we made it mandatory. The dictionary covers everything from demographics and MS history to symptoms, comorbidities, DMT exposure, and COVID-19 outcomes, with clear definitions and permissible values for each field.

**Step II** is where the three acquisition streams from Figure 1 actually execute. Direct entry and core data set sharing interact directly with the central platform, with CSV files flowing into dedicated storage layers. Federated registries follow a different path: predefined queries travel alongside Docker containers to the local side, where scripts process the data and compute buckets, then ship those aggregated results back. This step respects each registry's willingness and internal policies while maintaining ethical and legal standards across all pathways.

**Step III** handles storage. Data from different holders live in separate layers initially, this separation was intentional. It lets us apply stream-specific quality checks, maintain audit trails, and troubleshoot issues without contaminating other sources. You can see in the diagram how each stream has its own database layer before integration happens.

**Step IV** is where the magic of integration occurs. All those separate layers consolidate into one comprehensive dataset. This is where we convert individual patient records and aggregated buckets into a unified table where every row represents a patient (or a bucket of patients) and every column is a harmonized variable from our dictionary. The integration logic handles the complexity of merging direct entry, core uploads, and federated aggregates while preserving the provenance of each record.

**Step V** introduces the local dashboard, a quality check mechanism that lets data providers review their own uploads. This was crucial for building trust. Registries could see exactly what we received, spot any mapping errors, and give feedback before their data entered the integrated set. It served as an additional sanity check and helped us catch issues early.

**Step VI** shows the online dashboard that the taskforce used during study development. Fed by the integrated dataset, this dashboard helped us answer feasibility questions: Do we have enough patients on rituximab? What's the geographic distribution? Are there gaps in our outcome variables? The taskforce used it to monitor data collection in real time and adjust our research questions as the cohort grew.

**Step VII** connects the integrated dataset to the analysis team through a secured Jupyter Notebook environment. This is where statisticians ran the multilevel mixed-effects logistic regression models, explored covariates, and generated the adjusted odds ratios that informed global MS treatment guidance. The secure connection ensures that only authorized analysts access the data, and every query is logged for reproducibility.

Together, Figures 1 and 2 tell the complete story: how we welcomed registries with different constraints, harmonized their data through a shared dictionary, integrated everything into one analysis-ready table, and enabled both quality checks and statistical analysis, all while respecting local governance and maintaining transparency at every step.

The sections below follow the four implementation phases described in Pirmani et al. (Planning, Preparation, Training, Deployment) and summarize the concrete artifacts produced at each stage, including the data dictionary, PASS/FAIL rules, federated scripts, and regression outputs.

## How to Read This Page

- **Context** - All regulatory references (for example GDPR Article 9(2)(j) and national sovereignty clauses) relate to the pandemic setting documented in Pirmani et al.
- **Hybrid approach** - Direct entry, core data set uploads, and federated model sharing operated in parallel so that every registry could contribute under its own policies.
- **Terminology** - Acronyms are expanded on first use: DMT (disease-modifying therapy), EDSS (Expanded Disability Status Scale), DPO (data protection officer), aOR (adjusted odds ratio).

## Step Overview (Planning to Preparation to Training to Deployment)

| Step | Focus | Highlights |
|------|-------|------------|
| 1. Planning | Governance + justification | Problem statement (“MS + COVID-19 risk while respecting national restrictions”), GDPR Article 9 analyses, ethics approvals (CME2020/025 + national IRBs), stakeholder map, assumptions register, “COVID-19 in MS Core Data Set” |
| 2. Preparation | Data + infrastructure | Direct-entry forms, core dataset uploads, federated Docker pipelines (bucket computation), PASS/FAIL quality engine, harmonization playbook |
| 3. Training | Analytics + privacy | Multilevel mixed-effects logistic regression on aggregated tables, covariates (age, sex, phenotype, EDSS, DMT), random effects per data source, threat model + incident response plan |
| 4. Deployment | Reproducibility + maturity | Tagged GitHub releases, PhysioNet data, JMIR publication, documented access guidance, roadmap toward secure aggregation pilots |

---

## Step 1: Planning

### Step 1 Highlights

- Clarified the scientific goal: quantify COVID-19 severity for people with MS on different DMTs without exporting identifiable records.
- Brought together registry leads, advocacy groups, and privacy experts to agree on governance, authorship, escalation paths, and communication cadences.
- Authored the “COVID-19 in MS Core Data Set,” a shared schema covering demographics, MS history, symptoms, comorbidities, DMT exposure, and COVID-19 outcomes {% cite Pirmani2023GDSI %}.
- Obtained umbrella ethics approval through Hasselt University (CME2020/025) and tracked each national institutional review board (IRB) amendment in a shared register.
- Logged assumptions and risks (network connectivity, local Docker readiness, consent wording, analyst availability) so every steering meeting had a single source of truth.

### Step 1 Key Questions

1. **Why federate instead of centralize?** GDPR Article 9, national sovereignty clauses, and institutional policies explicitly blocked emergency transfers of raw MS records.
2. **What exactly must be harmonized?** The data dictionary enumerated every field, permissible value, and metadata note so that direct-entry forms, CSV uploads, and federated buckets described variables identically.
3. **Who owns which decision?** Roles for registry leads, patient advocates, DPOs/legal teams, ethics chairs, and the coordination pod were documented so everyone knew their responsibilities.
4. **What might derail the plan?** The assumptions register monitored telecom outages, staff availability, local consent wording, and each site’s ability to run the shared scripts.

### Step 1 Deliverables

- Published data dictionary PDF (MS Data Alliance GitHub).
- Ethics tracker with approval IDs, expiry dates, special conditions.
- Consortium agreement and authorship policy.
- Stakeholder responsibilities list.
- Assumption/risk register referenced in every steering call.

---

## Step 2: Preparation

### Step 2 Highlights

As documented in Figure 1 of Pirmani et al., the team translated planning artifacts into a three-layer acquisition architecture that welcomed any willing contributor:

1. **Direct entry (speed-first):** Clinicians or people with MS entered cases through a web form aligned with the dictionary, and those records were stored directly inside the trusted central platform under strict access controls.
2. **Core data set sharing (conventional upload):** Registries exported dictionary-aligned CSV files containing patient-level data and uploaded them through the central GDSI platform under signed data-transfer agreements, audit logging, and per-registry workspaces. Fourteen registries used this lane (6,374 records; 56.5 percent of the cohort).
3. **Federated model sharing (no raw export):** Registries prohibited from transmitting patient-level files received Docker containers (the federated pipeline) that:
   - Applied the same PASS/FAIL rules locally.
   - Aggregated variables into multivariate “buckets.”
   - Sent only the counts to the coordination server.
   Four registries opted for this lane but still supplied 3,527 records (31.3 percent) because each bucket covered many patients.

### Step 2 Quality and Monitoring

- The PASS/FAIL specification inspected ranges (for example EDSS between 0 and 10, age between 0 and 110) and logical constraints (for example hospitalization implies a confirmed or suspected case, dates cannot precede MS onset). FAIL flags asked contributors to fix or justify the discrepancy.
- Direct-entry forms embedded these validations at input time; core uploads triggered instant server-side checks with human follow-up; federated containers executed the same validations locally before producing buckets.
- Local dashboards enabled registries to review their own uploads, while a central dashboard monitored data volumes and flagged issues that needed remediation calls.

### Step 2 Deliverables

- Direct-entry form specification and privacy checklist.
- Upload portal runbook (authentication, encryption, troubleshooting, escalation contacts).
- Federated pipeline source code, Docker images, and walkthrough video.
- PASS/FAIL criteria document (Table 1 in the paper plus an extended PDF).
- Harmonization playbook with per-registry mapping sheets and “data snapshots” summarizing what each site could realistically contribute.
- Dry-run report proving that at least one site per stream could deliver data end-to-end within two days.

---

## Step 3: Training

### Step 3 Highlights

- Aggregated tables from all streams were combined into an analysis-ready dataset of 11,284 rows, each containing the dictionary-defined variables.
- Multilevel mixed-effects logistic regression, using random intercepts per data source, evaluated DMT exposure versus COVID-19 severity while adjusting for:
  - Age bands (18–50, 50–70, >70).
  - Sex.
  - MS phenotype (relapsing-remitting vs progressive).
  - Disability level using EDSS (<6 vs ≥6).
  - DMT category (untreated, interferon, fingolimod, ocrelizumab, rituximab, etc.).
  - Outcomes: hospitalization, intensive care unit (ICU) admission, mechanical ventilation, death.
- Federated results were compared with centralized (where data-use agreements allowed) and local-only baselines to ensure no material loss of signal.

### Step 3 Findings

- **Rituximab:** higher odds of hospitalization (aOR 2.76; 95% CI 1.87–4.07), ICU admission (aOR 4.32; 95% CI 2.27–8.23), and ventilation (aOR 6.15; 95% CI 3.09–12.27), but no significant association with death (aOR 1.72; 95% CI 0.58–5.10).
- **Ocrelizumab:** higher odds of hospitalization (aOR 1.75; 95% CI 1.29–2.38) and ICU admission (aOR 2.55; 95% CI 1.49–4.36), neutral for ventilation (aOR 1.60; 95% CI 0.82–3.14) and death (aOR 0.73; 95% CI 0.32–1.70).
- The findings informed global MS guidance on how to manage anti-CD20 therapies during COVID-19 surges.

### Step 3 Risk Management

- Privacy risks were assessed before any aggregated data left a registry, ensuring that even bucketed statistics complied with local governance requirements.
- Registries had the opportunity to review PASS/FAIL dashboards and approve the aggregated exports, which maintained trust despite strict sharing policies.
- Reproducibility: every training run stored seeds, data snapshot IDs, package versions, and checksums in audit JSON files. Ten-seed experiments yielded consistent results (standard deviation about 0.002), demonstrating stability.

### Step 3 Deliverables

- Regression notebooks + audit logs.
- Comparison deck (federated vs centralized vs local-only).
- Fairness appendix with stratified metrics.
- Threat model + privacy impact assessment.
- Incident-response playbook.

---

## Step 4: Deployment

### Step 4 Highlights

- Cleaned repositories, tagged the commit used for the JMIR publication, and published environment specifications (`requirements.txt`, Dockerfiles, R session info).
- Released artifacts:
  - **Code/tooling:** Data dictionary, PASS/FAIL pipeline scripts, Docker images, and the federated UI, all on GitHub/Docker Hub.
  - **Data:** Direct-entry dataset (PhysioNet v1.0.0) with documentation for secondary analysis.
  - **Publications:** JMIR Medical Informatics article plus supplementary appendices describing the data acquisition architecture.
  - **Guidance:** Summaries for the global MS community so clinicians could incorporate the findings into treatment decisions.
- Documented the analysis pipeline so others can reproduce the results or adapt the approach to different research questions.
- Described how to request access to aggregated outputs via the project’s governance structure, including eligibility criteria and timelines.

### Step 4 Deliverables

- Tagged GitHub releases plus a reproducibility README.
- Data-access guide outlining public versus restricted artifacts and application procedures.
- Gap analysis explaining what would be needed to move from research deployment to broader production use.
- Roadmap toward secure aggregation pilots, clinician dashboards, and live federated monitoring.

---

## Results Snapshot

- **Cohort size:** 11,284 people with MS and suspected/confirmed COVID-19 contributed to the combined dataset. Direct entry supplied 12.3% of records, core uploads 56.5%, and federated buckets 31.3%.
- **Geography:** 80 countries participated; the largest contributors were the United States, Australia, Spain, Sweden, Germany, Argentina, Brazil, Turkey, Denmark, and the United Kingdom.
- **Clinical insight:** Anti-CD20 therapies (rituximab/ocrelizumab) increased the odds of hospitalization, ICU admission, and ventilation but did not significantly change mortality risk compared with other DMTs.
- **Operational proof:** Direct entry, core uploads, federated aggregation, PASS/FAIL quality checks, and multilevel analysis coexisted without violating local governance, demonstrating that hybrid federation is practical at global scale.

## Key Takeaways

1. **Explain why federation is non-negotiable.** Regulators, clinicians, and funders need to see the legal/ethical reasoning up front.
2. **Meet partners where they are.** Keeping direct entry, core uploads, and federated buckets in play allowed every registry to contribute without abandoning local policies.
3. **Make quality and privacy visible.** PASS/FAIL dashboards, threat models, and reproducibility manifests are as important as the final regression tables.
4. **Treat deployment as part of the deliverable.** Open repositories, access guides, and documented next steps let other disease areas reuse the pipeline responsibly.

## Bibliography

{% bibliography --cited %}
