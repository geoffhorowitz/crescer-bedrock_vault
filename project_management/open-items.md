# Open Items

**Summary**: Active and resolved action items, blockers, and follow-ups for the Bedrock ATR project.

**Last updated**: 2026-07-29

---

## Active items

- **2026-07-29** - **V4 Report Narrative Update**: Sachin to update the V4 results report narrative so written context matches presented metrics (source: Iris Sync - 2026_07_29). [Status: Open]
- **2026-07-29** - **Diffusion Clean Split Model Training**: Pratyaksh to train a new diffusion model using a clean 75/25 background split to prevent data leakage during classification evaluation (source: Iris Sync - 2026_07_29). [Status: Open]
- **2026-07-29** - **Scaling Comparison Slack Share**: Ratul to share before-and-after images of object scaling on Slack for team review (source: Iris Sync - 2026_07_29). [Status: Open]
- **2026-07-29** - **EMD Decomposition Slack Share**: Pratyaksh to post images of EMD decomposition results on Slack (source: Iris Sync - 2026_07_29). [Status: Open]
- **2026-07-29** - **Image-Domain Augmentation Research**: Ratul to investigate and implement runtime image-domain augmentations (OpenCV Poisson blending) (source: Iris Sync - 2026_07_29). [Status: Open]
- **2026-07-29** - **Screen Recording Setup**: Geoff to ensure video capture is enabled for all upcoming meeting invites in the series (source: Iris Sync - 2026_07_29). [Status: Open]
- **2026-07-28** - **Skills Repository**: Create a centralized repository for documenting and sharing team skills and technical resources (source: Bedrock Discussion Continued (understanding eval agent) - 2026_07_28). [Status: Open]
- **2026-07-28** - **Procedural Generation Testing**: Test procedural generation using LLM judge to transform open-source images into target distribution (source: Bedrock Discussion Continued (understanding eval agent) - 2026_07_28). [Status: Open]
- **2026-07-28** - **EMD and Frequency Domain Testing**: Pratyaksh to experiment with Earth Mover's Distance and frequency domain transforms for image component isolation (source: Bedrock Discussion Continued (understanding eval agent) - 2026_07_28). [Status: Open]
- **2026-07-28** - **VAE Feasibility Study**: Pratyaksh to set up VAE pre-training on open-source data and report feasibility (source: Bedrock Discussion Continued (understanding eval agent) - 2026_07_28). [Status: Open]
- **2026-07-28** - **Image Augmentation Repository Sharing**: Sachin to post the HTML repository containing image augmentation data to Slack (source: Bedrock Discussion Continued (understanding eval agent) - 2026_07_28). [Status: Open]
- **2026-07-17** - **Magnetometer Pipeline Validation**: Run the current magnetometer pipeline on all annotated Bedrock datasets to generate per-class precision/recall and true/false positive tables (source: Aux Discussion Mag Data - 2026_07_17). [Status: Open]
- **2026-07-17** - **Confirmed UXO Toggle**: Implement a separate JSON toggle in the annotation schemas to distinguish confirmed UXOs from other small black artifacts (source: Iris Sync - 2026_07_17). [Status: In-Progress]
- **2026-07-17** - **Cross-Dataset Transformation**: Develop techniques for style-transferring VW data to match DRN or POE appearance for robust out-of-distribution evaluation (source: Iris Sync - 2026_07_17). [Status: Open]
- **2026-07-17** - **Black Patch Reclassification**: Move ambiguous small black artifacts to the black patch category in the next training cycle (source: Bedrock connect - 2026_07_17). [Status: Open]
- **2026-07-06** - **Jetson Backbone Selection**: Select and benchmark model backbones for compatibility with the Jetson onboard processor after establishing initial baselines (source: Iris Sync - 2026_07_06 and source: Iris Sync - 2026_07_13). [Status: Open]

## Resolved items

- - **2026-07-15** - **VW File Count Discrepancy**: Investigate the missing ~118 processed files in the Vineyard Winds dataset (345 files found vs. 463 expected), likely due to an incomplete unzip process (source: Iris Sync - 2026_07_15). [Status: Resolved - issue with VW phase 2 upload on FTP.]
- **2026-07-08** - **Multi-Class vs. Binary Output Confirmation**: Clarify with Bedrock on Slack if they require multi-class or single-class binary outputs from the model (source: Iris Sync - 2026_07_08). [Status: Resolved in meeting with Bridgit: Multi-class preferred, but binary UXO is sufficient as MVP if needed]
- 026-07-17** - **S7K Depth Coordinate Direction**: Clarify the Z-axis orientation in S7K/MBES data (source: Aux Discussion Mag Data - 2026_07_17). [Status: Resolved on 2026-07-17: confirmed Z-axis is positive downward, resolving depth inconsistencies.]
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

**Sources**: raw/meeting_transcripts/Iris Sync - 2026_06_24 through 2026_07_17; raw/meeting_transcripts/Aux Discussion Mag Data - 2026_07_17; raw/meeting_transcripts/Bedrock connect - 2026_07_17
