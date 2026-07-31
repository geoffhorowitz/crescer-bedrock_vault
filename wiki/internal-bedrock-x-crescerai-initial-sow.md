# Internal Bedrock x Crescerai Initial Sow

**Summary**: The initial SOW defines a proof of concept for a Bedrock sidescan sonar ATR model packaged for Jetson TX2, with a Streamlit prototype and model metrics report.

**Last updated**: 2026-07-15

---

## Purpose

The POC objective is to validate that Crescer AI can train and deliver an [[automated-target-recognition]] model for Bedrock [[onboard-deployment]] on Jetson TX2 using Bedrock sidescan sonar data (source: Internal Bedrock x CrescerAI Initial SOW.md).

If the POC is accepted, the parties expect to draft a follow-on SOW for a production model and onboard pipeline integration (source: Internal Bedrock x CrescerAI Initial SOW.md).

## Deliverables

The SOW requires a sample Docker inference container with a sample model, TensorRT 8 support, a minimal runtime environment, command-line inference entry point, and run instructions (source: Internal Bedrock x CrescerAI Initial SOW.md).

The model and metrics deliverable includes an initial trained ATR model, held-out validation metrics, false-negative rate on seeded targets, per-chunk inference time, CPU/GPU/memory utilization, and suggested improvements (source: Internal Bedrock x CrescerAI Initial SOW.md).

The prototype web app is a Streamlit app hosted by Crescer that lets users upload or point to a sample SSS chunk, run the model, view detections with confidence scores, and download CSV detections and quick-look image chips (source: Internal Bedrock x CrescerAI Initial SOW.md).

## Responsibilities

Bedrock is responsible for representative labeled SSS data and regular feedback on infrastructure and model needs (source: Internal Bedrock x CrescerAI Initial SOW.md).

Crescer AI is responsible for data preparation, model training and tuning, the Streamlit prototype, and the metrics report (source: Internal Bedrock x CrescerAI Initial SOW.md).

## Open Decisions

The SOW leaves several decisions open, including training data format, preprocessing requirements, input features, data exchange, acceptance thresholds, model I/O, runtime details, performance targets, future retraining ownership, long-term support, termination rights, and check-in cadence (source: Internal Bedrock x CrescerAI Initial SOW.md).

## Related pages

- [[automated-target-recognition]]
- [[onboard-deployment]]
- [[model-performance-and-metrics]]
- [[data-rights-and-ip]]

---

**Sources**: raw/Internal Bedrock x CrescerAI Initial SOW.md
