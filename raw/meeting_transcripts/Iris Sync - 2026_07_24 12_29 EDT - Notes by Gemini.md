# **📝 Notes**

Jul 24, 2026

## **Iris Sync**

Invited [Pratyaksh Singh](mailto:pratyaksh@crescer.ai) [Niveta Iyer](mailto:niveta@crescer.ai) [Hemanth Sarabu](mailto:hemanth@crescer.ai) [Geoff Horowitz](mailto:geoff@crescer.ai) [Siddharth Soni](mailto:siddharth@crescer.ai) [Ratul Shashank](mailto:ratul@crescer.ai) ~~[Sachin Pandey](mailto:sachin@crescer.ai)~~

Attachments [Iris Sync](https://calendar.google.com/calendar/event?eid=NnNzMHVxNzk3MmJqZGVwNXFoN2J1Mjd1OTdfMjAyNjA3MjRUMTYzMDAwWiBnZW9mZkBjcmVzY2VyLmFp)

Meeting records [Transcript](https://docs.google.com/document/d/1ljd3-Ol2DLj4hTniCB87GmdL3X_4v3ND0AgQKOVrDrY/edit?usp=drive_web&tab=t.uixg58ipn43) 

### **Summary**

The team reviewed model progress and data constraints while aligning on generative strategies and evaluation methodologies.

**Reviewing Project Strategy Goals**  
The team prioritized Unexploded Ordnance detection and balanced client preferences for higher recall over precision. Improvements focus on retraining models with integrated data and Magnetic fusion.

**Managing Data Quality Issues**  
Existing datasets suffer from significant duplication and geographic non-diversity. Implementation of K-fold cross-validation will improve statistical reliability for model performance assessments.

**Enhancing Model Training Data**  
Generative modeling creates novel object variations to address training shortages. One primary decision merged Unexploded Ordnance and Area of Interest small black objects into a single training class.

### **Decisions**

## Aligned

* **Current data constraints accepted** The project will proceed with current data availability, assuming no additional client data will be provided.

* **Model improvement scope defined** The model improvement scope is strictly limited to updating with new data, integrating synthetic data, and incorporating MAG fusion.

* **Metrics presentation strategy** The reporting strategy will prioritize qualitative examples over quantitative metrics when presenting performance updates to the client.

* **UXO performance prioritization** The UXO classification is prioritized, while ensuring that performance on existing non-UXO classes does not regress.

* **Performance metric preference** The performance metric priority is set to recall over precision, accepting higher false positives to minimize false negatives.

* **K-fold cross-validation standard** The K-fold cross-validation method is required for all final model deliveries to ensure statistically significant performance results.

* **UXO and AOI classification strategy** The UXO and AOI small black classes are treated as a single category during training but separated for evaluation and client presentation.

* **Client label verification process** The internal UXO and AOI classifications will be submitted to the client for verification and correction to refine the training dataset.

* **Mandatory code backup on GitHub** The team established a policy to back up all project code on GitHub or an existing repository branch to ensure data security.

* **Generative AI and augmentation strategy** The team decided to utilize generative AI for creating novel objects while using classical computer vision techniques for data augmentation, such as adjustments to elongation and background shapes.

* **MAG data incorporation milestone** The team established the incorporation of MAG data as the next project milestone to enable differentiation between object classes.

* **Retention of validation set images** The team decided to retain all provided images, including long and zoomed-out examples, within the validation set.

* **Cross-validation approach for model evaluation** The team decided to implement cross-validation to improve model recall and performance.

We've **updated the Decisions section** using your feedback.

Let us know what you think: [Helpful](https://google.qualtrics.com/jfe/form/SV_5bXzKQfylMIhSXc?isHelpful=True&entryPoint=decisions&isGoogler=False) or [Not Helpful](https://google.qualtrics.com/jfe/form/SV_5bXzKQfylMIhSXc?isHelpful=False&entryPoint=decisions&isGoogler=False)

### **Next steps**

- [ ] \[Pratyaksh Singh\] Research Seabed Simulation: Investigate existing research papers on placing objects on the seabed to simulate side-scan sonar data. Determine if a similar simulation method is feasible for the current project.

- [ ] \[Pratyaksh Singh\] Explore Agentic Simulation: Test agentic approaches by prompting models like Claude or Anti-gravity to derive a physics-based simulator for sonar data. Evaluate potential strategies for using these agents to build environmental simulations.

- [ ] \[Geoff Horowitz\] Consult Bridget: Inform the client that UXO and AOI Small Black objects are visually indistinguishable. Inquire how the client differentiates these categories to inform modeling and evaluation strategies.

- [ ] \[The group\] Implement Cross-Validation: Set up K-fold cross-validation for the model to ensure statistically significant results. Perform this validation process prior to delivering the final model.

- [ ] \[Ratul Shashank\] Present Generation Results: Demonstrate the Flux Turbo based object generation results to the team. Share these findings to evaluate potential model improvements.

- [ ] \[The group\] Prepare Shape Files: Create and distribute shape files containing latitude and longitude coordinates for data verification.

- [ ] \[Ratul Shashank\] Document Model: Share a document in the channel outlining model inputs, outputs, and training dataset statistics.

- [ ] \[Pratyaksh Singh\] Create Repository: Set up a GitHub repository to host the fine-tuning code.

- [ ] \[Ratul Shashank\] Upload Fine-tuning Code: Commit the fine-tuning code to the project repository.

- [ ] \[Ratul Shashank\] Generate Backgrounds: Run experiments to have the model generate backgrounds based on provided example data.

- [ ] \[Ratul Shashank\] Compare Models: Test and evaluate the effectiveness of closed-source versus open-source models for object generation.

- [ ] \[Ratul Shashank\] Perform Prompt Engineering: Attempt image generation through prompt engineering methods instead of using model fine-tuning.

- [ ] \[Sachin Pandey\] Slack Update: Share an update regarding retrained models on Slack for Geoff.

- [ ] \[Sachin Pandey\] Create Write-up: Document the findings and progress on current tasks in a written format.

- [ ] \[Sachin Pandey\] Share Link: Send the link for the model prediction analysis to Pratyaksh.

- [ ] \[Sachin Pandey\] Loss Analysis: Conduct a detailed loss analysis of all 130 images to detect error patterns. Submit these findings to Pratyaksh.

- [ ] \[Sachin Pandey\] Cross Validation: Perform K-fold cross validation on the training data.

### **Details**

* **System Status Update**: Hemanth informed the team that the "Ninja" system experienced power issues at their home and in San Francisco, causing it to go offline temporarily, but it was expected to return soon, while the "Wall-E" system remained functional ([00:00:03](#00:00:03)).

* **Client Meeting Update**: Geoff updated the team on their recent call with Bridget, reporting that the client was happy with the representative examples and progress shown via the Streamlit app ([00:02:16](#00:02:16)).

* **Synthetic Data Presentation**: Geoff presented the synthetic data strategy to Bridget by framing the iterations as a range from restrictive, true-to-life models to more generalized iterations, noting that she understood the limitations of the current target generation examples ([00:03:55](#00:03:55)) ([00:16:07](#00:16:07)).

* **Data Availability Limitations**: Geoff reported that Bridget confirmed they had shared all available UXO data and that no additional data is currently available, though they might collect more during upcoming operations in San Diego, which would be shared if obtained ([00:05:08](#00:05:08)).

* **Project Milestones Review**: Hemanth and Geoff clarified that the project milestones focus on retraining the model with new data, integrating synthetic data, and implementing MAG fusion as the primary technical improvements ([00:07:39](#00:07:39)).

* **Model Performance and Data Constraints**: Pratyaksh reported that improvements in the model's performance have stalled, likely due to data limitations, despite testing extensive augmentations ([00:08:45](#00:08:45)) ([00:20:41](#00:20:41)).

* **Expectations for Metrics**: Geoff noted that Bridget does not require specific, high-level metrics but expects the team to present qualitative performance results that are not embarrassing to leadership ([00:09:41](#00:09:41)).

* **Class Priorities and Multiclass Goals**: Geoff and the team discussed that Bridget prioritizes UXO detection over previous targets (support and benthos), although the team agreed they should avoid regressing on those earlier classes ([00:12:16](#00:12:16)).

* **Client Preferences for Recall and Precision**: Geoff relayed that Bridget prefers recall over precision, indicating a willingness to accept more false positives rather than missing potential contacts, though the team noted this must be balanced to avoid poor overall performance ([00:13:20](#00:13:20)).

* **Data Duplication Issues**: Pratyaksh demonstrated through a screen share that the current dataset contains many duplicated files from the same locations, which contributes to the model's overfitting and limits the effectiveness of augmentations ([00:18:37](#00:18:37)).

* **Model Performance Discrepancies**: Pratyaksh observed that the model performs better on the VW dataset compared to others, and while they are detecting some previously missed UXOs, the results vary and are affected by the small, geographically non-diverse nature of the data ([00:20:41](#00:20:41)).

* **Physics-Based Simulation Proposal**: Hemanth proposed a "Real-to-Sim" strategy to build a physics-based simulation for side scan returns using existing XTF files, trajectories, and MAG data, rather than relying solely on learning models to generate intensities ([00:25:42](#00:25:42)).

* **Agentic Simulation Strategy**: Hemanth and Pratyaksh discussed applying techniques similar to autonomous driving "real-to-sim" workflows, where agents use scene descriptions, trajectories, and ground truth data to reconstruct and simulate sonar renders ([00:27:59](#00:27:59)).

* **Cross-Validation Strategy**: To address the limited, geographically overlapping dataset, Pratyaksh and Hemanth agreed on the necessity of performing K-fold cross-validation to obtain more statistically dependable results regarding model performance ([00:33:32](#00:33:32)).

* **Generative Model Development**: Ratul reported successful initial results using Flux and LoRA to categorize UXOs by elongation, generating plausible synthetic objects that outperformed previous methods ([00:37:03](#00:37:03)) ([00:53:31](#00:53:31)).

* **Class Distinction and Confusion**: The team identified that UXOs and "AOI small black" objects are visually indistinguishable, leading to the decision to treat them as the same class during training while keeping them separate during evaluation and presentation to the client ([00:38:08](#00:38:08)).

* **Client Verification of Labels**: The team decided to share images and labels with the client to verify which objects are true UXOs, helping to clean the training data and reduce the risk of human error during client demonstrations ([00:48:33](#00:48:33)).

* **Technical Workflow for Generative Models**: Ratul explained the current technical workflow, which involves categorizing objects based on elongation, training LoRA models on these specific classes, and using multiple seed generation to improve image quality ([00:53:31](#00:53:31)).

* **Control Variables for Model Generation**: Hemanth Sarabu and Ratul Shashank identified that the control variables for the generative model include the reference image, labels—specifically COCO annotations—and model parameters such as noise and strength. Ratul Shashank noted their intention to train a safe tensor to generate specific examples, with the goal of testing whether the model could create novel variations of objects, such as adjusting shadows or elongation, rather than simply replicating the input image ([00:58:26](#00:58:26)).

* **Code Management and Accessibility**: Pratyaksh Singh requested that Ratul Shashank create a document and GitHub repository to manage the code for fine-tuning the model ([01:02:47](#01:02:47)). Geoff Horowitz emphasized the necessity of backing up all code on GitHub to prevent potential data or project loss due to issues with existing infrastructure like Wall-E, and Ratul Shashank agreed to resolve any access issues they previously encountered with the repository ([01:05:57](#01:05:57)).

* **Generating Diverse Training Data**: Pratyaksh Singh proposed using generative models to create novel Unexploded Ordnance (UXO) examples to address the lack of sufficient training data ([01:07:21](#01:07:21)). They suggested that if an open-source model could generate valid examples 10% to 20% of the time, the team could scale this process by having labelers verify the results, and Ratul Shashank agreed to test this strategy using both existing images and pure text-based prompts ([01:08:33](#01:08:33)) ([01:19:58](#01:19:58)).

* **Chain of Generation Hypothesis**: Ratul Shashank proposed a hypothesis for feeding a generated object back into the generative model after applying transformations like rotation or translation ([01:10:33](#01:10:33)). Pratyaksh Singh encouraged them to test this approach, although they expressed uncertainty about the outcome, noting that iterative generation processes can sometimes lead to random or degraded outputs ([01:14:31](#01:14:31)).

* **Defining Similarity and Data Requirements**: Pratyaksh Singh clarified that the team requires generated images to maintain the visual characteristics of Unexploded Ordnance (UXO) while being distinct enough to improve the robustness of the classification model ([01:23:12](#01:23:12)). Ratul Shashank and Pratyaksh Singh agreed that while some augmentations like shadow length and shape changes could be handled via classical computer vision, generative AI was necessary for creating entirely new object structures ([01:24:19](#01:24:19)).

* **Differentiation of Area of Interest (AOI) Small Black and UXO**: Ratul Shashank and Geoff Horowitz discussed the challenge of distinguishing between "Area of Interest" (AOI) small black patches and UXO, which currently represents a bottleneck ([01:28:06](#01:28:06)). Geoff Horowitz explained that while incorporating magnetic (MAG) data would be the solution for separating these two classes, it is not currently available, so the team will proceed with the existing pipeline as an interim measure ([01:29:31](#01:29:31)).

* **Model Training Progress**: Sachin Pandey reported that three models trained on "Ninja" failed to learn effectively, with training loss remaining stagnant at 0.9. Sachin Pandey confirmed that new experiments were underway on "Wally" and that they were conducting a thorough review of matrix calculations to ensure data integrity ([01:30:33](#01:30:33)).

* **Evaluation Strategies and False Positive Reduction**: Pratyaksh Singh and Sachin Pandey discussed addressing model errors, specifically focusing on reducing false positives caused by bounding box overlaps ([01:32:43](#01:32:43)) ([01:34:58](#01:34:58)). Sachin Pandey proposed implementing size filters based on class, noting that classes like "AI big" have predictable pixel sizes, which could help filter out incorrect predictions and improve overall precision ([01:33:56](#01:33:56)).

* **Performance Analysis and Next Steps**: Sachin Pandey reported that a recent multiclass model achieved a recall of 86% and a precision of 0.59, performing better than the binary model in most instances ([01:37:57](#01:37:57)) ([01:44:21](#01:44:21)). Pratyaksh Singh requested that Sachin Pandey conduct a loss analysis—reviewing individual predictions to identify error patterns—and they agreed to keep all images, including long or zoomed-out samples, in the validation set for comprehensive testing ([01:39:00](#01:39:00)) ([01:47:23](#01:47:23)).

* **Data Augmentation Strategy**: Pratyaksh Singh and Sachin Pandey discuss applying masks as a data augmentation strategy, specifically focusing on adjusting the original brightness and contrast levels of images. They reference utilizing dropations.ai/explore to facilitate these augmentation processes ([01:55:39](#heading=h.r8hxedv8risj)).

* **Starboard Data and Image Processing**: The team addresses the processing of starboard data, with Pratyaksh Singh suggesting the use of grid splits and separate images. Sachin Pandey confirms the process of converting files from HDF (Hierarchical Data Format) to PNG (Portable Network Graphics) and using cropped versions of the images to handle the data appropriately ([01:55:39](#heading=h.r8hxedv8risj)).

* **Open Source Models and Prompting**: The conversation shifts to the use of open-source training data and models. Ratul Shashank and Pratyaksh Singh discuss the use of JSON (JavaScript Object Notation) prompts, describing textured artifacts, and the potential for using open-source datasets to train models instead of relying solely on "vanilla" approaches ([02:01:38](#heading=h.2sifpr725t7s)).

* **Model Evaluation and Validation**: The participants address performance metrics and model refinement. Sachin Pandey cites recall figures of 91, 92, 88, and 86, while Pratyaksh Singh stresses the importance of using cross-validation to improve model performance. Additionally, they discuss specific image details, such as the UXO (unexploded ordnance) background located at the bottom left, and the need to address these features on a pixel basis to establish ground truth ([02:12:24](#heading=h.lzv76inkjjn7)).

*You should review Gemini's notes to make sure they're accurate. [Get tips and learn how Gemini takes notes](https://support.google.com/meet/answer/14754931)*

*How is the quality of **these specific notes?** [Take a short survey](https://google.qualtrics.com/jfe/form/SV_5bXzKQfylMIhSXc?confid=IU9jrvvJ5VFDLKx6fYFuDxIUOBEBMgUIigIgABgECA&detailid=standard&screenshot=false&entryPoint=footerMain&isGoogler=False) to let us know your feedback, including how helpful the notes were for your needs.*

# **📖 Transcript**

Jul 24, 2026

## **Iris Sync \- Transcript**

### **00:00:03** {#00:00:03}

**Ratul Shashank:** Wait a

**Sachin Pandey:** Hi,

**Ratul Shashank:** second.

**Sachin Pandey:** you watch clear.

**Ratul Shashank:** Sorry.

**Sachin Pandey:** Am I audible? Like uh trying to change the settings

**Ratul Shashank:** No,

**Sachin Pandey:** like

**Ratul Shashank:** you are you are perfectly audible.

**Sachin Pandey:** Okay.

**Ratul Shashank:** as Ninja online.

**Sachin Pandey:** I don't know. I need to check.

**Geoff Horowitz:** Guys, can you hear me?

**Ratul Shashank:** Yeah.

**Sachin Pandey:** I just

**Geoff Horowitz:** Okay.

**Hemanth Sarabu:** Hey guys. Um, there were a couple of power events in San well, one of them was at my home in my home and one was in the area in San Francisco. So, that left Ninja turned off. It'll be turned on soon. Um, and then Wall-E should be back up. Are you guys having any trouble with Wall-E?

**Sachin Pandey:** No, it it got down for few like few minutes in the middle but it is working right

**Hemanth Sarabu:** Yeah.

**Sachin Pandey:** now.

**Geoff Horowitz:** Yeah, I agree.

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** Uh, sorry, Ham, you said Ninja will be up

**Hemanth Sarabu:** Yeah, I should be up here.

### **00:02:16** {#00:02:16}

**Geoff Horowitz:** soon. Oh, hey Pro. Um, okay.

**Pratyaksh Singh:** And it

**Geoff Horowitz:** Let me let me start quickly.

**Pratyaksh Singh:** is

**Geoff Horowitz:** Let me give you an update on the call with Bridget. Um, and then and then I think I think you had the most uh the most kind of open items from the last meeting. So I would like you to take it away after that. Um okay. So my uh give me one second just open my notes. So my call with Bridget went very well. Went very well. She um we talked, you know, we talked a little bit about uh the progress we're making. I showed her some some representative examples um using the Streamlit app. She was pretty happy with those. You know, I crafted some story about how like even our existing models are showing a lot of improvement over uh just the baseline of what we had from the first deliverable. Um sorry.

**Hemanth Sarabu:** That was a sneeze.

**Geoff Horowitz:** Oh, because I'm tight.

### **00:03:55** {#00:03:55}

**Geoff Horowitz:** Um and you know, they're excited to hear that. So, so she was really happy with all that. Um then we spent some time going through the um synthetic data. uh she was basically I I kind of framed it as in a few different directions and I think I think project actually you you had seen this in the in the modified deck that you gave me but uh I kind of framed it in in a few different places where you know we're starting that we're doing a few different iterations of um target generation and those iterations give the model more and more freedom. So without telling her that we were doing kind of cut and paste, right? I was telling her that that the first iteration of the model is is very restrictive, right? It's very kind of true to life. And then I showed her kind of, you know, future iterations where um where the model gets more freedom, but that could create it it it you know could give more generalization, but it could create more false positives.

### **00:05:08** {#00:05:08}

**Geoff Horowitz:** Um, I kind of emphasized with her that, you know, more data would be really good. She said there's a possibility that we could get more data from the UK Royal Navy, but she she doesn't know and she won't know until uh for a few more weeks. Um,

**Hemanth Sarabu:** But have they exhausted all the data they can give

**Geoff Horowitz:** she said they have she said they're going out to San San Diego.

**Hemanth Sarabu:** us?

**Geoff Horowitz:** San Diego uh next week or two weeks and they they're they might be collecting more. If they are, then she'll share that with us. Um,

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** But according to her, she's shared all the UXO data that she can.

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** Um, I also showed her the the background generation stuff. Overall, she was really happy, really excited. She she kind of understood the limitations uh specifically with the target generation that, you know, we only have so many examples, right? And so the the generated data is just going to look like those examples.

### **00:06:18**

**Geoff Horowitz:** She understood that um but was still really excited about what we could do in the generation space. Those were the highlights. I have some more notes, but I'd like to pause there to see if you guys have any

**Hemanth Sarabu:** Thanks.

**Geoff Horowitz:** questions.

**Pratyaksh Singh:** Yeah, regarding more data like I mean can you can you add more on it like is it possible to get it? Will it be possible

**Geoff Horowitz:** I I think we have to assume it won't be.

**Pratyaksh Singh:** or

**Geoff Horowitz:** Um Bridget Bridget understands that that's going to limit you know the the um the performance of the model. Uh there is a possibility that we'll get more data. Also project if you kind of remember the layout this is we've

**Pratyaksh Singh:** Mhm.

**Geoff Horowitz:** kind of got three different milestones that are about improving the model. And so I'm okay with just giving her what we have or the best that we can do and then for

**Pratyaksh Singh:** Mhm.

**Geoff Horowitz:** future milestones if we get more data or we you know integrate MAG or we do these other things that the results will get incrementally better.

### **00:07:39** {#00:07:39}

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** This

**Hemanth Sarabu:** Um three milestones are updating the model with new data.

**Geoff Horowitz:** Yeah.

**Pratyaksh Singh:** job.

**Hemanth Sarabu:** Second one is synthetic. Third is mag.

**Geoff Horowitz:** I is that is that true? Hammond is milestone 2 does milestone 2 also include some synthetic

**Hemanth Sarabu:** So I I don't think there were if we don't include synthetic I don't recall there being three

**Geoff Horowitz:** data.

**Hemanth Sarabu:** or two improvements right we only promised we'll retrain on new data we'll add synthetic stuff we'll add mag there was no not supposed to be there was no other technology we were going to add

**Geoff Horowitz:** So this is this is kind of the summary here. Um what I have here is milestone 2 is updates basic basic synthetic data. Um integrate this synthetic data pipeline. What do I have for three? Oh three is mag fusion. Three is mag fusion.

**Hemanth Sarabu:** Yeah,

**Geoff Horowitz:** And then four and five are kind of just updating the model.

**Hemanth Sarabu:** integration. Yeah,

**Geoff Horowitz:** Yeah.

### **00:08:45** {#00:08:45}

**Hemanth Sarabu:** that's what I'm saying. I think as far As far as the as far as the tricks we were going to use to improve the model, it was just going to be retrain synth synthetic and mag. That's it.

**Geoff Horowitz:** Yeah.

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** But I'm saying if if we get more data, I mean that's that's great for Biosar 4,

**Hemanth Sarabu:** Yeah. Uh yeah. Yeah.

**Geoff Horowitz:** you know.

**Hemanth Sarabu:** Yeah. Yeah. But I'm I'm going to assume we don't get more data. Or let let me put it differently.

**Geoff Horowitz:** I agree.

**Hemanth Sarabu:** We're doing the best we can with the amount of data we get.

**Geoff Horowitz:** Yes,

**Hemanth Sarabu:** Given

**Geoff Horowitz:** I agree. Um, okay. Some other notes. Go

**Hemanth Sarabu:** really quickly prod are we seeing we're seeing

**Geoff Horowitz:** ahead.

**Hemanth Sarabu:** improvement due to augmentations and synthetic data. Is that right or is that wrong?

**Pratyaksh Singh:** some improvement. I think I think it has stalled. I have tried a lot of things but it has kind of

### **00:09:41** {#00:09:41}

**Hemanth Sarabu:** Sure.

**Pratyaksh Singh:** stalled and I think going back it's it's related to data only there is uh see uh okay can I uh once can we continue this once Jeff finishes

**Geoff Horowitz:** I've only got a few more points here.

**Hemanth Sarabu:** Okay. Well, Jeff,

**Geoff Horowitz:** So,

**Hemanth Sarabu:** really quickly,

**Geoff Horowitz:** yes,

**Hemanth Sarabu:** um,

**Geoff Horowitz:** sir.

**Hemanth Sarabu:** th this this whatever you presented to, uh, Bridget was, hey, we retrain the model on the new data, right?

**Geoff Horowitz:** Correct. And we and we made some minor improvements so

**Hemanth Sarabu:** We some minor I'm I'm wondering

**Geoff Horowitz:** far.

**Hemanth Sarabu:** does do we have enough room do we have enough room to show performance improvements for synthetic data and I guess mag I'm not too concerned about just the synthetic data milestone.

**Geoff Horowitz:** I I didn't give her any metrics.

**Hemanth Sarabu:** Okay, great. Great.

**Geoff Horowitz:** Yes,

**Hemanth Sarabu:** Great.

**Geoff Horowitz:** I didn't give her any metrics.

**Hemanth Sarabu:** All right.

**Geoff Horowitz:** And Hemant just to just to kind of actually that's one of my points here.

**Hemanth Sarabu:** Okay.

### **00:10:58**

**Geoff Horowitz:** We talked a little bit about metrics. He may recall this from past conversations with Bridget.

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** Bridget is not overly concerned about metrics themselves. she's she's okay giving kind of a qualitative measure of um

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** performance but she she explicitly said like the metrics need to be not terrible so that if you know Charlie the um the CTO Yeah.

**Hemanth Sarabu:** See you. Oh

**Geoff Horowitz:** or the CEO um ask about it or if the client asks about it that you know they

**Hemanth Sarabu:** yeah.

**Geoff Horowitz:** can present them without being embarrassed which I think is reasonable. Um, so yeah, so I didn't actually give her any metrics. I just kind of showed her a few examples.

**Hemanth Sarabu:** Okay. Okay, that sounds good.

**Geoff Horowitz:** Yeah. Um, that said, that said,

**Hemanth Sarabu:** Mommy.

**Geoff Horowitz:** I really don't want to show worse performance than what we delivered on the last one if possible.

**Hemanth Sarabu:** You mean numbers?

**Geoff Horowitz:** Yes, numbers. I do mean

**Hemanth Sarabu:** Yeah.

### **00:12:16** {#00:12:16}

**Hemanth Sarabu:** I I I don't I Okay,

**Geoff Horowitz:** numbers.

**Hemanth Sarabu:** we can talk about it. I don't think we can compare them like that.

**Geoff Horowitz:** Let's talk about it one second. I I've got two other things here. Number one is um I asked her about multiclass and

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** basically what she said was look, you know, this is the same thing something similar that we've talked about before. She said multiclass would be awesome. it would really show kind of our our value and the model's capabilities that would be really really really

**Hemanth Sarabu:** Heat.

**Geoff Horowitz:** good. She said if it's a problem then what she's focused on is UXO that if we have a model that says this is a UXO this is not a UXO that's that's the critical component. Um,

**Pratyaksh Singh:** What about the previous things that she gave us the support and bin

**Geoff Horowitz:** so we she she cares

**Pratyaksh Singh:** forms?

**Geoff Horowitz:** less she cares less about the previous things.

**Pratyaksh Singh:** So UXO is like most important that's all

### **00:13:20** {#00:13:20}

**Geoff Horowitz:** UXO is most important because that's what the UK Royal Navy is focused

**Pratyaksh Singh:** that's okay and the

**Geoff Horowitz:** on.

**Hemanth Sarabu:** U it's not like uh yes UXO is important but

**Pratyaksh Singh:** data

**Hemanth Sarabu:** that doesn't mean we we should not be regressing on the other

**Geoff Horowitz:** Yes,

**Hemanth Sarabu:** classes.

**Geoff Horowitz:** I agree.

**Hemanth Sarabu:** Does that make sense? the target the if you had to pick uh basically the worst we can do on the old classes is how we did last time and then we

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** try to maximize performance on

**Pratyaksh Singh:** Got it.

**Hemanth Sarabu:** UXO

**Geoff Horowitz:** Yes. Um the other thing that she said which you know well we can discuss this briefly but she said that she still does prefer recall to precision. meaning she still does prefer that we if if if we had to choose between getting more false positives or more false negatives, she'd prefer more false positives. She would prefer that we accidentally call something, you know, a contact. We have to get a human to look at it.

### **00:14:41**

**Geoff Horowitz:** The human says, "No, this isn't a contact." And you know we move on rather than us missing a contact. Um, again, the caveat there is if we're just calling everything a contact, then that's poor performance. Um, you know, so she she wants reasonable, but uh but to the extent that we need to kind of balance more false positives or more false negatives, she'd prefer more false positives. questions there.

**Pratyaksh Singh:** No, I think that is that is expected.

**Geoff Horowitz:** Yeah. Uh that's it. We talked a little bit about kind of just timelines.

**Pratyaksh Singh:** Excellent.

**Geoff Horowitz:** Um she she said our our existing timelines are are pretty reasonable. We talked a little bit like if if somebody asks her about it, how long might it take us to, you know, get a Streamlit ad app up or or uh, you know, get this running on the Jetson? And, you know, I said basically what I said was we need some time, but we can do it relatively quickly if push comes to shove. Those were the highlights of the conversation.

### **00:16:07** {#00:16:07}

**Geoff Horowitz:** Um, happy to answer any additional questions. uh otherwise project can take it away.

**Pratyaksh Singh:** What did what did she think about the synthetic data generation that we shared

**Geoff Horowitz:** She she was really happy with it.

**Pratyaksh Singh:** the like the last to the procedural generation one the last examples which we did for UXO

**Geoff Horowitz:** She uh so she didn't have a I I asked her if she had any kind of specific feedback. She said she said let me show you what I was showing. Um so this was kind of the first you most true to life, right? The cut and paste. She was kind of pretty impressed by this. Um, showed her a few examples there. Then I showed her the more procedural generation. I talked about how, you know, this this this gives us a a more kind of generalized view.

**Pratyaksh Singh:** Mhm.

**Geoff Horowitz:** Uh, gives the model a little more freedom. I showed her kind of apples to apples here. Um, she also thought that this was pretty impressive, pretty cool.

### **00:17:18**

**Geoff Horowitz:** She she was she was just she didn't have specific feedback about if this was better, if this was worse. What she said was, "I do see how the more we get down this road of um you know, looking less like the real example that uh it could produce more false positives." That's how we got into the false positive conversation. Did that make sense project?

**Pratyaksh Singh:** It does. It did. It

**Geoff Horowitz:** Yeah. Um I also this was also the place where I caveed like look if you can get us more data

**Pratyaksh Singh:** did.

**Geoff Horowitz:** we can generate more in distribution samples. Uh and that's where the that's where the data set conversation came

**Pratyaksh Singh:** Mhm.

**Geoff Horowitz:** up.

**Pratyaksh Singh:** I mean if they have problem sharing data because of client restrictions even if she can share the objects like how does the object look right just stop that out share that wherever they are marked that would be good too but again that's something not in our

**Geoff Horowitz:** Yeah, I I I am happy to push more.

### **00:18:37** {#00:18:37}

**Geoff Horowitz:** Uh it's not a problem to push more, but that's that's what she said when I asked her is basically like right now she can't share any additional data, but she will ask, she'll keep us updated, and if she gets more, she'll share it.

**Pratyaksh Singh:** What All right. Okay. Uh, I'll share my screen. Can you guys see my screen?

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** Hello.

**Geoff Horowitz:** Yeah.

**Pratyaksh Singh:** Okay. Can you see this

**Geoff Horowitz:** Yes.

**Pratyaksh Singh:** talk?

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** Uh so this is what I wanted to bring up like you know this is something that thought was a problem but we didn't discuss a lot in our initial train test split but like they gave us a lot of files the number of files are are huge but most of these files are just duplicated right it's the it's

**Hemanth Sarabu:** Mhm.

**Pratyaksh Singh:** the same thing I mean you here I think 10 or 15 files are just of the same location. So that doesn't give us a lot of information and it makes it easier for the model to overfitit and even with like you know very extensive augmentation still the model is overfitting and I think we are at limit of augmentation because you know copying pasting object and all these things.

### **00:20:41** {#00:20:41}

**Pratyaksh Singh:** I think the it has enabled the model to just learn the object,

**Hemanth Sarabu:** Mhm.

**Pratyaksh Singh:** right? There's so many objects that you can copy paste from and this goes for all the data set like this is for I think okay so this is another data set the DRN one I think same is here also number of files is no but uh it is mostly repeated uh same goes for port also port of high school and VW also I think there are more unique locations but you a lot of the data is repeated. So that's one problem. Another thing that I've seen is that the model usually performs much better on the VW data set compared to other data set. Like this is just qualitative assessment. And I was just looking at the predictions and this is what I saw that you know model usually performs much better on the VW data set and this can be due to you know unique locations of VW or or you know it's because the number of files here are are a lot to summarize the model performance there has been some improvement on the model like you know uh there there were some objects that were being missed previously which we are able to detect

### **00:22:10**

**Hemanth Sarabu:** in in what?

**Pratyaksh Singh:** now but uh there are these but I think Mhm.

**Hemanth Sarabu:** Compared to what? Compared to what?

**Pratyaksh Singh:** compared to what we discussed on discussed on the previous meeting.

**Hemanth Sarabu:** Um, sorry. Can you can you define the baseline? What is the baseline?

**Pratyaksh Singh:** All right. Uh

**Hemanth Sarabu:** I mean like just in words,

**Pratyaksh Singh:** okay.

**Hemanth Sarabu:** are you saying we are able to detect a few more compared to the model that was doing what?

**Pratyaksh Singh:** Yeah,

**Hemanth Sarabu:** XYZ

**Pratyaksh Singh:** we are able to detect few more UXOs compared to compared to what what we were doing. And for the UXOs that we are missing, I have seen that you know in different orientations we are getting some part of that

**Hemanth Sarabu:** Actually,

**Pratyaksh Singh:** UXOS.

**Hemanth Sarabu:** where we left off was you you were looking into whether being close to the border was

**Pratyaksh Singh:** And

**Hemanth Sarabu:** affecting things.

**Pratyaksh Singh:** yeah, so to sum to to conclude that conversation,

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** Sachin tried out you know not having that on the border and still the model missed it.

### **00:23:14**

**Hemanth Sarabu:** Mhm.

**Pratyaksh Singh:** I confirmed the augmentation. The augmentation was putting things nearby the border

**Hemanth Sarabu:** Mhm. I

**Pratyaksh Singh:** also. So

**Geoff Horowitz:** part.

**Hemanth Sarabu:** see.

**Geoff Horowitz:** If we got if we got actual

**Pratyaksh Singh:** Uh-huh.

**Geoff Horowitz:** images of the UXO outside of water, right?

**Pratyaksh Singh:** Mhm.

**Geoff Horowitz:** Um, so, so what I I'm kind of thinking out loud here, but I'm interested in your perspective. If we got images of these outside of the water, so then we have images of these outside of the water and we have images of these inside the water. So then we can kind of maybe make some assumptions about how these UXOs end up looking when they're in the seabed.

**Pratyaksh Singh:** I'm good.

**Geoff Horowitz:** Um then maybe we could we could try to like the only word I can think of is like interpolate. We can try to kind of interpolate different views. Maybe there's more sand cover, maybe there's less sand cover. Things like that.

**Pratyaksh Singh:** Mhm.

**Geoff Horowitz:** Would that be helpful?

### **00:24:24**

**Pratyaksh Singh:** I get what you're saying. There is actually a paper that I read on it where what the author did

**Geoff Horowitz:** Mhm.

**Pratyaksh Singh:** was they put different object on the C bit. They put different object on the seaweed and then they simulated moving a moving a sonar inside water and then get data from there get data from there to train their model. I can I think I will try to get I'll try to get that paper but yeah something that uh they didn't share the code but something something like this is doable but

**Geoff Horowitz:** Mhm.

**Pratyaksh Singh:** again I think there will be a gap between synthetic and real world data but we

**Geoff Horowitz:** Mhm.

**Pratyaksh Singh:** can explore something like this. So I think their work was mostly for aircraft detection. So they put part of aircraft shipwrecks and all these things in the seabed on the seabed and then they then they simulated the whole sonar and then try to get the sides scan sonar data. So something like this is scalable and is good but again uh I mean I mean like bedrock sides scan data doesn't even resemble the open open source sides scan data that we got.

### **00:25:42** {#00:25:42}

**Geoff Horowitz:** Now,

**Pratyaksh Singh:** So Mhm.

**Hemanth Sarabu:** Okay. Is it possible? So we have all this data, right? Um and we have the XTFS.

**Pratyaksh Singh:** Uh-huh.

**Hemanth Sarabu:** What if we ask an agent basically say hey I have the XTFs which have the trajectories the points the raw MAC data we may even

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** have the depth and altitude and things like that.

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** So what if we say hey you you cannot access the returns. So basically you're asking it, hey agent, you need to build me a I will give you an XTF but there's a trajectory inside you may have a sense of the object on the floor some way to characterize the object on the floor but you don't actually have the side scan returns the intensities figure out

**Pratyaksh Singh:** Okay.

**Hemanth Sarabu:** like a physics pipeline so that you can return the intensities a physics so it can't be learned. It has to be like a physics model. So it's like a simul basically asking it to figure out a simulation and the way it might it

### **00:26:57**

**Pratyaksh Singh:** Uhoh.

**Hemanth Sarabu:** might uh it should be able to do it is agents are good at hill climbing right there is a ground truth which is your ground truth uh mag values or your ground

**Pratyaksh Singh:** Uhhuh.

**Hemanth Sarabu:** truth raster. It needs to match that. But the the way it matches that is not using a machine like a machine learning model. It has to come up with a physics simulator.

**Pratyaksh Singh:** Yeah. Try,

**Hemanth Sarabu:** Um I I think there are some holes in this idea but I think it is

**Pratyaksh Singh:** right? Uh-huh.

**Hemanth Sarabu:** a valuable thing to do because we actually have decent amount of data. You know what I mean? Like so yeah. So it can do things like oh let me introduce uh I don't know maybe it'll come up. So I mean you have to give it enough information like there are sand ripples in these areas right otherwise it won't be able to actually model model that it won't be able to get a physic it it is

### **00:27:59** {#00:27:59}

**Pratyaksh Singh:** Hey.

**Hemanth Sarabu:** blind to it. So I think there's something there. And if we can get it to figure out this physics model to go from trajectories, objects to renders, maybe we can start modifying that a little

**Pratyaksh Singh:** Got it.

**Hemanth Sarabu:** bit.

**Pratyaksh Singh:** So let me let me uh let me repeat it so that I understand it correctly. So what you are basically saying is that we give the model the raw XTF or the return from the sides scan data, right? And we ask it to build a physics engine that can

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** simulate sona like that.

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** Right.

**Hemanth Sarabu:** Yeah. Yeah.

**Pratyaksh Singh:** All

**Hemanth Sarabu:** I mean,

**Pratyaksh Singh:** right.

**Hemanth Sarabu:** let me see if I can um let's take I don't know if you're familiar with autonomous driving, right?

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** So autonomous driving has this problem like they they they do things like this. I think I think it's called real to sim and it's interesting for one robot too. It's called real to sim.

### **00:29:09**

**Hemanth Sarabu:** So basically you have this real data. How do you reconstruct that in simulation? And there are different levels of fidelity right and gausian splatting which you know you looked into is like is a is a is a very photorealistic but physics very poor physics model right. Um so so I'll give you the autonomous driving example. In autonomous driving you will be driving a car. You'll have LAR. You'll have images coming in.

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** Um so you actually at the end you have these um People will actually sit and they will extract very carefully the trajectories like how did the car actually move and they will reconstruct the they'll reconstruct the the meshes and stuff for the for the for the scene for the map. Basically they'll build a map and now um the inputs to

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** the camera are are images so renders right? So renders. So then they will say, okay,

**Pratyaksh Singh:** Okay.

**Hemanth Sarabu:** they already have a render for the trajectory the car actually took.

### **00:30:21**

**Hemanth Sarabu:** But what if it went right a little bit, what if it went left a little bit, right? So the things that will stay constant are the map.

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** The map stays constant. Lighting conditions stay constant. The trajectory gets moved a little bit. And the goal of the physics, the the simulation should be okay.

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** Now these are things that are constant. Objects are where they are. other vehicles are where they are. The buildings are where they are, but I move differently. So, what should be my images? So, the the simulation engine should be able to uh generate uh the I don't know like it depends on what representation the radiance fields, the rays or just directly the renders, raers, whatever, right? It should be able to generate that. You get what I mean?

**Pratyaksh Singh:** I get what you

**Hemanth Sarabu:** So there are things that are there are yeah so there is the physics model and then

**Pratyaksh Singh:** mean.

**Hemanth Sarabu:** there are the inputs to the physics model.

### **00:31:17**

**Hemanth Sarabu:** The inputs to the physics model are the kind of the description of the scene. Oh the there the the object is here. Right? The object is shaped like this.

**Pratyaksh Singh:** Amen.

**Hemanth Sarabu:** It's oriented like this. The depth is like this. Right? And then the the simulation engine should basically be able to run the trajectory of the of the sonar and then somehow figure out how to render those images.

**Pratyaksh Singh:** Got it.

**Hemanth Sarabu:** Does that help? And I think this is actually difficult but it's it's very interesting I think because people have been trying to do s\*\*\* like this for a long time. Um it's very kind of manual. They will like read papers. They will tune parameters. Um but now agents can potentially do that.

**Pratyaksh Singh:** Got it. I'll see if you have some starting point. Let me know.

**Hemanth Sarabu:** I I I that's a good question. I actually do not.

**Pratyaksh Singh:** Okay, you have to find something and then I will see if I can search something.

### **00:32:20**

**Hemanth Sarabu:** Um

**Pratyaksh Singh:** I think the DreamX wallpaper that you shared with me that also had

**Hemanth Sarabu:** H yes I think they were doing agentic building of environments

**Pratyaksh Singh:** this trajectory control.

**Hemanth Sarabu:** right?

**Pratyaksh Singh:** Yeah. Yeah. Yeah.

**Hemanth Sarabu:** Yeah. So something something like that.

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** So, for this, I would actually talk to an agent and you can uh we can talk more. Like I'm curious what it would look like if you describe this problem to cloud or anti-gravity and describe how you want to use it and it'll come up with some ideas as to

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** how to solve it. That could be an interesting place to start.

**Pratyaksh Singh:** Yeah. All right. I will I will look into this. I'll look into this

**Hemanth Sarabu:** Okay, by the way, this is I think this is interesting,

**Pratyaksh Singh:** because yeah high risk high reward

**Hemanth Sarabu:** but I I think it's like a high-risisk high reward kind of thing.

**Pratyaksh Singh:** I get it because one more reason is that if pressure is going to be on this uh like low data region with sensors and all these things selected from sensor I think sim to real sorry real to sim will be something that

### **00:33:32** {#00:33:32}

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** that could be good. Anyways,

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** uh one more thing I wanted to say is that

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** I think the validation set is the validation set is for our model it is very small like these procedural generation I tried these augmentation out in a model and they didn't improve performance at all because you know the three or four object that our model was missing it didn't look anything like the procedural generation that we tried out. So one of the thing that I have been thinking is

**Hemanth Sarabu:** I think I think I think that's why you should do care

**Pratyaksh Singh:** yeah but again for kfold I think we'll have to

**Hemanth Sarabu:** Oh,

**Pratyaksh Singh:** uh I so I showed you this right is my screen is still visible

**Hemanth Sarabu:** yeah.

**Pratyaksh Singh:** so if we do it without any overlap I think this time we split the

**Geoff Horowitz:** Yeah.

**Pratyaksh Singh:** data in such a way that more of the data is in training but when you go to K4 fold. I think a lot of it will go to maybe validation.

### **00:34:48**

**Geoff Horowitz:** Heat.

**Pratyaksh Singh:** But yeah, I think that's the last thing we have to try out.

**Hemanth Sarabu:** Okay. So,

**Pratyaksh Singh:** So we we can try it

**Hemanth Sarabu:** so wait. Um,

**Pratyaksh Singh:** out.

**Hemanth Sarabu:** okay. There is one problem here. I think the only pro the problem here is that we don't have a lot of unique geog geographically unique data. Right? That is the problem.

**Pratyaksh Singh:** Yeah. Yeah.

**Hemanth Sarabu:** But how you split the training and validation should be basically uh based on latl long bounding boxes.

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** So the fact that these are all overlapping should not matter like you get what I

**Pratyaksh Singh:** Yeah, I get what you mean,

**Hemanth Sarabu:** mean.

**Pratyaksh Singh:** but uh so I think we we should try it out. It there's nothing wrong with it, but I'm just thinking of the issues that can come up like you

**Hemanth Sarabu:** Okay,

**Pratyaksh Singh:** know

**Hemanth Sarabu:** the problem is still that the problem is still that yes, our data set is so small that when you do train valid validation is very send.

### **00:35:48**

**Hemanth Sarabu:** I I agree. I would if I were in your position, I would there's only a couple of things you can if you don't if you're stuck with this much real data and your customer

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** is not giving you more real data. We either invent new data which is kind of what we were discussing, get open source data which we may have exhausted or the third thing is um you know cross validation

**Pratyaksh Singh:** And

**Hemanth Sarabu:** because then you basically get you're able to you're able to simulate many train val pairs train vals and so

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** you the way that will help you is you may get a more statistically significant result. That's all. I'm not saying you actually get more data.

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** You just get a more statistically uh you know dependable result about is my model

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** improving or not because your validation set is single

**Pratyaksh Singh:** Got it. Yeah, I get your point.

**Hemanth Sarabu:** digits.

**Pratyaksh Singh:** I get your point. Like, so yeah, I think we'll have to do all three maybe because Kfold cross validation I think we'll have to do before we deliver the final model just to know that which model is performing good.

### **00:37:03** {#00:37:03}

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** One thing that I was thinking of is that have all the real data maybe as validation and then uh you know use synthetic data as

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** training and uh

**Hemanth Sarabu:** Yeah. I think that's an interesting idea.

**Pratyaksh Singh:** Rul has been working on this. So I'll I'll give it to Rul. What we did was we started with fine-tuning vision model with Lora to generate just the objects. So we divided the UXOs's into multiple categories and with each

**Hemanth Sarabu:** Wait, wait, wait. When you say vision model, this is a diffusion,

**Pratyaksh Singh:** category yeah flux turbo these

**Hemanth Sarabu:** generator model. Nice.

**Pratyaksh Singh:** models diffuser models right so the idea is

**Hemanth Sarabu:** Nice. Nice. Okay.

**Pratyaksh Singh:** that to break uh these UXOs into multiple different categories of object and then uh like you know for each of them you train a model to generate examples like So he has some results for it. And I was thinking uh and I think his results are good.

### **00:38:08** {#00:38:08}

**Pratyaksh Singh:** He can show it to them or he can show it to you all. But I was thinking to extend it to generate the backgrounds too and then train entirely on synthetic data. See what happens entirely on open source and synthetic data and see what happens.

**Hemanth Sarabu:** Hold

**Pratyaksh Singh:** Can you take

**Hemanth Sarabu:** on.

**Ratul Shashank:** Yeah.

**Pratyaksh Singh:** over?

**Ratul Shashank:** Uh let me show share my screen. So So is my screen visible?

**Pratyaksh Singh:** Yes, it

**Ratul Shashank:** Uh so as mentioned that we took uh we

**Pratyaksh Singh:** is.

**Ratul Shashank:** uh we took two classes a UXO and AOI small black and we divided them into three

**Pratyaksh Singh:** Hey guys,

**Ratul Shashank:** categories.

**Pratyaksh Singh:** sorry. Sorry to cut you off but yesterday we looked into UXO and AI small

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** black and we came to the conclusion that there is no distinction there is no visual distinction between UXO and AI small black. So we are kind of treating them as one

**Hemanth Sarabu:** Okay. Yeah, I think that makes sense for a machine learning engineer.

### **00:39:26**

**Pratyaksh Singh:** object.

**Hemanth Sarabu:** We should tell Bridget that we're doing that. and basically ask Bridget, Bridget, if they look the same, how are you guys able to tell them apart? Maybe the answer is mag or maybe the answer is we actually already knew that there's a there's a mine here, the UXO

**Pratyaksh Singh:** Got

**Hemanth Sarabu:** here.

**Geoff Horowitz:** or I'll I'll add something else to that which is

**Pratyaksh Singh:** it.

**Geoff Horowitz:** that when we on the output we need to be able to distinguish between the two, right? Like we don't want to show if we're presenting an example of this, we don't want to accidentally present an example of a UXO that's not a UXO. Do you follow that?

**Pratyaksh Singh:** uh presenting an example. So like

**Hemanth Sarabu:** I don't follow that.

**Pratyaksh Singh:** Bridget

**Geoff Horowitz:** Okay. Um, okay. Let me let me show you this. Is Wall-E down? No.

**Hemanth Sarabu:** Is

**Pratyaksh Singh:** No, I think it's up.

**Geoff Horowitz:** Hold on.

**Pratyaksh Singh:** But uh we will have to rerun the application, I think.

### **00:40:52**

**Geoff Horowitz:** Uh, my stream app isn't working.

**Pratyaksh Singh:** Yeah, we'll have to restart it.

**Geoff Horowitz:** My eating volume. Oh. Oh. Oh. You have to restart. Okay. Sergeant. Well, whatever. Um, okay. My point is is that like I This is a little bit of a nuance thing. I I don't want to um I don't want to put them all into the same category. I want them to be separate categories so that we know which ones are UXOs and which ones are not UXOs. That's the point I'm getting at.

**Pratyaksh Singh:** got it.

**Geoff Horowitz:** Is that more clear? And is that

**Pratyaksh Singh:** So, so you want us to internally also maintain performance on UXO and then

**Geoff Horowitz:** possible?

**Pratyaksh Singh:** the probable UXO that we are calling UI small black right like you don't want us to treat it I mean like we can train the model on it together but we treat it as separate classes during evaluation or during presenting. Is that what you

### **00:42:01**

**Geoff Horowitz:** certainly during presenting.

**Pratyaksh Singh:** mean?

**Geoff Horowitz:** I'm trying to think through if it's important to separate them during evaluation. Um I think if it doesn't hurt the workflow too much then yes it would be good to to have those in a separate evaluation bucket. Uh and the reason is go

**Pratyaksh Singh:** Yeah. I was saying we keep it like that.

**Geoff Horowitz:** ahead.

**Pratyaksh Singh:** They are in separate bucket but for training we treat them as same but when

**Geoff Horowitz:** Ah, okay.

**Pratyaksh Singh:** we

**Geoff Horowitz:** Then we're aligned.

**Hemanth Sarabu:** But um okay I

**Geoff Horowitz:** Yeah.

**Hemanth Sarabu:** so if the reason we are clubbing them is because they're visually the same and we don't have enough examples of UXOS then I think that by construction that means our UXO performance is not great anyway which is so how do you actually when you're presenting your validation uh don't you think there will be a ton of confusion between UXO and uh AI Small black

**Geoff Horowitz:** Hammoth, I think there's there's two things that come to my mind here.

**Hemanth Sarabu:** curve.

### **00:43:45**

**Geoff Horowitz:** Number one is that number one is a recall question, right? If we're calling this a UXO, sorry, if this is actually a UXO, are we categorizing this correctly as a UXO? That's that's number one, right?

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** Okay. And and that might get diluted if we grouped them

**Hemanth Sarabu:** I don't I I don't think so.

**Geoff Horowitz:** together.

**Hemanth Sarabu:** The reason I don't think that is because, brother, correct me if I'm wrong, because we don't have enough UXO and the UXO and the other class look similar. By combining them and letting the model treat them the same way, we would be on net improving the recall of UXO.

**Pratyaksh Singh:** Yeah, that is true. So the thing is that during training we treat them as

**Geoff Horowitz:** Um,

**Pratyaksh Singh:** same during performance like during validation While deciding the model they are treated same but when we present it into the meeting we have them as different classes like I can present you the number on the number of missed UXO and number of missed AI small black so false negative on both the classes does it make sense

### **00:45:11**

**Hemanth Sarabu:** Hey, I want to ask a question. Are AOI small blacks present in the same data set as UXO or do they come okay and they're

**Pratyaksh Singh:** Yes.

**Hemanth Sarabu:** visually indistinguishable?

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** If they're visually indistinguishable, what is the We should be basically telling them, guys, visually these are the same. I can give you the metrics, but the metrics are unreliable, right?

**Pratyaksh Singh:** Yeah, I mean we can't do that one thing.

**Hemanth Sarabu:** Uh let's take a extreme example. There there are there are blue cars that have uh one of some of them have AC and some that don't

**Pratyaksh Singh:** Uh

**Hemanth Sarabu:** have AC. And we are saying uh from a bird's eye view we're distinguishing both these cars right and the and they look the same and because they look the same we are treating them the same in training but we're saying we will um report the the performance as two separate classes you know you know what I mean like we should if we think they're visually the same we should go and tell them they're visually the same Um, that's where my concern is coming

### **00:46:29**

**Pratyaksh Singh:** Got it.

**Geoff Horowitz:** I have on there's sorry there's there's one other there's one other thing

**Pratyaksh Singh:** I

**Hemanth Sarabu:** from.

**Geoff Horowitz:** here I I understand that I I don't want to jump too fast but there's another consideration which is it would be really really really embarrassing for us if we're presenting to Bridget and We say, "Hey, this is a UXO." And actually, this is not an example of a UXO. This is something else.

**Hemanth Sarabu:** I don't I don't understand what you mean by that. How um you mean just confusion?

**Geoff Horowitz:** Okay.

**Hemanth Sarabu:** You're talking purely about confusion like we we messed up or the model messed up. Which what level of what level of error are you talking

**Geoff Horowitz:** Yeah. That that we are we're we're referencing a UXO,

**Hemanth Sarabu:** about?

**Geoff Horowitz:** one of the 11 UXOs that that we're saying,

**Hemanth Sarabu:** Uhhuh.

**Geoff Horowitz:** oh, this, you know, hey, we want to show you this. This is a UXO, but it's not actually a UXO. That would be embarrassing for us.

### **00:47:33**

**Geoff Horowitz:** Is that clear or

**Hemanth Sarabu:** No, no, it would not. I mean,

**Geoff Horowitz:** no?

**Hemanth Sarabu:** we need to decide if recall is more important than precision or not. If recall is more important than precision, we are going to make those mistakes.

**Geoff Horowitz:** I I don't mean the model. I mean us when we're talking about it.

**Hemanth Sarabu:** You're saying we just need to be aware of which ones are true UXOs as humans, not the model.

**Geoff Horowitz:** Yes,

**Hemanth Sarabu:** Okay,

**Geoff Horowitz:** exactly.

**Hemanth Sarabu:** I think I understand what you're saying now.

**Geoff Horowitz:** Okay.

**Hemanth Sarabu:** Okay, that's fine.

**Geoff Horowitz:** Okay. That that was my second point is is I don't want to I don't want to get rid of the UXO class, right? I don't want to merge them permanently. I I want it to be I want us to be able to um extract let's say that we got 20 examples that were in this UXO plus AOI small black class, right? I want to know of those 20 examples which 11 are actual

### **00:48:33** {#00:48:33}

**Hemanth Sarabu:** Okay,

**Geoff Horowitz:** UXOs.

**Hemanth Sarabu:** so this is not an ML model mistake. These are silly human mistakes.

**Geoff Horowitz:** Yeah, we could call it that. just just for presenting to Bedrock. Is that more clear or are you still confused by what I was

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** Hey, I think it's clear but I wanted to know we were me and Sachin were discussing will it be possible to do

**Geoff Horowitz:** saying?

**Pratyaksh Singh:** something like what we did in the first term where we shared them our labels and asked them to verify.

**Geoff Horowitz:** Yes, we can do that. I just don't know if they will turn that around to us in time.

**Pratyaksh Singh:** What if we uh like dduplicate the data? It will be like six or seven files, 10 files for each data

**Geoff Horowitz:** Uh yeah,

**Pratyaksh Singh:** set.

**Geoff Horowitz:** I we project we can definitely ask we can ask anything we want to. Um,

**Pratyaksh Singh:** Uh-huh.

**Geoff Horowitz:** I just I I just can't guarantee that they will look at it and return it to us in

### **00:49:39**

**Pratyaksh Singh:** Understood.

**Geoff Horowitz:** time.

**Pratyaksh Singh:** Because I think when me and Sashin were discussing one thing that came out is that you know it's not just about training the model a lot of time we have to fix the data because we actually don't know what correct is

**Geoff Horowitz:** Yeah.

**Pratyaksh Singh:** and what is incorrect.

**Geoff Horowitz:** Um, I would also give I would give Yes.

**Pratyaksh Singh:** So

**Geoff Horowitz:** The answer is yes. Let's prepare it and let's give shape files. Um, let's give shape files that give them the lat long because they may,

**Pratyaksh Singh:** hey,

**Geoff Horowitz:** you know, they may also look at the mag data or something to verify

**Pratyaksh Singh:** Okay, but I would like to look at I would like them to look at the images because you know that's what we're training the model for at least at this for this milestone.

**Geoff Horowitz:** Yep.

**Pratyaksh Singh:** But I think we can.

**Geoff Horowitz:** We can ask or or f I mean we can just give them the images. They might come back and ask for the latl long.

### **00:50:46**

**Geoff Horowitz:** in which case we can generate that.

**Pratyaksh Singh:** Art.

**Geoff Horowitz:** I'm okay with either

**Hemanth Sarabu:** We give them images.

**Geoff Horowitz:** approach.

**Hemanth Sarabu:** Hey project, what if we give them images of AOI black and UXO in the same data set and we ask them to classify them?

**Pratyaksh Singh:** Yeah, that that's what my thought was like whatever we think is UXO AI black UXO anything we just label it and then we give it to them and ask them like what is right or and what is wrong which annotations are wrong and they can

**Hemanth Sarabu:** I see. I see.

**Pratyaksh Singh:** be they can tell us like you know they can correct us

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** that you know these are these are not UXOs because of this and this shape or because of this and this reason and then we can remove it from the whole data. All

**Hemanth Sarabu:** Yeah, let's do it.

**Pratyaksh Singh:** right.

**Hemanth Sarabu:** But Jeff,

**Ratul Shashank:** All

**Hemanth Sarabu:** do you I I think we should do this.

**Ratul Shashank:** right.

**Hemanth Sarabu:** We'll have to figure out how this jives with what I'm about to say, which is uh I think we should let Bridget know that those two are visually indistinguishable and ask them basically is that does that align

### **00:52:12**

**Geoff Horowitz:** I agree with you.

**Hemanth Sarabu:** with your understanding

**Geoff Horowitz:** I I I agree with you. I mean this is the same problem we had for the first statement of work which is they might be categorizing based on additional information right they might be categorizing based on the the the

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** elevation map they might be categorizing based on the um the mag data

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** like so so you know so so I

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** I agree with you um that especially for training it makes sense for us to group all these

**Hemanth Sarabu:** Yeah. Okay. Um I do have to drop I got I got a few calls starting soon. Um Rul, I know I know you're you're probably going to dig into this with the elders, but um would you be able to give us a highlight the highlights? What are the highlights?

**Ratul Shashank:** Uh so long story short, Lux is working phenomenal in UXO generation.

**Hemanth Sarabu:** Phenomenal. Okay.

**Ratul Shashank:** Yeah, I mean it's

**Hemanth Sarabu:** I don't think I've heard that in our team before.

### **00:53:31** {#00:53:31}

**Ratul Shashank:** uh because I I will share a contact sheet where one column is of Z image and one image one column is of flux Z image even though it's worked good but some uh artifacts it is uh it is creating uh some artificial artifacts like for example it would create uphill like structure or some kind of that so flux is not having that problem and uh uh I personally I found if if we generate two seed per images it's much better because in some cases it is

**Hemanth Sarabu:** Okay. Okay. Wait, wait, wait. Let's go back to flux is phenomenal because it is doing what?

**Ratul Shashank:** Uh flux is phenomenal because it is replicating the original uh image much better.

**Hemanth Sarabu:** Okay. And what are the control variables?

**Ratul Shashank:** uh condition variables as

**Hemanth Sarabu:** The condition variables.

**Ratul Shashank:** in

**Hemanth Sarabu:** How do you uh uh condition the

**Ratul Shashank:** uh so I have uh I I've first categorized them along uh

**Hemanth Sarabu:** generation?

**Ratul Shashank:** their uh elongation and I have trained uh lora models on separate classes.

### **00:54:58**

**Ratul Shashank:** So like I have three class elongated, round and uh moderate.

**Hemanth Sarabu:** I

**Ratul Shashank:** Uh this is basically just I just take the the length

**Hemanth Sarabu:** see.

**Ratul Shashank:** of this particular object and I categorize them. If this is below this level then it's elongated. If this is above this then it's round and just train a lower model on that. And that is basically the entire workflow and Lux is

**Hemanth Sarabu:** Okay.

**Ratul Shashank:** handling the

**Hemanth Sarabu:** So,

**Ratul Shashank:** rest.

**Hemanth Sarabu:** and you're able to create out of uh distribution images that look plausible.

**Ratul Shashank:** Yeah.

**Hemanth Sarabu:** Awesome. Can you can you show us a couple of

**Ratul Shashank:** Yeah. I mean these are all the the left most column will be real

**Hemanth Sarabu:** examples?

**Ratul Shashank:** objects and the right two columns are se uh seed generations using flux. Uh you can see in some cases it needs uh multiple seed operations like in in this case it's

**Hemanth Sarabu:** Right.

**Ratul Shashank:** better if we consider multi

**Hemanth Sarabu:** So, wait, wait, wait.

### **00:56:10**

**Hemanth Sarabu:** So, you have this you have this ground truth. You do you send the image to the left or no?

**Ratul Shashank:** Uh no I I what uh at in this example what I'm just doing is I'm just create I'm just sending the entire batch and asking it to generate for two seed images. Uh nothing

**Hemanth Sarabu:** Okay. So,

**Ratul Shashank:** else.

**Hemanth Sarabu:** what what you send in an image and I'm guessing that out comes an image that looks different along some dimensions, right? What what are those dimensions that are different?

**Ratul Shashank:** Yeah. Uh so you are asking in terms of seed generation, right? like different seed

**Hemanth Sarabu:** Not. Um,

**Ratul Shashank:** images.

**Hemanth Sarabu:** so your inputs to the model are is a is a seed image plus these uh geometry parameters.

**Ratul Shashank:** So uh I first tested for the various D noiseis levels and the model strength like I'm doing this on comfy UI so it is much

**Hemanth Sarabu:** Okay. Okay. Wait, wait, wait. So the question is,

### **00:57:20**

**Ratul Shashank:** easier

**Hemanth Sarabu:** how do you control what is being generated?

**Ratul Shashank:** uh at this present moment the control is basically in D noise level and the model strength I can also show you

**Hemanth Sarabu:** Okay.

**Ratul Shashank:** uh example I if you have

**Hemanth Sarabu:** Wait, wait, wait, wait, wait, wait, wait. Let's go back. Hold on.

**Ratul Shashank:** time.

**Hemanth Sarabu:** You're So you can only control this um when I say controlling the model. So in generative models, controllability or conditioning.

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** Um okay, so let's take a simple example. If you tell a model, hey, I want a banana, I want an apple, right? That is conditioned on text or it is text controlled. Okay. And then you you can say,

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** hey, I have this picture. Put a banana in it. That is an I I plus I plus T to I. That's image and text to image generative model. And it is conditioned on the reference image.

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** And it's it's also conditioned on the text you send.

### **00:58:26** {#00:58:26}

**Hemanth Sarabu:** And then you can also have hey,

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** I got this reference image. Put a banana in this bounding box. Now there are three control variables um or condition variables.

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** reference image banana the thing that is being put bounding box which is where you're putting it. So similarly what are the control variables for the model you have here?

**Ratul Shashank:** In this case the uh one would be image uh another would be the labels that I'm giving it. So the co the labels include the coco annotations and so coco to specify cocoa annotation will just help in creating the bounding box. Uh and another is just model parameters like d noise and

**Hemanth Sarabu:** Uhoh.

**Ratul Shashank:** uh model strength.

**Hemanth Sarabu:** Okay.

**Ratul Shashank:** So, so I I I would first give I I would first train a safe tensor using all these data that I have and then I can ask it to generate for any particular um any particular example and it could and the these would be the results.

### **00:59:46**

**Ratul Shashank:** I can I can and also share the uh example like what different testing uh different parameters it was giving

**Hemanth Sarabu:** No, no. Okay.

**Ratul Shashank:** like

**Hemanth Sarabu:** I I I actually want to know just one thing which is we have this data

**Ratul Shashank:** Uh-huh.

**Hemanth Sarabu:** set of uh contacts. Now we want to generate things that look like that but are actually different. Are we able to do that?

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** And how do we control how we do it?

**Ratul Shashank:** Uh that is something that I I want to test because uh I I I want to like I have something in mind

**Hemanth Sarabu:** Okay.

**Ratul Shashank:** like uh so in this case if I if I create a binary image so I would get a some something like a mask right?

**Hemanth Sarabu:** Mhm.

**Ratul Shashank:** Uh if I try to maybe flip this so this bright side is on bottom and this shadow would be on top or try to like elongate this. Do you get what I'm saying?

**Hemanth Sarabu:** Right. I see.

### **01:01:02**

**Ratul Shashank:** So like it's something that No,

**Hemanth Sarabu:** So you don't have that

**Ratul Shashank:** I this is something that I want to test it out.

**Hemanth Sarabu:** yet.

**Ratul Shashank:** Uh I I want to test it out after I am I first I want to transplant this into the background and want to see how this how this would fit into the entire picture. So I can I would know what I'm dealing with here.

**Hemanth Sarabu:** Okay.

**Ratul Shashank:** Right.

**Hemanth Sarabu:** Okay. Sounds good. Hey, sorry, I really have to drop,

**Ratul Shashank:** So

**Hemanth Sarabu:** but um I will catch up with uh Jeff and uh get a better picture from what you guys discussed now. Okay, thanks Rol. Thanks,

**Ratul Shashank:** okay.

**Hemanth Sarabu:** guys.

**Ratul Shashank:** Yeah. So as I was saying this uh flux is working better. uh some uh one caveat which is not regarding the model but there are some examples where we have this black uh margin kind of in some cases it's it's near the native region in some cases it's near the gap that we are experiencing and the pain gap so that can be reduced by taking another example where we don't have that uh gap like this ping gap but I don't know how we can reduce this shadow sorry water water column region uh I don't know how we can reduce this we uh I

### **01:02:47** {#01:02:47}

**Pratyaksh Singh:** That That is fine.

**Ratul Shashank:** Uh

**Pratyaksh Singh:** Rul uh I think we wanted to just test this out. Actually, we want more diversity from in the image like it shouldn't look like the input image. It should be more diverse, right?

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** uh okay will it be possible for you to share a doc in the channel describing uh input to the model output what how many examples how you know how many examples that you trained the model with like number of data points that you trained it with right

**Ratul Shashank:** Yeah, I can do that.

**Pratyaksh Singh:** you

**Ratul Shashank:** Uh but uh I I I first want to uh like I want to uh what what my thought process is. I can share that right now but I want to test if this can give us more examples of like more novel example where it's not very similar

**Pratyaksh Singh:** Yeah. Yeah.

**Ratul Shashank:** so I first want to try try that and then I can give the entire picture I can

**Pratyaksh Singh:** Exactly. No.

### **01:03:55**

**Ratul Shashank:** share in the talk.

**Pratyaksh Singh:** Yeah. Share that off also and then also check in the code, right?

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** Uh I will create a GitHub repo. Uh put your code there for finetuning.

**Ratul Shashank:** Amy.

**Pratyaksh Singh:** I'll also go through that code, right? Because I want to see what's happening.

**Ratul Shashank:** Okay,

**Pratyaksh Singh:** Uh, and also like it would be even okay if you don't condition it on anything. I mean like you know just if it takes it if it takes a noisy image and then just generate any of the any of the UXOs like wide varieties of UXO that is also good for us right. So for example,

**Ratul Shashank:** we know

**Pratyaksh Singh:** you conditioned it on image, right? But when you conditioned it on image, it looks a lot like the input image that was given to it.

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** It looks like you know this it has just I mean uh it might have maybe just increased the size of the image because there it lacks in diversity right but

### **01:04:58**

**Ratul Shashank:** Yeah. So, so I I these generations are in because um but I get I get your point. I get your

**Pratyaksh Singh:** So check in the code I will go through it too and we found out that you know

**Ratul Shashank:** point.

**Pratyaksh Singh:** flux is working which is which is a good thing because I never thought any of the open source model would work on this on fine tuning right so that is that is very good so whatever config or whatever things that you did to config UI if you can just upload it on GitHub or

**Ratul Shashank:** Anyway,

**Pratyaksh Singh:** anywhere else or if you have if you have the code on Wally if you can just share the location of it also I'll go through it and then I can I can suggest you I can suggest you you know any improvement An improvement is

**Ratul Shashank:** Yeah, I can I can share that with

**Geoff Horowitz:** Wait, wait, wait a second. Protect, I'm gonna I'm gonna push back on you for one second,

**Pratyaksh Singh:** good.

**Ratul Shashank:** you.

**Geoff Horowitz:** Rul.

### **01:05:57** {#01:05:57}

**Geoff Horowitz:** It should we should have a GitHub repo or at least a branch on an existing repo. All of our code should be backed up. Um, you know, at the end of the day, we never know quite what's going to happen to Wall-E, right? Wall-E might go down.

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** Wall-ally might get hacked. I mean, you know, anything could really happen. So, all of the code should be backed up on GitHub.

**Ratul Shashank:** Uh I think when I tried accessing GitHub when Sachin shared a code with me but it was not letting me access that. I don't I I don't know if that is solved but uh I will check and let you

**Geoff Horowitz:** I'll I'll

**Ratul Shashank:** know.

**Geoff Horowitz:** okay. Yeah, let me know. I can fix that if you run into trouble.

**Ratul Shashank:** Mhm. Uh and regarding the uh like if we feed any image like without fine-tuning a model. uh that would also generate decent example of that model but uh without oversimplific over uh simplification I uh like suppose if this is the model this is the source image right

### **01:07:21** {#01:07:21}

**Pratyaksh Singh:** Okay.

**Ratul Shashank:** uh it with with D noise 0.5. Uh you can see difference in the image. So I just wanted to know if this would work if these kind of novelty in the original image would work.

**Pratyaksh Singh:** Sachin, do they look like AOI black or UXOS? Yeah. So, this is good. This is something that we want, right? So, actually what I asked you uh actually what I wanted to do was

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** to go through any of these open source models or like open source, closed source, I don't care any of these model. give it one example, two or three examples and ask it to generate images similar to this, right?

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** Because I don't think we have enough data to fine-tune the model, right? Uh in your case, LoRa worked. But u I I didn't have we have enough I didn't think we have enough data to even do a Laura fine

**Ratul Shashank:** Maybe

**Pratyaksh Singh:** tune, but in your case, it worked. So that's why like I'm happy.

### **01:08:33** {#01:08:33}

**Pratyaksh Singh:** I want to look at look at how you know how many examples and how it worked. So, and it works. It's great. But one of the exploratory things that I wanted to do was so similar to similar to something like this like you give chat GP an image your image and you ask to generate similar image to this, you know, generate headshot of this, something like this, right? So, I wanted if you could if you could do something like this where you give it an image and then you ask it to generate similar images to this. You try out open source model, close source model, whatever, and you see if you can generate a lot of images. Let's say you find an open source model that 10% of the time generate good example. Then what we could do is we could ask our labelers to go through,000 5,000 examples and get us like 50 100 whatever like we we can just scale it up. We can ask our labelers to verify the image and then we can go from there.

### **01:09:30**

**Pratyaksh Singh:** Does it make sense?

**Ratul Shashank:** Yeah, it does. It does.

**Pratyaksh Singh:** If so if you have some time check in the code and then if you want to try something out set up a model training with it. So I think the next step was to have it generate novel examples right so in that case if you don't condition it on the image and just only condition it on the text and even not even on the text just you know just add some text which is which describes what you

**Ratul Shashank:** Oh

**Pratyaksh Singh:** want right so for example a sidesc a grayscale uh

**Ratul Shashank:** boy.

**Pratyaksh Singh:** there is a depression in ground and these kind of things and you train the and you fine-tune the model to generate any of the UXs you give 30 40 example fine tune your model see what happens right and parallelly without any fine-tuning you just do in context learning where you give the model some example and ask it to generate similar example to Nothing.

**Ratul Shashank:** Okay, I I I can I I will first try this with the existing Lora model.

### **01:10:33** {#01:10:33}

**Ratul Shashank:** if this if this can produce different things uh I will

**Pratyaksh Singh:** Mhm.

**Ratul Shashank:** uh I also want to ask like uh let's suppose let's suppose uh I transplant this generated uh UXO on a generated background and let's uh

**Pratyaksh Singh:** Mhm.

**Ratul Shashank:** suppose I rotate its orientation and Obviously if I am trans transplanting it then I would know its location.

**Pratyaksh Singh:** Mhm.

**Ratul Shashank:** it's where where I'm located that and I generate a synthetic uh annotation file for that and then I feed that into a new generation model or try to generate more examples of that uh of that new one a new example will that uh count as something useful I

**Pratyaksh Singh:** So what you are asking is that you take the image, you rotate it, translate it, scale it and do all these things and and you feed it to the generative model to to correct the image.

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** Is this what you're

**Ratul Shashank:** Mhm. uh not correct the image but but uh basically do what I'm

**Pratyaksh Singh:** asking

**Ratul Shashank:** doing right now um generate a generative image of from that

### **01:11:57**

**Pratyaksh Singh:** which is uh so what will be your final image?

**Ratul Shashank:** source.

**Pratyaksh Singh:** Will it be non-rotated non-scaled image or what will be your final image? So, so let's get two things clear, right? What will be the input to the model? What will be the output to the model? So, input to the model will be rotated image.

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** And what will be the output to the model? What do you want the model to

**Ratul Shashank:** Uh I want to see if I it the output would be the

**Pratyaksh Singh:** predict?

**Ratul Shashank:** rotated obviously. I wanted to see if passing these two gen uh layers of generation is in is bringing any changes to the original UXO original object. That was some that was what I had in mind.

**Pratyaksh Singh:** I'm sorry I didn't get it again like what just in layman term like just can you can you draw it out maybe what will be the input to

**Ratul Shashank:** Uh

**Pratyaksh Singh:** the model what will be the output what do you want the model to take as input and what do you want it to take as output can you draw it out so for example like Just take an excell and then you say I want to output something like

### **01:13:11**

**Ratul Shashank:** so let's suppose I am This

**Pratyaksh Singh:** this.

**Ratul Shashank:** is this is the the black rectangle is the background and this red rectangle red diamond is the

**Pratyaksh Singh:** Okay.

**Ratul Shashank:** uh what I have generated the generative object I

**Pratyaksh Singh:** Wait,

**Ratul Shashank:** feed this.

**Pratyaksh Singh:** what do you mean by generated? So,

**Ratul Shashank:** So this uh what I generated from

**Pratyaksh Singh:** so let me first summarize what we are discussing.

**Ratul Shashank:** plugs.

**Pratyaksh Singh:** Okay. Okay.

**Ratul Shashank:** Uh so uh I I I just wanted to uh know in summary I

**Pratyaksh Singh:** Okay.

**Ratul Shashank:** just wanted to know if I feed this through layers of generation like this uh I this then becomes the source image and then I generate another and then that another would become the image.

**Pratyaksh Singh:** What do you generate? What? What do you generate?

**Ratul Shashank:** I would generate this uh object.

**Pratyaksh Singh:** But you have already generated that object previously only,

**Ratul Shashank:** So yeah uh that's

**Pratyaksh Singh:** right?

**Ratul Shashank:** what that's what I wanted to find like if this is a generated object not a real object.

### **01:14:31** {#01:14:31}

**Ratul Shashank:** So if I generate uh another generated image of that

**Pratyaksh Singh:** Okay.

**Ratul Shashank:** generated image, so will that be of any uh so that that's just a a that's just a hypothesis. Uh that's I that's just a hypothesis or rather a training

**Pratyaksh Singh:** So on your train model you want to generate an object and then with that

**Ratul Shashank:** example.

**Pratyaksh Singh:** generate object you want to feed it to input and then generate again.

**Ratul Shashank:** Yeah.

**Pratyaksh Singh:** Is that what you want to do?

**Ratul Shashank:** Yeah.

**Pratyaksh Singh:** Try it out. Try it out. Let's see what happens because uh honestly I don't know what will happen because I've seen I've seen somewhere that you know people ask charg to generate the same image again and again and again and then it ends up and it ends up generating yeah it will change something subtly and

**Ratul Shashank:** changing the image. Yeah.

**Pratyaksh Singh:** then after a lot of iteration it just generates something random. So you can you can see I think this won't require a lot of your time right you have already have a train model so yeah you can generate

### **01:15:43**

**Ratul Shashank:** Yeah. So the logic was that would uh so the point is

**Pratyaksh Singh:** it

**Ratul Shashank:** we can hypothetically get much closer result but with slight novelty. Right? So I I will train the I will I will get

**Pratyaksh Singh:** yeah but I would I would rather if you're training the model I would rather have you you know go from scratch to an object because then like you know you force the model to generate a lot more. Do you get what I

**Ratul Shashank:** Yeah, I understand. I understand.

**Pratyaksh Singh:** mean?

**Ratul Shashank:** Okay, I will I will get back get back to you later. like I I have a few questions. I will ask them. I I will ask them separately because I need to test it out. Obvious uh I have a few doubts. I will clear create clear them and share the results.

**Pratyaksh Singh:** Can you uh will it be possible?

**Ratul Shashank:** Yeah.

**Pratyaksh Singh:** Just give me a minute. So yeah, I will suggest you know uh write a read me or create a doc and then check in the code.

### **01:17:24**

**Pratyaksh Singh:** I will I will go through it. I think it's amazing that flux is working right and I think we can if it's working we can do a lot from it. We can do a lot of things from it.

**Ratul Shashank:** Uh,

**Pratyaksh Singh:** Anyways, okay.

**Ratul Shashank:** so I have a doubt.

**Pratyaksh Singh:** So, let let me share my screen. Can I share my screen?

**Ratul Shashank:** Okay. Okay. Yeah.

**Pratyaksh Singh:** So, I wanted to see if we can do something like this, right? Let me know when my screen is visible. Is it?

**Ratul Shashank:** Yeah, it's a

**Pratyaksh Singh:** So see I gave it an example right?

**Ratul Shashank:** bit

**Pratyaksh Singh:** Can you see the chat GPT?

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** Right. Uh I gave it an example. I just asked it to generate 10 images which look like the object in the polygon. I g I gave a brief description. It's a side scan sonar data and the polygon is supposed to show a m right you can add a lot more description in the detail you can add in color lighting and all of these

### **01:18:25**

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** things right and then it generate this example right it generated I think 10 example of what the object should look like right each of these examples have something unique in them they are similar to the object that you have here right they're not similar to the that's why maybe you will require some training technique but with more prompt with a more clever prompt engineering and giving it more example in its

**Ratul Shashank:** Oh,

**Pratyaksh Singh:** context you can ask it to generate these kind of example. Now these examples all of these they look like a probable mine.

**Ratul Shashank:** wait.

**Pratyaksh Singh:** Imagine if this was in the sides scan sonar data you would have marked it as mine right and this gives you like eight or nine maybe maybe not

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** all of them are uniques right you can prompt it to you know generate different uh in all of these 10 uh all those okay let me just ask it to right? So you can formulate your prompt like this and then you can ask it to generate 10 unique example or 30 40 whatever unique examples right and you ask it to generate it.

### **01:19:58** {#01:19:58}

**Pratyaksh Singh:** You can give it more examples.

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** You can give it a lot more example right and you let the model generate it because in its training data it knows how to manipulate image and all of these things. And if you can get an open-source model which succeeds in generating unique real life object let's say 10 or 20% of the times even 10 or 20% of the time then you can ask your labelers to label the data right so just can you compare closed source as well as open source model to do this open source model would be obviously

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** better because you know open source model will be better because then we can have unlimited generation. But even with closed source model if required we can pay pay for it or we can come up with a work around to have it generate examples,

**Ratul Shashank:** Yeah. So I that was that

**Pratyaksh Singh:** right? Does it make sense? Now, see, with with each iteration, it starts to generate something more rugged,

**Ratul Shashank:** uh

### **01:20:58**

**Pratyaksh Singh:** something more different. There is shadow in some images. There aren't anything in another example. Another thing you can do is you can ask it to write code which can generate some example or you can ask it to to describe it in such a way that and similar like compare a lot of these model find out which one of them is performing really good and then we can do lot of these uh a lot of in context learning.

**Ratul Shashank:** Yeah.

**Pratyaksh Singh:** Does it make sense?

**Ratul Shashank:** Yeah, it made sense. Uh I I just wanted to push uh on this like uh I want to ask uh let me form my thought uh like when we say similar

**Pratyaksh Singh:** Mhm.

**Ratul Shashank:** image right? So what is the bare minimum criteria for being similar? Is it shadow? Is it structure?

**Pratyaksh Singh:** Okay. Great.

**Ratul Shashank:** because what I uh sorry yeah so

**Pratyaksh Singh:** Oh,

**Ratul Shashank:** uh just let me finish uh sorry to get here um I was saying what

### **01:22:05**

**Pratyaksh Singh:** no. No

**Ratul Shashank:** I found was when I used chat GPT or nano banana on

**Pratyaksh Singh:** problem.

**Ratul Shashank:** this it's overly generating the background uh even in even what you you just saw what images chat GPT created So that was like I want to

**Pratyaksh Singh:** Mhm.

**Ratul Shashank:** just like just the base criteria or the bare minimum like what is necessary in this uh similar what is similar

**Pratyaksh Singh:** Got it. So, okay. I want you to now do two things.

**Ratul Shashank:** exactly.

**Pratyaksh Singh:** One is generate the UXO objects and now I want you to ask the model to generate the images too. So to generate the backgrounds too like have two sets of experiment where you ask it where you ask the model to generate the background right you will you just give it an example of background from any of the image. So like you will open maybe POE data set right or DRN data set VW data set you are you give it some example and ask it to generate image similar to this right

### **01:23:12** {#01:23:12}

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** now coming back to your question on what is similar right so I'm sorry like for confusing you with words but similar here means that it looks like AOI or it looks like the mind that you are giving example and internally we want it to be as distinct as possible. So you want to train a model that works everywhere, right?

**Ratul Shashank:** Oh,

**Pratyaksh Singh:** But you don't have enough data.

**Ratul Shashank:** hello.

**Pratyaksh Singh:** Just try to understand why we why we are doing this experiment. we have we we want to train a model that can take it different ways the UXO might appear and then it is able to categorize it but the problem that we have is we don't have enough data so we are asking our generative AI model to generate maybe different ways that example might occur so that the classification model that we are training is robust to all those permutations does that make sense

**Ratul Shashank:** More Yeah, it

**Pratyaksh Singh:** So you want it to be similar in the sense that it still looks like UXO but you

### **01:24:19** {#01:24:19}

**Ratul Shashank:** does.

**Pratyaksh Singh:** want it to be distinct so that it covers how all the UXO looks like.

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** Is that clear?

**Ratul Shashank:** Mhm. Yeah. So, uh that was that was my initial thought. So that is why I uh as you as you also mentioned like generate a background and generate the object like uh what I thought I could like transplanting this object was basically that exact step. uh I want to see how this like how this entire falls in

**Pratyaksh Singh:** Got

**Ratul Shashank:** the in in the picture if this is actually usable in the actual image and regarding the uh regarding similar

**Pratyaksh Singh:** it.

**Ratul Shashank:** factor. Uh so I uh so that was also something that I thought uh and my what conclusion that I came up with was uh I can like have the have the image maybe change the elongation or like shorter

**Pratyaksh Singh:** Uh-huh. Yeah.

**Ratul Shashank:** shadow or longer shadow like these were something that I had in mind.

**Pratyaksh Singh:** Exactly.

**Ratul Shashank:** So I wanted to just clear it out with you if I am on the right track or Yeah.

### **01:25:53**

**Pratyaksh Singh:** Yeah.

**Ratul Shashank:** So that's what I wanted to clear

**Pratyaksh Singh:** So, so yeah. So those are some distinction right? So shadow shadow might change the size of the image might change or uh the size

**Ratul Shashank:** out.

**Pratyaksh Singh:** of image might change or maybe see so some of things you can you can you can simulate synthetically which we call augmentation. So for example it's a changing the elongation changing the elongation you can do it with classical

**Ratul Shashank:** Thank

**Pratyaksh Singh:** computer vision right you can elongate in one direction changing the shape you can do it with

**Ratul Shashank:** you.

**Pratyaksh Singh:** classical machine learning tool right there are some things that you can't do right uh may maybe it is possible maybe changing the length of the shadow maybe that is also possible with classical learning but generating the whole object uh but generating the whole

**Ratul Shashank:** Yeah, I mean it is Mhm.

**Pratyaksh Singh:** object that is not possible So that's what we want the help of generative AI for us to Otherwise those things that can be done with classical M classical computer vision that we can do during our training which we call as augmentation does that

### **01:27:00**

**Ratul Shashank:** I understand. Yeah,

**Pratyaksh Singh:** does that make sense so see I

**Ratul Shashank:** I Yeah, it does. It does.

**Pratyaksh Singh:** want you to do prompt engineering right so for example let's say people train these large language models right but uh I mean that don't really train it. They just formulate their prompt in such a way that it works as they expect. Right? So I want you to do I want to do the same thing for image generation. Okay?

**Ratul Shashank:** I hope

**Pratyaksh Singh:** And these examples you know if you can generate it without example without giving image example it is all well and good but you know if you have to put image

**Ratul Shashank:** What do you what do you mean by without giving image

**Pratyaksh Singh:** example

**Ratul Shashank:** example like feeding

**Pratyaksh Singh:** okay so so can you just feed in prompt for

**Ratul Shashank:** the

**Pratyaksh Singh:** it to generate

**Ratul Shashank:** Okay. I Okay,

**Pratyaksh Singh:** images.

**Ratul Shashank:** I understand. I understand now. I

**Pratyaksh Singh:** Can you give it this text?

### **01:28:06** {#01:28:06}

**Pratyaksh Singh:** This is what I mean.

**Ratul Shashank:** understand.

**Pratyaksh Singh:** So with image you give it more context, right? But when you give it more context, you limit it to. So my question is, can you just describe things as text and then have it generate them?

**Ratul Shashank:** Yeah, I I think it is possible with the Loa. I have not tried that but I think it it could be possible because there is

**Pratyaksh Singh:** No. Can you try it without fine tuning? No. Laura fine tuning. Can you first try that? Can you do it with just prompt engineering?

**Ratul Shashank:** Okay.

**Pratyaksh Singh:** I'll be back in a minute.

**Ratul Shashank:** I

**Pratyaksh Singh:** Just a minute.

**Ratul Shashank:** Okay.

**Geoff Horowitz:** suction.

**Ratul Shashank:** Uh Jeff,

**Geoff Horowitz:** I'm

**Ratul Shashank:** uh I just wanted to add on that AOI small black and

**Geoff Horowitz:** Yeah.

**Ratul Shashank:** UX. So like uh our pro uh like the uh not the problem but bottleneck was it is similar right? uh and the generative model would uh more or less give it would be difficult for us to distinguish if it's UXO or AY small black that was the

### **01:29:31** {#01:29:31}

**Geoff Horowitz:** Mhm.

**Ratul Shashank:** bottleneck right I think Mac data would be helpful in that because if this

**Geoff Horowitz:** Right. I agree with you.

**Ratul Shashank:** is entirely uh dependent on data set like Mac

**Geoff Horowitz:** I agree with

**Ratul Shashank:** data yeah what I found was Mac data uh In DRN data set the MAC the values is very less compared to A and DS

**Geoff Horowitz:** I I agree with you, Rachel. Uh I I just I want to cut you off a little.

**Ratul Shashank:** and

**Geoff Horowitz:** I want to cut you off briefly, which is to say we should absolutely look at that, but with the pipeline as it exists right now, we don't have the MAG data. So without the MAG data as an additional input, the model can't differentiate between the two just visually. That will be the next milestone.

**Ratul Shashank:** Yeah.

**Geoff Horowitz:** The next milestone will be incorporating the MAG data in which case maybe we can then separate the two back out.

**Ratul Shashank:** Yeah. Yeah. I understand. Uh yeah,

**Geoff Horowitz:** Yeah.

### **01:30:33** {#01:30:33}

**Ratul Shashank:** that was just my that was just my reasoning like we can just use this for uh confirmation or something.

**Geoff Horowitz:** Absolutely. I agree with you. Um I was going to say Sachin, I'm going to need to drop in a few minutes. Would you please give an update uh on Slack? Would you just update me on Slack? I know I think we left off yesterday that um uh you were you were trying to figure out why those precision results were so low. Um, so just shoot me an update if you've retrained anything. Just send a Slack message and I'll I'll read it

**Sachin Pandey:** Yeah. Uh I trained three models uh on the Ninja but like they were not learning

**Geoff Horowitz:** later.

**Sachin Pandey:** very good because the train loss was fixed on 0.9 like which is very low around 8 8 to 9% drop in the like drop in the like loss.

**Geoff Horowitz:** Okay,

**Sachin Pandey:** So I so new experiments are running running on volley.

**Geoff Horowitz:** just I I

**Sachin Pandey:** When I get the result I will share it with you.

### **01:31:44**

**Geoff Horowitz:** sounds

**Sachin Pandey:** In the meantime I am yeah I am just like uh digging deep into the

**Geoff Horowitz:** good.

**Sachin Pandey:** matrix calculation.

**Geoff Horowitz:** Okay,

**Sachin Pandey:** So like matrices are correct like we can rely on

**Geoff Horowitz:** good.

**Sachin Pandey:** them.

**Geoff Horowitz:** Okay, perfect. Perfect. Just when when you when you can just do a write up.

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** I don't want to break into project action virtual conversation too much.

**Pratyaksh Singh:** Hey Jeff, I I want to like you know would it be possible like if I can also take help of

**Geoff Horowitz:** Thanks.

**Pratyaksh Singh:** Sachin and because for the next 2 three days I would like really want to see if synthetic data or open-source data can help us because

**Geoff Horowitz:** Yep.

**Pratyaksh Singh:** I think I think we're training the model with a lot of at least I trained a lot of model with lot of variations but it's giving diminishing return because I don't think we have enough data or diversity in in our data set.

**Geoff Horowitz:** Yep.

**Pratyaksh Singh:** So that's why that's why I think you know on Monday at least at least we should have an

### **01:32:43** {#01:32:43}

**Geoff Horowitz:** Yep.

**Pratyaksh Singh:** answer yes or Is it possible? Is it not possible? Something like

**Geoff Horowitz:** Yeah, the I mean PR Josh it's as far as I'm concerned you know it's your show take you

**Pratyaksh Singh:** that.

**Geoff Horowitz:** know reassign as as you see fit the only the only thing Praash that I'll mention which um I don't know if you saw Satchin's message or if we were having that as a discussion Sachin Sachin identified some issues with the underlying data. Um and and so I think that I mean I think that's I think that's what we're seeing right what we're seeing is maybe some underlying issues uh which are good which are good catches. So, remind me what was the or was it an issue with the it was an issue with the way that the model is validating

**Sachin Pandey:** Yeah,

**Geoff Horowitz:** right for the wind farms for the

**Sachin Pandey:** like for uh if there is not the like overlap what the bounding box the mask the remaining is considered as the

**Geoff Horowitz:** AY

**Sachin Pandey:** false positive and it messing up with the like object level matrix.

### **01:33:56** {#01:33:56}

**Sachin Pandey:** But if you see the like pixel level, it is like looking good. And like if you want to focus on the prediction side, we can like improve the prediction more by like putting a size filter based on class because like AI big is generally around 3,000 to 4,000 pixel. The smallest one is around this much. So anything which is below this is like automatically removed.

**Geoff Horowitz:** But that's that's for AOI big. What about like the UXOs,

**Sachin Pandey:** Yeah, but this is only applied on the class-based filtering.

**Geoff Horowitz:** right?

**Sachin Pandey:** So for it will be around 10 pixel 20 pixel but for AI big or black patch it can be around like 3,000 4,000 pixels. So it will like definitely reduce the number of false positive because we are confident around the size any small mistake which is getting predicted will automatically be removed. So this will also like push the prediction matrix up.

**Geoff Horowitz:** I see.

**Sachin Pandey:** But we are yeah still we are trying to like fix the root cause.

**Geoff Horowitz:** Anyway, seriously thing

### **01:34:58** {#01:34:58}

**Sachin Pandey:** If like models should not predict these and if it still does then we can just fix it like these ways.

**Geoff Horowitz:** I see what you're saying. Um, projects, the the the in summary, the point I was getting at is, you know, by all means, uh, but I I also think that the things that Satchin has been doing have have identified some issues that maybe we didn't know about before. So,

**Pratyaksh Singh:** Yeah. Yeah. I think I think we discussed it.

**Geoff Horowitz:** yeah.

**Pratyaksh Singh:** So as in it's related to the eval that we are running right on the

**Sachin Pandey:** Yes.

**Pratyaksh Singh:** HTML. Yeah.

**Sachin Pandey:** Yeah.

**Pratyaksh Singh:** I think I think that can be fixed. uh I I'm more concerned about the false negative the things that we are missing than the false positive because I think we did this previously also where with size filters and uh some This time augmentation we could we could reduce the number of false positive but I think false negatives are the one which which hurts a

### **01:35:55**

**Sachin Pandey:** false neg for UXO like I I don't have the ninja running so I as much as I remember it was like one or two false negative and The even the false parity for UXO specifically it was like something like it is not

**Pratyaksh Singh:** Uh-huh.

**Sachin Pandey:** random like there were a few mistakes like for a poor data set it it made the shades as

**Pratyaksh Singh:** All

**Sachin Pandey:** a UXO which is wrong but others were looking like genuine like similar to UXO which we can

**Pratyaksh Singh:** right. So if our false negative for UXO and if our

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** P negative for UXO and that and AI black if they are good I think we should run the K-fold cross validation and we

**Sachin Pandey:** This

**Pratyaksh Singh:** would I think I think we would have a really good model if it is detecting all the UXOs and if it's detecting all the UXOs and the AI blacks basically I think I think that's what the project is all about.

**Sachin Pandey:** Yeah, F1 score was around 71% for object level.

**Pratyaksh Singh:** Uh, okay.

**Sachin Pandey:** So

### **01:37:04**

**Pratyaksh Singh:** No, I I'm more I'm more concerned about like what was the recall like object object based

**Sachin Pandey:** recall uh I will be able to

**Pratyaksh Singh:** recall?

**Sachin Pandey:** share it once the ninja is up.

**Pratyaksh Singh:** Uh,

**Sachin Pandey:** It was in the HTML but but it

**Pratyaksh Singh:** okay. All right.

**Sachin Pandey:** was at least for the UX.

**Pratyaksh Singh:** I think I think Got it.

**Sachin Pandey:** So it was looking good.

**Pratyaksh Singh:** What is the pixel size that you're running it on? 128 \+ 128 or 256\.

**Sachin Pandey:** Uh, I need to check it.

**Pratyaksh Singh:** All right. All right. Let me know of the model.

**Sachin Pandey:** Uh,

**Pratyaksh Singh:** I think then we can just fix the eval and then we will be done with it because whatever model I am training it's missing like four.

**Sachin Pandey:** okay.

**Pratyaksh Singh:** I think there are those repeated five UXOs that are being missed by the model which was concerning me. you know if the model you trained it works good on them then it's perfect then I think then I think

### **01:37:57** {#01:37:57}

**Sachin Pandey:** Yeah.

**Pratyaksh Singh:** we you know we can we can give them that model we can improve the recall of it sorry we can improve the precision of it and then we can give it the give them that

**Sachin Pandey:** Okay,

**Pratyaksh Singh:** model

**Sachin Pandey:** I will share it once uh once like Ninja is running and also the config like all the configs are

**Pratyaksh Singh:** great awesome awesome

**Sachin Pandey:** changed.

**Pratyaksh Singh:** Uh Sachin, can you uh can you restart 8512?

**Sachin Pandey:** Uh, it was running, right? I thought it was already running.

**Pratyaksh Singh:** I think uh let me check. Anyways, anyways,

**Sachin Pandey:** Is it?

**Pratyaksh Singh:** if that model is good,

**Sachin Pandey:** I Yeah,

**Pratyaksh Singh:** just host the

**Sachin Pandey:** I found the screenshot. I shared it with you. So recall call is86 and precision is 0.59 and F1

**Pratyaksh Singh:** Where is where is the

**Sachin Pandey:** score is I will tag it to you

**Pratyaksh Singh:** screenshot?

**Sachin Pandey:** I guess yeah this was the

**Pratyaksh Singh:** Yeah. Yeah. I think one one thing that I was telling you was that I wasn't I think this confusion matrix

### **01:39:00** {#01:39:00}

**Sachin Pandey:** model

**Pratyaksh Singh:** is inverted. That is that is what uh I was concerned about.

**Sachin Pandey:** yeah we can check it

**Pratyaksh Singh:** So just confirm it. Is it running on Ninja or on Wally?

**Sachin Pandey:** it.

**Pratyaksh Singh:** This HTML.

**Sachin Pandey:** This This one is on

**Pratyaksh Singh:** Okay. Okay. Once you have it, just share the link with me.

**Sachin Pandey:** Ninja.

**Pratyaksh Singh:** I will I'll confirm it out. And one thing I would also like you to do is if you are very confident on a model or whatever your best model is. There are only like 130 images, right? Go through all of its prediction and try to do. So this is something that we call loss analysis where you go through each of the prediction and you try to come up with hypothesis that you know what is going wrong what what I need to fix you know are there some patterns to what the mistake is you know what the mistake is and all these things does it make

**Sachin Pandey:** Okay.

### **01:39:57**

**Sachin Pandey:** Yeah, it makes sense.

**Pratyaksh Singh:** sense

**Sachin Pandey:** Like similar to what you do for like when you ask to update the prediction in the stream.

**Pratyaksh Singh:** yeah yeah exactly and share it with me also like if

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** this model is good Then amazing. I think I think we'll be done with it mostly.

**Sachin Pandey:** Okay, I I will share it with

**Pratyaksh Singh:** All

**Sachin Pandey:** you.

**Pratyaksh Singh:** right.

**Sachin Pandey:** Like even if you consider the matrix is bad at least like the center one which is like it

**Pratyaksh Singh:** Mhm.

**Sachin Pandey:** is identifying 13 objects correctly. So out of 15 it is

**Pratyaksh Singh:** No. So see this is what is confusing to me right? Uh it is saying that 13 it is identifying correctly. 9 it is missing. So 13 \+ 9 is 22\.

**Sachin Pandey:** Nine is nine it is not missing n it is predicting the UXO in the background that

**Pratyaksh Singh:** Okay.

**Sachin Pandey:** was I telling about like most of these things like some are mistakes like in prediction in both

### **01:40:55**

**Pratyaksh Singh:** Uh got it.

**Sachin Pandey:** data set are mistakes but other look the object these nines like similar

**Pratyaksh Singh:** Got it. So, so according to this you have like 15 object right 13 correct and then one it has

**Sachin Pandey:** Yeah.

**Pratyaksh Singh:** mclassified into a small black and one is the background right total 15

**Sachin Pandey:** And background. Yeah.

**Pratyaksh Singh:** object right I think I think that your metrics might be

**Sachin Pandey:** Yes.

**Pratyaksh Singh:** correct all right yeah share the example I'll I'll go through them I'll go through the prediction

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** And then at least this we can have as baseline or it will be a really good model.

**Sachin Pandey:** Yeah,

**Pratyaksh Singh:** If I look at the matrix,

**Sachin Pandey:** please like we can also pass it through the training set to see like it will pull more AI which we may have missed and like put And then again or like if check

**Pratyaksh Singh:** Yeah.

**Sachin Pandey:** we'll just ask the labeler to check it if it is matching with the like the features which we have you can just add it into a training

### **01:41:53**

**Pratyaksh Singh:** Mhm.

**Sachin Pandey:** set it will only increase the like increase the confidence in the training

**Pratyaksh Singh:** Got it. Got it.

**Sachin Pandey:** data

**Pratyaksh Singh:** The only thing it is it is a for small black, right?

**Sachin Pandey:** why small black yeah

**Pratyaksh Singh:** Yeah. In the 50s.

**Sachin Pandey:** Uh

**Pratyaksh Singh:** But still it's like it's a really good model.

**Sachin Pandey:** yes,

**Pratyaksh Singh:** All

**Sachin Pandey:** I think we can check it. I I I remember I updated it in the the app which Jeff was using to

**Pratyaksh Singh:** right.

**Sachin Pandey:** show. We can check the predictions there also. It will be in 8505

**Pratyaksh Singh:** 850\. Okay. Give Give me a minute. I wanted to do something else.

**Sachin Pandey:** 850\.

**Pratyaksh Singh:** What is s equal to?

**Sachin Pandey:** Uh which one?

**Pratyaksh Singh:** What is the query

**Sachin Pandey:** Yeah,

**Pratyaksh Singh:** after?

**Sachin Pandey:** it's just a unique URL. It will redirect. It will show you the same setting which I am using.

**Pratyaksh Singh:** Got it.

### **01:44:21** {#01:44:21}

**Pratyaksh Singh:** Okay.

**Sachin Pandey:** binary one is the first model which we like first set of model which we trained.

**Pratyaksh Singh:** So multiclass UX on binary

**Sachin Pandey:** Yeah, these two are the one. Multiclass is the one latest one which I just shared the matrix with you Binary is binary

**Pratyaksh Singh:** Mhm.

**Sachin Pandey:** was like mainly for like

**Pratyaksh Singh:** So this is surprising like multiclass is working better than binary, right?

**Sachin Pandey:** I found one example if you see the image pipe the multiclass missed but bindary ported I'm just going through all the examples

**Pratyaksh Singh:** Got it. Yeah, I'm also going

**Sachin Pandey:** Let me multimodel is doing much better. It was the only one case where the binder was identifying the object.

**Pratyaksh Singh:** So apart from the fifth image everywhere the multiclass is identifying the object

**Sachin Pandey:** Yes,

**Pratyaksh Singh:** right.

**Sachin Pandey:** I'm on the 10th image. It's taking some time. Five images are

**Pratyaksh Singh:** Got it.

**Sachin Pandey:** remaining. these long images like the ones which are like very long should we remove it from the validation set I don't think we will be getting these like our client will be giving these the one which are like very

### **01:47:23** {#01:47:23}

**Pratyaksh Singh:** Which one? Which images?

**Sachin Pandey:** long and very zoomed out

**Pratyaksh Singh:** No. No. I don't think I should remove anything. They gave it to us. Should keep it.

**Sachin Pandey:** This one is doing better. Much better.

**Pratyaksh Singh:** This is so wait on 10th image. Did it predict anything? I can't see it if it did. Yeah,

**Sachin Pandey:** That one was didn't loaded for me.

**Pratyaksh Singh:** I think it did. Thank

**Sachin Pandey:** I think it it did because uh only one image we missed was on the

**Pratyaksh Singh:** you.

**Sachin Pandey:** five and we found the one which was with the AI

**Pratyaksh Singh:** Mhm.

**Sachin Pandey:** small black it wasn't I guess yeah there should be only one image that we missed I guess it was it will be five

**Pratyaksh Singh:** Yeah, that's what I want to confirm. I want to test out your metric and see in the 10th image it is missing two object actually I think certainly it is missing one object maybe maybe I'm wrong but let me show you the link

### **01:49:12**

**Sachin Pandey:** I check the others but I check the others but I

**Pratyaksh Singh:** of it huh yeah

**Sachin Pandey:** didn't others it is identifying I will check the template

**Pratyaksh Singh:** so see I told you right so all the models that I have also trained they are missing like five object four or five object Right? One is the fifth one. There are two object and the 10th one which they are missing. And then my model is uh the models that I'm training are underperforming on. So see these examples right I think it is missing one. This is so small that it's like how to view it. But it it's missing like two or three object here maybe on this image this thin kind of image it is missing object the 10th

