# Onboard Deployment

**Summary**: Onboard deployment covers packaging, runtime, input format, and AUV integration support for running Bedrock ATR models on embedded hardware.

**Last updated**: 2026-08-14

---

## Hardware And Runtime

The initial SOW requires a Docker image with a sample model capable of running on Jetson TX2 using TensorRT 8, a minimal runtime environment, and command-line inference (source: Internal Bedrock x CrescerAI Initial SOW.md).

The milestone deck reports Jetson Nano benchmark results and states that TX2 performance is expected to be better (source: SOW 1 Milestone 2 Presentation.pptx).

## Jetson Testing & Model Delivery Status (August 10)

As the project transitions to shipping mode for Milestone 2 closure, Geoff Horowitz is spearheading final Jetson testing with Sachin Pandey's support, aiming to finalize model delivery to Bedrock and complete embedded Jetson testing within the week (source: Iris Sync - 2026_08_10).

## Jetson Deployment Architecture & M2 Timeline (August 12)

Deployment architecture and timelines were clarified during the August 12 sync (source: Iris Sync - 2026_08_12):
- **Architecture Split**: The model inference pipeline will run directly on the embedded Jetson device, while the Streamlit application user interface will be hosted on local development machines or the Wally server.
- **Weekend Verification**: Geoff and Sachin scheduled a weekend working session to configure and test the Jetson deployment scripts to prevent integration blockers.
## Jetson Embedded Environment Setup (August 14)

Geoff confirmed the completion of the Jetson embedded development environment setup for Sachin (source: Iris Sync - 2026_08_14):
- **User and Path Consistency**: Configured with the standard username `cresser` (and admin privileges) to mirror directory paths and file conventions on Bedrock's Jetson devices.
- **Onboard Verification Readiness**: Sachin verified SSH access, establishing readiness for containerized model inference testing over the weekend ahead of the end-of-August Milestone 2 delivery deadline.

## Integration Support

SOW 2 makes Bedrock's team primarily responsible for onboard integration while Crescer AI provides responsive support and interface validation (source: Bedrock SOW 2.md).

SOW 2 Milestone 1 is complete when Bedrock's integration lead confirms the model runs stably onboard the AUV on Bedrock-generated PNG inputs (source: Bedrock SOW 2.md).

## Input Format

SOW 2 requires Bedrock and Crescer AI to define a PNG input specification for real-time onboard inference, including dimensions, layout, intensity normalization, scaling, and slant-range or geometric corrections expected upstream (source: Bedrock SOW 2.md).

Bedrock retains ownership of the real-time preprocessing pipeline, and Crescer AI retains no rights to it (source: Bedrock SOW 2.md).

## Related pages

- [[automated-target-recognition]]
- [[model-performance-and-metrics]]
- [[model-training-and-iterations]]
- [[data-rights-and-ip]]
- [[internal-bedrock-x-crescerai-initial-sow]]
- [[sow-1-milestone-2-presentation]]
- [[bedrock-sow-2]]
- [[mollusk-platform]]
- [[iris-sync-2026-08-10]]
- [[iris-sync-2026-08-12]]
- [[iris-sync-2026-08-14]]

---

**Sources**: raw/Internal Bedrock x CrescerAI Initial SOW.md; raw/SOW 1 Milestone 2 Presentation.pptx; raw/Bedrock SOW 2.md; raw/meeting_transcripts/Iris Sync - 2026_08_10 12_27 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_08_12 12_27 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_08_14 12_30 EDT - Notes by Gemini.md
