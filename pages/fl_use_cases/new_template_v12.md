---
title: Federated Analytics Life Cycle Template
version: 1.2
search_exclude: true
description: Document your federated analytics project from conception to deployment
page_id: new_template_v12
---

<style>
/* Info Box */
.example-toggle {
  background: linear-gradient(to right, #e3f2fd, #f0f4ff);
  border-left: 5px solid #1976d2;
  padding: 20px 25px;
  margin: 25px 0;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0,0,0,0.05);
}

/* Phase Headers */
h2[id*="phase"] {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white !important;
  padding: 16px 24px;
  margin: 40px 0 25px 0;
  font-weight: 600;
  font-size: 1.5em;
  border-radius: 8px;
  box-shadow: 0 3px 10px rgba(102, 126, 234, 0.3);
  border: none;
}

/* Example Container */
details.example {
  background: #ffffff;
  border: 1px solid #e1e4e8;
  border-left: 4px solid #6c63ff;
  border-radius: 8px;
  margin: 20px 0;
  overflow: hidden;
  box-shadow: 0 1px 3px rgba(0,0,0,0.06);
  transition: all 0.2s ease;
}

details.example:hover {
  box-shadow: 0 2px 8px rgba(0,0,0,0.1);
}

/* Example Summary */
details.example summary {
  cursor: pointer;
  padding: 14px 20px;
  background: linear-gradient(to right, #f8f9fa, #fff);
  font-weight: 600;
  color: #5a52d5;
  font-size: 0.95em;
  user-select: none;
  transition: all 0.2s ease;
  display: flex;
  align-items: center;
  border: none;
  border-radius: 0;
  margin: 0;
}

details.example summary:hover {
  background: linear-gradient(to right, #eef2ff, #f8f9ff);
  color: #4338ca;
}

details.example summary::marker {
  color: #6c63ff;
}

details.example[open] summary {
  background: linear-gradient(to right, #eef2ff, #f5f3ff);
  border-bottom: 2px solid #e5e7eb;
  color: #4338ca;
  margin-bottom: 0;
}

/* Example Content */
details.example .example-content {
  padding: 24px;
  background: #fafbfc;
  line-height: 1.8;
  color: #24292f;
  font-size: 0.95em;
}

details.example .example-content p {
  margin: 0 0 16px 0;
  line-height: 1.8;
}

details.example .example-content p:last-child {
  margin-bottom: 0;
}

/* Strong text in examples */
details.example .example-content strong {
  color: #1a202c;
  font-weight: 600;
}

/* Lists in examples */
details.example .example-content ul,
details.example .example-content ol {
  margin: 12px 0;
  padding-left: 24px;
}

details.example .example-content li {
  margin: 8px 0;
  line-height: 1.7;
}

/* Code-like elements in examples */
details.example .example-content code {
  background: #f1f3f5;
  padding: 2px 6px;
  border-radius: 3px;
  font-family: 'Monaco', 'Menlo', 'Consolas', monospace;
  font-size: 0.9em;
  color: #d73a49;
}

/* Blockquote styling - remove */
details.example blockquote {
  background: transparent;
  border: none;
  margin: 0;
  padding: 0;
}

/* Section descriptions */
h3 + p, h4 + p {
  color: #586069;
  font-size: 0.95em;
  margin-top: 8px;
  margin-bottom: 16px;
}
</style>

<div class="example-toggle">
  <strong>📘 Using this template:</strong> This template guides you through documenting your federated analytics project across its full lifecycle. Examples throughout use a running case study (sepsis prediction across European hospitals).
  <br><br>
  <button onclick="toggleAllExamples()" id="toggleBtn" style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white; border: none; padding: 10px 20px; border-radius: 6px; cursor: pointer; font-weight: 600; box-shadow: 0 2px 4px rgba(102,126,234,0.3); transition: all 0.2s ease;" onmouseover="this.style.transform='translateY(-1px)'; this.style.boxShadow='0 4px 8px rgba(102,126,234,0.4)'" onmouseout="this.style.transform='translateY(0)'; this.style.boxShadow='0 2px 4px rgba(102,126,234,0.3)'">
    ✨ Show All Examples
  </button>
</div>

<script>
let examplesVisible = false;
function toggleAllExamples() {
  const details = document.querySelectorAll('details.example');
  const btn = document.getElementById('toggleBtn');
  examplesVisible = !examplesVisible;

  details.forEach(d => {
    if (examplesVisible) {
      d.setAttribute('open', '');
    } else {
      d.removeAttribute('open');
    }
  });

  btn.textContent = examplesVisible ? '✨ Hide All Examples' : '✨ Show All Examples';
}
</script>

---

## Federated Analytics Lifecycle

This template follows the federated analytics lifecycle from **planning** through **deployment**:

1. **🎯 Planning & Scoping** → Define the problem, objectives, and federated approach
2. **⚖️ Governance & Ethics** → Establish oversight, legal basis, and data sharing agreements
3. **🗂️ Data & Standards** → Understand data landscape and harmonization needs
4. **🔧 Preparation & Infrastructure** → Prepare data locally and set up federation infrastructure
5. **🧬 Development & Training** → Design and execute federated computations
6. **🔒 Privacy, Security & Risk** → Implement safeguards and threat mitigation
7. **📚 Reproducibility & Sharing** → Enable others to validate, reuse, or extend your work
8. **🚀 Deployment & Maturity** → Plan for operational use and assess readiness

---

## 🎯 Phase 1: Planning & Scoping

### Problem and Domain
What challenge are you addressing? Describe the clinical, scientific, or operational need in plain language.

<details class="example">
<summary>📝 Example</summary>
<div class="example-content" markdown="1">

Early detection of sepsis in intensive care units is still a huge clinical challenge. When treatment gets delayed beyond the first hour of onset, mortality rates jump above 25%. Our consortium of five European university hospitals wants to build a machine learning model that can predict sepsis onset 4 to 6 hours before doctors would normally catch it, giving clinicians actual time to step in and treat patients. The problem with current commercial sepsis alerts is they go off way too often (high false-positive rates) because they're trained on narrow datasets from just one or two hospitals. We think that training a model across our diverse hospital populations will make it work better in the real world without giving up patient privacy.

</div>
</details>

### Why Federated Analytics?
Why can't you pool data centrally? Explain the regulatory, policy, trust, or infrastructure barriers.

<details class="example">
<summary>📝 Example</summary>
<div class="example-content" markdown="1">


ICU data are incredibly sensitive and protected under GDPR and national health data laws. Every hospital's ethics committee has said absolutely no to transferring individual patient records outside their firewalls. On top of that, hospital data governance boards are nervous about sharing raw data because of competitive concerns and liability worries. Federated learning lets us train a shared model while keeping all patient records local at each hospital, which works for both the regulators and the hospital administrators.


</div>
</details>

### Primary Objective
State your single most important goal. Be specific and measurable.

<details class="example">
<summary>📝 Example</summary>
<div class="example-content" markdown="1">


Train a recurrent neural network that can predict sepsis onset 4 to 6 hours in advance, hitting at least 0.80 AUROC and 0.30 positive predictive value when tested on held-out data at all five of our hospitals.


</div>
</details>

### Population and Setting
Who or what does your data represent? Include geographic and temporal scope.

<details class="example">
<summary>📝 Example</summary>
<div class="example-content" markdown="1">


Adult patients (18 years and older) admitted to intensive care units at our five participating hospitals between January 2018 and December 2023. Data come from electronic health record systems with ICU-specific modules that capture vital signs, lab results, medications, and clinical notes. We've got two hospitals in Germany, one in the Netherlands, one in France, and one in Spain. Total cohort is roughly 45,000 ICU admissions.


</div>
</details>

### Outputs
What will you produce? (Model, statistics, dashboard, insights)

<details class="example">
<summary>📝 Example</summary>
<div class="example-content" markdown="1">


The primary output is a trained LSTM-based sepsis prediction model with serialized weights, preprocessing pipelines, and clinical deployment documentation. Secondary outputs include federated summary statistics on sepsis incidence, time-to-treatment, and demographic distributions across sites (without disclosing individual hospital identities). We will also produce a privacy-preserving dashboard showing model performance trends over training rounds.


</div>
</details>

### Out of Scope
What will you NOT do? Manage expectations explicitly.

<details class="example">
<summary>📝 Example</summary>
<div class="example-content" markdown="1">


This project does not include pediatric ICU patients, post-surgical recovery units, or emergency department settings. We will not develop a treatment recommendation system, just an early warning for sepsis risk. Real-time deployment integration with hospital alert systems is out of scope for the current phase; this work focuses on model development and offline validation.


</div>
</details>

### Assumptions and Constraints
Make hidden assumptions explicit. What technical, organizational, or regulatory limits exist?

<details class="example">
<summary>📝 Example</summary>
<div class="example-content" markdown="1">


**Assumptions:** We assume all hospitals use Sepsis-3 clinical criteria and document it in structured EHR fields within 24 hours. We assume vital signs are recorded every 15 minutes and that key labs (CBC, lactate, creatinine) are available for most patients. We assume each hospital can dedicate a GPU server accessible during evening/weekend training rounds and that data can be harmonized to OMOP or FHIR within the project timeline.

**Constraints:** Two hospitals use air-gapped networks requiring secure file transfer via IT departments. All sites need annual ethics renewal (12-month cycles). GPU access limited to off-peak hours (8 PM to 6 AM). One site has an older EHR with limited API access. Budget caps us at 100 federated rounds (~€5,000 cloud costs).

**Validation:** During month one, we'll pilot with 1,000 random admissions per site to verify sepsis labeling accuracy, vital sign completeness, and lab availability. We'll test network connectivity and GPU access during two mock training rounds. If any site shows <80% data completeness, we'll revisit criteria or provide wrangling support.


</div>
</details>

---

## ⚖️ Phase 2: Governance & Ethics

### Stakeholders and Roles
Who are the decision-makers, data custodians, developers, and users?

<details class="example">
<summary>📝 Example</summary>
<div class="example-content" markdown="1">


**Principal Investigator:** Dr. Elena Schmidt (Charité Berlin)
**Site Leads:** Dr. Jan de Vries (Amsterdam UMC), Dr. Marie Dubois (AP-HP Paris), Dr. Carlos Martínez (Hospital Clínic Barcelona), Dr. Hans Müller (Heidelberg)
**Data Stewards:** One per site, responsible for local extraction and QA
**Technical Team:** TU Munich (federation infrastructure), University of Amsterdam (model architecture)
**End Users:** ICU physicians and nursing staff
**Funding:** EU Horizon Europe Grant No. 101234567
**Oversight:** Independent Data Safety Monitoring Board, quarterly reviews


</div>
</details>

### Ethics and Approvals
List institutional review boards, ethics committees, and approval reference numbers.

<details class="example">
<summary>📝 Example</summary>
<div class="example-content" markdown="1">


Each hospital obtained independent ethics approval:
- Charité Ethics Committee (EA1/078/23)
- Amsterdam UMC Medical Ethics Review Committee (2023.0156)
- INSERM Paris Ethics Committee (23-1042)
- Hospital Clínic Barcelona Clinical Research Ethics Committee (HCB/2023/0389)
- Heidelberg University Hospital Ethics Committee (S-245/2023)

All approvals granted waiver of informed consent for retrospective analysis of de-identified data. Federated Data Protection Impact Assessment completed March 2024.


</div>
</details>

### Ethics Status
Choose: Approved / Waived or Exempt / Not Applicable

<details class="example">
<summary>📝 Example</summary>
<div class="example-content" markdown="1">


**Approved** by all five institutional ethics committees. Waiver of informed consent granted under GDPR Article 89 (research in public interest) as this involves retrospective de-identified data with minimal privacy risk given federated approach. Patients informed via hospital privacy notices that de-identified data may be used for research and quality improvement.


</div>
</details>

### Legal Basis and Agreements
Describe data use agreements, legal frameworks (GDPR, HIPAA), and consortium contracts.

<details class="example">
<summary>📝 Example</summary>
<div class="example-content" markdown="1">


**GDPR Basis:** Article 6(1)(e) public interest + Article 9(2)(j) scientific research with safeguards
**Consortium Agreement:** Multi-party contract specifying no individual-level data transfer. Model updates (gradients/weights) considered non-personal data under GDPR when aggregated across sufficient patients.
**Provisions:** Audit rights, site withdrawal process, dispute resolution


</div>
</details>

### Access and Sharing Policy
Who can see raw data, models, and results? Any embargoes?

<details class="example">
<summary>📝 Example</summary>
<div class="example-content" markdown="1">


**Raw data:** Never leave hospital premises
**Model updates:** Accessible only to central server during training, deleted after aggregation
**Final model:** Shared with consortium under restricted license for validation and potential clinical use
**Metrics:** Aggregated performance and federated statistics publicly available via project website
**Site-level results:** Not disclosed without explicit site permission
**Embargo:** 6 months from data collection end for consortium manuscript preparation


</div>
</details>

### Publication and Dissemination
Authorship rules, preprint policies, media engagement, open access mandates.

<details class="example">
<summary>📝 Example</summary>
<div class="example-content" markdown="1">


**Authorship:** ICMJE guidelines; site leads and key technical contributors as co-authors
**Review:** Manuscript drafts circulated 4 weeks before submission
**Preprints:** Encouraged but must notify consortium
**Media:** Requires approval from all institutional communications officers
**Open Access:** EU Horizon mandates (immediate OA or 6-month green OA)
**Code:** Apache 2.0 license
**Model weights:** Research-only license due to clinical safety considerations


</div>
</details>

---

## 🗂️ Phase 3: Data & Standards

### Clients and Data Sources
List participating sites or data silos with context on their systems.

<details class="example">
<summary>📝 Example</summary>
<div class="example-content" markdown="1">


Five university hospital ICUs:
1. **Charité Berlin:** Epic EHR, ~12,000 ICU admissions/year
2. **Amsterdam UMC:** Metavision ICU system, ~8,000/year
3. **AP-HP Paris:** Orbis/Dedalus, ~10,000/year
4. **Hospital Clínic Barcelona:** SAP i.s.h.med, ~7,000/year
5. **Heidelberg University Hospital:** Copra System, ~8,000/year

All use bedside monitoring logging vitals every 1-5 minutes with lab system integration.


</div>
</details>

### Federation Mode
Simulated / Live / Hybrid. Describe your progression through TRL phases.

<details class="example">
<summary>📝 Example</summary>
<div class="example-content" markdown="1">


**Hybrid approach with phased progression:**

**Phase 1 (current, TRL 4):** Fully simulated using MIMIC-III partitioned into five virtual clients by random patient assignment. We introduced heterogeneity via stratified sampling (mortality rates 8-15%, varying surgical vs. medical ICU proportions). Each virtual client runs in separate Docker container. Does NOT capture: real network latency, firewall constraints, site-specific data quality issues, local workflow variations, or organizational coordination overhead.

**Phase 2 (planned, TRL 6):** Pilot with two live hospitals (Charité, Amsterdam UMC) using historical data, plus three simulated MIMIC-III clients. Tests real data heterogeneity, network, and governance without requiring all five sites ready simultaneously.

**Phase 3 (future, TRL 7+):** All five hospitals with live data, moving toward prospective real-time validation.


</div>
</details>

### Inclusion and Exclusion Criteria
Define eligibility for records or subjects.

<details class="example">
<summary>📝 Example</summary>
<div class="example-content" markdown="1">


**Include:** Adults ≥18 years, ICU stay ≥24 hours, at least one vital sign set and one lab result recorded

**Exclude:**
- Sepsis on ICU admission (we predict new-onset during stay)
- Comfort-care or DNR orders within first 6 hours (end-of-life confounding)
- ICU readmissions same hospitalization (ensure independence)
- Missing patient IDs or implausible vitals (e.g., HR >300 bpm)


</div>
</details>

### Features and Data Dictionary
Summarize variables by family. Link to full data dictionary.

<details class="example">
<summary>📝 Example</summary>
<div class="example-content" markdown="1">


**48 features in 5 families:**

1. **Demographics:** Age, sex, admission source
2. **Vital signs** (hourly): HR, BP systolic/diastolic, temperature, RR, SpO2, GCS
3. **Labs** (irregular): WBC, platelets, lactate, creatinine, bilirubin, procalcitonin
4. **Interventions** (binary): Mechanical ventilation, vasopressors, renal replacement
5. **Comorbidities:** Charlson Index from ICD-10 codes

Full dictionary: `docs/data_dictionary.md` using OMOP CDM v5.4


</div>
</details>

### Outcome Definitions
If modeling or testing: define targets clearly.

<details class="example">
<summary>📝 Example</summary>
<div class="example-content" markdown="1">


**Primary:** Sepsis onset per Sepsis-3 (SOFA ≥2 point increase within 24h + suspected infection via blood culture order or antibiotic start). Label assigned 4 hours before clinical documentation to allow prediction lead time. Exclude onset within first 6 hours (prevalent cases).

**Secondary:** Septic shock (sepsis + vasopressors + lactate >2 mmol/L), 28-day mortality


</div>
</details>

### Dataset Characteristics
Sample sizes, class balance, known biases.

<details class="example">
<summary>📝 Example</summary>
<div class="example-content" markdown="1">


**Total:** ~45,000 ICU admissions (range per site: 7K-12K)
**Sepsis incidence:** 12% overall, varies by site (9-16%) due to case mix differences
**Class imbalance:** Significant (1:8 ratio), requiring weighting strategies
**Biases:** Elderly (>75) underrepresented at surgical sites; one site has high proportion of immunocompromised patients (oncology/transplant co-location). Sex: 60% male, 40% female


</div>
</details>

### Data Quality Issues
Missingness, measurement errors, documentation gaps.

<details class="example">
<summary>📝 Example</summary>
<div class="example-content" markdown="1">


**Vitals:** >95% complete due to continuous monitoring, but gaps during patient transport
**Labs:** Procalcitonin ~40% missing (not routinely ordered everywhere). Lactate more common in septic patients (potential label leakage).
**One site:** 6-month period in 2019 with inconsistent GCS documentation due to EHR migration, may exclude
**Timestamps:** Vitals accurate to minute; some labs only have date (not time)


</div>
</details>

### Standards and Harmonization
Vocabularies, units, ontologies, versioning.

<details class="example">
<summary>📝 Example</summary>
<div class="example-content" markdown="1">


**Labs:** LOINC v2.73
**Vitals:** IEEE 11073 nomenclature
**Diagnoses:** ICD-10 (2019 version)
**Medications:** ATC classification
**Units:** UCUM standard (temperature °C, BP mmHg, labs in SI units)
**Conversions:** One site reports temperature °F and creatinine mg/dL, automated conversion in preprocessing
**SOFA calculation:** Standardized shared Python function
**Versioning:** Frozen at project start, updates trigger mapping revalidation


</div>
</details>

---

## 🔧 Phase 4: Preparation & Infrastructure

### Local Data Preparation

**This is where raw data transforms into analysis-ready features at each participating site.** All processing happens locally before any federated training begins. Document your preprocessing pipeline, data splits, normalization approach, and quality assurance steps so others can understand and reproduce your work.

**What to document:** Describe the complete data transformation pipeline (filtering, feature engineering, windowing), how you create train/validation/test splits, your strategy for normalization (local vs. global statistics), how you handle missing values and class imbalance, and what automated quality checks you run before data enters the federation.

<details class="example">
<summary>📝 Example: Complete Data Preparation Pipeline</summary>
<div class="example-content" markdown="1">

**Preprocessing Steps (Python 3.10, version-controlled):**

1. Extract ICU stays meeting criteria (past 5 years)
2. Resample vitals to 1-hour intervals (last-observation-carried-forward if gap <2h; missing if >2h)
3. Align labs to nearest hourly timestamp
4. Calculate rolling 24h SOFA scores using shared function
5. Generate time-series windows: 12-hour lookback (12 timesteps × 48 features)
6. Flag and exclude windows with >30% missing features
7. Apply label: positive if sepsis 4-6h later, negative otherwise
8. Export to HDF5 with metadata (patient hash, timestamp, site pseudonym)

**Data Splits (Temporal):**
- Train: 2018-2021 (~70%), Validation: 2022 (~15%), Test: 2023 (~15%, held out)
- Patients kept together (all windows from one stay in same split) to prevent leakage

**Normalization (Federated Two-Stage):**
1. Each site computes local mean/SD on training data
2. Server aggregates to global statistics (sample-size weighted)
3. Sites apply z-score: (value - global_mean) / global_SD
4. Outliers clipped to 1st/99th percentile before normalizing

**Missing Data:**
- Vitals: Carry forward last value within 2h → patient median → site median
- Labs: Add binary "missingness indicator" (ordering decision is informative)
- Procalcitonin (40% missing): Include value (imputed) + missingness flag

**Class Imbalance (12% sepsis incidence, 1:8 ratio):**
- Class weighting: Positive=8.0, Negative=1.0 in loss function
- Batch stratification: Ensure ≥20% positive examples per batch

**Quality Assurance:**
- Schema validation, range checks, duplicate detection, temporal consistency
- Label sanity check (sepsis incidence 5-25%), missingness profiling
- **Discovery:** One site inverted BP columns, caught by range check (systolic < diastolic impossible)

</div>
</details>

### Federation Infrastructure

**The computational backbone that enables distributed training.** Document your network architecture, software stack, compute resources, and operational procedures. This helps others understand technical requirements and troubleshoot issues.

**What to document:** Network topology (star, peer-to-peer, hierarchical), orchestration framework and scheduling, client participation policies, hardware specifications, simulation setup (if applicable), monitoring and failure recovery mechanisms, and baseline security controls.

<details class="example">
<summary>📝 Example: Complete Infrastructure Setup</summary>
<div class="example-content" markdown="1">

**Topology & Orchestration:**
- Centralized star: Single Azure server + five hospital clients (no client-to-client communication)
- Flower 1.5.0 on Azure D4s v3 VM (4 vCPUs, 16GB RAM, Ubuntu 22.04)
- Schedule: Saturday nights 00:00-06:00 CET to avoid disrupting hospital operations
- Round duration: ~90min (10min distribution, 60min training, 10min upload, 10min aggregation)
- Chosen for simplicity and easier ethics approval (peer-to-peer requires additional governance)

**Software Stack:**
- Flower 1.5.0, PyTorch 2.0.1, NumPy 1.24.3, Pandas 2.0.1, Scikit-learn 1.2.2, H5py 3.8.0
- Docker containers (pytorch/pytorch:2.0.1-cuda11.7-cudnn8-runtime), version-tagged in Azure Container Registry

**Client Participation:**
- Minimum 3 of 5 clients per round; if <3 within 30min, round postponed
- All available clients included (no performance-based selection to avoid fairness issues)
- Consistent dropout (>3 rounds) triggers troubleshooting
- **Pilot issue:** One client had firewall blocks; worked with IT to whitelist server IP

**Compute & Network:**
- Server: Azure D4s v3 (~€150/month), 4 vCPUs, 16GB RAM, 128GB SSD
- Clients: On-prem workstations, 8-16 cores, 32-64GB RAM, NVIDIA RTX 3080/A4000 (10-16GB VRAM), 1TB SSD
- Bandwidth: Model size ~45MB, ~50GB total transfer over 100 rounds (negligible for hospital networks)

**Simulation (Current Phase, MIMIC-III):**
- Five virtual Docker containers on single Ubuntu server (AMD Threadripper 3970X, 64 cores, 128GB RAM, 2×RTX 3090)
- Artificial 2-5s network delay via time.sleep()
- **NOT simulated:** Packet loss, firewall negotiations, human coordination, real data heterogeneity
- **Purpose:** Algorithm development; will underestimate real-world challenges

**Monitoring & Recovery:**
- Centralized logging (Azure Monitor), real-time dashboards (Prometheus + Grafana)
- Alerts via Email/Slack: round failures, insufficient clients, crashes
- Retry logic: Timeout >10min → aggregate without that client (if ≥3 present)
- Model checkpoints every 5 rounds to Azure Blob for disaster recovery

**Security Baseline:**
- HTTPS with TLS 1.3 (Let's Encrypt certificate)
- Pre-shared 256-bit API tokens (rotated quarterly, distributed via encrypted email)
- Azure VM in dedicated VNet, inbound HTTPS only from whitelisted IPs
- SSH: team IPs only, public key authentication
- Binary PyTorch files only (no raw patient data transmitted)
- Monthly vulnerability scans (Azure Security Center)

</div>
</details>

---

## 🧬 Phase 5: Development & Training

### Computation Plan

**For Predictive Modeling:**

<details class="example">
<summary>Example: Centralized Baseline</summary>
<div class="example-content" markdown="1">


Trained same LSTM on full MIMIC-III (~40K stays) with identical preprocessing/hyperparameters. Achieved AUROC 0.83 (95% CI: 0.81-0.85) on MIMIC-III test set. Reference to assess if federated learning on our five-hospital consortium can match/exceed centralized performance while preserving privacy. Note: MIMIC-III is single-center US data; generalization to European hospitals uncertain.


</div>
</details>

<details class="example">
<summary>Example: Federated Algorithms</summary>
<div class="example-content" markdown="1">


Compare three:
1. **FedAvg** (vanilla baseline)
2. **FedProx** (proximal term for heterogeneity, mu=0.01)
3. **FedAvgM** (server-side momentum, beta=0.9)

All aggregate via sample-size-weighted average. No personalized FL (want single global model deployable everywhere without site-specific versions).


</div>
</details>

<details class="example">
<summary>Example: Model Architecture</summary>
<div class="example-content" markdown="1">


**Bidirectional LSTM:**
- Input: 48 features × 12 timesteps
- 2 stacked Bi-LSTM layers (128 hidden units each)
- Dropout (p=0.3)
- FC layer (64 units, ReLU)
- Dropout (p=0.3)
- Output (2 units, softmax)
- Total: ~2.3M parameters

Chose LSTMs over Transformers (more sample-efficient, lower memory for our moderate datasets and GPU limits). Tested logistic regression on time-aggregated features but much worse (AUROC 0.68).


</div>
</details>

<details class="example">
<summary>Example: Training Schedule</summary>
<div class="example-content" markdown="1">


Up to 100 communication rounds. Each round: 3 local epochs, batch size 64 (shuffled). Early stopping: if validation AUROC doesn't improve for 10 consecutive rounds, stop. Simulation converged around round 60-70. Local training: ~45 min/client (varies: Charité 12K admissions ~60min, Barcelona 7K ~30min).


</div>
</details>

<details class="example">
<summary>Example: Hyperparameters</summary>
<div class="example-content" markdown="1">


Tuned on MIMIC-III simulation via grid search: learning rate (0.001, 0.0005, 0.0001), dropout (0.2, 0.3, 0.5), LSTM hidden (64, 128, 256), local epochs (1, 3, 5).

**Best:** LR 0.0005 (Adam), dropout 0.3, hidden 128, 3 epochs. Same hyperparameters for all algorithms (fair comparison). Aggregation weights proportional to training samples (FedAvg standard). No additional tuning on live hospital data (avoid overfitting, limited compute time).


</div>
</details>

**For Analytics Without Modeling:**

<details class="example">
<summary>Example: Federated Statistics</summary>
<div class="example-content" markdown="1">


Compute federated descriptive stats on sepsis epidemiology: mean time ICU admission→sepsis, median SOFA at diagnosis, incidence per 1000 patient-days. Each site calculates local means/variances/sample sizes → server computes weighted averages. Assume independence across patients and sites. For incidence: Poisson model aggregating counts and person-time.


</div>
</details>

<details class="example">
<summary>Example: Reproducibility Controls</summary>
<div class="example-content" markdown="1">


**Fixed seeds:** Data split=42, model init=123, batch shuffle=1000+epoch
**Deterministic mode:** torch.use_deterministic_algorithms(True), cudnn.benchmark=False (slight training slowdown)
**Non-determinism:** Client participation order can introduce minor variance but negligible impact. Log exact participation order each round for traceability.


</div>
</details>

### Evaluation and Success Criteria

**For Modeling:**

<details class="example">
<summary>Example: Metrics</summary>
<div class="example-content" markdown="1">


**Primary:** AUROC averaged across five hospital test sets (threshold-independent, clinically interpretable)
**Secondary:** AUPRC (important for imbalance), sensitivity/specificity at fixed threshold (80% sensitivity target), PPV, Brier score (calibration)
**Success:** Federated AUROC ≥0.80 average, no site <0.75


</div>
</details>

<details class="example">
<summary>Example: Client-Side Evaluation</summary>
<div class="example-content" markdown="1">


Each hospital evaluates final global model on local 2023 test set. Generate: ROC curve, PR curve, confusion matrix at threshold, metrics stratified by age (<65, 65-75, >75), sex, ICU type (medical vs. surgical). Results reported as standardized JSON (aggregated metrics only, no raw predictions). Calibration curve: binned predicted probs vs. observed sepsis rates.


</div>
</details>

<details class="example">
<summary>Example: Comparison to Centralized Baseline</summary>
<div class="example-content" markdown="1">


Best federated model (FedAvgM, AUROC 0.81±0.03 across five hospitals) vs. centralized MIMIC-III baseline (AUROC 0.83). Federated slightly worse (Δ=-0.02), could be data heterogeneity or privacy-preservation cost. However, MIMIC-III model on Amsterdam UMC test achieves only 0.76, suggesting federated generalizes better despite small MIMIC-III gap. Demonstrates value of diverse multi-site training.


</div>
</details>

<details class="example">
<summary>Example: Calibration & Thresholds</summary>
<div class="example-content" markdown="1">


Threshold for 80% sensitivity averaged across sites (high recall since missing sepsis is dangerous): predicted probability ~0.18 (lower than 0.5 due to imbalance). Calibration plots: 10 bins, mean predicted prob vs. observed rate. Global model moderately well-calibrated but slightly overconfident at Barcelona (lower baseline incidence). May apply Platt/temperature scaling per site for deployment.


</div>
</details>

<details class="example">
<summary>Example: Runtime & Cost</summary>
<div class="example-content" markdown="1">


68 rounds (early stop vs. planned 100). Total: 9 weeks (Saturday nights, ~6h/round). Cost: ~€1,200 (€150/month×2 for Azure + ~€500 electricity across five GPUs). Communication: ~50 GB total (45MB model × 2 directions × 5 clients × 68 rounds). Negligible vs. ~500 TB raw EHR for centralized.


</div>
</details>

<details class="example">
<summary>Example: Fairness & Subgroup Analysis</summary>
<div class="example-content" markdown="1">


**Age:** Worse in >75 years (AUROC 0.76 vs. 0.82 younger), likely due to comorbidities and atypical presentations
**Sex:** Slight drop in females (0.79 vs. 0.82 males), may reflect historical underrepresentation or biological differences
**Site:** Range 0.77-0.85; surgical ICU site (Barcelona) lower, possibly different risk factors post-op vs. medical
**ICU type:** No significant difference after site adjustment; site-specific factors (data quality, coding) matter more

**Implication:** If deployed, may need site-specific recalibration; use cautiously in elderly and female patients until further validation.


</div>
</details>

**For Analytics:**

<details class="example">
<summary>Example: Analytics Evaluation</summary>
<div class="example-content" markdown="1">


**Accuracy:** Federated mean time-to-sepsis vs. MIMIC-III ground truth: 38.2h (SE 1.4) vs. 38.5h. Bias <1%, variance slightly higher due to heterogeneity but acceptable.

**Coverage:** 95% CIs for federated incidence rate covered true MIMIC-III rate 94% of time in 100 bootstrap runs (near nominal).

**Sensitivity:** Tested imputation strategies (site median, global median, exclude missing). Mean time-to-sepsis varied <5% (37.1-39.3h), robust. Incidence more sensitive when excluding missing lactate (12%→10%), reflects selection bias.

**Robustness:** Leave-one-site-out: incidence 11.2% (w/o Barcelona) to 12.6% (w/o Paris). No single site dominates. Equal weighting vs. sample-size weighting: 12.0%→11.5%, minor difference.


</div>
</details>

---

## 🔒 Phase 6: Privacy, Security & Risk

### Threat Model

<details class="example">
<summary>📝 Example</summary>
<div class="example-content" markdown="1">


**Three scenarios:**

1. **Honest-but-curious server:** Coordinating university follows protocol but might try inferring patient info from model updates. *Defense:* Aggregation across multiple clients; analysis ensuring no single patient dominates gradients.

2. **External attacker:** Intercepts traffic or compromises server. *Defense:* TLS encryption, authentication, firewall rules.

3. **Malicious client:** Compromised hospital sends poisoned updates to degrade model or inject backdoors. *Defense:* Outlier detection on uploaded weights (flag L2 norm >3 SD from median, exclude).

**Not defended:** Insider threats (hospital staff extracting local data) governed by institutional access controls.

**Attack vectors of concern:** Membership inference (can adversary determine if specific patient in training?), model inversion (reconstruct features from gradients?). No formal defenses beyond aggregation (limits leakage but no provable guarantees).


</div>
</details>

### Controls in Use

<details class="example">
<summary>📝 Example</summary>
<div class="example-content" markdown="1">


1. **Encryption in transit:** TLS 1.3 client-server
2. **Authentication:** API tokens (256-bit), quarterly rotation
3. **Encryption at rest:** Hospital drives encrypted (IT managed); server artifacts on Azure Blob with AES-256, access keys restricted to project leads
4. **Access logging:** All API calls with timestamps + client IDs, retained 2 years, monthly review
5. **Outlier detection:** Anomalous model update norms flagged and excluded
6. **Aggregation privacy:** ≥3 clients combined before storing/sharing (harder to isolate individual contributions)
7. **Small cell suppression:** Aggregated stats suppress counts <5 before public release

**NOT used:** Secure MPC (too complex), differential privacy (noise would degrade below clinical utility AUROC <0.75; ethics based on aggregation not formal DP), trusted execution environments (unavailable on all hardware).


</div>
</details>

### Privacy Budget Accounting

<details class="example">
<summary>📝 Example</summary>
<div class="example-content" markdown="1">


Not applicable. We don't use formal DP. If added in future: track epsilon across all rounds/queries using Rényi DP accountant (tighter bounds), set project budget (e.g., ε=10), stop when exhausted.


</div>
</details>

### Simulation-Specific Notes

<details class="example">
<summary>📝 Example</summary>
<div class="example-content" markdown="1">


In simulation (MIMIC-III on single server), five virtual clients share physical machine so traditional network attacks unrealistic. Focus: validating aggregation logic doesn't leak across virtual clients (e.g., client A can't access client B's data directory). Threat model primarily algorithmic privacy (gradient analysis, membership inference on aggregated updates) not network security.

**Phase 2 (live hospitals):** New threats emerge: network interception, firewall traversal, hospital IT insiders, compromised client in different jurisdiction. Will add: stricter access controls, hospital security audits, potentially hardware trusted execution if budget allows. Simulation doesn't model regulatory compliance risks (GDPR breach notification timelines) critical in production.


</div>
</details>

### Incident Response

<details class="example">
<summary>📝 Example</summary>
<div class="example-content" markdown="1">


**Security Lead:** Dr. Hans Müller (hans.mueller@hospital.de, +49-xxx-xxxx)
**DPO:** Maria Schneider (dpo@charite.de)

**Procedure:**
1. Suspected breach/incident detected → notify security lead immediately (phone + email)
2. Pause federation (server stops accepting rounds)
3. Notify affected hospitals within 24h
4. Investigation: review logs, check exfiltration, assess scope
5. If patient data compromised: GDPR breach notification to authorities within 72h
6. Remediation: rotate keys, patch vulnerabilities, potentially discard compromised checkpoints
7. Post-incident review and protocol update

**Fallback:** If server compromised beyond recovery, restart from clean server using last validated checkpoint from offline backup (Azure Blob immutable storage, 30-day retention).


</div>
</details>

---

## 📚 Phase 7: Reproducibility & Sharing

### Code and Environment

<details class="example">
<summary>📝 Example</summary>
<div class="example-content" markdown="1">


**Repository:** https://github.com/eu-sepsis-fl/federated-sepsis-prediction (Apache 2.0)
**Release:** v1.0.2 (commit: a3f5d91c)
**Includes:** FL scripts (Flower client/server), preprocessing, architectures, eval notebooks, configs
**CI/CD:** GitHub Actions automated tests

**Environment:**
- Python 3.10.8, PyTorch 2.0.1, Flower 1.5.0, NumPy 1.24.3, Pandas 2.0.1, Scikit-learn 1.2.2
- Ubuntu 22.04 LTS
- Docker image: eu-sepsis-fl:v1.0.2 (Docker Hub)
- Conda: environment.yml provided

**Reproducibility:** Bit-identical on same hardware with seeds. Different GPUs may vary in 4th decimal (hardware floating-point) but AUROC stable within ±0.001.


</div>
</details>

### Data Availability

<details class="example">
<summary>📝 Example</summary>
<div class="example-content" markdown="1">


**Public (simulation):** MIMIC-III v1.4 via PhysioNet. Access: (1) CITI training, (2) sign data use agreement, (3) request at https://physionet.org/content/mimiciii/ (approval 1-2 weeks, free).

**Restricted (live hospitals):** Cannot share due to GDPR. Researchers can contact consortium lead (elena.schmidt@charite.de) for collaboration and DUA templates.

**Synthetic:** Provide synth_sepsis_data.py generating mock ICU time-series with similar stats (sample sizes, distributions, sepsis prevalence) but no real patient info. For code testing and method development.


</div>
</details>

### Artifacts

<details class="example">
<summary>📝 Example</summary>
<div class="example-content" markdown="1">


**Will release:**
1. Config files (YAML) with hyperparameters, data paths, federation settings
2. MIMIC-III simulation model weights (PyTorch .pth, CC-BY-4.0)
3. Live hospital model weights: NOT released (governance), but share final metrics (AUROC, confusion matrices, calibration) as JSON/CSV
4. Figures/tables: vector graphics (SVG, PDF)
5. Preprocessing scripts with detailed comments
6. Jupyter notebooks for evaluation/visualization

**Archive:** Zenodo DOI: 10.5281/zenodo.xxxxxxx (assigned upon publication, 20-year retention)
**Experiment Tracking:** MLflow server https://mlflow.eu-sepsis-fl.org (password-protected for consortium, read-only public post-publication)
**Version Control:** DVC integrated with Git for datasets/large model files, Azure Blob remote


</div>
</details>

### Known Limitations

<details class="example">
<summary>📝 Example</summary>
<div class="example-content" markdown="1">


1. **Simulation vs. reality:** MIMIC-III results may not generalize to European hospitals (different populations, practices, EHRs)
2. **Incomplete data:** Procalcitonin 40% missing may bias detection; imputation pragmatic but unvalidated
3. **Temporal drift:** 2023 test set; performance may degrade over time (ICU protocols, resistance patterns, demographics change)
4. **Label quality:** Sepsis-3 relies on structured EHR fields potentially documented inconsistently or delayed
5. **No external validation:** Haven't tested outside consortium
6. **Fairness:** Lower performance in elderly and women; deployment should account for this or await additional validation
7. **Unvalidated assumption:** Assume sites correctly implement preprocessing; no site visits/audits to verify Phase 2 data quality


</div>
</details>

---

## 🚀 Phase 8: Deployment & Maturity

### Intended Use and Operationalization

<details class="example">
<summary>Example: Deployment Target</summary>
<div class="example-content" markdown="1">


**Intended use (TRL 4-6, not deployed):** Integration into hospital ICU monitoring as real-time clinical decision support. Would run in background, analyze vital signs/labs hourly, alert when sepsis risk exceeds threshold (pred prob >0.18). Alerts on EHR dashboards, potentially pager notifications.

**Still proof-of-concept. Deployment requires:**
1. Engagement with clinical informatics to design alert workflows (avoid alarm fatigue)
2. Partnership with EHR vendors (Epic, Metavision) for integration
3. Prospective validation where clinicians use alerts, measure impact (time to antibiotics, mortality)
4. Regulatory review (medical device? CE mark or FDA?)
5. Hospital IT security and medical device committee approvals

**No deployment owner yet.** Discussions with ICU medical directors at Charité and Amsterdam UMC for silent trial (model runs, alerts logged not shown, assess feasibility).


</div>
</details>

<details class="example">
<summary>Example: Monitoring for Drift (Planned)</summary>
<div class="example-content" markdown="1">


Once deployed:
1. **Feature distributions:** Monthly Kolmogorov-Smirnov tests vs. training dist; flag if p<0.01 for >3 months (data drift)
2. **Predictions:** Log mean daily sepsis probability; alert if deviates >20% from baseline (population shift or data quality issues)
3. **Performance:** Monthly AUROC on recent cases (retrospective labels); trigger retraining review if <0.75
4. **Label drift:** Monitor incidence; if significant change (e.g., 12%→8%), investigate practice changes (new screening protocol?) or missing cases

Dashboard reviewed monthly by clinical and technical teams.


</div>
</details>

<details class="example">
<summary>Example: Update & Retraining Policy</summary>
<div class="example-content" markdown="1">


**Quarterly retraining** using federated learning on new 3-month data from each hospital. Validate on held-out test, compare to current production; deploy update only if AUROC improves >0.02 or stays within 0.01 (avoid degradation).

**Event-driven retraining if:**
1. Major guideline change (revised sepsis criteria)
2. New biomarkers or EHR fields introduced
3. Significant drift detected

Archive all versions for 5 years (allow rollback).


</div>
</details>

<details class="example">
<summary>Example: Site Playbooks & Training</summary>
<div class="example-content" markdown="1">


Created 25-page operations manual (English, German, French, Spanish):
1. Client install and config (step-by-step with screenshots)
2. Run preprocessing pipeline and QA
3. Troubleshoot common issues (firewall blocks, GPU OOM, schema mismatches)
4. Interpret local metrics and calibration curves
5. Incident reporting

Two remote training sessions (2h each, Zoom, recorded). Each hospital has designated lead who attended in-person 2-day workshop in Berlin. Ongoing support: shared Slack channel, monthly office hours.


</div>
</details>

<details class="example">
<summary>Example: Sunset Plan</summary>
<div class="example-content" markdown="1">


**Decommission if:**
1. Consortium dissolves or loses funding (EU grant ends Dec 2025, no renewal)
2. Performance degrades below clinical threshold despite retraining
3. Superior alternative emerges (e.g., centralized EU health data space permits pooled analysis)
4. Regulatory prohibition due to safety concerns

**Upon decommissioning:** Archive model checkpoints/logs 10 years (EU guidelines), then secure delete. Local hospital data unaffected (under hospital control). GitHub and Zenodo artifacts remain public indefinitely.

**Rollback if deployed and harmful:** Immediately disable alerts, notify all sites within 24h, root cause investigation before resuming or permanent retirement.


</div>
</details>

### Technology Readiness Level

<details class="example">
<summary>Example: TRL Assessment</summary>
<div class="example-content" markdown="1">


**Claimed: TRL 5-6** (technology validated in relevant environment, approaching pilot)

**Justification:** Successfully demonstrated FL on MIMIC-III simulation (TRL 4), completed initial testing with two live hospitals on historical data (TRL 5). Model achieves clinical performance (AUROC 0.81), established governance, DSAs, technical infrastructure. Have NOT: conducted prospective clinical trial, integrated into live EHRs (TRL 7-8), obtained regulatory clearance or routine operational use (TRL 9).

**Evidence:**
1. Peer-review publication in *J Critical Care Med* (submitted, under review): simulation and pilot
2. Technical report on FL infrastructure and security audit (project website)
3. DSAs signed and approved by all five hospital ethics committees
4. Pilot with Charité and Amsterdam UMC: 68 rounds over 9 weeks, no major failures
5. Positive ICU physician feedback at pilot sites (informal)
6. Presented at European Society of Intensive Care Medicine (Sept 2024, 150+ attendees)

**Gaps to TRL 7:**
1. **Prospective silent trial:** Deploy in 2-3 hospitals generating real-time predictions (blinded clinicians). Run 6 months, assess stability, drift, feasibility.
2. **EHR integration:** Build alert interfaces, test interoperability with vendors
3. **Regulatory pathway:** Consult EU MDR and Notified Bodies (likely Class IIa device, what evidence for CE mark?)
4. **User acceptance testing:** Structured interviews/usability studies with ICU nurses and physicians, refine alerts, avoid alarm fatigue
5. **Clinical impact study:** RCT comparing sepsis outcomes (time to treatment, mortality) in ICUs with alerts vs. standard care
6. **Scale to all five sites:** Currently only two in Phase 2; onboard remaining three

Timeline to TRL 7: 18-24 months. Cost: ~€500K (personnel, compute, RCT coordination).

**Target deployment (5-10 years):** Scale to 50+ ICUs across Europe, continuously learning sepsis prediction network. Hospitals contribute local data via FL, benefit from model trained on diverse populations. Each gets customized global model, optionally fine-tuned locally. Support multiple tasks beyond sepsis (AKI, respiratory failure, delirium). Envision EHDS integration once frameworks mature, potential commercialization via spin-off or EHR vendor licensing. Success: tens of thousands of patients benefiting from earlier detection, measurable mortality reduction, replicable privacy-preserving collaborative ML model for healthcare.


</div>
</details>

### Lessons Learned

<details class="example">
<summary>Example: What Worked & What Surprised Us</summary>
<div class="example-content" markdown="1">


**Worked well:**
1. Starting with MIMIC-III simulation was clutch. Could debug algorithms, test infrastructure, train team without five-hospital coordination headaches.
2. Data harmonization upfront (OMOP mapping, shared preprocessing) painful initially but saved months later.
3. Weekly video calls kept everyone aligned and built real trust across consortium.
4. Using Flower framework instead of custom code: huge time-saver.

**Surprised us:**
1. Holy cow, data use agreements took 6+ months longer than budgeted. Ethics committees had never seen federated learning and we basically taught them.
2. Hospital firewalls way more painful than expected. Two sites needed months of IT back-and-forth just for outbound HTTPS.
3. Model performance varied way more across sites (AUROC 0.77-0.85) than expected. Really can't validate at one site and call it done.
4. Clinicians super excited but some had totally unrealistic deployment timelines. Constant communication to manage expectations.

**Would do differently:**
1. Start ethics/legal a full year earlier, honestly.
2. Budget way more for hospital IT coordination. Not just technical, it's a people problem.
3. Plan hybrid simulation-to-live from day one instead of figuring out halfway.
4. Get ICU nurses involved earlier, not just physicians. They'll actually use the alerts.


</div>
</details>

<details class="example">
<summary>Example: Key Decisions & Rationale</summary>
<div class="example-content" markdown="1">


**Decision 1: Centralized star topology** (vs. peer-to-peer/hierarchical)
*Why:* Way simpler to implement, easier past ethics (no hospital-to-hospital communication), good enough for our needs. Downside: single point of failure but covered with checkpoint backups; model small enough bandwidth isn't an issue.

**Decision 2: Skip differential privacy** (for now)
*Why:* DP noise would probably tank model below clinical utility (AUROC <0.75). Ethics approvals based on aggregation privacy not formal DP. Maybe revisit if better DP methods emerge.

**Decision 3: Temporal splits** (not random)
*Why:* Absolutely essential to avoid time-series leakage. Non-negotiable.

**Decision 4: LSTM architecture** (not Transformers/gradient boosting)
*Why:* Best balance of performance and what hardware could handle. Transformers ate way too much GPU memory; tree methods didn't click with time-series.

**Decision 5: Quarterly retraining** (not continuous)
*Why:* Keeps model reasonably fresh without requiring 24/7 infrastructure hospitals can't guarantee.


</div>
</details>

<details class="example">
<summary>Example: Next Steps to Raise TRL</summary>
<div class="example-content" markdown="1">


**Immediate (6 months):**
1. Submit EU Horizon Europe Phase 2 grant (€2M, deadline Feb 2025)
2. Publish main results (under review)
3. Onboard remaining three hospitals to live federation (complete Phase 2)
4. Begin regulatory consult with Notified Body (MDR pathway)
5. Design silent trial protocol, submit to ethics

**Medium-term (12-18 months):**
6. Launch silent trial at two pilots
7. User acceptance testing with ICU staff (n=20 clinicians)
8. Build EHR integration prototypes (Epic, Metavision)
9. Present at major conferences (ESICM, SCCM) for visibility

**Long-term (2-3 years):**
10. If silent trial succeeds: RCT measuring patient outcomes (n=5000 patients, five sites)
11. Seek CE mark if required
12. Publish RCT results
13. Explore commercialization or open-source strategy
14. Scale to more hospitals (target: 15 sites by 2027)


</div>
</details>

---

## Appendix: Changes from Template v1.1

**Added fields:**
- Governance: "Ethics status" for public datasets, secondary analysis, N/A cases
- Data landscape: "Federation mode" (simulated/live/hybrid) with simulation guidance
- Infrastructure: Explicit simulation environment description
- Computation: Request for centralized baselines in modeling
- Evaluation: "Comparison to centralized baseline" to quantify privacy trade-offs
- Privacy: "Simulation-specific notes" distinguishing current vs. future threat models
- Reproducibility: "Data availability" (public/restricted/synthetic)
- Operationalization: "Intended use case" for proof-of-concept without deployment owner

**Clarified language:**
- Scope: "Population and setting" explicitly includes non-clinical subjects (sensors, data sources)
- Evaluation: "Fairness and subgroup checks" includes non-demographic subgroups (per-site, per-outcome, etc.)
- Throughout: Added simulation considerations for early-stage work

**Structure improvements:**
- Reorganized around **8 lifecycle phases** (vs. 14 flat sections)
- Added visual phase markers to show progression
- Collapsed related content for better flow
- Contextual section notes explain purpose
- Global example toggle for cleaner reading

**Design principles preserved from v1.1:**
- Prose-first approach (minimize bullets in completed examples)
- Separation of governance (policy) from privacy/security (technical controls)
- Explicit TRL assessment with gap analysis
- Reproducibility focus with artifact tracking
