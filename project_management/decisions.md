# Decisions

**Summary**: Significant decisions made by the team or client, with rationale and date.

**Last updated**: 2026-07-29

---

- **2026-07-29** - **Standardized K-Fold Benchmark Splits Across Models**: Adopted standardized K-fold validation data splits kept constant across all model recipes to enable direct line-by-line performance comparisons (across parallel GPUs) rather than collapsing metrics into single averages (source: Iris Sync - 2026_07_29).
- **2026-07-29** - **Image-Domain Augmentations Adopted Over XTF Operations**: Adopted runtime image-domain augmentations (OpenCV Poisson copy-paste, rotation/scaling matrices, shadow additions) over XTF raw amplitude manipulation due to gradient mismatch and spatial scale discrepancies across datasets (e.g. VW to ANTX) (source: Iris Sync - 2026_07_29).
- **2026-07-29** - **Mean Pixel Calculation for Image Blending**: Standardized on taking the mean of pixel values when overlapping or blending image regions to prevent numerical clipping and overflow (>255) (source: Iris Sync - 2026_07_29).
- **2026-07-29** - **Clean 75/25 Background Split for Diffusion Models**: To prevent data leakage, agreed to train diffusion models exclusively on background sonar splits (excluding real object annotations), populate generated backgrounds with external/procedurally generated objects, and evaluate classifiers on a held-out 25% test set (source: Iris Sync - 2026_07_29).
- **2026-07-29** - **Screen Recordings Enabled for Meeting Series**: Screen recordings enabled across all meetings in the series to enhance transcript and documentation quality (source: Iris Sync - 2026_07_29).
- **2026-07-28** - **LLM-As-Judge Evaluation Strategy**: Adopted a strategy using an LLM as an evaluation judge to score how well procedurally generated images match the target data distribution, providing feedback to a coding agent for iterative refinement. Target acceptance threshold set at 0.9. The LLM judge is augmented with perceptual loss heuristics (AlexNet features) and object detection metrics to compensate for vision-language model limitations (source: Bedrock Discussion Continued (understanding eval agent) - 2026_07_28).
- **2026-07-28** - **Open-Source Base Data Strategy**: Shifted synthetic data generation from modifying existing Bedrock data (which produces outputs indistinguishable from standard augmentations) to using open-source data (~300k images) as a base and converting it to the target distribution via procedural generation (source: Bedrock Discussion Continued (understanding eval agent) - 2026_07_28).
- **2026-07-28** - **No-Assumption Data Processing Policy**: Established a policy to avoid assumptions about data conventions (rotation, axis orientation, coordinate systems) when processing newly acquired datasets. Base structure must be investigated empirically before drawing conclusions about data quality (source: Bedrock Discussion Continued (understanding eval agent) - 2026_07_28).
- **2026-07-28** - **25 Pixel-Based Color Augmentations**: Accepted 25 pixel-based color augmentations as a fallback strategy if synthetic generation proves insufficient (source: Bedrock Discussion Continued (understanding eval agent) - 2026_07_28).
- **2026-07-17** - **Dual-Threshold IOU Reporting**: The team decided to report baseline model metrics at both 0.1 and 0.5 IOU thresholds. This provides a more useful representation for client demonstrations, showing that even single-pixel overlaps indicate target presence detection (source: Bedrock connect - 2026_07_17).
- **2026-07-17** - **Hyperparameter Consistency**: For the latest training cycle, the team decided to modify only the learning rate, keeping all other hyperparameters consistent with the previous model version to isolate performance changes (source: Bedrock connect - 2026_07_17).
- **2026-07-17** - **Open-Source Data Pre-Training**: The team decided to use broad open-source sonar datasets for pre-training to learn background distributions, followed by fine-tuning on the smaller Bedrock dataset. This mitigates out-of-distribution noise from training directly on mixed data (source: Iris Sync - 2026_07_17).
- **2026-07-17** - **Generative AI Training Setup**: Split sonar images into port and starboard channels prior to training the generative models. This removes the central water column gap (which accounts for 30-40% of the image) and optimizes model capacity (source: Iris Sync - 2026_07_17).
- **2026-07-17** - **Magnetometer Altitude Integration**: AUV altitude will be used as a direct input parameter to the detection algorithm (attenuating thresholds as altitude increases) rather than segregating training data into discrete altitude bands, which would introduce look-ahead bias (source: Aux Discussion Mag Data - 2026_07_17).
- **2026-07-17** - **Mag As Confidence Score Adjuster**: Magnetometer data will not be used as a binary search filter to prune sidescan sonar regions, because non-ferrous and deeply buried targets may lack magnetic signatures. Instead, it acts as an additional model channel that adjusts detection confidence scores (source: Aux Discussion Mag Data - 2026_07_17).
- **2026-07-15** - **Noise Class Removal**: The noise class was removed entirely from the training pipeline because it was not represented in the validation set (source: Iris Sync - 2026_07_15).
- **2026-07-15** - **Visual Class Merging**: Merged the "black patch" and "AOI support artifacts" classes because the model frequently confused them due to similarity in cropped contexts (source: Iris Sync - 2026_07_15).
- **2026-07-13** - **Model Naming Standardization**: Standardized model file names to include model name, date, dataset, and configuration format to ensure tracking consistency across training iterations (source: Iris Sync - 2026_07_13).
- **2026-07-10** - **Geographic Data Splitting**: Adopted a geographic data split strategy using latitude/longitude coordinates to partition training and test datasets. Random splits were prohibited to prevent data leakage from overlapping passes (source: Iris Sync - 2026_07_08 and source: Iris Sync - 2026_07_10).
- **2026-07-10** - **Data Split Ratio**: Moved from a 3-way split to an 80/20 train/validation split to reduce statistical noise caused by the small dataset size (source: Iris Sync - 2026_07_10).
- **2026-07-06** - **Sonar Processing Edge Filter**: Applied a 60-degree edge filtering threshold to S7K/MBES data to remove swath edge data where depth uncertainty is high (source: Iris Sync - 2026_07_06).
- **2026-07-03** - **Mag Training Baseline**: Start model training using filtered (despiked, calibrated) magnetometer data, deferring the integration of raw_raw data stream processing (source: Iris Sync - 2026_07_03).

## Related pages

- [[model-training-and-iterations]]
- [[data-sets-and-curation]]
- [[magnetometer-fusion]]
- [[sss-augmentation-methods]]
- [[data-quality-and-gaps]]

---

**Sources**: raw/meeting_transcripts/Iris Sync - 2026_07_03 through 2026_07_17; raw/meeting_transcripts/Aux Discussion Mag Data - 2026_07_17; raw/meeting_transcripts/Bedrock connect - 2026_07_17
