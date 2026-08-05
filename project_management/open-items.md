# Open Items

**Summary**: Active and resolved action items, blockers, and follow-ups for the Bedrock ATR project.

**Last updated**: 2026-08-05

---

## Active items

- **2026-08-05** - **V4 Performance Report Sharing**: Sachin to share HTML performance report detailing V4 object-level results across folds (source: Iris Sync - 2026_08_05). [Status: Open]
- **2026-08-05** - **V4 Inference & Notion Documentation**: Sachin to run V4 inference on new data and update model overview in Notion with K-fold and inference metrics (source: Iris Sync - 2026_08_05). [Status: Open]
- **2026-08-05** - **Synthetic AOI Small Black Generation**: Ratul to produce remaining synthetic AOI small black object crops using GPT prompts (source: Iris Sync - 2026_08_05). [Status: Open]
- **2026-08-05** - **Synthetic Object Comparison Presentation**: Ratul to compile original vs generated synthetic object images into a PowerPoint presentation (source: Iris Sync - 2026_08_05). [Status: Open]
- **2026-08-05** - **Wall-E Generative Prototype Exploration**: Ratul to evaluate Hemanth's generative prototypes on Wall-E (8502 & 8504) and discuss with Pratyaksh (source: Iris Sync - 2026_08_05). [Status: Open]
- **2026-08-03** - **SoCal Data Upload & Inference**: Geoff to upload Southern California mission data to Wall-E; Sachin to run qualitative inference pass with V4 model (source: Iris Sync - 2026_08_03). [Status: Open]
- **2026-08-03** - **Milestone 2 Presentation Deck**: Sachin to prepare slides detailing model performance (3-tier SOW1 vs retrained SOW1 vs V4), false positives, and false negatives (source: Iris Sync - 2026_08_03). [Status: Open]
- **2026-08-03** - **5-Fold Geographic K-Fold Reruns**: Pratyaksh and Sachin to rerun V3, V4, and V3 + Tversky loss across the 5 spatial K-folds once Ratul finishes ground truth fixes (source: Iris Sync - 2026_08_03). [Status: Open]
- **2026-08-03** - **Synthetic Foreground Generation Agent**: Sachin to configure procedural agent for object category foreground generation; Pratyaksh to evaluate progress (source: Iris Sync - 2026_08_03). [Status: Open]
- **2026-08-03** - **Training Set Clustering Report**: Pratyaksh to analyze clustered training image text files and report on cluster similarities to existing training examples (source: Iris Sync - 2026_08_03). [Status: Open]
- **2026-08-03** - **EMD App Directory Setup**: Pratyaksh to complete dropdown directory selection setup in EMD app for Hemanth (source: Iris Sync - 2026_08_03). [Status: Open]
- **2026-08-03** - **Sid Onboarding & Transition**: Pratyaksh to brief Sid on project status and assist in transitioning project responsibilities over the next month (source: Iris Sync - 2026_08_03). [Status: Open]
- **2026-07-31** - **Object Orientation & Calibration Pass Cross-Check**: Ratul to cross-check target object orientations and verify XTF source files to confirm objects are not from calibration paths (source: Iris Sync - 2026_07_31). [Status: Open]
- **2026-07-31** - **Base Ground Truth Data Issue Resolution**: Sachin to resolve underlying base ground truth annotation issues and incorrect markings by Monday (source: Iris Sync - 2026_07_31). [Status: Open]
- **2026-07-31** - **K-Fold Model Benchmark Update**: Sachin to update K-fold model results in Bedrock channel once dataset issues are resolved (source: Iris Sync - 2026_07_31). [Status: Open]
- **2026-07-31** - **Background Diffusion Model Refinement**: Pratyaksh to refine dataset for background generation model (removing black artifact regions) and proceed with fine-tuning (source: Iris Sync - 2026_07_31). [Status: Open]
- **2026-07-31** - **Latent Diffusion Setup**: Pratyaksh to set up latent diffusion model for training (source: Iris Sync - 2026_07_31). [Status: Open]
- **2026-07-31** - **Latent Space Distance Computation**: Pratyaksh to compute latents on generated images to measure distribution distances and prune similar data (source: Iris Sync - 2026_07_31). [Status: Open]
- **2026-07-31** - **FID Diversity Techniques Investigation**: Pratyaksh to investigate FID and related techniques for ensuring generation of diverse synthetic examples (source: Iris Sync - 2026_07_31). [Status: Open]
- **2026-07-31** - **Interactive EMD Application Build**: Pratyaksh to build an EMD decomposition application where users can select source images and modify parameters (source: Iris Sync - 2026_07_31). [Status: Open]
- **2026-07-29** - **V4 Report Narrative Update**: Sachin to update the V4 results report narrative so written context matches presented metrics (source: Iris Sync - 2026_07_29). [Status: Open]
- **2026-07-29** - **Diffusion Clean Split Model Training**: Pratyaksh to train a new diffusion model using a clean 75/25 background split to prevent data leakage during classification evaluation (source: Iris Sync - 2026_07_29). [Status: Open]
- **2026-07-29** - **Image-Domain Augmentation Research**: Ratul to investigate and implement runtime image-domain augmentations (OpenCV Poisson blending) (source: Iris Sync - 2026_07_29). [Status: Open]
- **2026-07-28** - **Skills Repository**: Create a centralized repository for documenting and sharing team skills and technical resources (source: Bedrock Discussion Continued (understanding eval agent) - 2026_07_28). [Status: Open]
- **2026-07-28** - **Procedural Generation Testing**: Test procedural generation using LLM judge to transform open-source images into target distribution (source: Bedrock Discussion Continued (understanding eval agent) - 2026_07_28). [Status: Open]
- **2026-07-28** - **EMD and Frequency Domain Testing**: Pratyaksh to experiment with Earth Mover's Distance and frequency domain transforms for image component isolation (source: Bedrock Discussion Continued (understanding eval agent) - 2026_07_28). [Status: Open]
- **2026-07-28** - **VAE Feasibility Study**: Pratyaksh to set up VAE pre-training on open-source data and report feasibility (source: Bedrock Discussion Continued (understanding eval agent) - 2026_07_28). [Status: Open]
- **2026-07-17** - **Magnetometer Pipeline Validation**: Run the current magnetometer pipeline on all annotated Bedrock datasets to generate per-class precision/recall and true/false positive tables (source: Aux Discussion Mag Data - 2026_07_17). [Status: Open]
- **2026-07-17** - **Confirmed UXO Toggle**: Implement a separate JSON toggle in the annotation schemas to distinguish confirmed UXOs from other small black artifacts (source: Iris Sync - 2026_07_17). [Status: In-Progress]
- **2026-07-17** - **Cross-Dataset Transformation**: Develop techniques for style-transferring VW data to match DRN or POE appearance for robust out-of-distribution evaluation (source: Iris Sync - 2026_07_17). [Status: Open]
- **2026-07-17** - **Black Patch Reclassification**: Move ambiguous small black artifacts to the black patch category in the next training cycle (source: Bedrock connect - 2026_07_17). [Status: Open]
- **2026-07-06** - **Jetson Backbone Selection**: Select and benchmark model backbones for compatibility with the Jetson onboard processor after establishing initial baselines (source: Iris Sync - 2026_07_06 and source: Iris Sync - 2026_07_13). [Status: Open]

## Resolved items
 
- **2026-07-15** - **VW File Count Discrepancy**: Investigate the missing ~118 processed files in the Vineyard Winds dataset (345 files found vs. 463 expected), likely due to an incomplete unzip process (source: Iris Sync - 2026_07_15). [Status: Resolved - issue with VW phase 2 upload on FTP.]
- **2026-07-08** - **Multi-Class vs. Binary Output Confirmation**: Clarify with Bedrock on Slack if they require multi-class or single-class binary outputs from the model (source: Iris Sync - 2026_07_08). [Status: Resolved in meeting with Bridgit: Multi-class preferred, but binary UXO is sufficient as MVP if needed]
- **2026-07-17** - **S7K Depth Coordinate Direction**: Clarify the Z-axis orientation in S7K/MBES data (source: Aux Discussion Mag Data - 2026_07_17). [Status: Resolved on 2026-07-17: confirmed Z-axis is positive downward, resolving depth inconsistencies.]
- **2026-07-17** - **S7K Sound Velocity Drift**: Improve S7K point cloud alignment (source: Aux Discussion Mag Data - 2026_07_17). [Status: Resolved on 2026-07-17: used surface sensor speed datagram instead of constant 1500 m/s, reducing deviation from 8 cm to under 6 cm.]
- **2026-07-17** - **Synthetic Mine Generation**: Create realistic synthetic mine examples for rare-class training (source: Iris Sync - 2026_07_15). [Status: Resolved on 2026-07-17: successfully generated cylindrical targets with shadow and sine-wave pattern in image space.]
- **2026-07-17** - **Copy-Paste Augmentation Implementation**: Implement target copy-pasting for training data augmentation (source: Iris Sync - 2026_07_06). [Status: Resolved on 2026-07-17: completed and integrated copy-paste pipeline with Poisson blending.]

## Related pages

- [[automated-target-recognition]]
- [[magnetometer-fusion]]
- [[sss-augmentation-methods]]
- [[onboard-deployment]]
- [[data-quality-and-gaps]]

---

**Sources**: raw/meeting_transcripts/Iris Sync - 2026_06_24 through 2026_07_31; raw/meeting_transcripts/Aux Discussion Mag Data - 2026_07_17; raw/meeting_transcripts/Bedrock connect - 2026_07_17; raw/meeting_transcripts/Bedrock Discussion Continued (understanding eval agent) - 2026_07_28
