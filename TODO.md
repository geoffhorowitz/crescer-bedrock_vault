# Project TODOs

This file tracks open technical challenges, research items, and implementation gaps in the Bedrock ATR project.

## Sonar Modeling & Processing

### 1. Multi-Class vs. Binary Model Outputs
- **Issue**: There is ambiguity regarding whether Bedrock requires a multi-class model (separating various anomaly types) or a single-class binary detection output. Training logs show binary models currently underperform compared to multi-class configurations.
- **Proposed Long-term Fix**: Await confirmation from Bedrock via Slack. Retrain the baseline model as binary or multi-class according to client requirements and benchmark both versions to optimize validation metrics.

### 2. Confirm UXO Annotation Toggle
- **Issue**: There is naming and classification confusion between "mine", "UXO", and generic "black patch" labels across datasets. True UXOs are scarce (only 10-11 unique examples).
- **Proposed Long-term Fix**: Implement a separate JSON toggle in the annotation formats to distinguish confirmed UXOs from other small black artifacts. Reclassify ambiguous small black objects to the black patch category in the next training cycle to improve model precision.

### 3. Cross-Dataset Style Transformation
- **Issue**: Sonar image appearances vary significantly across survey areas (e.g., Vineyard Winds vs. Danish Royal Navy). Simple model transfer fails due to out-of-distribution noise, and initial efforts to transform style across datasets have not succeeded.
- **Proposed Long-term Fix**: Investigate style transfer architectures (such as CycleGAN or Contrastive Unpaired Translation) to map VW imagery to DRN/POE distributions, creating a robust evaluation set.

### 4. Jetson Onboard Backbone Selection & Performance Benchmarking
- **Issue**: The model must run onboard the AUV on a Jetson TX2, but backbone selection has been deferred until after initial pipeline benchmarking.
- **Proposed Long-term Fix**: Perform comprehensive runtime profiling (latency, memory utilization, throughput) of YOLOv8 and U-Net variants on a physical Jetson TX2. Select the backbone that maximizes F1 score while staying within onboard power and memory budgets.

## Magnetometer Data Integration

### 5. Magnetometer Pipeline Validation
- **Issue**: The custom raw-data magnetometer processing pipeline reproduces anomaly locations but yields peak amplitudes 2-2.5x greater than Bedrock's filtered values.
- **Proposed Long-term Fix**: Run the pipeline on all annotated Bedrock datasets to generate per-class precision/recall and true/false positive tables. Confirm if relative signals are robust for joint SSS-mag classification.

### 6. Physical Forward Modeling for Synthetic Magnetometer Data
- **Issue**: SOW 2 Milestone 3 requires synthetic magnetometer data, but the pipeline lacks a validated physics-based forward model specification.
- **Proposed Long-term Fix**: Collaborate with Bedrock's domain experts to define the forward model specification, fitting synthetic dipole responses against measured data to accurately simulate target size and burial depth.

## Data Quality & Infrastructure

### 7. VW Dataset File Count Discrepancy
- **Issue**: The processed Vineyard Winds (VW) dataset contains ~345 files instead of the expected 463 files. This is suspected to be due to an incomplete extraction/unzip process.
- **Proposed Long-term Fix**: Audit the raw SOW 1 zip files and re-run the extraction scripts to recover the missing ~118 files, updating the training baseline dataset.

### 8. Server Storage Optimization
- **Issue**: Disk space constraints on the primary server frequently trigger failures in the Volley software, which crashes when disk usage exceeds 75-80%.
- **Proposed Long-term Fix**: Set up automated cron-based cleanup scripts for training checkpoints and log files to prevent storage-related service outages.
