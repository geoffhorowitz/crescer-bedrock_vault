# Model Training And Iterations

**Summary**: Progress on model training across multiple iterations, including architecture comparisons, class strategy decisions, test set selection, hyperparameter searches, augmentation combinations, V3/V4 model performance, and model lineage documentation.

**Last updated**: 2026-07-29

---

## Architecture Comparisons

Two model architectures were compared for the Vineyard Winds dataset:
- **U-Net with ResNet-50 backbone**: Previously used as the baseline for VW (source: Iris Sync - 2026_07_06)
- **YOLOv8**: Trained across multiple iterations with varying class counts to focus on the most important features (source: Iris Sync - 2026_07_06)

Backbone selection for Jetson compatibility was deferred until after initial benchmarks were established (source: Iris Sync - 2026_07_13).

## Classification Strategy

### Multi-Class vs. Binary

The team trained both multi-class and binary models using the old pipeline (source: Iris Sync - 2026_07_08). The binary model initially underperformed compared to multi-class, with rising loss observed in training logs (source: Iris Sync - 2026_07_08). A decision was made to clarify with the client on Slack whether they require multi-class or single-class output (source: Iris Sync - 2026_07_08).

### Class Merging

The final classification strategy merges similar-looking classes to reduce the count to four, with the exception of UXO-style targets which are kept separate (source: Iris Sync - 2026_07_13). Key mergers:
- The noise class was removed entirely (source: Iris Sync - 2026_07_15)
- Black patch and AOI support artifacts were merged into one class because the model confused them — both appear as dark regions and the model only sees cropped versions it cannot distinguish from context (source: Iris Sync - 2026_07_15)
- Strategy: classify distinct objects into separate classes initially, merge only if needed later (source: Iris Sync - 2026_07_15)

## Training Decisions

### Data Split

The team moved from a three-way train/validation/test split (original deck described 80/10/10) to an 80/20 split due to small dataset size producing noisy statistics (source: Iris Sync - 2026_07_10). Once hyperparameters are finalized, training on the full dataset was the planned approach (source: Iris Sync - 2026_07_10).

### Test Set Selection

Geographic overlap between training and test data was identified as a data leakage risk (source: Iris Sync - 2026_07_08). The team created a geographically distinct test set using latitude/longitude coordinates rather than random selection (source: Iris Sync - 2026_07_10). Overlapping regions were prohibited and must be partitioned or removed (source: Iris Sync - 2026_07_13).

### Background Class Error

An initial error was discovered where the background class was incorrectly included in metric calculations, distorting results. This required model retraining with the test set excluded from training data (source: Iris Sync - 2026_07_10).

## Performance Observations

Model comparison showed an 8% precision increase but a 7% recall decrease in new iterations versus the old model on old data (source: Iris Sync - 2026_07_15). This comparison was noted as potentially unreliable due to differences in images, resolutions, and annotation classes (source: Iris Sync - 2026_07_15).

Pixel-level metrics were found misleading for classes like sand ripple that occupy large areas and dominate pixel counts, making object-level metrics more informative (source: Iris Sync - 2026_07_15).

## Benchmarking Strategy

The legacy model was run on the new dataset to establish a baseline benchmark. Two tables were defined:
- **Table 1**: Old model on old data, replicating previous results
- **Table 2**: Old model performing inference on a mixture of datasets without retraining
(source: Iris Sync - 2026_07_15)

## Naming Convention

Model nomenclature was standardized to include model name, date, dataset, and configuration (source: Iris Sync - 2026_07_13).

## IOU Threshold Addition

Geoff Horowitz requested that an 0.1 IOU threshold be added to the results table alongside the existing 0.5 IOU. At 0.1 IOU, the model achieves 0.866 (rounded to 0.87). Both thresholds will be used for internal evaluation and client reporting to show detection capability at varying strictness levels (source: Bedrock connect - 2026_07_17).

## Annotation Inclusion Strategy

Sachin outlines the S1 model assumptions: binary classification with sand ripple and "incorrect" annotations excluded from the JSON. The images themselves remain in training, but the annotations for excluded classes are not processed. Geoff and Sachin confirm this did not improve false positive results, so the baseline approach is retained. Included classes are POI, Faint POI, and Line Artifacts (source: Bedrock connect - 2026_07_17).

## Training Parameter Consistency

For the latest training cycle, only the learning rate was modified. All other hyperparameters remain consistent with the previous model version. Black patches and AOI support classifications will be adjusted in the next training cycle to improve accuracy (source: Bedrock connect - 2026_07_17).

## Model Iterations: V1 vs V2

Six new models were trained across two groups:
- **Group 1 (V1)**: Original pipeline with no hyperparameter changes. Three sub-models representing different label grouping strategies: binary (all classes merged), multiclass (original annotations after fixing), and UXO class (targets marked as UXO pulled into a separate class).
- **Group 2 (V2)**: Modified hyperparameters including learning rate changes. Same three sub-models as V1.

V2 generally outperforms V1 across all label grouping strategies. The sub-models differ only in how the labels are grouped, not in architecture or hyperparameters (source: Iris Sync - 2026_07_20).

## Input Resolution Benchmarking

Hyperparameter search on ResNet-50 compared 256-pixel and 512-pixel input image sizes. Models utilizing 512-pixel inputs consistently outperformed 256-pixel models across all metric evaluations (source: Iris Sync - 2026_07_22).

## Augmentation Combination Experiments

Tested transformations including perspective, Poisson blending, sonar roll, cutmix, and softmix (alpha blending of image and mask). The best-performing model utilized a combination of Poisson blending, sonar roll, and cutmix, achieving an object F1 score of 0.49 @ 20% IOU (source: Iris Sync - 2026_07_22).

## Port and Starboard Channel Separation

Model training will be updated to treat port and starboard sonar channels as separate training categories rather than combined inputs to improve spatial learning (source: Iris Sync - 2026_07_22).

## K-Fold Cross-Validation & Spatial Partitioning

Adopted K-fold cross-validation as standard strategy to address low UXO validation support (13–15 total objects). Naive random splits are prohibited due to geographic tile overlap; data must be manually partitioned into spatially distinct folds to prevent data leakage (source: Iris Sync - 2026_07_22).

## V3 Model Selection & Variable Isolation Strategy

The V3 model was selected as the top performer for UXO and general classes, scheduled for integration into the Streamlit presentation dashboard (`instance 8505`) for client review (source: Meeting started 2026_07_23).

To establish clean causal relationships, future training iterations will enforce single-variable isolation—separating image transformations (brightness, gamma) from synthetic data augmentations (cut-and-paste)—to measure exact per-feature performance deltas (source: Meeting started 2026_07_23).

## UXO and AOI Small Black Training Class Merger

Because UXO targets and AOI small black patches are visually indistinguishable in SSS imagery, the team adopted a merged training strategy: treat both as a single unified class during model training to maximize feature learning and recall, while maintaining separate classes during evaluation and client presentations (source: Iris Sync - 2026_07_24).

## Flux Turbo + LoRA Elongation Fine-Tuning

Generative AI fine-tuning adopted Flux Turbo with LoRA models, categorizing targets by elongation (elongated, round, moderate). Fine-tuning separate LoRA models per elongation class successfully generated plausible synthetic UXOs without structural artifacts (source: Iris Sync - 2026_07_24).

## Mandatory GitHub Code Backup Policy

To mitigate single-point-of-failure infrastructure risks (such as system offline events on Wall-E or Ninja), the team established a mandatory policy requiring all model training, fine-tuning, and evaluation code to be committed and backed up to GitHub repositories (source: Iris Sync - 2026_07_24).

## V4 Model Development & Class Imbalance Weighting

The V4 model was introduced to resolve class imbalance issues between UXO targets and AI Small objects by adjusting penalty weights assigned to false positives. Model lineage was formally structured:
- **V1 / V2**: Built on the legacy data pipeline and initial annotation set
- **V3 / V4**: Built on corrected, cleaned training annotations

V4 achieved superior UXO classification performance and is scheduled for end-to-end integration and verification within the primary Bedrock application prior to client demonstration (source: Iris Sync - 2026_07_27).

## GitHub Collapsible Model Version Log

To ensure transparent provenance and support automated agentic queries, the team mandated maintaining a running collapsible list on GitHub documenting each model iteration's specifications, training datasets, hyperparameters, and key performance outcomes (source: Iris Sync - 2026_07_27).

## V4 Focal Dice Loss Implementation

The V4 model introduced a Focal Dice loss function to address severe class imbalance and false positive rates.
- **False Positive Drop**: Total false positives dropped from 1,100–1,500 range to ~200 total (UXO FP dropped to 12, AOI big to 83, black patch to 179) (source: Iris Sync - 2026_07_29).
- **Loss Function Stability**: Pratyaksh noted that Focal Dice loss can be unstable when used alone and recommended investigating pairing it with Binary Cross Entropy (BCE) in future recipes (source: Iris Sync - 2026_07_29).

## Standardized K-Fold Model Benchmarking Across GPUs

To allow direct comparison between model recipes (such as V4 baseline vs heavy augmentation variants):
- **Consistent Splits**: The 5-fold cross-validation data splits will be kept fixed across all experiments rather than generating new splits per model (source: Iris Sync - 2026_07_29).
- **Parallel GPU Execution**: Utilizing available multi-GPU infrastructure to train and evaluate recipes on identical K-fold splits simultaneously (source: Iris Sync - 2026_07_29).
- **Line-by-Line Reporting**: Model metrics (precision, recall, F1 per fold) will be compared line-by-line across folds rather than reducing each model's performance to a single averaged metric (source: Iris Sync - 2026_07_29).

## July 31 Baseline Confirmation & K-Fold Training Pause

The July 27 V4 model was confirmed as the active baseline for performance evaluation.
- **Metric Bug Fixes**: Fixed underlying bugs in V4 metric calculations regarding annotation processing and handling overlap thresholds below 0.1 IoU (source: Iris Sync - 2026_07_31).
- **K-Fold Training Paused**: K-fold model training was halted mid-process after failing to achieve 50% IoU. The root cause was identified as incorrect markings and quality issues in the base ground truth annotations, which are being resolved prior to resuming K-fold runs (source: Iris Sync - 2026_07_31).

## Milestone 2 Closure 3-Tier Proof Strategy

The team established a 3-tier performance comparison structure to finalize Milestone 2 closure (source: Iris Sync - 2026_08_03):
1. **SOW 1 Baseline Model**: Evaluated on current updated data to demonstrate poor baseline performance.
2. **Retrained SOW 1 Model**: Fine-tuned on updated data to show moderate improvement but insufficient gain.
3. **V4 Model**: Evaluated on the same data to demonstrate substantial performance gains driven by Tversky loss, Focal Dice weighting, and 512px input resolution.

## Geographic K-Fold Cross-Validation Implementation

To solve the small validation set constraint (~11 unique UXO objects across datasets) without data leakage:
- **Spatial & ID Partitioning**: UXOs are segregated into 5 folds using a combination of geographic coordinates (area-based grid cells) and unique object IDs to ensure no spatial or target overlap exists between training and validation folds (source: Iris Sync - 2026_08_03).
- **Experimental Recipe Plan**: Models V3, V4, and a V3 variant with Tversky loss will be evaluated across the identical 5 K-folds to generate statistically reliable, leak-free metrics (source: Iris Sync - 2026_08_03).

## K-Fold 100m Geographic Grid Split vs. Patch Inference

The spatial partitioning methodology for K-fold cross-validation was updated from 128×128 pixel grids to a **100m × 100m geographic map grid**.
- **K-Fold Partitioning**: Mapping data to a 100m map grid prevents boundary cutoffs and background data loss that occurred when splitting port and starboard channels using 128×128 pixel tiles (source: Iris Sync - 2026_08_05).
- **Inference Raster Patches**: Standard model inference continues to utilize 128×128 raster patches. The 100m geographic grid applies specifically to defining cross-validation split boundaries (source: Iris Sync - 2026_08_05).

## V4 Baseline Standard Confirmation

V4 was officially confirmed as the standard baseline model for ongoing development, superseding V3 due to V3's excessive false-positive rate (source: Iris Sync - 2026_08_05).

## August 7 K-Fold Benchmarks & Training Policies

Results from preliminary 5-fold cross-validation runs on V4 variants led to new training guidelines (source: Iris Sync - 2026_08_07):
- **V4 Base Overfitting vs. Augmented Recall**: The base V4 model without image augmentations suffered from severe overfitting due to high false-negative penalties. Applying standard image augmentations (color/noise) allowed V4 to capture underlying target patterns, reaching ~90% recall (with precision ~20–50%).
- **Zero-F1 Early Stopping Rule**: Established policy to terminate K-fold model runs early if the F1 score drops to 0, indicating a complete failure to learn effectively on that fold.
- **Dedicated Cut-and-Paste Model**: Resolved to train a dedicated model incorporating corrected cut-and-paste data to test whether copy-paste augmentations restore robustness prior to closing Milestone 2.
- **Model Deferment Policy**: Agreed to defer external delivery of the best-performing model until the subsequent milestone to demonstrate continuous step-by-step performance improvements to stakeholders.

## Related pages

- [[synthetic-data-requirements]]
- [[sss-augmentation-methods]]
- [[model-performance-and-metrics]]
- [[data-sets-and-curation]]
- [[bedrock-meeting-transcripts-summary]]
- [[iris-sync-2026-07-29]]
- [[iris-sync-2026-07-31]]
- [[iris-sync-2026-08-03]]
- [[iris-sync-2026-08-05]]
- [[iris-sync-2026-08-07]]
- [[internal-bedrock-x-crescerai-initial-sow]]
- [[sow-1-milestone-2-presentation]]
- [[lumen-model]]

---

**Sources**: raw/meeting_transcripts/Iris Sync - 2026_06_12 through 2026_08_07; raw/Internal Bedrock x CrescerAI Initial SOW.md; raw/SOW 1 Milestone 2 Presentation.pptx; raw/Bedrock SOW 2.md; raw/meeting_transcripts/Iris Sync - 2026_07_03; raw/meeting_transcripts/Iris Sync - 2026_07_06; raw/meeting_transcripts/Iris Sync - 2026_07_08; raw/meeting_transcripts/Iris Sync - 2026_07_10; raw/meeting_transcripts/Iris Sync - 2026_07_13; raw/meeting_transcripts/Iris Sync - 2026_07_15; raw/meeting_transcripts/Bedrock connect - 2026_07_17; raw/meeting_transcripts/Iris Sync - 2026_07_20; raw/meeting_transcripts/Iris Sync - 2026_07_22; raw/meeting_transcripts/Meeting started 2026_07_23; raw/meeting_transcripts/Iris Sync - 2026_07_24; raw/meeting_transcripts/Iris Sync - 2026_07_27 12_29 EDT - Notes by Gemini.md.md; raw/meeting_transcripts/Iris Sync - 2026_07_29 12_26 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_07_31 12_26 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_08_03 12_28 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_08_05 12_24 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_08_07 12_16 EDT - Notes by Gemini.md
