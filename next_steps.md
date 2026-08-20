# Next Steps

**Summary**: Trackable action items and milestone deliverables from team discussions through August 14, 2026.

**Last updated**: 2026-08-14

---

## Milestone 2 Deliverable Tracking & Completion Status

| Deliverable / Requirement                         | Description & Scope                                                                                                                | Status                                                              | Progress & Next Steps (Aug 14, 2026)                                                                                                              | Owner              |
| :------------------------------------------------ | :--------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------ | :------------------------------------------------------------------------------------------------------------------------------------------------ | :----------------- |
| **1. 3-Tier Model Comparison Presentation**       | Slide deck presenting baseline SOW 1 model vs retrained SOW 1 model vs V4 performance gains with false positive/negative analysis. | <span style="color: #2e7d32; font-weight: bold;">IN PROGRESS</span> | Sachin constructing slides comparing SOW 1 baseline vs retrained SOW 1 vs V4 model versions and 4-bucket confusion matrix categorizations.       | Sachin             |
| **2. Geographic K-Fold Validation**               | 5-fold cross-validation with spatial grid/ID partitioning to eliminate data leakage across UXO targets (~11 unique UXOs).          | <span style="color: #2e7d32; font-weight: bold;">IN PROGRESS</span> | Data leakage resolved and verified; training optimized (repeat factor 1, 200 epochs) and parallelized across Blackwell MIG and Volley for weekend completion. | Pratyaksh & Sachin |
| **3. Synthetic Data Integration**                 | Integration of verified cut-and-paste foreground augmentations and procedural generation into training batches.                   | <span style="color: #2e7d32; font-weight: bold;">IN PROGRESS</span> | Poisson copy-paste + procedural mines achieved top recall (1–2 missed targets); data-driven mask modulation (1.5 SD) committed to Bedrock GitHub repo. | Pratyaksh & Ratul  |
| **4. Southern California & Treasure Island Data** | Performance evaluation and qualitative inference pass on newly received SoCal and Treasure Island datasets using V4 model.         | <span style="color: #2e7d32; font-weight: bold;">IN PROGRESS</span> | Base V4 inference completed on Treasure Island (347 multi-pass / 61 unique contacts detected with rocky background noise); next steps: incorporate rocky tiles into future training and evaluate top M2 model with mag fusion. | Geoff & Sachin     |
| **5. Containerized Build & Metrics Report**       | Demo-ready containerized build suitable for UK Royal Navy demonstration + comprehensive metrics report.                            | <span style="color: #2e7d32; font-weight: bold;">IN PROGRESS</span> | Jetson development environment set up with `cresser` username; weekend container verification underway for end-of-August M2 hard stop.            | Geoff & Sachin     |

---

## Action Items

### Model & Metrics
- <span style="color: #2e7d32;">**Parallelize K-Fold Training Runs (Repeat Factor 1)**: Execute parallel 5-fold training runs on Blackwell MIG and Volley with repeat factor 1 and 200 epoch cap ahead of Monday sync (Aug 14). [Sachin & Pratyaksh]</span>
- <span style="color: #2e7d32;">**Generate Draft 4-Bucket Confusion Matrices**: Produce and share 4-bucket confusion matrices with prediction images by Sunday for team review (Aug 14). [Pratyaksh & Sachin]</span>
- <span style="color: #2e7d32;">**Execute Jetson Onboard Container Verification**: Validate containerized model execution on the Jetson over the weekend for end-of-August M2 delivery (Aug 14). [Geoff & Sachin]</span>
- ~~**Fix K-Fold Crop Data Leakage**: Resolve crop-level file duplication and missing masks in K-fold pipeline within 24 hours (Aug 12). [Sachin, Pratyaksh, Ratul]~~ *(Aug 14: Completed; verified no overlap via pixel counts and crop boundary checks)*
- **Document V4 AUG + Copy-and-Paste in HTML Report**: Document verified 80/20 benchmark results (with corrected class groupings) and confusion matrices within 24 hours (Aug 12/14). [Sachin]
- **Evaluate Treasure Island Dataset on Top Model**: Perform full model evaluation on Treasure Island dataset once K-fold pipeline is corrected (Aug 7/12). [Sachin & Team]
- ~~**Final Data Re-Labeling & Cleaning Pass**: Review model false positive predictions and execute a rapid re-labeling pass to capture missing ground truth UXO / AOI small black annotations (Aug 10). [Sachin & Pratyaksh]~~ *(Aug 12: Completed; ~80 UX annotations integrated into `AOI small black` ground truth)*
- ~~**Train Cut-and-Paste Model Run**: Incorporate corrected cut-and-paste data into model training and verify performance improvements compared to base V4 (Aug 7). [Sachin]~~ *(Aug 12: Completed on verified 80/20 split; V4 AUG + Copy-Paste achieved 92% merged F1 / 94% precision)*
- **Share 4 Result Tables on Slack**: Share four performance tables (2 unprocessed raw prediction tables across folds/models vs. 2 post-processed tables with size/confidence filters) on the project Slack (Aug 10). [Sachin]
- **Post-Processing: Implement Inference Pixel Filters & Output Config**: Add size filter to exclude items smaller than 2,000–3,000 pixels (AOI Big) and configure class outputs to focus on UXO and small black objects (Aug 5). [Geoff & Sachin]
- **Milestone 2 3-Tier Proof Deck**: Construct presentation slides comparing SOW 1 baseline model vs retrained SOW 1 model vs V4 model, detailing FP/FN analysis (Aug 3). [Sachin]
- **V4 Report Narrative Update**: Update the V4 results report narrative so written context matches presented metrics and 4-bucket confusion matrix framework (July 29 / Aug 7). [Sachin]

### Synthetic Data & R&D
- <span style="color: #2e7d32;">**Commit Data-Driven Mask Modulation Code**: Push object mask modulation code and entry point documentation to Bedrock GitHub repo branch (Aug 14). [Ratul]</span>
- <span style="color: #2e7d32;">**Build Side-by-Side Real vs. Synthetic Comparison App**: Develop application for client review comparing real sonar contacts against synthetic targets (Aug 14). [Ratul & Geoff]</span>
- <span style="color: #2e7d32;">**Research Magnetometer Software Verification Source**: Investigate software and filtering tools used for Bedrock's magnetic data verification (Aug 14). [Geoff]</span>
- **Resolve 3D Synthetic Shadow Gap & Share Fit Code**: Investigate 2-pixel shadow gap artifact / alpha blending on 3D objects and share fit/bulge parameter ranges file (Aug 12). [Ratul]
- **Noise Transform Masking & Procedural Training on 80/20**: Implement water-line/padding masking for noise transforms and train procedural model on 80/20 split (Aug 12). [Pratyaksh]
- **Real vs. Synthetic Sonar Image Game**: Build interactive classification game challenging users to identify real vs. synthetic images for client engagement (Aug 12). [Group]
- **Implement Evolutionary Optimization Loop (CMA-ES / CEM)**: Set up derivative-free optimization loop (using `scipy.optimize` or custom CMA-ES/CEM) with structural/color losses to automatically search procedural shape and blending parameters (Aug 10). [Pratyaksh]
- **Evaluate Claude Procedural Generation**: Test procedural object code generation capabilities using Claude (Aug 7). [Pratyaksh]
- **Build Side-by-Side Visualization App**: Develop side-by-side visualization tool to compare real samples against procedurally generated samples (Aug 7). [Pratyaksh]
- **Generate Synthetic AOI Small Black Objects**: Produce remaining synthetic AOI small black object crops using GPT / nano banana master prompts (Aug 5). [Ratul]
- **Create Comparison Slides**: Compile original and generated synthetic object crops into a PowerPoint presentation (Aug 5). [Ratul]
- **Explore Wall-E Generative Prototypes**: Evaluate Hemanth's suggested generative prototypes on Wall-E (8502 & 8504) for structure/speckle decomposition, VGG sand ripples, and style remixing (Aug 5). [Ratul & Pratyaksh]
- ~~**Diffusion Synthetic Generation & Leakage Prevention**: Set up latent diffusion model for training on background-only splits and integrate target objects via inpainting (July 29/31). [Pratyaksh]~~ *(Aug 7: Shelved for target generation - produced unusable "blobs"; pivoted to VLM code-based procedural generation)*
- ~~**LoRA Novel Object Generation**: Train LoRA model on 144 object crop examples for novel synthetic object generation (July 31). [Ratul & Pratyaksh]~~ *(Aug 5: Shelved / confirmed unsuccessful for target generation)*
- ~~**Fast Fourier Transform (FFT) Wave Synthesis**: Explore FFT for sonar wave and texture manipulation (July 28). [Ratul]~~ *(Aug 5: Confirmed ineffective for sonar texture synthesis)*
- ~~**Interactive EMD Application Build**: Build interactive EMD decomposition web application for selecting source images, tuning parameters, and visualizing IMFs (July 31). [Pratyaksh]~~ *(Aug 3: Dropdown directory selection completed for Hemanth)*
- **Dataset Deduplication**: Clean 10–15 duplicate files per location across DRN, Port, POE, and VW datasets to eliminate data bottlenecks stalling augmentation gains (July 24). [Pratyaksh]
- **LLM-as-Judge Evaluation Framework**: Implement LLM judge (0.9 target score threshold) augmented with AlexNet perceptual loss to score synthetic image distribution fit (July 28). [Pratyaksh & Hemanth]
- **Procedural & Reconstruction Loops**: Test hill-climbing optimization, VAE, and diffusion reconstruction loops (July 28). [Hemanth & Pratyaksh]
- **Latent Distance Metrics & Dataset Pruning**: Compute latents on generated images to measure distribution distances (FID-like) and prune similar data (July 31). [Pratyaksh & Hemanth]
- **VAE Feasibility Study**: Pre-train VAE/diffusion models on open-source data and evaluate feasibility (July 28). [Pratyaksh]

### Data Management & Project Execution
- **Centralized Skills Repository**: Create team repository for documenting and sharing skills and technical resources (July 28). [Group]
- **Client Label Verification**: Send image samples of ambiguous small black / UXO targets to Bridget for client label verification (July 24).
- **Sid Onboarding & Transition**: Brief Sid on project status and assist in transitioning project responsibilities over the coming weeks (Aug 3). [Pratyaksh & Sid]

### Magnetometer Processing (MAG) & Milestone 3
- **MAG Data & Ground Truth Correlation**: Correlate MAG data analysis with ground truth annotations to prepare for Milestone 3 (Aug 7). Create 2-pane visualization comparing MAG amplitude with XTF imagery, with amplitude peak location markers (July 20). Run Ratul's mag pipeline across all annotated Bedrock datasets to generate per-class precision/recall and true/false positive tables (July 17/24). [Ratul]

---

**Sources**: raw/meeting_transcripts/Iris Sync - 2026_07_20 12_30 EDT - Notes by Gemini.md; raw/meeting_transcripts/Meeting started 2026_07_23 15_29 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_07_24 12_29 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_07_27 12_29 EDT - Notes by Gemini.md.md; raw/meeting_transcripts/Bedrock Discussion Continued (understanding eval agent) - 2026_07_28 11_59 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_07_29 12_26 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_07_31 12_26 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_08_03 12_28 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_08_05 12_24 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_08_07 12_16 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_08_10 12_27 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_08_12 12_27 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_08_14 12_30 EDT - Notes by Gemini.md

