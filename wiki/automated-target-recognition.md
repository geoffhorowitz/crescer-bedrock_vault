# Automated Target Recognition

**Summary**: Bedrock and Crescer AI's ATR work focuses on detecting discrete targets in sidescan sonar, then extending toward onboard AUV operation and magnetometer-aware detection. Dataset details are documented in [[data-sets-and-curation]] and training progress in [[model-training-and-iterations]].

**Last updated**: 2026-08-10

---

## Role In The Project

The initial POC validates whether Crescer AI can train and deliver an ATR model for Bedrock SSS data and package it for Jetson TX2 (source: Internal Bedrock x CrescerAI Initial SOW.md).

The milestone deck defines the operational goal as auto-detecting discrete objects per SSS waterfall swath onboard, with reprocessing after navigation post-processing and optional batch processing in [[mollusk-platform|Mollusk]] (source: SOW 1 Milestone 2 Presentation.pptx).

SOW 2 expands the model to new contact types such as UXO-style objects and seabed robustness improvements for dredging scars and complex background texture (source: Bedrock SOW 2.md).

As of July 28, the team shifted strategy: instead of modifying existing Bedrock data for synthetic augmentation, the new approach uses open-source data as a base and converts it to the target distribution via procedural generation with an LLM-as-judge evaluation loop. This better addresses the rare-class and data diversity challenges. See [[sss-augmentation-methods]] and [[bedrock-discussion-eval-agent-2026-07-28]] for details.

## Datasets In Use

The team works with five primary datasets: VW (Vineyard Winds) as the baseline, ANTX (commonly mislabeled as ENTX in transcripts) with labeled features, DRN (Danish Royal Navy) with small non-ferromagnetic targets, POE (Port of Espoo), and a port background dataset. Additional evaluation datasets include open-source sonar corpora (~300k images), Southern California mission data, and the Treasure Island dataset. See [[data-sets-and-curation]] for details (source: multiple Iris Sync transcripts, source: Bedrock Discussion Continued (understanding eval agent) - 2026_07_28).

## Outputs

The deck lists v1 outputs as latitude, longitude, and class, with confidence, size, and orientation expected later (source: SOW 1 Milestone 2 Presentation.pptx).

The initial SOW lists model output format as an unresolved decision point, including possible CSV schema, OBR overlay fields, provisional latitude/longitude, ping/time, and range (source: Internal Bedrock x CrescerAI Initial SOW.md).

## Related pages

- [[onboard-deployment]]
- [[model-performance-and-metrics]]
- [[synthetic-data-requirements]]
- [[sss-augmentation-methods]]
- [[magnetometer-fusion]]
- [[data-sets-and-curation]]
- [[model-training-and-iterations]]
- [[internal-bedrock-x-crescerai-initial-sow]]
- [[sow-1-milestone-2-presentation]]
- [[bedrock-sow-2]]
- [[magnetometer-processing-pipeline]]
- [[mollusk-platform]]

---

**Sources**: raw/Internal Bedrock x CrescerAI Initial SOW.md; raw/SOW 1 Milestone 2 Presentation.pptx; raw/Bedrock SOW 2.md; raw/meeting_transcripts/Iris Sync - 2026_07_03 through 2026_08_10; raw/meeting_transcripts/Bedrock Discussion Continued (understanding eval agent) - 2026_07_28 11_59 EDT - Notes by Gemini.md
