# Sow 1 Milestone 2 Presentation

**Summary**: The milestone deck presents Bedrock and Crescer AI's SSS ATR project status, interim model metrics, runtime results, project roadmap, and data quality issues.

**Last updated**: 2026-07-28

---

## Scope

The deck frames the goal as an onboard model that auto-detects discrete objects in sidescan sonar waterfall swaths, with later re-runs after navigation post-processing and optional batch processing in [[mollusk-platform|Mollusk]] (source: SOW 1 Milestone 2 Presentation.pptx).

The v1 scope includes contacts, pipelines, and wrecks, with outputs of latitude, longitude, and class, and eventual confidence, size, and orientation fields (source: SOW 1 Milestone 2 Presentation.pptx).

Potential hooks include OBR annotation, optional acoustic communications summaries, and an AUV retask signal (source: SOW 1 Milestone 2 Presentation.pptx).

## Project Milestones

The presentation says BRX leadership approved a three-month Crescer AI project with milestones for a sample inference container, an interim model and preliminary metrics report, and a final POC model with Streamlit app, full metrics report, and TX2 smoke test (source: SOW 1 Milestone 2 Presentation.pptx).

## Data And Training

Bedrock is expected to provide SSS data with annotated survey and contact information plus high-value target classifications (source: SOW 1 Milestone 2 Presentation.pptx).

Crescer is expected to conduct EDA, partition the data, augment with existing and synthetic data as needed, and train [[lumen-model|Lumen]] object detection models optimized for lightweight onboard deployment (source: SOW 1 Milestone 2 Presentation.pptx).

The dataset overview estimates about 400 raw XTF files, an 80/10/10 train-validation-test split, about 80 images with labeled contact points, and about 320 background or negative examples (source: SOW 1 Milestone 2 Presentation.pptx). **Note**: the 80/10/10 split was later superseded by an 80/20 train-validation split to reduce statistical noise from the small dataset size (source: Iris Sync - 2026_07_10).

## Interim Metrics

The deck reports baseline model metrics of 212 true positives, 41 false negatives, 0.84 recall, 0.59 precision, and 0.69 F1 (source: SOW 1 Milestone 2 Presentation.pptx).

It also reports that small object filtering improved F1 to 0.73 while reducing recall to 0.80 and improving precision to 0.67 (source: SOW 1 Milestone 2 Presentation.pptx).

Runtime results show 0.917 seconds average per XTF on Jetson Nano, 37% peak CPU, 99% peak GPU, and 3.7 GB RAM plus 2 GB swap peak at batch size 4; the deck expects TX2 performance to be better (source: SOW 1 Milestone 2 Presentation.pptx).

## Data Quality Gaps

The deck identifies missing contacts, invisible contacts, visually similar unlabeled features, low contrast, sand ripples, false negatives, and false positives as improvement areas (source: SOW 1 Milestone 2 Presentation.pptx).

Some contacts may not be identifiable using SSS alone and may need MBES or magnetometer data context (source: SOW 1 Milestone 2 Presentation.pptx).

## Roadmap

The roadmap lists a Q4 2025 Streamlit proof of concept, a Q1 2026 pipeline-on-platform demo, a Q2 2026 pipeline-on-vehicle demo, and Q3 2026 deployment on Bedrock AUVs for online testing and integration (source: SOW 1 Milestone 2 Presentation.pptx).

## Related pages

- [[automated-target-recognition]]
- [[onboard-deployment]]
- [[model-performance-and-metrics]]
- [[synthetic-data-requirements]]
- [[magnetometer-fusion]]
- [[magnetometer-processing-pipeline]]
- [[mollusk-platform]]
- [[lumen-model]]

---

**Sources**: raw/SOW 1 Milestone 2 Presentation.pptx
