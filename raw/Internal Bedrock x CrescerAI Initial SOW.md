# Bedrock x Crescer AI Initial SOW

## **1\. POC Objective**

Validate that Crescer AI can train and deliver an automated-target-recognition (ATR) model for Bedrock sidescan sonar (SSS) data and package it so it runs on our embedded platform (Jetson TX2). If the proof-of-concept is accepted, the parties will draft a follow-on Statement of Work to build a full production model and integrate it into the onboard pipeline.

---

## **2\. Deliverables**

Delivery of the Section 2 deliverables and documentation of open decision points will constitute completion of the POC for contractual purposes.

### **2.1 Sample Inference Container**

* Docker image containing:  
  * A sample model capable of running on the Jetson TX2 (TensorRT 8\)  
  * Minimal runtime environment and dependencies.  
  * Command-line entry point to run inference.  
* Instructions to run

### **2.2 Model & Metrics**

* Initial trained ATR model using Bedrock-provided labeled SSS data.  
* Report or presentation summarizing:  
  * Tradeoffs between model size and performance.  
  * Precision, recall, and F1 score on held-out validation set.  
  * False-negative rate on seeded targets.  
  * Average per-chunk inference time on hardware comparable to Jetson TX2.  
  * Resource utilization profile (CPU %, GPU %, memory)  
  * Suggested next steps for improvement

### **2.3 Prototype Web App**

* Access to streamlit app hosted on Crescer servers:  
  * Lets users upload or point to a sample SSS “chunk” (\~3-minute swath).  
  * Runs the model and displays detections with confidence scores.  
  * Provides download of detections as CSV and quick-look image chips.

---

## **3\. Bedrock Responsibilities**

* Supply representative, labeled SSS dataset (train/validation/test split in discussion with Crescer).  
* Provide regular feedback and updates regarding infrastructure and model needs. 

---

## **4\. Crescer AI Responsibilities**

* Data preparation: clean and augment provided dataset as needed.  
* Model training and tuning to meet agreed accuracy targets.  
* Provide Streamlit prototype and metrics report.

---

## **5\. Suggested framework for Intellectual Property & Data Rights**

* **Bedrock Data.** All sidescan sonar data, labels, and related metadata provided by Bedrock remain the sole property of Bedrock. Crescer AI is granted a limited, non-exclusive right to use this data solely for the purpose of performing the services described in this Statement of Work.  
* **Deliverables.** Upon final payment for a production model (post POC), Bedrock will own the trained model weights, any configuration files, and any inference-time code developed specifically for Bedrock to pre-process input data to the model and post-process output data from the model (collectively, the “Deliverables”). Crescer AI retains ownership of any pre-existing code, libraries, or generic training pipelines used to create the Deliverables.  
* **License Back to Crescer AI.** Crescer AI may not use Bedrock data or the Deliverables for any other client or for commercial purposes without Bedrock’s prior written consent.

## **6\. Decision Points (to be finalized jointly)**

These items need agreement between Bedrock and Crescer AI during the POC:

1. Training Data Format & Handoff: exact file format(s) and metadata required for model training.  
2. Tradeoffs between model size and performance.  
3. Pre-processing Requirements – slant-range correction, intensity normalization, or other transforms to apply before inference.  
4. Input Features – which auxiliary data (e.g., altitude, vehicle pose, speed) will be passed to the model.  
5. Data Exchange & Storage – method for moving data between teams (e.g., Mosaic workspace, secure transfer protocol).  
6. Acceptance Criteria Values – final numeric thresholds for precision, recall, false negatives on seeded targets, and per-chunk latency/utilization.  
7. Model I/O Specification – format of the model’s outputs (e.g., CSV schema, OBR overlay fields, provisional lat/lon plus ping/time/range).  
8. Runtime Environment – ONNX version, Docker base image, and any GPU/CPU runtime details (e.g., TensorRT engine if GPU path is chosen).  
9. Performance targets – per chunk inference time, precision, recall thresholds.   
10. Who owns responsibility for future retraining once the production model is delivered (Crescer AI, Bedrock, or shared)?  
11. Definition of long-term support: bug fixes, periodic retraining, updates when sensors or data characteristics change.  
12. Termination scenario: longer term once we have a production model, if the contract ends, confirm that Bedrock receives a stable, production-ready model, the right to run it, and the ability to make bug fixes or improvements.  
13. Check-in cadence and style: how often progress updates occur during the POC (e.g., weekly Slack/Zoom sync) and what form status reports will take.

---

## **7\. Timeline & Next Steps**

* Week 1: data hand-off and environment alignment. Bedrock provides Crescer access to TX2  
* Week 2: delivery of sample model container  
* Week 3-9: Crescer AI training & internal evaluation.  
* Week 10: delivery of container, Streamlit prototype, and metrics report.  
* Week 11: joint review and smoke test on Bedrock Jetson TX2.

