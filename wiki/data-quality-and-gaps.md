# Data Quality And Gaps

**Summary**: Identified data quality issues in Sidescan Sonar XTF files, including confirmed missing pings, annotation errors, file count discrepancies, and processing pipeline inconsistencies.

**Last updated**: 2026-08-10

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

These cleaning operations improved training focus but introduced metric comparison complications due to ground truth denominator changes. The team must rerun validation predictions on consistent ground truth for valid cross-model comparisons.

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

---

**Sources**: raw/meeting_transcripts/Iris Sync - 2026_06_24; raw/meeting_transcripts/Iris Sync - 2026_07_06; raw/meeting_transcripts/Iris Sync - 2026_07_13; raw/meeting_transcripts/Iris Sync - 2026_07_15; raw/meeting_transcripts/Iris Sync - 2026_07_22; raw/meeting_transcripts/Iris Sync - 2026_07_27 12_29 EDT - Notes by Gemini.md.md; raw/meeting_transcripts/Iris Sync - 2026_08_07 12_16 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_08_10 12_27 EDT - Notes by Gemini.md
