# Learnings

**Summary**: Lessons learned, pitfalls, and insights from execution on the Bedrock ATR project.

**Last updated**: 2026-07-29

---

- **2026-07-29** - **Pixel Mean Blending vs. Summing**: Summing overlapping pixel values causes numerical overflow and clipping (>255), destroying subtle gradient details. Taking the pixel-wise mean preserves intensity nuance and natural background transitions (source: Iris Sync - 2026_07_29).
- **2026-07-29** - **Latent Noise Inpainting for Diffusion Blending**: Copy-pasting a target object onto a generated background, encoding to latent space, adding minor noise, and running 1–2 d-noising diffusion steps naturally forces the pasted object into the target distribution without destroying surrounding background structure (source: Iris Sync - 2026_07_29).
- **2026-07-29** - **XTF vs. Image-Domain Scale Discrepancies**: Transferring objects across datasets in raw XTF space (e.g. VW to ANTX) causes scaling issues due to spatial resolution differences. Image-domain transformations (OpenCV Poisson copy-paste, rotation/scaling matrices) provide significantly greater flexibility and robustness (source: Iris Sync - 2026_07_29).
- **2026-07-28** - **Modifying vs. Converting Data**: Modifying existing Bedrock data for synthetic augmentation produces outputs indistinguishable from standard augmentations. Converting open-source data to the target distribution via procedural generation is more effective for creating genuinely novel training samples (source: Bedrock Discussion Continued (understanding eval agent) - 2026_07_28).
- **2026-07-28** - **Token Limitations for Image Evaluation**: High-resolution images consume too many tokens for full-image LLM evaluation in procedural generation loops. On-device heuristics and computed metrics are needed instead of passing complete images into the model context window (source: Bedrock Discussion Continued (understanding eval agent) - 2026_07_28).
- **2026-07-28** - **Data Convention Assumptions Trap**: The Ulysses dataset showed unexpected patterns (varying shades/shapes) that appeared to be quality issues but may actually be rotation, flip, or coordinate convention differences. Investigating base structure before concluding data is flawed prevents false exclusions (source: Bedrock Discussion Continued (understanding eval agent) - 2026_07_28).
- **2026-07-28** - **SVD/PCA Non-Linear Limitation**: SVD reconstructs images from top 10 singular values but PCA struggles with non-linear components (oscillations in PC4 are not linearly separable). Earth Mover's Distance and frequency domain transforms are better suited for evaluating non-linear distribution components in synthetic vs. real image comparison (source: Bedrock Discussion Continued (understanding eval agent) - 2026_07_28).
- **2026-07-17** - **Magnetometer Amplitude Discrepancy**: The custom preprocessing pipeline replicates Bedrock's filtered magnetometer anomaly locations using raw data and a despiking filter without offline calibration coefficients, but yields peak amplitudes 2-2.5x greater. Relative signal presence is considered sufficient for target verification even if absolute values differ, which is valuable for onboard integration (source: Aux Discussion Mag Data - 2026_07_17).
- **2026-07-17** - **Magnetometer Multi-Pass Purpose**: Repeated survey passes are performed to reduce measurement uncertainty rather than compensate for the vehicle's magnetic field. Vehicle magnetic field compensation is handled in a separate dedicated calibration run on flat, object-free seabed before the survey starts (source: Aux Discussion Mag Data - 2026_07_17).
- **2026-07-17** - **S7K Multi-Beam Z-Axis Orientation**: The Z-axis in S7K/MBES point cloud data is positive downward (depth increases with positive Z values), resolving a misunderstanding where points appeared to lie above sea level (source: Aux Discussion Mag Data - 2026_07_17).
- **2026-07-17** - **Sound Velocity Profile Accuracy**: Using the sensor speed datagram from S7K files as a surface-layer approximation instead of a constant 1500 m/s reduces positional deviation from ~8 cm to under 6 cm against the reference LAS file (source: Aux Discussion Mag Data - 2026_07_17).
- **2026-07-17** - **Virtual Sensor Parameter Efficacy**: Virtual sensor changes in XTF metadata (e.g., altitude and speed) produce visible changes in sonar images. However, roll changes do not visibly affect final mosaic images because the XTF-to-image conversion pipeline does not utilize roll data (source: Iris Sync - 2026_07_17).
- **2026-07-15** - **Poisson Blending Efficacy**: In [[sss-augmentation-methods]], Poisson blending outperformed alpha and direct copy-paste techniques. By utilizing the gradient of the source object, it successfully blends targets into complex backgrounds without creating obvious bounding boundary seams (source: Iris Sync - 2026_07_15).
- **2026-07-15** - **Data Quality Bottleneck**: Manual annotation quality is the primary limiting factor for model accuracy. Labelers over-annotate unclear features or draw imprecise boundaries, raising training loss. The team resolved this by instructing labelers to review and correct annotations by comparing model predictions against manual labels (source: Iris Sync - 2026_07_15).
- **2026-07-10** - **Background Class Error**: An early validation error occurred when the background class was incorrectly included in metric calculations, leading to distorted performance metrics and requiring model retraining (source: Iris Sync - 2026_07_10).
- **2026-07-10** - **Infrastructure Constraints**: Primary server storage limits affect tools like Volley, which fails when storage exceeds 75-80% capacity, requiring periodic checkpoint cleanup (source: Iris Sync - 2026_07_06 and source: Iris Sync - 2026_07_13).
- **2026-06-24** - **XTF Data Gaps**: Black strips in sonar images are caused by missing pings in raw XTF files, not processing bugs. OpenSideScan skips these gaps since it stacks pings sequentially without georeferencing (source: Iris Sync - 2026_06_24).

## Related pages

- [[magnetometer-processing-pipeline]]
- [[magnetometer-fusion]]
- [[sss-augmentation-methods]]
- [[data-quality-and-gaps]]
- [[model-training-and-iterations]]

---

**Sources**: raw/meeting_transcripts/Iris Sync - 2026_06_24 through 2026_07_17; raw/meeting_transcripts/Aux Discussion Mag Data - 2026_07_17
