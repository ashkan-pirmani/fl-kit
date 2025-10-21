---
title: federated learning life cycle in BCI finger movement decoding
version: 2.0
contributors: [Axel Faes]
search_exclude: true
description: Example of documenting a federated tensor regression project using the FA life cycle template
page_id: fbttr_bci
license: public dataset
---

## Introduction
This project evaluated whether Federated Block-Term Tensor Regression (FBTTR) can decode individual finger movements from electrocorticography (ECoG) recordings while preserving data privacy. Traditional centralized approaches require pooling sensitive neural data, conflicting with privacy regulations and institutional policies. Federated learning enables collaborative model development without centralizing raw brain recordings, addressing both privacy concerns and data localization requirements. The results are intended for neuroscientists developing brain-computer interfaces, clinicians designing neural prosthetics, and researchers studying motor control decoding.

---

## Scope and objectives
The primary objective was to assess whether FBTTR can match or exceed centralized tensor regression performance in predicting finger movements from ECoG signals, while comparing multiple federated optimization strategies (FedAvg, FedYogi, FedAdam, FedProx).

The population consists of three subjects with implanted ECoG electrode arrays (62, 48, and 64 channels) performing cued finger flexion tasks from the BCI Competition IV dataset. Outputs include predictive models for continuous finger trajectory decoding, performance comparisons across federated strategies, and benchmarks against non-multilinear methods (Random Forest, CNN, LSTM) and centralized tensor methods (HOPLS, BTTR). Out of scope were real-time decoding, multi-subject generalization, and clinical deployment.

---

## Assumptions and constraints
Key assumptions included that finger movements can be decoded from motor cortex ECoG with sufficient accuracy, temporal cross-validation adequately simulates distributed data, and 4th-order tensor structure captures relevant neural dynamics. Constraints included limitation to a public single-session dataset, simulated rather than true multi-institutional federation, and ring finger co-activation with adjacent fingers limiting decoding accuracy. Assumptions were validated by comparing federated against centralized baselines and statistical testing across 5-fold cross-validation.

---

## Governance
The research team at UHasselt Biomedical Data Sciences conducted the work using the publicly available BCI Competition IV dataset. Because this involved secondary analysis of public data, no new ethics approval was required. **[NEW FIELD]** Ethics status: N/A for secondary analysis of previously approved public datasets. All preprocessing code and model parameters were released openly, with results published in peer-reviewed proceedings.

---

## Data landscape
**[NEW FIELD]** Federation mode: Simulated via temporal cross-validation. Three subjects with ECoG arrays were studied, with each subject treated independently. Within-subject federation created five clients through 5-fold temporal cross-validation, chosen because temporal blocks approximate distributed collection across sites or sessions.

The input tensor X ∈ R^(Samples × Channels × Frequencies × Time) comprised curated ECoG electrodes (61, 46, 63 channels), 8 frequency bands (1.5-130 Hz), and 10 time bins (100 ms resolution). Output Y ∈ R^(Samples × 5) contained z-scored finger trajectories. Training used 400 seconds, testing used 200 seconds, with 150 trials per subject. Finger 4 (ring) showed strong co-activation with adjacent fingers. Bad channels were removed, and Common Average Referencing reduced noise.

### Standards and harmonization
Finger indexing followed 1=Thumb through 5=Pinky. ECoG signals were measured in microvolts, finger flexion was z-scored per session, and time bins had 100 ms resolution. The BCI Competition IV dataset version was fixed at 2008 release.

---

## Infrastructure
**[NEW TEMPLATE ELEMENT: Explicit simulation details]** The federation used simulated horizontal topology with star architecture. Clients were defined by 5-fold temporal cross-validation within subjects, approximating distributed data collection while using the public dataset. The framework combined Flower for orchestration with custom tensor operations. All five clients participated fully in each round with equal weighting. Compute came from Flanders Supercomputer Center using Intel Xeon CPUs. Communication was simulated without actual network latency. Because this was simulation, security protocols were not implemented; future deployment would use Flower's secure aggregation and TLS encryption.

---

## Wrangling
Preprocessing applied notch filtering (50/100 Hz), bad channel removal, Common Average Referencing, dataglove lag correction (37 ms), Butterworth bandpass filtering (8 bands), and sliding window extraction (1 second, 10 Hz). The temporal split allocated 400 seconds to training and 200 seconds to testing, with 5-fold cross-validation within training. Finger trajectories were z-scored per client using training statistics to avoid leakage. Bad channels were removed rather than imputed.

---

## Computation plan
**[NEW TEMPLATE ELEMENT: Comparison to centralized baseline]** Centralized baselines included BTTR, eBTTR, and HOPLS. Non-multilinear baselines comprised AM-Linear Regression, Random Forest, LARS, CNN, and LSTM. Federated variants tested FedAvg, FedAdagrad, FedYogi, and FedProx aggregation strategies.

The model used Tucker decomposition with sequential deflation and Automatic Component Extraction (ACE) to determine block count. Factor matrices covered channel, frequency, and time modes. Training extracted 30 blocks sequentially. Hyperparameters SNR [1-50] and τ [90-100] were optimized via BIC, with all clients required to use identical values for dimensional compatibility. Ten repetitions with different random seeds assessed stability.

---

## Evaluation and success criteria
**[NEW TEMPLATE ELEMENT: Centralized baseline comparison]** The primary metric was Pearson correlation between predicted and actual trajectories. Results averaged across fingers 1-3 and 5, excluding ring finger due to co-activation. Each fold evaluated locally before unweighted aggregation across folds.

Runtime showed FBTTR's efficiency: 5 minutes per subject versus 3 minutes for centralized BTTR and 14 hours for HOPLS. Statistical testing used mean ± std across 10 repetitions. Fairness analysis examined per-finger performance, finding ring finger consistently underperformed.

Critical comparisons to Centralized BTTR showed: Subject 1 (0.64 vs 0.66), Subject 2 (0.48 vs 0.48), Subject 3 (0.68 vs 0.66). FBTTR achieved parity or superiority while preserving privacy.

---

## Privacy, security, and risk
**[NEW TEMPLATE ELEMENT: Simulation-specific privacy]** Current simulation has no actual privacy threats (single machine). Future deployment must address honest-but-curious servers, gradient inversion attacks, and membership inference. Secure aggregation and differential privacy were not implemented in this proof-of-concept. Code versioning provides audit trails. Tensor decomposition inherently provides some obfuscation, though this should not be relied upon as formal privacy protection.

---

## Reproducibility and sharing
**[NEW TEMPLATE ELEMENT: Public dataset availability]** Code repository with commit tags will be released under open-source license. Environment uses Python 3.x with PyTorch, Flower, and scikit-learn (CPU-based). Artifacts include preprocessing pipeline, FBTTR implementation, orchestration scripts, and configurations. Data is publicly available from BCI Competition IV (http://www.bbci.de/competition/iv/), cited as Miller & Schalk (2008). Known limitations: simulated federation, single-session data, ring finger co-activation, potential limited generalization to other electrode placements.

---

## Operationalization and maintenance
**[NEW TEMPLATE ELEMENT: Future deployment scenarios]** Current status is TRL 4-5 proof-of-concept without operational deployment. Future scenario envisions multi-institutional BCI research consortium for collaborative model development. Future deployment should monitor per-session correlations, alert on performance degradation, and retrain when adding new subjects. Site playbooks would cover preprocessing SOPs, Flower client setup, and troubleshooting ACE synchronization.

---

## Technology readiness level (TRL)
Claimed TRL is 4 (validated in simulation). Evidence includes peer-reviewed publication, benchmarking against established methods, and statistical validation across subjects and seeds. Gaps to TRL 5 include deployment across 2-3 labs with real network communication. Reaching TRL 6 requires piloting with clinical partners collecting new data, addressing network latency, institutional IT security, heterogeneous resources, and long-term signal stability. Target setting is multi-institutional neuroscience consortia and clinical BCI labs working with paralyzed patients.

---

## Wrap up
FBTTR achieves performance parity with centralized BTTR while enabling privacy-preserving collaboration. FedAvg performs best for tensor regression, while adaptive methods show less consistent performance. ACE can be federated by synchronizing hyperparameters. Tensor decomposition provides computational efficiency (5 minutes vs 14 hours for HOPLS).

Key decisions included using temporal cross-validation to approximate spatial distribution, unweighted aggregation given comparable fold sizes, prioritizing accuracy over differential privacy for proof-of-concept, and excluding ring finger from averages due to co-activation.

Next steps include implementing secure aggregation immediately, deploying across 2-3 partner labs within 6 months, piloting with clinical sites collecting new data within 12 months, and long-term integration into multi-site clinical trial infrastructure.