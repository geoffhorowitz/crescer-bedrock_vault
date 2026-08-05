# Bedrock Meeting Transcripts Summary

**Summary**: Consolidated summary of 30 internal and Bedrock meeting transcripts from June 12 through August 5, 2026, covering model training progress, data pipeline decisions, magnetometer processing, milestone planning, hyperparameter benchmarking, data cleaning impacts, K-fold validation, UXO/AOI class merging, Flux Turbo LoRA synthetic generation, V4 false-positive penalty weighting, LLM validation agent loops, July 28 strategy shift, July 31 latent diffusion/pixel crops, August 3 Milestone 2 closure & geographic K-fold splits, and August 5 100m geo-grid K-fold partitioning & generative image decomposition.

**Last updated**: 2026-08-05

---

## Timeframe and Sources

This page synthesizes 30 meeting transcripts spanning from June 12, 2026 through August 5, 2026:
- 23 weekly Iris Sync meetings (internal Crescer standups through August 5, 2026)
- 1 Bedrock discussion continuation (June 23, 2026)
- 1 Bedrock magnetometer discussion with Francisco Bolivar (July 1, 2026)
- 1 Bedrock connect meeting (July 17, 2026)
- 1 Aux Discussion Mag Data meeting (July 17, 2026)
- 1 technical review meeting (July 23, 2026)
- 1 Bedrock discussion: understanding eval agent and synthetic data strategy (July 28, 2026)

## Key Track During This Period

### Milestone Timeline

A 4 to 6 week timeline was established for the current milestone deliverables (source: Iris Sync - 2026_07_06). The team confirmed that prioritizing image data for current milestones takes precedence over secondary detection signals (source: Iris Sync - 2026_07_06).

### Model Training Iterations

Training progressed through multiple iterations comparing U-Net (ResNet-50) against YOLOv8 architectures (source: Iris Sync - 2026_07_06). A key decision was made to reduce class count by removing the noise class and merging visually similar classes (black patch, AOI support artifacts) to cut non-essential classes and improve accuracy (source: Iris Sync - 2026_07_03).

Classification strategy settled on initially keeping objects in separate classes to maintain data granularity, with the option to merge later if needed (source: Iris Sync - 2026_07_15). A debate on multi-class versus binary output led to a decision to clarify with the client on Slack (source: Iris Sync - 2026_07_08).

The team adopted a standardized model naming convention including model name, date, dataset, and configuration (source: Iris Sync - 2026_07_13).

### Pipeline Benchmarking

The legacy pipeline was run on new datasets to establish a performance benchmark (source: Iris Sync - 2026_07_10). An early error was discovered: the background class was incorrectly included in metric calculations, distorting results, requiring model retraining (source: Iris Sync - 2026_07_10).

Open-source data was evaluated and excluded from the training baseline due to out-of-distribution noise (bounding boxes instead of required masks, highly variable samples), though retained as a backup option (source: Iris Sync - 2026_07_10).

### Data Split Strategy

The team moved from a three-way train/validation/test split to an 80/20 or 90/10 split to mitigate noise from small dataset size (source: Iris Sync - 2026_07_10). A geographically distinct test set was created using latitude/longitude coordinates to prevent data leakage from geographic overlap (source: Iris Sync - 2026_07_08 and source: Iris Sync - 2026_07_10). Overlapping regions between training and test sets were explicitly prohibited (source: Iris Sync - 2026_07_13).

### Datasets

Multiple datasets were actively used and discussed:
- **VW (Vineyard Winds)**: The original dataset, used for baseline comparison and legacy model evaluation
- **ENTX**: New dataset with labeled features for training
- **DRN (Danish Royal Navy)**: Noted as having no objects/annotations in certain regions; non-highly-ferromagnetic, small objects that did not meet detection thresholds
- **POE (Port of Espoo)**: Used as background dataset for training and testing false positives on varied backgrounds
- **Port dataset**: Additional background dataset lacking annotations, used as test set for false positive monitoring

### Data Quality

Data quality and annotation cleanliness were identified as the primary bottleneck (source: Iris Sync - 2026_07_15). Labelers were instructed to correct annotations by comparing model predictions against manual labels to speed the process (source: Iris Sync - 2026_07_15). A file count discrepancy was discovered: originally 463 files, only ~345 present after processing, suspected to be from an incomplete unzip process (source: Iris Sync - 2026_07_15).

### Labeling Bottleneck

Manual labeling was identified as the current bottleneck (source: Iris Sync - 2026_07_03). Gamification of the labeling process was suggested to increase labeler engagement (source: Iris Sync - 2026_07_03).

### Agentic Systems

The team explored building a secure containerized agentic operating system to synthesize meeting data and tribal knowledge (source: Iris Sync - 2026_07_10). A product requirements document was proposed to formalize the architecture (source: Iris Sync - 2026_07_10). An agent-based experimentation pipeline was proposed where agents use seed papers to source, test, and integrate model improvements (source: Iris Sync - 2026_07_03).

### Reporting Standards

Geoff Horowitz pushed for consistent, sharable reports documenting dataset sizes, training progress, and results (source: Iris Sync - 2026_07_10). Reports were to be exported as documents for easier review and commenting (source: Iris Sync - 2026_07_13).

### Infrastructure

- Storage constraints on the primary server required cleanup of old checkpoints (source: Iris Sync - 2026_07_13)
- Volley software stops functioning when storage reaches 75-80% capacity (source: Iris Sync - 2026_07_06)
- Evaluation rejected purchasing additional GPUs since the primary bottleneck is data availability, not compute (source: Iris Sync - 2026_07_15)
- Backbone selection for Jetson compatibility was deferred until after initial benchmarks (source: Iris Sync - 2026_07_13)

## July 17 Updates

### IOU Threshold Reporting

The team established a dual-threshold reporting strategy: results will be reported at both 0.1 and 0.5 Intersection Over Union (IOU). The 0.1 IOU yielded a metric of 0.866 (rounded to 0.87). The rationale is that even a single pixel of overlap indicates the model identified the object's presence, which is a useful metric for client interactions. Both thresholds will appear in baseline reporting (source: Bedrock connect - 2026_07_17).

### Ground Truth Count Adjustment

Ground truth object count adjusted from 256 to 253 between milestones 2 and 3 (source: Bedrock connect - 2026_07_17).

### UXO Scarcity and Classification Confusion

Confirmed only 10-11 unique UXO objects across the entire dataset. Bridget (Bedrock) is unlikely to have more UXO data available to share. Significant confusion exists between "mine" and "UXO" labels: the one AOI mine example found by Pratyaksh was classified inconsistently across labeling iterations. Sachin plans to add a separate JSON toggle to clearly mark which objects are confirmed UXOs versus other small black artifacts (source: Iris Sync - 2026_07_17).

### Synthetic Augmentation Progress

Completed work as of July 17:
- Copy-paste augmentation: done
- Synthetic mine example generation: done (cylindrical objects with shadow, sine-wave pattern added in image space)
- Roll-like artificial data: done
- Cross-dataset transformation (one dataset style to another): no success yet

Virtual sensor parameter experiments (Ratul Shashank): altitude and speed changes produce visible image differences; roll changes do not visibly affect mosaics because the XTF-to-image conversion does not use roll data. XTF files in ENTX and VW show sensor speed of zero, while DRN and POE consistently show ~2 m/s (source: Iris Sync - 2026_07_17).

### Open-Source Data Strategy Shift

Pratyaksh proposed a new strategy for leveraging open-source sonar data: use broad open-source data for pre-training the model, then fine-tune on the smaller Bedrock dataset. This mirrors large language model pre-training pipelines. Open-source data should be categorized by quality (high: similar to Bedrock; medium: convertible; low: completely different). Generative AI (Flux models) should be used with Bedrock data only to avoid setting client expectations about open-source data performance (source: Iris Sync - 2026_07_17).

### Magnetometer Amplitude Discrepancy

Ratul's pipeline reproduces Bedrock's filtered results from raw data without requiring offline calibrations, but peak amplitudes are 2-2.5x greater than Bedrock's values at the same locations. Geoff expresses skepticism but tentatively accepts the finding. The relative signal presence is considered sufficient as a decision factor, even if absolute values differ (source: Aux Discussion Mag Data - 2026_07_17).

### Magnetometer: Multiple Passes Purpose

Multiple survey passes reduce measurement uncertainty rather than compensating for vehicle magnetic field (which is handled during a dedicated calibration step on flat, object-free seabed). Geoff disagrees with Ratul's initial understanding that repeated passes remove vehicle and geological noise (source: Aux Discussion Mag Data - 2026_07_17).

### Magnetometer: Mag As Decision Factor, Not Filter

Geoff emphasizes that mag data should not be used as a binary filter to narrow the search area, because non-ferrous objects and buried targets may not produce detectable mag signatures. Instead, mag data serves as an additional input channel that adjusts confidence scores (source: Aux Discussion Mag Data - 2026_07_17).

### Magnetometer: Next Steps

Run Ratul's pipeline on all annotated Bedrock data to generate per-class precision/recall tables. Use altitude as an algorithm input (e.g., attenuating thresholds at higher altitude) rather than segregating data by altitude bands, which would introduce look-ahead bias (source: Aux Discussion Mag Data - 2026_07_17).

### S7K Multi-Beam Z-Axis Direction

The Z-axis in S7K/MBES point cloud data is positive downward: the ship is at zero, and increasing depth yields more positive Z values. This resolved confusion about whether the output data seemed to place points above sea level (source: Aux Discussion Mag Data - 2026_07_17).

### S7K Sound Velocity Profile

Using the sensor speed datagram from the S7K file instead of a constant 1500 m/s for sound velocity reduces positional deviation from ~8 cm to under 6 cm against the reference LAS file (source: Aux Discussion Mag Data - 2026_07_17).

### Data Exclusions Must Be Documented

Geoff emphasized that any data excluded from training or testing must have the reasoning documented to prevent information loss across the team (source: Bedrock connect - 2026_07_17).

### Black Patch Reclassification

Sachin plans to move ambiguous small black artifacts to the black patch category and adjust AOI support classification in the next training cycle (source: Bedrock connect - 2026_07_17).

## July 20 Updates

### Client Meeting Preparation

Meeting with Bridget scheduled for Thursday, July 23 at 5 PM ET. Primary objectives: review preliminary results and present synthetic data outputs. Pratyaksh Singh to create slides illustrating synthetic data. Hemanth Sarabu will attend upon receiving forwarded invitation (source: Iris Sync - 2026_07_20).

### Streamlit Model Selection Toggle

Sachin Pandey to add a toggle to the Streamlit app enabling users to select between old and new model versions. A backup of the current app will be created before changes (source: Iris Sync - 2026_07_20).

### Model Training: V1 vs V2

Six new models trained across two groups: V1 (original pipeline, no hyperparameter changes) and V2 (with hyperparameter adjustments). Each group has three sub-models representing different label grouping strategies (binary, multiclass, UXO-class). V2 generally outperforms V1 across all groupings (source: Iris Sync - 2026_07_20).

### Pixel Threshold Filter Impact

Increasing the prediction pixel threshold from 10 to 100 pixels resulted in approximately a 20% jump in precision-recall score without reducing true positives. The default of 10 pixels produced excessive false positives (source: Iris Sync - 2026_07_20).

### Synthetic Augmentation Baseline Testing

Pratyaksh Singh will train a segmentation model without advanced augmentation as a baseline, then train variants with individual augmentations and combinations to measure delta improvement. Specific augmentation methods were not defined, though examples may include: diffusion-generated backgrounds, copy-paste objects, procedural mine generation, classical image-space transforms. Results to be reported Wednesday ahead of the client meeting (source: Iris Sync - 2026_07_20).

### Feature Development Prioritization

Development focus prioritized toward UXO and small black patch data. Sand ripples deprioritized as the client does not prioritize them (source: Iris Sync - 2026_07_20).

### Sand Patch Annotation Strategy

Two options for sand patch annotations: drop entirely or merge with sand ripples to improve classification performance (source: Iris Sync - 2026_07_20).

### Updated Dataset As New Baseline

The updated dataset (with fixes and additional VW phase 2 data) is now the project baseline for all future comparisons, replacing the static historical baseline (source: Iris Sync - 2026_07_20).

### UXO Metric Exclusion

Images where UXO objects are not visually identifiable will be excluded from metric calculations to prevent corrupted evaluation results. UXO recall currently around 40%, with some false negatives from files marked as UXO but where the object isn't visually present (source: Iris Sync - 2026_07_20).

### Magnetometer Data Client Exclusion

Team decided to exclude MAG data from the upcoming client meeting agenda unless specific questions arise requiring client input. Location accuracy remains at 5-10 m range. Ratul Shashank to create 2-pane visualization comparing MAG amplitude with XTF imagery (source: Iris Sync - 2026_07_20).

### Centralized Data Tracking

Agreement to establish a centralized reference list for all open-source and raw datasets. Sachin Pandey to compile; Geoff Horowitz to handle VW phase 2 data transfer on SFTP (source: Iris Sync - 2026_07_20).

### Documentation Formalization

Sachin Pandey to formalize project documentation with dated entries, links to reports, TL;DR rationale for each experiment, results, and proposed next steps (source: Iris Sync - 2026_07_20).

### Geo-Referenced JSON Deliverables

Client to receive geo-referenced JSON files for sand ripples and black patches, formatted for direct drag-and-drop onto XTF or mosaic software (source: Iris Sync - 2026_07_20).

### Open-Source Pre-Training Strategy Reinforced

Open-source sonar data plan: search and classify by similarity to Bedrock data, use for pre-training, then fine-tune on Bedrock data. Labelers won't fully annotate open-source examples due to volume and out-of-distribution appearance (source: Iris Sync - 2026_07_20).

### Overlap Threshold for Internal Use

Overlap threshold higher than 0.01 recommended for internal evaluation to better understand model performance, though 0.01 will be used for client-facing presentations. Confidence levels and minimum filter size settings to remain exposed in the viewer (source: Iris Sync - 2026_07_20).

### Metrics Table Improvement Indicators

Sachin Pandey to add improvement indicators against the baseline model to the performance table, displayed in parentheses next to relevant figures (source: Iris Sync - 2026_07_20).

## July 22 Updates

### Hyperparameter Search & Resolution Benchmarking

Pratyaksh Singh conducted a hyperparameter search using ResNet-50 comparing 256-pixel and 512-pixel input resolutions. Models using 512-pixel inputs consistently outperformed 256-pixel models. Evaluated transformations including perspective, Poisson blending, roll, cutmix, and softmix. The combination of Poisson blending, roll, and cutmix achieved the highest object-level F1 score of 0.49 @ 20% IOU (source: Iris Sync - 2026_07_22).

### Data Cleaning Metric Skew

Sachin Pandey removed ~1,300 small black patch/noisy point annotations (Annotation 2) to clean training data. While pixel-level accuracy reached the ~90th percentile, object-level F1 dropped because modifying the ground-truth annotation count altered the metric denominator. Rerunning validation predictions on identical ground-truth annotations is required for valid comparisons (source: Iris Sync - 2026_07_22).

### K-Fold Cross-Validation Strategy

The team adopted K-fold cross-validation to compensate for small UXO validation support (only 13–15 total UXO objects across the dataset). Naive random splits are invalid due to geographic tile overlap; manual spatial partitioning is required to prevent data leakage (source: Iris Sync - 2026_07_22).

### "Probable UXO" Class Creation

Pratyaksh Singh proposed introducing a "Probable UXO" category to capture ambiguous objects resembling UXO rather than deleting them, improving model recall while addressing visual discrepancies between open-source mine data (cylindrical with shadows) and Bedrock UXO data (pits/depressions in side-scan sonar) (source: Iris Sync - 2026_07_22).

### Border Sensitivity & Port/Starboard Separation

Observed false negatives occurring near image borders (border sensitivity). Planned augmentations to remove black edge regions and agreed to process port and starboard sonar channels as separate training categories (source: Iris Sync - 2026_07_22).

## July 23 Updates

### Object Metric Calculation Bug Fix

Sachin Pandey identified a bug in object-level metric calculations where large objects ("AI big") with high pixel overlap (~80%) were fragmented into separate annotations, artificially deflating object F1. Fixed the calculation error to correctly unify contiguous predictions (source: Meeting started 2026_07_23).

### V3 Model Selection for Client Presentation

Selected the V3 model as the top performer for UXO and general classes. Agreed to deploy V3 to the Streamlit app instance `8505` for upcoming client demonstration to Bridget (source: Meeting started 2026_07_23).

### Variable Isolation Training Strategy

Established a policy for future training runs to isolate single variables (e.g., separating image transformations like brightness/gamma from synthetic cut-and-paste augmentations) to measure the exact contribution of each technique (source: Meeting started 2026_07_23).

### Dashboard & Documentation Standardization

Standardized dashboard reporting to feature high-level summary headlines with clickable links to detailed HTML specs, keeping the main interface clean and easy to navigate (source: Meeting started 2026_07_23).

## July 24 Updates

### Client Meeting & Recall Priority

Geoff Horowitz reported positive feedback from Bridget (Bedrock) on representative targets shown via Streamlit. Bridget confirmed Bedrock has shared all available UXO data (no new client data currently available; possible future San Diego data collection). Client prioritizes UXO detection and prefers recall over precision (accepting more false positives to prevent missed contacts). Qualitative demonstration examples are preferred over strict metric hurdles (source: Iris Sync - 2026_07_24).

### UXO and AOI Small Black Class Merging

Identified that UXOs and "AOI small black" patches are visually indistinguishable in SSS data. The team decided to merge UXO and AOI small black into a single training class to maximize training signal and boost UXO recall, while retaining separate classes for evaluation and client presentations. Image samples will be sent to Bridget for client label verification (source: Iris Sync - 2026_07_24).

### Heavy Dataset File Duplication

Pratyaksh Singh demonstrated that existing datasets (DRN, Port, POE, VW) contain 10–15 duplicate files per location, leading to model overfitting and stalling augmentation gains. Performance bottlenecks stem from dataset quantity and geographical diversity limits rather than lack of augmentations (source: Iris Sync - 2026_07_24).

### Flux Turbo + LoRA Synthetic Object Generation

Ratul Shashank demonstrated successful synthetic UXO generation using Flux Turbo with LoRA models, categorizing targets by elongation (elongated, round, moderate). Flux Turbo generated plausible object variations without the artificial artifacts seen in previous models. Division of labor established: Generative AI handles novel object structure creation, while classical CV handles brightness, contrast, and shape transformations (source: Iris Sync - 2026_07_24).

### Real-to-Sim Physics Simulation Proposal

Hemanth Sarabu proposed a "Real-to-Sim" physics simulation strategy using raw XTF metadata (trajectories, altitude, depth, MAG data) to render side-scan intensity returns. Suggested exploring agentic simulation prompts (e.g. Claude / Antigravity) to derive physics models from scene descriptions (source: Iris Sync - 2026_07_24).

### Mandatory Code Backups & Validation Retention

Standardized K-fold cross-validation for final model deliveries to ensure statistical reliability. All validation images (including long/zoomed-out views) will be retained. Established a mandatory policy requiring all project and fine-tuning code to be committed and backed up to GitHub (source: Iris Sync - 2026_07_24).

## July 27 Updates

### V4 Model Development & Penalty Weighting

Sachin Pandey introduced the V4 model, which addresses UXO and AI Small class imbalance by adjusting false-positive penalty weights. The lineage was clarified: V1/V2 used the legacy pipeline, while V3/V4 utilize corrected training annotations. V4 demonstrates strong performance for UXO classification and is scheduled for integration into the main Bedrock app prior to external sharing (source: Iris Sync - 2026_07_27).

### Model Version Tracking on GitHub

Geoff Horowitz and Hemanth Sarabu established a standardized documentation policy to maintain a running collapsible list of model versions, specifications, and data configurations on GitHub. This structured Markdown/HTML history will enable transparent tracking and allow future LLM agents to query past runs (source: Iris Sync - 2026_07_27).

### Training Data Annotation Cleaning

Sachin Pandey initiated cleaning of training data by removing non-essential small "footprint discoloration" annotations (Annotation 2) that cause spurious false positive predictions, while ensuring missed valid annotations are added (source: Iris Sync - 2026_07_27).

### False Positive Rotation & Scaling Augmentation

The team approved incorporating rotated, scaled, and morphed annotations into the training set as false positives to enhance model robustness and precision across varied sonar backgrounds (source: Iris Sync - 2026_07_27).

### Interactive Agent-Based Generation & LLM Validation Loop

Transitioned synthetic data generation toward interactive agent-based workflows. Sachin Pandey established an LLM-based Validation Agent loop that compares synthetic sonar images against reference data using similarity metrics (initial threshold set at 80%) for automated image refinement (source: Iris Sync - 2026_07_27).

### Technical Diagnostics & Texture Metrics

Pratyaksh Singh and Sachin Pandey resolved an unexpected data drop issue in technical processing by conducting soft matrix histogram range comparisons, evaluating GLCM (Gray-Level Co-occurrence Matrix) texture metrics, and confirming correct matrix expressions (source: Iris Sync - 2026_07_27).

## July 28 Updates

### Synthetic Data Strategy Shift

The team shifted away from modifying existing Bedrock data (which produces outputs indistinguishable from standard augmentations) toward using open-source data (~300k images) as a base for procedural generation. An LLM judge scores how well generated images match the target distribution and provides feedback to a coding agent to refine the process (source: Bedrock Discussion Continued (understanding eval agent) - 2026_07_28).

### Procedural Generation Frameworks

Two complementary approaches proposed by Hemanth: (1) hill-climbing optimization where the LLM judge incentivizes iterative score improvement, and (2) a reconstruction loop analogous to VAEs/diffusion where the system learns to reconstruct reference images procedurally, then is perturbed to create novel data. Token limitations prevent full-image processing, requiring on-device heuristics instead (source: Bedrock Discussion Continued (understanding eval agent) - 2026_07_28).

### Dimensionality Reduction Transition

Moving from SVD/PCA to Empirical Mode Decomposition (EMD) for isolating non-linear components between synthetic and real images. SVD reconstructs well from top 10 singular values but PCA struggles with non-linear oscillations. Pratyaksh to test EMD and frequency domain transforms (source: Bedrock Discussion Continued (understanding eval agent) - 2026_07_28).

### VAE Pre-Training Exploration

Hemanth proposed training a VAE to extract components from an embedding space/codebook. Pratyaksh to explore VAE or diffusion pre-training on open-source data and report feasibility (source: Bedrock Discussion Continued (understanding eval agent) - 2026_07_28).

### 25 Pixel-Based Augmentations Accepted

Accepted as a fallback strategy if synthetic generation proves insufficient (source: Bedrock Discussion Continued (understanding eval agent) - 2026_07_28).

### Skills Repository

Consensus to create a centralized repository for documenting and sharing team skills and technical resources (source: Bedrock Discussion Continued (understanding eval agent) - 2026_07_28).

## July 29 Updates

### V4 Model Focal Dice Loss & False Positive Reduction

Implemented Focal Dice loss in V4, dramatically lowering false positive predictions (UXO FP dropped to 12, AOI big to 83, black patch to 179; total FPs reduced to ~200 from 1,100–1,500). Precision improved significantly across all classes; recall dropped 8% on `AOI big` but improved in other categories. Noted potential stability issues with Focal Dice loss on its own, suggesting future pairing with BCE (source: Iris Sync - 2026_07_29).

### Standardized K-Fold Benchmark Splits Across GPUs

Agreed to standardize K-fold data splits across all model recipes to enable direct, line-by-line model performance comparisons on parallel GPUs rather than collapsing metrics into an average score. Low false negatives for UXOs reconfirmed as the top priority over minimizing false positives (source: Iris Sync - 2026_07_29).

### UXO / AOI Small Black Merging & Report Narrative

Merging `UXO` and `AOI small black` classes boosted true positive matches from 3 to 23 on the synthetic test set. Geoff instructed Sachin to revise the V4 report narrative to ensure the written text accurately reflects the metric context (source: Iris Sync - 2026_07_29).

### Diffusion Data Synthesis Anti-Leakage Workflow

To prevent data leakage when using diffusion models, agreed to train the diffusion model on a clean 75% background split (excluding object-level training samples), generate synthetic background patches (128x128 / 256x256), paste external/procedurally generated objects, and test the classifier on the held-out 25% (source: Iris Sync - 2026_07_29).

### Latent Space Inpainting D-Noising Trick

Hemanth proposed a 5-step blending pipeline: (1) generate background, (2) copy-paste object, (3) encode to latent space, (4) add slight noise to latent representation, (5) run 1–2 d-noising diffusion steps to naturally integrate the object into the sonar distribution (source: Iris Sync - 2026_07_29).

### Transition to Image-Domain Augmentations & Mean Pixel Blending

Shifted from XTF-level raw amplitude operations to runtime image-domain augmentations (OpenCV Poisson copy-paste, rotation/scaling matrices, shadow additions). XTF operations suffered from gradient mismatch and dataset scaling discrepancies (e.g. VW object transfer to ANTX). Standardized pixel blending logic to take the mean of overlapping pixels rather than summing to avoid clipping/overflow (>255) (source: Iris Sync - 2026_07_29).

## July 31 Updates

### Sonar Data Categorization Protocol
Established a file categorization protocol splitting sonar scan files into XTF and DRN groups. Each group represents a unique object across multiple scan passes, accounting for duplicate passes appropriately (source: Iris Sync - 2026_07_31).

### Model Training Status & Bug Fixes
Confirmed the July 27 V4 model remains the baseline. Fixed V4 metric bugs regarding annotation processing and overlaps < 0.1 IoU. Paused K-fold model training mid-process after failing to reach 50% IoU due to underlying base ground truth annotation issues (source: Iris Sync - 2026_07_31).

### Pixel Crop Pivot & LoRA Model Generation
Pivoted from manipulating raw sensor values in XTF files to using pixel crops for object manipulation. Fine-tuning a LoRA model on 144 object crop examples for novel synthetic object generation (source: Iris Sync - 2026_07_31).

### Latent Space Dataset Pruning & EMD App Tooling
Proposed using latent space distance metrics (such as FID) to evaluate generated image distributions, enabling semi-automated dataset pruning and avoiding duplicates. Planned an interactive EMD application for visualizing decomposed intrinsic mode functions (IMFs) (source: Iris Sync - 2026_07_31).

## August 3 Updates

### Milestone 2 Closure 3-Tier Proof Strategy
Established a 3-tier proof structure for the Milestone 2 presentation: (1) baseline SOW 1 model performance, (2) retrained SOW 1 model performance, and (3) V4 model performance gains (driven by Tversky loss and Focal Dice weighting). Sachin preparing slides detailing false positive and false negative analysis (source: Iris Sync - 2026_08_03).

### Geographic K-Fold Cross-Validation & Data Leakage Avoidance
Implemented spatial partitioning across 5 K-folds using geographic coordinates and object IDs to ensure zero data leakage between training and validation folds. This addresses the small validation set constraint (~11 unique UXO objects) (source: Iris Sync - 2026_08_03).

### Synthetic Data Strategy & Guidance/Step Benchmarking
Restricted M2 synthetic training additions to verified cut-and-paste object placement due to V4 automated augmentation recall drops. Real AOI data is reserved for validation, while training uses real backgrounds + synthetic foreground objects (closed-source prompt engineering by Ratul + procedural agent by Sachin). Evaluated flow matching background model parameters (classifier guidance weight 1 preserves quality; 25 diffusion steps outperform 10 steps on low-representation datasets) (source: Iris Sync - 2026_08_03).

### ResNet-50 Embedding Noise Filtering & SoCal Mission Data
Implemented DBSCAN clustering on ResNet-50 embeddings to isolate distorted synthetic images. Evaluated ~300 side-scan XTF files (2km x 2km, >1000 contacts) from Southern California; agreed to run qualitative inference with the V4 model first before deciding on manual labeling (source: Iris Sync - 2026_08_03).

## August 5 Updates

### K-Fold 100m Geographic Grid Partitioning vs. Patch Inference
Transitioned K-fold cross-validation spatial dataset partitioning from 128x128 pixel grids to a 100m x 100m geographic map grid to eliminate boundary cutoffs and background data loss when separating port and starboard channels. Standard model inference continues using 128x128 raster patches (source: Iris Sync - 2026_08_05).

### V4 Baseline Standard & Object-Level Metric Priority
Confirmed V4 model as baseline standard (superseding V3 due to V3 false positive rates). Prioritized object-level precision and recall metrics over pixel-level IoU. Determined K-fold cross-validation is omitted for unseen client test data since models are not retrained on it (source: Iris Sync - 2026_08_05).

### Inference Filters & Class Deliverable Configurations
Mandated a minimum pixel size filter (2,000–3,000 pixels for AOI Big) and class output configurations to isolate UXO and combined small black objects while excluding unwanted non-targets (source: Iris Sync - 2026_08_05).

### Synthetic Generation, GAN Shelving & Decomposition Prototypes
Ratul generated novel UXO object crops using GPT / nano banana image-to-image prompts while preserving blob structures. GANs were formally shelved due to data volume limits and instability; LoRA was confirmed ineffective. Hemanth introduced image decomposition prototypes (structure, speckle, base layer separation via EMD-like algorithms) to naturally blend crops into backgrounds. Explored VGG sand ripples and style transfer remixing; confirmed FFT is ineffective (source: Iris Sync - 2026_08_05).

## Related pages

- [[magnetometer-processing-pipeline]]
- [[synthetic-data-requirements]]
- [[sss-augmentation-methods]]
- [[model-training-and-iterations]]
- [[data-quality-and-gaps]]
- [[data-sets-and-curation]]
- [[iris-sync-2026-07-29]]
- [[iris-sync-2026-07-31]]
- [[iris-sync-2026-08-03]]
- [[iris-sync-2026-08-05]]

---

**Sources**: raw/meeting_transcripts/Iris Sync - 2026_06_12 through 2026_08_05 (all 24 transcripts); raw/meeting_transcripts/Bedrock Discussion Cont - 2026_06_23; raw/meeting_transcripts/Bedrock__Crescer_ Mag Discussion - 2026_07_01; raw/meeting_transcripts/Bedrock connect - 2026_07_17; raw/meeting_transcripts/Aux Discussion Mag Data - 2026_07_17; raw/meeting_transcripts/Meeting started 2026_07_23 15_29 EDT - Notes by Gemini.md; raw/meeting_transcripts/Bedrock Discussion Continued (understanding eval agent) - 2026_07_28 11_59 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_07_29 12_26 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_07_31 12_26 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_08_03 12_28 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_08_05 12_24 EDT - Notes by Gemini.md
