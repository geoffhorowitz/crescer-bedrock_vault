# **📝 Notes**

Aug 3, 2026

## **Iris Sync**

Invited [Sachin Pandey](mailto:sachin@crescer.ai) [Pratyaksh Singh](mailto:pratyaksh@crescer.ai) [Hemanth Sarabu](mailto:hemanth@crescer.ai) [Geoff Horowitz](mailto:geoff@crescer.ai) [Siddharth Soni](mailto:siddharth@crescer.ai) [Ratul Shashank](mailto:ratul@crescer.ai)

Attachments [Iris Sync](https://calendar.google.com/calendar/event?eid=NnNzMHVxNzk3MmJqZGVwNXFoN2J1Mjd1OTdfMjAyNjA4MDNUMTYzMDAwWiBnZW9mZkBjcmVzY2VyLmFp)

Meeting records [Transcript](https://docs.google.com/document/d/1KOgkMwk7hl5zuD_NDAy_Ezu6PGH3VdJKJem13puHdag/edit?usp=drive_web&tab=t.kq8d34kktm0p) [Recording](https://drive.google.com/file/d/12R-pZkGGLlZZmSRWu9fRKtjuZiWxvAPW/view?usp=drive_web) 

### **Summary**

The meeting finalized model testing milestones with updated validation strategies and synthetic data generation techniques for performance.

**Evaluating New Mission Data**  
Team prioritized qualitative assessment of model performance on new data over manual labeling. This approach avoids resource commitment until baseline capabilities are confirmed.

**Refining Cross-Validation Strategies**  
Discussions focused on implementing cross-validation by splitting data geographically to prevent leakage. The strategy establishes consistent signals for measuring improvements across model versions.

**Optimizing Synthetic Data Generation**  
The team finalized plans to use real backgrounds combined with generated foreground objects for training. Clustering algorithms were successfully implemented to isolate high-quality samples from noise.

### **Decisions**

## Aligned

* **New mission data evaluation strategy** The new mission data from Southern California will be used solely for model evaluation on the current model, with incorporation into training deferred until ground truth becomes available.

* **New mission data labeling requirement** The new mission data will be submitted to labelers to establish a quantitative performance benchmark for the model.

* **Milestone 2 results presentation approach** The Milestone 2 presentation will utilize the V4 model to demonstrate performance improvements by comparing it against the baseline model and the retrained S1 model.

* **K-fold cross-validation implementation** K-fold cross-validation will be implemented for model versions V1 through V4 to generate robust and verifiable performance metrics.

* **Milestone 2 model evaluation experiments** The experimental plan for Milestone 2 closure will involve rerunning models V3 and V4, alongside V3 with Torski loss, and evaluating these outputs using K-fold cross-validation.

* **Validation and training data strategy set** The validation set strategy is established to use the full ground truth dataset, while the training data will combine real backgrounds with synthetic foreground objects generated via a closed-source model, with real data used as a fallback strategy if necessary.

We've **updated the Decisions section** using your feedback.

Let us know what you think: [Helpful](https://google.qualtrics.com/jfe/form/SV_5bXzKQfylMIhSXc?isHelpful=True&entryPoint=decisions&confid=gvi7Xsno-pWPQPPbjfOvDxIUOBEBMgUIigIgABgECA&isGoogler=False) or [Not Helpful](https://google.qualtrics.com/jfe/form/SV_5bXzKQfylMIhSXc?isHelpful=False&entryPoint=decisions&confid=gvi7Xsno-pWPQPPbjfOvDxIUOBEBMgUIigIgABgECA&isGoogler=False)

### **Next steps**

- [ ] \[Geoff Horowitz\] Upload Data: Transfer the Southern California mission data to Wall-E. Notify Sachin Pandey once the upload is complete.

- [ ] \[The group\] Review Updates: Evaluate the synthetic data work updates and the open query provided by Ratul.

- [ ] \[Pratyaksh Singh\] Respond to Query: Reply to the open question regarding the synthetic data research.

- [ ] \[Sachin Pandey\] Prepare Presentation: Construct slides detailing model performance for the milestone 2 summary. Include information on false positives and negatives.

- [ ] \[Sachin Pandey\] Verify Models: Confirm the configuration and context of model versions 3 and 4 for the milestone report.

- [ ] \[Pratyaksh Singh, Sachin Pandey\] Implement K-fold: Develop the cross validation strategy and calculate performance metrics for all model versions.

- [ ] \[Pratyaksh Singh\] Onboard Colleague: Connect with Sid to provide a project status briefing. Assist with the transition of project responsibilities.

- [ ] \[Pratyaksh Singh, Sachin Pandey\] Evaluate Models: Re-run versions 3 and 4 along with the version 3 with Torski loss using K-fold validation. Finalize the comparison of results for model selection.

- [ ] \[Pratyaksh Singh\] Report Analysis: Analyze the clustered image text files and prepare a report on the findings for the upcoming Wednesday meeting.

- [ ] \[Pratyaksh Singh\] Generate Foreground: Develop the foreground generation method using the identified approach and provide a progress update on Wednesday.

- [ ] \[Pratyaksh Singh\] Finalize App: Complete the final setup for the EMD application.

- [ ] \[Hemanth Sarabu\] Contact Ulyses: Follow up with Ulyses via text message regarding the previous email.

- [ ] \[Sachin Pandey\] Setup Agent: Configure the agent to procedurally generate background and foreground objects based on the agreed categories.

### **Details**

* **Southern California Mission Data**: Bridget provided data from a recent mission off the coast of Southern California, which includes approximately 2km by 2km of coverage ([00:02:27](#00:02:27)). The dataset contains nearly 300 side-scan XTF files with over 1,000 real-time contacts. Although the data lacks ground truth, Geoff is currently downloading the files to upload to Wall-E, with plans to perform an initial deep dive and inference run using the current model to evaluate performance ([00:04:26](#00:04:26)).

* **Labeling Strategy**: There was a discussion regarding whether to label this new dataset to improve evaluation accuracy. Pratyaksh advocated for labeling to increase the validation data, while Geoff suggested running an inference pass first to assess current capabilities before committing resources to manual labeling ([00:05:56](#00:05:56)). The consensus is to prioritize a qualitative assessment of the model's performance on this data first ([00:04:26](#00:04:26)) ([00:07:08](#00:07:08)).

* **Data Features and Identification**: The team reviewed the nature of the contacts found in the new dataset ([00:08:34](#00:08:34)). Sachin noted that some features resemble rocks rather than UXOs and that the high-resolution, processed nature of the images makes visual identification difficult. The team acknowledged the challenge of differentiating between actual UXOs and background features in the absence of ground truth ([00:11:29](#00:11:29)).

* **Data Access and Viewing**: Geoff confirmed that the Bedrock "Mosaic" application is the appropriate viewer for this data ([00:16:25](#00:16:25)). Access to the Mosaic site is available to both Sachin and Geoff, and they confirmed the presence of various open-source datasets within the application ([00:14:51](#00:14:51)).

* **Milestone 2 Wrap-up Objectives**: To finalize Milestone 2, the team outlined a plan to demonstrate model improvements ([00:20:35](#00:20:35)). The presentation will feature three specific performance proofs: the baseline performance of the Statement of Work 1 model, the improvements seen in the retrained Statement of Work 1 model, and the substantial performance gains demonstrated by the V4 model ([00:23:07](#00:23:07)).

* **Model Augmentation Strategy**: Sachin explained that augmentation was previously removed from the V4 model because it led to increased false positives and reduced recall. Moving forward, the team plans to verify the quality of any images before incorporating them into training, specifically intending to use verified cut-and-paste augmentations to ensure high input quality ([00:19:19](#00:19:19)) ([00:27:02](#00:27:02)).

* **K-Fold Cross-Validation Status**: The team is working to implement K-fold cross-validation to mitigate issues caused by the limited size of the validation set ([00:28:38](#00:28:38)). Previous attempts yielded poor results due to the inclusion of incorrect ground truth data in the test set, but Ratul is currently addressing this, with a resolution expected by tomorrow ([00:32:04](#00:32:04)).

* **Implementation of K-Fold Validation**: Discussions regarding K-fold validation focused on the importance of avoiding data leakage. The team discussed the need to use this method not just for validation but to provide a consistent signal on whether model changes result in genuine performance improvements ([00:34:22](#00:34:22)). There was agreement that metrics should be averaged or compared across folds to achieve reliable results ([00:38:19](#00:38:19)).

* **Geographic Data Splitting Strategy**: To prevent data leakage during K-fold validation, the team discussed splitting the UXO data based on geographical location and unique identifiers ([00:39:33](#00:39:33)). Sachin plans to use a mixture of area-based and ID-based grouping to segregate the data into five distinct folds, ensuring that each validation set contains unseen samples ([00:46:11](#00:46:11)).

* **Milestone 2 Execution Plan**: The team finalized a plan to rerun models V3 and V4 to finalize Milestone 2\. This includes testing V3 with the Torski loss function used in V4 and applying cut-and-paste augmentation to the training sets. This approach is expected to provide enough flexibility to incorporate further synthetic data improvements in future milestones ([00:50:14](#00:50:14)).

* **Personnel Transition**: Geoff announced that Sid will return to Bedrock within the next few weeks. The goal is for Sid to take over most of the workload from Pratyaksh, allowing them to focus on other R\&D initiatives ([00:52:02](#00:52:02)). Pratyaksh and Sid will coordinate to get Sid up to speed on current projects ([00:53:39](#00:53:39)).

* **Synthetic Background Generation Model**: Pratyaksh shared updates on the background generation model, which utilizes flow matching loss ([00:52:02](#00:52:02)) ([00:57:03](#00:57:03)). The model has demonstrated good performance across datasets, including those with limited examples ([00:53:39](#00:53:39)). Experiments with classifier guidance weights showed that a weight of 1 preserved image quality, whereas higher weights distorted the output; additionally, 25 diffusion steps were found to be more effective than 10 for lower-representation datasets ([00:55:45](#00:55:45)).

* **Image Quality Clustering**: Pratyaksh identified that the generation process occasionally produced clusters of low-quality or noise images ([00:58:18](#00:58:18)). To manage this, a clustering algorithm based on ResNet 50 embeddings was implemented, which successfully identified and segregated these noise images from the usable generated examples ([00:59:52](#00:59:52)).

* **Training Data Clustering Plan**: Pratyaksh Singh reported that they have clustered the entire training set using features from a pre-trained model to identify unique examples. They plan to generate 100,000 synthetic examples, use embeddings to cluster them into groups, and then sample from these groups. Pratyaksh Singh committed to providing a report by Wednesday regarding the similarity between these clusters and the existing training examples ([01:01:36](#01:01:36)).

* **Synthetic Training Strategy**: The team's training strategy involves using only real backgrounds, with synthetic foreground objects integrated via a closed-source model. All area-of-interest data will be reserved for the validation set ([01:02:41](#01:02:41)). Pratyaksh Singh explained that Ratul is utilizing prompt engineering to describe objects to the closed-source model to guide the generation of synthetic examples, which will be combined with procedurally generated objects ([01:04:05](#01:04:05)).

* **Foreground Object Generation**: The team is adjusting their foreground generation approach by categorizing objects and providing specific examples to the model to produce similar results, as previous attempts at procedural generation were unsuccessful ([01:05:14](#01:05:14)). Pratyaksh Singh requested that Sachin Pandey set up an agent for this process, noting that if the agent fails to produce the desired results, they will need to explore alternative methods ([01:06:20](#01:06:20)). Pratyaksh Singh plans to provide an update on the foreground generation progress by Wednesday ([01:04:05](#01:04:05)).

* **EMD App Access**: Hemanth Sarabu requested functionality to access the EMD app and select images from a directory via a dropdown menu, rather than uploading images manually. Pratyaksh Singh agreed to complete the setup for this feature within 30 minutes ([01:06:20](#01:06:20)).

* **Validation Strategy**: The primary plan for validation is to use a fully ground-truth dataset. Pratyaksh Singh indicated that if a fully synthetic approach is unsuccessful, they will consider incorporating a mix of real and synthetic data into the training batches to improve performance ([01:07:15](#01:07:15)).

* **Administrative Updates**: Hemanth Sarabu noted that they sent an email to Ulyses regarding a pending matter and, as they have not yet received a response, they plan to send a follow-up text message ([01:08:22](#01:08:22)).

* **Model Performance and Data Experiments**: Pratyaksh Singh and Sachin Pandey reviewed experiment reports regarding the generation of objects on backgrounds ([01:08:22](#01:08:22)). They discussed comparing various model versions (V1 through V10) and testing different data splits (splits 1 through 5\) to evaluate accuracy. The team explored technical adjustments, including the use of focal loss and post-processing, and noted specific performance metrics, such as a 34% accuracy rate ([01:23:37](#01:23:37)) ([01:47:59](#01:47:59)). Throughout the discussion, they addressed ongoing issues with object generation, including instances where objects were produced at incorrect sizes or were difficult to identify ([01:09:49](#01:09:49)) ([01:42:25](#01:42:25)).

*You should review Gemini's notes to make sure they're accurate. [Get tips and learn how Gemini takes notes](https://support.google.com/meet/answer/14754931)*

*How is the quality of **these specific notes?** [Take a short survey](https://google.qualtrics.com/jfe/form/SV_5bXzKQfylMIhSXc?confid=gvi7Xsno-pWPQPPbjfOvDxIUOBEBMgUIigIgABgECA&detailLevel=standard&hasImages=False&entryPoint=footerMain&isGoogler=False) to let us know your feedback, including how helpful the notes were for your needs.*

# **📖 Transcript**

Aug 3, 2026

## **Iris Sync \- Transcript**

### **00:02:27** {#00:02:27}

**Pratyaksh Singh:** Hi

**Hemanth Sarabu:** Hey,

**Pratyaksh Singh:** guys.

**Sachin Pandey:** I have a texture. I

**Pratyaksh Singh:** How are

**Sachin Pandey:** just

**Geoff Horowitz:** Hey guys.

**Pratyaksh Singh:** you?

**Geoff Horowitz:** Uh, I think we can get started. Rul said he was not feeling well. Um, I think I think he had an open question to you, but I didn't read all of his updates yet. Um, see uh yeah, project he had Rul had an update on his synthetic data work and an open question for you. Um, I think we should all take a second and review that at after the meeting, but uh, project be sure to respond if you can. Um, Bridget Bridget reached out to me and said they did a uh another mission off the coast of Southern California. Um, she said they She said there there are Okay, they mapped this area. Um, it's approximately here she goes two 2 km by 2 km and they know that there are mineike objects in this data set. Um, they don't yet have the ground truth for the data that they collected.

### **00:04:26** {#00:04:26}

**Geoff Horowitz:** Um,

**Hemanth Sarabu:** Okay,

**Geoff Horowitz:** what was the question?

**Hemanth Sarabu:** I said okay.

**Geoff Horowitz:** Oh, they don't yet have the ground truth for that. Um,

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** she asked if we wanted her to share the data. I said, "Yeah, of course we want to share the data." I said, "We can use it for evaluation on the current model. Once they get the ground truth, we can incorporate that into training in a future milestone." So, I think that's altogether a good plan. Um, Sachin, I am downloading the data right now and I will upload it to Wall-E. I'll ping you when it's done and available. Um, she said she said there's just under 300 sides scan XTFs uh with real time contacts picked over a thousand. I don't know what this means. and our post-process narrowed down contacts, but they don't have the ground truth. So, we might have to dig through the data a little bit. Um, again, I don't necessarily think that we should use it for training right now, uh, unless we find that we're deficient, but I think it would be good to kind of deep dive run it through the current model, deep dive into the results that we get, and just qualitatively see how we're doing.

### **00:05:56** {#00:05:56}

**Pratyaksh Singh:** Why not get it labeled by the labels?

**Geoff Horowitz:** We can do that. I'm not I'm not opposed to it. Um, ultimately, I guess I don't trust I trust our labels that they look like what we think UXOs are. But I don't trust that what we think UXOs are are necessarily what UXOs are. Did you follow that

**Pratyaksh Singh:** I I get what you mean,

**Geoff Horowitz:** project?

**Pratyaksh Singh:** but the model the model will learn what we thinks are UXO what we think are UXO so it will predict that only right so I think we

**Geoff Horowitz:** That's true.

**Pratyaksh Singh:** are short on data if it has a lot of contact it will help us to either

**Geoff Horowitz:** I I Go

**Pratyaksh Singh:** increase I was saying it will help us to increase the

**Geoff Horowitz:** ahead.

**Pratyaksh Singh:** data as well as the validation

**Hemanth Sarabu:** Excellent.

**Geoff Horowitz:** I'm not opposed to it at all. Um I'm not opposed to it at all to get our labelers to to label this. I do think it would be good to use the existing model let me let me say this differently.

### **00:07:08** {#00:07:08}

**Geoff Horowitz:** I think it would be good to do a full like just inference on this data and just see how we're doing. Um, and then afterward incorporate the data into training if we do

**Pratyaksh Singh:** got it.

**Geoff Horowitz:** that.

**Pratyaksh Singh:** Uh, another reason was that if you can get it labeled first, what would happen is that we can just quantitatively have a number for how good we are doing, right?

**Geoff Horowitz:** I agree. I agree with you. Um, okay. I will. So, as I said, I'm It's

**Hemanth Sarabu:** How did they how did they um she

**Geoff Horowitz:** downloading.

**Hemanth Sarabu:** said with real time contacts picked so they picked over a thousand contacts our post-processing narrow down contacts Is that should I

**Geoff Horowitz:** Where are you looking?

**Hemanth Sarabu:** ask

**Geoff Horowitz:** Look with realtime contacts picks over a thousand or postp processing narrowed down contacts. You can't ask, but I figured we'd look through the data first.

**Hemanth Sarabu:** there.

**Geoff Horowitz:** Up to you.

**Hemanth Sarabu:** I'll think about

**Geoff Horowitz:** You want to ask? Go ahead.

### **00:08:34** {#00:08:34}

**Hemanth Sarabu:** it.

**Geoff Horowitz:** I don't know what does she have over a thousand contacts picked? Think so.

**Pratyaksh Singh:** If it has over a thousand contacts and it would solve a lot of our problems.

**Geoff Horowitz:** I don't think it does. I think there's probably a lot of I think the real time stuff has a lot of false positives there. She says postprocess narrowed down

**Hemanth Sarabu:** Quickly.

**Geoff Horowitz:** context. Actually, let me um say

**Hemanth Sarabu:** Um, I wonder if they're using Mac.

**Geoff Horowitz:** We know they use men.

**Hemanth Sarabu:** No, I mean process to pick real time.

**Geoff Horowitz:** I mean, it looks like they have their guess of what these of contacts, but I think she's not sure that these are actually contacts. You guys see?

**Hemanth Sarabu:** Do that

**Geoff Horowitz:** Uh, yeah. So, can you see my screen,

**Hemanth Sarabu:** again.

**Geoff Horowitz:** Hoth? I guess they have their This is probably all in the report, but I haven't finished downloading it yet. So, they probably have their guess of what contacts exist in this in this data.

### **00:11:29** {#00:11:29}

**Geoff Horowitz:** That's probably all these contacts first three days. Um, and then But they don't have the actual ground truth from the um from the US Navy. Like they don't know what are act what actually are contacts and what are not

**Hemanth Sarabu:** I'm good.

**Geoff Horowitz:** contacts. also project action. Looks like these don't actually line up exactly, right? They're probably looking at this guy and they've mapped it right there.

**Pratyaksh Singh:** Can I zoom out a bit? Does this look like another background?

**Sachin Pandey:** Yeah, like the shadows and the like something like a

**Pratyaksh Singh:** Yeah,

**Hemanth Sarabu:** Wait,

**Sachin Pandey:** rock

**Hemanth Sarabu:** do what do you mean by

**Pratyaksh Singh:** exactly.

**Hemanth Sarabu:** background?

**Geoff Horowitz:** this.

**Pratyaksh Singh:** I mean,

**Sachin Pandey:** but like it is not looking like a UXO. The features are looking more like a rock.

**Pratyaksh Singh:** it's

**Sachin Pandey:** If you see like the similar uh features are available all around it but just a little smaller. Yeah.

**Hemanth Sarabu:** You've now become a UXO expert. That's crazy.

### **00:13:17**

**Hemanth Sarabu:** You You're very valuable to the US Navy. Do you actually feel like do you think you got good at uh UXO

**Sachin Pandey:** But

**Hemanth Sarabu:** identification? And if so, what what are

**Sachin Pandey:** no, like it the features that we saw in like the previous data is not matching with these

**Hemanth Sarabu:** the

**Sachin Pandey:** ones.

**Geoff Horowitz:** So,

**Hemanth Sarabu:** not like you're looking at anything specific? You just like you're saying it looks different.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** I could be

**Pratyaksh Singh:** Hey, my problem is a bit different. Suchin,

**Geoff Horowitz:** honest.

**Pratyaksh Singh:** do you think it looks like like what is the closest data set it looks like in term of background like apart from the UXOS? Does it

**Sachin Pandey:** These like look like process data and in

**Pratyaksh Singh:** look

**Sachin Pandey:** DRN like process data because these are very clean and

**Pratyaksh Singh:** these? Looks

**Sachin Pandey:** high resolution.

**Pratyaksh Singh:** like

**Sachin Pandey:** They have like they did some processing on it.

**Pratyaksh Singh:** but DRN also maybe we can discuss this but the training data that I have seen in DRN it's not that high dimensional

### **00:14:51** {#00:14:51}

**Geoff Horowitz:** Um, I mean, Pratak ultimately this is this is my concern about incorporating it into training. I don't you know would we would we categorize this as a UXO? Would we categorize this as UXO? Each of these AOI small black you know

**Pratyaksh Singh:** Yeah. Yeah. I don't know what the labelers will even what guidelines you should give

**Geoff Horowitz:** I So,

**Pratyaksh Singh:** them.

**Geoff Horowitz:** so I think that gets to the core the core of it. I'm certainly not opposed to like labeling it and trying it out and seeing um but I do think it would be good to test

**Sachin Pandey:** I think we can yeah we can like get some good

**Geoff Horowitz:** it beforehand.

**Sachin Pandey:** idea with just the model predictions like what model is classifying.

**Geoff Horowitz:** Okay. Um, Sachin, I know you have access to this. You have access to the site. Um, Artex, do you have the login for all this

**Pratyaksh Singh:** I have the login for sorry

**Geoff Horowitz:** for the mosaics?

**Pratyaksh Singh:** repeat.

### **00:16:25** {#00:16:25}

**Geoff Horowitz:** If if you if you need the login for this mosaic site, this viewer here, if you think that'd be helpful, um has it or I have it. I'm sorry. Satchin has it or I have it.

**Pratyaksh Singh:** Okay. All right. All right. I'll let you know. I think it's working good with me with images. What if needed? Which app is

**Geoff Horowitz:** Okay,

**Pratyaksh Singh:** it?

**Geoff Horowitz:** this is Bedrock's like uh data viewer app.

**Pratyaksh Singh:** Okay.

**Geoff Horowitz:** It's called Mosaic. They um they built it. They have a whole bunch of open source data here.

**Hemanth Sarabu:** I think Sid has seen this,

**Pratyaksh Singh:** That's

**Geoff Horowitz:** Sid has seen it.

**Hemanth Sarabu:** right?

**Geoff Horowitz:** Uh Sachin I know dug into it a little bit.

**Sachin Pandey:** Uh, FMS is also a new data.

**Geoff Horowitz:** No, I think FMS was the role but hold on. So project you can see a lot of this is open source data that um Bedrock has. We looked at it.

### **00:17:39**

**Geoff Horowitz:** It's it it's pretty good data, but none of it has ground truth. Nothing here has ground truth even for um it even has a lot of uh multi-beam data on it, but no ground truth.

**Pratyaksh Singh:** So, can't we like we can get some data labeled? Bion only blood

**Geoff Horowitz:** F section FMS was the RO data.

**Pratyaksh Singh:** site.

**Geoff Horowitz:** FMS was the RO data

**Sachin Pandey:** Okay.

**Geoff Horowitz:** set.

**Pratyaksh Singh:** It's like if there are good public data set that they have, why not get it labeled by the labelers?

**Geoff Horowitz:** So we were we were kind of doing that with the iris data, right? The um um the point cloud data.

**Pratyaksh Singh:** Mhm.

**Geoff Horowitz:** I think it's I think it's much easier to do with land features than it is to do with subseek features. And I mean not not opposed to it, but it's what are we spending our time doing? That's the question, right?

**Pratyaksh Singh:** um because sides scan is I think faster to label and we need data set that's why we are moving towards synthetic data and all those things

### **00:19:19** {#00:19:19}

**Sachin Pandey:** So pax like you the model you are training you are not using the like any of the actual objects you are just using the background. So can't you just put all the data into the like training

**Pratyaksh Singh:** Yeah.

**Sachin Pandey:** set training set because we don't have any

**Pratyaksh Singh:** And do Yeah.

**Sachin Pandey:** annotation and I don't think there will be a UXO in it

**Pratyaksh Singh:** Mhm.

**Sachin Pandey:** so like then it will be mostly background

**Pratyaksh Singh:** Okay.

**Sachin Pandey:** Oh,

**Geoff Horowitz:** Uh, I still think It needs to be even if we did that it still needs to be look okay a few things. Number one I don't think we need to do this for this milestone to close out this milestone.

**Pratyaksh Singh:** Okay.

**Geoff Horowitz:** Number two um it would still need to be gone through by the labelers because we don't I mean Sachin you're saying like it probably doesn't have UXO or or a humanmade object but it might. Um and I think the one thing that we always adhere to is that the input quality of the training data has to be very high.

### **00:20:35** {#00:20:35}

**Geoff Horowitz:** Uh yeah, those are some of my thoughts. um have side scan data. Okay. Um we can get back to this. I don't think this even has this thing. These are empty folders. Uh let's let's let's get back to this. Let's talk about where we need to be to wrap up milestone 2\. Are you back?

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** Okay.

**Hemanth Sarabu:** Here.

**Geoff Horowitz:** Um, so Sen, go ahead. Go

**Hemanth Sarabu:** So, Jeff,

**Geoff Horowitz:** ahead.

**Hemanth Sarabu:** you mentioned uh we don't have a clear sense of uh what model is less and what pre-processing steps under

**Geoff Horowitz:** Um I think that we know that the Sachin step in here. I think we know the V4 model is about as good as we can get. We want to incorporate some synthetic data, some synthetic data, whether that's just cut and paste, whether it's additional backgrounds. In order to to wrap up milestone 2, we need to show them that we've incorporated some synthetic data. Um, I think what I don't know is what of the synthetic data has been incorporated, what hasn't, is it actually increasing results, is it making results worse?

### **00:23:07** {#00:23:07}

**Geoff Horowitz:** um soft project.

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** Go

**Hemanth Sarabu:** Yeah.

**Sachin Pandey:** So like I think we can like go ahead with the voer model.

**Geoff Horowitz:** ahead.

**Sachin Pandey:** So like we can make some slides like where the model is like making the false positive we can put the images like the false positive also look more like a UX. So it's not like randomly picking any objects and also the false negative are also very low. So if you want like we can I can prepare the slides which we can share for the milestone

**Hemanth Sarabu:** Okay. So the headline of that what you just said is basically

**Sachin Pandey:** too.

**Hemanth Sarabu:** B4 is a good model. How what is V4? How is it different? So we need to show I think there are two or three things we need to show. Okay. So let's introd uh please uh uh please just try to like follow along. One the baseline model so the SA one statement of work one that model how does that perform?

### **00:24:22**

**Hemanth Sarabu:** We know that performs poorly. So we we show that. Okay. Again on the same point we're showing that look you can't have the same model you need to keep retraining that's why you need creser so that is that is something we need to show and we're able to show that right we have the proof for it

**Sachin Pandey:** Yes, we can like show the prediction of the same on the same images.

**Hemanth Sarabu:** okay awesome number two is the retrain model from cell one only retrain And we want to show that it improves but not substantially. Okay. So it improves but not substantially. Um that is point number two. Point number three is there is a model with a bunch of XYZ tricks. It is better than the previous one I just mentioned which is a fine-tuned S one model. It is substantially better than that model. There's point number three we need to show now. Is that true? Do we have proof for that point? The third question.

### **00:25:37**

**Sachin Pandey:** Yeah. So that will be uh I will check the context but I guess V V3 will be the one which we can show. It was trained on the same uh pipeline as the S41 and with the updated data set and it was not performing as well as the one where we have like change the loss function and

**Hemanth Sarabu:** Okay, great.

**Sachin Pandey:** everything.

**Hemanth Sarabu:** So, V4. Okay. And then we say that's why V4 exists, right? So, that's point number three. So, we're happy up to this point. Is that right?

**Sachin Pandey:** Yeah.

**Hemanth Sarabu:** Okay. So, it sounds like we have enough for this milestone, but we don't want to be in a position where we potentially risk a future milestone where we're supposed to show even more improvements. And uh so to that question, do we is there more juice we can squeeze from any of the trips from uh augmentations, generative modeling, loss functions, anything else? How much more juice can we squeeze assuming we don't get more data?

### **00:27:02** {#00:27:02}

**Sachin Pandey:** uh like we have to test it out. For V4, we dropped the agmentation because it was introducing a lot of false positives mainly for like UXO.

**Hemanth Sarabu:** with no improvement in Here you go.

**Sachin Pandey:** Yes, recall was going like recall was very low with augmentation.

**Hemanth Sarabu:** That's

**Sachin Pandey:** Like if you remember the starting models the like precision were like decent but recalls were very

**Hemanth Sarabu:** interesting.

**Sachin Pandey:** good. like if we like put the argumentation as a image instead of just like uh which is done automatically then I think it will it will improve where like we are sure we are putting the images which are looking good

**Hemanth Sarabu:** I don't

**Sachin Pandey:** and with the correct like copy paste or any other argumentation we have Okay.

**Hemanth Sarabu:** I still don't follow. Can you elaborate?

**Sachin Pandey:** So like Ratul and Pat are working on like generating the like similar data right. So once that data is ready and we know like we are we will be putting the actual images into the data because

**Hemanth Sarabu:** Yeah.

### **00:28:38** {#00:28:38}

**Sachin Pandey:** we have verified that it is looking good uh and matching the actual data. So like if we incorporate these data uh then like I think performance will

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** Peace.

**Hemanth Sarabu:** protect you get silent. Uh do you have any thoughts

**Pratyaksh Singh:** Uh

**Hemanth Sarabu:** here?

**Pratyaksh Singh:** see I think the performance can increase but again my problem is with the small validation set that we're using at least for like uxs they're very small so I don't know how much we can That's

**Hemanth Sarabu:** Did we ever did we ever do the K4 cross

**Pratyaksh Singh:** fine.

**Hemanth Sarabu:** validation on these different model versions?

**Pratyaksh Singh:** Such you tried it out right careful cross validation.

**Sachin Pandey:** Yeah, I tried it out by changing the like their loss functions like how like reversing the one which we trained earlier.

**Geoff Horowitz:** Peace. Peace.

**Sachin Pandey:** So instead of and beta as 0.3 and 0.7 respectively. I inverted them. It was not doing like better than the first one.

**Hemanth Sarabu:** Um careful cross validation. Are we using it correctly?

### **00:30:20**

**Hemanth Sarabu:** Because our validation set is wrong like this.

**Sachin Pandey:** like whether the US represented correctly uh enough in all the five sets.

**Hemanth Sarabu:** So you guys remember we had a chat about if we have five folds you can compute uh metrics for each of those folds

**Sachin Pandey:** Yeah. If you train two model on the same like same five-fold data

**Hemanth Sarabu:** Yeah.

**Sachin Pandey:** set

**Hemanth Sarabu:** Did we ever do that?

**Sachin Pandey:** yeah like the new model which I trained the like the even the evaluation metrics were not reaching the one like reaching around the one which we trained

**Hemanth Sarabu:** I get it.

**Sachin Pandey:** earlier.

**Hemanth Sarabu:** I get it. My Okay. The question I'm asking is we don't have enough validation data. Are we leveraging something like Kfl validation to solve that issue?

**Sachin Pandey:** Uh, not right now.

**Hemanth Sarabu:** Okay. So project what's uh what's happening? Are we are we really blocked on low validation data? There's nothing we can do.

**Pratyaksh Singh:** I mean right now K4 cross validation is the only option to like get those numbers for the V4 model to get the actual number.

### **00:32:04** {#00:32:04}

**Pratyaksh Singh:** I think careful see this top I'll discuss with Sachin I think we'll implement something and then we can for all these V1 V2 V3 V4 we can get the metrics for people cross valuation

**Hemanth Sarabu:** question. Amen.

**Geoff Horowitz:** So, I thought we discussed this on Friday. This is where you said we had done the K-fold validation, but the the metrics were wonky, right? They they didn't they didn't look right. Something didn't add up. So, I thought you were going to work on that Saturday and and today. Um, now maybe Ulisses came up Saturday,

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** but did you get a chance to look at it

**Sachin Pandey:** No, like I the matrix was bad because of the like the test data,

**Geoff Horowitz:** today?

**Sachin Pandey:** the artificial test data, the ground root was not correct. So, Ratul is like working on it. He he told me like he will get it done by tomorrow. So once I get it,

**Geoff Horowitz:** Okay.

**Sachin Pandey:** I will just update

### **00:33:25**

**Geoff Horowitz:** Okay. So, so I think this was maybe the information that Hemoth was looking for,

**Sachin Pandey:** it.

**Geoff Horowitz:** right? So, so let me try to recap and you guys break in or correct. We we did try k-fold validation. We tried using the same model just with different validation sets. The V4 model with different validation sets, different folds.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** The we did something wrong, right? The metrics were bad. Sachin, what you're saying is what we did wrong was we actually included additional test data which was it turned out was bad data. Right.

**Sachin Pandey:** like we were evaluating the model on the bad data. So once we get the good data,

**Geoff Horowitz:** Right.

**Sachin Pandey:** we can get a better idea whether the V4 is working well or one of the Kfold is doing better than the V4.

**Geoff Horowitz:** Okay. So, we're still trying to do K-fold. The blocker is that Ratul was fixing up the data and he won't have it ready till tomorrow.

### **00:34:22** {#00:34:22}

**Geoff Horowitz:** Okay, he that's that's the summary you were looking for,

**Sachin Pandey:** Yes.

**Geoff Horowitz:** right?

**Hemanth Sarabu:** No, no,

**Geoff Horowitz:** Okay,

**Hemanth Sarabu:** my my the reason I brought up Kold is the reason I brought up Kold is we've gone through

**Geoff Horowitz:** so correct me.

**Hemanth Sarabu:** this we don't have enough data conversation and we we need to like break out of it. Um so one of the ideas was scold validation. Now I don't even know if that you know like I don't know if we're using it to resolve that issue of we don't have enough training and validation data. It's not just about doing so firstly I think we there are issues with the data set but that's not my point. My point is we don't yeah we don't have an evaluation data can we use careful cross validation to to give us a signal about whether model is improving or not and we don't even know that right we don't even know

**Geoff Horowitz:** So, Son, why why can't why can't we just use this on the same exact data that you ran the the base V4 model on?

### **00:35:37**

**Sachin Pandey:** uh we can because we because the data is already included in the training set. So like it model the cap model has already seen it some so we can't just like uh use it to evaluate

**Geoff Horowitz:** But but you already used it. Hold on. Let me just show you here. So, and may maybe we need like sub sub uh you know like v4.0 or something,

**Sachin Pandey:** So

**Geoff Horowitz:** right? When you made this, this was the model that we had uh that we were doing pretty well on. We had uh what was it?

**Sachin Pandey:** heat.

**Geoff Horowitz:** 80 yeah 80% um 80% recall on UXOs's you know relatively high precision uh same on the where AOI small black we were doing pretty well on uh on recall and that that was the issue right so are you saying that even on this data set we had the bad we had the bad ground truth data Okay.

**Sachin Pandey:** No. like the actual data which is used in training is tried and in kfold the all the data was passed to the model.

### **00:36:53**

**Geoff Horowitz:** So,

**Sachin Pandey:** So like I am looking for like artificial data or like something like the data we just got we can use it to evaluate the all the before and the kfold models because the data was never seen by any of the models. So like we can get a better idea. We can like put all the model side by side and see like like ask labelers to select which is doing well and something like that. The validation set which are used for V4 we can't just use it directly as is for K4 model like only one model in the Kfold can be like run with this validation the rest we can't run it

**Geoff Horowitz:** I I agree with you, but I I Yeah, go ahead. Protect

**Pratyaksh Singh:** So you divided everything into let's say eight folds right for each

**Sachin Pandey:** Five.

**Pratyaksh Singh:** of okay uh for five folds for each of these five folds you had a value valuation set right and you trade you trained

**Sachin Pandey:** Yes.

**Pratyaksh Singh:** five separate models on these data That is

### **00:38:19** {#00:38:19}

**Sachin Pandey:** Yeah.

**Pratyaksh Singh:** correct. Now the result of kfold cross validation is the average

**Sachin Pandey:** Yes.

**Pratyaksh Singh:** of the five-fold cross validation the five-fold validation model. So you don't need to evaluate it on a particular validation set. So let's say the model on the model on hold one had validation accuracy of 15%. And the same model configuration on fold two had validation accuracy of 20%. Then what you can do is you can take a weighted average kind of thing to get the final final accurate final valid precision and recall for that model. Does it make sense? So yeah,

**Sachin Pandey:** Yes.

**Geoff Horowitz:** and

**Pratyaksh Singh:** you just have to you just have to take the weighted average if you have if you have the

**Geoff Horowitz:** section

**Hemanth Sarabu:** Or just keep or just keep the keep the numbers separate.

**Pratyaksh Singh:** old

**Geoff Horowitz:** keep section one of those folds should match this data.

**Hemanth Sarabu:** Keep

**Geoff Horowitz:** That's I think what I was saying originally.

**Sachin Pandey:** uh not exactly because like uh no I I I am not sure whether it will match it or not.

### **00:39:33** {#00:39:33}

**Sachin Pandey:** I guess the separation was uh done from scratch. So it's a low chance that the like any of the one fold will match exactly with the one of one of these validation set.

**Hemanth Sarabu:** Wait, wait, wait, wait, Wait, wait, wait, wait. Such an all you're saying is that that was not K, right? It just randomly training and validation. Is that right?

**Sachin Pandey:** Uh can you repeat

**Hemanth Sarabu:** Is that right?

**Sachin Pandey:** it?

**Hemanth Sarabu:** It's is it is it it doesn't match because that was not it was not using these K4 samples. Is that is that it?

**Sachin Pandey:** I don't get your

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** question.

**Hemanth Sarabu:** Uh Jeff, go on.

**Geoff Horowitz:** Um, so, so Sashin, the reason that we split it up into five different folds was because we only had like five UXO samples, right? Or six US UXO samples. And so we were split we were splitting it up geographically. Uh so that at least one UXO in each of the folds was unseen in the training set.

### **00:40:44**

**Geoff Horowitz:** Is that

**Sachin Pandey:** Uh, no.

**Geoff Horowitz:** correct? Are you going to tell me where I'm wrong?

**Sachin Pandey:** So we did it like based on just the like total area covered not like based on like uh making sure like each UXO is in one of the validation

**Hemanth Sarabu:** Can we do what just said?

**Sachin Pandey:** Not exactly. And there are more than five UX. So in total we have 11 unique UXO.

**Hemanth Sarabu:** Okay. Um, so we can't we can't do what Jeff said.

**Sachin Pandey:** It will be hard.

**Hemanth Sarabu:** Explain explain why you're you're saying no. It won't be hard.

**Sachin Pandey:** It it will be like uh for

**Hemanth Sarabu:** Oh,

**Sachin Pandey:** explanation.

**Hemanth Sarabu:** sorry.

**Sachin Pandey:** Uh I think it will be easier to understand with the once we see how the like vexo are separated. I think that will helpful.

**Hemanth Sarabu:** Do you want to draw it out or something?

**Sachin Pandey:** Yeah. I was just finding the images are here right

**Hemanth Sarabu:** Is it is

**Sachin Pandey:** now.

### **00:42:36**

**Hemanth Sarabu:** it

**Sachin Pandey:** So like all the green ones you are seeing are all the unique UXO. So like it will be hard to like split them into five categories because they are only splitted bit they are only in present in only two data sets.

**Hemanth Sarabu:** into data sets. So why what is the distance between them?

**Geoff Horowitz:** Aren't there

**Hemanth Sarabu:** What is the distance between them?

**Sachin Pandey:** H.

**Hemanth Sarabu:** As in like so if you take you can't just like draw let's say speaking

**Sachin Pandey:** Yeah.

**Hemanth Sarabu:** naively.

**Sachin Pandey:** And then like we have to draw it like on a map or something like like putting these like for these two data set. We have to draw the like draw the separation the

**Hemanth Sarabu:** Yeah, why don't we do that?

**Sachin Pandey:** fold

**Hemanth Sarabu:** Why don't why can't the form be one where you randomly sample n of these uh by area using a bounding box or something like that.

**Sachin Pandey:** Can you elaborate it a little more?

**Hemanth Sarabu:** Yeah,

**Sachin Pandey:** You want me to put it this in uh

### **00:44:17**

**Hemanth Sarabu:** I got

**Sachin Pandey:** Excalibur?

**Hemanth Sarabu:** it. So tell me this is not possible. But why can we not separate them like something like that? Then then you can do that with everyone, right? So you get like a total total of this is like n and now you can sample them however you want. Jesus

**Sachin Pandey:** Okay, I I will I will try it.

**Geoff Horowitz:** Sachin I hem can you share this excelad please? Um or maybe he maybe this is a question for you but um couldn't

**Hemanth Sarabu:** Christ. We

**Geoff Horowitz:** Can I go to your scale draw?

**Hemanth Sarabu:** won't let you go.

**Geoff Horowitz:** There it is. There it is. Uh, so my question is, I mean, can't we can't we even just do something as trivial as like this is one fold, this is another fold, this is a fold, this is a fold, so on and so forth.

**Hemanth Sarabu:** You can also do that. You can also do that. That is less IID than the one I

### **00:46:11** {#00:46:11}

**Geoff Horowitz:** I I agree with you.

**Hemanth Sarabu:** mentioned.

**Geoff Horowitz:** I agree with you. It's less I But at least it'll give us more information than what we have right now. U Sachin,

**Hemanth Sarabu:** I mean, why don't I just do it properly?

**Geoff Horowitz:** this is a question for you.

**Hemanth Sarabu:** Why don't I just do it

**Geoff Horowitz:** Well, so Satchin, this is a question for you.

**Hemanth Sarabu:** proper?

**Geoff Horowitz:** Can we can we do we have the ability to segregate like this? Uh or is there too much overlap between each of these? Like are each of these UXOs too close that we don't have enough overlap? Uh I'm sorry other way around that we have too much overlap to cybergate them.

**Sachin Pandey:** No, I think it it will be possible. I can

**Geoff Horowitz:** It will be possible.

**Sachin Pandey:** Yeah,

**Geoff Horowitz:** All right.

**Sachin Pandey:** I can use mixture of both.

**Geoff Horowitz:** There is still a risk.

**Sachin Pandey:** H because we have the name I can just use the name to group them

### **00:47:05**

**Geoff Horowitz:** Go ahead.

**Sachin Pandey:** together and like each of the smaller box will be like grouped in because only green ones are the actual UXO. So we can like separate this and this out. Then we have a five. 1 2 3 four and five. Let's do two examples. I mean each

**Hemanth Sarabu:** If you're able to do it even if you're able to do it even if you're able to singulate them that will be better. But if they're like Jeff said they're too close you cannot singate them.

**Geoff Horowitz:** I I I would just say let's I I agree that Hemmont's approach is way better. I would just be cautious that we are we are very very sure that we don't have data leakage. Um, That's it.

**Sachin Pandey:** We can test it out. We can also visualize it to just make sure there's no data leakage for each fold.

**Geoff Horowitz:** Okay.

**Sachin Pandey:** We can just uh test it out.

**Pratyaksh Singh:** I mean we have image size of like whatever image size you can we are using we can break the map into cell of that image size and then just pick from there.

### **00:48:33**

**Pratyaksh Singh:** do a stratified sampling there so that it's balanced and it none of the folds overlap.

**Hemanth Sarabu:** Yes.

**Geoff Horowitz:** Okay. Okay. So, do we have a do we have a plan for this then suction?

**Sachin Pandey:** Yeah, I I have

**Geoff Horowitz:** I think you're right.

**Pratyaksh Singh:** So let's discuss on this after the meeting also

**Geoff Horowitz:** Uh

**Hemanth Sarabu:** Come

**Pratyaksh Singh:** once

**Hemanth Sarabu:** on.

**Geoff Horowitz:** now, hold on.

**Sachin Pandey:** Okay.

**Geoff Horowitz:** This is something that I Sachin you might have addressed this but maybe I missed it. Does the does this data set this V40 data set have cut and paste UXOs in it?

**Sachin Pandey:** B4.

**Geoff Horowitz:** V4 does not have cut and paste UXOs.

**Sachin Pandey:** No.

**Geoff Horowitz:** Does and I assume it also does not have any sort of synthetic backgrounds. Correct.

**Sachin Pandey:** Yes. No

**Geoff Horowitz:** Okay.

**Sachin Pandey:** background.

**Geoff Horowitz:** So, so I think to close out milestone two, we need to have some synthetic data. I'm okay with just the cut and paste. That's fine with me.

### **00:50:14** {#00:50:14}

**Geoff Horowitz:** All right. Josh, any feedback on that?

**Pratyaksh Singh:** Oh, I think uh Sachin, you had V3 with cut and paste augmentation, right? Uh let's rerun V\_sub1,

**Sachin Pandey:** Yes.

**Pratyaksh Singh:** V2, uh sorry, at least V3 and V4 again. and then B3 plus the traversy loss that you're using in V4. Let's have that as B5. And then once we have the Kful result, I think the cut and paste augmentation should help.

**Sachin Pandey:** So, B3 with the updated loss and uh and B4

**Pratyaksh Singh:** So V3,

**Sachin Pandey:** Huh?

**Pratyaksh Singh:** V4 and then V3 plus the Torski loss all of them evaluated on Kfold. Then once we get the numbers we can we can decide on it.

**Sachin Pandey:** Good.

**Geoff Horowitz:** And then project if we just use cut and paste here that'll give us enough um what's the word? Uh like running room that'll give us enough room to incorporate additional synthetic data that should improve results in the future. Right. milestone

**Pratyaksh Singh:** It should. It should. I think at least with more object type.

### **00:52:02** {#00:52:02}

**Geoff Horowitz:** board.

**Pratyaksh Singh:** I think it should

**Geoff Horowitz:** Okay, any final thoughts with all

**Hemanth Sarabu:** Um,

**Geoff Horowitz:** this?

**Hemanth Sarabu:** okay. So, sounds like a sounds like a plan. Project, do you have any updates on the generative stuff?

**Pratyaksh Singh:** Yeah. Uh, so I was able to train the background generation model.

**Hemanth Sarabu:** This

**Pratyaksh Singh:** Yeah. Uh, let me turn on the server for it.

**Hemanth Sarabu:** is

**Geoff Horowitz:** Oh, project, while you're opening that up, I forgot to mention this at the beginning. Uh, hopefully some good news. Hopefully, we're wrapping up Boommy within the next, you know, within the next few weeks. Um, so we're gonna have Sid slowly start coming back into Bedrock. Um, I think the goal is going to be that he takes some or most of the work off your plate to,

**Pratyaksh Singh:** All

**Geoff Horowitz:** you know, free you up for some of these other R\&D projects or other things that we're going to have you work on. Yeah. So um I guess what I would say Pratak is you know when you get some time connect with

### **00:53:39** {#00:53:39}

**Pratyaksh Singh:** right.

**Geoff Horowitz:** Sid just to just to get him up to speed keep them involved in some of these conversations um and then you know slowly over the course of the next month we'll incorporate it more and

**Pratyaksh Singh:** All right. Well done. Okay.

**Geoff Horowitz:** Thanks.

**Pratyaksh Singh:** Uh so these are like some of the images that this model generated. they looked in distribution with the example. Uh I am running I think one thing which is in okay I'll show you some more images. So these are all for the ENTX data set and similarly I think it it did quite decent for uh for like those data where there weren't any there weren't like a lot of example for example this ent data it had very small amount of examples but it did pretty good for that for that data also. Uh one thing that is quite annoying

**Hemanth Sarabu:** This is image to a text

**Pratyaksh Singh:** is not text to image it

**Hemanth Sarabu:** image.

**Pratyaksh Singh:** is uh just a condition to category to image categorical variable to image uh I think one of the things one of the annoying annoying things is that when I try to condition it too much let's say when the weight is so for example this is with weight uh this is with weight of one I mean completely unweighted then I'll just have weighted two and then uh classify guidance with

### **00:55:45** {#00:55:45}

**Pratyaksh Singh:** weight five also so with one it looks like real example with two it starts to get a little bit darker which is I think which is I think something that uh that we have seen in data set but with five weight it completely destroys the image and this I have seen in all the data set and for the experiment with like number of number of uh what do you say number of diffusion steps. So these uh these are the image with 10 diffusion strips and then this is the image with uh 25 diffusion strip the below one for data set which has very good representation it does a pretty good job even with 10 steps it looks pretty good but uh for those images which didn't have a lot of examples for example for entx slim with 10 the images Not that good.

**Hemanth Sarabu:** Thank you.

**Pratyaksh Singh:** And these are the images. But but with 25 steps, it is it is like much better.

**Hemanth Sarabu:** Interesting.

**Pratyaksh Singh:** It is

**Hemanth Sarabu:** Interesting. So this is still your uh full image.

### **00:57:03** {#00:57:03}

**Pratyaksh Singh:** very Yeah.

**Hemanth Sarabu:** No, not

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** later.

**Pratyaksh Singh:** This is well I think it trained it finished training in the morning today.

**Hemanth Sarabu:** The later

**Pratyaksh Singh:** So yeah,

**Hemanth Sarabu:** one.

**Pratyaksh Singh:** I I trained it with flow matching loss. So I think during training I didn't have to specify the number of time steps, right? because it was just uh sampling from uh

**Hemanth Sarabu:** Yeah, one direction. Uh I'm sorry.

**Pratyaksh Singh:** sorry.

**Hemanth Sarabu:** No, it's just the safe direction, right? There is no like very little state dependence for the ground. Uh is that true?

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** Yeah. Yeah, I think that's true.

**Pratyaksh Singh:** So yeah, the thing thing is with like with flow matching it it turns into an OD, right? So, so the way that you do it is you you have continuous variable for time time signal. So during training it is just uniform between zero and one

**Hemanth Sarabu:** Mhm.

**Pratyaksh Singh:** and during evaluation you can choose between you can choose between whatever the number of strips it is.

### **00:58:18** {#00:58:18}

**Pratyaksh Singh:** Uh yeah, one bad thing is that I don't know I saw with Sin is is this in the new VW data set that there are a lot of images like this. You see this this kind of image

**Sachin Pandey:** Can you tell the number? Your cursor is not

**Pratyaksh Singh:** which image four.

**Sachin Pandey:** visible.

**Pratyaksh Singh:** So yeah I think second from the left top and then you will see fourth image also image hash4 image hash 8 image hash 12 image \# 15 image 30 these kind of images so I mean I didn't I haven't generated a lot of these examples but in the 32 example I generated I think There were around five six images like this. The good thing is that I ran a clustering algorithm. Okay. Did I just close? Yeah. Uh so what I did was I I ran clustering on the images and it was able to cluster those image out.

**Hemanth Sarabu:** Nice.

**Pratyaksh Singh:** So if we want to we can huh sorry.

**Hemanth Sarabu:** Based on patient the clustering was patient.

### **00:59:52** {#00:59:52}

**Hemanth Sarabu:** What was the clustering based on?

**Pratyaksh Singh:** So the clustering So the clustering was uh based on the embeddings from a pre-trained model uh I think it was ResNet 50 ResNet

**Hemanth Sarabu:** Let's

**Pratyaksh Singh:** 50 pre-trained model and then it was density based scanning so it was able to segregate things out uh so for example let's

**Hemanth Sarabu:** see.

**Pratyaksh Singh:** say oh yeah so clusters this one so for example This is it is specified as noise but these are these images 004008

**Hemanth Sarabu:** Hey,

**Pratyaksh Singh:** 002

**Hemanth Sarabu:** I only see your terminal.

**Pratyaksh Singh:** only see my you don't see the V code my screen. Let me see uh let me know when you can see the VS code.

**Hemanth Sarabu:** Yes, this could see.

**Pratyaksh Singh:** Okay. Can you see the browser now?

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** Okay. So here you can see that the image cluster image 4 image 8 12 22 30 it was able to cluster them into one group and those are actually these images. So this is your image four 8 then your 12 uh and 30 where did I classify 30 is 30 is also in this group.

### **01:01:36** {#01:01:36}

**Pratyaksh Singh:** So this basically proved that uh this clustering with the features that you get from pre-train model that work. So I I actually clustered the whole training set right to see

**Hemanth Sarabu:** Mhm.

**Pratyaksh Singh:** how many unique example they are. I think it just finished before this meeting.

**Hemanth Sarabu:** Mhm.

**Pratyaksh Singh:** So I don't have much information on it but I have these text files with the cluster. So as soon as I do an analysis uh I will let you guys know and the plan is and the next step is I think it it's similar to what we discussed where I'm going to generate a lot of examples and then I will cluster them in groups. So for example, it's a we generate 100,000 example and then using the embedding I can cluster it into multiple groups and then we can basically sample from each of the clusters

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** and I will also like I will also try to present which cluster is similar to like you know how similar the clusters are to to the training example.

### **01:02:41** {#01:02:41}

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** I will have a report on this in on on Wednesday. One question I had was what do you guys think? Do you guys think we should have labelers go through the examples to uh to verify them or should we just feed it to the feed it to the model? the synthetic images to the model.

**Hemanth Sarabu:** Can you can you remind us what was the recipe you were going to go for again? The drink.

**Pratyaksh Singh:** So okay so the idea was that all the objects will go into validation set. We will only train on real background plus synthetic background added with the foreground object of contact.

**Hemanth Sarabu:** Here

**Pratyaksh Singh:** So mostly the training data will be majorly synthetic and all of the area of interest would be would be in the validation set.

**Hemanth Sarabu:** we

**Pratyaksh Singh:** And then the uh the recipe was that we will generate

**Hemanth Sarabu:** go.

**Pratyaksh Singh:** examples. Sorry, we will generate backgrounds and then foregrounds would be generated by closed source model and then we will just copy paste those on the background and then we will train train the model with

### **01:04:05** {#01:04:05}

**Hemanth Sarabu:** Okay. Okay.

**Pratyaksh Singh:** it.

**Hemanth Sarabu:** Let me let me see if I understand. We take the full data set uh only get the backgrounds. Try to generate a model on the backgrounds.

**Pratyaksh Singh:** Mhm. Mhm.

**Hemanth Sarabu:** You're going to put objects using a closed source model. Are you going to share reference objects, ground truth objects with a closed source model?

**Pratyaksh Singh:** Yeah, I think it's uh what Ratul mentioned right he is doing prompt engineering where he will explain the object to them to the model and then it will generate

**Hemanth Sarabu:** Great.

**Pratyaksh Singh:** some synthetic example of that object and

**Hemanth Sarabu:** Nice.

**Pratyaksh Singh:** then this will be added along with some procedurally generated object where

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** I think our main goal is that you know if it's some dark black patch then just classify it into UI. This is I think what we are pushing for right. So yeah I I'll in the next couple of days I will try to work on

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** foreground generation too and I will I will update you guys on Wednesday on this also for foreground generation.

### **01:05:14** {#01:05:14}

**Pratyaksh Singh:** Sachin, I think you you set up a an agent to do this, right? For foreground generation.

**Hemanth Sarabu:** Thank you.

**Sachin Pandey:** Yes,

**Pratyaksh Singh:** Any good results

**Sachin Pandey:** the open source data to uh the model

**Pratyaksh Singh:** there?

**Sachin Pandey:** where like it was converting the open source data to backdrop like data.

**Pratyaksh Singh:** No. No, not that one where we were giving it a crop and then asking it to generate the different objects. Did you get time to set it up? I think we discussed it one or two days. One B. I think yesterday only. If you didn't get time, it's fine. We can discuss it again and then. Can you please set it up? We'll discuss it if you have So it's it's

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** sim it's similar paradigm right where we were asking the model to procedurally previously like we were asking the agent to procedurally generate the background where it was struggling instead of that what we will do is we have categories of object we have

**Hemanth Sarabu:** Yeah.

### **01:06:20** {#01:06:20}

**Pratyaksh Singh:** categorized the object uh and then each category we

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** will feed to the model Right?

**Hemanth Sarabu:** Right.

**Pratyaksh Singh:** And then we will ask it to generate similar object to it. We will feed one or two example of a category and ask the model to like write a function that given a background can generate this object and everything that we discussed will be same.

**Hemanth Sarabu:** I

**Pratyaksh Singh:** So if the agent figures it out it's good. If it doesn't then we'll have to come up with another way.

**Hemanth Sarabu:** got it. Um, hey, uh, did you did you get a chance to dread that EMD app or just not get

**Pratyaksh Singh:** Oh yeah,

**Hemanth Sarabu:** done?

**Pratyaksh Singh:** I'm sorry. I'll get it done I think in the in next half an hour.

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** I have everything. I'll just need to get done.

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** You one thing you wanted was access to images, right? Easily that you don't have to upload images. You can just select

### **01:07:15** {#01:07:15}

**Hemanth Sarabu:** Yeah. Yeah. just basically it's already looking at it is already looking at a directory with these

**Pratyaksh Singh:** them.

**Hemanth Sarabu:** images.

**Pratyaksh Singh:** Okay. Okay.

**Hemanth Sarabu:** So I can just select from a drop down or something like that.

**Pratyaksh Singh:** All right.

**Hemanth Sarabu:** Okay, thanks. Okay.

**Pratyaksh Singh:** Out.

**Hemanth Sarabu:** Okay, sounds good. And your plan is to just use the fully ground proof data set for validation.

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** Okay. I mean, if we can pull this off, this will be

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** great.

**Pratyaksh Singh:** I hope we can but I think even if we even if we aren't uh we can do simplest real I've seen like what some people do is in the same batch they would have some synthetic data and some real

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** data and that that works pretty pretty good.

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** So yeah, the idea is that if completely synthetic works that's fine but if it doesn't we can add in some real

**Hemanth Sarabu:** Okay,

**Pratyaksh Singh:** data.

### **01:08:22** {#01:08:22}

**Hemanth Sarabu:** sounds good. Um, yeah, project, if you could take the few minutes to set up the app, that would be useful.

**Pratyaksh Singh:** or a job.

**Hemanth Sarabu:** Okay guys, I got a drop.

**Pratyaksh Singh:** Avalanche.

**Hemanth Sarabu:** And we got anything else to touch on? I sent the email to Ulyses. Haven't heard back. So, I'll um I'll drop the I'll drop my contact our text to see what what

**Geoff Horowitz:** Cool. All right. Thanks,

**Hemanth Sarabu:** P effect.

**Geoff Horowitz:** guys.

**Pratyaksh Singh:** Do you want to stay back on this one? All

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** Thanks.

**Pratyaksh Singh:** right.

**Geoff Horowitz:** Bye.

**Sachin Pandey:** But so a little bit time to see uh the HTML the report I said

**Pratyaksh Singh:** uh for the open source to background generation, right?

**Sachin Pandey:** uh UXO on open source data

**Pratyaksh Singh:** UXO on open source data. Can you can I just share the link

**Sachin Pandey:** it's

**Pratyaksh Singh:** again?

**Sachin Pandey:** yeah it is like uh main issue I spotted is like it is making the object

### **01:09:49** {#01:09:49}

**Pratyaksh Singh:** Wait, wait,

**Sachin Pandey:** bigger

**Pratyaksh Singh:** wait. Have you shared any link or so it is making the object better because I I don't understand.

**Sachin Pandey:** bigger.

**Pratyaksh Singh:** Explain me what is going on here. I I looked at this report.

**Sachin Pandey:** So,

**Pratyaksh Singh:** Explain me what is going on here.

**Sachin Pandey:** so base image is the one where we like we added a filter to make it look like the the data we which is in the backdrop and then it was like trying

**Pratyaksh Singh:** Okay.

**Sachin Pandey:** to paste the UXO onto the background like in this

**Pratyaksh Singh:** Wait. Was it trying to paste or was it trying to

**Sachin Pandey:** case

**Pratyaksh Singh:** generate?

**Sachin Pandey:** here.

**Pratyaksh Singh:** Give me a minute. Give me a minute, Sachin. Give me a minute.

**Sachin Pandey:** Okay. Thank you.

**Pratyaksh Singh:** Hello.

**Sachin Pandey:** Yeah.

**Pratyaksh Singh:** Generate key.

**Sachin Pandey:** So,

**Pratyaksh Singh:** Uh-huh. Huh. Good. Uh-huh.

**Sachin Pandey:** Maybe add tend to depress this

**Pratyaksh Singh:** Uh-huh. My

### **01:12:59**

**Sachin Pandey:** may.

**Pratyaksh Singh:** question

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** about let it Y

**Sachin Pandey:** What do you

**Pratyaksh Singh:** crop from each data

**Sachin Pandey:** know?

**Pratyaksh Singh:** set. Let's crop images. Crop 12 256 256 objects. Object category 1\. Object category 2\. Multiple object category. master. No subent spawn and her subent. Work on single subobject folder with task of procedural generation of object which look like the object in the specified. Okay. Present task to write a function generate object background.

**Sachin Pandey:** It's me. It's mention cut and

**Pratyaksh Singh:** Uh to write a

**Sachin Pandey:** paste.

**Pratyaksh Singh:** function generate object background image background image any random image of images folder image and Then it will generate object generate an object on that background.

**Sachin Pandey:** roughly

**Pratyaksh Singh:** Huh. Uh-huh.

**Sachin Pandey:** same multiple times.

**Pratyaksh Singh:** Huh.

**Sachin Pandey:** Open background.

**Pratyaksh Singh:** generate object doesn't exist. context window apart from writing a function. Generate object function.

### **01:17:53**

**Pratyaksh Singh:** Generate object function.

**Sachin Pandey:** Uh

**Pratyaksh Singh:** object.

**Sachin Pandey:** do this image model cont.

**Pratyaksh Singh:** Model model cont.

**Sachin Pandey:** So

**Pratyaksh Singh:** Click there.

**Sachin Pandey:** mention

**Pratyaksh Singh:** Take

**Sachin Pandey:** tests data image load.

**Pratyaksh Singh:** generate object. container

**Sachin Pandey:** Let me just background image. Okay.

**Pratyaksh Singh:** images. Okay. object function object

**Sachin Pandey:** It's

**Pratyaksh Singh:** scripts.

**Sachin Pandey:** ready.

**Pratyaksh Singh:** Generate object cat one generate object function. and generate object function

**Sachin Pandey:** Oops.

**Pratyaksh Singh:** or generate object function Python script or images. Image object.

**Sachin Pandey:** I'm going to do it.

**Pratyaksh Singh:** Object Cat 1\. Agent version previous

**Sachin Pandey:** set of

**Pratyaksh Singh:** set of

**Sachin Pandey:** object

**Pratyaksh Singh:** object modification. history.

**Sachin Pandey:** Sorry.

**Pratyaksh Singh:** Get logs.

**Sachin Pandey:** Someone Yeah.

**Pratyaksh Singh:** Autonomous agents.

**Sachin Pandey:** Huh?

**Pratyaksh Singh:** Take care. Hello.

**Sachin Pandey:** Uh-huh. Test.

**Pratyaksh Singh:** Validate.

**Sachin Pandey:** Or

**Pratyaksh Singh:** divide away.

**Sachin Pandey:** uh

**Pratyaksh Singh:** Take

**Sachin Pandey:** 2\. Second

### **01:23:37** {#01:23:37}

**Pratyaksh Singh:** validation validation model matrix. Hannah pick.

**Sachin Pandey:** No.

**Pratyaksh Singh:** Fold four five. Same model. M12 same model but different model different M13. M1 or

**Sachin Pandey:** data

**Pratyaksh Singh:** M1

**Sachin Pandey:** set.

**Pratyaksh Singh:** V1 model. V2 model V1 V2

**Sachin Pandey:** Main data set. Uh main data set improvement

**Pratyaksh Singh:** V3 V3 or V3 V4 difference V3 or

**Sachin Pandey:** V3 or V4mentation

**Pratyaksh Singh:** V4

**Sachin Pandey:** dropment cut and paste.

**Pratyaksh Singh:** take So experiment data or

**Sachin Pandey:** Yeah,

**Pratyaksh Singh:** model perfect always experiment discuss model experiment model. Same

**Sachin Pandey:** Somebody

**Pratyaksh Singh:** modelit

**Sachin Pandey:** here.

**Pratyaksh Singh:** same V3 or V4 V3 augmentation drop V3 augmentation Drop. loss functioning post-processing model deep model augmentation model confict So model, V4%.

**Sachin Pandey:** That's better.

**Pratyaksh Singh:** Let's say accuracy percent accuracy start accuracy plus% accuracy piece accuracy%

**Sachin Pandey:** Keep

**Pratyaksh Singh:** model number

**Sachin Pandey:** 3.4 It's

**Pratyaksh Singh:** 34% accuracy

**Sachin Pandey:** 34\.

**Pratyaksh Singh:** accuracy 34% But clean model perform M\_sub\_2 this person perform

### **01:29:29**

**Sachin Pandey:** Hey.

**Pratyaksh Singh:** Similarly, M2 to instead of summarizing in just one number compare M2 most of the most four M12 M12 maybe model M1 validations. M1 perform M1 M2 betteration

**Sachin Pandey:** What

**Pratyaksh Singh:** models compare.

**Sachin Pandey:** comparison last model

**Pratyaksh Singh:** All

**Sachin Pandey:** Normal training

**Pratyaksh Singh:** right.

**Sachin Pandey:** model.

**Pratyaksh Singh:** Huh. validate V5, V6, V7, V8, V9, V10, V1. 100% accuracy mater. slightly better.

**Sachin Pandey:** How are you?

**Pratyaksh Singh:** number V3, V4, V5, V6 happens.

**Sachin Pandey:** Christ within you.

**Pratyaksh Singh:** Uh

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** before

**Sachin Pandey:** Oh,

**Pratyaksh Singh:** next

**Sachin Pandey:** wait.

**Pratyaksh Singh:** Let's say geographically.

**Sachin Pandey:** Uh, geographic. Divide data

**Pratyaksh Singh:** There you go.

**Sachin Pandey:** set

**Pratyaksh Singh:** All right. Huh? No. No. Crop geol

**Sachin Pandey:** geography.

**Pratyaksh Singh:** location.

**Sachin Pandey:** Yeah, he need one.

**Pratyaksh Singh:** data subfolder data folder split one images masks Split images mask split three images mask. Split four images masks.

### **01:36:13**

**Pratyaksh Singh:** Split five images or Take function folder splits. Splits list of list of directory data set data set two split three split four test one split three split four split

**Sachin Pandey:** All

**Pratyaksh Singh:** five or test split Hello.

**Sachin Pandey:** right.

**Pratyaksh Singh:** Command line instantiate to train data set equal to data set two. Nit 3, N 4, five or data set data split one or two.

**Sachin Pandey:** Um,

**Pratyaksh Singh:** But data set One, two, three, four.

**Sachin Pandey:** That's verify.

**Pratyaksh Singh:** Let's

**Sachin Pandey:** Yes,

**Pratyaksh Singh:** say 256 cross 256 5.2 Republic. Sorry. flow value. So split one split split

**Sachin Pandey:** Sound

**Pratyaksh Singh:** one

**Sachin Pandey:** group.

**Pratyaksh Singh:** sampling.

**Sachin Pandey:** Oh.

**Pratyaksh Singh:** UXOP

**Sachin Pandey:** Oh.

**Pratyaksh Singh:** to

**Sachin Pandey:** Um.

**Pratyaksh Singh:** make. Uh

**Sachin Pandey:** divide

**Pratyaksh Singh:** h exactly, exactly.

**Sachin Pandey:** Please.

**Pratyaksh Singh:** break. algorithm.

**Sachin Pandey:** Oh

**Pratyaksh Singh:** Okay.

**Sachin Pandey:** dear. Come on.

### **01:42:25** {#01:42:25}

**Pratyaksh Singh:** Datlit. Let's say manage verify data. M1 M2 better

**Sachin Pandey:** Sorry.

**Pratyaksh Singh:** question.

**Sachin Pandey:** Thank you. Just say

**Pratyaksh Singh:** Huh?

**Sachin Pandey:** easy

**Pratyaksh Singh:** Get book.

**Sachin Pandey:** example. UX example.

**Pratyaksh Singh:** H. Uh uh.

**Sachin Pandey:** UX

**Pratyaksh Singh:** Uh let's say

**Sachin Pandey:** model.

**Pratyaksh Singh:** hard to find example. Okay.

**Sachin Pandey:** Oh,

**Pratyaksh Singh:** Hard example three.

**Sachin Pandey:** hold three subm model compare.

**Pratyaksh Singh:** Huh? M1 M24 hard

**Sachin Pandey:** I'm not here.

**Pratyaksh Singh:** to find example. Best model.

**Sachin Pandey:** Tell

**Pratyaksh Singh:** All good

**Sachin Pandey:** me.

**Pratyaksh Singh:** question. Everyone

**Sachin Pandey:** There you

**Pratyaksh Singh:** knows

**Sachin Pandey:** go.

**Pratyaksh Singh:** Clearly discuss. model.

**Sachin Pandey:** Oh, are we discussing

**Pratyaksh Singh:** Byebye.

**Sachin Pandey:** Another artificial data.

**Pratyaksh Singh:** Then artificial

**Sachin Pandey:** model. I'm

**Pratyaksh Singh:** data

**Sachin Pandey:** sorry.

**Pratyaksh Singh:** M2 solution.

**Sachin Pandey:** to M11 Dubara train longer time.

**Pratyaksh Singh:** Huh? Sorry. It open.

### **01:47:59** {#01:47:59}

**Pratyaksh Singh:** Sorry. M M11 M11 M11

**Sachin Pandey:** Sorry.

**Pratyaksh Singh:** instance.

**Sachin Pandey:** M1

**Pratyaksh Singh:** Uh huh. Final stage

**Sachin Pandey:** Uh,

**Pratyaksh Singh:** finch.

**Sachin Pandey:** sorry.

**Pratyaksh Singh:** M1 prime and prime delivered

**Sachin Pandey:** Sorry. Uh I I

**Pratyaksh Singh:** was

**Sachin Pandey:** configuration.

**Pratyaksh Singh:** Uh con experiment.

**Sachin Pandey:** Last Yeah,

**Pratyaksh Singh:** Experiment.

**Sachin Pandey:** just

**Pratyaksh Singh:** model

**Sachin Pandey:** wait.

**Pratyaksh Singh:** training

**Sachin Pandey:** model

**Pratyaksh Singh:** config.py

**Sachin Pandey:** config

**Pratyaksh Singh:** box size 0.0. Okay.

**Sachin Pandey:** training. training.

**Pratyaksh Singh:** Oh

**Sachin Pandey:** Well,

**Pratyaksh Singh:** yeah.

**Sachin Pandey:** model

**Pratyaksh Singh:** very much love.

**Sachin Pandey:** or is It's the matrix

**Pratyaksh Singh:** model.

**Sachin Pandey:** better.

**Pratyaksh Singh:** Focal loss. Latest Most probably

**Sachin Pandey:** 10

**Pratyaksh Singh:** changes.

**Sachin Pandey:** mut. doing here. Hello.

**Pratyaksh Singh:** Hello.

**Sachin Pandey:** Uh

**Pratyaksh Singh:** Uh

**Sachin Pandey:** yeah,

**Pratyaksh Singh:** uh

**Sachin Pandey:** change the

**Pratyaksh Singh:** change

**Sachin Pandey:** code.

**Pratyaksh Singh:** color.

**Sachin Pandey:** I

**Pratyaksh Singh:** Okay.

**Sachin Pandey:** think data.

**Pratyaksh Singh:** How much

**Sachin Pandey:** branch.

**Pratyaksh Singh:** personal soldier that

**Sachin Pandey:** All right.

**Pratyaksh Singh:** trackformation.

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** Hey Got that.

**Sachin Pandey:** basically 3D shape

**Pratyaksh Singh:** Uh

**Sachin Pandey:** simplify

**Pratyaksh Singh:** we do that.

**Sachin Pandey:** single plastic

**Pratyaksh Singh:** Uh, nice.

**Sachin Pandey:** simplify. Arch mainly

**Pratyaksh Singh:** How much is too good? P say

**Sachin Pandey:** back. Thank you.

**Pratyaksh Singh:** Okay.

### **Transcription ended after 01:56:06**

*This editable transcript was computer generated and might contain errors. People can also change the text after it was created.*