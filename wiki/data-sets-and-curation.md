# Data Sets And Curation

**Summary**: Catalog of datasets used in the Bedrock ATR project, their characteristics, annotation status, and curation decisions.

**Last updated**: 2026-07-29

---

## Dataset Catalog

### VW (Vineyard Winds)

The original dataset from SOW 1. Used as the baseline for all model comparisons and legacy model evaluation. Has well-established annotations and served as the starting point for multi-class labeling experiments (source: Iris Sync - 2026_07_03 and source: Iris Sync - 2026_07_08).

File count discrepancy: originally 463 files, only ~345 visible after processing (see [[data-quality-and-gaps#file-count-discrepancy]]) (source: Iris Sync - 2026_07_15). Note: the milestone deck rounds this to about 400 files (source: SOW 1 Milestone 2 Presentation.pptx).

### ANTX (commonly mislabeled as ENTX in transcripts)

New dataset with labeled features used for both training and validation. Labelers completed annotation of 2 parts, with 1 part remaining (source: Iris Sync - 2026_07_03). *Note*: Referred to as "ENTX" or "ENTx" in Gemini transcripts, but the authoritative dataset name is **ANTX**. ANTX sample sizes are smaller relative to VW, causing spatial metric scaling discrepancies when transferring cropped target objects between datasets (source: Iris Sync - 2026_07_29).

### DRN (Danish Royal Navy)

Characterized by non-highly-ferromagnetic targets and physically small objects that do not meet the 5 nT attention threshold or 10 nT target threshold in magnetometer data (source: Iris Sync - 2026_07_13). Certain regions have no objects or annotations at all (source: Iris Sync - 2026_07_15).

### POE (Port of Espoo)

Used as a background dataset for training. Provides varied backgrounds for testing false positive rates (source: Iris Sync - 2026_07_08). Has good data quality for augmentation testing (source: Iris Sync - 2026_07_15).

### Port Dataset

Additional background dataset lacking annotations. Used as a test set to assess model performance on varied backgrounds and monitor false positives (source: Iris Sync - 2026_07_08).

### Ulysses Dataset

Newly acquired dataset presented by Sachin Pandey on July 28 showing unexpected patterns: varying shades and shapes rather than the expected consistent shading. The team advised investigating potential rotation, flip, or convention discrepancies before concluding the data is inherently flawed. Policy established to avoid assumptions about data conventions (rotation, axis orientation) when processing new datasets (source: Bedrock Discussion Continued (understanding eval agent) - 2026_07_28).

### Open-Source Base Dataset (~300k Images)

Pratyaksh identified an open-source dataset of approximately 300k images to serve as a base for synthetic generation rather than modifying existing Bedrock data. The research paper describing this dataset is pending review (source: Bedrock Discussion Continued (understanding eval agent) - 2026_07_28).

## Curation Decisions

### UXO Versus Mine Classification Confusion

Significant confusion exists between "mine" and "UXO" labels across the dataset. The one AOI mine example found by Pratyaksh was classified inconsistently across labeling iterations — previously put into the "other" category. Sachin marked it as mine because open-source data showed similar-looking objects as mines. Geoff notes that not all AOI small black objects are UXOs, and the distinction is important. Sachin plans to add a separate JSON file that toggles to show confirmed UXOs, since most UXO objects are in the ENTX and DRN datasets and typically appear as small black spots rather than elongated shapes (source: Iris Sync - 2026_07_17).

### UXO Naming Convention

UXO naming convention requires further discussion before formalizing in reports. The features defining a UXO vary across different datasets, making a unified definition challenging (source: Bedrock connect - 2026_07_17).

### Black Patch Reclassification

Small black artifacts that resemble black patches will be moved to the black patch category in the next labeling and training cycle to improve model classification (source: Bedrock connect - 2026_07_17).

### Sand Patch Annotation Strategy

Two options for sand patch annotations: drop them entirely or merge them with sand ripples. Goal is to improve object-wise classification, as sand patches often closely resemble black patches and cause confusion (source: Iris Sync - 2026_07_20).

### Development Prioritization: UXO and Black Patches Over Sand Ripples

Development focus prioritized toward UXO and small black patch data. Sand ripples deprioritized because the client does not prioritize them (source: Iris Sync - 2026_07_20).

### Centralized Data Reference List

The team previously lacked a centralized reference list for all open-source and raw datasets. Sachin Pandey tasked to compile this reference list in the project tracker, including source URLs and metadata fields. Geoff Horowitz to handle VW phase 2 data transfer on SFTP (source: Iris Sync - 2026_07_20).

### Updated Dataset As Project Baseline

The updated dataset (with fixes and additional VW phase 2 data) is now the project baseline for all future comparisons. This replaces the static historical baseline, even though updating the baseline can complicate tracking of model improvements (source: Iris Sync - 2026_07_20).

### Geographic Splitting

Training and validation splits are made by geographic proximity using latitude/longitude coordinates, not random selection (source: Iris Sync - 2026_07_10). Polygons drawn around data regions to verify no overlap (source: Iris Sync - 2026_07_15).

### Class Count Reduction

The team reduced class count by removing non-essential classes. The noise class was eliminated because it was not present in the validation set. Several visually similar artifact classes were merged (source: Iris Sync - 2026_07_15).

### Open-Source Data Exclusion

Open-source sonar data was evaluated and excluded from training due to annotation format mismatch (bounding boxes instead of masks), high variability, and out-of-distribution noise (source: Iris Sync - 2026_07_10). Retained as a backup option. **Later superseded** by the open-source base-data strategy (see below), which re-examines open-source data as a synthetic generation base rather than direct training input.

The sand ripple data from open-source sources was handled separately and included in training because it has strong features and was easy to predict (source: Iris Sync - 2026_07_10).

### "Probable UXO" Category Inclusion

The team created a dedicated "Probable UXO" class to accommodate ambiguous objects that visually resemble UXO but were previously classified as small black patches or removed. Retaining these objects under a probable classification prevents loss of training signals and improves recall (source: Iris Sync - 2026_07_22).

### Training Data Cleaning (Removal of ~1,300 Annotations)

Sachin Pandey removed approximately 1,300 noisy or small black patch point annotations from the training dataset. This cleanup focused the model on distinct targets, though it altered the ground truth count and required careful metric alignment across validation sets (source: Iris Sync - 2026_07_22).

### Manual Spatial Partitioning for K-Fold Cross-Validation

Geographic tile overlap between sonar imagery passes prevents naive automatic random splitting for K-fold cross-validation. Data tiles must be manually partitioned into spatially distinct regions to eliminate data leakage across folds (source: Iris Sync - 2026_07_22).

### UXO Morphology Discrepancy (Pits vs Cylinders)

Analysis of false negatives revealed a structural difference in target appearance: open-source mine data typically features cylindrical objects with clear acoustic shadows, whereas Bedrock's UXO targets in side-scan sonar frequently appear as pits or depressions in the seabed (source: Iris Sync - 2026_07_22).

### Dataset Transformation

Exploration of transforming VW data to resemble DRN or POE appearance to create a robust evaluation set. If successful, well-labeled VW data could serve as a strong test set (source: Iris Sync - 2026_07_03).

### Heavy File Duplication Across Datasets

Analysis presented by Pratyaksh Singh revealed significant file duplication across existing datasets (DRN, POE, Port, VW), with 10 to 15 duplicate files recorded per location. This duplication causes model overfitting and limits the effectiveness of data augmentations, confirming that performance bottlenecks stem from dataset quantity and geographic diversity rather than lack of augmentations (source: Iris Sync - 2026_07_24).

### Client Label Verification Workflow

To refine ground truth annotations, the team will prepare image samples of annotated UXOs and AOI small black objects for Bridget to verify and correct, reducing annotation error risks prior to formal milestone demonstrations (source: Iris Sync - 2026_07_24).

### Validation Set Image Retention Policy

The team established a policy to retain all provided images in the validation set—including long, zoomed-out, or distant views—to maintain comprehensive testing integrity (source: Iris Sync - 2026_07_24).

### No-Assumption Policy for New Datasets

The team established a policy to avoid making assumptions about data conventions (rotation, axis orientation, coordinate systems) when processing newly acquired datasets. Instead, the base structure should be investigated empirically before drawing conclusions about data quality or content. This was prompted by issues with the Ulysses dataset (source: Bedrock Discussion Continued (understanding eval agent) - 2026_07_28).

### Open-Source Base-Data Strategy

The team shifted strategy for synthetic data generation: instead of modifying existing Bedrock data (which produces outputs indistinguishable from standard augmentations), the new approach uses open-source data (~300k images) as a base and converts it to the target distribution using a procedural generation pipeline with an LLM judge (source: Bedrock Discussion Continued (understanding eval agent) - 2026_07_28).

### Standardized Patch Sizing & Directory Alignment (July 29)

The team standardized data preparation across VW, ANTX, and DRN datasets:
- **Patch Sizes**: Image patches standardized to 128x128 and 256x256 pixel dimensions.
- **Mask Format**: Annotation masks formatted and saved as PNG files (`0`/`1` mask values).
- **Directory Layout**: Train and validation folder structures aligned across all datasets to support automated loading in diffusion and classification pipelines (source: Iris Sync - 2026_07_29).

## Related pages

- [[model-training-and-iterations]]
- [[synthetic-data-requirements]]
- [[sss-augmentation-methods]]
- [[data-quality-and-gaps]]
- [[bedrock-meeting-transcripts-summary]]
- [[iris-sync-2026-07-29]]

---

**Sources**: raw/meeting_transcripts/Iris Sync - 2026_07_03; raw/meeting_transcripts/Iris Sync - 2026_07_06; raw/meeting_transcripts/Iris Sync - 2026_07_08; raw/meeting_transcripts/Iris Sync - 2026_07_10; raw/meeting_transcripts/Iris Sync - 2026_07_13; raw/meeting_transcripts/Iris Sync - 2026_07_15; raw/meeting_transcripts/Iris Sync - 2026_07_17; raw/meeting_transcripts/Bedrock connect - 2026_07_17; raw/meeting_transcripts/Iris Sync - 2026_07_20; raw/meeting_transcripts/Iris Sync - 2026_07_22; raw/meeting_transcripts/Iris Sync - 2026_07_24; raw/meeting_transcripts/Bedrock Discussion Continued (understanding eval agent) - 2026_07_28 11_59 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_07_29 12_26 EDT - Notes by Gemini.md
