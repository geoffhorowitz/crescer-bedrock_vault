# Synthetic Data Requirements

**Summary**: SOW scope, client approvals, and forward-modeling requirements for synthetic Sidescan Sonar (SSS) and magnetometer data. Detailed implementation progress is documented in [[sss-augmentation-methods]].

**Last updated**: 2026-07-21

---

## SOW Requirements

The milestone deck says Crescer may augment Bedrock SSS data with existing and synthetic data as needed (source: SOW 1 Milestone 2 Presentation.pptx).

SOW 2 requires synthetic data integration for Milestone 2, with Bedrock approval of the augmentation approach before use; email approval is sufficient (source: Bedrock SOW 2.md).

SOW 2 requires the metrics report to summarize classes and conditions represented in generated data, show synthetic samples alongside real equivalents, and state the criteria used to judge synthetic examples realistic enough for training (source: Bedrock SOW 2.md).

## Magnetometer Data

SOW 2 requires a synthetic magnetometer data pipeline developed and validated against a physics-based forward model specification defined jointly with Bedrock (source: Bedrock SOW 2.md).

The synthetic mag pipeline is expected to be refined in Milestone 4 based on Milestone 3 evaluation lessons (source: Bedrock SOW 2.md).

The July 1, 2026 magnetometer discussion with Francisco Bolivar indicated that forward modeling for mag data is the next step after anomaly characterization, where synthetic target responses are fitted against measured responses to infer target size and burial depth (source: Bedrock__Crescer_ Mag Discussion - 2026_07_01).

## Ownership

Intellectual property rights for synthetic data are split: Crescer AI retains SSS generation methodology, while Bedrock owns the resulting SSS training dataset and all developed magnetometer forward modeling pipelines. Refer to [[data-rights-and-ip]] for the authoritative SOW clauses (source: Bedrock SOW 2.md).

## Related pages

- [[automated-target-recognition]]
- [[model-performance-and-metrics]]
- [[magnetometer-fusion]]
- [[data-rights-and-ip]]
- [[sss-augmentation-methods]]

---

**Sources**: raw/SOW 1 Milestone 2 Presentation.pptx; raw/Bedrock SOW 2.md; raw/meeting_transcripts/Bedrock__Crescer_ Mag Discussion - 2026_07_01
