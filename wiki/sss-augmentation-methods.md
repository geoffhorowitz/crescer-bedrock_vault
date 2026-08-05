# SSS Augmentation Methods

**Summary**: Practical engineering implementation of sidescan sonar (SSS) data augmentation strategies, including cut-paste, Poisson blending, diffusion models, LLM validation loops, and handling of rare classes.

**Last updated**: 2026-07-29

---

## Cut-Paste Augmentation With Blending

Cut-paste augmentation emerged as the most effective augmentation technique (source: Iris Sync - 2026_07_15). The strategy copies objects from annotated images onto unannotated background images to generate positive training examples for underrepresented classes.

Three blending methods were evaluated:
- **Blend direct**: Simple copy-paste; produces visible seams that the model can easily detect as artifacts (source: Iris Sync - 2026_07_15)
- **Blend alpha**: Smoother transition but still visibly obvious (source: Iris Sync - 2026_07_15)
- **Poisson blending**: Uses the gradient of the source object to blend it naturally into the background; produces the most realistic results where the object appears to genuinely belong in the scene (source: Iris Sync - 2026_07_15)

Poisson blending performed best across all datasets, including complex backgrounds (source: Iris Sync - 2026_07_15).

## Enhancement Plans

The blending code was planned to be enhanced with rotation, size variation, and shape augmentation to increase diversity of synthetic objects (source: Iris Sync - 2026_07_15).

## Diffusion Model Strategy

A tiered synthetic data generation approach was adopted (source: Iris Sync - 2026_07_06):

1. **Simplest tier**: Copy existing contacts onto existing backgrounds (cut-paste augmentation)
2. **Intermediate tier**: Generate new contacts for existing backgrounds using diffusion
3. **Advanced tier**: Train a model to generate both backgrounds and contacts from scratch

The team prioritized starting with the simpler tiers while running the diffusion model in parallel as a contingency (source: Iris Sync - 2026_07_06).

## Diffusion Model Development

- Data is prepared as 256x256 patches from stacked port and starboard images (source: Iris Sync - 2026_07_08)
- Dual training approach: both training from scratch and fine-tuning with LoRA (Low-Rank Adaptation) using Comfy UI (source: Iris Sync - 2026_07_08)
- The model is conditioned on both the mask and the dataset to generate specific target classes (source: Iris Sync - 2026_07_08)
- Initial inpainting approach using 800,000 patches failed due to data scarcity; moved to a two-stage approach generating background first, then masking out regions for object insertion (source: Iris Sync - 2026_07_15)

## Latent Noise Denoising

Hemanth Sarabu described a technique where a cut-pasted image is converted to a latent space, noise is added, and then a diffusion denoiser reconstructs it. The denoiser makes the result look more in-distribution, smoothing visible blending artifacts (source: Iris Sync - 2026_07_15).

## Rare Class Challenges

### Mine Detection

The team identified one to two distinct mine examples in the entire dataset (source: Iris Sync - 2026_07_15 and source: Iris Sync - 2026_07_17). The team reached out to Bedrock to request additional mine data, and explored classical techniques to generate synthetic line-like artifacts for mines (source: Iris Sync - 2026_07_15).

### AOI Support Objects

Small dark circular objects (AOI support) are difficult to capture due to limited examples (source: Iris Sync - 2026_07_15). The team plans to generate these synthetically using simple geometric shapes colored to match the expected appearance.

## Additional Augmentations

- **Random line dropping**: Simulating different sonar speeds and altitudes by randomly dropping lines from the waterfall image (source: Iris Sync - 2026_07_15)
- **Width variation**: Port/starboard scan width varies significantly across datasets (600-650 pixels down to 130 pixels), requiring augmentation to make the model robust to different widths (source: Iris Sync - 2026_07_15)
- **Dataset transformation**: Exploring whether VW data could be transformed to resemble DRN or POE appearance, enabling the use of well-labeled VW data as a robust evaluation set (source: Iris Sync - 2026_07_15)

## Augmentation Progress As Of July 17

### Completed Work

- **Copy-paste augmentation**: Done (source: Iris Sync - 2026_07_17)
- **Synthetic mine generation**: Done — cylindrical objects with shadow, sine-wave intensity pattern added in image space (not XTF level). Results look convincing to the team (source: Iris Sync - 2026_07_17)
- **Roll-like artificial data**: Done (source: Iris Sync - 2026_07_17)

### Unresolved

- **Cross-dataset style transformation**: Pratyaksh attempted to transform one dataset's appearance to match another (e.g., VW → DRN appearance). No success yet (source: Iris Sync - 2026_07_17)
- **XTF-level augmentation**: Current augmentations are in image space (PNG layer). XTF-level manipulation (e.g., correcting roll via raw XTF metadata) remains a future goal. Hemanth suggests exploring Empirical Mode Decomposition (EMD) — 2D variants of the technique used for time-series — to isolate wave-like components from images (source: Iris Sync - 2026_07_17).

### Rare-Class Target Scarcity

UXO-style objects: there are only 10-11 unique UXO objects across the entire dataset. Bridget (Bedrock) confirmed that no more UXO data is likely available to share (source: Iris Sync - 2026_07_17).

Mine objects: Pratyaksh found only one to two distinct mine examples in annotated data. Most UXO objects are concentrated in the ENTX and DRN datasets and typically appear as small black spots rather than elongated shapes (source: Iris Sync - 2026_07_17).

### UK Royal Navy Demo Context

Geoff warns that future datasets for the UK Royal Navy demonstration will notably differ from the VW dataset, as VW has a disproportionate number of easily recognizable objects. The team should not over-index on VW-style objects when designing synthetic or augmentation strategies (source: Iris Sync - 2026_07_17).

## Virtual Sensor Parameter Experiments

Ratul Shashank tested how changing virtual sensor parameters in XTF metadata affects the rendered images:

- **Altitude**: Produces the most visually significant changes to sonar images (source: Iris Sync - 2026_07_17)
- **Speed**: Produces visible changes (source: Iris Sync - 2026_07_17)
- **Roll**: Does not visibly affect mosaic images because the XTF-to-image conversion does not use roll data. Roll affects waterfall views but not the final stitched mosaics used for training (source: Iris Sync - 2026_07_17)

XTF sensor speed metadata shows zero for all ENTX and VW files, while DRN and POE files consistently show ~2 m/s. The reason for the zero values is unknown (source: Iris Sync - 2026_07_17).

## Open-Source Data Strategy

Pratyaksh proposed a new approach for leveraging open-source sonar data, modeled after large language model pre-training pipelines (source: Iris Sync - 2026_07_17):

1. **Pre-training phase**: Collect a broad corpus of open-source sonar imagery and train without annotations to learn background distributions
2. **Fine-tuning phase**: Fine-tune on the smaller, high-quality Bedrock dataset with annotations

Open-source data should be categorized by quality relative to Bedrock data:
- **High quality**: Very similar to Bedrock data distribution
- **Medium quality**: Convertible to Bedrock-like distribution (e.g., downsampling high-resolution open-source imagery)
- **Low quality**: Completely different from Bedrock data

Generative AI (e.g., Flux models) should be conditioned on Bedrock data for novel image generation. QC by labelers with a simple yes/no check. Key guidance: do not condition generative models on existing images lightly — noise heavily or generate from scratch to produce truly novel samples rather than near-duplicates (source: Iris Sync - 2026_07_17).

## Generative AI Guidance

Pratyaksh's specific guidance for Ratul's generative AI work:
- Generate novel images, not near-duplicates of existing training data (the dataset already has duplication across 6-7 XTF files per location)
- Split each image into port and starboard sides before feeding to the model, since 30-40% of the full image is just water column gaps that waste model capacity
- Use the Bedrock data distribution only for generative AI, not open-source data, to avoid setting client expectations about open-source generalization (source: Iris Sync - 2026_07_17)

## AOI Small (Black Patch) Augmentation Details

Pratyaksh presented examples of the "AOI small black" class, noting the objects are not completely black but have gradient and shape patterns that are difficult to replicate procedurally. Object pasting (copy-paste) works well for these objects. A procedural generation approach was attempted with an 80th-percentile intensity threshold to create gradients within a blob, but still fell short of matching real examples (source: Iris Sync - 2026_07_20).

## Baseline Testing Plan

Pratyaksh to train a no-advanced-augmentation baseline model first, then train variants with individual augmentations and combinations to measure delta improvement. Specific augmentation methods were not defined, though examples may include: diffusion-generated backgrounds, copy-paste objects, procedural mine generation, classical image-space transforms. Sachin and Pratyaksh to review classical augmentation outputs together to determine effective methods for model improvement. Results reported ahead of the client meeting (source: Iris Sync - 2026_07_20).

## Open-Source Pre-Training Clarification

Open-source data plan confirmed: search through open-source datasets, classify examples by similarity to Bedrock data, use for pre-training, then fine-tune on Bedrock data. Not viable to have labelers fully annotate open-source examples due to volume and out-of-distribution appearance (source: Iris Sync - 2026_07_20).

## Augmentation Combination Benchmarking

Pratyaksh Singh evaluated combinations of transformations (perspective, Poisson blending, roll, cutmix, softmix) on ResNet-50. The combination of Poisson blending, sonar roll, and cutmix achieved the top object-level F1 score of 0.49 @ 20% IOU. Perspective transform combined with Poisson and roll also placed among top performers (source: Iris Sync - 2026_07_22).

## Pit and Depression Feature Augmentation

Because Bedrock UXO objects present as seabed pits/depressions rather than cylindrical open-source mines, Pratyaksh Singh initiated specific augmentations targeting pit and depression morphological patterns in side-scan sonar imagery (source: Iris Sync - 2026_07_22).

## Variable Isolation Strategy

To determine exact performance gains from synthetic data versus image-space transformations, future training runs will isolate single variables—testing image transformations (brightness, gamma) independently from cut-and-paste data augmentations (source: Meeting started 2026_07_23).

## Flux Turbo + LoRA Synthetic Pipeline

Ratul Shashank implemented a Generative AI pipeline utilizing Flux Turbo with LoRA models to generate synthetic UXO targets categorized by elongation (elongated, round, moderate). Flux Turbo produced realistic object variations without structural artifacts. Task division established: Generative AI creates novel object structures, while classical computer vision handles image brightness, contrast, and geometric transformations (source: Iris Sync - 2026_07_24).

## Real-to-Sim Physics Simulation Proposal

Hemanth Sarabu proposed a "Real-to-Sim" physics simulation pipeline that uses raw XTF metadata (vehicle trajectories, sensor depth, altitude, MAG readings) to simulate side-scan sonar intensity returns. Suggested leveraging agentic simulation workflows (e.g. Claude / Antigravity) to derive physics models from scene descriptions (source: Iris Sync - 2026_07_24).

## False Positive Rotation & Scaling Augmentations

The team approved adding rotated, morphed, and scaled object annotations directly into training batches as explicitly designated false-positive samples. This image-space augmentation strategy expands background diversity and helps suppress spurious detections on complex seafloor textures (source: Iris Sync - 2026_07_27).

## LLM Validation Agent Similarity Loop

Sachin Pandey established an interactive LLM-based Validation Agent loop for synthetic generation evaluation. The validation agent uses similarity metrics (with an initial similarity threshold of 80%) to compare generated sonar samples against reference targets, iteratively filtering and refining synthetic outputs to ensure alignment with real-world distributions (source: Iris Sync - 2026_07_27).

The team refined this approach on July 28, clarifying that the prior strategy of modifying existing Bedrock data produced outputs indistinguishable from standard augmentations. The new direction uses open-source data (~300k images) as a base and converts it to the target distribution, with an LLM judge scoring distribution fidelity and providing feedback to a coding agent to refine generation (source: Bedrock Discussion Continued (understanding eval agent) - 2026_07_28).

## Procedural Generation Framework (July 28)

Hemanth Sarabu proposed two complementary approaches to procedural synthetic generation:

- **Hill-climbing**: Frame generation as a hill-climbing optimization task where the LLM judge scores iterative improvements, incentivizing the generation agent to maximize a distribution-matching score (target threshold: 0.9) (source: Bedrock Discussion Continued (understanding eval agent) - 2026_07_28)
- **Reconstruction loop**: Force the system to learn reconstruction of reference images via procedural generation, analogous to how VAEs or diffusion models operate, then perturb the learned process to create novel training data (source: Bedrock Discussion Continued (understanding eval agent) - 2026_07_28)

The LLM judge alone may be insufficient due to vision-language model limitations. The team proposed augmenting evaluation with perceptual loss (potentially using AlexNet features) and object detection heuristics (source: Bedrock Discussion Continued (understanding eval agent) - 2026_07_28).

High-resolution images consume too many tokens for full-image processing in the LLM context window. Heuristics or on-device computed metrics are needed instead of passing complete images for evaluation (source: Bedrock Discussion Continued (understanding eval agent) - 2026_07_28).

## Dimensionality Reduction: EMD Transition (July 28)

Pratyaksh reported that SVD can reconstruct images from the top 10 singular values, but PCA struggles with non-linear components (oscillations in PC4 are not linearly separable). Hemanth proposed testing Empirical Mode Decomposition (EMD) to isolate non-linear components that PCA and SVD struggle with.

Pratyaksh agreed to test both EMD (Empirical Mode Decomposition) and frequency domain transforms for component isolation (source: Bedrock Discussion Continued (understanding eval agent) - 2026_07_28).

## VAE Pre-Training Exploration (July 28)

Hemanth proposed training a Variational Autoencoder to extract components from an embedding space or codebook. Pratyaksh plans to explore pre-training a VAE or diffusion tool on open-source data and report on feasibility (source: Bedrock Discussion Continued (understanding eval agent) - 2026_07_28).

## 25 Pixel-Based Color Augmentations (July 28)

The team accepted 25 pixel-based color augmentations as a fallback strategy if synthetic generation proves insufficient. Sachin to share the HTML repository containing augmentation data on Slack (source: Bedrock Discussion Continued (understanding eval agent) - 2026_07_28).

## Diffusion Model Data Synthesis Anti-Leakage Workflow (July 29)

To prevent data leakage when generating synthetic training patches using trained diffusion models:
- **Clean Background Split**: The diffusion model will be trained exclusively on a clean 75% dataset split containing background sonar textures only (excluding images with real object annotations) (source: Iris Sync - 2026_07_29).
- **Synthetic Object Overlay**: Backgrounds generated by the diffusion model are populated with external or procedurally generated objects (via vision models or procedural code) (source: Iris Sync - 2026_07_29).
- **Held-Out Evaluation**: Downstream ATR classifiers are evaluated against the held-out 25% dataset containing real objects that neither the diffusion model nor classifier ever saw during training (source: Iris Sync - 2026_07_29).

## Latent Space Inpainting D-Noising Workflow (July 29)

Hemanth Sarabu proposed a latent-space blending technique to naturally integrate pasted objects into generated sonar backgrounds:
1. Generate a synthetic background patch with the diffusion model.
2. Copy-paste a target object onto the background.
3. Encode the composite patch into latent space using the model's autoencoder.
4. Add a low level of noise to the full latent representation.
5. Run 1–2 d-noising diffusion steps using the trained diffusion model to force the pasted object into the target data distribution without destroying background structure (source: Iris Sync - 2026_07_29).

## Image-Domain Augmentations vs. XTF Operations (July 29)

The team decided to standardize on runtime image-domain augmentations rather than manipulating raw XTF sensor amplitudes:
- **Limitations of XTF Manipulation**: Experiments with XTF raw amplitude modification (median background subtraction, height scaling x1.3) encountered severe gradient mismatch and scale discrepancies when transferring objects between datasets (e.g. VW to ANTX) (source: Iris Sync - 2026_07_29).
- **Image-Domain Pipeline**: Adopted OpenCV Poisson copy-paste, rotation matrices (sin/cos affine coordinate tracking for bounding boxes), scaling, and directional shadow additions (source: Iris Sync - 2026_07_29).
- **Runtime Flexibility**: Image-domain operations enable real-time augmentation during training batches without creating static pre-rendered image files (source: Iris Sync - 2026_07_29).

## Pixel Blending Rule (July 29)

When blending or merging overlapping image patches or dark target regions, the team established a strict rule to compute the mean pixel value rather than summing pixel intensities (e.g., $125 + 125 = 250$ vs $255 + 255 \rightarrow \text{overflow/clip at } 255$). Averaging preserves gradient nuance and prevents pixel value overflow (source: Iris Sync - 2026_07_29).

## Pixel Crop Pivot over Raw XTF Manipulation (July 31)

The team formally adopted pixel cropping as the standard methodology for object manipulation, replacing raw XTF sensor amplitude operations.
- **Rationale**: High physics accuracy for shadows is not strictly required to achieve the team's object detection goals, and pixel crop operations avoid the gradient and scale mismatch issues inherent in raw XTF manipulation (source: Iris Sync - 2026_07_31).

## LoRA Model Object Generation (July 31)

Pivoted target simulation strategy to fine-tuning a LoRA (Low-Rank Adaptation) model on 144 real target crop examples to generate novel synthetic target objects (source: Iris Sync - 2026_07_31).

## Flow Matching Background Generation & Guidance Benchmarking (August 3)

Pratyaksh completed training a background generation model using flow matching loss, enabling continuous ODE-based time-step sampling (source: Iris Sync - 2026_08_03).
- **Classifier Guidance Weights**: Tested weights 1, 2, and 5. Unweighted/weight 1 produced realistic in-distribution backgrounds. Weight 2 began darkening textures, while weight 5 destroyed image structure across all datasets (source: Iris Sync - 2026_08_03).
- **Diffusion Steps**: 10 diffusion evaluation steps were sufficient for well-represented datasets, but 25 steps significantly improved background quality on small datasets like ENTX (source: Iris Sync - 2026_08_03).

## ResNet-50 Embedding DBSCAN Noise Filtering & 100k Sampling (August 3)

To handle low-quality/noise artifacts generated by diffusion and flow matching models:
- **ResNet-50 Embedding DBSCAN**: Extracted embeddings from a pre-trained ResNet-50 and applied density-based spatial clustering (DBSCAN) to automatically detect and isolate distorted synthetic images (source: Iris Sync - 2026_08_03).
- **100k Synthetic Sampling Strategy**: Planned pipeline to generate 100,000 synthetic examples, cluster them in embedding space, and sample representatively across clusters to ensure maximum feature diversity (source: Iris Sync - 2026_08_03).

## Real Backgrounds + Closed-Source Synthetic Foregrounds Strategy (August 3)

The team established a hybrid synthetic training recipe (source: Iris Sync - 2026_08_03):
- **Validation Reservation**: All real Area-of-Interest (AOI) target data is reserved exclusively for validation sets.
- **Training Recipe**: Models are trained on real backgrounds plus synthetic foreground objects generated via closed-source prompt engineering (Ratul) and procedural object agents (Sachin), combined with verified cut-and-paste augmentations for Milestone 2 closure.

## GPT Prompted Object Generation & GAN Shelving (August 5)

Target generation methods were refined based on empirical testing (source: Iris Sync - 2026_08_05):
- **GPT / Nano Banana Image-to-Image Prompts**: Ratul created master prompts using GPT and image-to-image models to generate grids of novel UXO target crops, retaining morphological blob-like structures while generating novel object variations.
- **Discontinuation of GANs & LoRA Failure**: GAN-based synthetic generation was formally shelved due to excessive data volume requirements and model instability. LoRA fine-tuning was also confirmed unsuccessful for novel target generation.

## Image Decomposition Techniques for Composite Placement (August 5)

Hemanth introduced image decomposition tools using EMD-like algorithms (source: Iris Sync - 2026_08_05):
- **Structure and Speckle Layering**: Sonar images are decomposed into structural, speckle, and base components. When pasting target crops, components are recombined with normalization so the target absorbs local background speckle and texture properties.

## Generative Texture Prototypes & FFT Inefficacy (August 5)

Explored additional generative methods for sonar texture simulation (source: Iris Sync - 2026_08_05):
- **VGG Sand Ripples**: Generative method using VGG statistics to synthesize realistic sand ripple patterns from noise.
- **Style Transfer Remixing**: Blends content and style images to remix sonar background textures.
- **FFT Inefficacy**: Confirmed Fast Fourier Transform (FFT) analysis is ineffective for sonar wave texture manipulation.

## Related pages

- [[automated-target-recognition]]
- [[model-performance-and-metrics]]
- [[data-sets-and-curation]]
- [[magnetometer-fusion]]
- [[synthetic-data-requirements]]
- [[iris-sync-2026-07-29]]
- [[iris-sync-2026-07-31]]
- [[iris-sync-2026-08-03]]
- [[iris-sync-2026-08-05]]

---

**Sources**: raw/meeting_transcripts/Iris Sync - 2026_06_12 through 2026_08_05; raw/meeting_transcripts/Bedrock Discussion Continued (understanding eval agent) - 2026_07_28 11_59 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_08_03 12_28 EDT - Notes by Gemini.md; raw/meeting_transcripts/Iris Sync - 2026_08_05 12_24 EDT - Notes by Gemini.md
