# Bedrock Sow 2

**Summary**: SOW 2 expands the Bedrock ATR work into updated SSS modeling, synthetic data, onboard PNG input validation, UXO-style targets, and magnetometer fusion.

**Last updated**: 2026-07-15

---

## Objective

SOW 2 builds on the SOW 1 proof of concept by developing an updated and expanded ATR model for Bedrock sidescan sonar and magnetometer data, improving generalizability across survey conditions, and supporting integration onto Bedrock's AUV platform (source: Bedrock SOW 2.md).

The expected engagement duration is about 4.5 to 5 months from the effective date, with an internal target to complete Milestones 1 and 2 by July 1, 2026 for a planned client demonstration (source: Bedrock SOW 2.md).

## Milestones

Milestone 1 covers onboard deployment support, PNG input specification, validation of Bedrock-generated PNGs against an XTF-derived baseline, and documentation of preprocessing requirements (source: Bedrock SOW 2.md).

Milestone 2 covers a retrained [[lumen-model|Lumen]] model with UXO-style objects, seabed robustness improvements, AUV roll support, synthetic data integration, a metrics report, and a demo-ready containerized build for a UKRN client demonstration (source: Bedrock SOW 2.md).

Milestone 3 covers a magnetometer fusion MVP using SSS and mag data as joint model inputs, co-registered datasets, synthetic mag data, TX2 benchmarking, ferrous versus non-ferrous evaluation, and a feasibility report (source: Bedrock SOW 2.md).

Milestone 4 hardens the mag model, refines synthetic mag data, performs onboard TX2 validation with the mag channel active, and recommends future architecture and training strategy (source: Bedrock SOW 2.md).

Milestone 5 hardens the final model, validates onboard TX2 performance, provides a full metrics report, and recommends future retraining strategy as new data becomes available (source: Bedrock SOW 2.md).

## Responsibilities

Bedrock is responsible for SSS and mag datasets, a jointly developed train/validation/test split strategy, domain expertise on magnetometer interpretation and synthetic methodology, approval of synthetic augmentation before training use, and TX2 access for testing (source: Bedrock SOW 2.md).

Crescer AI is responsible for data preparation, synthetic data pipeline development and validation, model training and tuning, containerized deliverables, metrics reports, specified support, and training compute costs (source: Bedrock SOW 2.md).

## Decision Points

Open decision points include SSS-mag co-registration, synthetic mag forward model specification, Milestone 2 acceptance criteria, mag channel input specification, preprocessing requirements, and onboard deployment support SLA (source: Bedrock SOW 2.md).

## Related pages

- [[automated-target-recognition]]
- [[onboard-deployment]]
- [[model-performance-and-metrics]]
- [[synthetic-data-requirements]]
- [[magnetometer-fusion]]
- [[data-rights-and-ip]]
- [[lumen-model]]

---

**Sources**: raw/Bedrock SOW 2.md
