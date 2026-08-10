# Model Performance And Metrics

**Summary**: Model evaluation centers on detection quality, false negatives, runtime, and embedded resource use. Training iteration details are documented in [[model-training-and-iterations]].

**Last updated**: 2026-07-29

---

## Required Metrics

The initial SOW requires precision, recall, F1 score, false-negative rate on seeded targets, average per-chunk inference time, CPU/GPU/memory utilization, and model size versus performance tradeoffs (source: Internal Bedrock x CrescerAI Initial SOW.md).

SOW 2 repeats those metrics for Milestone 2 and adds comparison against SOW 1 baseline metrics, per-chunk inference time on TX2, resource utilization, and synthetic data validation summary (source: Bedrock SOW 2.md).

For mag fusion, SOW 2 requires comparison against an SSS-only baseline, ferrous versus non-ferrous discrimination evaluation, per-chunk inference time, and resource utilization with the mag channel active (source: Bedrock SOW 2.md).

## Reported Interim Results

The milestone deck reports baseline metrics of 0.84 recall, 0.59 precision, and 0.69 F1, with 212 true positives and 41 false negatives (source: SOW 1 Milestone 2 Presentation.pptx).

The deck reports that small object filtering changed performance to 0.80 recall, 0.67 precision, and 0.73 F1 (source: SOW 1 Milestone 2 Presentation.pptx).

The deck reports a 0.917 second average per XTF on Jetson Nano, with 37% peak CPU, 99% peak GPU, and 3.7 GB RAM plus 2 GB swap peak at batch size 4 (source: SOW 1 Milestone 2 Presentation.pptx).

## Metric Issues Discovered

### Background Class Error

An initial error was found where the background class was incorrectly included in metric calculations, distorting results. This required model retraining with corrected exclusion of the test set (source: Iris Sync - 2026_07_10).

### Object vs. Pixel Metrics

Pixel-level metrics proved misleading for classes like sand ripple that occupy large areas and dominate pixel counts. Object-level metrics provide a more informative picture of model performance (source: Iris Sync - 2026_07_15).

### Apples-to-Apples Comparison

Geoff Horowitz emphasized the need for apples-to-apples comparisons: the same pipeline, same data, with only one variable changed at a time (source: Iris Sync - 2026_07_15). Comparisons across iterations were noted as unreliable when images, resolutions, and annotation classes differ (source: Iris Sync - 2026_07_15).

## Evaluation Metrics Choice

Discussion ongoing between recall and F1 score as the primary evaluation metric, to be discussed further between Geoff Horowitz and Pratyaksh Singh (source: Iris Sync - 2026_07_13).

## IOU Threshold Reporting

The team established a dual-threshold reporting strategy using both 0.1 and 0.5 Intersection Over Union (IOU). At 0.1 IOU, a metric of 0.866 (rounded to 0.87) was achieved. The 0.1 IOU rationale is that even a single pixel of overlap confirms model awareness of the object, which is valuable for client-facing reporting. Both thresholds will be included in baseline results tables for comparison (source: Bedrock connect - 2026_07_17).

## Ground Truth Count Adjustment

The ground truth object count was adjusted from 256 to 253 between milestones 2 and 3. Geoff Horowitz clarified that these values shifted as part of transitions between milestones (source: Bedrock connect - 2026_07_17).

## Data Exclusion Documentation (Reinforced)

Geoff emphasized again that any data excluded from training or testing must have reasoning documented to prevent information loss (source: Bedrock connect 2026_07_17 and source: Iris Sync - 2026_07_20).

## Pixel Threshold Filter Impact

Increasing the prediction pixel threshold from 10 to 100 pixels yielded approximately a 20% jump in the precision-recallscore without reducing true positives. The default of 10 pixels led to excessive false positives. This filter was applied during inference to remove small, spurious predictions rather than as part of training (source: Iris Sync - 2026_07_20).

## UXO Metric Exclusion

Images where UXO objects are not visually identifiable by labelers will be excluded from metric calculations to prevent corrupted evaluation. UXO recall currently around 40%, with some false negatives originating from files marked as UXO annotations but where the object isn't visually present (source: Iris Sync - 2026_07_20).

## Overlap Threshold for Internal vs. Client Reporting

An overlap threshold higher than 0.01 recommended for internal evaluation to better understand model performance, though 0.01 will be used for client-facing presentations. Confidence levels and minimum filter size settings to remain exposed in the viewer (source: Iris Sync - 2026_07_20).

## Metrics Table Improvement Indicators

Sachin Pandey to add improvement indicators against the baseline model to the performance table, displayed in parentheses next to relevant figures (source: Iris Sync - 2026_07_20).

## Documentation Formalization

Sachin to formalize project documentation with dated entries, links to reports, a TL;DR rationale for each experiment, results, and proposed next steps (source: Iris Sync - 2026_07_20).

## Ground Truth Denominator Impact (Data Cleaning)

Removing ~1,300 small black patch/noisy point annotations (Annotation 2) significantly boosted pixel-level precision into the ~90th percentile, but adversely affected object-level F1 scores. Because the ground-truth object count (the denominator) changed, raw object-level metrics were not comparable to baseline runs without rerunning validation predictions on identical ground-truth targets (source: Iris Sync - 2026_07_22).

## Border Sensitivity

Error analysis revealed a recurring pattern where missed detections (false negatives) occurred primarily near image borders. Augmentation strategies to crop or remove black edge regions were planned to test model border sensitivity (source: Iris Sync - 2026_07_22).

## Large Object Metric Calculation Bug Fix

Sachin Pandey identified and resolved a calculation flaw where contiguous predictions for large objects ("AI big") achieving high (~80%) pixel overlap were divided into multiple separate annotations. This calculation error artificially depressed object-level F1 metrics despite high pixel accuracy (source: Meeting started 2026_07_23).

## Client Recall-Over-Precision Preference

Geoff Horowitz confirmed from client discussions (Bridget/Bedrock) that the client explicitly prefers high recall over precision. Accepting higher false positive counts (requiring human triage) is preferred over false negatives (missed UXO contacts) (source: Iris Sync - 2026_07_24).

## Qualitative vs. Quantitative Presentation Strategy

Because metric thresholds vary across dataset iterations and annotation shifts, reporting to client leadership will emphasize qualitative demonstration examples (visual target predictions in Streamlit) rather than strict numerical metric hurdles (source: Iris Sync - 2026_07_24).

## K-Fold Cross-Validation Mandate for Deliverables

To overcome statistical instability caused by small UXO sample sizes, K-fold cross-validation is formally mandated for all final model milestone deliverables to produce dependable confidence intervals (source: Iris Sync - 2026_07_24).

## Footprint Discoloration Annotation Removal

Sachin Pandey initiated systematic training data cleaning by stripping small, non-essential "footprint discoloration" annotations (Annotation 2) that previously triggered false positives. Removing these ambiguous targets aims to increase model precision without penalizing valid contact recall (source: Iris Sync - 2026_07_27).

## Texture Metrics & Matrix Diagnostic Verification

To resolve an unexpected data drop issue during inference processing, Pratyaksh Singh and Sachin Pandey implemented diagnostic verification using soft matrix histogram range comparisons and GLCM (Gray-Level Co-occurrence Matrix) texture analysis, confirming the mathematical accuracy of matrix expressions before final model evaluation (source: Iris Sync - 2026_07_27).

## V4 False Positive Reduction & Metric Impact

The V4 model's Focal Dice loss function achieved significant false positive reductions across all classes:
- UXO false positives dropped to 12
- AOI big false positives dropped to 83
- Black patch false positives dropped to 179
- Total false positives fell to ~200 (compared to 1,100–1,500 previously). Precision improved substantially, though recall for `AOI big` dropped by 8% while recall for other classes improved (source: Iris Sync - 2026_07_29).

## Merged UXO / AOI Small Black Class Benchmark & Report Narrative

Merging `UXO` and `AOI small black` classes during synthetic benchmarking increased true positive matches from 3 to 23. Geoff Horowitz instructed Sachin Pandey to update the V4 report narrative to ensure text descriptions accurately contextualize post-merge recall figures against baseline expectations (source: Iris Sync - 2026_07_29).

## V4 Metric Overlap & Annotation Bug Fixes

Sachin Pandey corrected bugs in V4 metric evaluation logic regarding annotation processing and handling overlap thresholds under 0.1 IoU. Fixing these calculation bugs ensures consistent, accurate metric reporting across baseline runs (source: Iris Sync - 2026_07_31).

## Object-Level Metric Priority Mandate

The team mandated evaluating model performance using **object-level precision and recall metrics** rather than pixel-level IoU. Pixel-level metrics cause confusion regarding model superiority, whereas object-level metrics accurately reflect target detection capability (source: Iris Sync - 2026_08_05).

## Inference Pixel Size Filters & Output Configurations

To refine inference outputs on new datasets:
- **Area-of-Interest Filter**: Added a minimum size filter to exclude small non-target items (<2,000 to 3,000 pixels for AOI Big) (source: Iris Sync - 2026_08_05).
- **Class Output Configuration**: Established output configuration settings so client deliverables focus on UXO and combined small black objects while suppressing unwanted classifications (source: Iris Sync - 2026_08_05).
- **K-Fold Omission for Unseen Data**: Omitted K-fold evaluation structures when predicting on brand-new unseen datasets (since models are not retrained on that data), prioritizing direct performance visualization (source: Iris Sync - 2026_08_05).

## Four-Bucket Confusion Matrix Reporting Strategy (August 7)

Hemanth Sarabu proposed a hierarchical four-bucket reporting framework to present model performance trade-offs to stakeholders clearly (source: Iris Sync - 2026_08_07):
- **Tier 1 (High-Level Categorization)**: Evaluates high-level separation between:
  1. `UXO-like` (True UXO, AOI Small Black)
  2. `Non-UXO-like` (AOI Big, Black Patch / windmill supports)
  3. `Background noise`
  - *Goal*: Demonstrate nearly zero off-diagonal misclassifications between UXO-like objects, non-UXO-like objects, and background noise.
- **Tier 2 (Zoomed-In Target Sensitivity)**: Evaluates detailed classification within the `UXO-like` category (`True UXO` vs. `Not True UXO` / `AOI Small Black`).
  - *Goal*: Demonstrate high recall for true UXOs (minimizing false negatives) while contextualizing lower precision (false positives resulting from misclassifications among visually similar UXO-like objects).
- **Precision Floor Warning**: Geoff Horowitz cautioned that while high recall on true UXO targets is the primary goal, precision must maintain a baseline selectivity floor so client teams are not overwhelmed by manual verification of non-UXO contacts.
- **Treasure Island Evaluation Target**: Established performance validation on the new Treasure Island dataset as a core completion requirement for Milestone 2.

## Related pages

- [[automated-target-recognition]]
- [[onboard-deployment]]
- [[synthetic-data-requirements]]
- [[sss-augmentation-methods]]
- [[magnetometer-fusion]]
- [[model-training-and-iterations]]
- [[data-quality-and-gaps]]
- [[iris-sync-2026-07-29]]
- [[iris-sync-2026-07-31]]
- [[iris-sync-2026-08-03]]
- [[iris-sync-2026-08-05]]
- [[iris-sync-2026-08-07]]
- [[internal-bedrock-x-crescerai-initial-sow]]
- [[sow-1-milestone-2-presentation]]
- [[bedrock-sow-2]]

---

**Sources**: raw/Internal Bedrock x CrescerAI Initial SOW.md; raw/SOW 1 Milestone 2 Presentation.pptx; raw/Bedrock SOW 2.md; raw/meeting_transcripts/Iris Sync - 2026_07_10 through 2026_08_07; raw/meeting_transcripts/Iris Sync - 2026_08_07 12_16 EDT - Notes by Gemini.md
