Jul 28, 2026

## **Bedrock Discussion Continued (understanding eval agent)**

Invited [Sachin Pandey](mailto:sachin@crescer.ai) [Hemanth Sarabu](mailto:hemanth@crescer.ai) [Geoff Horowitz](mailto:geoff@crescer.ai) [Pratyaksh Singh](mailto:pratyaksh@crescer.ai)

Attachments [Bedrock Discussion Continued (understanding eval agent)](https://calendar.google.com/calendar/event?eid=NWtpaWd0MzVyZDNpNmt0ZDh2Y3E4YnVxdmcgZ2VvZmZAY3Jlc2Nlci5haQ) [Notes by Gemini](https://docs.google.com/document/d/1jPIS4B1g7Qd7rbgUkOU2oS_HvWhMC7U6ZPofTXN17As/edit?usp=meet_tnfm_calendar)

Meeting records [Recording](https://drive.google.com/file/d/1vf0SghDgJy_dzsqn9GHnu2V_-pic1cS1/view?usp=drive_web) 

### **Summary**

Technical teams discussed synthetic data generation strategies and infrastructure challenges while standardizing collaborative resource management via a repository.

**Enhancing Workflow and Generation**  
A consensus emerged to establish a centralized repository for sharing technical resources to improve efficiency. Development shifted toward procedural generation methods, including reconstruction loops, to mitigate token limitations.

**Advanced Image Data Modeling**  
Analyses revealed quality inconsistencies in the dataset and limitations in using Singular Value Decomposition. Strategies now prioritize Empirical Mode Decomposition and Variational Autoencoder training for synthetic data production.

### **Decisions**

## Aligned

* **LLM evaluation judge strategy adopted** The team adopted a strategy of framing the procedural generation problem by utilizing an LLM as an evaluation judge to score and provide feedback on in-distribution samples.

* **Data processing assumptions policy established** The team established a policy to avoid making assumptions about data conventions (such as rotation or axis orientation) when processing new datasets, instead opting to investigate the base structure.

* **Usage of 25 pixel-based augmentations** The team will utilize 25 pixel-based color augmentations for the model.

We've **updated the Decisions section** using your feedback.

Let us know what you think: [Helpful](https://google.qualtrics.com/jfe/form/SV_5bXzKQfylMIhSXc?isHelpful=True&entryPoint=decisions&confid=MYzYg_porhCxFHOG_KvADxIXOBEBMgUIigIgABgBCA&isGoogler=False) or [Not Helpful](https://google.qualtrics.com/jfe/form/SV_5bXzKQfylMIhSXc?isHelpful=False&entryPoint=decisions&confid=MYzYg_porhCxFHOG_KvADxIXOBEBMgUIigIgABgBCA&isGoogler=False)

### **Next steps**

- [ ] \[The group\] Create Skills Repository: Establish a repository to document and share team skills.

- [ ] \[Pratyaksh Singh\] Share Data Paper: Provide the research paper that introduces the 300k open source image data set.

- [ ] \[The group\] Test Procedural Generation: Use an LLM to transform open source images into the target data distribution.

- [ ] \[Sachin Pandey\] Process Ulyses Data: Analyze the Ulyses data set and run a model evaluation on the processed information.

- [ ] \[Sachin Pandey\] Create Slack Channel: Initialize a new communication channel for ongoing discussions regarding data variations.

- [ ] \[Sachin Pandey\] Analyze Data Variations: Instruct the agent to consider multiple rotation and convention variations. Plot the findings to evaluate potential improvements in data structure interpretation.

- [ ] \[Pratyaksh Singh\] Experiment with decomposition: Test Empirical Mode Decomposition and frequency domain transforms to isolate image components.

- [ ] \[Pratyaksh Singh\] Set up VAE: Explore dataset feasibility for pretraining a Variable Autoencoder to generate synthetic data. Report progress findings during the next meeting.

- [ ] \[Sachin Pandey\] Share image repository: Post the HTML repository containing image augmentation data to the Slack channel.

- [ ] \[Sachin Pandey\] Post Ulisses discussion: Create a new Ulisses channel and document the recent group discussion there.

### **Details**

* **Eval Agent and Data Strategy**: Sachin Pandey clarifies the progress on the Eval Agent, explaining that the team is shifting away from modifying existing data and toward using open-source data as a base for model training. Sachin Pandey notes that the previous approach of modifying the same data resulted in outputs indistinguishable from standard augmentations, and they aim to use the model to convert open-source data into the required format to improve validation accuracy.

* **Defining Roles and Collaboration**: Pratyaksh Singh joins the meeting to clarify that they and Sachin Pandey are collaborating, with Pratyaksh Singh providing guidance. The team discusses the need to standardize the sharing of skills and repositories to improve workflow efficiency, and they reach a consensus to create a repository for sharing these resources.

* **Image Generation Challenges**: Pratyaksh Singh reports on the attempt to use the Codex (SOL 5.6) model to generate images that match their dataset, noting that the results were unsatisfactory and appeared overly synthetic. The team discusses whether to persist with LLM-in-the-loop generation or explore alternative procedural generation methods.

* **Data Sourcing**: Pratyaksh Singh identifies an open-source dataset containing approximately 300k images that may be relevant to their project. The team agrees to review the research paper describing this dataset to determine its utility.

* **Tool Access and Costs**: The group discusses access to advanced AI models, noting that certain models like GLM 5.2 are resource-intensive and difficult to host, while pay-as-you-go models are costly. Pratyaksh Singh notes that attempting to run large models often leads to slow processing speeds, such as 3 or 4 tokens per second, making them difficult to utilize.

* **Procedural Generation via Computational Graphs**: Hemanth Sarabu suggests investigating the use of computational graphs, or "graphs as behaviors," to define system hardness and behavior. Hemanth Sarabu proposes framing the problem as a hill-climbing task for an LLM, where the model is incentivized to optimize a score through iterative improvements.

* **Reconstruction Loop Framework**: Hemanth Sarabu introduces a conceptual framework for data generation where an LLM is tasked with reproducing reference images using procedural generation. They suggest that by forcing a system to learn reconstruction, similar to VAEs or diffusion models, they can eventually perturb the process to create new training data.

* **Implementation of Procedural Generation**: Pratyaksh Singh elaborates on the strategy of using open-source, high-resolution data as a base to be converted into their target data format. The goal is to use an LLM as a judge to score how well the generated image matches the target distribution and provide feedback to the coding agent regarding necessary changes.

* **Data Quality Issues (Ulysses Dataset)**: Sachin Pandey presents findings from the recently acquired Ulysses data, noting that it shows unexpected patterns, specifically varying shades and shapes rather than the expected consistent shading. Hemanth Sarabu advises against assuming the data structure is fixed and suggests investigating potential rotation, flip, or convention discrepancies before concluding the data is inherently flawed.

* **Token Limitations and Computation**: Pratyaksh Singh notes that running loops on the entire dataset is not feasible due to token limitations, as high-resolution images require significant tokens. The team discusses the need to use heuristics or metrics computed on-device rather than passing full images into the model's context window.

* **Dimensionality Reduction for Image Analysis**: Pratyaksh Singh reports on using Singular Value Decomposition (SVD) to analyze image components, finding that the top 10 singular values can reconstruct an image effectively. Hemanth Sarabu suggests that instead of SVD, the team should test Earth Movers Distance (EMD) to potentially isolate linearly separable components more effectively in the continuous time domain.

* **Proposed Loss Function Design**: Pratyaksh Singh proposes using a vision model as a judge to evaluate whether images are in-distribution, providing feedback to the coding agent to refine the images until reaching a score of 0.9. Hemanth Sarabu agrees this is a good starting point but suggests the VLM may require assistance due to inherent limitations; they propose integrating heuristics such as perceptual loss or object detection to improve accuracy.

* **Perceptual Loss and PCA Limitations**: Pratyaksh Singh suggests that perceptual loss, potentially utilizing AlexNet features, would be a robust solution. Hemanth Sarabu notes that while PCA was used to extract gradients from images, it struggles with non-linear components, citing the presence of oscillations in PC4 that are not linearly separable.

* **Empirical Mode Decomposition and Alternative Methods**: Hemanth Sarabu suggests attempting Empirical Mode Decomposition (EMD) to better handle non-linear components, acknowledging this is a personal bias. Pratyaksh Singh agrees to test EMD and also investigate the frequency domain to see if it yields better results.

* **VAE and Pre-training Strategy**: Hemanth Sarabu suggests training a Variational Autoencoder (VAE) to extract components from an embedding space or "codebook". Pratyaksh Singh plans to explore pre-training and fine-tuning a VAE or a diffusion tool using available open-source data. Despite concerns regarding potential bias, Pratyaksh Singh intends to review the dataset and provide an update on the feasibility of this approach tomorrow.

* **Synthetic Data and Augmentation Plans**: Regarding backup strategies if synthetic data generation is unsuccessful, Pratyaksh Singh proposes training a model with heavy augmentation, specifically citing the 25 pixel-based color augmentations identified by Sachin Pandey. Sachin Pandey confirms they will share the relevant documents from the HTML repository on Slack.

* **Project Objectives and Communication**: Geoff Horowitz instructs the team to create a new Ulysses channel to document and discuss these findings. Hemanth Sarabu emphasizes that the main objective is to use this project as an opportunity to learn how to generate synthetic data, regardless of how the Bedrock model improves.

