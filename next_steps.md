# Next Steps

**Summary**: Trackable action items and milestone deliverables from team discussions through August 5, 2026.

**Last updated**: 2026-08-05

---

## Milestone 2 Deliverable Tracking & Completion Status

| Deliverable / Requirement | Description & Scope | Status | Progress & Next Steps (Aug 5, 2026) | Owner |
| :--- | :--- | :--- | :--- | :--- |
| **1. 3-Tier Model Comparison Presentation** | Slide deck presenting baseline SOW 1 model vs retrained SOW 1 model vs V4 performance gains with false positive/negative analysis. | <span style="color: #2e7d32; font-weight: bold;">IN PROGRESS</span> | Sachin constructing slides detailing FP/FN metrics and V4 performance gains. | Sachin |
| **2. Geographic K-Fold Validation** | 5-fold cross-validation with spatial grid/ID partitioning to eliminate data leakage across UXO targets (~11 unique UXOs). | <span style="color: #2e7d32; font-weight: bold;">IN PROGRESS</span> | 100m geo grid split applied. Sachin sharing HTML report of V4 object-level results across folds. | Pratyaksh & Sachin |
| **3. Synthetic Data Integration** | Integration of verified cut-and-paste foreground augmentations into training batches. | <span style="color: #2e7d32; font-weight: bold;">IN PROGRESS</span> | Ratul generating synthetic AOI small black crops via GPT. Hemanth's image decomposition prototypes ready for testing. | Pratyaksh & Ratul |
| **4. Southern California Mission Data Inference** | Qualitative inference pass on newly received SoCal dataset (~300 XTFs, 2km x 2km, >1000 contacts) using V4 model. | <span style="color: #2e7d32; font-weight: bold;">IN PROGRESS</span> | V4 predictions run. Sachin adding 2k-3k pixel filter for AOI Big and output config for UXO/small black isolation. | Geoff & Sachin |
| **5. Containerized Build & Metrics Report** | Demo-ready containerized build suitable for UK Royal Navy demonstration + comprehensive metrics report. | <span style="color: #2e7d32; font-weight: bold;">PENDING</span> | Awaiting object-level K-fold benchmark report and slide deck sign-off. | Team |

---

## Action Items

### Model & Metrics
- <span style="color: green;">**Share V4 Performance Report**: Share HTML report detailing V4 model object-level performance and precision/recall metrics across folds (Aug 5). [Sachin]</span>
- <span style="color: green;">**Run V4 Inference on New Data**: Perform inference on new client data using the V4 model and visualize masks (Aug 5). [Sachin]</span>
- <span style="color: green;">**Update Notion Model Overview**: Update model overview in Notion with K-fold and inference metrics consistent with past documentation (Aug 5). [Sachin]</span>
- <span style="color: green;">**Implement Inference Pixel Filters & Output Config**: Add size filter to exclude items smaller than 2,000–3,000 pixels (AOI Big) and configure class outputs to focus on UXO and small black objects (Aug 5). [Geoff & Sachin]</span>
- **Milestone 2 3-Tier Proof Deck**: Construct presentation slides comparing SOW 1 baseline model vs retrained SOW 1 model vs V4 model, detailing FP/FN analysis (Aug 3). [Sachin]
- **5-Fold Geographic K-Fold Reruns**: Execute spatial K-fold validation across 5 geographically segregated folds for V3, V4, and V3 + Tversky loss once ground truth fixes are complete (Aug 3). [Pratyaksh & Sachin]
- **SoCal Mission Data Qualitative Inference**: Upload ~300 side-scan XTF files from SoCal mission to Wall-E and run qualitative inference pass with V4 model (Aug 3). [Geoff & Sachin]
- **V4 Report Narrative Update**: Update the V4 results report narrative so written context matches presented metrics (July 29). [Sachin]

### Synthetic Data & R&D
- <span style="color: green;">**Generate Synthetic AOI Small Black Objects**: Produce remaining synthetic AOI small black object crops using GPT / nano banana master prompts (Aug 5). [Ratul]</span>
- <span style="color: green;">**Create Comparison Slides**: Compile original and generated synthetic object crops into a PowerPoint presentation (Aug 5). [Ratul]</span>
- <span style="color: green;">**Explore Wall-E Generative Prototypes**: Evaluate Hemanth's suggested generative prototypes on Wall-E (8502 & 8504) for structure/speckle decomposition, VGG sand ripples, and style remixing (Aug 5). [Ratul & Pratyaksh]</span>
- ~~**LoRA Novel Object Generation**: Train LoRA model on 144 object crop examples for novel synthetic object generation (July 31). [Ratul & Pratyaksh]~~ *(Aug 5: Shelved / confirmed unsuccessful for target generation)*
- ~~**GAN Synthetic Generation**: Explore GANs for synthetic target generation (July 28/31). [Ratul]~~ *(Aug 5: Formally shelved due to high data volume requirements and training instability)*
- ~~**Fast Fourier Transform (FFT) Wave Synthesis**: Explore FFT for sonar wave and texture manipulation (July 28). [Ratul]~~ *(Aug 5: Confirmed ineffective for sonar texture synthesis)*
- **Dataset Deduplication**: Clean 10–15 duplicate files per location across DRN, Port, POE, and VW datasets to eliminate data bottlenecks stalling augmentation gains (July 24). [Pratyaksh]
- **LLM-as-Judge Evaluation Framework**: Implement LLM judge (0.9 target score threshold) augmented with AlexNet perceptual loss to score synthetic image distribution fit (July 28). [Pratyaksh & Hemanth]
- **Procedural & Reconstruction Loops**: Test hill-climbing optimization, VAE, and diffusion reconstruction loops (July 28). [Hemanth & Pratyaksh]
- **Diffusion Synthetic Generation & Leakage Prevention**: Set up latent diffusion model for training on background-only splits and integrate target objects via inpainting (July 29/31). [Pratyaksh]
- **Latent Distance Metrics & Dataset Pruning**: Compute latents on generated images to measure distribution distances (FID-like) and prune similar data (July 31). [Pratyaksh & Hemanth]
- **Interactive EMD Application Build**: Build interactive EMD decomposition web application for selecting source images, tuning parameters, and visualizing IMFs (July 31). [Pratyaksh]
- **VAE Feasibility Study**: Pre-train VAE/diffusion models on open-source data and evaluate feasibility (July 28). [Pratyaksh]

### Data Management & Project Execution
- **Centralized Skills Repository**: Create team repository for documenting and sharing skills and technical resources (July 28). [Group]
- **Client Label Verification**: Send image samples of ambiguous small black / UXO targets to Bridget for client label verification (July 24).
- **Sid Onboarding & Transition**: Brief Sid on project status and assist in transitioning project responsibilities over the coming weeks (Aug 3). [Pratyaksh & Sid]

### Magnetometer Processing (MAG)
- **2-Pane Visualization**: Create 2-pane visualization comparing MAG amplitude with XTF imagery, with amplitude peak location markers (July 20). [Ratul]
- **MAG Pipeline Full Run**: Run Ratul's mag pipeline across all annotated Bedrock datasets to generate per-class precision/recall and true/false positive tables (July 17/24). [Ratul]

---

**Sources**: raw/meeting_transcripts/Iris Sync - 2026_07_20 12_30 EDT - Notes by Gemini.md; raw/meeting_transcripts/Meeting started 2026_07_23 15_29 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_07_24 12_29 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_07_27 12_29 EDT - Notes by Gemini.md.md; raw/meeting_transcripts/Bedrock Discussion Continued (understanding eval agent) - 2026_07_28 11_59 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_07_29 12_26 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_07_31 12_26 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_08_03 12_28 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_08_05 12_24 EDT - Notes by Gemini.md
