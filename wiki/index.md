# Bedrock Wiki Index

**Summary**: Table of contents for the Bedrock x Crescer AI knowledge base.

**Last updated**: 2026-07-29

---

## Source summaries

- [[internal-bedrock-x-crescerai-initial-sow]] - Initial POC scope for SSS ATR, Jetson TX2 delivery, Streamlit prototype, metrics, IP, and open decision points.
- [[sow-1-milestone-2-presentation]] - Interim SOW 1 milestone presentation covering model goals, data, metrics, runtime, roadmap, and data quality gaps.
- [[bedrock-sow-2]] - Follow-on scope for expanded SSS ATR, synthetic data, onboard integration support, UXO-style targets, and magnetometer fusion.
- [[bedrock-meeting-transcripts-summary]] - Consolidated summary of 27 internal and Bedrock meeting transcripts from June 12 through July 29, 2026.
- [[bedrock-discussion-eval-agent-2026-07-28]] - July 28 strategy shift: open-source base data, LLM-as-judge procedural generation, EMD transition, VAE exploration, Ulysses dataset issues, and no-assumption data policy.
- [[iris-sync-2026-07-29]] - July 29 sync: V4 Focal Dice loss, standardized K-fold splits across GPUs, diffusion anti-leakage split, latent inpainting trick, and image-domain augmentations (Poisson blending, mean pixel rule).

## Concepts

- [[automated-target-recognition]] - ATR goals, model scope, outputs, datasets, and evolution from SSS-only detection toward richer onboard use.
- [[onboard-deployment]] - Jetson, container, TensorRT, PNG input, and AUV integration requirements.
- [[model-performance-and-metrics]] - Precision, recall, F1, false negatives, runtime, resource utilization, and metric issues discovered during training.
- [[model-training-and-iterations]] - Architecture comparisons, classification strategy, data splitting, class merging, and benchmarking decisions.
- [[synthetic-data-requirements]] - SOW requirements, client approvals, and forward-modeling specifications for synthetic sonar and magnetometer data.
- [[sss-augmentation-methods]] - Practical implementation of SSS image augmentations, Poisson blending, diffusion models, and rare-class handling.
- [[magnetometer-fusion]] - Planned SSS-mag fusion milestones, onboard data availability, training data strategy, and unresolved methodology decisions.
- [[magnetometer-processing-pipeline]] - Bedrock's OBF format, despiking workflow, ambient vs. residual separation, analytical signal, 5/10 nT thresholds, and anomaly picking.
- [[data-sets-and-curation]] - Catalog of VW, ANTX, DRN, POE, and port datasets with annotation status and curation decisions.
- [[data-quality-and-gaps]] - Confirmed XTF data gaps, annotation quality issues, file count discrepancies, and multi-beam processing notes.
- [[data-rights-and-ip]] - Data ownership, deliverables ownership, license restrictions, and SOW 2 non-compete constraints.
- [[lumen-model]] - Crescer AI's object detection model line used for Bedrock SSS ATR.
- [[mollusk-platform]] - Bedrock's batch processing platform for post-survey sonar data reprocessing.

---

**Sources**: raw/Internal Bedrock x CrescerAI Initial SOW.md; raw/SOW 1 Milestone 2 Presentation.pptx; raw/Bedrock SOW 2.md; raw/meeting_transcripts/ (27 transcripts through July 29, 2026)
