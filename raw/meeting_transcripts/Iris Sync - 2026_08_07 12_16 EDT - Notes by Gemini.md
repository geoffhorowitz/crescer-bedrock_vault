# **📝 Notes**

Aug 7, 2026

## **Iris Sync**

Invited [Sachin Pandey](mailto:sachin@crescer.ai) [Pratyaksh Singh](mailto:pratyaksh@crescer.ai) [Hemanth Sarabu](mailto:hemanth@crescer.ai) [Geoff Horowitz](mailto:geoff@crescer.ai) [Siddharth Soni](mailto:siddharth@crescer.ai) [Ratul Shashank](mailto:ratul@crescer.ai)

Attachments [Iris Sync](https://calendar.google.com/calendar/event?eid=NnNzMHVxNzk3MmJqZGVwNXFoN2J1Mjd1OTdfMjAyNjA4MDdUMTYzMDAwWiBnZW9mZkBjcmVzY2VyLmFp) [Iris Sync - 2026/08/07 12:16 EDT - Recording](https://drive.google.com/file/d/1ZcfOLBbiN5HFPQayvAirirBm3IhSlalo/view?usp=drive_web)

Meeting records [Transcript](https://docs.google.com/document/d/1eBlfaSPs8HxEGyXE4cdE5qOsIcEHV6yuanHhwkIo52w/edit?usp=drive_web&tab=t.u5nv2zfk9vqz) [Recording 2](https://drive.google.com/file/d/1Q9qISkvIQXa24fto5WF8JVZtqo0C6_95/view?usp=drive_web) [Recording](https://drive.google.com/file/d/1ZcfOLBbiN5HFPQayvAirirBm3IhSlalo/view?usp=drive_web) 

### **Summary**

Meeting discussions focused on optimizing Version 4 model training with augmented data and refining Milestone 2 deliverables.

**Model Evaluation and Augmentation**  
The team analyzed Version 4 model performance, noting that data augmentation and K-fold validation are critical for improving robustness against overfitting. The group decided to include corrected artificial data in the training set to enhance model accuracy.

**Architectural Shifts and Realism**  
Participants determined that current diffusion-based object generation was ineffective and pivoted to a code-based procedural generation method. They agreed to test both close-cropping and background stripping techniques to improve synthetic data quality.

**Reporting and Milestone Completion**  
The team established a strategy for performance reporting using confusion matrices to balance recall and precision requirements. They finalized requirements for Milestone 2 completion, including integrating cut-and-paste datasets and cross-validation metrics.

### **Decisions**

## Aligned

* **Early stopping criteria for model training** Model training is to be terminated early if the F1 score reaches zero, indicating a failure to learn effectively.

* **Deferment of current model sharing** The sharing of the current best model is deferred until the next milestone to allow for demonstrating further performance improvements.

* **Evaluation of object generation approaches** Both close-cropped and background-removed object generation approaches will be evaluated to determine the most effective methodology.

* **Validation run using real data** A model training run will be executed using real data, excluding diffusion-based synthetic data, to validate the current procedural generation.

* **Milestone 2 comparison plan** The V40 model performance will be compared against a version including additional cut-and-paste objects to complete Milestone 2 requirements.

* **Inclusion of cut-and-paste data in training** The team will train a model that incorporates cut-and-paste data to evaluate its impact on performance.

* **Acceptance of current image blending** The team determined that current image blending is sufficient and requires no further intervention.

* **Adoption of four-bucket performance reporting** The team will report model performance using a four-bucket framework consisting of UXO-like, actual UXO, non-UXO-like, and background categories.

* **Completion criteria for Milestone 2** Milestone 2 completion criteria are established as finishing cross-validation metrics, incorporating cut-and-paste data in training, and validating performance on the Treasure Island dataset.

We've **updated the Decisions section** using your feedback.

Let us know what you think: [Helpful](https://google.qualtrics.com/jfe/form/SV_5bXzKQfylMIhSXc?isHelpful=True&entryPoint=decisions&confid=0eBV83MaqUEvn-DED9YPDxIUOBEBMgUIigIgABgECA&isGoogler=False) or [Not Helpful](https://google.qualtrics.com/jfe/form/SV_5bXzKQfylMIhSXc?isHelpful=False&entryPoint=decisions&confid=0eBV83MaqUEvn-DED9YPDxIUOBEBMgUIigIgABgECA&isGoogler=False)

### **Next steps**

- [ ] \[Sachin Pandey\] Compare Model Performance: Analyze and document performance numbers comparing previous fine-tuned results with new versions.

- [ ] \[Pratyaksh Singh\] Review Sand Ripples: Review the sand ripple artifacts shared in the channel by Monday.

- [ ] \[Pratyaksh Singh\] Build Visualization App: Develop a side-by-side visualization tool to compare real samples against generated samples.

- [ ] \[Pratyaksh Singh\] Test Claude Generation: Evaluate procedural generation capabilities using Claude.

- [ ] \[Pratyaksh Singh\] Visualize Clusters: Create a visualization application for the 100,000 generated clusters stored in JSON format.

- [ ] \[Sachin\] Finish Cross Validation: Complete the cross validation metrics for the trained models. Share the results with the team once finished.

- [ ] \[Sachin\] Train Cut Paste Model: Incorporate the cut and paste data into the model training process. Verify the performance improvements compared to the base model.

- [ ] \[The group\] Evaluate Treasure Island: Perform an assessment of model performance using the new Treasure Island dataset. Ensure the team is confident in the results.

- [ ] \[Ratul\] Analyze MAG Data: Correlate the MAG data analysis with ground truth annotations. Connect next week to discuss the findings.

### **Details**

* **K-Fold Training and Model Evaluation**: Sachin proposes training models on individual folds in parallel to diagnose performance issues, to which Hemanth responds that K-fold validation is necessary due to the high uncertainty inherent in the small dataset size ([00:06:58](#00:06:58)). They agree that if a model exhibits poor performance, such as a zero F1 score, they can proceed with early stopping ([00:09:40](#00:09:40)).

* **V4 Model Performance and Baseline Comparisons**: Sachin explains that the V4 model struggled with overfitting and poor performance on validation sets due to penalties on false negatives, though data augmentation improved results ([00:09:40](#00:09:40)). Hemanth tasks them with creating a report comparing the V2 baseline, the fine-tuned version, and the new V4 model to quantify improvements for the upcoming milestone, and Sachin agrees to share this table once the team is assembled ([00:11:52](#00:11:52)).

* **Team Project Updates and Resource Sharing**: Pratyaksh and Ratul provide updates on their recent tasks, including procedural generation of UFOs and object generation; Ratul commits to sharing the Google Drive folder containing generated objects and prompts on the Bedrock channel. Pratyaksh confirms they will review Hemanth's previous work on sand ripples on Monday to determine if it can be integrated into their current workflow ([00:13:11](#00:13:11)).

* **Object Generation Agent Pipeline**: Sachin describes an agent-based architecture where a main agent manages a sub-agent to place objects on backgrounds, but the results produced only "blobs" rather than usable images ([00:17:00](#00:17:00)) ([00:21:07](#00:21:07)). After reviewing the output, the team determines that the current approach is ineffective for generating the desired UXO objects ([00:23:35](#00:23:35)).

* **Proposed Architectural Changes for Object Generation**: Hemanth proposes an alternative architecture where they isolate objects from the background and use a VLM to generate them procedurally through code, rather than using diffusion models ([00:26:51](#00:26:51)). The team discusses the trade-offs between "close cropping" to retain context versus stripping the background entirely, and they decide to test both methods to determine the most effective approach ([00:30:29](#00:30:29)).

* **Procedural Generation and Shape Classification**: Pratyaksh reports progress on procedurally generating objects based on four categories: circles, ovals, water drops, and cylindrical shapes ([00:33:11](#00:33:11)). They explain the process of manipulating polygon points to create random shapes and darkening specific regions to mimic real-world appearance ([00:34:25](#00:34:25)).

* **Improving Realism in Synthetic Data**: Hemanth and Pratyaksh discuss methods to increase the realism of synthetic objects, including decomposing images into background, speckle, and structural components ([00:37:43](#00:37:43)). Pratyaksh intends to develop an application to visualize and compare real versus generated samples to identify where further blending or textural adjustments are needed ([00:39:47](#00:39:47)) ([00:46:04](#00:46:04)).

* **Aligning Lighting and Gradients**: Hemanth suggests using an LLM to align the lighting and gradients of synthetic objects with their backgrounds, noting that current synthetic outputs lack proper shadow consistency ([00:44:08](#00:44:08)). Pratyaksh plans to run a new model iteration using these procedurally generated objects—bypassing diffusion models—to test the viability of this strategy ([00:45:06](#00:45:06)).

* **Data Visualization and MLOps Industry Observations**: Pratyaksh reports having generated 100k images and clustering them via embedding maps, though the visualization app remains an open task ([00:46:04](#00:46:04)). The team briefly discusses the value of simple, specialized MLOps tools, referencing companies like Tensor Elite and Goodfire that address specific data analysis needs ([00:47:15](#00:47:15)).

* **Confidentiality and Project Documentation**: Geoff shares a communication from Bridget regarding a potential Swedish-made mine-like object, prompting a discussion about confidentiality and the sensitivity of the information ([00:49:49](#00:49:49)). The team transitions to reviewing the requirements for wrapping up Milestone 2, with Geoff emphasizing the need for comprehensive performance comparisons across all models, including the V40.

* **Validation of Cut-and-Paste Data**: Regarding the wrap-up of Milestone 2, the team clarifies the status of the cut-and-paste dataset used for testing. Ratul notes they provided a small set of images to Sachin for validation, leaving the task of scaling this data for comprehensive testing as an open item ([00:59:24](#00:59:24)).

* **UXO Annotation Discrepancies**: Sachin Pandey explained that previous issues with ground truth data arose because annotations for artificial UXO data were not correctly copied when generating the base images ([01:02:31](#01:02:31)). Geoff Horowitz confirmed that they had previously utilized this data only for testing rather than training, and the group agreed to include the corrected artificial data in the training set to improve model robustness ([01:03:41](#01:03:41)).

* **Model Training and Augmentation**: Pratyaksh Singh noted that the V4 model performance had decreased because direct copy-paste augmentation was excluded, contributing to a lack of robustness ([01:04:45](#01:04:45)). The participants agreed that blending issues with these augmentations were not a concern, and they planned to proceed with training a model that incorporates these techniques to better handle the dataset ([01:03:41](#01:03:41)).

* **K-fold Validation Results**: Sachin Pandey presented preliminary results from the K-fold validation, identifying that the V4 model with augmentation provided the best recall despite ongoing precision challenges. Geoff Horowitz and Pratyaksh Singh observed that the base V4 model exhibited signs of overfitting, whereas the augmented version successfully captured base patterns ([01:06:32](#01:06:32)). Sachin Pandey estimated that the remaining training for these configurations would be completed within one or two days ([01:09:48](#01:09:48)).

* **Reporting Strategy for Model Performance**: Hemanth Sarabu proposed organizing the model performance reporting into three specific categories: UXO-like objects, non-UXO-like objects, and background ([01:13:04](#01:13:04)). The group discussed how the current model struggles to distinguish between actual UXOs and UXO-like objects, such as certain black patches and aerial object indicators, but can successfully differentiate these from background noise ([01:11:44](#01:11:44)).

* **Confusion Matrix and Metrics**: Hemanth Sarabu outlined the need to visualize the model’s performance using a confusion matrix that demonstrates high recall for true UXOs, even if precision remains low due to misclassifications within the UXO-like category ([01:18:53](#01:18:53)). The team agreed that while high precision is desirable, the current priority is achieving high recall for true UXOs, and they discussed how to present these trade-offs clearly to external stakeholders ([01:22:37](#01:22:37)).

* **Precision Concerns**: Geoff Horowitz raised concerns regarding the low precision of the current model, warning that if the model classifies everything as a UXO, high recall scores could become misleading and burdensome for manual verification ([01:31:13](#01:31:13)). The group agreed to continue evaluating the confusion matrices to ensure the model maintains enough selectivity to provide meaningful predictions ([01:32:34](#01:32:34)).

* **Milestone 2 Completion**: Geoff Horowitz defined the requirements for finalizing Milestone 2, which include finishing the cross-validation metrics, training a model with the integrated cut-and-paste data, and ensuring comfort with the model's performance on the Treasure Island dataset ([01:34:10](#01:34:10)). The participants clarified that the K-fold process is intended to provide insights into model sensitivity rather than serving as a separate model development track ([01:35:43](#01:35:43)).

* **Milestone 3 Planning**: Geoff Horowitz initiated a discussion about resuming the analysis of MAG data for Milestone 3\. Ratul Shashank reported that the current progress allows for object detection with a location buffer, and the group agreed to reconnect next week to continue developing this aspect of the project ([01:39:39](#01:39:39)).

*You should review Gemini's notes to make sure they're accurate. [Get tips and learn how Gemini takes notes](https://support.google.com/meet/answer/14754931)*

*How is the quality of **these specific notes?** [Take a short survey](https://google.qualtrics.com/jfe/form/SV_5bXzKQfylMIhSXc?confid=0eBV83MaqUEvn-DED9YPDxIUOBEBMgUIigIgABgECA&detailLevel=standard&hasImages=False&entryPoint=footerMain&isGoogler=False) to let us know your feedback, including how helpful the notes were for your needs.*

# **📖 Transcript**

Aug 7, 2026

## **Iris Sync \- Transcript**

### **00:00:58**

**Hemanth Sarabu:** I check.

**Sachin Pandey:** Hi. Your voice was Yeah,

**Hemanth Sarabu:** Hey.

**Sachin Pandey:** it's it's fine

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** now.

**Hemanth Sarabu:** How are things going

**Sachin Pandey:** in general or like project.

**Hemanth Sarabu:** in general?

**Sachin Pandey:** It's going good. H I wanted to ask some question.

**Hemanth Sarabu:** Yeah.

**Sachin Pandey:** So in the like K-fold training instead of training

**Hemanth Sarabu:** Sash, give me one second. One second. One second. I can't I I'm having some audio trouble.

**Sachin Pandey:** Okay.

**Hemanth Sarabu:** Let me fix it. One second.

**Sachin Pandey:** Okay.

**Hemanth Sarabu:** Welcome to the I can't sleep podcast where I help you drift off one fact at a time. I'm your host Benjamin Boster and today's episode is about silk. Silk is a natural protein fiber. Okay.

**Sachin Pandey:** Yeah.

**Hemanth Sarabu:** Okay. I can hear you now.

**Sachin Pandey:** Was that Alexa?

**Hemanth Sarabu:** No, no, no. That was a part. So, I have these headphones and it has uh usually these headphones if you double tap it'll play, right?

### **00:06:58** {#00:06:58}

**Hemanth Sarabu:** And usually it'll play Spotify. So, that was just a podcast on Spotify that uh so I went to get my headphones and I wore them and by

**Sachin Pandey:** Yeah,

**Hemanth Sarabu:** mistake I double tapped I guess since we started playing Spotify.

**Sachin Pandey:** but like playing audio doesn't shouldn't stream it in the mic.

**Hemanth Sarabu:** So the on the computer the output is was not set to the headphones. It was set to speaker and so it basically by doubletapping I effectively just hit

**Sachin Pandey:** Oh f\*\*\*.

**Hemanth Sarabu:** play on Spotify even though the audio out was speaker. So it was just coming out of the speaker and it was going into the microphone.

**Sachin Pandey:** Yeah, exactly. Yeah.

**Hemanth Sarabu:** Yeah.

**Sachin Pandey:** Uh the question was like instead of training like one model on all GPU like on all five fold I pick one fold and train all the model on it in parallel. So this way like I can get a better idea like so suppose one model is not

**Hemanth Sarabu:** Uh-huh.

**Sachin Pandey:** doing best and we know the reason like it it could be the like loss function it is not working well with the data set.

### **00:08:13**

**Sachin Pandey:** So does it make sense to like train it more on other fold also or we can

**Hemanth Sarabu:** So you're okay.

**Sachin Pandey:** like

**Hemanth Sarabu:** So it's um so the thing about this is because our data set is small and our validation data set is small is okay let's say I have five five my the number of UXOs I have in my validation set let's say it's five I'm just making this up total our examples like five or six now if for some if you have if your recall is three for some it is four some it is two the noise is so high like the the uncert uncertainty. Do you understand uncertainty? Like the uncertainty is so high that uh So what I would say to

**Sachin Pandey:** You love this.

**Hemanth Sarabu:** you like take read on uncertainty and confidence intervals when you're like measuring things like these accuracy or whatever you take a look at that and you'll understand what I'm talking about. So that uncertainty is very high especially at these small numbers and so that is a thing that this K4 will help the K4 will say okay my validation set is not just four out of this let's say 20 it is any four out of this 20 or many many samples of four or five out of 20\. So now it's as if I'm training this model on different data sets.

### **00:09:40** {#00:09:40}

**Hemanth Sarabu:** It's not actually data sets but different samples of like a larger data set and the idea is that you you you just get a better better estimate of performance. So this is more about you follow me so

**Sachin Pandey:** Yeah. Yeah. I get it like yeah it it will be helpful for when cases like it's not doing that well but it is like

**Hemanth Sarabu:** far?

**Sachin Pandey:** performing a little bit at least.3 F1 score or something but if F1 score is getting zero

**Hemanth Sarabu:** So yes. Yes. Then stop. Then stop. Correct.

**Sachin Pandey:** then

**Hemanth Sarabu:** You're right. Then you can stop early. You're basically saying that the difference is so much. I don't care. Right. This one is not going to do well and others. It failed so poorly. Yes, you can. You can stop that

**Sachin Pandey:** yeah I can try to

**Hemanth Sarabu:** now.

**Sachin Pandey:** uh modify it.

**Hemanth Sarabu:** Right.

**Sachin Pandey:** So actually the model which were performing poor was V4 and the reason was the like the penalty was set to uh not produce false negatives.

### **00:10:40**

**Sachin Pandey:** So it was penalizing more to not produce a false negative.

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** So it it like it memorized the overfitit on the training set and working poorly on the

**Hemanth Sarabu:** So,

**Sachin Pandey:** like validation set. And I have the same config but with like lot of argumentations and that one because of the argumentation it was able to learn the pattern instead of overfitting. So that is doing much better.

**Hemanth Sarabu:** Okay,

**Sachin Pandey:** So like for the base V4 uh should I try like changing the uh

**Hemanth Sarabu:** let's

**Sachin Pandey:** for like for fold two or fold three should I try changing the like learning rate and the loss function because we want to train it without any argumentation or just stop the V4 like right now focus on the one which is doing better like argumentation false positive.

**Hemanth Sarabu:** Yeah, that's a good question. I don't know. I don't know the answer. So, let's Okay, so the good news basically is that okay,

**Sachin Pandey:** Okay.

**Hemanth Sarabu:** augmentation helps. The thing that I'm I would be I'm interested in balancing is we don't want to share the best model right now because there'll be another milestone where we need to show an improvement, right?

### **00:11:52** {#00:11:52}

**Hemanth Sarabu:** So um so I will go back to asking

**Sachin Pandey:** Yeah.

**Hemanth Sarabu:** you if If you can draw an Excala draw or your report somewhere, you can tell me these those numbers that I mentioned earlier which is what is the S one previous project one finetune just same recipe that was used in the first project. Okay. Um if that was fine tuned on this new data what is the performance? Okay. So that is our baseline and then how

**Sachin Pandey:** H.

**Hemanth Sarabu:** much are we improving on top with these different versions is something I would like to know and then how much more can we improve is something I'd like to know and then based on that we'll have to make a call.

**Sachin Pandey:** And yeah like I I have a table where like V2 will be the base base

**Hemanth Sarabu:** All right.

**Sachin Pandey:** one and we can see like all the improvements.

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** I will share it once everyone joins.

**Hemanth Sarabu:** Okay. Uh, where is everyone? Is the meeting starting now?

### **00:13:11** {#00:13:11}

**Hemanth Sarabu:** Okay. Starting now. Hey, brother.

**Sachin Pandey:** How about this?

**Pratyaksh Singh:** Hi guys, how are

**Hemanth Sarabu:** pretty good. Pretty good.

**Pratyaksh Singh:** you?

**Sachin Pandey:** Good.

**Hemanth Sarabu:** Um, were those uh things helpful? Are you guys like using them? The um uh the things that I showed you for

**Pratyaksh Singh:** The one that you made.

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** Yeah. uh I haven't gotten time to go much deeper into other things but I think

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** uh the sand ripple one will surely be helpful right

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** uh today I was working on procedural generation of UFOs and I think after that I will I will look into the things that you worked on to see if we can

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** include them

**Hemanth Sarabu:** Okay. Again, uh no no pressure if it's not actually useful. Uh obviously I'm I'm just curious to see if it

**Pratyaksh Singh:** Yeah. Yeah, I get it.

**Hemanth Sarabu:** works.

**Pratyaksh Singh:** I I think you tagged Ratul in your on that thread, right?

### **00:14:30**

**Hemanth Sarabu:** Yes.

**Pratyaksh Singh:** Yeah. So, I thought Ratul was uh you know,

**Hemanth Sarabu:** Yes.

**Pratyaksh Singh:** Ratul was looking into it and that's why like I I spend my time in the procedural generation of UXs. But I will I will look at it.

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** I think not on the weekend but may on Monday. I

**Hemanth Sarabu:** All right.

**Pratyaksh Singh:** will

**Hemanth Sarabu:** Should we actually let's today start with uh you both since last time we didn't get a lot of time. It's not a welcome.

**Pratyaksh Singh:** Ratul. Do you want to

**Ratul Shashank:** Yeah,

**Pratyaksh Singh:** start

**Ratul Shashank:** I mean my update is short so I'll finish it quickly. Uh just a short update. I have shared the objects generated objects with prat and I I am looking into what you shared in the channel. Uh since EMD is new to me so I am first understanding what this is. So not much not much to update on that. Yeah.

**Hemanth Sarabu:** Do

**Ratul Shashank:** And I'm and I'm also like uh as I stated in the last meeting like I

### **00:15:48**

**Hemanth Sarabu:** that.

**Ratul Shashank:** was looking into other uh ways uh that I also discussed with you. So yeah, not uh delved into any particular direction but Gro mentioned something which could be which could be uh good but uh I shared that with PEX as well. If that is something that would be good then I will share the updates but nothing as of yet.

**Hemanth Sarabu:** Okay,

**Ratul Shashank:** That's all of my

**Hemanth Sarabu:** I'm

**Pratyaksh Singh:** Ratul,

**Ratul Shashank:** side.

**Pratyaksh Singh:** can you share those in the bedrock channel?

**Hemanth Sarabu:** scared.

**Pratyaksh Singh:** The objects images that you shared with me and the other

**Ratul Shashank:** The end the entire

**Pratyaksh Singh:** update.

**Ratul Shashank:** folder.

**Pratyaksh Singh:** Yeah, share the entire Google Drive. Like whatever you shared with me,

**Ratul Shashank:** Okay.

**Pratyaksh Singh:** just shared it on

**Ratul Shashank:** I Okay.

**Pratyaksh Singh:** bedrock.

**Ratul Shashank:** I uh also the uh the other prompt generation as well or just

**Pratyaksh Singh:** Yeah. Everything.

**Ratul Shashank:** the folder.

**Pratyaksh Singh:** Everything. Everything.

**Ratul Shashank:** Okay. Okay. Okay. I I will I will do that right

### **00:17:00** {#00:17:00}

**Pratyaksh Singh:** Yeah.

**Ratul Shashank:** now.

**Pratyaksh Singh:** And like if you have any update uh just share it in in group or even if like have question just share it in the

**Ratul Shashank:** Oh,

**Pratyaksh Singh:** channel.

**Ratul Shashank:** okay. I will do that right now.

**Pratyaksh Singh:** Sachin uh do you want also want to give a brief update of uh on the agent that you put to run to generate the object.

**Sachin Pandey:** Yeah. Uh that agent is like able to mix uh like

**Pratyaksh Singh:** Okay.

**Sachin Pandey:** basic shapes like uh a bump in the surface but not able to generate the like unique UX source which we want.

**Pratyaksh Singh:** Can can you share images to it if you have some? I think you had that. drive. Uh, sorry that HTML,

**Sachin Pandey:** Yes.

**Pratyaksh Singh:** right?

**Sachin Pandey:** So these are the object which are getting pasted.

**Pratyaksh Singh:** H are they pasted or are they being

**Hemanth Sarabu:** So,

**Sachin Pandey:** This one these are generated.

**Hemanth Sarabu:** uh,

**Pratyaksh Singh:** generated?

**Hemanth Sarabu:** okay. Situate me a little

### **00:18:40**

**Sachin Pandey:** Sorry, not past.

**Hemanth Sarabu:** bit.

**Sachin Pandey:** Uh, wait. I don't open the wrong folder.

**Pratyaksh Singh:** This is like uh this is what we discussed in one of our meetings where we asked the we asked one of the AI agent to write code to do procedural generation of object and then you have a vision model which gives it feedback by seeing how how they are

**Hemanth Sarabu:** Nice.

**Pratyaksh Singh:** different.

**Hemanth Sarabu:** Very cool. Very cool. Is the book you're reading helping with all this or not really?

**Pratyaksh Singh:** I think it is helpful. I think uh it should be helpful once I start to implement

**Sachin Pandey:** Yeah, these are the ones.

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** real UX.

**Pratyaksh Singh:** these

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** So yeah,

**Hemanth Sarabu:** Uh-huh.

**Sachin Pandey:** so this like this is the UXO which is try it is trying to generate it doesn't have

**Hemanth Sarabu:** The Okay.

**Sachin Pandey:** the it doesn't have this U this image but the main agent which is running the sub agent will tell it like how it looks and it is try to generate that on a on a random background something like this.

### **00:19:54**

**Sachin Pandey:** This is the background it cropped. This is the cropped region of this this

**Hemanth Sarabu:** wait. Okay.

**Sachin Pandey:** area.

**Hemanth Sarabu:** Okay. Uh

**Sachin Pandey:** It should be four

**Hemanth Sarabu:** so how many agents are there? So what can you draw a pipeline?

**Sachin Pandey:** octive.

**Hemanth Sarabu:** Can you draw a pipeline? uh to say how many agents are there? What does each one do?

**Sachin Pandey:** Uh I don't have like idea about like how many agents were there but mainly the task was to pick each of the like pick each example and try to replicate it in the with a like anyway without cut and

**Hemanth Sarabu:** Okay,

**Sachin Pandey:** paste.

**Hemanth Sarabu:** move on. Okay, let's say stick to one. Maybe go to the top and stick to one.

**Sachin Pandey:** Yeah, the results are not good first because the main base image is also the open source data

**Hemanth Sarabu:** Okay, let's see.

**Sachin Pandey:** which we like applied a filter to make it look like The like the like bad images and it like because that's why it's look very grainier

### **00:21:07** {#00:21:07}

**Hemanth Sarabu:** Fine. Okay. Well,

**Sachin Pandey:** and the UX also are not looking

**Hemanth Sarabu:** okay. Wait, wait, wait, wait, wait, wait, wait. Stop. That's what What uh

**Sachin Pandey:** Good.

**Hemanth Sarabu:** let's You're cropping. Tell us give us a sense of the pipeline in more detail.

**Sachin Pandey:** So like how the agent is handling it or how it's getting created.

**Hemanth Sarabu:** Um just the high level architecture what is the

**Sachin Pandey:** Yeah.

**Hemanth Sarabu:** approach

**Sachin Pandey:** approach is like uh there will be a main agent which is which have access to all base images and the UXOS's images and it will be like telling the sub aents it will be describing the Yes. Uso So first the main will be the agent which will which have all the access to the base image folder UXOs and the background. The sub agent will only have access to the background not the u the UXO object and the agent will be telling the sub agent to like describing the object to the sub agent and uh the sub agent will try to replicate those object into the background which was shared and uh this will be checked by the main agent and like it will be running in the load.

### **00:23:35** {#00:23:35}

**Hemanth Sarabu:** interesting. Okay. And what what are the results? Would you say it's not

**Sachin Pandey:** results are not good because the agent is not able to see it based on the description.

**Hemanth Sarabu:** working?

**Sachin Pandey:** It is not able to generate like good-looking images like these are like

**Hemanth Sarabu:** Interesting.

**Sachin Pandey:** just blobs. blobs not like not things which we can like actually use.

**Hemanth Sarabu:** these this is the open source data

**Sachin Pandey:** Yeah,

**Geoff Horowitz:** Does the does the

**Sachin Pandey:** this is the base image is the open source data set.

**Hemanth Sarabu:** set.

**Geoff Horowitz:** sub agent give me any

**Sachin Pandey:** Yeah,

**Geoff Horowitz:** feedback?

**Sachin Pandey:** the like the main agent like uh based on like it will check the resulted generated images and it will try to like make the changes or try to improve it or tell it what to change and

**Geoff Horowitz:** So the main agent will modify the description to the sub agent.

**Sachin Pandey:** main agent will be checking the output like with uh like it's image analyze it. It will analyze the image and then like give more instruction to a sub

### **00:24:55**

**Geoff Horowitz:** Do you have any sense if it's actually improving?

**Sachin Pandey:** agent.

**Geoff Horowitz:** Like do you have any insight into the the steps of the iterations of the sub agent?

**Sachin Pandey:** No. So these are the examples like how the data was open source data was before and after it's converted to like bedlog looking object bedrop filter to make it look like a beddrop style. In short like this is not that helpful. If you go with the route of copy pasting uh I think it will perform much

**Hemanth Sarabu:** Hey, how um so Sash thanks for summarizing it that way.

**Sachin Pandey:** better.

**Hemanth Sarabu:** Um, what if what if you I'm actually I'm I want to propose a change to your architecture. Um, let me share my screen real quick. To see my screen.

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** What if uh what if like let's say you have this whole image I mean I'm sure this also has it its issues and you have these objects right

**Sachin Pandey:** Mhm.

**Hemanth Sarabu:** what if you grab the object grab the object and then there's all these tricks to separating out the object from the background I think you guys have those tricks I have those tricks somewhere through.

### **00:26:51** {#00:26:51}

**Hemanth Sarabu:** So let's say you uh separate these into two components, right? Basically, you you're able to sub split these split this and maybe you can take this guy. Uh I don't know. Basically, you you've grabbed this object and uh and and a VLM. So, basically,

**Sachin Pandey:** It's basically

**Hemanth Sarabu:** you create this data set. Okay. So, let's call this like an example, right? Xi X1. So,

**Sachin Pandey:** So you

**Hemanth Sarabu:** you can do this for all the objects. And then you can basically create a data set of objects,

**Sachin Pandey:** can

**Hemanth Sarabu:** right? Um what if we asked a VLM to look at each one of those objects which should not have any background information. It can look at it but it has to code up it has to code up a way to generate those objects. Uh does that make sense? it has to code up a way to generate those objects. So it has access to it can actually see these images.

### **00:28:03**

**Hemanth Sarabu:** Uh so let's see it can actually it is able to generate new images procedurally in using code not diffusion or anything like that. Um maybe we can ask it to I don't know I I want to say code and then it can generate these examples and then it can compare these with these two and compute some loss or whatever it wants to do. What if we try this out? So now it's only focused on on the objects themselves.

**Sachin Pandey:** object. Yes.

**Hemanth Sarabu:** Objects and the objects are pretty simple. And I think what I'm more interested in is this code that comes out of it and can we use that to to augment. Yeah. Now it may be really stupid and simple where it's like mixing like circles. it is like uh morphing circles, ellipses, um adding multiple ellipses, something maybe it's doing something simple. I don't know. So, but that's that's one idea.

**Sachin Pandey:** That's it.

**Hemanth Sarabu:** I would I would try that out

**Sachin Pandey:** Yeah, we can try it out.

### **00:29:18**

**Sachin Pandey:** Rol tried a like similar to this like he cropped out the images and try to like generate those images by like generative model like Gemini or uh like any other model.

**Hemanth Sarabu:** I think that's different, right?

**Sachin Pandey:** Yeah,

**Hemanth Sarabu:** And I think it's very important.

**Sachin Pandey:** it it's not it's not get generating from the code. It's like image

**Hemanth Sarabu:** Exactly. Exactly.

**Sachin Pandey:** generation.

**Hemanth Sarabu:** And I'm specifically interested in not letting the BLM worry about generating the background. Uh, I I do think it'll figure it out, but I think maybe we don't actually bother

**Sachin Pandey:** So when we pass the images the background will be black like completely black or like transparent

**Hemanth Sarabu:** That's a good question. I don't know the answer. Maybe maybe

**Sachin Pandey:** where the only the object is like there.

**Hemanth Sarabu:** uh yeah I mean um I don't know I don't know the answer. It could be either I don't know what will be better necessarily but you know it is something like that. It is it is background removed right which means there's no background detail.

### **00:30:29** {#00:30:29}

**Hemanth Sarabu:** So it can be transparent it can be all black. It can be 0.5 values and then the uh the object is object takes object pixels take some value between \-1 and one something like that.

**Sachin Pandey:** What's up? It's a good plan like we can we can set up agent to like test it

**Hemanth Sarabu:** Uh

**Sachin Pandey:** out.

**Hemanth Sarabu:** yeah.

**Pratyaksh Singh:** I I I think that a close crop should be better than just sending in the object. The reason is because the object is defined by its background. if you like if you crop it out a lot uh like if you just crop out the object then you will lose a lot of information and I think uh I I'll share some examples

**Hemanth Sarabu:** I think we should just try both, right? Like we should have enough compute and bandwidth to just try

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** both. I do agree there are some shadows and things like that

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** uh that are how do I stop whose information comes you know is is indicated by the back by whatever is behind the object

### **00:31:52**

**Pratyaksh Singh:** Yeah. All right. Can I go ahead with my update?

**Hemanth Sarabu:** Yeah. I thought you were going to share

**Pratyaksh Singh:** Yeah,

**Hemanth Sarabu:** something.

**Pratyaksh Singh:** like this is what I was showing that uh you know this kind of close crop where you have enough background to distinguish the object out of but not that many that uh that you like kind of that you know you're confusing the VLM with a lot of other details that are not important. I actually did something like this like I just did it manually right where I would I would give the model these kind of object and then I would ask it to

**Hemanth Sarabu:** Mhm.

**Pratyaksh Singh:** the right function to generate this object like it would struggle. So I had to do the planning for it and then I I had to continuously correct it like where it is making mistake and then At the end it did like for only for writing code it did a good job but understanding the image and planning for it I don't think it did a very good job so can I

### **00:33:11** {#00:33:11}

**Hemanth Sarabu:** Can you try it with cloud? Can you try it with favorable?

**Pratyaksh Singh:** try okay I will try it out so I'll I'll update like what I did like uh when I looked at all of these objects I found out that there are four kind of shapes basically. One is like circle and then I also saw this oval kind of shape like if there is circle there is oval also and then you have this water drop kind of shape like and then you have cylindrical shapes which look like

**Hemanth Sarabu:** H

**Pratyaksh Singh:** these. this cylindrical not cylindrical but uh a shape like this right where

**Hemanth Sarabu:** something along. Yeah.

**Pratyaksh Singh:** you have cone like cone at the end and then yeah this kind of this kind of shape so what I did was initially I asked the

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** model to generate mask for these shapes right so it generated mask for all of these shape what I'm doing here is I'm I'm like messing up the shapes so that it look like real

**Hemanth Sarabu:** H.

**Pratyaksh Singh:** object.

### **00:34:25** {#00:34:25}

**Pratyaksh Singh:** To mess up the shape, I couldn't come up with a better algorithm. So what I did was I put points on on this polygon, right? So this polygon is made up of multiple point, right?

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** And then what I do is I drop a percent of these point. Now when you drop a percentage of these these points, the shape will change, right? So each of the time you get a random shape. And then once I had the mask figured out,

**Hemanth Sarabu:** Right.

**Pratyaksh Singh:** another step I did was to generate to like to group all of these all of these out. Right? So one of these examples are that in that particular shape you just have a black kind of region. Right? So this function actually uh this one it takes a random shape and then it darkens it out to kind of create blackish kind of region. So this is one of the uh this is one of one of the UXO that I found out. Another one was uh this kind of UX show where you have a light outline at one end and then a black background kind of extended something like this.

### **00:35:37**

**Pratyaksh Singh:** Right? this kind of thing.

**Hemanth Sarabu:** Oh, we we just See,

**Pratyaksh Singh:** A percentage is okay.

**Hemanth Sarabu:** doc, we sync.

**Pratyaksh Singh:** Can you see UX is 012? Can you see the image for UXO 012?

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** Yeah. So this image, this one,

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** right? Right.

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** So here or the one above it which is UXO 01 or UXO010 even 09 08

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** All of these have a similar pattern where you have a white outline,

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** a light outline and then you have rest of the part which is black.

**Hemanth Sarabu:** No.

**Pratyaksh Singh:** So I described to it and then it was able to write some function which looks like this.

**Hemanth Sarabu:** Oh, this is cool. That's

**Pratyaksh Singh:** Yeah, with the same shape it was able to generate.

**Hemanth Sarabu:** cool.

**Pratyaksh Singh:** So currently I'm like working with uh water drop but you can do it with circle cylinder all of these things. So it works pretty good there also.

### **00:36:25**

**Hemanth Sarabu:** Nice.

**Pratyaksh Singh:** And then yeah another another one was uh this kind of

**Hemanth Sarabu:** All

**Pratyaksh Singh:** shape uh which is UXO 026 where you have two circles which are close by right or 025 those I think

**Hemanth Sarabu:** right.

**Pratyaksh Singh:** this is also like 034 033 0301 those kind

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** of so for this uh this is an example of it

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** right So this looks synthetic but I think we can make it look better and the way we can do it is uh by applying a

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** gaussian blur on one of only one of the slide only one of the sides right where it just blends into the background so it is much better but I didn't put a lot

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** of attention on it because I think uh when Jeff was showing it to Bridget we already had this kind of thing where we were generating these hello kind of structure.

**Hemanth Sarabu:** Is that

**Pratyaksh Singh:** So, so yeah. So,

**Hemanth Sarabu:** one?

**Pratyaksh Singh:** and then another one that I noticed was these kind of shape where you know it looks like it has a height on top of it, right?

### **00:37:43** {#00:37:43}

**Pratyaksh Singh:** The cylindrical kind of shape or oval kind of shape with some which is coming out of surface like it it has a 3D structure.

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** There is not a lot of change in color but it has a 3D structure right.

**Hemanth Sarabu:** Yeah. Yeah.

**Pratyaksh Singh:** So for that also I was able to generate it and okay so this is

**Hemanth Sarabu:** Oh, nice.

**Pratyaksh Singh:** bad but this one huh?

**Hemanth Sarabu:** So, this is cool. I I actually think we should figure a way out.

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** We should figure a way out where you Okay, this is this is my belief. My belief is we should try to decompose we should try to decompose these into backgrounds, speckle, structure, object, etc.

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** Okay.

**Hemanth Sarabu:** And then I think you can generate your clean objects and then add back the speckle and maybe some other structural noise. Um I think I think it would it could uh look very realistic if you mix those

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** things because the a lot of the speckle and and the back the background

### **00:38:45**

**Pratyaksh Singh:** Mhm. Yeah.

**Hemanth Sarabu:** related effects I think you can learn it uh or when I say you can do a

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** datadriven a datadriven uh approach approach to figuring out what it is. Meaning you learn the speckles, distributions, etc. That's a thought. I think it's worth considering because um yeah, I think that's what worth considering. But this looks very realistic. These are both fake,

**Pratyaksh Singh:** Yeah,

**Hemanth Sarabu:** right?

**Pratyaksh Singh:** these are both fake. They were gen just generated using code.

**Hemanth Sarabu:** Nice.

**Pratyaksh Singh:** So yeah.

**Hemanth Sarabu:** Nice.

**Pratyaksh Singh:** So, so like this is my thought, this was my thought like you know for all of the different kind of object that we have I think I was able to generate for all of them and I think we

**Hemanth Sarabu:** Can you can you create can you create an app where on the left it's a real on the right the

**Pratyaksh Singh:** should

**Hemanth Sarabu:** generated samples left are real samples right are generated samples so we can go side by

### **00:39:47** {#00:39:47}

**Pratyaksh Singh:** all Yeah.

**Hemanth Sarabu:** side

**Pratyaksh Singh:** Yeah, I can do that. But I think I think it needs some more work here and I

**Hemanth Sarabu:** so So,

**Pratyaksh Singh:** would like uh

**Hemanth Sarabu:** so if you look at that the the previous one the you were scrolling in your notebook

**Pratyaksh Singh:** Yeah. Yeah.

**Hemanth Sarabu:** you can go uh go up up um down.

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** Yeah, that one that Yeah,

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** this one looks uh very fake, right?

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** I actually do believe that if if you use the some of the blending stuff that I showed you, you can take this very clean looking object and make it look make it blend make it look like it's part of the original original image.

**Pratyaksh Singh:** Got it. I agree with you. Like so this

**Hemanth Sarabu:** So the the ma the the main reason by the way is if you look at the background there's a

**Pratyaksh Singh:** is

**Hemanth Sarabu:** clear gradient. It is it is bright at the top and it's dark at the bottom.

### **00:40:41**

**Pratyaksh Singh:** Uh-huh.

**Hemanth Sarabu:** Right? And in some ways uh actually the shadow um I think that shadow is fine but uh you're if you look at the bottom edge of the left side image the bottom edge of the object that there's a clear line which is very well lit and one would expect that at the because this is like a diagonal right at the top left where the object meets the background that would be brighter and of course it would blend and then at the as it

**Pratyaksh Singh:** Wait, give me a Sorry, I'm losing you.

**Hemanth Sarabu:** yeah

**Pratyaksh Singh:** Let me just draw it out. Okay. So, what you're saying is uh this region, right?

**Hemanth Sarabu:** that region right do you want can you share uh can you share the link it's

**Pratyaksh Singh:** Okay. So, you're saying this?

**Hemanth Sarabu:** very yes this actually. Yeah, let's try.

**Pratyaksh Singh:** Okay. I think I have to start this. Oh, wow. Is already

**Hemanth Sarabu:** Oh, someone's already there.

**Pratyaksh Singh:** I think it's just me.

### **00:41:57**

**Pratyaksh Singh:** I don't like someone previous link maybe to

**Hemanth Sarabu:** Oh, it's your shadow. Uh,

**Pratyaksh Singh:** come.

**Hemanth Sarabu:** it's loading. I don't see uh um Okay,

**Geoff Horowitz:** Looks like you have something here.

**Hemanth Sarabu:** I see it. See it.

**Pratyaksh Singh:** Okay.

**Hemanth Sarabu:** Yeah. So, okay. Yeah. So, you know, you'd expect this to be Oh, error kind of seems to be too big. Uh, this should be light and then this should be dark, right?

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** And then as you go from here to here, you'll you should in a realistic setting,

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** you would see like uh if I if I plot like light versus dark, right? Like this is the intensity, you'll see kind of this this kind of a graph if you plot along this line. So that's what I mean by I think there are things you can do by decomposing and then recomposing. Uh but but do your thing do your thing like uh do whatever you think would

### **00:43:01**

**Pratyaksh Singh:** understood.

**Hemanth Sarabu:** work.

**Pratyaksh Singh:** So let me get this image.

**Hemanth Sarabu:** Oh yeah yeah yeah. Like that like that on the

**Pratyaksh Singh:** Yeah. So it's actually that right you know this was the first iteration like the this was the first

**Hemanth Sarabu:** left. Yeah.

**Pratyaksh Singh:** iteration and I I found those issues so I I actually modified it for the second

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** iteration which is this right

**Hemanth Sarabu:** Nice, nice,

**Pratyaksh Singh:** so yeah so here I think

**Hemanth Sarabu:** nice.

**Pratyaksh Singh:** I think it's good I would like uh Ratul and Sachin to go through it once to make some modification if the thing it is necessary and like I would like to at least get uh you know before spending a lot more time on this I would like to get one model iteration on top of it that can we use yeah

**Hemanth Sarabu:** Yeah. Can I suggest some more things real quick?

**Pratyaksh Singh:** go

**Hemanth Sarabu:** Okay. So,

**Pratyaksh Singh:** ahead

**Hemanth Sarabu:** I think um I think this is something you can do without with an LLM.

### **00:44:08** {#00:44:08}

**Hemanth Sarabu:** Yeah, with an LLM. Basically right now if you look at this guy there is a light source in this direction okay for the object whereas for the for the

**Pratyaksh Singh:** Yeah,

**Hemanth Sarabu:** background there's a light source in this direction so this is a little better because I think

**Pratyaksh Singh:** got it.

**Hemanth Sarabu:** it looks better because you've applied texture um but actually I I think the

**Pratyaksh Singh:** Uhhuh.

**Hemanth Sarabu:** light does not agree still right the same issue I think the only difference between those two is appears to be texture not

**Pratyaksh Singh:** Got

**Hemanth Sarabu:** the the lighting consistency. So you can actually align like the fact that I can see that there's a light gradient this way and the object

**Pratyaksh Singh:** it.

**Hemanth Sarabu:** has a light gradient this way.

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** Uh you should be able to compute or estimate or ask an LLM to align this. So basically it instead of lighting it from here, it or rotate it and try to write light it from here and that could make it more realistic.

**Pratyaksh Singh:** Got it.

### **00:45:06** {#00:45:06}

**Hemanth Sarabu:** You get what I mean,

**Pratyaksh Singh:** I think I get what you mean.

**Hemanth Sarabu:** right? This this shadow should not be

**Pratyaksh Singh:** I get what you mean.

**Hemanth Sarabu:** here.

**Pratyaksh Singh:** I get what you mean. I I want to see if I can just use poison copy paste to fix this up, but I'll have to check it out. Uh one one thing that will make it easier is usually for for sonar when you're going

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** in this direction the lighting seems to be something like this.

**Hemanth Sarabu:** Yeah. Yeah. Yes,

**Pratyaksh Singh:** So that we can also

**Hemanth Sarabu:** that's right. Yeah,

**Pratyaksh Singh:** use.

**Hemanth Sarabu:** you're I think you're absolutely right because um basically away from the the center, right? The center line.

**Pratyaksh Singh:** Yes.

**Hemanth Sarabu:** Yeah. So,

**Pratyaksh Singh:** Yes.

**Hemanth Sarabu:** that's a pretty good clue actually. Like that can help quite a bit.

**Pratyaksh Singh:** Yeah. uh I was saying that you know I I would want to have you know one run of the model on this where we don't use the diffusion based synthetic data generated but like we use the real data on which the diffusion model was trained and then we

### **00:46:04** {#00:46:04}

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** just uh generate these objects procedurally like whatever function we have we generate the object

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** procedurally to see like if it's working right like if if what we're

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** generating is correct

**Hemanth Sarabu:** Okay. Yeah, I agree.

**Pratyaksh Singh:** All right. So this was the update from my end. Uh another thing is that uh the diffusion model I was able to generate around 100k images for each of the data.

**Hemanth Sarabu:** That's

**Pratyaksh Singh:** I was able to cluster them too but uh I wasn't able to build an app to visualize it. So I need to figure that out. I have the cluster in JSON. I just need to build an app to visualize it. Once that app is done,

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** I will it I'll I'll put a link to to you guys so that uh you know you guys can look at it.

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** So the way that I am planning the app is like you will have X and Y. I have applied um map on the embedding so that you can see the clusters and if you click on one point it will show the generated image and you can see which one is real,

### **00:47:15** {#00:47:15}

**Hemanth Sarabu:** Nice.

**Pratyaksh Singh:** which one is fake.

**Hemanth Sarabu:** Nice.

**Pratyaksh Singh:** This that's

**Hemanth Sarabu:** There's a I I saw this company at CVPR.

**Pratyaksh Singh:** it.

**Hemanth Sarabu:** They're called Tensor something Tensor Elite and their whole thing is this. Their whole thing is uh oh, we'll help you find issues with data through embeddings.

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** I'm like, "This is open source. We can put it up." Jeff there is

**Pratyaksh Singh:** I mean you can I mean you

**Hemanth Sarabu:** really Yeah. Yeah. What are you saying?

**Pratyaksh Singh:** can like put uh that also pointly thing Open.

**Hemanth Sarabu:** That's

**Pratyaksh Singh:** And also I think uh one of the thing that I saw

**Hemanth Sarabu:** true.

**Pratyaksh Singh:** was I saw one video where like people built really simple things and they were making like $10 million annually that kind of very simple

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** thing. It's it's just amazing that you just need to find the market who don't want to use code and they just have the money to

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** spend this

### **00:48:25**

**Hemanth Sarabu:** Yes. Yeah. Exactly. That's I think Jeff Jeff totally agrees with

**Pratyaksh Singh:** uh yeah this is I think pretty

**Hemanth Sarabu:** that.

**Pratyaksh Singh:** interesting like I I love this company goodfire so they use

**Hemanth Sarabu:** Goodbye.

**Pratyaksh Singh:** uh they're doing like very good work they use XAI to come up with ways uh you can understand your model how it's making prediction and then with that you can

**Hemanth Sarabu:** Very interesting.

**Pratyaksh Singh:** take informed decisions.

**Hemanth Sarabu:** Very

**Pratyaksh Singh:** So yeah,

**Hemanth Sarabu:** interesting.

**Pratyaksh Singh:** this is like this is I think silico what they have this is for LLMs or even for smaller models too where it's mostly just sparse autoenccoders they'll use sparse autoenccoders to come up with ways but it's like chat background so you can see where and if if you look if you'll go through their blogs they have they've done good work with some companies

**Hemanth Sarabu:** Interesting. Interesting.

**Geoff Horowitz:** Um, I need some time. How are you done with

**Pratyaksh Singh:** Yeah, I'm finished with my

**Geoff Horowitz:** your

**Pratyaksh Singh:** object.

### **00:49:49** {#00:49:49}

**Hemanth Sarabu:** Oh,

**Geoff Horowitz:** Okay.

**Hemanth Sarabu:** interesting.

**Geoff Horowitz:** Um, first of all, I shared a uh this just might be interesting to you guys. I shared a message that Bridget sent this morning. Um, share my screen here. Um, so Bridget said they found another, this is a Swedishmade mine. Um, Rockin is a a Swedish guess explosive company or something. Um, MLO mine like object. So,

**Hemanth Sarabu:** What does sketchy confirmation

**Geoff Horowitz:** I don't know.

**Hemanth Sarabu:** mean?

**Geoff Horowitz:** I think it means that she's not confident, but to me, this picture looks pretty confident. So, um,

**Hemanth Sarabu:** So, So to someone that is is it I guess my question the question behind my question is is this sensitive?

**Geoff Horowitz:** What does that mean?

**Hemanth Sarabu:** We should be discussing now someone says sketchy confidence sketchy

**Geoff Horowitz:** Oh.

**Hemanth Sarabu:** confirmation. I'm thinking I haven't actually told you this but I'm telling you this.

**Geoff Horowitz:** Oh, okay.

**Hemanth Sarabu:** That's all.

**Geoff Horowitz:** Well,

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** I guess I guess don't repeat it then.

### **00:51:24**

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** But then again, she shared it with us.

**Hemanth Sarabu:** Yeah, that's what I'm impressed by.

**Geoff Horowitz:** Uh but

**Hemanth Sarabu:** Let's stop recording this for this part of the conversation.

### **Session ended after 00:51:33**

### **00:54:37**

**Geoff Horowitz:** so the other things I wanted to talk about were specifically about wrapping up milestone 2\. uh a lot of things we've been discussing are going to go toward milestone 4 with you know the additional inclusion of all the synthetic data. Um what do we need to wrap up milestone 2? Uh so um have a little table here. Okay. Um, so Sachin, um, I think you were putting together slides for comparing some of the old performance with the new performance. I'm going to jump past this one quickly because I still think there's some more models that we want to be able to get um, data on. Have you Sachin have you finished the kfold validation or is there still it's still in

**Sachin Pandey:** It's still in

**Geoff Horowitz:** training?

**Sachin Pandey:** training.

**Geoff Horowitz:** Um, so I think we'll want to be able to look at those results and at least have an understanding about um how sensitive the model is to various training sets.

### **00:56:31**

**Geoff Horowitz:** I mean I I also think that'll give us some insight into the benefits of additional data. Um for the synthetic data we discussed including cut and paste for the objects uh my understanding is that is not in this thing that I'm calling the V40 model. Uh what do I mean by do you guys know what I mean by that?

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Okay. Uh I'm gonna add it here just for everybody else. Um, so we should have another model that includes the additional cut and paste objects which I think we already have but then we can compare those results to the V40 model. Um hopefully they improve. I would expect they hopefully do. Uh that's going to be good enough for Milestone 2\.

**Hemanth Sarabu:** Geoff, are you using Obsidian?

**Geoff Horowitz:** I come on you would laugh at me.

**Hemanth Sarabu:** Crazy.

**Geoff Horowitz:** I'm using everything under the

**Hemanth Sarabu:** You're using actually everything.

**Geoff Horowitz:** sun.

**Hemanth Sarabu:** The Google Docs, Notion, Obsidian.

**Geoff Horowitz:** I'm using every I'm using everything. I use I use obsidian.

### **00:57:56**

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** I use obsidian for um the age of one

**Hemanth Sarabu:** anything LLM related. I actually like obscene way better than notion. I'm just Oh, we lost Jeff. Didn't know Sweden made bombs to Sweden. Uh I think Sweden is a pretty um I think they're a significant like defense technology. They're a defense supplier. I think India gets a bunch of used to get a bunch of stuff from there. There's also the scandal back in the early '90s. I think it was sweet Sweden related for

**Geoff Horowitz:** Okay. Can you guys hear me now?

**Hemanth Sarabu:** sc.

**Geoff Horowitz:** Um, so yeah, he was I'm using everything. I'm using Obsidian for my for my agent. Uh but then like I use notion for my own notes and then we all use Google Drive.

**Hemanth Sarabu:** Nice.

**Geoff Horowitz:** So yes, I I I I found something that works but I don't think it's um replicatable. So anyway,

**Hemanth Sarabu:** I see.

**Geoff Horowitz:** um so where where are we on that?

### **00:59:24** {#00:59:24}

**Geoff Horowitz:** I uh I I this was a model that we had discussed. Have we trained it yet? Is it in the works? Is this something we need to do? I think R tool you were working on on a lot of this cut and paste data with Protap. Is that right?

**Ratul Shashank:** Yeah, but I I gave a small set of images to search in for validation but uh not on a big scale. So that is an open item.

**Geoff Horowitz:** putting it on a big scale. What do you

**Ratul Shashank:** Yeah.

**Geoff Horowitz:** mean?

**Ratul Shashank:** I mean I just uh I shared a few images I think uh eight or 10 images which has the cut and paste objects on the backgrounds for such in to test if these are even detecting if if the model is even detecting those objects or not. So that uh nothing nothing much.

**Geoff Horowitz:** What what were the results of

**Ratul Shashank:** Suchin can share that uh that part.

**Geoff Horowitz:** that?

**Ratul Shashank:** He he ran the model on those data.

### **01:00:51**

**Ratul Shashank:** Uh I think the model was uh detecting false positives sorry false negatives more right such

**Sachin Pandey:** Is it for the cut and paste or the the one which you generate?

**Ratul Shashank:** cut and paste

**Sachin Pandey:** Okay. So Jeff the cut and paste data was like on the B sorry fold model which I put on the drive that was the same data where we were

**Geoff Horowitz:** Uh, hold on. For the for the cross validation model,

**Sachin Pandey:** like artificial

**Geoff Horowitz:** you included additional cut and paste data.

**Sachin Pandey:** data.

**Geoff Horowitz:** Is that what you're saying?

**Sachin Pandey:** Let me think. the data used to compare V4 versus K-fold V4 on a like by for a apple to apple comparison we used a different data set which uh Ratul shared and this was the data set the cut and paste on the background and model was detecting it but also there were few false negatives

**Geoff Horowitz:** I I I'm lost. Uh I'm lost. I'll show you why I'm lost. So the V.

**Sachin Pandey:** So do you remember the artificial data which we are using to test out the models and we dropped it because they have a

### **01:02:31** {#01:02:31}

**Geoff Horowitz:** Do I remember the artificial

**Sachin Pandey:** few like the ground was not perfect.

**Geoff Horowitz:** date?

**Sachin Pandey:** There were UXs which were not marked in the ground truth.

**Geoff Horowitz:** I don't recall this data set.

**Sachin Pandey:** Okay.

**Geoff Horowitz:** You're saying we had a data set that had artificial data in it,

**Sachin Pandey:** So if

**Geoff Horowitz:** but not all the UXOs's part.

**Sachin Pandey:** Yeah. Yeah. Because like the ratul used to generate the UXO and draw draw the annotation. If the base image already has a UXO present in it, those annotations were not copied over. So those were the areas where which those that miss that mismatch caused the like issue.

**Geoff Horowitz:** Ah, I I do vaguely recall you saying about This I think I think a week ago. I think last Friday.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** And then you said that Ratul is fixing

**Sachin Pandey:** Yes.

**Geoff Horowitz:** that.

**Sachin Pandey:** In short the performance was decent like not much better but we were detecting the UXOs.

**Geoff Horowitz:** Okay. I we we just said a lot of things.

### **01:03:41** {#01:03:41}

**Geoff Horowitz:** So let me let me repeat at that. We did train a model with cut and paste and the model results were no,

**Sachin Pandey:** No mod model was not trained on it.

**Geoff Horowitz:** we did not.

**Sachin Pandey:** It was just for testing. We ran the model on the prediction sorry on the image. We didn't train any model on

**Geoff Horowitz:** I see I see what you're saying.

**Sachin Pandey:** this.

**Geoff Horowitz:** So, we included it in the validation set or the test set, whatever we're calling it now. uh but we did not include it in the training set. Okay.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** So let's let's simultaneously run a model where we include it in the training set.

**Sachin Pandey:** Okay. We we can we can train this one. Do we have enough data to like put it into training?

**Geoff Horowitz:** I mean let's let's make more right look. I mean this isn't so different than like the normal augmentations that we usually do.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** Um right so I don't think this is like a very novel approach which is

### **01:04:45** {#01:04:45}

**Sachin Pandey:** Yes.

**Geoff Horowitz:** why yeah that's it. Um so we should be able to generate a lot of like UXOs. Um excuse me. There was one concern about that them not blending correctly, but pract is is that a is that going to be a concern here? Do we need to deal with the blending right

**Pratyaksh Singh:** No, no,

**Geoff Horowitz:** now?

**Pratyaksh Singh:** no. I think I think it blends. Blending is fine.

**Geoff Horowitz:** It blends well.

**Pratyaksh Singh:** I think Sachin the your V4 you remove the augmentation for of direct copy paste, right? So that is why it is not robust to the copy pasting augmentation

**Sachin Pandey:** Yes.

**Pratyaksh Singh:** in in the in that data set. This is why I want to look at uh it is important to look at the K-fold validation so that we can know if uh V3 and V4 where it is doing better where it is underperforming.

**Geoff Horowitz:** Do you have any preliminary results from the cable

**Sachin Pandey:** Yes.

**Geoff Horowitz:** train? Have you already shared those?

### **01:06:32** {#01:06:32}

**Sachin Pandey:** Uh, no, I haven't shared it right now.

**Geoff Horowitz:** Okay. Can you share it quickly?

**Sachin Pandey:** Yeah. So we trained like four different model. Let me share the screen as well. So instead of choosing one like one model and training all the fold, I pick one fold and train all the model in it. So the the namings are like this where the m is the model one will be the like what type of config it is and next one will be the fold like what type of fold it is. So these are all the like four one is the config for fold one and similar to all the models. So if we see like V4 with argumentation is giving us the best recall but uh struggling with precision and the base V4 is very bad and we the reason was it's overfitting. uh we will be training like these models on different folds as well to get a better idea like how it's changed when the data set base data is changed. But till now like we have uh these are the

### **01:08:03**

**Geoff Horowitz:** Which what was the a I don't know if you just said this.

**Sachin Pandey:** results.

**Geoff Horowitz:** What was the augmentation on um M4?

**Sachin Pandey:** It was like all the image fragmentation which we decided on. So

**Pratyaksh Singh:** uh those that are color based augmentation. Okay. So Jeff these are augmentation like adding noise uh changing the color those kind of

**Sachin Pandey:** yes,

**Pratyaksh Singh:** things the standard augmentations.

**Geoff Horowitz:** Okay. Okay. Okay. So, we're saying that without any augmentations we're uh overfitting on the data. With augmentations, we're getting reasonable results.

**Sachin Pandey:** Yes, because like uh V4 is penalizing more for like false negative. So with augumentation model is able to pick the base like pick the pick the base pattern instead of overfitting. So that's why that's the reason we are getting like much better like matrix for with P4 with argumentations.

**Geoff Horowitz:** Okay. 90% recall.

**Sachin Pandey:** decision is tied. We made few changes in the uh split also. The latest split look like this like simple grid by grade approach where we like drop the base data based on the maps and without any padding.

### **01:09:48** {#01:09:48}

**Sachin Pandey:** padding was adding a lot of black areas which we removed it.

**Geoff Horowitz:** Right.

**Sachin Pandey:** So that

**Geoff Horowitz:** When when do you expect training to be

**Sachin Pandey:** uh it's just taking

**Geoff Horowitz:** done?

**Sachin Pandey:** longer I think one or two days uh

**Hemanth Sarabu:** Two

**Pratyaksh Singh:** such a reduce the number of epochs.

**Sachin Pandey:** like h yeah

**Hemanth Sarabu:** is.

**Sachin Pandey:** uh some are training like faster like uh M2 and M1 these are training faster but the growth both in like M3 and M4.

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** Uh I'm looking for the time.

**Geoff Horowitz:** What do you think is going on with these precision numbers?

**Sachin Pandey:** Oh,

**Geoff Horowitz:** I mean, you think about

**Sachin Pandey:** once more models were trained,

**Hemanth Sarabu:** So let me ask you guys this.

**Sachin Pandey:** we can visualize them.

**Hemanth Sarabu:** Okay. So what is our odd like um UXO like precision recall? So let's say there's a class which is uh I guess okay you have object F1 okay you have object precision recall

**Sachin Pandey:** object. Oh no.

### **01:11:44** {#01:11:44}

**Hemanth Sarabu:** so UXO AI big black patch are all UXO labels. Is that

**Sachin Pandey:** Yes,

**Hemanth Sarabu:** right?

**Sachin Pandey:** UXO and AI black are all UXO like out there.

**Geoff Horowitz:** but a big and black patch are different.

**Sachin Pandey:** Yes,

**Geoff Horowitz:** No

**Sachin Pandey:** UXO small black and uh UXO. These are the two class which looks similar. Ay big are the wind wheel base and black patch are like random black random black things and plus the supports for the windmill.

**Hemanth Sarabu:** I want to understand what is uh what does our confusion matrix look like for UXO like classes, non-UXO like classes and background. You get what I mean? Because that is what they will care about.

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** That is the story we will tell them. We like these are all things that look like UXOs and our model thinks they look like UXOs. These are all things that are clearly not. And one of them, let's say clear example is sand patches. And we never think sand patches are UXOs and background, right?

### **01:13:04** {#01:13:04}

**Hemanth Sarabu:** These are the three buckets they'll care about.

**Sachin Pandey:** So this can be better explained with these. So these are the a prediction on the new data that we got. And if we uh let me just a small is uh yellow and uo is pink. So so the objects we are classifying like it have a like a little bit of features that that we were trained on.

**Hemanth Sarabu:** What are you saying?

**Sachin Pandey:** So it's like it's not like so if you see

**Hemanth Sarabu:** What is your What is your statement? What's your headline?

**Sachin Pandey:** like the green one is the which they have marked which I think is not aligning well but model is picking up. So these both look similar and even if you trust like suppose this is this will be there we are

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** only marking it marking one but this is also looking like similar to UXO and model is classifying it.

**Hemanth Sarabu:** Yep.

**Sachin Pandey:** So,

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** so the conclusion was that as you said like UXO like objects are only getting classified as UXO.

### **01:14:21**

**Sachin Pandey:** It's not like random background objects are

**Hemanth Sarabu:** Okay. All right. Okay. So, we that is the story we need to tell.

**Sachin Pandey:** classified.

**Hemanth Sarabu:** But we need metrics. Would it be possible for us to generate metrics? Uh three buckets. UXO. Uh well, let's say four. UXO like um actual UXO, nonXO like and background.

**Sachin Pandey:** UX. So like non UXO will be background, right?

**Geoff Horowitz:** Well, 9 UXO could be AOI big.

**Hemanth Sarabu:** Um the back.

**Geoff Horowitz:** It could be U black.

**Hemanth Sarabu:** Yes.

**Geoff Horowitz:** What's it called? Black area.

**Hemanth Sarabu:** Such an background is its own thing. Okay. Background is its own thing. If we call I don't consider if we're segmenting sand patches. I don't consider background is anything that we are not supposed to be pulling out. We are not supposed to be segmenting it. So put that treat that on its own. Right? You follow?

**Sachin Pandey:** Yeah, like if objects are like UXO like which it is pulling from background then

### **01:15:41**

**Hemanth Sarabu:** What do you mean it's pulling from background?

**Sachin Pandey:** so These are not good example. But if suppose there is a there was a like feature which was not in the background but looks like UXO. It was not classified anything. It was just

**Hemanth Sarabu:** But okay, it but okay.

**Sachin Pandey:** background.

**Hemanth Sarabu:** So let me see if I understand it correctly. There is a picture there. There's a there's a there's an image. There is a UXO like object and the model is picking it up and then but why hasn't it been tagged

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** as a UXO like object? It must have been tagged, right? We must have annotated that. That is a labeling issue, right?

**Sachin Pandey:** Uh we can get a better idea once we separated the groups with

**Hemanth Sarabu:** Okay. All right. Okay. So, these are the three large groups.

**Sachin Pandey:** images.

**Hemanth Sarabu:** Okay. UXO like not UXO like

**Sachin Pandey:** Now I'm going to show

### **01:17:13**

**Hemanth Sarabu:** background.

**Sachin Pandey:** you.

**Geoff Horowitz:** So, we only have four classes, right? We have AOI small black,

**Sachin Pandey:** Yes.

**Geoff Horowitz:** we have AOI big, and we have black patch in UXO. So, the nonUXO is just AOI big and black

**Sachin Pandey:** Yes.

**Geoff Horowitz:** patch.

**Sachin Pandey:** Nonexos which we are classifying as UXOs.

**Geoff Horowitz:** Say that once

**Sachin Pandey:** Nonexos objects like black patch or a bit big which we are classifying as

**Geoff Horowitz:** more.

**Sachin Pandey:** UXOs.

**Geoff Horowitz:** Is that what you were asking for? Ha.

**Hemanth Sarabu:** Oh, so

**Geoff Horowitz:** Were you asking for the false positives?

**Hemanth Sarabu:** Um,

**Geoff Horowitz:** Or were you asking for what are the metrics on you know these other two

**Hemanth Sarabu:** let me hold on.

**Geoff Horowitz:** classes?

**Hemanth Sarabu:** Let me let me draw it out. So, here's the story we're telling these guys.

**Geoff Horowitz:** Okay.

**Hemanth Sarabu:** Okay. The story is uh again bedrock we don't have a lot of UXO uh UXO um examples.

**Geoff Horowitz:** Samples

**Hemanth Sarabu:** Okay, what we have are UXO like examples a lot of them.

### **01:18:53** {#01:18:53}

**Hemanth Sarabu:** So we have let's very simply we have three buckets okay where and this is the this is UXO like UXO like not UXO like and background okay and this is the confusion matrix for it not UXO like and background by the way we'll have multiple confusion matrices here what we want to what we really want to see is this is great. This is very high. Okay, we and we don't want to see anything here and here. We don't want to see anything here and here. Okay, now of course we want similar performance in here too.

**Sachin Pandey:** These

**Hemanth Sarabu:** But this is most important. We don't want to um these are so different as categories UXO like and not UXO like that there should be basically zero

**Sachin Pandey:** are

**Hemanth Sarabu:** zero values here in this confusion matrix you guys follow does that make sense?

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** Okay. That is what we want to show. Now I'm not going to talk about these other boxes. Uh this is this is number one.

### **01:20:09**

**Hemanth Sarabu:** This is what we want to present this confusion matrix. Now you may zoom in. You may zoom in into this area and you will have in here a confusion matrix that basically looks like true UXOs. Okay. And not true UXOs. Basically labeled as UXO and not labeled as. And now same thing true UXO and not true UXO. And now this confusion matrix is going to look terrible. You follow me? And in here we actually want a very high recall

**Sachin Pandey:** Yeah.

**Hemanth Sarabu:** meaning uh let's call this ground uh

**Sachin Pandey:** Okay.

**Hemanth Sarabu:** what is what is the actual uh let's say this is ground truth and this is predicted. Okay. So I want high high recall or true UXO which means the ground truth is UXO uh and predicted is UXO. Uh, so I want this to be high and I want this to be high. This is a high recall situation for true UXO, right?

**Sachin Pandey:** Okay.

**Hemanth Sarabu:** You follow? Okay.

### **01:21:29**

**Hemanth Sarabu:** Now, I want uh you okay, you get where I'm going where I'm going with this? At this level, we want to say these UX like objects all look the same.

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** So, but as long as you are within that those boundaries, those classes, excellent performance. Now, these other objects look very different. our model is able to tell that they're very different and they puts it into those buckets. Under true UXO, it is very difficult and so and so but our goal is recall. So these two are very high, but our precision is unfortunately low. It's unfortunately low. If we can bring this up too,

**Sachin Pandey:** You

**Hemanth Sarabu:** that'd be great. But uh our I guess uh uh this is the wrong direction.

**Sachin Pandey:** guys

**Hemanth Sarabu:** I guess uh unfortunately this is high and uh this is low, right?

**Sachin Pandey:** basically all the

**Hemanth Sarabu:** This is basically a high recall situation for true UXOs and a low precision uh situation for true UXOs. You follow? Let me see if I if I said this correctly.

### **01:22:37** {#01:22:37}

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** Ground truth UXO should be predicted should be high. And what I'll what I'll say is I'll call this like this should be high ground truth exo predict predicted uh true yes and then we predict true exo for nonuxo2 I mean this is not ideal but this is what we expect right this is a high recall situation this is what we'll be

**Sachin Pandey:** Yes, that's that's what we are

**Hemanth Sarabu:** showing correct and then I I know this should not be

**Sachin Pandey:** getting.

**Hemanth Sarabu:** uh yeah I I don't think that should be green that's not what is desired but it is unfortunately what we're getting uh this is a high high recall situation for true UXO and the expense and the reason we're able to do that is because ground truth not really UXO also we're putting it as true UXO so this will go down and then ground truth true UXO but we are saying not UXO This should be low. Okay. So, I'm going to actually color this uh green and like that. So, this is what we're This is what's going on.

### **01:23:54**

**Hemanth Sarabu:** Okay. Let me explain.

**Sachin Pandey:** It should

**Hemanth Sarabu:** We should be at this level. They should be nearly perfect like true UXO like objects and what we predict as

**Sachin Pandey:** be

**Hemanth Sarabu:** UXO like objects should be near perfect. We should have very high precision and recall. The other ones also should be near perfect, right? We should basically see tick marks like that. The other one's off off diagonal should be near zero. You follow? You guys follow? Okay.

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** Zooming in to UXOs. We because we are recall. We are focusing on recall. High value up here. Uh low value down here is important. And then the tradeoff for that is you you might have some high values here and low values here. I think that is right. Yeah. Yeah. I think that's right. Okay.

**Sachin Pandey:** Can you put put some numbers?

**Hemanth Sarabu:** Does that make sense?

**Sachin Pandey:** So suppose like right now so for

### **01:25:02**

**Hemanth Sarabu:** I I can't put numbers like

**Sachin Pandey:** uso we have like we can use the current matrix that we have for true positive at least. So we have uh recall of 80%

**Hemanth Sarabu:** Which where this matrix or this matrix here?

**Sachin Pandey:** in the above

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** one

**Hemanth Sarabu:** Which uh which okay let's let's say this is 1 2 3 1 2 3\. Okay. Which row which column do you want me to put those numbers?

**Sachin Pandey:** like two three columns will be like filter out based on the false quality we have to QA We will be queuing the

**Hemanth Sarabu:** Sure.

**Sachin Pandey:** false positives and putting it into these categories. So we can't put a number right now on those.

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** I was a little confused about the zoom in uh matrix where so there are like two classes which looks like UXO. Ay small black and UXO. Where should the AI small black will be? And if object is classifying it as US small black sorry model is classifying it as

### **01:26:09**

**Hemanth Sarabu:** Mhm.

**Geoff Horowitz:** It it it depends where you're looking. That's what he's saying. On the upper on on the upper matrix,

**Sachin Pandey:** Um, I want

**Geoff Horowitz:** UXO light includes AOI small black and UXO.

**Sachin Pandey:** that.

**Geoff Horowitz:** on the lower matrix. He's he's split them out. Does that make

**Hemanth Sarabu:** Yeah. Let me uh let me give you an example of such.

**Sachin Pandey:** I mean,

**Hemanth Sarabu:** Okay,

**Geoff Horowitz:** sense?

**Hemanth Sarabu:** this up here is like uh is like

**Sachin Pandey:** yes.

**Hemanth Sarabu:** uh uh this is like a car, bicycle or a bike. Okay, car bike. Our model should be able to tell car and bike apart really well. you follow.

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** But then you can zoom into this and basically say how good is our model actually at differentiating cars. And this could be a let's call it a

**Geoff Horowitz:** Be a car.

**Hemanth Sarabu:** What car and

**Geoff Horowitz:** I was going to say car or truck, but

**Sachin Pandey:** Real car versus

### **01:27:25**

**Hemanth Sarabu:** truck okay let's say Kia and Hyundai let's

**Sachin Pandey:** car.

**Geoff Horowitz:** okay.

**Hemanth Sarabu:** just say that they look very similar. So maybe our model is not very good but let you know so this will not look as clean as

**Sachin Pandey:** Okay.

**Hemanth Sarabu:** this. So this is the difference. What that's what I mean by zooming in UXO like objects UXO like objects actually have two cate two subclasses true UXOs which bedrock is saying is UXOs AOI small I think AOI small I don't know if there are

**Sachin Pandey:** Yeah.

**Hemanth Sarabu:** more okay and this is a true UXO and this is the not not true

**Sachin Pandey:** Okay.

**Hemanth Sarabu:** UXO so I just used a placeholder name because I don't know how many not true UXO categories are

**Sachin Pandey:** Okay.

**Hemanth Sarabu:** You follow.

**Sachin Pandey:** Yes, if you go to the matrix uh if ground truth is non UXO and model is predicting not

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** nono why the arrow is down the lower

**Hemanth Sarabu:** The ground truth is not UXO.

**Sachin Pandey:** one

**Hemanth Sarabu:** Um, so that is good.

### **01:28:32**

**Hemanth Sarabu:** That is good. If it is actually not UXO and the model is predicting not UXO then at well the ideal situation is it should be high but we I don't believe we can do that because we because we are doing we are attempting to do this we're saying I want to actually this these arrows are confusing right sorry about the arrows guys the green all of this is hard. Okay. Um, how do I say this? Let's let's say uh what we want is we want to be high here and we want to be high here. We want to be low here and we want to be low here. Okay, you follow. Oh, we don't we don't get that. We don't get that because these are too similar.

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** So, what we get is we are going to get this and we are going to get this. This is what we are saying. I'm saying look my model is not good enough to separate so many scam calls.

### **01:29:33**

**Sachin Pandey:** See

**Hemanth Sarabu:** My model is not good enough to separate these. So I will generally predict everything is a true UXO. And you can't do this without taking a hit on this guy. And uh is it this guy too? Not this. No, this will this is fine. This will be low. You follow?

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** This is up, up, down, down. You're saying I want up up here.

**Sachin Pandey:** more.

**Hemanth Sarabu:** So somewhere else it has to be down. And that down is here.

**Sachin Pandey:** Okay,

**Hemanth Sarabu:** You swapped these two.

**Sachin Pandey:** I get it.

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** It will be clear once we got the images and count.

**Hemanth Sarabu:** Now, sure. I'm going to take a screenshot of Uh maybe it'll be useful. I'm going to put it on Slack. Okay. Done. So, do you do you understand what we want to report?

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** Great.

**Geoff Horowitz:** Okay, I want to jump back section for one second to what you were showing before.

### **01:31:13** {#01:31:13}

**Geoff Horowitz:** Um, I think it was that table down at the bottom. Here's so here's where my concern was. you know, if we're showing great recall time, but if if the precision is so low, and I guess we'll see this on the on the confusion matrices, if the precision is so low, the story there is almost like we're just predicting everything as a UXO, right? Everything. And if we're predicting everything, then of course the recall is going to be good because everything gets predicted as US UXO. And and I think that's that's where my concern is coming from where, you know, on our V40 model, we at least have reasonable enough precision that we're not just saying that the model isn't looking at, you know, everything and saying, hey, if it if it looks like anything, it's fine. Um, I'm sorry that wasn't clear. If if if there's any kind of deviation in the image, then we're going to mark that up, which is almost what this M41 model is looking at.

**Sachin Pandey:** Thank

**Geoff Horowitz:** But if you go back to the one you were showing before with a,

### **01:32:34** {#01:32:34}

**Sachin Pandey:** you.

**Geoff Horowitz:** you know, 50% precision, that at least gives us some confident that the model is being more selective. Um, at least that's making sense in my head. So, so I guess that's something to keep in mind as we go forward.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** But again, I I uh I think the confusion matrices that Hamoth just proposed will help give us some insight there. Um, I guess you know don't don't stop once you've produced those matrices. like think about what those matrices mean. Um, you know, and what what we might need to do to fix them if there's

**Sachin Pandey:** Yeah, like high recall is good but if we are pointing everything as a like

**Geoff Horowitz:** issues.

**Sachin Pandey:** false everything is a UX. So then like it's it will be hard for them like blind because they have to like manually verify each of

**Geoff Horowitz:** Right. Exactly. it suddenly doesn't become a meaningful um prediction

**Sachin Pandey:** them.

**Geoff Horowitz:** anymore, right? Okay. Okay. Um so let me just summarize here to wrap up this milestone.

### **01:34:10** {#01:34:10}

**Geoff Horowitz:** I think we need to finish the cross validation metrics. make sure we're comfortable with those. Um, we'll have a model where we've incorporated the the um cut and paste data and training. I expect that model to be a little bit better uh to show a little bit better results, but I mean I guess we never know at the end of the day. Um, okay. And then the last thing is I think that we need to be comfortable with our model's performance on this um Treasure Island data set, this new data set that she just gave us. uh you know we there's some ambiguity here because you know maybe their their their identifications aren't right either right so so we're going to kind of have to go through this but I do think that we want to be comfortable with our performance on that data set so if we can get those three items I think we're good to close out the milestone um thoughts questions comments concerns anything on

**Sachin Pandey:** So any any improvement in this model will be like shipped in the milestone 3 or milestone 2\.

### **01:35:43** {#01:35:43}

**Geoff Horowitz:** Say that one more.

**Sachin Pandey:** So if we get a better model from like these kfolds that will be in like we will share it in milestone 3 or milestone 2\.

**Geoff Horowitz:** So the the kfolds aren't unless I'm misremembering something Sachin the the cross validation that we're doing it's not a different model from the V40 model right it's still the same model we're just getting more insight into how it performs uh into into how sensitive it is two different training sets.

**Sachin Pandey:** Yeah, but we added we added a one more model just for testing.

**Geoff Horowitz:** Does that make sense?

**Sachin Pandey:** So like V4 arugumentation is uh let's say it's a newer

**Geoff Horowitz:** We added is a newer model. Okay. So,

**Sachin Pandey:** model.

**Geoff Horowitz:** so then I think we want to look at that at the end of the day and if if the V4 augmentation is better then we we would want to use that. But do you understand what I'm saying that the the cross validation doesn't the cross validation

**Sachin Pandey:** Yes. Yes.

**Geoff Horowitz:** isn't training a different model it's just giving at the end of the day the model that we use will be trained

### **01:36:53**

**Sachin Pandey:** Just a different data.

**Geoff Horowitz:** on all of the data

**Sachin Pandey:** Yes.

**Geoff Horowitz:** right okay so the

**Sachin Pandey:** Yeah. So this is just to find out which like how well it's perform on varieties of

**Geoff Horowitz:** cross

**Sachin Pandey:** data.

**Geoff Horowitz:** yeah I mean maybe he has a better way of thinking about it. But that's how I think about it. It's like how sensitive is it to the specific training set that we're using or the validation set for that matter.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Okay.

**Sachin Pandey:** Uh one more update it was for the IACNA. So we are getting like 50% of the noise at like 99% accuracy but not able to capture all the points. There are still some tests left which we can do to improve it little more. But till now we have

**Geoff Horowitz:** um Sachin Sachin let's end this meeting and certain

**Sachin Pandey:** like

**Geoff Horowitz:** we want to talk about that is that

**Sachin Pandey:** Okay.

**Geoff Horowitz:** okay anything else to talk about this Pratyaksh anything that

**Sachin Pandey:** Yes.

### **01:38:11**

**Geoff Horowitz:** you any thoughts that you have about milestone 2 deliverables.

**Pratyaksh Singh:** uh not right now but I think I agree with you like once we have kfold results I'm sure that uh adding the copy paste augmentation at least should give us better result in term of recall at least

**Geoff Horowitz:** Okay. Okay. Um, all right. So, Sachin, you basically you think that these results are going to be done this weekend, right? One day, maybe two. Okay.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** All right. Share them as soon as you can. We'll all look over them. Such, you look over them, too. You know, they should make sense to you. They should tell a really compelling story.

**Sachin Pandey:** Yeah. I will be looking like checking the ones which are getting like trained which are already trained and Try to improve them with each

**Geoff Horowitz:** Okay. All right. Nothing else from my end. Anything else anybody wants to bring up?

**Sachin Pandey:** No.

**Geoff Horowitz:** Okay.

### **01:39:39** {#01:39:39}

**Geoff Horowitz:** Um, road tool session. Let's uh I'll send out a link. Let's reconnect. Um, oh, one thing I forgot, Ratul. Um, this is not critical for milestone 2, but it is for milestone 3\. We're going to want to pick back up the MAG data. I think we left off where you were going to um you were going to see how your analysis of the mag data lined up with um the ground truth annotations.

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** Uh so I think at some point next week have you you have you finished that yet?

**Ratul Shashank:** I mean it's uh I I have not improved. So by finish that the final stage is that we are able to detect the objects with a little buffer in the uh location. So that is I have not gotten past that stage.

**Geoff Horowitz:** Okay, let's connect on this next week then. Um, and we can we can get the ball rolling on that again.

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** Okay.

**Ratul Shashank:** Copy.

**Geoff Horowitz:** All right, guys. Talk to you later.

### **Transcription ended after 01:41:28**

*This editable transcript was computer generated and might contain errors. People can also change the text after it was created.*