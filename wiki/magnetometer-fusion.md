# Magnetometer Fusion

**Summary**: Magnetometer fusion is the SOW 2 path from SSS-only ATR toward joint SSS and mag inputs, synthetic mag data, and ferrous/non-ferrous evaluation. Processing pipeline details are documented in [[magnetometer-processing-pipeline]].

**Last updated**: 2026-07-17

---

## Motivation

The milestone deck notes that some contacts may not be identifiable using SSS alone and may need MBES or magnetometer data context (source: SOW 1 Milestone 2 Presentation.pptx).

SOW 2 expands the engagement to include magnetometer data alongside sidescan sonar data (source: Bedrock SOW 2.md).

## Onboard Data Availability

For onboard AUV inference, the data available is likely raw_raw (uncompensated, unfiltered). The despiking filter may be feasible to replicate onboard, but coefficient compensation presents a significant challenge as it requires vehicle-specific calibration parameters (source: Bedrock__Crescer_ Mag Discussion - 2026_07_01). The onboard mag processing approach remains open (source: Iris Sync - 2026_07_03).

## Training Data Strategy

The team decided to start with filtered (calibrated, despiked) magnetometer data as the primary baseline for training, reserving raw data investigation for future requirements (source: Iris Sync - 2026_07_03). Thresholds of 5 nT for attention and 10 nT for confirmed targets are used (source: Bedrock__Crescer_ Mag Discussion - 2026_07_01 and source: Iris Sync - 2026_07_03).

Preliminary dipole interference analysis on DR data showed blue markers where amplitude spikes aligned with dipole interference, though the team was advised to confirm reliability across different regions (source: Iris Sync - 2026_07_03).

## Dataset-Specific Challenges

DRN data presents particular challenges: the targets are non-highly-ferromagnetic and physically small, so current results do not meet the 5 nT attention or 10 nT target thresholds (source: Iris Sync - 2026_07_13). AUV altitude and dataset constraints may limit the magnetic signal viability, requiring independent investigation (source: Iris Sync - 2026_07_13).

## MVP Scope

SOW 2 Milestone 3 defines a fusion architecture using SSS and mag data as joint model inputs, trained on Bedrock-provided co-registered SSS and mag datasets (source: Bedrock SOW 2.md).

The MVP includes synthetic mag data, benchmarking on TX2, detection comparison against an SSS-only baseline, ferrous versus non-ferrous discrimination evaluation, and a feasibility report (source: Bedrock SOW 2.md).

## Hardening

SOW 2 Milestone 4 addresses robustness gaps found in Milestone 3, refines synthetic mag data, validates onboard TX2 performance with the mag channel active, and recommends future architecture and training strategy (source: Bedrock SOW 2.md).

## Reproducing Filtered Data From Raw

Ratul Shashank's pipeline can replicate Bedrock's filtered magnetometer anomaly detections using only raw data and a despiking filter, without Bedrock's offline calibration coefficients. This is surprising to Geoff, who expected the offline calibrations to be necessary, but the finding is tentatively accepted. The amplitude values are 2-2.5x higher than Bedrock's, but the locations align. The takeaway is that raw mag data may be feasible for onboard processing if the relative signal is sufficient, though this needs further validation (source: Aux Discussion Mag Data - 2026_07_17).

## Open Decisions

SOW 2 leaves co-registration methodology, synthetic mag forward model specification, mag channel input specification, and preprocessing requirements as joint decision points (source: Bedrock SOW 2.md).

Whether to use raw or filtered magnetometer data for onboard processing remains unresolved (source: Iris Sync - 2026_07_03 and source: Bedrock__Crescer_ Mag Discussion - 2026_07_01).

## Related pages

- [[automated-target-recognition]]
- [[synthetic-data-requirements]]
- [[model-performance-and-metrics]]
- [[data-rights-and-ip]]
- [[magnetometer-processing-pipeline]]

---

**Sources**: raw/SOW 1 Milestone 2 Presentation.pptx; raw/Bedrock SOW 2.md; raw/meeting_transcripts/Bedrock__Crescer_ Mag Discussion - 2026_07_01; raw/meeting_transcripts/Iris Sync - 2026_07_03; raw/meeting_transcripts/Iris Sync - 2026_07_13; raw/meeting_transcripts/Aux Discussion Mag Data - 2026_07_17
