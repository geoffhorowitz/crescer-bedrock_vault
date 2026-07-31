# Onboard Deployment

**Summary**: Onboard deployment covers packaging, runtime, input format, and AUV integration support for running Bedrock ATR models on embedded hardware.

**Last updated**: 2026-07-15

---

## Hardware And Runtime

The initial SOW requires a Docker image with a sample model capable of running on Jetson TX2 using TensorRT 8, a minimal runtime environment, and command-line inference (source: Internal Bedrock x CrescerAI Initial SOW.md).

The milestone deck reports Jetson Nano benchmark results and states that TX2 performance is expected to be better (source: SOW 1 Milestone 2 Presentation.pptx).

## Integration Support

SOW 2 makes Bedrock's team primarily responsible for onboard integration while Crescer AI provides responsive support and interface validation (source: Bedrock SOW 2.md).

SOW 2 Milestone 1 is complete when Bedrock's integration lead confirms the model runs stably onboard the AUV on Bedrock-generated PNG inputs (source: Bedrock SOW 2.md).

## Input Format

SOW 2 requires Bedrock and Crescer AI to define a PNG input specification for real-time onboard inference, including dimensions, layout, intensity normalization, scaling, and slant-range or geometric corrections expected upstream (source: Bedrock SOW 2.md).

Bedrock retains ownership of the real-time preprocessing pipeline, and Crescer AI retains no rights to it (source: Bedrock SOW 2.md).

## Related pages

- [[automated-target-recognition]]
- [[model-performance-and-metrics]]
- [[data-rights-and-ip]]
- [[internal-bedrock-x-crescerai-initial-sow]]
- [[sow-1-milestone-2-presentation]]
- [[bedrock-sow-2]]
- [[mollusk-platform]]

---

**Sources**: raw/Internal Bedrock x CrescerAI Initial SOW.md; raw/SOW 1 Milestone 2 Presentation.pptx; raw/Bedrock SOW 2.md
