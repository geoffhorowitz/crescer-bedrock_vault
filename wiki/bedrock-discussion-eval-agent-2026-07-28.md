# Bedrock Discussion: Understanding Eval Agent

**Summary**: July 28, 2026 meeting discussing synthetic data generation strategy shift toward open-source data pre-training, LLM-as-judge evaluation, procedural generation frameworks, and EMD decomposition.

**Last updated**: 2026-07-28

---

## Attendance

Sachin Pandey, Hemanth Sarabu, Geoff Horowitz, Pratyaksh Singh.

---

## Strategy Shift: Open-Source Data As Base

The team shifted away from modifying existing Bedrock data toward using open-source data (~300k images) as a base for synthetic generation. The prior approach of modifying the same Bedrock data produced outputs indistinguishable from standard augmentations. The goal is to use models to convert open-source data into the target distribution to improve validation accuracy.

Pratyaksh identified an open-source dataset with approximately 300k images. The team agreed to review the associated research paper to assess its utility.

## LLM-As-Judge Evaluation Framework

Adopted a strategy where an LLM serves as an evaluation judge to score how well procedurally generated images match the target data distribution and provide feedback to the coding agent about necessary changes. Target score threshold initially set at 0.9 for in-distribution acceptance.

The vision-language model may need assistance evaluating images due to inherent limitations. The team proposed integrating heuristics such as perceptual loss (potentially using AlexNet features) and object detection metrics to augment the LLM judge.

## Procedural Generation Framework

Hemanth proposed two complementary approaches:

- **Hill-climbing**: Frame the generation problem as a hill-climbing task where the LLM is incentivized to optimize a score through iterative improvements
- **Reconstruction loop**: Force a system to learn reconstruction of reference images using procedural generation (analogous to VAEs or diffusion models), then perturb the learned process to create novel training data

Pratyaksh elaborated that high-resolution open-source data serves as the base, converted to the target sonar format. The LLM judge scores distribution fidelity and provides feedback to refine the process.

## Token Limitation Challenge

Running generation loops on the entire dataset is infeasible due to token limitations. High-resolution images consume significant tokens. The team needs heuristics or metrics computed on-device rather than passing full images into the model's context window.

## Dimensionality Reduction: SVD to EMD

Pratyaksh reported that SVD's top 10 singular values can reconstruct images effectively. Hemanth suggested testing Empirical Mode Decomposition (EMD) to isolate non-linear components that PCA and SVD struggle with (oscillations in PC4 are not linearly separable). Pratyaksh agreed to test both EMD and frequency domain transforms.

## VAE Pre-Training Exploration

Hemanth proposed training a Variational Autoencoder to extract components from an embedding space or codebook. Pratyaksh plans to explore pre-training a VAE or diffusion tool on available open-source data and report feasibility the next day.

## 25 Pixel-Based Color Augmentations

Accepted as a backup strategy if synthetic augmentation proves insufficient. Sachin to share the HTML repository containing image augmentation data on Slack.

## Data Convention Policy

The team established a policy to avoid making assumptions about data conventions (rotation, axis orientation) when processing new datasets, instead investigating the base structure first.

## Skills Repository

The team reached consensus to create a centralized repository for documenting and sharing team skills and technical resources.

## Objective Framing

Hemanth emphasized that the main objective is to use this project as an opportunity to learn how to generate synthetic data, regardless of how the Bedrock model improves.

## Next Steps

- [ ] Create a skills repository for shared technical resources
- [ ] Pratyaksh: share research paper for the 300k open-source image dataset
- [ ] Test procedural generation using LLM judge on open-source images
- [ ] Sachin: create Slack channel for data variation discussions
- [ ] Pratyaksh: experiment with EMD and frequency domain decomposition
- [ ] Pratyaksh: set up VAE and report feasibility
- [ ] Sachin: share image augmentation HTML repository on Slack

## Related pages

- [[sss-augmentation-methods]]
- [[synthetic-data-requirements]]
- [[data-sets-and-curation]]
- [[model-training-and-iterations]]

---

**Sources**: raw/meeting_transcripts/Bedrock Discussion Continued (understanding eval agent) - 2026_07_28 11_59 EDT - Notes by Gemini.md
