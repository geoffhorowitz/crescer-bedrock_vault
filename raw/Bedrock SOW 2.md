# STATEMENT OF WORK (SOW) \#2

**1\. Services**

**A. Objective**

Building on the successful proof-of-concept delivered under SOW \#1, Crescer AI will develop an updated and expanded ATR model for Bedrock sidescan sonar (SSS) and magnetometer (mag) data, improve generalizability across survey conditions, and support Bedrock's integration of the existing model onto its AUV platform. The work is organized into five milestones which may be completed ahead of schedule at Crescer AI's discretion.

**B. Anticipated Timeline**

The engagement is expected to span approximately 4.5-5 months from the Effective Date, with an internal target of completing Milestones 1 and 2 by July 1, 2026 to support a planned client demonstration. Milestones 3, 4, and 5 are not calendar-gated and will be invoiced upon completion.

**C. Deliverables**

*Milestone 1: Onboard Deployment Support and Input Interface Specification*

* Crescer AI will provide technical support to Bedrock's robotics integration lead as needed to resolve questions arising during onboard deployment of the SOW \#1 model and/or SOW \#2 Milestone 2 model, via Slack, Zoom, or agreed async channel  
* Bedrock and Crescer AI will jointly define and document the PNG input specification for real-time onboard inference, including: image dimensions, layout, intensity normalization and scaling approach, and any slant-range or geometric corrections expected to be applied upstream by Bedrock's preprocessing pipeline  
* Crescer AI will validate model performance on Bedrock-generated PNGs against the XTF-derived baseline to confirm no performance regression attributable to the input format change  
* Any preprocessing requirements that must be met by Bedrock's pipeline for model performance guarantees to hold will be documented explicitly as a deliverable of this milestone  
* Bedrock retains full ownership of the real-time preprocessing pipeline; Crescer AI retains no rights to it  
* Milestone is considered complete when Bedrock's integration lead confirms the model is running stably onboard the AUV on Bedrock-generated PNG inputs  
* Bedrock acknowledges that primary integration responsibility lies with Bedrock's team; Crescer AI's obligation is responsive support and interface validation

*Milestone 2: Core Model Update \+ Synthetic Data Integration \+ Demo-Ready Build*

* Retrained Lumen model incorporating:  
  * New contact types (UXO-style objects)  
  * Seabed robustness improvements (dredging scars, complex background texture)  
  * AUV roll support via new model input channel  
* Synthetic data pipeline integrated and validated, with Bedrock approval on augmentation approach prior to use (email sufficient)  
* Metrics report summarizing:  
  * Precision, recall, and F1 on held-out validation set  
  * False-negative rate on seeded UXO-style targets  
  * Comparison against SOW \#1 baseline metrics  
  * Per-chunk inference time on TX2  
  * Resource utilization (CPU %, GPU %, memory)  
  * Synthetic data validation summary: general description of the classes and conditions represented in the generated data, examples of synthetic samples alongside real equivalents, and the criteria used to determine that synthetic examples are sufficiently realistic for training inclusion. Crescer AI retains ownership of the underlying generation methodology and architecture; Bedrock's interest is in validating the output characteristics and approving the augmentation dataset prior to training use.  
* Demo-ready containerized build suitable for UKRN client demonstration

*Milestone 3: Magnetometer Fusion MVP*

* *Fusion architecture incorporating SSS and mag data as joint model inputs, developed in collaboration with Bedrock domain expertise*  
* *Trained on Bedrock-provided co-registered SSS and mag datasets*  
* *Synthetic mag data pipeline developed and validated against physics-based forward model specification defined jointly with Bedrock*  
* *Preliminary benchmarking on TX2 including:*  
  * *Detection performance comparison vs. SSS-only baseline (precision, recall, F1)*  
  * *Ferrous vs. non-ferrous discrimination evaluation on available ground truth*  
  * *Per-chunk inference time and resource utilization with mag channel active*  
* *Feasibility and methodology report including assessment of synthetic mag approach and recommended path forward for production*

*Milestone 4: Hardened Mag Model \+ Onboard Validation*

* *Addresses robustness gaps and underperforming regimes identified in Milestone 3*  
* *Refined synthetic mag data pipeline incorporating lessons from Milestone 3 evaluation*  
* *Final onboard performance validation on TX2 with mag channel active*  
* *Full metrics report covering all model variants developed during engagement*  
* *Recommended architecture and training strategy for future retraining as new data or sensor configurations change*

*Milestone 5: Hardened Final Model \+ Full Metrics Report*

* Addresses robustness gaps identified in previous Milestones   
* Final onboard performance validation on TX2  
* Full metrics report covering all model variants developed during engagement  
* Recommended architecture and training strategy for future retraining as new data becomes available

**2\. Bedrock Responsibilities**

* Provide SSS and mag datasets as agreed, train/validation/test split strategy developed jointly with Crescer AI  
* Provide domain expertise and knowledge transfer on magnetometer data interpretation, processing, and synthetic data methodology as needed   
* Provide Bedrock approval on synthetic data augmentation approach prior to use in training (not to be unreasonably withheld; email sufficient)  
* Provide access to Jetson TX2 for joint testing and benchmarking as needed

**3\. Crescer AI Responsibilities**

* Data preparation: clean and augment provided datasets as needed per agreed methodology  
* Develop and validate synthetic data pipeline for SSS and mag modalities  
* Train and tune models to meet agreed accuracy targets  
* Provide all containerized deliverables, metrics reports, and support specified above  
* Bear all compute costs for training and experimentation

**4\. Intellectual Property**

The IP framework established in SOW \#1 and the MSA shall apply to this SOW. For clarity and given the expanded scope, the following additional provisions apply:

* Any mag fusion methodology, forward modeling approaches, or synthetic mag data pipelines developed during this engagement are Deliverables IPR and are owned by Bedrock  
* During the term of this SOW and for a period of 12 months following its completion, Crescer AI agrees not to develop, offer, or deliver magnetometer data fusion services or capabilities for subsea survey applications for any third party without Bedrock's prior written consent. This restriction applies regardless of the underlying architecture or methodology used, and is intended to protect Bedrock's investment in domain knowledge transfer provided under this SOW.  
* Crescer AI may not reuse, adapt, or transfer mag fusion methodology, architectures, or pipelines developed under this SOW to any other client or engagement without Bedrock's prior written consent  
* Bedrock retains ownership of all SSS and mag datasets provided under this SOW and all model weights, configuration files, and inference-time code produced as Deliverables

**5\. Decision Points (to be finalized jointly)**

* Co-registration methodology for SSS and mag data prior to fusion training  
* Synthetic mag data forward model specification and validation approach  
* Acceptance criteria values for Milestone 2 demo-ready build  
* Mag channel input specification and preprocessing requirements  
* Onboard deployment support communication channel and expected response SLA