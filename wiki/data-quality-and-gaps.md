# Data Quality And Gaps

**Summary**: Identified data quality issues in Sidescan Sonar XTF files, including confirmed missing pings, annotation errors, file count discrepancies, and processing pipeline inconsistencies.

**Last updated**: 2026-08-14

---

## XTF Data Gaps

Black strip artifacts in processed sonar images were traced to missing pings in the underlying XTF files (source: Iris Sync - 2026_06_24). Ratul Shashank confirmed by running a time-series analysis showing that timestamps do not correlate with ping numbers in affected regions — some ping intervals are five times the median duration, indicating missing data (source: Iris Sync - 2026_06_24).

The gaps were confirmed as real data collection failures, not processing artifacts. The estimated ground loss per missing ping is on the order of a few centimeters (source: Iris Sync - 2026_06_24).

Open-source tools like OpenSideScan do not reveal these gaps because they stack pings sequentially on the Y-axis rather than georeferencing them, so missing pings are simply skipped (source: Iris Sync - 2026_06_24).

Whether these gaps appear in the low-pass XTF data was raised as an open question requiring verification (source: Iris Sync - 2026_06_24).

## Annotation Quality

Annotation quality was identified as the primary limiting factor for model performance (source: Iris Sync - 2026_07_15). Specific issues:
- Over-annotation: Labelers marking objects (e.g., sand ripple) where the features are not confidently identifiable (source: Iris Sync - 2026_07_15)
- Boundary precision: Labelers had poor boundaries on annotations, contributing to higher training loss (source: Iris Sync - 2026_07_15)

The fix was to have labelers review and correct existing annotations by comparing model predictions against their original labels, selecting the better annotation to speed the process (source: Iris Sync - 2026_07_15). Focus was placed on keeping only objects with strong, well-defined features (source: Iris Sync - 2026_07_15).

## File Count Discrepancy

Original VW dataset contained 463 files, but only approximately 345 files appeared after processing (see [[data-sets-and-curation#vw-vineyard-winds]]) (source: Iris Sync - 2026_07_15). Suspected cause: incomplete unzipping process, pending investigation (source: Iris Sync - 2026_07_15).

## Data Organization

A lack of systematic dataset archiving made it difficult to identify which annotation iterations were correct (source: Iris Sync - 2026_07_15). The team adopted a "paranoid" approach to logging dataset paths and configurations (source: Iris Sync - 2026_07_15).

## Later Data Cleaning

Significant annotation cleaning was performed after the initial quality assessment:
- Approximately 1,300 noisy small black patch point annotations (Annotation 2) were removed from the training dataset by Sachin Pandey on July 22. This altered the ground truth count and required rerunning validation predictions for valid metric comparison (source: Iris Sync - 2026_07_22)
- On July 27, Sachin Pandey conducted further training data cleaning by removing non-essential "footprint discoloration" annotations that caused spurious false positive predictions, while ensuring missed valid annotations were added (source: Iris Sync - 2026_07_27)
- On August 7, the team discovered that poor baseline performance on artificial copy-paste evaluation sets was caused by un-annotated pre-existing UXO contacts on base images rather than model detection failures (source: Iris Sync - 2026_08_07)
- On August 10, false positive error analysis on the high-recall V4 model revealed that many flagged false positives are genuine un-annotated UXO contacts or missed `AOI small black` targets. Ground truth labeling omission error was estimated at ~1–5%, prompting a final rapid re-labeling pass (source: Iris Sync - 2026_08_10)
- On August 12, Sachin completed the ground truth cleaning pass by integrating approximately 80 mined UXO-resembling targets into the `AOI small black` training annotations (source: Iris Sync - 2026_08_12)

These cleaning operations improved training focus but introduced metric comparison complications due to ground truth denominator changes. The team must rerun validation predictions on consistent ground truth for valid cross-model comparisons.

## K-Fold Crop Duplication & Data Leakage (August 12)

Investigation into cross-validation metric anomalies uncovered data leakage at the image crop level during 5-fold spatial partitioning (source: Iris Sync - 2026_08_12):
- **Duplication & Annotation Asymmetry**: Certain image crops were repeated across folds such that a file possessed ground truth masks in one fold but lacked annotations in another, causing training and validation sets to overlap and corrupting cross-validation metrics.
- **Remediation**: Initial estimates indicated ~14% file repetition across folds. Sachin initiated a 24-hour fix to correct the crop-generation pipeline prior to retraining models across folds.

## Evaluation Script Class Merging Bug & Rocky Seafloor False Positives (August 14)

Quality issues and domain gaps identified during the August 14 sync (source: Iris Sync - 2026_08_14):
- **Evaluation Metric Script Class Merging**: A previously reported 90%+ F1 score on the 80/20 train/validation split was found to be artificially inflated because the evaluation script inadvertently merged `AOI big` and `black patch` into a single class alongside `UXO` + `AOI small black`. Separating non-UXO classes and generating clean 4-bucket confusion matrices resolved the calculation anomaly.
- **Treasure Island Rocky Terrain Domain Shift**: Sonar inference on the Treasure Island dataset revealed increased false positive rates on rocky seafloor topography. Natural rock formations produce acoustic highlights, curves, and dark shadows that visually mimic UXO morphologies, highlighting an underrepresentation of rocky terrain in the original training data.

## Multi-Beam Processing

For the S7k/MBES data:
- A 60-degree edge filtering threshold is applied to remove swath edges where uncertainty is higher (source: Iris Sync - 2026_07_06)
- S7K file processing showed a 6 cm deviation in replication, with sound velocity profiles suggested as a potential fix (source: Iris Sync - 2026_07_13)

## Related pages

- [[data-sets-and-curation]]
- [[model-training-and-iterations]]
- [[model-performance-and-metrics]]
- [[magnetometer-processing-pipeline]]
- [[bedrock-meeting-transcripts-summary]]
- [[iris-sync-2026-08-10]]
- [[iris-sync-2026-08-12]]
- [[iris-sync-2026-08-14]]

---

**Sources**: raw/meeting_transcripts/Iris Sync - 2026_06_24; raw/meeting_transcripts/Iris Sync - 2026_07_06; raw/meeting_transcripts/Iris Sync - 2026_07_13; raw/meeting_transcripts/Iris Sync - 2026_07_15; raw/meeting_transcripts/Iris Sync - 2026_07_22; raw/meeting_transcripts/Iris Sync - 2026_07_27 12_29 EDT - Notes by Gemini.md.md; raw/meeting_transcripts/Iris Sync - 2026_08_07 12_16 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_08_10 12_27 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_08_12 12_27 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_08_14 12_30 EDT - Notes by Gemini.md
