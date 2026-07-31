# Next Steps

**Summary**: Action items, completed tasks, and upcoming milestones from team discussions through July 24, 2026.

**Last updated**: 2026-07-27

---

## Bridget Meeting — Thursday July 23, 5 PM ET

### Model Demo
- ~~Connect the best V2 model to the Streamlit app [Sachin]~~ *(Completed: V3 model selected and deployed to Streamlit app instance `8505` on July 23)*
- ~~Add toggle in the app to switch between old (delivered) and new model versions [Sachin]~~ *(Completed: Added model toggle)*
- ~~Metrics table must include improvement indicators vs. baseline, displayed in parentheses [Sachin]~~ *(Completed)*
- ~~Exclude images where UXO objects are not visually identifiable from metric calculations [Sachin]~~ *(Completed)*
- ~~Use overlap threshold >0.01 for internal evaluation; 0.01 for client presentation~~ *(Completed)*

### Synthetic Data Outputs
- ~~Create slides illustrating synthetic data outputs for the meeting [Pratyaksh]~~ *(Completed)*
- ~~Include examples from: diffusion model background/object generation, copy-paste augmentation, procedural cylindrical mine generation~~ *(Completed)*

### Deliverables
- ~~Generate geo-referenced JSON files for sand ripples and black patches, formatted for drag-and-drop onto XTF/mosaic software [Sachin]~~ *(Completed)*

### Open Questions for Bedrock
- ~~Sand ripples: should we include them in the model?~~ *(Resolved July 24: Deprioritized by client; focus shifted exclusively to UXO and small black patches)*
- ~~Black patches: what classification approach do they prefer?~~ *(Resolved July 24: Client prioritizes recall over precision and accepts false positives; UXO & AOI small black merged for training)*
- ~~Open-source data: should we train on it for pre-training?~~ *(Resolved July 24: Open-source sonar data approved for pre-training, fine-tuned on Bedrock data)*

---

## Model & Metrics

- Updated dataset (with VW phase 2 data) is now the project baseline for all future comparisons
- Pixel threshold filter at 100px documented as the primary improvement driver (~20% precision-recall gain without losing true positives)
- Six models trained across V1 (original pipeline) and V2 (adjusted hyperparameters), each with three label grouping strategies (binary, multiclass, UXO-class). V2 outperforms V1 across all groupings
- AI big class performance heavily improved after VW phase 2 data inclusion
- Overall assessment: preliminary results are better than baseline but not yet at strong customer-satisfaction levels
- <span style="color: #2e7d32;">**V3 Model Selection**: Deployed V3 model as top performer for UXO and general classes to Streamlit instance `8505` (July 23).</span>
- <span style="color: #2e7d32;">**512px Resolution Standard**: Hyperparameter search confirmed 512-pixel inputs consistently outperform 256-pixel inputs (July 22).</span>
- <span style="color: #2e7d32;">**Augmentation Leader**: Poisson blending + roll + cutmix combination achieved top object F1 of 0.49 @ 20% IOU (July 22).</span>
- <span style="color: #2e7d32;">**Object Metric Fix**: Fixed calculation error where large objects ("AI big") with ~80% pixel overlap were fragmented into separate annotations, deflating F1 (July 23). [Sachin]</span>
- <span style="color: #2e7d32;">**K-Fold Spatial Partitioning**: Adopted K-fold cross-validation with manual spatial splits to prevent data leakage from tile overlap (July 22/24).</span>
- <span style="color: #2e7d32;">**UXO / Small Black Class Merging**: Merging UXO and AOI small black into a single class during training to maximize signal and boost UXO recall, while retaining separate classes for evaluation (July 24).</span>
- <span style="color: #2e7d32;">**Client Recall Preference**: Client explicitly confirmed preference for recall over precision (accepting false positives to prevent missed contacts) and qualitative demos over rigid metric hurdles (July 24).</span>

---

## Synthetic Data Baseline Testing

- ~~Train no-advanced-augmentation baseline model [Pratyaksh]~~ *(Completed July 22)*
- ~~Train variants with individual augmentations and combinations to measure delta vs. baseline...~~ *(Completed July 22: Poisson + roll + cutmix identified as best combination)*
- ~~Review classical augmentation outputs together to identify effective methods [Sachin & Pratyaksh]~~ *(Completed July 22)*
- ~~Results due Wednesday before client meeting~~ *(Completed: Presented July 23)*
- <span style="color: #2e7d32;">**Dataset Duplication Bottleneck**: Discovered 10–15 duplicate files per location across DRN, Port, POE, and VW datasets, identifying data volume/diversity as the primary bottleneck stalling augmentation gains (July 24). [Pratyaksh]</span>
- <span style="color: #2e7d32;">**Flux Turbo + LoRA Synthetic Pipeline**: Implemented synthetic UXO generation categorized by target elongation using Flux Turbo + LoRA models (July 24). [Ratul]</span>
- <span style="color: #2e7d32;">**Real-to-Sim Physics Simulation**: Proposed rendering side-scan intensity returns using raw XTF metadata (trajectories, altitude, depth, MAG) via LLM agent physics prompts (July 24). [Hemanth]</span>

---

## Data Management

- ~~Compile centralized reference list of all open-source and raw datasets in the project tracker, including source URLs and metadata [Sachin]~~ *(Completed July 24)*
- ~~Move VW phase 2 data on SFTP [Geoff]~~ *(Completed July 24)*
- Formalize documentation with dated entries, links to reports, TL;DR rationale, results, and proposed next steps [Sachin]
- <span style="color: #2e7d32;">**Mandatory Code Backup Policy**: Enforce policy requiring all training, fine-tuning, and project code to be committed and backed up to GitHub (July 24).</span>
- <span style="color: #2e7d32;">**Dataset Deduplication**: Clean duplicate files (10–15 duplicates per location) from training sets to prevent model overfitting (July 24). [Pratyaksh]</span>
- <span style="color: #2e7d32;">**Validation Set Image Retention**: Retain all validation images (including long/zoomed-out views) for statistical reliability (July 24).</span>
- <span style="color: #2e7d32;">**Client Label Verification**: Send image samples of ambiguous small black / UXO targets to Bridget for client label verification (July 24).</span>

---

## MAG (Excluded From Client Meeting)

- Create 2-pane visualization comparing MAG amplitude with XTF imagery, with amplitude peak location marker [Ratul]
- Current MAG location accuracy: 5-10 m range, unchanged
- ~~MAG data will not be presented to Bedrock at the July 23 meeting unless specific questions arise requiring client input~~ *(Completed: Excluded from July 23 meeting as planned)*
- <span style="color: #2e7d32;">**MAG Pipeline Full Run**: Execute Ratul's mag pipeline across all annotated Bedrock datasets to generate per-class precision/recall and true/false positive tables (July 17/24). [Ratul]</span>

---

**Sources**: raw/meeting_transcripts/Iris Sync - 2026_07_20 12_30 EDT - Notes by Gemini.md; raw/meeting_transcripts/Meeting started 2026_07_23 15_29 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_07_24 12_30 EDT - Notes by Gemini.md
