# Next Steps

**Summary**: Trackable action items and milestone deliverables from team discussions through August 10, 2026.

**Last updated**: 2026-08-10

---

## Milestone 2 Deliverable Tracking & Completion Status

| Deliverable / Requirement                         | Description & Scope                                                                                                                | Status                                                              | Progress & Next Steps (Aug 10, 2026)                                                                                                              | Owner              |
| :------------------------------------------------ | :--------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------ | :------------------------------------------------------------------------------------------------------------------------------------------------ | :----------------- |
| **1. 3-Tier Model Comparison Presentation**       | Slide deck presenting baseline SOW 1 model vs retrained SOW 1 model vs V4 performance gains with false positive/negative analysis. | <span style="color: #2e7d32; font-weight: bold;">IN PROGRESS</span> | Sachin constructing slides comparing SOW 1 baseline vs retrained SOW 1 vs V4 model versions and false positive categorizations.                | Sachin             |
| **2. Geographic K-Fold Validation**               | 5-fold cross-validation with spatial grid/ID partitioning to eliminate data leakage across UXO targets (~11 unique UXOs).          | <span style="color: #2e7d32; font-weight: bold;">IN PROGRESS</span> | Completed runs across ~20 models; V4 confirmed highest recall. V4 AUG + Cut-and-Paste undergoing final cross-validation testing.                  | Pratyaksh & Sachin |
| **3. Synthetic Data Integration**                 | Integration of verified cut-and-paste foreground augmentations into training batches.                                              | <span style="color: #2e7d32; font-weight: bold;">IN PROGRESS</span> | Radial boundary distance shapes parameterized; setting up derivative-free evolutionary optimization loop (CMA-ES/CEM) for automated tuning.      | Pratyaksh & Ratul  |
| **4. Southern California & Treasure Island Data** | Performance evaluation and qualitative inference pass on newly received SoCal and Treasure Island datasets using V4 model.         | <span style="color: #2e7d32; font-weight: bold;">IN PROGRESS</span> | Evaluating model performance on Treasure Island dataset to fulfill M2 requirements.                                                               | Geoff & Sachin     |
| **5. Containerized Build & Metrics Report**       | Demo-ready containerized build suitable for UK Royal Navy demonstration + comprehensive metrics report.                            | <span style="color: #2e7d32; font-weight: bold;">IN PROGRESS</span> | Geoff spearheading Jetson deployment testing with Sachin to deliver models and complete M2 package this week.                                     | Geoff & Sachin     |

---

## Action Items

### Model & Metrics
- <span style="color: #2e7d32;">**Share 4 Result Tables on Slack**: Share four performance tables (2 unprocessed raw prediction tables across folds/models vs. 2 post-processed tables with size/confidence filters) on the project Slack (Aug 10). [Sachin]</span>
- <span style="color: #2e7d32;">**Validate V4 AUG + Cut-and-Paste via Cross-Validation**: Train and evaluate V4 AUG with cut-and-paste augmentation across folds to validate whether it confirms leading candidate status for Milestone 2 (Aug 10). [Sachin]</span>
- <span style="color: #2e7d32;">**Final Data Re-Labeling & Cleaning Pass**: Review model false positive predictions and execute a rapid re-labeling pass to capture missing ground truth UXO / AOI small black annotations (Aug 10). [Sachin & Pratyaksh]</span>
- <span style="color: #2e7d32;">**Complete Jetson Onboard Deployment Testing**: Finalize and validate model container execution on Jetson embedded hardware for Milestone 2 delivery this week (Aug 10). [Geoff & Sachin]</span>
- **Compare Model Performance Table**: Analyze and document fine-tuned performance numbers comparing previous baseline/fine-tuned results with V4 versions (Aug 7). [Sachin]
- ~~**Finish Cross-Validation Metrics**: Complete cross-validation metrics for trained models across folds and share results (Aug 7). [Sachin]~~ *(Aug 10: Completed across ~20 models/folds; V4 demonstrated highest recall)*
- **Train Cut-and-Paste Model Run**: Incorporate corrected cut-and-paste data into model training and verify performance improvements compared to base V4 (Aug 7). [Sachin]
- **Evaluate Treasure Island Dataset**: Perform assessment of model performance using the new Treasure Island dataset for Milestone 2 completion (Aug 7). [Team]
- **Implement Inference Pixel Filters & Output Config**: Add size filter to exclude items smaller than 2,000–3,000 pixels (AOI Big) and configure class outputs to focus on UXO and small black objects (Aug 5). [Geoff & Sachin]
- **Milestone 2 3-Tier Proof Deck**: Construct presentation slides comparing SOW 1 baseline model vs retrained SOW 1 model vs V4 model, detailing FP/FN analysis (Aug 3). [Sachin]
- ~~**5-Fold Geographic K-Fold Reruns**: Execute spatial K-fold validation across 5 geographically segregated folds for V3, V4, and V3 + Tversky loss with zero-F1 early stopping rule (Aug 3/7). [Pratyaksh & Sachin]~~ *(Aug 10: Completed across ~20 models)*
- **SoCal Mission Data Qualitative Inference**: Upload ~300 side-scan XTF files from SoCal mission to Wall-E and run qualitative inference pass with V4 model (Aug 3). [Geoff & Sachin]
- **V4 Report Narrative Update**: Update the V4 results report narrative so written context matches presented metrics and 4-bucket confusion matrix framework (July 29 / Aug 7). [Sachin]

### Synthetic Data & R&D
- <span style="color: #2e7d32;">**Implement Evolutionary Optimization Loop (CMA-ES / CEM)**: Set up derivative-free optimization loop (using `scipy.optimize` or custom CMA-ES/CEM) with structural/color losses to automatically search procedural shape and blending parameters (Aug 10). [Pratyaksh]</span>
- <span style="color: #2e7d32;">**Finalize Radial Boundary Shape Parameters & Deliver within 24 Hours**: Deliver tuned radial boundary distance shape parameters (with 0.7–0.9 background drop rates and blend mask multipliers) to unblock pipeline training (Aug 10). [Ratul]</span>
- <span style="color: #2e7d32;">**Run Synthetic Model Iterations**: Complete 1–2 model training iterations using synthetic data by Wednesday (Aug 10). [Pratyaksh]</span>
- **Evaluate Claude Procedural Generation**: Test procedural object code generation capabilities using Claude (Aug 7). [Pratyaksh]
- **Build Side-by-Side Visualization App**: Develop side-by-side visualization tool to compare real samples against procedurally generated samples (Aug 7). [Pratyaksh]
- **Generate Synthetic AOI Small Black Objects**: Produce remaining synthetic AOI small black object crops using GPT / nano banana master prompts (Aug 5). [Ratul]
- **Create Comparison Slides**: Compile original and generated synthetic object crops into a PowerPoint presentation (Aug 5). [Ratul]
- **Explore Wall-E Generative Prototypes**: Evaluate Hemanth's suggested generative prototypes on Wall-E (8502 & 8504) for structure/speckle decomposition, VGG sand ripples, and style remixing (Aug 5). [Ratul & Pratyaksh]
- ~~**Diffusion Synthetic Generation & Leakage Prevention**: Set up latent diffusion model for training on background-only splits and integrate target objects via inpainting (July 29/31). [Pratyaksh]~~ *(Aug 7: Shelved for target generation - produced unusable "blobs"; pivoted to VLM code-based procedural generation)*
- ~~**LoRA Novel Object Generation**: Train LoRA model on 144 object crop examples for novel synthetic object generation (July 31). [Ratul & Pratyaksh]~~ *(Aug 5: Shelved / confirmed unsuccessful for target generation)*
- ~~**Fast Fourier Transform (FFT) Wave Synthesis**: Explore FFT for sonar wave and texture manipulation (July 28). [Ratul]~~ *(Aug 5: Confirmed ineffective for sonar texture synthesis)*
- **Dataset Deduplication**: Clean 10–15 duplicate files per location across DRN, Port, POE, and VW datasets to eliminate data bottlenecks stalling augmentation gains (July 24). [Pratyaksh]
- **LLM-as-Judge Evaluation Framework**: Implement LLM judge (0.9 target score threshold) augmented with AlexNet perceptual loss to score synthetic image distribution fit (July 28). [Pratyaksh & Hemanth]
- **Procedural & Reconstruction Loops**: Test hill-climbing optimization, VAE, and diffusion reconstruction loops (July 28). [Hemanth & Pratyaksh]
- **Latent Distance Metrics & Dataset Pruning**: Compute latents on generated images to measure distribution distances (FID-like) and prune similar data (July 31). [Pratyaksh & Hemanth]
- ~~**Interactive EMD Application Build**: Build interactive EMD decomposition web application for selecting source images, tuning parameters, and visualizing IMFs (July 31). [Pratyaksh]~~
- **VAE Feasibility Study**: Pre-train VAE/diffusion models on open-source data and evaluate feasibility (July 28). [Pratyaksh]

### Data Management & Project Execution
- **Centralized Skills Repository**: Create team repository for documenting and sharing skills and technical resources (July 28). [Group]
- **Client Label Verification**: Send image samples of ambiguous small black / UXO targets to Bridget for client label verification (July 24).
- **Sid Onboarding & Transition**: Brief Sid on project status and assist in transitioning project responsibilities over the coming weeks (Aug 3). [Pratyaksh & Sid]

### Magnetometer Processing (MAG) & Milestone 3
- **MAG Data & Ground Truth Correlation**: Correlate MAG data analysis with ground truth annotations to prepare for Milestone 3 (Aug 7). Create 2-pane visualization comparing MAG amplitude with XTF imagery, with amplitude peak location markers (July 20). Run Ratul's mag pipeline across all annotated Bedrock datasets to generate per-class precision/recall and true/false positive tables (July 17/24). [Ratul]

---

**Sources**: raw/meeting_transcripts/Iris Sync - 2026_07_20 12_30 EDT - Notes by Gemini.md; raw/meeting_transcripts/Meeting started 2026_07_23 15_29 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_07_24 12_29 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_07_27 12_29 EDT - Notes by Gemini.md.md; raw/meeting_transcripts/Bedrock Discussion Continued (understanding eval agent) - 2026_07_28 11_59 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_07_29 12_26 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_07_31 12_26 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_08_03 12_28 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_08_05 12_24 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_08_07 12_16 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_08_10 12_27 EDT - Notes by Gemini.md
