# Next Steps

**Summary**: Active action items, decisions, and upcoming milestones from team discussions through July 28, 2026.

**Last updated**: 2026-07-28

---

## Model & Metrics

- **Project Baseline**: Updated dataset (with VW phase 2 data) serves as the project baseline for all future comparisons. [--> What is the action item here??
- **Pixel Threshold Filter**: Filter at 100px documented as primary improvement driver (~20% precision-recall gain without losing true positives). [--> I don't think this was fixed. The latest was that Sachin was looking into adaptable size limits based on the classification type. 100px might be a fallback? But also might be too big for UXOs.
- **V4 Model & Penalty Weighting**: Deployed V4 model with adjusted false-positive penalty weights to resolve UXO/AI Small class imbalance; scheduled for Streamlit app integration [Sachin]. [Status: --> implemented in v4. false-positive rate went much lower ]
- **512px Resolution Standard**: 512-pixel input resolution adopted as standard after hyperparameter search confirmed it consistently outperforms 256-pixel inputs.
- **Augmentation Combination**: Poisson blending + roll + cutmix established as top performing augmentation combo (object F1 of 0.49 @ 20% IOU). [--> Confirm that cutmix is the only synth being used in training.
- **Object Metric Fix**: Fixed calculation error where large objects ("AOI big") with ~80% pixel overlap were fragmented into separate annotations, deflating F1 [Sachin]. [--> confirm sachin fixed this.
- **K-Fold Spatial Partitioning**: K-fold cross-validation with manual spatial splits adopted to prevent data leakage from geographic tile overlap. [--> implemented, training started, results not discussed yet.
- **UXO / Small Black Class Merging**: Merging UXO and AOI small black into a single class during training to maximize signal and boost UXO recall, while retaining separate classes for evaluation. [--> have not yet discussed results
- **Client Recall Preference**: Optimization aligned to prioritize recall over precision (accepting false positives to prevent missed contacts) per client feedback. [Status: resolved item.]
- **Training Data Cleaning**: Remove non-essential "footprint discoloration" annotations (Annotation 2) causing false positives and add missing valid targets [Sachin]. [Status: In Progress]
- **GitHub Model Version Tracking**: Maintain running collapsible history of model versions, specs, and dataset configs on GitHub for transparent tracking and LLM agent queries [Geoff & Hemanth].

---

## Synthetic Data & LLM Evaluation Loop

- **Dataset Deduplication**: Clean 10–15 duplicate files per location across DRN, Port, POE, and VW datasets to eliminate data bottlenecks stalling augmentation gains [Pratyaksh]. [which meeting was this from? Is this stale?]
- **Open-Source Base Data Strategy Shift**: Shift from modifying Bedrock data to using ~300k open-source image dataset as base for procedural target generation. [--> this is not true. This shift did not happen]
- **Open-Source Research Paper Review**: Share and review paper for ~300k open-source sonar image dataset [Pratyaksh]. [already shared. No longer open item.]
- **LLM-as-Judge Evaluation Framework**: Implement LLM judge (0.9 target score threshold) augmented with AlexNet perceptual loss and detection metrics to score synthetic image distribution fit.
- **Procedural Generation Frameworks**: Test hill-climbing optimization and VAE/diffusion reconstruction loops with on-device heuristics to bypass token limitations [Hemanth & Pratyaksh].
- **Earth Mover's Distance & Frequency Domain Testing**: Test Earth Mover's Distance (EMD) and frequency domain transforms to isolate non-linear image components [Pratyaksh].
- **VAE Pre-Training Exploration**: Pre-train VAE/diffusion models on open-source data and evaluate feasibility [Pratyaksh].
- **Interactive Validation Agent Loop**: LLM Validation Agent loop comparing synthetic images against reference data using similarity metrics (80% threshold) [Sachin].
- **False Positive Augmentations**: Incorporate rotated, scaled, and morphed annotations as false positives to improve background precision. [Sachin discussed this as an option, but probably an irrelevant idea. can discount implementation.]
- **25 Pixel-Based Color Augmentations**: Share HTML repo of augmentation data on Slack as fallback strategy [Sachin].

---

## Data Management & Documentation

- **Centralized Skills Repository**: Create team repository for documenting and sharing skills and technical resources.
- **Ulysses Dataset Analysis & No-Assumption Policy**: Conduct empirical analysis of Ulysses dataset for rotation/flip/convention variations before drawing data quality conclusions [Sachin]. [remove Ulysses tracking]
- **Data Variation Slack Channels**: Initialize dedicated Slack channels for Ulysses and data variation discussions [Sachin & Geoff]. [remove Ulysses tracking]
- **Documentation Formalization**: Formalize documentation with dated entries, links to reports, TL;DR rationale, results, and proposed next steps [Sachin]. [--> Check that sachin is updating the running list]
- **Mandatory Code Backup Policy**: Enforce policy requiring all training, fine-tuning, and project code to be committed and backed up to GitHub.
- **Validation Set Image Retention**: Retain all validation images (including long/zoomed-out views) for statistical reliability.
- **Client Label Verification**: Send image samples of ambiguous small black / UXO targets to Bridget for client label verification.

---

## Magnetometer Processing (MAG)

- **2-Pane Visualization**: Create 2-pane visualization comparing MAG amplitude with XTF imagery, with amplitude peak location markers [Ratul].
- **MAG Pipeline Full Run**: Run Ratul's mag pipeline across all annotated Bedrock datasets to generate per-class precision/recall and true/false positive tables [Ratul].
- **Location Accuracy Baseline**: Maintain 5-10 m location accuracy baseline.

---

**Sources**: raw/meeting_transcripts/Iris Sync - 2026_07_20 12_30 EDT - Notes by Gemini.md; raw/meeting_transcripts/Meeting started 2026_07_23 15_29 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_07_24 12_29 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_07_27 12_29 EDT - Notes by Gemini.md.md; raw/meeting_transcripts/Bedrock Discussion Continued (understanding eval agent) - 2026_07_28 11_59 EDT - Notes by Gemini.md
