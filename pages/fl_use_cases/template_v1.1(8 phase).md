---
version: 1.1
search_exclude: false
toc: true
title: Federated Analytics Life Cycle Template
description: Document your federated analytics project from conception to deployment
---

<style>
/* Info Box */
.info-box {
  background: linear-gradient(to right, #e3f2fd, #f0f4ff);
  border-left: 5px solid #1976d2;
  padding: 20px 25px;
  margin: 25px 0;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0,0,0,0.05);
}

/* Phase Headers */
h2 {
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
}

details.example summary:hover {
  background: linear-gradient(to right, #eef2ff, #f8f9ff);
  color: #4338ca;
}

details.example[open] summary {
  background: linear-gradient(to right, #eef2ff, #f5f3ff);
  border-bottom: 2px solid #e5e7eb;
  color: #4338ca;
}

/* Example Content */
details.example .example-content {
  padding: 24px;
  background: #fafbfc;
  line-height: 1.8;
  color: #24292f;
  font-size: 0.95em;
}

details.example .example-content strong {
  color: #1a202c;
  font-weight: 600;
}

details.example .example-content ul,
details.example .example-content ol {
  margin: 12px 0;
  padding-left: 24px;
}

details.example .example-content li {
  margin: 8px 0;
}

/* Phase Introduction Box */
.phase-intro {
  background: linear-gradient(to right, #f8f9ff, #faf8ff);
  border-left: 5px solid #9333ea;
  padding: 20px 24px;
  margin: 20px 0 30px 0;
  border-radius: 6px;
  box-shadow: 0 1px 3px rgba(147, 51, 234, 0.1);
  font-size: 1.05em;
  line-height: 1.7;
}

/* Phase metadata items */
.phase-meta {
  background: #ffffff;
  border: 1px solid #e5e7eb;
  border-radius: 8px;
  padding: 20px;
  margin: 20px 0;
  box-shadow: 0 1px 2px rgba(0,0,0,0.05);
}

.phase-meta-item {
  margin: 16px 0;
  padding-left: 28px;
  position: relative;
}

.phase-meta-item::before {
  position: absolute;
  left: 0;
  font-size: 1.2em;
}

.phase-meta-item.questions::before {
  content: "❓";
}

.phase-meta-item.people::before {
  content: "👥";
}

.phase-meta-item.timeline::before {
  content: "⏱️";
}

.phase-meta-item.mistakes::before {
  content: "⚠️";
}

.phase-meta-item.deliverables::before {
  content: "📦";
}

.phase-meta-item strong {
  color: #6366f1;
  font-size: 0.95em;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

/* Lifecycle connection box */
.lifecycle-note {
  background: linear-gradient(135deg, #fef3c7 0%, #fde68a 100%);
  border-left: 5px solid #f59e0b;
  padding: 20px 24px;
  margin: 25px 0;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(245, 158, 11, 0.1);
}

/* Clean Professional Overview */
.project-overview {
  background: #ffffff;
  border: 1px solid #e2e8f0;
  border-radius: 12px;
  margin: 30px 0 40px 0;
  padding: 0;
  position: relative;
  overflow: hidden;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
}

.overview-intro {
  background: #ffffff;
  margin: 0;
  padding: 30px;
  border-radius: 12px 12px 0 0;
  position: relative;
  z-index: 2;
}

.overview-intro h3 {
  margin: 0 0 16px 0;
  font-size: 1.6em;
  font-weight: 600;
  color: #1e293b;
  border: none;
  padding: 0;
  text-align: left;
}

.overview-intro p {
  margin: 0 0 20px 0;
  font-size: 1em;
  line-height: 1.6;
  color: #4a5568;
  text-align: left;
}

.usage-guidance {
  background: #f8fafc;
  border-radius: 8px;
  padding: 20px;
  margin-top: 0;
  border: 1px solid #e2e8f0;
}

.guidance-item {
  display: flex;
  align-items: flex-start;
  gap: 12px;
  margin-bottom: 16px;
}

.guidance-item:last-child {
  margin-bottom: 0;
}

.guidance-icon {
  font-size: 1.3em;
  flex-shrink: 0;
  margin-top: 2px;
}

.guidance-content h4 {
  margin: 0 0 6px 0;
  font-size: 1em;
  font-weight: 600;
  color: #1e293b;
  line-height: 1.3;
}

.guidance-content p {
  margin: 0;
  font-size: 0.9em;
  line-height: 1.5;
  color: #475569;
}

.guidance-content a {
  color: #667eea;
  text-decoration: none;
  font-weight: 500;
}

.guidance-content a:hover {
  text-decoration: underline;
  color: #5568d3;
}

.inline-toggle-btn {
  background: #667eea;
  color: white;
  border: none;
  padding: 6px 12px;
  border-radius: 4px;
  cursor: pointer;
  font-weight: 500;
  font-size: 0.85em;
  display: inline-block;
  margin: 0 4px;
}

.tldr-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
  margin: 0 30px 30px 30px;
  position: relative;
  z-index: 2;
}

@media (max-width: 1200px) {
  .tldr-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 768px) {
  .tldr-grid {
    grid-template-columns: 1fr;
  }
}

.tldr-phase {
  background: #ffffff;
  border-radius: 8px;
  padding: 20px;
  border: 1px solid #e2e8f0;
  cursor: pointer;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
}

.tldr-phase-number {
  font-weight: 600;
  color: #667eea;
  font-size: 0.85em;
  margin-bottom: 8px;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

.tldr-phase-title {
  font-weight: 600;
  color: #1e293b;
  margin-bottom: 12px;
  font-size: 1.1em;
  line-height: 1.4;
}

.tldr-phase-desc {
  color: #64748b;
  font-size: 0.9em;
  line-height: 1.5;
  margin-bottom: 0;
  font-weight: 400;
}

.tldr-quick-links {
  background: #ffffff;
  border-radius: 8px;
  padding: 24px;
  margin: 0 30px 30px 30px;
  border: 1px solid #e2e8f0;
  position: relative;
  z-index: 2;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
}

.tldr-quick-links h4 {
  margin: 0 0 24px 0;
  color: #1e293b;
  font-size: 1.2em;
  font-weight: 600;
  text-align: center;
}

.tldr-links-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
  gap: 16px;
}

.tldr-link {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  padding: 8px 12px;
  background: #f1f5f9;
  border-radius: 4px;
  text-decoration: none;
  color: #334155;
  font-size: 0.85em;
  font-weight: 500;
  border: 1px solid #cbd5e1;
  text-align: center;
}

/* Phase Details - Collapsible */
.phase-details {
  margin: 30px 0;
  border: 1px solid #e1e4e8;
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 1px 3px rgba(0,0,0,0.06);
}

.phase-header {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white !important;
  padding: 16px 24px;
  margin: 0;
  font-weight: 600;
  font-size: 1.5em;
  border-radius: 0;
  box-shadow: none;
  border: none;
  cursor: pointer;
  user-select: none;
  transition: all 0.2s ease;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.phase-header:hover {
  background: linear-gradient(135deg, #5a67d8 0%, #6b46c1 100%);
}

.phase-header::after {
  content: "▼";
  font-size: 0.8em;
  transition: transform 0.3s ease;
  opacity: 0.8;
}

.phase-details[open] .phase-header::after {
  transform: rotate(180deg);
}

.phase-details .phase-intro,
.phase-details .phase-meta,
.phase-details h3,
.phase-details h4,
.phase-details details.example {
  margin-left: 0;
  margin-right: 0;
}

/* Override h2 styling inside phase details */
.phase-details h2 {
  background: none !important;
  color: inherit !important;
  padding: 0 !important;
  margin: 0 !important;
  font-weight: inherit !important;
  font-size: inherit !important;
  border-radius: 0 !important;
  box-shadow: none !important;
  border: none !important;
}

/* Smooth scrolling for anchor links */
html {
  scroll-behavior: smooth;
}

/* Phase content styling */
.phase-details .phase-content {
  padding: 20px 24px;
}

/* Better spacing for phase sections */
.phase-details h3 {
  margin-top: 30px;
  margin-bottom: 15px;
  color: #2d3748;
  font-size: 1.3em;
  font-weight: 600;
}

.phase-details h4 {
  margin-top: 20px;
  margin-bottom: 10px;
  color: #4a5568;
  font-size: 1.1em;
  font-weight: 600;
}
</style>

<div class="project-overview">

  <div class="overview-intro">
    <p>This comprehensive template guides you through <strong>eight essential phases</strong> that follow the natural progression of a federated analytics project, from initial planning and stakeholder alignment to deployment and long-term sustainability. Each phase includes detailed guidance, real-world examples, and best practices for conducting reproducible, transparent, and ethically sound federated analytics research.</p>

    <div class="usage-guidance">
      <div class="guidance-item">
        <div class="guidance-content">
          <h4>💡 How to use this template</h4>
          <p>Read each section's guidance text carefully, it explains what to document and why it matters for your project's success. Click on the expandable examples to see how each section was completed in a real published study {% cite Pirmani2025-sd %}.</p>
        </div>
      </div>

      <div class="guidance-item">
        <div class="guidance-content">
          <h4>🗺️ Navigation</h4>
          <p>Click any phase card below to jump directly to that section, or use the quick reference links for specific topics. The <button onclick="toggleAllExamples()" id="toggleBtn" class="inline-toggle-btn">✨ Show All Examples</button> button expands all real-world examples at once for comprehensive reference.</p>
        </div>
      </div>

      <div class="guidance-item">
        <div class="guidance-content">
          <h4>🔗 FL Lifecycle alignment</h4>
          <p>These phases align with the standard <a href="/fl_life_cycle">Federated Learning Lifecycle</a>, providing detailed, actionable steps for each lifecycle stage while maintaining scientific rigor and practical applicability.</p>
        </div>
      </div>
    </div>

  </div>

    <div class="tldr-grid">
      <div class="tldr-phase" onclick="document.querySelector('#phase1').scrollIntoView({behavior: 'smooth'})">
        <div class="tldr-phase-number">🎯 Phase 1</div>
        <div class="tldr-phase-title">Planning & Scoping</div>
        <div class="tldr-phase-desc">Define the problem, justify federation, set clear objectives and scope boundaries</div>
      </div>

      <div class="tldr-phase" onclick="document.querySelector('#phase2').scrollIntoView({behavior: 'smooth'})">
        <div class="tldr-phase-number">⚖️ Phase 2</div>
        <div class="tldr-phase-title">Governance & Ethics</div>
        <div class="tldr-phase-desc">Establish legal frameworks, ethics approvals, stakeholder roles, and publication policies</div>
      </div>

      <div class="tldr-phase" onclick="document.querySelector('#phase3').scrollIntoView({behavior: 'smooth'})">
        <div class="tldr-phase-number">🗂️ Phase 3</div>
        <div class="tldr-phase-title">Data & Standards</div>
        <div class="tldr-phase-desc">Characterize data sources, define clients, assess quality, and harmonization needs</div>
      </div>

      <div class="tldr-phase" onclick="document.querySelector('#phase4').scrollIntoView({behavior: 'smooth'})">
        <div class="tldr-phase-number">🔧 Phase 4</div>
        <div class="tldr-phase-title">Preparation & Infrastructure</div>
        <div class="tldr-phase-desc">Set up data pipelines, federation infrastructure, and technical architecture</div>
      </div>

      <div class="tldr-phase" onclick="document.querySelector('#phase5').scrollIntoView({behavior: 'smooth'})">
        <div class="tldr-phase-number">🧬 Phase 5</div>
        <div class="tldr-phase-title">Development & Training</div>
        <div class="tldr-phase-desc">Design algorithms, train models, evaluate performance, and compare baselines</div>
      </div>

      <div class="tldr-phase" onclick="document.querySelector('#phase6').scrollIntoView({behavior: 'smooth'})">
        <div class="tldr-phase-number">🔒 Phase 6</div>
        <div class="tldr-phase-title">Privacy & Security</div>
        <div class="tldr-phase-desc">Threat modeling, implement safeguards, assess risks, and document controls</div>
      </div>

      <div class="tldr-phase" onclick="document.querySelector('#phase7').scrollIntoView({behavior: 'smooth'})">
        <div class="tldr-phase-number">📚 Phase 7</div>
        <div class="tldr-phase-title">Reproducibility & Sharing</div>
        <div class="tldr-phase-desc">Document code, environment, data access, and enable validation by others</div>
      </div>

      <div class="tldr-phase" onclick="document.querySelector('#phase8').scrollIntoView({behavior: 'smooth'})">
        <div class="tldr-phase-number">🚀 Phase 8</div>
        <div class="tldr-phase-title">Maturity Assessment</div>
        <div class="tldr-phase-desc">Assess TRL, plan deployment, document lessons learned, and next steps</div>
      </div>
    </div>

    <div class="tldr-quick-links">
      <h4>🔗 Quick Reference Links</h4>
      <div class="tldr-links-grid">
        <a href="#phase1" class="tldr-link">Problem Definition</a>
        <a href="#phase2" class="tldr-link">Ethics Approval</a>
        <a href="#phase3" class="tldr-link">Data Inventory</a>
        <a href="#phase4" class="tldr-link">Infrastructure Setup</a>
        <a href="#phase5" class="tldr-link">Algorithm Design</a>
        <a href="#phase6" class="tldr-link">Threat Model</a>
        <a href="#phase7" class="tldr-link">Code Repository</a>
        <a href="#phase8" class="tldr-link">TRL Assessment</a>
        <a href="#appendix" class="tldr-link">Version Changes</a>
        <a href="#bibliography" class="tldr-link">References</a>
      </div>
    </div>

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

// Simple smooth scroll for anchor links
document.addEventListener('DOMContentLoaded', function() {
  document.querySelectorAll('a[href^="#"]').forEach(anchor => {
    anchor.addEventListener('click', function (e) {
      e.preventDefault();
      const target = document.querySelector(this.getAttribute('href'));
      if (target) {
        target.scrollIntoView({ behavior: 'smooth' });
      }
    });
  });
});
</script>

---

<h2 class="phase-header" id="phase1">
🎯 Phase 1: Planning & Scoping
</h2>

<div class="phase-intro" markdown="1">
<strong>This is where everything begins.</strong> Before writing code or contacting potential partners, you need crystal-clear answers to fundamental questions: What problem are we solving? Why does it matter? Why can't we just pool data centrally? What exactly will we deliver, and what's out of scope?
</div>

<div class="phase-meta" markdown="1">

<div class="phase-meta-item questions">
<strong>Key Questions:</strong> What specific clinical, scientific, or operational gap are you filling? Who benefits (patients, researchers, policymakers)? Why is federated analytics necessary rather than just preferable? What does success look like concretely? What assumptions underpin your approach, and how will you validate them?
</div>

<div class="phase-meta-item people">
<strong>Who's Involved:</strong> Principal investigators and domain experts define the problem and objectives. Legal and compliance officers identify regulatory barriers to centralization. Project managers establish scope boundaries and timelines. Funding agencies assess whether problem justifies resources.
</div>

<div class="phase-meta-item timeline">
<strong>Timeline:</strong> Initial scoping: First couple of weeks of stakeholder discussions and literature review. Refinement happens throughout project as you learn more, but major scope changes after Phase 3 are costly.
</div>

<div class="phase-meta-item mistakes">
<strong>Common Mistakes:</strong> Vague problem statements ("improve healthcare"), unrealistic objectives (overpromising performance), weak federation justification (could actually centralize with proper agreements), hidden assumptions that blow up later (assuming all sites have same data quality).
</div>

<div class="phase-meta-item deliverables">
<strong>Deliverables:</strong> One-page project summary, stakeholder roster with commitments, explicit list of in-scope and out-of-scope deliverables, documented assumptions with validation plan.
</div>

</div>

### Problem and Domain

**What to document:** Describe the clinical, scientific, or operational challenge you're addressing in plain language. What gap in knowledge or capability are you filling? Who will benefit from solving this problem?

**Why it matters:** A clear problem statement aligns stakeholders, justifies resource allocation, and helps readers quickly assess whether your approach is relevant to their context.

<details class="example">
<summary>📝 Example from FL-MS Study (Pirmani et al., 2025)</summary>
<div class="example-content" markdown="1">

Early prediction of disability progression in multiple sclerosis (MS) remains challenging despite its critical importance for therapeutic decision-making. MS affects millions of people worldwide, with each patient experiencing unique disease progressions and varying responses to treatment. The primary challenge lies in capturing this heterogeneity to enable personalized, data-driven treatment strategies. While machine learning shows promise for improving our understanding of MS progression and predicting individual treatment responses, developing advanced ML models remains constrained by limited access to large-scale, high-quality datasets. Although MS impacts an estimated 2.8 million individuals globally, clinical data needed for precision modeling remain fragmented and siloed across healthcare institutions.

</div>
</details>

### Why Federated Analytics?

**What to document:** Explain the specific barriers preventing centralized data pooling. These might be regulatory (GDPR, HIPAA), institutional policy, data ownership concerns, trust issues between organizations, technical infrastructure limitations, or competitive considerations.

**Why it matters:** Stakeholders need to understand why you can't simply pool data in one place. This justification is crucial for funding proposals, ethics applications, and convincing institutions to participate in your federation.

<details class="example">
<summary>📝 Example from FL-MS Study</summary>
<div class="example-content" markdown="1">

Aggregating MS clinical data across international institutions is complicated by legitimate but complex regulatory constraints (GDPR, national health data laws), data ownership concerns, and inconsistent data quality standards. Healthcare institutions are reluctant to share raw patient records due to privacy regulations, competitive concerns, and liability fears. Federated learning offers a decentralized learning paradigm that enables training ML models while preserving data localization, strongly aligned with data privacy and protection standards. This approach allows collaborative model development without requiring data centralization.

</div>
</details>

### Primary Objective

**What to document:** State your single most important goal in concrete, measurable terms. Be specific about what success looks like. Examples: "Train a prognostic model achieving AUROC ≥0.80" or "Estimate treatment effect heterogeneity across 20 sites with 95% confidence intervals."

**Why it matters:** A well-defined objective guides all downstream decisions (choice of algorithms, evaluation metrics, success criteria) and prevents scope creep.

<details class="example">
<summary>📝 Example from FL-MS Study</summary>
<div class="example-content" markdown="1">

Assess whether personalized federated learning can match or exceed centralized model performance in predicting 2-year disability progression in multiple sclerosis patients, while maintaining data localization and privacy. Success defined as achieving comparable ROC-AUC to centralized baseline (~0.81) using federated approaches across 32 international sites.

</div>
</details>

### Population and Setting

**What to document:** Describe your data subjects or sources. For clinical studies: patient populations, inclusion/exclusion criteria, geographic and temporal scope. For other domains: IoT devices, sensor networks, administrative databases, etc.

**Why it matters:** Clear population definition ensures reproducibility and helps readers assess generalizability to their own settings.

<details class="example">
<summary>📝 Example from FL-MS Study</summary>
<div class="example-content" markdown="1">

Patients with relapsing or progressive multiple sclerosis drawn from the MSBase international registry, spanning 32 countries. Inclusion criteria: age over 18 years, MS or clinically isolated syndrome diagnosis, minimum 12-month follow-up, at least three EDSS measurements in the 3.25 years before baseline, plus sufficient follow-up to assess two-year outcomes. Final dataset: 283,115 episodes from 26,246 patients collected between [data collection period from registry]. Geographic scope: Global (North America, Europe, Australia, Middle East, others).

</div>
</details>

### Outputs

**What to document:** List all deliverables. For modeling projects: trained models, performance metrics, calibration curves. For analytics: summary statistics, dashboards, reports. For infrastructure: frameworks, APIs, deployment guides.

**Why it matters:** Explicit outputs help manage stakeholder expectations and guide dissemination planning.

<details class="example">
<summary>📝 Example from FL-MS Study</summary>
<div class="example-content" markdown="1">

**Primary outputs:**

- Trained personalized federated learning models for 2-year disability progression prediction
- Novel AdaptiveDualBranchNet architecture designed for personalized FL
- Comparative performance analysis across centralized, federated, and personalized approaches
- Client-specific performance metrics showing improvements for smaller/imbalanced sites

**Secondary outputs:**

- Open-source code repository with preprocessing pipelines and training scripts
- Hyperparameter configurations and training logs
- Published peer-reviewed manuscript (npj Digital Medicine, 2025)

</div>
</details>

### Out of Scope

**What to document:** Explicitly state what this project will NOT address. This prevents misunderstandings and helps focus resources.

**Why it matters:** Saying "no" is as important as saying "yes." Clear boundaries protect project timelines and budgets.

<details class="example">
<summary>📝 Example from FL-MS Study</summary>
<div class="example-content" markdown="1">

This project does not include:

- Real-time clinical decision support integration (offline validation only)
- Exploratory analytics or federated statistics beyond progression prediction
- Imaging data analysis (focused on tabular clinical data only)
- Treatment recommendation systems (prediction only, not prescription)
- Live deployment across hospital IT systems (simulated federation)
- External validation beyond MSBase registry

</div>
</details>

### Assumptions and Constraints

**What to document:** List key assumptions underlying your approach (e.g., "Sites use consistent diagnostic criteria," "Clients remain online during training"). Note technical, organizational, and regulatory constraints. Describe how you'll validate assumptions.

**Why it matters:** Explicit assumptions surface risks early. Constraints help readers assess feasibility in their own contexts.

<details class="example">
<summary>📝 Example from FL-MS Study</summary>
<div class="example-content" markdown="1">

**Key Assumptions:**

- Disability progression can be reliably captured by EDSS scores following published validation criteria
- Site-level data are consistent enough to harmonize into comparable features across 32 countries
- Simulated federation by country approximates real multi-site federation (reasonable for algorithm development)
- Patient episodes are independent observations (appropriate for population-level modeling)

**Constraints:**

- Only registry data from MSBase available (no access to raw hospital EHR systems)
- Clients simulated on centralized infrastructure rather than distributed across live hospital servers (TRL limitation)
- Computational budget limited to Flanders Supercomputer Center resources
- Data use agreement prohibits physical data transfer or splitting across storage locations

**Validation Approach:**

- Assumptions checked against prior MS literature and clinical expert consultation
- Internal validation via 10 repeated runs with different random seeds to assess robustness
- Client-level performance analysis to identify sites where assumptions may be violated

</div>
</details>

---

<h2 class="phase-header" id="phase2">
⚖️ Phase 2: Governance & Ethics
</h2>

<div class="phase-intro" markdown="1">
<strong>Governance can make or break multi-institutional projects.</strong> This phase establishes legal and ethical frameworks, defines decision-making authority, and builds trust among partners. Without solid governance, projects stall in endless negotiations or face ethics violations. Done well, governance becomes your foundation for long-term collaboration.
</div>

<div class="phase-meta" markdown="1">

<div class="phase-meta-item questions">
<strong>Key Questions:</strong> Who approves what decisions? What's the legal basis for processing sensitive data? Which ethics committees need to review this work? How will results be shared and published? What happens if a partner wants to withdraw? How do we handle disputes?
</div>

<div class="phase-meta-item people">
<strong>Who's Involved:</strong> Principal investigators lead consortium building. Legal counsels draft agreements. Ethics committees (IRBs) review protocols. Data protection officers assess GDPR compliance. Institutional signing authorities approve contracts. Patient advocates may review for some clinical projects.
</div>

<div class="phase-meta-item timeline">
<strong>Timeline:</strong> This is often the LONGEST phase (Even it can take up to years). Multi-party agreements take time. Ethics reviews can require multiple rounds of revision. Do NOT underestimate. Start early, often in parallel with Phase 1.
</div>

<div class="phase-meta-item mistakes">
<strong>Common Mistakes:</strong> Underestimating timeline for ethics/legal (budget 6+ months), forgetting to get institutional signing authority approval (not just PI agreement), unclear authorship rules leading to publication conflicts, not documenting data access procedures clearly, skipping data protection impact assessments.
</div>

<div class="phase-meta-item deliverables">
<strong>Deliverables:</strong> Signed consortium agreement or data use agreements, ethics approval letters with reference numbers, documented roles and responsibilities, publication policy document, data access and sharing policy.
</div>

</div>

### Stakeholders and Roles

**What to document:** List all key participants with their roles and responsibilities: principal investigators, data custodians at each site, technical developers, funders, oversight bodies (data safety monitoring boards, steering committees), and end users. Include affiliations and contact information where appropriate.

**Why it matters:** Clear role definition prevents confusion, establishes accountability, and facilitates communication throughout the project lifecycle.

<details class="example">
<summary>📝 Example from FL-MS Study</summary>
<div class="example-content" markdown="1">

**Principal Investigator:** Ashkan Pirmani (KU Leuven - , Belgium)
**Supervisors:** Yves Moreau (KU Leuven), Edward De Brouwer (KU Leuven), Liesbet M. Peeters (Hasselt University & Universitair MS Centrum Pelt)
**Technical Team:** Martijn Oldenhof, Ádám Arany, Antoine Passemiers (KU Leuven), Axel Faes (Hasselt University)
**Data Provider:** MSBase International Registry (coordinated by University of Melbourne)
**MSBase Study Group:** 70+ co-authors representing participating clinics across 32 countries (see full author list in publication)
**Ethics Oversight:** Uhasselt, KU Leuven and Universitait MS Centrum Pelt Social and Societal Ethics Committee
**Compute Provider:** Flanders Supercomputer Center (VSC)
**End Users:** Clinicians managing MS patients, MS researchers developing prognostic tools

</div>
</details>

### Ethics and Approvals

**What to document:** Name all institutional review boards, ethics committees, or data protection impact assessments that reviewed and approved your work. Include approval reference numbers, dates, and key conditions or restrictions.

**Why it matters:** Ethics approval is mandatory for most health research and demonstrates responsible conduct. Reference numbers enable verification and help other researchers navigate similar approval processes.

<details class="example">
<summary>📝 Example from FL-MS Study</summary>
<div class="example-content" markdown="1">

**Hasselt University and KU Leuven PRET (Privacy, Research Ethics and Technology) Approval:** G 2023 6771

**Social and Societal Ethics Committee:** Confirmed GDPR alignment for federated processing of MSBase data

**Data Provider Ethics:** MSBase has existing multi-center ethics framework covering participating sites globally. Individual site approvals managed by MSBase consortium.

**Key Conditions:** All analyses conducted in simulated manner with data remaining on approved computing host (Flanders Supercomputer Center). No physical data transfer or splitting across storage locations.

</div>
</details>

### Ethics Status

**What to document:** Specify your ethics pathway. Choose one: (1) Approved by ethics committee with reference numbers, (2) Waived or exempt with justification (e.g., secondary analysis of de-identified public data), or (3) Not applicable with clear rationale (e.g., purely synthetic benchmarks).

**Why it matters:** Different ethics pathways have different implications for data handling, consent, and dissemination. Being explicit helps readers understand your regulatory context.

<details class="example">
<summary>📝 Example from FL-MS Study</summary>
<div class="example-content" markdown="1">

**Approved by ethics committee.** Hasselt University and KU Leuven granted approval (G 2023 6771) for secondary analysis of de-identified MSBase registry data. The Social and Societal Ethics Committee confirmed the federated simulation approach complies with GDPR. No individual patient consent required for this secondary analysis under European research exception provisions, as data were already collected under MSBase's established multi-center ethics framework with appropriate patient consent at participating sites.

</div>
</details>

### Legal Basis and Agreements

**What to document:** Describe the legal foundation for data processing (GDPR Article citations, HIPAA provisions, institutional policies). List data use agreements, consortium contracts, or memoranda of understanding between participating organizations. Note key terms: data ownership, permitted uses, publication rights, dispute resolution.

**Why it matters:** Legal clarity prevents conflicts and ensures all parties understand their rights and obligations.

<details class="example">
<summary>📝 Example from FL-MS Study</summary>
<div class="example-content" markdown="1">

**GDPR Legal Basis:** Article 6(1)(e) processing necessary for research in public interest + Article 9(2)(j) processing special category health data for scientific research with appropriate safeguards

**Data Use Agreement:** Researchers accessed MSBase harmonized dataset under established agreements between Hasselt University, KU Leuven and MSBase consortium. Agreement specifies: (1) Data remains on approved computing infrastructure (Flanders Supercomputer Center), (2) No data transfer to third parties, (3) Results may be published with appropriate co-authorship acknowledging MSBase contributors, (4) Code must be made openly available.

**Key Terms:** MSBase retains data ownership. Derived models and analysis code belong to research team. Publications require coordination with MSBase steering committee.

</div>
</details>

### Access and Sharing Policy

**What to document:** Specify who can access what. For raw data: controlled access procedures, credentialing requirements. For intermediate artifacts (models, checkpoints): sharing rules. For results: publication policies, embargoes, site-level result disclosure rules.

**Why it matters:** Clear access policies prevent data breaches, manage expectations about data availability for replication, and respect institutional sensitivities.

<details class="example">
<summary>📝 Example from FL-MS Study</summary>
<div class="example-content" markdown="1">

**Raw Data:** MSBase registry data remain under MSBase consortium control. Researchers may request access via formal application to MSBase (www.msbase.org), requiring: (1) Research protocol submission, (2) Ethics approval from home institution, (3) Data use agreement signature, (4) Expected approval timeline 2-6 months.

**Model Weights:** Trained model weights from simulated federation not publicly released (privacy considerations even for aggregate models). Architecture and hyperparameters fully documented.

**Code:** All preprocessing, training, and evaluation code publicly available on GitHub (Apache 2.0 license) to enable reproduction with other datasets.

**Results:** Aggregated performance metrics (ROC-AUC, PR-AUC) across sites publicly reported in publication. Country-level results not individually disclosed without permission from MSBase steering committee.

**Publication Policy:** Manuscript circulated to all MSBase contributing authors 4 weeks before submission per consortium agreement.

</div>
</details>

### Publication and Dissemination

**What to document:** Outline authorship criteria (e.g., ICMJE guidelines), preprint policies, media engagement rules, open access mandates from funders, and timelines for public release of code/models.

**Why it matters:** Publication conflicts can derail multi-institutional collaborations. Explicit policies set expectations and ensure fair credit attribution.

<details class="example">
<summary>📝 Example from FL-MS Study</summary>
<div class="example-content" markdown="1">

**Authorship:** ICMJE guidelines. Lead authors: study conception, implementation, analysis, manuscript writing. MSBase Study Group (70+ co-authors): data contribution and critical review. All authors reviewed and approved final manuscript.

**Journal:** Published in npj Digital Medicine (Nature Portfolio), open access
**License:** Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 (CC BY-NC-ND 4.0)
**Preprint:** Not posted (direct to peer review)
**Code Release:** GitHub repository made public upon manuscript acceptance
**DOI:** https://doi.org/10.1038/s41746-025-01788-8
**Funding Acknowledgment:** Supported by [funding sources listed in publication]

</div>
</details>

---

<h2 class="phase-header" id="phase3">
🗂️ Phase 3: Data & Standards
</h2>

<div class="phase-intro" markdown="1">
<strong>Understanding your data landscape is critical before building any federated system.</strong> This phase characterizes what data exist at each site, how heterogeneous they are across clients, and what standards or harmonization steps are needed to make distributed data semantically comparable.
</div>

<div class="phase-meta" markdown="1">

<div class="phase-meta-item questions">
<strong>Key Questions:</strong> Where does your data live? How many clients will participate? How different are they from each other (data volume, feature distributions, outcome prevalence)? What clinical or technical vocabularies do you need to align? What data quality issues exist?
</div>

<div class="phase-meta-item mistakes">
<strong>Common Mistakes:</strong> Assuming all sites have similar data quality or feature availability, underestimating harmonization effort, ignoring extreme heterogeneity that might make federation infeasible.
</div>

<div class="phase-meta-item deliverables">
<strong>Deliverables:</strong> Client inventory with data volumes, data quality assessment reports from each site, harmonization mapping documents, documented decision on client definition (institution-level, region-level, etc.).
</div>

</div>

### Clients and Data Sources

**What to document:** List all participating data silos (hospitals, clinics, research cohorts, IoT deployments). Provide context on their systems: EHR vendors, data collection protocols, approximate data volumes. Describe how you defined "clients" (by institution, by country, by device type, etc.).

**Why it matters:** Client definition has major implications for privacy, communication overhead, and model personalization strategies. Readers need this context to assess whether your setup applies to their scenario.

<details class="example">
<summary>📝 Example from FL-MS Study</summary>
<div class="example-content" markdown="1">

**Data Source:** MSBase international MS registry, a large prospective observational cohort collecting routine clinical data from MS patients worldwide.

**Client Definition:** Clients defined at country level, resulting in 32 federated sites. This choice balances: (1) Sufficient sample size per client (many countries have 1000+ patients), (2) Meaningful clinical heterogeneity (MS care practices, genetic backgrounds, environmental factors vary by country), (3) Regulatory alignment (data localization often follows national boundaries).

**Participating Countries/Regions:** Australia, Czech Republic, Turkey, Argentina, Belgium, Canada, Italy, Austria, Egypt, Iran, Denmark, Spain, Portugal, Switzerland, Netherlands, Hungary, Kuwait, Israel, Greece, Jordan, South Africa, New Zealand, Germany, United Arab Emirates, France, Brazil, Serbia, Oman, Russia, Saudi Arabia, Norway, Qatar (32 total).

**Data Characteristics:** MSBase uses standardized electronic data capture forms across sites. Data include demographics, EDSS scores, Kurtzke Functional System scores, relapse history, therapy records, and lab results (when available). Approximate total: ~26,000 patients, ~280,000+ patient episodes.

</div>
</details>

### Federation Mode

**What to document:** Specify whether you're using simulated federation (single infrastructure with partitioned data), live federation (truly distributed clients), or hybrid approaches. If simulated: describe data partitioning strategy and what real-world factors you're NOT capturing. If live: describe network topology and coordination mechanisms.

**Why it matters:** Simulation is valuable for algorithm development but has different privacy, performance, and operational characteristics than live federation. Readers need to know your TRL and what still needs validation.

<details class="example">
<summary>📝 Example from FL-MS Study</summary>
<div class="example-content" markdown="1">

**Simulated Federation (TRL 4-5):**

MSBase registry data accessed on Flanders Supercomputer Center infrastructure. Data partitioned by country to create 32 virtual clients, but all data physically reside on same computing cluster. Each virtual client has exclusive access to its country's data subset during training (enforced programmatically). Simulated server-client architecture with Flower framework orchestrating communication rounds.

**Captures:**

- Realistic data heterogeneity (countries genuinely differ in patient demographics, disease severity, treatment patterns)
- Client-level data isolation (no raw data sharing)
- Multi-round communication and aggregation overhead

**Does NOT Capture:**

- Real network latency across international hospital connections
- Firewall negotiations and institutional IT security requirements
- Human coordination overhead (scheduling training across time zones, aligning with hospital IT maintenance windows)
- Hardware heterogeneity (all clients use same CPU architecture in simulation)
- True distributed data governance (single institution ethics approval, not 32 separate approvals)

**Purpose:** Algorithm development, hyperparameter tuning, and comparative evaluation of personalization strategies. Results inform future live deployment but should be validated again in real distributed setting.

</div>
</details>

### Inclusion and Exclusion Criteria

**What to document:** Define eligibility for records, subjects, or data samples at both the dataset level (which sites participate) and record level (which observations are analyzed). Document any temporal restrictions, data quality filters, or minimum sample size requirements.

**Why it matters:** Clear criteria ensure reproducibility and allow readers to assess whether your findings generalize to their populations.

<details class="example">
<summary>📝 Example from FL-MS Study</summary>
<div class="example-content" markdown="1">

**Patient-Level Inclusion:**

- Diagnosis of MS or clinically isolated syndrome (CIS)
- Age ≥18 years
- Minimum 12-month follow-up in registry
- At least 3 EDSS measurements in 3.25 years before baseline assessment

**Episode-Level Inclusion:**

- Baseline EDSS score available
- Sufficient historical data in observation window (relapses, therapies, function scores)
- 2-year follow-up available for outcome labeling

**Exclusion:**

- EDSS measurements within 30 days of relapse (to avoid confounding by transient disability)
- Episodes with missing critical features (baseline EDSS, follow-up duration)
- Clients (countries) with <5 patient episodes (too small for meaningful training)

**Final Dataset:** 283,115 episodes from 26,246 patients across 32 countries after applying criteria.

</div>
</details>

### Features and Data Dictionary

**What to document:** List all variables used in your analysis, grouped by type (demographics, clinical measures, lab values, etc.). Provide or link to a detailed data dictionary with units, permissible ranges, and definitions. Note any derived features (feature engineering).

**Why it matters:** Comprehensive feature documentation is essential for reproducibility and helps others map your approach to their data schemas.

<details class="example">
<summary>📝 Example from FL-MS Study</summary>
<div class="example-content" markdown="1">

**42 Tabular Features for Modeling:**

**Demographics & Disease Characteristics:**

- Age at episode baseline
- Sex
- Disease duration
- MS type (relapsing-remitting, secondary progressive, primary progressive)

**Disability Measures:**

- Baseline EDSS (Expanded Disability Status Scale, 0-10 scale)
- Kurtzke Functional System scores (pyramidal, cerebellar, brainstem, sensory, bowel/bladder, visual, cerebral/mental)
- Changes in EDSS over observation window

**Disease Activity:**

- Number of relapses in past 12 months, 24 months, and observation window
- Annualized relapse rate
- Time since last relapse

**Treatment History:**

- Current disease-modifying therapy (DMT) class
- Treatment duration
- Number of prior DMT switches
- Treatment-naive status

**Full data dictionary:** Maintained within MSBase consortium documentation (access via data use agreement). Features follow standard MS research conventions (EDSS per Kurtzke standardized scoring, relapses per McDonald criteria).

</div>
</details>

### Outcome Definitions

**What to document:** For supervised learning: precisely define your target variable(s). For hypothesis testing: state your null and alternative hypotheses. Include operational definitions, time windows, confirmation requirements, and any exclusions.

**Why it matters:** Ambiguous outcome definitions lead to non-reproducible results and clinical misinterpretation. Precision here is non-negotiable.

<details class="example">
<summary>📝 Example from FL-MS Study</summary>
<div class="example-content" markdown="1">

**Primary Outcome: Confirmed Disability Progression (CDP)**

Defined as sustained increase in EDSS score from baseline, confirmed at 6-month follow-up, following published validation criteria:

- EDSS increase ≥1.0 point if baseline EDSS ≤5.5
- EDSS increase ≥0.5 points if baseline EDSS >5.5
- Increase sustained for at least 6 months (confirmation period)
- EDSS measurements within 30 days of relapse excluded (avoid confounding by transient relapse-associated disability)

**Prediction Window:** 2 years from baseline assessment

**Binary Label:** CDP=1 (progression occurred within 2 years), CDP=0 (no progression or insufficient follow-up)

**Rationale:** 6-month confirmation reduces false positives from measurement variability or short-term fluctuations. 2-year window clinically relevant for treatment decision-making.

</div>
</details>

### Dataset Characteristics

**What to document:** Report sample sizes (total and per client), class balance or outcome prevalence, known biases or selection effects, and missing data patterns. Quantify heterogeneity across clients if applicable.

**Why it matters:** Understanding your data distribution is crucial for choosing appropriate algorithms, handling imbalance, and interpreting model performance. Transparency about biases supports critical appraisal.

<details class="example">
<summary>📝 Example from FL-MS Study</summary>
<div class="example-content" markdown="1">

**Total Sample:** 283,115 episodes from 26,246 unique patients across 32 countries

**Episodes Per Client:** Highly variable (range: 5 to 60,000+ episodes). Largest clients: Australia (~60K), Czech Republic (~45K), Turkey (~30K). Smallest clients: <100 episodes in several countries.

**Class Balance:** Overall progression rate ~18-20% (confirmed disability progression within 2 years). However, class balance varies dramatically by client:

- Some sites have very low progression rates (5-10%, mostly stable patients)
- Others have higher rates (25-30%, potentially referral bias toward more severe cases)
- A few small sites have NO positive cases in their sample

**Known Biases:**

- Referral bias: Academic centers (which contribute to MSBase) may see more severe or treatment-refractory cases
- Geographic bias: MSBase over-represents high-income countries with established MS registries
- Treatment bias: Patients on registry may have better access to disease-modifying therapies than general MS population
- Temporal bias: Data collection practices evolved over registry's multi-decade history

**Missing Data:** Variability in KFS completeness, some lab values (e.g., MRI metrics) rarely available, treatment history more complete for recent years. Missingness handled via feature engineering and model design tolerant to sparse inputs.

</div>
</details>

### Data Quality and Harmonization

**What to document:** Note any data quality issues discovered during exploration (missingness, outliers, measurement errors). List vocabularies, ontologies, coding systems, and unit conventions used for harmonization across sites. Describe mapping rules for sites with local codes. Mention versioning strategy if standards change over time.

**Why it matters:** Data quality issues directly impact model validity. Harmonization documentation enables others to prepare their data compatibly.

<details class="example">
<summary>📝 Example from FL-MS Study</summary>
<div class="example-content" markdown="1">

**Data Quality:**

- EDSS scores generally high quality (required field in MSBase, trained raters, standardized assessment)
- KFS component scores have higher missingness (~10-15% of episodes)
- Relapse dating precision varies (some sites record exact date, others only month/year)
- Treatment coding evolved over time as new DMTs approved
- Some older episodes lack detailed therapy class information

**Harmonization Standards:**

- EDSS: Kurtzke's standardized scale (0.0 to 10.0, half-point increments)
- MS diagnosis: McDonald criteria (version documented in registry)
- Relapses: Clinical events with objective neurological findings, minimum 30-day separation
- DMT classification: Grouped into standard categories (platform injectables, oral DMTs, high-efficacy therapies, etc.) using MSBase coding system

**Data Versioning:** MSBase maintains centralized data quality procedures. This study used data snapshot from [specific date/version]. Future analyses may differ due to ongoing data cleaning and historical record updates.

**No explicit ontology mapping needed:** MSBase pre-harmonizes data across sites, providing research-ready dataset. Individual sites handle local EHR-to-MSBase mapping independently.

</div>
</details>

---

<h2 class="phase-header" id="phase4">
🔧 Phase 4: Preparation & Infrastructure
</h2>

<div class="phase-intro" markdown="1">
<strong>This is where planning becomes implementation.</strong> You'll transform raw data into analysis-ready features at each client site and set up the technical infrastructure for federation. This phase has two parallel tracks: (1) data engineering happening locally at each site, and (2) federation infrastructure setup happening centrally. Both must work together seamlessly.
</div>

<div class="phase-meta" markdown="1">

<div class="phase-meta-item questions">
<strong>Key Questions:</strong> How do you preprocess data consistently across all sites while respecting local variations? How will you handle train/test splits in distributed setting? What normalization strategy avoids information leakage? What federation framework and topology will you use? What hardware do clients need? How will you monitor training and handle failures?
</div>

<div class="phase-meta-item people">
<strong>Who's Involved:</strong> Data engineers at each site implement local preprocessing pipelines. ML engineers set up federation framework (Flower, PySyft, TensorFlow Federated, etc.). IT administrators configure servers and network access. DevOps engineers handle monitoring and logging. System architects design topology. All following shared specifications from coordination team.
</div>

<div class="phase-meta-item timeline">
<strong>Timeline:</strong> 4-12 weeks depending on number of sites and technical complexity. Data pipeline development: 2-4 weeks. Infrastructure setup and testing: 2-4 weeks. Integration and debugging: 2-4 weeks. More sites = more coordination overhead.
</div>

<div class="phase-meta-item mistakes">
<strong>Common Mistakes:</strong> Inconsistent preprocessing across sites (subtle bugs multiply), ignoring data leakage (test statistics leaking into normalization), underestimating infrastructure complexity (firewalls, authentication, monitoring), poor error handling (one client failure crashes everything), inadequate logging (can't debug when things go wrong).
</div>

<div class="phase-meta-item deliverables">
<strong>Deliverables:</strong> Validated preprocessing pipelines running at each site, federation infrastructure passing integration tests, monitoring dashboards operational, documented hardware and software specifications, runbooks for troubleshooting common issues.
</div>

</div>

### Local Data Preparation

**What to document:** Describe your complete preprocessing pipeline: data transformations, filtering, feature engineering, temporal windowing, and quality checks. Explain how you create train/validation/test splits (temporal, random, stratified). Detail your normalization strategy (local statistics, global statistics, fixed references). Describe missing data imputation and class imbalance handling.

**Why it matters:** Preprocessing choices profoundly affect model performance and validity. Transparent documentation of these steps is essential for reproducibility and helps others avoid common pitfalls (e.g., data leakage, improper normalization).

<details class="example">
<summary>📝 Example from FL-MS Study</summary>
<div class="example-content" markdown="1">

**Episode Construction:**
Preprocessed longitudinal MS patient data into analysis episodes. Each episode:

- Starts at baseline EDSS measurement
- Includes 3.25-year observation window capturing: relapse history, therapy changes, prior EDSS trajectory
- Has binary label: confirmed disability progression at 2-year follow-up (yes/no)

**Feature Engineering:**

- Computed annualized relapse rates over multiple time windows
- Derived EDSS change metrics (slope, volatility)
- Encoded treatment history (current DMT class, duration, number of switches)
- Extracted KFS scores and changes
- Created temporal features (time since diagnosis, time on current therapy)
- Final feature set: 42 numerical inputs

**Train/Validation/Test Splits:**

- 60% train, 20% validation, 20% test split performed independently at each client
- Splits performed at patient level (all episodes from same patient in same split) to prevent leakage
- Random stratified sampling to maintain class balance across splits

**Normalization:**

- Applied per-client using training set statistics (mean/standard deviation)
- Each client independently normalizes continuous features
- Avoids information leakage from test set or other clients
- Trade-off: local normalization may hurt model convergence when client distributions differ substantially

**Missing Data:**

- Documented but not heavily imputed (model architecture chosen to be tolerant to missing features)
- KFS scores: Mean imputation within client when missing
- Treatment data: "Unknown" category for missing values

**Class Imbalance:**

- Documented wide variation across clients (5-30% progression rates)
- Did NOT apply loss weighting or resampling in main analysis
- Personalization strategies designed to help models adapt to local class distributions

**Provenance:** All preprocessing captured in versioned Python code with clear documentation. Each transformation logged for audit trail.

</div>
</details>

### Federation Infrastructure

**What to document:** Describe your network topology (star, hierarchical, peer-to-peer), orchestration framework, scheduling approach, client participation policies, and hardware specifications. If simulating: explain setup and limitations. Include monitoring, failure recovery, and baseline security measures (transport encryption, authentication).

**Why it matters:** Infrastructure choices affect privacy guarantees, communication overhead, fault tolerance, and scalability. This documentation helps others estimate resource requirements and identify potential deployment challenges.

<details class="example">
<summary>📝 Example from FL-MS Study</summary>
<div class="example-content" markdown="1">

**Topology:**

- Centralized star architecture: single server coordinates 32 clients
- All clients participate in each round (no client sampling)
- Server-client communication only (no peer-to-peer)

**Orchestration:**

- Flower 1.5.0 federated learning framework
- Server: Centralized coordinator on Flanders Supercomputer Center
- Clients: Simulated as separate processes on same infrastructure (country-partitioned data)
- 50 federation rounds per experiment, each round includes: (1) Server distributes global model, (2) Clients train locally for specified epochs, (3) Clients send model updates to server, (4) Server aggregates updates via FedAvg/FedProx/FedOpt

**Compute Environment:**

- Infrastructure: Flanders Supercomputer Center (VSC), Intel Xeon Platinum 8260 CPUs
- No GPU acceleration (tabular data, MLP architecture trains efficiently on CPU)
- Each experiment repeated 10 times with different random seeds for robustness assessment
- Total experiments: >100 configurations tested (different algorithms, client fractions, personalization strategies)

**Client Participation:**

- Main experiments: All 32 clients participate every round
- Client fraction experiments: Tested 100%, 60%, 40% participation to assess efficiency trade-offs
- No client dropout handling needed (simulated environment, deterministic availability)

**Monitoring:**

- Flower framework built-in logging: round times, client training metrics, aggregation success
- Custom logging: model performance on validation sets each round, early stopping based on validation performance plateau

**Simulation Limitations:**

- All clients on same physical infrastructure (no real network latency, firewall issues, or distributed governance)
- Deterministic client availability (not realistic for hospital IT environments with maintenance windows, downtimes)
- Uniform hardware (real hospitals would have heterogeneous compute capabilities)
- No real data quality heterogeneity beyond what exists in MSBase (which is already harmonized)

**Security Baseline (Simulated):**

- Data access controlled via Flanders Supercomputer authentication
- Experiment isolation via separate processing jobs
- No data physically transferred (remains on approved infrastructure per ethics agreement)
- Model updates in memory only, not transmitted over external networks

</div>
</details>

---

<h2 class="phase-header" id="phase5">
🧬 Phase 5: Development & Training
</h2>

<div class="phase-intro" markdown="1">
<strong>This is where the federated learning happens.</strong> You'll design your analytical approach, train models (or run federated analytics), and rigorously evaluate results. This phase generates your scientific findings and determines whether federated analytics successfully solved your problem.
</div>

<div class="phase-meta" markdown="1">

<div class="phase-meta-item questions">
<strong>Key Questions:</strong> What algorithms will you test? How do they handle data heterogeneity across clients? What does "success" look like (metrics, thresholds)? How does federated performance compare to centralized and local-only baselines? Does the model work fairly across all participating sites?
</div>

<div class="phase-meta-item people">
<strong>Who's Involved:</strong> Data scientists and ML engineers design and implement methods. Domain experts (clinicians, scientists) validate that approach makes sense for the problem. Statisticians ensure rigorous evaluation. Site coordinators support distributed execution.
</div>

<div class="phase-meta-item timeline">
<strong>Timeline:</strong> This is typically the longest phase (weeks to months depending on number of experiments, computational resources, and debugging cycles).
</div>

<div class="phase-meta-item deliverables">
<strong>Deliverables:</strong> Trained models or computed statistics, comprehensive performance reports comparing multiple approaches, fairness analysis showing per-client results, documented hyperparameters and training configurations.
</div>

</div>

### Computation Plan

**What to document:**

**For Predictive Modeling:** List all algorithms tested - both federated (FedAvg, FedProx, etc.) and baselines (centralized, local-only). Describe your model architecture in detail. Explain hyperparameter choices and how you tuned them. Document training schedules (number of rounds, local epochs, batch sizes, early stopping). If using personalization: explain your strategy (local fine-tuning, meta-learning, architecture-based personalization). ALWAYS include a centralized baseline to quantify the privacy-utility trade-off.

**For Analytics Without Modeling:** Describe statistical methods (federated mean, median, quantiles, regression coefficients). Explain how local summaries combine (weighted average, meta-analysis, secure aggregation protocols). Document hypothesis tests and distributional assumptions. If using differential privacy: specify epsilon/delta budgets, sensitivity calculations, and composition strategy.

**For Both:** Set and document random seeds for reproducibility. Note any sources of non-determinism (GPU operations, asynchronous updates, client ordering effects).

**Why it matters:** Method transparency enables peer review, helps readers choose appropriate approaches for their contexts, supports regulatory assessment, and allows others to build on your work. Comparison to centralized baseline quantifies the cost of privacy preservation and justifies federated approach.

<details class="example">
<summary>📝 Example from FL-MS Study</summary>
<div class="example-content" markdown="1">

**Model Architecture:**

- Multi-Layer Perceptron (MLP): 5 hidden layers, each with 256 neurons
- Input layer: 42 features (clinical and demographic variables)
- Output: Binary classification (disability progression yes/no)
- Activation: ReLU for hidden layers, sigmoid for output
- Total parameters: ~330K

**Centralized Baseline:**

- Same MLP architecture trained on globally pooled data (all 283K episodes)
- Standard PyTorch training with Adam optimizer
- Achieved ROC-AUC ~0.81, PR-AUC ~0.46 on country-partitioned test set
- Reference for assessing federated vs. centralized trade-off

**Federated Algorithms Tested:**

1. **FedAvg** (Federated Averaging): Baseline FL method, simple weighted average of client model updates
2. **FedProx**: Adds proximal term to handle client heterogeneity (tested mu=0.001, 0.01, 0.1)
3. **FedOpt variants:** Server-side adaptive optimizers
   - FedYogi (better convergence for non-IID data)
   - FedAdam (adaptive learning rates)
   - FedAdagrad (adaptive per-parameter learning)

**Personalization Strategies:**

1. **AdaptiveDualBranchNet (Novel Architecture):**

   - Shared trunk: Common layers trained federally (learns population-level patterns)
   - Client-specific branches: Local layers adapted to site-specific distributions
   - Adaptive scaling: Branch size proportional to client data volume (large sites get more parameters, small sites share more globally)
   - Enables personalization without requiring post-training fine-tuning

2. **Post-Federation Fine-Tuning:**
   - Train global model via federated learning (any algorithm: FedAvg, FedProx, etc.)
   - After federation completes, each client fine-tunes global model on local training data
   - Reduced learning rate (1/10 of federated training) and fewer epochs (5-10)
   - Adapts model to local data distribution while retaining global knowledge

**Local-Only Baseline:**

- Each client trains MLP independently on own data (no federation)
- Represents maximum personalization but no knowledge sharing
- Expected to perform poorly for small clients, well for large clients

**Training Schedule:**

- 50 communication rounds for federated experiments
- Local training: variable epochs per round depending on configuration (1-5 epochs tested)
- Batch size: 64 (when client has sufficient data; smaller for tiny clients)
- Early stopping: Monitor validation performance, stop if no improvement for 10 rounds (not always triggered in 50-round experiments)

**Hyperparameters:**

- Learning rate: 0.001 (Adam optimizer) for federated training, 0.0001 for fine-tuning
- Dropout: Not used (MLP with L2 regularization instead)
- Weight decay: 1e-4
- Aggregation weights: Proportional to client training set size (standard in FedAvg)
- Tuned via grid search on country-based FedAvg configuration, then applied consistently across all experiments for fair comparison

**Reproducibility:**

- 10 repeated runs per configuration with different random seeds (seeds 0-9)
- Seeds control: data splits, model initialization, batch shuffling
- Report mean ± standard deviation across runs
- PyTorch deterministic mode enabled where possible (some CPU operations non-deterministic)

</div>
</details>

### Evaluation and Success Criteria

**What to document:**

**For Modeling:** Define your primary metric (the ONE number you'll use to judge success) and secondary metrics (additional performance dimensions). Explain how evaluation happens: where are models tested (centrally or at each client), how do you aggregate local performance metrics, and how do you ensure test data never leaked into training. Compare federated performance to three baselines: (1) centralized (what you'd get with pooled data), (2) local-only (what each site gets training alone), (3) simpler methods (logistic regression, clinical scores). Report runtime and computational cost. Quantify statistical uncertainty (confidence intervals, multiple runs). Check fairness: do results hold across all clients, or do some sites get worse predictions?

**For Analytics:** Report accuracy and precision of federated estimates compared to centralized ground truth (if available). Do confidence intervals have appropriate coverage? How sensitive are results to analytical choices (imputation methods, aggregation strategies)? Do conclusions change when you exclude certain sites (leave-one-out robustness)?

**Why it matters:** This is where you prove your method works. Rigorous evaluation with proper baselines distinguishes publishable science from exploratory tinkering. Fairness analysis is ethically essential - a model that works well on average but fails for smaller sites creates equity issues and reduces participation incentives.

<details class="example">
<summary>📝 Example from FL-MS Study</summary>
<div class="example-content" markdown="1">

**Primary Metrics:**

- **ROC-AUC** (area under receiver operating characteristic curve): Threshold-independent performance measure
- **PR-AUC** (area under precision-recall curve): Emphasizes performance on minority class (important given imbalance)

**Client-Side Evaluation:**

- Each client evaluates model on own test set (20% of local data, never seen during training)
- Computed metrics: ROC-AUC, PR-AUC, accuracy, sensitivity, specificity
- Test sets partitioned by country (consistent across all experiments)

**Aggregation Across Clients:**

- Weighted average by test set size: ROC-AUC_global = Σ(n_i × ROC-AUC_i) / Σ(n_i)
- Also report: simple average (treats all sites equally), min/max (quantify heterogeneity), standard deviation across sites

**Comparison to Centralized Baseline:**

- Centralized MLP: ROC-AUC 0.81 ± 0.01, PR-AUC 0.46 ± 0.02
- Baseline FedAvg: ROC-AUC 0.73 ± 0.02, PR-AUC 0.28 ± 0.03 (worse than centralized)
- **Personalized FedProx: ROC-AUC 0.84 ± 0.002, PR-AUC 0.52 ± 0.01 (BETTER than centralized!)**
- Personalized FedAvg: ROC-AUC 0.838 ± 0.001, PR-AUC 0.51 ± 0.01

**Key Finding:** Personalization overcomes heterogeneity penalty, enabling federated learning to match or exceed centralized performance while preserving data localization.

**Statistical Uncertainty:**

- 10 repeated runs with different seeds per configuration
- Report mean ± standard deviation
- Confidence intervals for ROC-AUC computed via DeLong's method
- Overall low variance across runs (standard deviations ~0.001-0.003), indicating robust performance

**Runtime and Cost:**

- Experiment time tracked from first round start to final round completion
- Centralized training: ~9 minutes average
- FedAvg (32 clients, 50 rounds): ~29 minutes average
- Client fraction experiments: 60% participation reduced time by ~30% with minimal performance loss
- Computational cost: CPU-hours on supercomputer (GPU not required for MLP on tabular data)

**Fairness and Subgroup Analysis:**

- Performance stratified by client size (small <1000 episodes, medium 1000-10K, large >10K)
- **Small clients benefit most from personalization:** Local-only models perform terribly (insufficient data), baseline FL performs poorly (dominated by large clients), personalized FL achieves strong performance (benefits from global knowledge + local adaptation)
- **Large clients:** Personalization offers modest gains over baseline FL
- **Imbalanced clients:** Sites with extreme class imbalance (5% or 30% progression rates) show larger improvements with personalization vs. global model

**Sensitivity Analyses:**

- Tested different client fractions (100%, 60%, 40% participation)
- Tested multiple federated algorithms (FedAvg, FedProx with varying mu, FedOpt variants)
- Tested two personalization strategies (architecture-based, fine-tuning-based)
- Results robust to these choices; personalization consistently improves performance

</div>
</details>

---

<h2 class="phase-header" id="phase6">
🔒 Phase 6: Privacy, Security & Risk
</h2>

<div class="phase-intro" markdown="1">
<strong>Privacy and security aren't afterthoughts - they're core design requirements for federated analytics.</strong> This phase documents the technical safeguards that implement your governance policies (from Phase 2). You'll identify threats, describe defenses, and be transparent about what is and isn't protected. Privacy is a spectrum, not binary.
</div>

<div class="phase-meta" markdown="1">

<div class="phase-meta-item questions">
<strong>Key Questions:</strong> What could go wrong (threat model)? Who might try to attack your system (adversaries)? What information could leak (attack vectors)? What defenses have you implemented? What privacy guarantees can you actually make? For simulations: how does your threat model differ from real deployment?
</div>

<div class="phase-meta-item people">
<strong>Who's Involved:</strong> Security engineers conduct threat modeling and implement controls. Privacy experts assess re-identification risks. Cryptography specialists design secure aggregation if needed. Data protection officers ensure GDPR compliance. IT security teams handle infrastructure hardening.
</div>

<div class="phase-meta-item timeline">
<strong>Timeline:</strong> Threat modeling: 1-2 weeks. Implementation of basic controls (encryption, authentication): 1-2 weeks. Advanced privacy tech (differential privacy, secure MPC): 4-8+ weeks if needed. Security audit: 1-2 weeks. This often overlaps with Phase 4 infrastructure work.
</div>

<div class="phase-meta-item mistakes">
<strong>Common Mistakes:</strong> Assuming "federated = private" automatically (not true without additional safeguards), ignoring simulation vs. production threat model differences, implementing differential privacy without understanding epsilon parameters, over-claiming privacy guarantees, no incident response plan.
</div>

<div class="phase-meta-item deliverables">
<strong>Deliverables:</strong> Threat model document, implemented security controls checklist, privacy impact assessment, incident response plan, audit logs and monitoring setup.
</div>

</div>

### Threat Model and Controls

**What to document:** Identify potential adversaries (honest-but-curious server, malicious clients, external attackers, insiders) and attack vectors (model inversion, membership inference, gradient leakage, Byzantine updates). List implemented defenses (secure aggregation, encryption, differential privacy, access logging). If using DP: document privacy budget accounting. For simulations: note how threat model differs from live deployment.

**Why it matters:** Privacy is not binary. Explicit threat modeling helps stakeholders understand what is and isn't protected, supports ethics review, and guides design choices.

<details class="example">
<summary>📝 Example from FL-MS Study</summary>
<div class="example-content" markdown="1">

**Threat Model:**

Primary concern: **Honest-but-curious server or researchers** attempting to infer individual patient information from shared model updates or aggregated results.

**Considered Attack Vectors:**

- Membership inference: Could an adversary determine if specific patient was in training set?
- Model inversion: Could patient features be reconstructed from model weights?
- Gradient leakage: Could individual patient data be extracted from gradient updates?

**NOT considered in this study:** Byzantine attacks (malicious clients sending poisoned updates), external network attackers (simulated environment), insider threats at individual MSBase sites (governed by institutional access controls).

**Privacy Controls Implemented:**

1. **Data Localization:** In simulation, data partitioned by country with programmatic access controls preventing cross-client data access. In future live deployment, data would physically remain at source institutions.

2. **Aggregation-Based Privacy:** Server aggregates model updates from 32 clients before storing or analyzing. Individual client updates not retained after aggregation.

3. **No Raw Data Sharing:** Only model parameters (weights, gradients) communicated. Raw patient records never leave client environments.

4. **Access Controls:** MSBase data access on Flanders Supercomputer restricted to authorized researchers (authentication, audit logging).

**Privacy Controls NOT Implemented:**

- **Differential Privacy:** Not applied (would add noise to gradients, potentially degrading model utility below clinical threshold). Could be explored in future work with careful epsilon budget selection.
- **Secure Multi-Party Computation:** Not used (adds complexity; aggregation-based privacy deemed sufficient for this research context).
- **Trusted Execution Environments:** Not available on supercomputer infrastructure.

**Simulation-Specific Notes:**

Current threat model is theoretical: data already reside on single infrastructure, so network-based attacks not realistic. Focus on validating algorithmic privacy (ensuring aggregation logic doesn't leak client-specific information in results).

When transitioning to live deployment (TRL 6+), new threats emerge: real network interception, compromised clients in different jurisdictions, insider threats at individual hospitals. Would need: TLS encryption for model transmission, client authentication (certificates or API tokens), network firewalls, and potentially hardware-based trusted execution.

**Incident Response:**

No formal incident response plan for simulation phase (research setting, de-identified data). Future clinical deployment would require: designated security officer, breach notification procedures (GDPR 72-hour requirement), remediation protocols (pause federation, rotate credentials, investigate scope).

</div>
</details>

---

<h2 class="phase-header" id="phase7">
📚 Phase 7: Reproducibility & Sharing
</h2>

<div class="phase-intro" markdown="1">
<strong>Making your work reproducible is not optional - it's a scientific and ethical obligation.</strong> This phase documents everything someone else needs to validate your findings or apply your methods to their own data. For federated analytics, reproducibility has unique challenges because data can't be shared, yet methods must still be verifiable.
</div>

<div class="phase-meta" markdown="1">

<div class="phase-meta-item questions">
<strong>Key Questions:</strong> Can someone else reproduce your results with access to the same (or similar) data? Have you documented enough detail about your environment, hyperparameters, and preprocessing that results should be identical? If data can't be shared, what alternatives enable validation (synthetic data, code testing, detailed methods)?
</div>

<div class="phase-meta-item people">
<strong>Who's Involved:</strong> Research software engineers ensure code quality and documentation. Data stewards document data access procedures. Legal/ethics teams review what can be publicly shared. Principal investigators decide publication strategy.
</div>

<div class="phase-meta-item timeline">
<strong>Timeline:</strong> Overlaps with Phase 5 (document as you go) but finalization happens after results are ready. Budget 2-4 weeks for code cleanup, documentation writing, and artifact archiving before publication.
</div>

<div class="phase-meta-item mistakes">
<strong>Common Mistakes:</strong> Waiting until submission deadline to organize code (leads to rushed, poor documentation). Forgetting to document version numbers. Releasing code that can't run without undocumented dependencies. Not explaining data access process clearly.
</div>

<div class="phase-meta-item deliverables">
<strong>Deliverables:</strong> Public code repository with documentation, environment specification files, archived artifacts with persistent identifiers (DOIs), data access guide, documented limitations.
</div>

</div>

### Code, Data, and Artifacts

**What to document:**

**Code:** GitHub/GitLab repository URL with specific commit hash or release tag used for published results. README explaining how to run code. Requirements file with package versions. If using containers: Docker image tags or Conda environment files.

**Environment:** Software versions (Python, R, libraries), operating system, hardware (CPU/GPU specs). Note: exact hardware may not be reproducible, but document what you used.

**Random Seeds:** All seeds for data splits, initialization, sampling. Mention sources of non-determinism (GPU operations, async updates).

**Data Availability:** Choose one path and explain clearly: (1) Public - provide dataset name and download link, (2) Restricted - explain application process, timeline, costs, (3) Synthetic - provide generator scripts or synthetic samples.

**Artifacts:** List everything you're releasing: model weights (if allowed by governance), configuration files, evaluation outputs, figures. Use persistent identifiers (Zenodo DOI, Figshare).

**Limitations:** Be honest about what doesn't work, what you couldn't validate, and where your approach might not generalize.

**Why it matters:** Reproducibility builds scientific trust, enables others to validate your claims, and accelerates cumulative progress. In federated learning where data can't be shared, code and environment documentation become even more critical for verification.

<details class="example">
<summary>📝 Example from FL-MS Study</summary>
<div class="example-content" markdown="1">

**Code Repository:**

- GitHub: https://github.com/ashkan-pirmani/FL-MS (Apache 2.0 license)
- Release tag: v1.0.0 (commit hash: [specific commit])
- Includes: Preprocessing scripts, Flower FL implementation, model architectures, evaluation notebooks, configuration files

**Software Environment:**

- Python 3.9
- PyTorch 1.12.1
- Flower 1.5.0
- Scikit-learn 1.2.0, Pandas 1.5.2, NumPy 1.23.5
- Operating System: Linux (VSC cluster)
- Hardware: Intel Xeon Platinum 8260 CPU

**Reproducibility:**

- Random seeds: 0-9 for 10 repeated runs
- Seeds control: data splits, model initialization, batch shuffling
- Results highly reproducible (SD across runs ~0.001-0.003 for ROC-AUC)

**Data Availability:**

- **Restricted Access:** MSBase registry data not publicly available due to privacy/governance
- **Access Process:** Researchers may apply at www.msbase.org. Requires: research proposal, ethics approval, data use agreement, 2-6 month approval timeline
- **Synthetic Data:** Not provided (difficult to generate realistic longitudinal MS data preserving clinical patterns)
- **Alternative:** Our code can run on any tabular longitudinal dataset with similar structure (episodes with features + binary outcome)

**Artifacts Released:**

- Configuration files (JSON/YAML) for all experiments
- Hyperparameter specifications
- Model architecture code (full Python implementation)
- Evaluation scripts and metrics calculation
- Trained model weights: NOT released (privacy concerns even for aggregated models, plus MSBase data use restrictions)

**Persistent Identifiers:**

- Publication DOI: https://doi.org/10.1038/s41746-025-01788-8
- Code repository: Archived on Zenodo upon publication (DOI to be assigned)
- Experiments not tracked in MLflow (simpler logging via Flower framework sufficient)

**Known Limitations:**

1. **Simulation vs. live federation:** Results from simulated setup may not fully generalize to live distributed deployment (network latency, hardware heterogeneity, real governance overhead not captured)
2. **MSBase generalizability:** Registry data may not represent general MS population (referral bias toward academic centers, geographic bias toward high-income countries)
3. **Label quality:** Disability progression relies on EDSS documentation quality, which varies across sites
4. **No external validation:** Results not tested on datasets outside MSBase
5. **Client definition:** Country-level clients convenient for simulation but may not align with real deployment (hospitals/clinics are more natural units)
6. **Temporal validation:** Test set contemporary with training data; future drift not assessed

</div>
</details>

---

<h2 class="phase-header" id="phase8">
🚀 Phase 8: Maturity Assessment & Path Forward
</h2>

<div class="phase-intro" markdown="1">
<strong>This phase honestly assesses where you are and what comes next.</strong> Not every federated learning project needs to reach production deployment - many generate valuable scientific insights while remaining research tools. This section helps you and your stakeholders understand the current maturity level, what it would take to advance, and whether that investment makes sense.
<br><br>
<em>Honest reflection matters more than hype.</em> Many research projects contribute valuable knowledge at TRL 4-5 without ever deploying. Overpromising deployment timelines damages credibility and wastes resources.
</div>

<div class="phase-meta" markdown="1">

<div class="phase-meta-item questions">
<strong>Key Questions:</strong> Is this production-ready, or proof-of-concept? What evidence supports your maturity claim? What would it actually take (time, money, people, approvals) to reach the next level? Is deployment realistic and worthwhile, or is the research contribution sufficient?
</div>

<div class="phase-meta-item people">
<strong>Who's Involved:</strong> Principal investigators assess scientific maturity. Clinical champions evaluate deployment feasibility. IT leaders estimate infrastructure requirements. Funders consider return on investment. Regulators may need consultation for medical applications.
</div>

<div class="phase-meta-item timeline">
<strong>Timeline:</strong> Initial TRL assessment happens throughout the project. Final assessment and roadmap creation: 1-2 weeks after results finalize. If pursuing deployment: gap analysis and planning can take months.
</div>

<div class="phase-meta-item deliverables">
<strong>Deliverables:</strong> TRL assessment with evidence, gap analysis with resource estimates, deployment roadmap OR research-only justification, lessons learned document, recommendations for future work.
</div>

</div>

### Technology Readiness Level (TRL) Assessment

**What to document:**

**TRL Scale (briefly explained):**

- **TRL 1-3:** Basic research, proof of concept on toy data
- **TRL 4:** Technology validated in lab (realistic data, controlled environment)
- **TRL 5:** Technology validated in relevant environment (simulation with real data characteristics)
- **TRL 6:** Technology demonstrated in relevant environment (pilot with actual users)
- **TRL 7-8:** System prototype demonstration in operational environment
- **TRL 9:** Actual system proven in operational use

**Your Assessment:** Claim specific TRL (or range like 4-5) and justify with evidence: publications, pilot results, user feedback, regulatory interactions, deployment case studies.

**Gap Analysis:** For each gap to next TRL, specify: (1) What needs to happen, (2) Who needs to do it, (3) Estimated time and cost, (4) Key risks or blockers.

**Target Setting:** If deploying: describe ultimate operational environment concretely (50 hospitals? consumer app with 100K users? national disease registry?). If remaining research tool: describe intended research applications honestly.

**Why it matters:** TRL assessment grounds expectations in reality. Funders use this to allocate resources. Research teams use it to prioritize effort. Overstating maturity damages trust; understating it misses deployment opportunities.

<details class="example">
<summary>📝 Example from FL-MS Study</summary>
<div class="example-content" markdown="1">

**Claimed TRL: 4-5**

**TRL Definitions:**

- TRL 4: Technology validated in lab environment
- TRL 5: Technology validated in relevant environment (simulated clinical setting)
- TRL 6: Technology demonstrated in relevant environment (pilot with real users)

**Justification for TRL 4-5:**

- ✅ Methods validated in simulation with realistic, multi-country MS registry data (26K+ patients)
- ✅ Demonstrated that personalized FL achieves performance comparable to or exceeding centralized approaches
- ✅ Published in peer-reviewed journal (npj Digital Medicine, Nature Portfolio)
- ✅ Open-source code enables replication
- ❌ NOT yet: Live distributed federation across actual hospital computing infrastructure
- ❌ NOT yet: Prospective clinical validation with real clinicians using predictions
- ❌ NOT yet: Regulatory review or medical device assessment

**Evidence:**

1. Large-scale experiments using MSBase registry (283K episodes, 32 countries)
2. Peer-reviewed publication with rigorous methods and statistical validation
3. Multiple algorithmic innovations (AdaptiveDualBranchNet architecture)
4. Code publicly released enabling community replication and extension
5. Positive feedback from MSBase consortium and MS research community

**Gaps to Reach TRL 6-7:**

1. **Live Federation Deployment:** Transition from simulated to real distributed clients

   - Set up FL infrastructure across subset of MSBase participating hospitals (target: 5-10 sites)
   - Navigate distributed governance (separate ethics approvals, data use agreements per hospital)
   - Handle real IT challenges (firewalls, VPNs, hardware heterogeneity, maintenance windows)

2. **Prospective Validation:**

   - Silent trial: Deploy model predictions without showing to clinicians, collect ground truth outcomes
   - Assess model calibration and drift in real-time use
   - Measure whether predictions remain stable over time

3. **Clinical Usability Study:**

   - Work with neurologists to design decision support interface
   - Conduct user acceptance testing (n=10-20 clinicians)
   - Assess whether predictions change clinical decision-making
   - Identify barriers to adoption

4. **Regulatory Pathway:**

   - Consult with regulatory bodies (FDA, EMA) regarding classification
   - Determine if system qualifies as medical device requiring approval
   - Prepare regulatory dossier if needed

5. **External Validation:**
   - Test model on MS cohorts outside MSBase (different registries or hospital EHR data)
   - Assess generalization to populations not represented in training data

**Estimated Timeline to TRL 7:** 2-3 years
**Estimated Resources:** €500K-1M (personnel, infrastructure, clinical trial coordination)

**Target Deployment Setting:**

Long-term vision: Federated MS progression prediction network spanning major MS registries and academic medical centers globally. Hospitals would join consortium, contribute local data via federated training, and receive personalized prognostic models benefiting from diverse international data while maintaining local data governance. System could support multiple clinical prediction tasks (progression, relapse risk, treatment response) and continuous model updating as new data accumulate.

**Alternative Path: Research Tool Only**

Given regulatory and deployment complexity, may remain research tool for: (1) MS epidemiology studies, (2) Clinical trial enrichment (identifying high-risk patients), (3) Comparative effectiveness research, (4) Hypothesis generation for prospective studies. This is valuable even without clinical deployment.

</div>
</details>

### Lessons Learned and Key Decisions

**What to document:**

**Reflections:** What worked well that you'd recommend to others? What surprised you or turned out harder than expected? What would you do differently if starting over?

**Critical Decisions:** Highlight 3-5 major choices you made (algorithm selection, client definition, personalization strategy, etc.) with honest rationale. Explain trade-offs you considered. Were you right? Would you make same choice again?

**Unexpected Findings:** Scientific surprises, technical challenges you didn't anticipate, or assumptions that turned out wrong.

**Practical Advice:** Concrete recommendations for future teams attempting similar work. Things you wish someone had told you at the start.

**Next Steps:** If continuing the work: prioritized action items with timelines and resource estimates. If wrapping up: suggestions for what future research should tackle.

**Why it matters:** This section has disproportionate value for readers. Your mistakes and surprises are learning opportunities for the community. Honest reflection on decisions helps others navigate similar trade-offs. This is where you teach, not just report.

<details class="example">
<summary>📝 Example from FL-MS Study</summary>
<div class="example-content" markdown="1">

**What Worked Well:**

1. **Starting with simulation:** Using MSBase data on supercomputer allowed rapid iteration, algorithm development, and hyperparameter tuning without distributed coordination overhead. Could test 100+ configurations in reasonable time.

2. **Personalization focus:** Explicitly testing personalization strategies (not just vanilla FL) was crucial. Revealed that baseline FL underperforms centralized due to heterogeneity, but personalized FL can exceed centralized by leveraging diverse data.

3. **Rigorous evaluation:** 10 repeated runs per configuration quantified uncertainty. Client-stratified analysis revealed where methods work (small clients benefit from personalization) and where they struggle (tiny clients <100 samples still difficult).

4. **MSBase collaboration:** Working with established registry consortium provided clean, harmonized data and built-in multi-center network for future deployment.

**What Surprised Us:**

1. **Heterogeneity impact:** Baseline FL performed surprisingly poorly (ROC-AUC 0.73 vs. centralized 0.81). We expected some degradation but not this large. Highlighted critical need for personalization in real-world federated settings.

2. **Personalization effectiveness:** Personalized methods didn't just close the gap - they exceeded centralized performance (0.84 vs. 0.81). Counter-intuitive but makes sense: local adaptation captures site-specific patterns centralized model averages away.

3. **Small client behavior:** Tiny clients (<100 samples) benefit from federation + personalization, but gains limited by fundamental data scarcity. Some clients with no positive cases can't train meaningful classifiers regardless of method.

4. **Client fraction experiments:** Reducing participation from 100% to 60% clients per round cut training time by ~30% with negligible performance loss (<0.01 ROC-AUC drop). Suggests communication overhead dominates; could design more efficient sampling strategies.

**What We'd Do Differently:**

1. **Earlier stakeholder engagement:** Should have consulted with MSBase clinics earlier about live deployment feasibility. Many sites lack IT resources for running FL clients; would inform more realistic TRL roadmap.

2. **External validation planning:** Should have arranged access to external MS cohort (MSOAC, NARCOMS, etc.) from project start for out-of-sample validation.

3. **Interpretability:** Focused heavily on performance metrics; should have invested more in model interpretability (feature importance, counterfactual explanations) for clinical trust.

4. **Cost-benefit analysis:** Didn't systematically quantify costs (compute, development time, coordination overhead) vs. benefits. Future work should include economic evaluation.

**Key Decisions and Rationales:**

1. **Decision: Country-level clients** (vs. hospital-level)
   _Rationale:_ Balances sample size per client (many countries have 1000+ patients) with meaningful heterogeneity. Matches regulatory boundaries (data localization often national). Simplifies simulation (fewer clients, faster experiments). Trade-off: May not capture within-country variation.

2. **Decision: Simulation before live deployment**
   _Rationale:_ De-risks algorithm development. Can test many approaches quickly. Avoids burdening hospital IT with immature systems. Must transition to live federation for higher TRL.

3. **Decision: No differential privacy**
   _Rationale:_ DP noise would likely degrade model below acceptable performance. Aggregation over 32 clients provides some privacy protection. Future work could explore DP with larger client pools or better DP-FL algorithms.

4. **Decision: MLP architecture**
   _Rationale:_ Simple, interpretable, trains fast on CPU. More complex architectures (deep learning, transformers) overkill for tabular data with 42 features. Facilitates comparison across conditions.

5. **Decision: Test personalization strategies**
   _Rationale:_ Literature suggested FL struggles with heterogeneity; personalization seemed necessary. Confirmed via experiments.

**Next Steps:**

**Immediate (6-12 months):**

1. Publish results and code (✅ completed, Nature npj Digital Medicine 2025)
2. Present at MS research conferences (ECTRIMS, ACTRIMS) to engage clinical community
3. Apply for funding for live deployment pilot (EU Horizon, national research councils)
4. Identify 3-5 MSBase sites willing to pilot live FL infrastructure

**Medium-term (1-2 years):** 5. Deploy live FL across pilot hospitals 6. Develop hospital-friendly FL client software (easy installation, minimal IT burden) 7. Conduct prospective silent validation (predictions generated but not shown to clinicians) 8. Assess clinical utility via user studies with neurologists

**Long-term (3-5 years):** 9. Scale to 20+ hospitals if pilot succeeds 10. Explore real-time integration with EHR systems 11. Extend to additional prediction tasks (relapse risk, treatment response) 12. Pursue regulatory pathway if clinical deployment becomes goal

</div>
</details>

---

## Appendix: Changes from Template v1.1 {#appendix}

**Structural Improvements:**

- Reorganized around 8 lifecycle phases (vs. 14 flat sections) to reflect natural project progression
- Added visual phase markers and lifecycle roadmap
- Consolidated related content: merged Data + Standards, merged Wrangling into Preparation, merged Computation + Evaluation
- Added rich explanatory text for each section explaining what to document and why it matters

**New Fields Added (v1.2):**

- **Ethics Status:** Explicit field for approved/waived/N/A to handle various research contexts (public data, secondary analysis)
- **Federation Mode:** Simulated/Live/Hybrid with guidance on documenting simulation limitations
- **Centralized Baseline:** Explicit request for performance comparison to quantify privacy-utility trade-off
- **Data Availability:** Structured field for public/restricted/synthetic data access paths
- **Intended Use Case:** Allows documenting vision for proof-of-concept work without concrete deployment plan

**Clarifications:**

- Population & Setting: Now explicitly includes non-clinical subjects (sensors, administrative data)
- Fairness & Subgroup Analysis: Clarified to include non-demographic stratifications (per-site, per-outcome, etc.)
- Simulation Considerations: Added guidance throughout to support early-stage TRL work

**Example Study:**

- Replaced generic examples with real published work: Pirmani et al. (2025), "Personalized federated learning for predicting disability progression in multiple sclerosis using real-world routine clinical data," npj Digital Medicine

**Design Principles Preserved:**

- Prose-first approach (guidance as narrative, not bullet checklists)
- Separation of governance (policy) from privacy/security (technical controls)
- Explicit TRL assessment with gap analysis
- Focus on reproducibility and transparency


---

## Appendix: Changes from Template v1.1

**Major Structural Changes:**

- **Simplified from 8 phases to 4 phases** aligned with standard FL lifecycle
- **Removed confusing quick start guide** that created multiple frameworks
- **Added clear beginner guidance** with step-by-step instructions
- **Consolidated related phases** to reduce cognitive load

**Design Improvements:**

- Added hero section with clear value proposition
- Redesigned phase cards with better visual hierarchy
- Implemented progressive disclosure with collapsible sections
- Added difficulty indicators and timeline estimates
- Simplified content with bullet points and shorter paragraphs
- Improved mobile responsiveness

**Content Improvements:**

- **Aligned with standard FL lifecycle** (Planning, Preparation, Training, Deployment)
- **Added beginner-friendly guidance** for newcomers to the domain
- **Consolidated governance and ethics** into planning phase
- **Combined data understanding and infrastructure** into preparation phase
- **Integrated privacy/security** into training phase
- **Merged reproducibility and maturity assessment** into deployment phase

**User Experience:**

- **Single clear framework** instead of multiple confusing ones
- **Clear beginner path** with step-by-step instructions
- **Less intimidating first impression** with better onboarding
- **Clearer navigation** aligned with standard FL lifecycle
- **Better visual breathing room** with consolidated content






## Bibliography {#bibliography}

{% bibliography --cited %}
