# **📝 Notes**

Jul 20, 2026

## **Iris Sync**

Invited [Pratyaksh Singh](mailto:pratyaksh@crescer.ai) [Niveta Iyer](mailto:niveta@crescer.ai) [Hemanth Sarabu](mailto:hemanth@crescer.ai) [Geoff Horowitz](mailto:geoff@crescer.ai) [Siddharth Soni](mailto:siddharth@crescer.ai) [Ratul Shashank](mailto:ratul@crescer.ai) ~~[Sachin Pandey](mailto:sachin@crescer.ai)~~

Attachments [Iris Sync](https://calendar.google.com/calendar/event?eid=NnNzMHVxNzk3MmJqZGVwNXFoN2J1Mjd1OTdfMjAyNjA3MjBUMTYzMDAwWiBnZW9mZkBjcmVzY2VyLmFp)

Meeting records [Transcript](https://docs.google.com/document/d/1LYQojbVMPXkxZ1PTRiuuT7J2H6lyN5-9d5qveMOJbIM/edit?usp=drive_web&tab=t.scmuw6m0i62a) 

### **Summary**

The team aligned on data management protocols and refined synthetic generation strategies to prepare for upcoming demonstrations.

**Data Management and Organization**  
The team agreed to establish a centralized reference list for open source and raw data. Leadership decided to personally oversee the relocation of phase 2 Secure File Transfer Protocol data.

**Synthetic Data and Modeling**  
Experiments showed that diffusion models effectively generate background data while object pasting works for feature generation. The team will now train segmentation models using these augmented datasets to establish performance baselines.

**Performance Metrics and Reporting**  
Adjusting the prediction size filter significantly improved precision and recall metrics for unexploded ordnance classification. Analysts will standardize project documentation to clearly communicate experimental rationale and outcomes.

### **Decisions**

## Aligned

* **Streamlit model selection toggle** The Streamlit app is updated to include a toggle feature enabling users to select between old and new model versions.

* **UXO metric calculation exclusion** Images where UXO objects are not visually identifiable are excluded from metric calculations to prevent corrupted evaluation results.

* **Feature development prioritization** Development focus is prioritized toward UXO and small black patch data, deprioritizing sand ripples.

* **Sand patch annotation training strategy** The model training strategy is established to either drop 'sand patch' annotations or merge them with 'sand ripples' to improve classification performance.

* **Updated data as project baseline** The project baseline is set to utilize the updated dataset, rather than static historical data, to ensure accurate performance comparisons.

* **MAG data exclusion from client review** The team decided to exclude MAG data from the upcoming client meeting agenda unless specific questions arise that require client input.

We've **updated the Decisions section** using your feedback.

Let us know what you think: [Helpful](https://google.qualtrics.com/jfe/form/SV_5p6FWBVWvynleNU?isGoogler=no&isHelpful=yes) or [Not Helpful](https://google.qualtrics.com/jfe/form/SV_5p6FWBVWvynleNU?isGoogler=no&isHelpful=no)

### **Next steps**

- [ ] \[Sachin Pandey\] Track data sets: Compile a reference list of open source and raw data sets in the project tracker.

- [ ] \[Geoff Horowitz\] Move phase 2: Transfer phase 2 files between the raw data and open source data directories.

- [ ] \[Sachin Pandey\] Update tracker: Update the tracker to reflect the moved data files.

- [ ] \[Sachin Pandey\] Correct spelling: Edit the color legend label to use American English spelling.

- [ ] \[Sachin Pandey\] Update Streamlit app: Add a model selection toggle to the Streamlit app to allow switching between the current and previous model versions.

- [ ] \[Pratyaksh Singh\] Create slides: Prepare presentation slides illustrating synthetic data outputs for the upcoming meeting.

- [ ] \[Sachin Pandey, Ratul Shashank\] Review augmentations: Analyze the outputs of various augmentations to determine effective classical methods for model improvement.

- [ ] \[Sachin Pandey\] Filter UXO metrics: Remove images from metrics calculation where the target object is not visually identifiable by labelers.

- [ ] \[Pratyaksh Singh\] Train models: Run training sessions for segmentation models using the specified augmentation variants and baseline parameters.

- [ ] \[Sachin Pandey\] Update Metrics Table: Add improvement indicators against the baseline model to the performance table. Include these values in parentheses next to the relevant figures.

- [ ] \[Sachin Pandey\] Create Bedrock Report: Generate a document and georeferenced JSON files for Bedrock regarding sand ripples and black patches. Format the data to allow direct drag and drop onto XTF or mosaic software.

- [ ] \[Sachin Pandey\] Document Training Progress: Incorporate new metrics into the ongoing training progress file. Provide a summary explaining the purpose of each experiment and link to all corresponding report files.

- [ ] \[Ratul Shashank\] Create Visualization: Produce a 2 pane view comparing magnetic data with side scan imagery. Highlight the exact location of the amplitude peak on the side scan images.

### **Details**

* **Data Set Tracking**: Geoff Horowitz initiated a discussion regarding whether the team is tracking various data sets in a central location. Sachin Pandey explained that they are currently pulling data and an agent is downloading it to Ninja and tracking the source URLs, but there is no centralized reference list. The team agreed to create a central list for both open source and raw data, with Sachin Pandey tasked to compile this information ([00:02:36](#00:02:36)).

* **Secure File Transfer Protocol Data Management**: Sachin Pandey confirmed that raw data is located in the Secure File Transfer Protocol (SFTP) folder. There was a discussion regarding moving "VW phase 2" data to the SFTP folder. Sachin Pandey expressed concern about the difficulty of modifying permissions to remove or move data directly on the SFTP server. Geoff Horowitz decided they would handle moving the phase 2 data ([00:03:59](#00:03:59)).

* **Upcoming Meeting with Bridget**: Geoff Horowitz announced a meeting with Bridget scheduled for Thursday at 5:00 PM Eastern (2:00 PM Pacific). The main objectives are to review preliminary results and discuss synthetic data outputs. Geoff Horowitz will forward the meeting invitation to Hemanth Sarabu to ensure they can attend ([00:07:54](#00:07:54)) ([00:11:01](#00:11:01)).

* **Model Versioning for Demonstrations**: To prepare for the meeting with Bridget, Geoff Horowitz requested that the team connect the best current model to the Streamlit app. Sachin Pandey agreed to create a backup of the current app and add functionality to allow toggling between the old model and the new model, ensuring they can easily demonstrate both deliverables ([00:09:39](#00:09:39)).

* **Open Source Data Utility**: Pratyaksh Singh presented open source mine examples, noting that they differ significantly from Bedrock data in resolution and intensity. Hemanth Sarabu questioned whether they should train on this data, but Sachin Pandey noted the labeling is not identical and the data distribution is distinct from their current process. Pratyaksh Singh suggested using this data for pre-training and then fine-tuning on Bedrock data to improve generalization ([00:12:03](#00:12:03)).

* **Synthetic Data Generation Techniques**: Pratyaksh Singh reported on progress generating small patches for mines (class AOI small). They utilized object pasting, which works well, and a procedural generation method that proved less effective due to issues with replicating gradients. Pratyaksh Singh also plans to develop a tool using a diffusion model to generate objects from masks, though they noted the model is limited to 128 by 128 pixel patches ([00:17:55](#00:17:55)).

* **Synthetic Data Strategy Summary**: Pratyaksh Singh summarized the generation methods, noting that diffusion models are working for background generation, while copy-pasting is effective for object generation. Procedural generation for cylindrical mines is functional but less useful due to limited examples in the dataset. The team plans to train several segmentation models with these augmentations in the next couple of days and report results on Wednesday ([00:23:12](#00:23:12)).

* **Augmentation Baseline Testing**: Hemanth Sarabu emphasized the need to establish a performance baseline. Pratyaksh Singh will train a segmentation model without advanced augmentation for a baseline, and then train variants with different augmentation combinations (A, B, C, and D) to measure the "delta," or improvement. This testing will help demonstrate the value of the synthetic data pipeline to Bridget ([00:26:16](#00:26:16)).

* **Model Performance Analysis**: Sachin Pandey reported on six new models, categorized into group one (original pipeline with no hyperparameter changes) and group two (with hyperparameter adjustments). Group two models generally perform better than group one. Sachin Pandey identified that adding a filter for prediction size significantly improved the F1 score by reducing false positives ([00:31:55](#00:31:55)) ([00:37:59](#00:37:59)).

* **Unexploded Ordnance Class Performance**: The team discussed the Unexploded Ordnance (UXO) class performance. Sachin Pandey noted that the UXO model is generally better as it learns more features. However, Hemanth Sarabu expressed concern regarding the 40 percent recall rate. They discovered that some false negatives are due to files being marked as UXO even when the object is not visually present in that specific file. They agreed to clean the metrics by discounting these specific examples ([00:40:53](#00:40:53)).

* **Prediction Filtering and Metrics**: The team discussed using an overlap threshold. Geoff Horowitz suggested that an overlap threshold higher than 0.01 is more useful for understanding model performance internally, even if 0.01 is used for client presentations. They plan to continue exposing confidence levels and minimum filter size settings in the viewer to help manage false positives ([00:49:22](#00:49:22)).

* **Sand Ripples and Labeling Clarification**: Regarding sand ripples, Pratyaksh Singh clarified that the client does not prioritize them, focusing instead on AOI small and mines. Pratyaksh Singh also flagged an issue with the VW data set, where examples of "AOI small black" were labeled under "AOI support." The team will investigate these labels further to ensure accurate classification ([00:53:50](#00:53:50)) ([00:56:14](#00:56:14)).

* **AI Support and UXO Annotation Updates**: Sachin Pandey and Pratyaksh Singh discussed the current iteration of AI support features, noting that these features often closely resemble black patches and are being combined in the model. Pratyaksh Singh advised updating the latest annotations on the viewer, to which Sachin Pandey agreed, confirming they would provide the necessary file. The team also discussed the importance of filtering datasets to retain only the files where unexploded ordnance (UXO) is marked, ensuring that the model is trained on relevant data ([00:59:29](#00:59:29)).

* **Dataset Cleaning and Model Training**: Sachin Pandey described plans to train a new model focused on high-visibility features to improve performance where features are currently weak. Pratyaksh Singh cautioned that they must ensure the accuracy of these annotations, specifically those provided by or used by Bedrock, to avoid training the model on false positives ([01:03:28](#01:03:28)). Sachin Pandey confirmed that all annotations for the VW, ETX, and BRN datasets are being maintained and that they are testing different models by dropping or merging sand patches with sand ripples to improve object-wise classification ([01:04:39](#01:04:39)).

* **Performance Metrics and Baseline Strategy**: Sachin Pandey reported that increasing the pixel threshold to 100 pixels resulted in a 20% jump in the precision-recall score without reducing true positives, whereas a default of 10 pixels led to excessive false positives ([01:06:17](#01:06:17)). Geoff Horowitz advised against adding too much information to the primary results table to avoid confusion, suggesting they use a separate table or a "diff" format to clearly show updates ([01:09:32](#01:09:32)). Regarding the baseline, the team agreed that the updated, high-quality data should serve as the baseline for all future comparisons, even though updating the baseline can complicate the tracking of model improvements ([01:10:42](#01:10:42)).

* **Client Meeting Preparation**: To resolve uncertainties regarding data inclusions, such as sand ripples and black patches, Geoff Horowitz directed Sachin Pandey to prepare a PowerPoint presentation with specific questions for the upcoming meeting with Bedrock on the 23rd ([01:13:24](#01:13:24)). The team plans to provide geo-referenced JSON files and reports, which will allow the client to drag and drop the data onto their XTF mosaics for offline review ([01:14:27](#01:14:27)).

* **Documentation of Progress**: Geoff Horowitz requested that Sachin Pandey formalize project documentation to ensure progress is tracked over time. Sachin Pandey agreed to improve their current tracking file by adding metrics and a summary that includes the date, a link to the report, a "too long; didn't read" (TL;DR) section explaining the rationale behind experiments, the results, and proposed next steps ([01:15:47](#01:15:47)).

* **Magnetometer Data Testing and Visualization**: Ratul Shashank provided an update on Magnetometer (MAG) data, noting that there has not been significant improvement in location accuracy, which remains within a 5 to 10-meter range ([01:18:41](#01:18:41)). Geoff Horowitz does not plan to discuss the MAG data with Bedrock at the moment, though they acknowledged that the current accuracy is still useful ([01:20:11](#01:20:11)). Ratul Shashank will create visual reports featuring two panes—one for the XTF image and one for MAG amplitude—with a marker indicating the predicted object location to improve visual clarity ([01:21:28](#01:21:28)).

* **Meeting Logistics**: Geoff Horowitz and Pratyaksh Singh discussed technical issues that have caused Pratyaksh Singh to struggle with consistent connectivity during meetings. Geoff Horowitz suggested using a call-in number to maintain audio connectivity even if the video feed drops, though they acknowledged this might only be feasible with US-based numbers ([01:24:54](#01:24:54)).


# **📖 Transcript**

Jul 20, 2026

## **Iris Sync \- Transcript**

### **00:00:50**

**Ratul Shashank:** Hello. Hello

**Sachin Pandey:** I'm Richard. I

**Ratul Shashank:** Jeff.

**Sachin Pandey:** fix.

**Ratul Shashank:** Did I send you the repo that I got for OSX and I mean have I

**Sachin Pandey:** Yeah. Yes. Yes.

**Ratul Shashank:** sh

**Sachin Pandey:** That's the same rapper we were uh using earlier like when

**Ratul Shashank:** all the

**Sachin Pandey:** Yeah,

**Ratul Shashank:** columns

**Sachin Pandey:** that's the same which we downloaded the mind data from.

**Ratul Shashank:** uh there are Like there are also other data sets like there is a shipwreck uh shipwreck one is more there are more

**Sachin Pandey:** Yeah, I I shared the report like Siddhhat created a report for this dog already.

**Ratul Shashank:** examples.

**Sachin Pandey:** I just like when I saw the name of the I was able to find it on the our like our drive. I have shared it with you right.

**Ratul Shashank:** Yeah, I can't access that report or something.

**Sachin Pandey:** Try using like even with casher

**Ratul Shashank:** Mhm.

**Sachin Pandey:** ID

**Ratul Shashank:** I can't access that report.

**Sachin Pandey:** and

**Ratul Shashank:** I I will I will I think because my phone I will I will take a look.

### **00:02:36** {#00:02:36}

**Pratyaksh Singh:** Hi guys.

**Geoff Horowitz:** So,

**Ratul Shashank:** paper.

**Geoff Horowitz:** are we keeping track of all these different data sets in some tracker or that tracker that I set up rather?

**Sachin Pandey:** Currently we are not we are like just trying to pull the data. Uh, I have one like do which is like managed by agent like all the data set he's downloading he's just tracking which URL it is used to download the data set and putting the data set on ninja downloading downloading it on ninja

**Geoff Horowitz:** Can

**Pratyaksh Singh:** What are you talking about? Are you talking about open source data or dead rocks and small

**Geoff Horowitz:** you

**Pratyaksh Singh:** data?

**Sachin Pandey:** open source data

**Geoff Horowitz:** So,

**Pratyaksh Singh:** Okay.

**Geoff Horowitz:** so I'm actually talking about all of it, right? I think that we need a central place where we can all understand what data we have. Um, and I mean I it's it's fine to have an agent uh obviously it's fine to have an agent um you know look at this but um at some point I you know I think we need like a even just a place that we we know where it exists

### **00:03:59** {#00:03:59}

**Pratyaksh Singh:** Hey, I really liked having the data on FTP

**Geoff Horowitz:** Hey,

**Pratyaksh Singh:** server.

**Hemanth Sarabu:** Thank you,

**Pratyaksh Singh:** Can't we just put it there?

**Hemanth Sarabu:** sir.

**Pratyaksh Singh:** For example,

**Geoff Horowitz:** yeah.

**Pratyaksh Singh:** make one for bedrock and then put it because it's very organized, right? From creser to crer,

**Geoff Horowitz:** Yeah,

**Pratyaksh Singh:** what's the date and all those things?

**Geoff Horowitz:** absolutely. I'm that's fine with me. I mean, again, I don't I don't really care where it's stored. I I just want a um I want a list. I want a reference list, you know? I want I want this metadata in a place where it's just easy for us to see even if we don't have like these, right? Um I think these are important.

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** Sachin, can you throw it together for the open source data and the role data?

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** Yes. Uh ro data will be same in SFTP. I will just put the put it here.

**Geoff Horowitz:** roll data will be what?

### **00:05:06**

**Sachin Pandey:** Ro data will be present in the SFTP folder.

**Geoff Horowitz:** Ah yeah yeah yeah. Uh also such I don't think I moved that. Uh one second.

**Sachin Pandey:** paste to

**Geoff Horowitz:** Yeah,

**Sachin Pandey:** VW

**Geoff Horowitz:** exactly. I didn't move the VW phase 2\. You want me to move it or you want to move it?

**Sachin Pandey:** uh I can move it like it will take time because I don't think like we need some thing to like we need to like uh it will be hard to remove it from SFTP directly. We need to change some permission and like set it back up again.

**Geoff Horowitz:** I'll I'll do it. I'll do it.

**Sachin Pandey:** It will like do you have a dog ready somewhere for

**Geoff Horowitz:** I about about how to do

**Sachin Pandey:** this?

**Geoff Horowitz:** it.

**Sachin Pandey:** No. How to like uh disable the flag and reenable it after deleting

**Geoff Horowitz:** I um I I've asked I've asked Google like a few

**Sachin Pandey:** it.

**Geoff Horowitz:** times and it shows it to me right away.

### **00:06:08**

**Geoff Horowitz:** Uh I don't think I actually put it in the doc mostly because I didn't want to make it easy for myself to to delete stuff. You know, I purposely wanted to make it difficult.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** Um but I don't let me let me double check. I don't think I put it in the uh SFTTP SFTTP. Yeah, I did not add it here. I not add it here. I mean I can just want it and add it here. I just I I I think it's smart to make it difficult for us, right? The whole point is that we can't edit it.

**Sachin Pandey:** Let me

**Geoff Horowitz:** Yeah, I'll take care of it. Sin,

**Sachin Pandey:** guess.

**Geoff Horowitz:** I'll move I'll move uh phase two. But if you can if you can move uh you know move whatever is needed between the RO data and the open source data and then just update this update this tracker also I mean look clearly this isn't critical these fields but especially if you have an agent that already does this I think it's good to be able to track okay this has mag data this has side scan this has you know multi-beam data so on and so forth.

### **00:07:54** {#00:07:54}

**Sachin Pandey:** Okay, I will try to fill the uh as much space I

**Geoff Horowitz:** Okay.

**Sachin Pandey:** can

**Geoff Horowitz:** Um, okay. Uh, he I'm meeting with Bridget on Thursday at 5:00 PM Eastern. Um any chance you're available then?

**Hemanth Sarabu:** I think that should work. So that's 2 p.m.

**Geoff Horowitz:** Yeah,

**Hemanth Sarabu:** Pacific.

**Geoff Horowitz:** let me send you I will forward this on to you if I know

**Hemanth Sarabu:** actually my happy PD.

**Geoff Horowitz:** how.

**Hemanth Sarabu:** So forward it to me but um have PT

**Geoff Horowitz:** Fine. Um,

**Hemanth Sarabu:** then

**Geoff Horowitz:** why can't I forward this? You know, she sent it to me before I could even send it. Send her. So, See if I can send it forward. That would be uh 2 o'clock your time. Okay. Um so my objective on Thursday, so this is I think by Wednesday um you know in two days we should have the following. I I want to go over with Bridget. Number one just some of the pre preliminary results we're seeing.

### **00:09:39** {#00:09:39}

**Geoff Horowitz:** So Sachin um you know Thursday let's take the best model that we have and upload it to or rather connected to the streamllet app. Um, and actually now that I think about it, we should probably, we should probably create a new Streamlit app or else or else be able to select the model, one or the other. Just something so that if we ever want to go back to the to the previous deliverable, we can do that pretty easily with Bridget.

**Sachin Pandey:** Okay. Uh I will create create a I will take the backup of the current one and then add this

**Geoff Horowitz:** Okay. Okay. All right. Uh you'll take a backup of crew.

**Sachin Pandey:** functionality.

**Geoff Horowitz:** Okay. But if the backup isn't live, I'd like to be able to access the old model, whether that's in the same app with uh Hold on, let me share my screen.

**Sachin Pandey:** It will be in the same app with the toggle like you can select the model,

**Geoff Horowitz:** Yeah, that's fine.

**Sachin Pandey:** you can select the old model and new

### **00:11:01** {#00:11:01}

**Geoff Horowitz:** Perfect. That that'll certainly work. That works. Thanks, AA.

**Sachin Pandey:** model.

**Geoff Horowitz:** So, so by Wednesday, let's get whatever we have the most up to date to at least be able to show her something. Um, this Oh, and then the second thing actually, we talked about this on Friday, is I want to go over um our synthetic data outputs and I want her to be able to kind of look at them and see what we're getting. uh see how the results look. I will also take that opportunity to be like look you know we don't have a ton of data here. You know we we are creating synthetic data but it's all going to look like these you know seven samples that you gave us. Um there's not a lot of variety here.

**Pratyaksh Singh:** Got it.

**Geoff Horowitz:** So

**Pratyaksh Singh:** And you want it for all the different classes. Right. I'll I'll I'll create slides. You can choose from them.

**Geoff Horowitz:** yeah, that'd be great.

### **00:12:03** {#00:12:03}

**Geoff Horowitz:** Thanks. Thanks, Proach.

**Pratyaksh Singh:** All right.

**Geoff Horowitz:** Um, I even think Protach, we can even show her the open source stuff that you had too. Um, I think I think it would be good to show. I'm not sure that I will ask her if she wants us to train on it or not, the open source stuff. Um, if they're not going to if we're not going to predict on those examples, then we can choose. I mean, we can always train on it if we think it's going to help

**Hemanth Sarabu:** What what are these open source uh

**Geoff Horowitz:** generalization.

**Hemanth Sarabu:** examples?

**Pratyaksh Singh:** these are the mines examples that we got from open source data set.

**Sachin Pandey:** I

**Hemanth Sarabu:** H

**Pratyaksh Singh:** It it doesn't have the same distribution as the bedrock data because it is very high

**Geoff Horowitz:** Um,

**Sachin Pandey:** didn't

**Pratyaksh Singh:** resolution. So that's

**Hemanth Sarabu:** But we cannot make it look low res.

**Pratyaksh Singh:** It's difficult. I can show you some examples.

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** Uh I'll show you the link here in chat in data set.

### **00:13:11**

**Pratyaksh Singh:** You can select open source and then it will visible. It's not just the resolution, but also like the intensity. It's much different than that. And what they gave us

**Hemanth Sarabu:** I don't know why it won't uh it's not opening for me. Let me see.

**Geoff Horowitz:** I love Can you see it?

**Pratyaksh Singh:** trigger

**Hemanth Sarabu:** What?

**Geoff Horowitz:** Can you see? I'm sharing my screen.

**Hemanth Sarabu:** Yeah. Yeah. Yeah.

**Geoff Horowitz:** I think the bigger problem here on this was my thought on Friday is that this this just doesn't look like even if we lowered the resolution, it doesn't it doesn't really look like the objects that Bedrock does

**Pratyaksh Singh:** So I looked actually I looked through it for a lot of examples and here the mines were basically cylindrical kind of object with shadow in

**Geoff Horowitz:** one

**Pratyaksh Singh:** them. That was the pattern that I saw in this data in this data set.

**Geoff Horowitz:** which is do these do these correspond to the legend here. Oh, Sachin, do me a favor.

### **00:14:41**

**Geoff Horowitz:** Take out the U from color. We're we're presenting to Americans.

**Hemanth Sarabu:** H.

**Geoff Horowitz:** So,

**Sachin Pandey:** Uh, which one?

**Geoff Horowitz:** uh can you see here color legend?

**Sachin Pandey:** Okay. Okay.

**Geoff Horowitz:** Take That's a beautiful color.

**Hemanth Sarabu:** So, have we tried training with this data and without this data to make some claims about whether it'll help

**Sachin Pandey:** So, no, we haven't trained a model on this one.

**Hemanth Sarabu:** Can

**Sachin Pandey:** uh like it it doesn't like the labelers labeling is on this data are like not identical to what we want exactly and like we need to do a lot of labeling and like mo most of the objects in this are unrecognizable like we can't even identify a good level for that. And uh the distribution is also very different like the data looks very like out of the distribution. Not even the process data looks like these uh

**Pratyaksh Singh:** The plan was which I think we discussed in the previous meeting was that we will get we will try to see how much data that we can get from this open source as well as using using generative aware to generate random sites scans.

### **00:16:31**

**Pratyaksh Singh:** sonar data and then with that if we can use it for pre-training h and then fine-tune on the bedrock data if something like that can help because I don't think it's viable to label all these examples so the idea was that we will search through open source data set we will classify them if they're close to bedrock or not and then we will use it as pre-training and then just fine-tune on the bedrock data so we actually were going to Discuss that

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** in

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** That's that's all I had. Um, if you want to unless anybody has questions about what I said, if you want to take over,

**Pratyaksh Singh:** uh okay uh I'll share my update. I tried generating the small pads for mines. The class that are labeled AOI small. The thing is that uh I wasn't able to recreate it because the intensity is not just black. There is some pattern to it which I'm not able to replicate. So I tried object pasting for it only that seemed to work.

### **00:17:55** {#00:17:55}

**Pratyaksh Singh:** So I'll continue with that. And then And uh I have been working with u working with ratul for xtier based augmentation. Uh but that will take some time too. I I'm going to I'm working on setting up model training with the augmentations that we discussed and more augmentation for more experiment but no update there also. I'll try to set it up tonight or by

**Hemanth Sarabu:** Can you show us the examples or

**Pratyaksh Singh:** tomorrow. Yeah, I can show you examples.

**Hemanth Sarabu:** anything?

**Pratyaksh Singh:** Give me a minute. Let me know when my screen is visible.

**Geoff Horowitz:** I can I can see it

**Pratyaksh Singh:** All right, let's give

**Geoff Horowitz:** now.

**Pratyaksh Singh:** them okay. So you see these these are the actual annotation for mines or small black as it's called in this in this lesson. I'll just scroll through those. like uh in the bottom image you can see where it's marked and in the top image you can see the annotation. Okay. And the thing is that when I'm trying to recreate it, it's something like this that the color is just constant.

### **00:19:47**

**Pratyaksh Singh:** Can you see my VS Code image

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** there?

**Hemanth Sarabu:** What is what is desired like what what is

**Pratyaksh Singh:** Huh? The desired is something like this.

**Hemanth Sarabu:** that

**Pratyaksh Singh:** You see this uh uh can you see the image on my browser?

**Hemanth Sarabu:** yeah yeah yeah

**Pratyaksh Singh:** So it's not completely black. Right.

**Hemanth Sarabu:** you mean

**Pratyaksh Singh:** There is there is some shape to it.

**Hemanth Sarabu:** okay

**Pratyaksh Singh:** Right. If I if I go through more examples,

**Hemanth Sarabu:** I think

**Pratyaksh Singh:** I think we'll even be more clear. Let's example for this example. Right. So it's not completely black.

**Geoff Horowitz:** There's a there's a shape and there's a gradient to it is what you're saying.

**Pratyaksh Singh:** Yeah, there is shape and there is grading. I I wouldn't push much on the shape but grading for sure. Right. So to do that what I did was uh for the grading what I did was I only

**Geoff Horowitz:** No

**Pratyaksh Singh:** made the 80th percentile to 80th percentile to black and then let the rest of the intensity be like this.

### **00:20:51**

**Pratyaksh Singh:** So for example, let's say that whatever the 80th percentile of the image is of the of the image inside blob

**Geoff Horowitz:** heat.

**Pratyaksh Singh:** is I convert it to make it to black and then do the same transformation to for all the pixels in the in the blob and this is actually what you see here but again like even in this case also the idea was that it will copy the texture but even in this case also like it it it doesn't it doesn't

**Hemanth Sarabu:** What? What are you training here? What are you training

**Pratyaksh Singh:** huh uh I'm not training anything here I'm

**Hemanth Sarabu:** here?

**Pratyaksh Singh:** just trying to simulate these examples so Those can be used for an additional example during

**Hemanth Sarabu:** Right. But what is um sorry,

**Pratyaksh Singh:** training.

**Hemanth Sarabu:** is there a learning piece? Anything like that?

**Pratyaksh Singh:** No, no learning PC.

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** What What can we learn here?

**Hemanth Sarabu:** I I forgot what what method you were using to generate the the uh targets.

**Pratyaksh Singh:** What method was I using to generate the T?

### **00:22:02**

**Hemanth Sarabu:** Is it just copy? What? You get what I mean? How are you

**Pratyaksh Singh:** No, it's it's not copy paste. It's randomly selecting an area creating a blob of it and then in that blob you'll

**Hemanth Sarabu:** generating?

**Pratyaksh Singh:** try to artificially generate the gradients like these like the one that you see in image. Does that make sense? For copy paste it works. I checked for copy paste. For copy paste it, it worked. So that we can do. I wanted to see if you know there are other ways where we can generate this example. For example, we copy paste here. It pasted that object which looked like it. But uh if we want to do a procedural generation there it doesn't work. I will I'll also I'll also create a tool with the diffusion model that we trained that can take a mask and then generate the object from it and I'll give it to labelers to see if we can generate more data.

### **00:23:12** {#00:23:12}

**Pratyaksh Singh:** But the bottleneck there is that the diffusion model was trained only on 128 \+ 128 pixels. Uh so we will be limited for training our model with that only

**Hemanth Sarabu:** Okay. Um, so so 128 \+ 128 for the whole swap. Or how

**Pratyaksh Singh:** So the diffusion model was trained to take 120\. No, not for the whole swath. It's just a patch of it that was done to increase the number of examples that diffusion model can take.

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** So it's just a small patch.

**Hemanth Sarabu:** Okay. So, can you summarize what synthetic data gen methods are working for us?

**Pratyaksh Singh:** All right. So um if I have to summarize it, so there are two things that I'll have to that I can summarize it on. One is background generation and then another one is foreground generation. With foreground I mean object generation. So for background generation the diffusion model that is

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** working if if you want to generate new backgrounds we can use a diffusion model for it that is working for for object generation the

### **00:24:53**

**Hemanth Sarabu:** Very cool.

**Pratyaksh Singh:** diffusion model is working for data sets where we had we had given it examples. So for example for VW and ENTX diffusion model is also working for any data set copy pasting of the object is working and again for background generation the role generation for from procedural data the role generation is working for background generation which is also using just cinosidal way cinosidal. So for object generation adding object uh I think copy pasting is the major one

**Hemanth Sarabu:** Very cool.

**Pratyaksh Singh:** for cylindrical minds there is a procedural generation there is a procedural generation that is working but I don't think it is useful because there is only one example of cylind cylindrical mind that they have in the whole data set but I will again add it to the training and then train a model with it uh in

**Hemanth Sarabu:** Got

**Pratyaksh Singh:** the next couple of days I am going to I'm going to train uh I'll try to

**Hemanth Sarabu:** it.

**Pratyaksh Singh:** train several models. I'll try other augmentations also and I I'll let you guys know of the result on Wednesday and then with that I think we will we can we can plan next what are the things to work on

### **00:26:16** {#00:26:16}

**Hemanth Sarabu:** So got it.

**Pratyaksh Singh:** for

**Hemanth Sarabu:** Is anyone working on? So protect when you say a couple of days are you saying um you're going to train the segmentation model with these augmentations or you going to train like generative models for the augmentations?

**Pratyaksh Singh:** uh I am going to change I'm going to train the segmentation model with it and then with loss analysis I'll try to find where it is it is kind of like lacking and then I will I'll try generating I'll try generating those examples in any way possible. If your question was for generative modeling,

**Hemanth Sarabu:** Got it.

**Pratyaksh Singh:** I think there are two more efforts that is going on where Sachin is working on getting open source data for pre-training or anything like that and then Ratul is also looking

**Hemanth Sarabu:** I

**Pratyaksh Singh:** in using these large vision models to to you know just generate examples without any finetuning to see if any of them succeed.

**Hemanth Sarabu:** I see. Um so I do think now is a good So you have a bunch of good um augmentations, right?

### **00:27:39**

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** Now is a good time to get a baseline on a sense of how well they work.

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** All

**Geoff Horowitz:** meaning meaning train on those augmentations.

**Hemanth Sarabu:** Yeah. Yeah. I mean if we can go to if we can go to uh what's your face Bridget and say

**Geoff Horowitz:** Yeah.

**Hemanth Sarabu:** this is with just your data and this is with your data and our synthetic stuff I think that'll be pretty strong

**Geoff Horowitz:** Yeah,

**Hemanth Sarabu:** case.

**Geoff Horowitz:** I agree with you.

**Hemanth Sarabu:** So if anything,

**Pratyaksh Singh:** right.

**Hemanth Sarabu:** we actually want to go to that meeting with with this with good news about our synthetic data gen pipeline having a substantial positive effect.

**Pratyaksh Singh:** Makes sense. That makes sense.

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** You want to show the difference. What I'll do is I'll train just one model without any augmentation which can

**Hemanth Sarabu:** Mhm.

**Pratyaksh Singh:** be baseline and then I can train one with uh when I say without any augmentation it can be like you know no augmentation at all apart from these fine transformation

### **00:29:00**

**Hemanth Sarabu:** Yeah, I think we should use um we should use

**Pratyaksh Singh:** Right.

**Hemanth Sarabu:** what I here's what I would do. Do a yeah like a actual vanilla augmentation with the simple aine stuff and then you want to do multiple variants of

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** yours, right? adding augmentation A, augmentation A, uh, augmentation B, augmentation C, augmentation D, augmentation ABC, B, C, D, something like that.

**Pratyaksh Singh:** Got

**Hemanth Sarabu:** And um um especially since this is pretty cheap to

**Pratyaksh Singh:** it.

**Hemanth Sarabu:** run, right? We should I would like you to sweep through that as soon as

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** possible.

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** And then it would be interesting to know how much of a Delta, we get boost. we get from the first statement of work the first project we did for bedrock um sorry I didn't phrase that correctly but it would

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** be good to know for the SA one we used some augmentations

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** right now whatever whatever the best that you get now how different is it is is actually the true is the true delta right um

### **00:30:22**

**Pratyaksh Singh:** Got

**Hemanth Sarabu:** unless we only used simple find rotations type

**Pratyaksh Singh:** it.

**Hemanth Sarabu:** stuff in which case they're the

**Pratyaksh Singh:** One thing that is kind of bothering me. Okay, I will I think we can discuss it on Wednesday, but like I think the validation set is like pretty small. So the difference is won't be that much visible but but you know we can I think we can discuss on it on Wednesday once we have the result.

**Hemanth Sarabu:** Okay, that's good.

**Pratyaksh Singh:** Uh I one thing I would also like one of us to do is like to go through this album's augmentation and then just see just see the output of it to be like you know what augmentations what like what classical augmentation that we can use apart from these apart from the copy pasting and things that we're

**Hemanth Sarabu:** Um, Sachin or Rul. Can one of you guys own

**Ratul Shashank:** Yeah, I will

**Hemanth Sarabu:** that?

**Pratyaksh Singh:** Uh ratul I think I think I would like you to focus on

**Ratul Shashank:** look

**Pratyaksh Singh:** the generative one Sachin if you have time because you know you are looking at open source data too, right?

### **00:31:55** {#00:31:55}

**Pratyaksh Singh:** So you know basically how the sites can sonar actually looks in different scenarios. So you and me we can we can do it together like I'll set up the training and then I'll have free time can create a

**Sachin Pandey:** Yes.

**Pratyaksh Singh:** sheet and then we can try it out together.

**Sachin Pandey:** Okay.

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** Cure. Anything else you wanted to

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** discuss?

**Pratyaksh Singh:** No, that's it from my side.

**Geoff Horowitz:** Um, okay. Sachin. Um, can you give us an update?

**Sachin Pandey:** Yes. So I uh after like the new like fixing the data set, we trained around six new models based on like the V1 are the one without V1 are the like original pipeline without any hyperparameters changes and V\_sub2 are like with some changes. So and in V1 we trained two mod three model. One is binary where like every class is like you know

**Geoff Horowitz:** Wait, wait.

**Sachin Pandey:** merged

**Geoff Horowitz:** I'm sorry, Sachin. I Something happened on my end.

### **00:33:31**

**Sachin Pandey:** h

**Geoff Horowitz:** I just lost the last like 30 seconds. Do you mind starting

**Sachin Pandey:** yeah so like there are uh two groups and each group contains three models.

**Geoff Horowitz:** over?

**Sachin Pandey:** The group one is the like original pipeline where there is no change in the hyperparameter. Group two is like the B2 is the where we change the hyperparameters and in V1 there are three models. One is

**Geoff Horowitz:** Oh, so I just want to be clear.

**Sachin Pandey:** binary.

**Geoff Horowitz:** So V1 is our is our baseline, right? So V1 is we used the old model,

**Sachin Pandey:** Yes.

**Geoff Horowitz:** the model that we delivered last time. We trained the new data uh and and that's that's the V1 results. Is that correct?

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Okay. Keep

**Sachin Pandey:** Yes. So we were like each group has uh I was

**Hemanth Sarabu:** What is the

**Geoff Horowitz:** coming.

**Hemanth Sarabu:** headline?

**Sachin Pandey:** just like uh explaining all the difference between model then we will see the results of the model.

### **00:34:33**

**Hemanth Sarabu:** Tell me the results first.

**Sachin Pandey:** uh insert model is improving because the like most of the mistakes in the data are reduced and we like we also find a way to increase the precision more like suppose this is the one and

**Hemanth Sarabu:** No, don't don't don't use don't use just tell me in words.

**Sachin Pandey:** like

**Hemanth Sarabu:** Don't use uh don't use a screen. What is the headline? What um what should we care

**Sachin Pandey:** okay so fixing the data

**Hemanth Sarabu:** about?

**Sachin Pandey:** like uh increase the final result but we are Still like seeing things

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** where model is predicting similar objects which

**Hemanth Sarabu:** Mhm.

**Sachin Pandey:** sometimes looks correct and uh and there are also places where the model is

**Hemanth Sarabu:** Mhm.

**Sachin Pandey:** like missing very obvious missed

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** things.

**Hemanth Sarabu:** So, we're doing better. Uh, and there's some Okay,

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** I I think I understand that. How much better than baseline are we doing?

**Sachin Pandey:** um almost all the fields uh I

### **00:35:36**

**Hemanth Sarabu:** Like how good is it? Is it is it really good? Is it is it

**Sachin Pandey:** I don't have a percentage no some fields are really good like AI big because uh after

**Hemanth Sarabu:** not?

**Sachin Pandey:** including the phase 2 the the VW data was increased so AI big performance was like uh heavily improved

**Hemanth Sarabu:** Okay. So if I give this to a customer,

**Sachin Pandey:** True.

**Hemanth Sarabu:** will they be happy with it? Will they be unhappy with it? Will they be somewhere in the middle?

**Sachin Pandey:** Somewhere in the middle.

**Hemanth Sarabu:** Somewhere in the middle. Okay. Um,

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** do we need to look at all these variants or do we need to only look at the the best performing one and maybe one or two more?

**Sachin Pandey:** all the variants in the

**Hemanth Sarabu:** So,

**Sachin Pandey:** model.

**Hemanth Sarabu:** you have you have a lot of variance here, right? Like um it looks like you have six tabs. Um okay.

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** Um are they Oh, am I going in and out?

### **00:36:35**

**Geoff Horowitz:** I can hear

**Hemanth Sarabu:** Okay. Okay. Okay. Google Meet is telling me my

**Sachin Pandey:** No.

**Geoff Horowitz:** you.

**Hemanth Sarabu:** videos. Okay. Um Okay. Sachin, I guess. Um what what what are the six tabs here like at a high level? Why why do they exist

**Sachin Pandey:** Like each type contains the information or metrics for each model.

**Hemanth Sarabu:** each model and um okay and the difference in the model are multiclass versus binary in the loss functions used

**Geoff Horowitz:** Well, one is one is you maybe this would be a good time for me to just walk us through.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** It looks like one is UXO and the other maybe isn't or

**Hemanth Sarabu:** Okay. Okay. All right. Um, yeah. Sachin, take away. Take it

**Sachin Pandey:** Okay.

**Hemanth Sarabu:** away.

**Sachin Pandey:** So binary class will be where everything is merged. Then there will be a multiclass where like we have the original annotation uh after fixing and then there is a UXO class where we like created another UXO class and pull all the targets which were like which client shared to into a UXO class.

### **00:37:59** {#00:37:59}

**Sachin Pandey:** So those are like generally difference. V\_sub\_2 is like better uh generally better in all the cases than V\_sub\_1 and V\_sub\_1 is

**Geoff Horowitz:** So what that means is so what that means is that V v1 is our baseline.

**Sachin Pandey:** like

**Geoff Horowitz:** So the fact that V2 is better than V1, V, excuse me, excuse me, that V2 is better than V1 means that, you know, we we're we're just improving, you know, through the hyperparameter,

**Sachin Pandey:** if Yeah,

**Geoff Horowitz:** we're improving on the data,

**Sachin Pandey:** by changing the loss and few things like model is learning

**Geoff Horowitz:** right?

**Sachin Pandey:** mode.

**Geoff Horowitz:** Okay.

**Sachin Pandey:** So, so this will be like our baseline the V1 without any changes and the model which we did last time.

**Geoff Horowitz:** That specific one. Multiclass excluding lines.

**Sachin Pandey:** Yes. So yeah, so if you see like the ground truth object and the prediction object are like very very different like there is a lot of false positives and this is like when I was viewing the predictions there were like small points like random points like these which were like creating these issues some these points these points.

### **00:39:26**

**Sachin Pandey:** So I just added a filter to see like how like just changing removing the pixel like per pixel drop how much like change we can get and if you see the F1 score and the value is increasing a lot without like dipping the actual data. So around like for this specific data around like 53 is the point where we can increase without any decrease in any of the values and this alone like improves a lot of like uh false positive and increase overall value.

**Geoff Horowitz:** So this is a size

**Sachin Pandey:** Yes,

**Geoff Horowitz:** filter.

**Sachin Pandey:** on the predictions generally

**Hemanth Sarabu:** So what is the best model here?

**Sachin Pandey:** uh like like if we like which way we want to go whether we want to like use the UXO or without UXO. So these two will be the best one and if you don't want to split then this will be the one.

**Hemanth Sarabu:** Actually

**Geoff Horowitz:** So we we care about UXOs, right? So if we don't use UXOs, what's the effect of

**Hemanth Sarabu:** let me ask you Sachin.

### **00:40:53** {#00:40:53}

**Hemanth Sarabu:** Suchin which one can we are they interchangeable?

**Geoff Horowitz:** that?

**Hemanth Sarabu:** Can we give either one to the customer?

**Sachin Pandey:** Yes. Like as Jeff said, we we want a toggle like we where customer can switch between the

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** models and something like this will be appear like

**Geoff Horowitz:** just just now you can

**Sachin Pandey:** different model different predictions.

**Geoff Horowitz:** Yeah. Yeah. So, so to your question, it sounds like yes, we can get both models and it'll be like a drop down, right, Sachin?

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** I'm wondering if uh if how do we compare uh I guess my my question is how do we compare these two?

**Sachin Pandey:** UX and nonexo

**Hemanth Sarabu:** Yeah. How does uh so if we give it to the customer the customer needs to make a call about using one or the other, right? So, how how how does one make that

**Sachin Pandey:** Yeah.

**Hemanth Sarabu:** determination?

**Sachin Pandey:** Like if if customer wants UXO then UXO model will be much better because it it like it learns a lot of feature and like generally it is trained on the data which they have marked as UXO not the like similar looking thing but not UXOR in different class

### **00:42:39**

**Geoff Horowitz:** What?

**Sachin Pandey:** completely

**Hemanth Sarabu:** Do we have a recommendation?

**Geoff Horowitz:** Why would

**Hemanth Sarabu:** Like for example, are we saying something? A recommendation could be something like look, we don't have enough UXO examples, so there's no point actually using the UXO model. You should use the other model until we have enough UXO examples. Right? That's a recommendation. Do we have a recommendation? One model versus the

**Sachin Pandey:** So I think UXO one will be better because it will at least give some idea whether it is a UXO even if it's not a

**Hemanth Sarabu:** other.

**Sachin Pandey:** UXO it will like move it to the AY small which is like similar thing like UXO object but not model is not confident it's a UXO something like this where it made the mistake ground to UXO

**Hemanth Sarabu:** So,

**Sachin Pandey:** and it marked as a small

**Hemanth Sarabu:** so here's what I will say. um is that actually a delta like if generally our model is not good at getting a

**Sachin Pandey:** Black.

**Hemanth Sarabu:** UXO then maybe it's better to not predict a UXO right what is a precision recall for the UXO class

### **00:43:38**

**Sachin Pandey:** It's low. This is pixel

**Hemanth Sarabu:** is there a way what is the um that is pixel based okay and this is object

**Sachin Pandey:** base.

**Hemanth Sarabu:** level Okay.

**Sachin Pandey:** Yeah.

**Hemanth Sarabu:** Mhm.

**Sachin Pandey:** around

**Hemanth Sarabu:** H.

**Sachin Pandey:** 50\.

**Hemanth Sarabu:** So if this is if this is object level uh Okay. And then this is object level confusion matrix down

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** below.

**Sachin Pandey:** So six correct one is different class uh eight in background.

**Hemanth Sarabu:** So this is actually very cool by the way. This app is very cool that you can click and get these examples. But so if you go up right, you scroll up a little bit. My guess is our customer will not be okay with this particular model

**Sachin Pandey:** See?

**Hemanth Sarabu:** because your UXO recall is 40%. Even though precision is 60%. Now are are these UXOs going are we confusing? It looks like a lot of these UXOs are just going into background. like we don't even detect them into another class.

### **00:44:47**

**Hemanth Sarabu:** Right?

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** So that is bad. That's quite bad. Um, And what about the other model? So, okay, do you get do you get where I'm going with this? So this model would probably not be good for our customer because

**Sachin Pandey:** Yes, but there is like one more catch here, right? Because same location may not capture the same details uh like multiple

**Hemanth Sarabu:** we're

**Sachin Pandey:** XTF from the same location may not capture the like same details in each one. So suppose this is the location but it was detected in like five other one but in this one because of the image it didn't get detected but like if we can like if we will be giving the final output in the like uh latl longl long coordinates and there will be like five six u uh detection for this specific UXO even though this in this specific file we didn't detect

**Hemanth Sarabu:** I I get what you're saying. Um Okay. Um, so when you're actually when we're actually running this, so the model will should be expected to pick out a UXO if visually it looks there looks like there's a UXO there, right?

### **00:46:19**

**Hemanth Sarabu:** That's it. Um, now if you're saying are you saying that in some of these images you can't actually see the UXO

**Sachin Pandey:** Yes. And the reason we marked it because like we know this location is marked in other file and unless

**Hemanth Sarabu:** even

**Sachin Pandey:** it's in the black region we are like marking it as a UXO.

**Hemanth Sarabu:** understood. So, but this is uh not something. So, there's like a there's a bug in the way we we compute the metrics then. So, maybe maybe you should go through this and discount images where our labelers would not pick out a UXO, right?

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** Otherwise, we won't know. We we will have we have contaminated metrics. Do you agree?

**Sachin Pandey:** Yeah. So these are these will be like false positive and these two

**Hemanth Sarabu:** False. Positive.

**Sachin Pandey:** are because this is the one where ground to is using like marking it as

**Hemanth Sarabu:** Uh, okay.

**Sachin Pandey:** UXO. These all are false positive.

**Hemanth Sarabu:** Okay.

### **00:47:47**

**Hemanth Sarabu:** It looks like false positive is not much of an issue as the false negative, right? Because if you scroll back up, okay, actually if you look at the confusion matrix, So, our recall is 40%, which means we're missing 60%. UXOs. Uh,

**Sachin Pandey:** Yeah,

**Hemanth Sarabu:** and I guess the numbers are pretty small if we're getting 667 and stuff, right? Is this out of 10 examples total? Something like that.

**Sachin Pandey:** the screen.

**Hemanth Sarabu:** Ah, 15\. Okay. Okay. So Sachin, you're telling me the recall number is actually not correct.

**Sachin Pandey:** Any

**Hemanth Sarabu:** Then we need to fix it.

**Sachin Pandey:** idea how we can fix it?

**Hemanth Sarabu:** So why is the recall number wrong?

**Sachin Pandey:** Because we have marked the annotations which may like which like object is there but not visible in the specific file in that specific file.

**Hemanth Sarabu:** Okay. So,

**Sachin Pandey:** Plus the

**Hemanth Sarabu:** we just need we need we need to find the files those files and

**Sachin Pandey:** Yeah.

**Hemanth Sarabu:** discount those examples, right?

### **00:49:22** {#00:49:22}

**Sachin Pandey:** Yeah. These were like some examples. The object is not visible but marked as UXO. We we will be removing these from the metric calculation.

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** Wait one more thing.

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** It was on 50%.

**Geoff Horowitz:** I don't know if you guys talked about this hem on but such and I were discussing that you know 50% might be a good metric for us to look at internally a 50% overlap but if you recall when we presented to bedrock we used 0.01 1, meaning any sort of overlap says, "Hey, there's an object here. Look over here." Even if we're not highlighting the entire

**Hemanth Sarabu:** I Yeah, I I don't actually remember that, but I believe

**Geoff Horowitz:** opa,

**Hemanth Sarabu:** you. Okay, I got to run. Um,

**Geoff Horowitz:** I missed a little bit of that conversation. So, I just want to confirm my understanding here. Basically, you're saying that because we had because we knew where these UXO objects were and we had multiple images where they should exist from a from a byma where they should exist from a

### **00:51:08**

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** um you know a georreerencing space. They don't they don't necessarily exist from a visual space,

**Sachin Pandey:** Yes.

**Geoff Horowitz:** right? But they but they were being uh included as annotations.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** And so even though the model couldn't see them, it was saying, "Oh, they should be

**Sachin Pandey:** There is something. Yeah,

**Geoff Horowitz:** there."

**Sachin Pandey:** because like when we decrease the overlap, this is this is the only file like where the model didn't predicted anything and like it is a

**Geoff Horowitz:** Uhhuh.

**Sachin Pandey:** background but the annotations are saying something different and like this one where the completely

**Geoff Horowitz:** I I I do I do think like you know something higher than

**Sachin Pandey:** missed.

**Geoff Horowitz:** 0.01 is a better space for us to work in because because it tells us more about how the model's thinking, right? and and what's actually going on even if we don't end up presenting those to

**Sachin Pandey:** Yeah,

**Geoff Horowitz:** Bedrock.

**Sachin Pandey:** I think this filter will be helpful like we can actually like for classes like these where the generally the objects are very big.

### **00:52:26**

**Sachin Pandey:** We can like set some kind of filter there because if you see the precision is like heavily increased if we just drop the noise.

**Geoff Horowitz:** Uh-huh. Um,

**Sachin Pandey:** So

**Geoff Horowitz:** we we expose this filter to bedrock, right?

**Sachin Pandey:** uh we can like it is just the it is done on the final prediction similar

**Geoff Horowitz:** Uh, my recollection is that on our actually I'll look right

**Sachin Pandey:** to like confidence

**Geoff Horowitz:** now. I'll look right now.

**Sachin Pandey:** Amen.

**Geoff Horowitz:** I guess we weren't we weren't doing it on this one, but yeah, on the last on one version of the um the bedrock um you know the bedrock viewer. Yeah, exactly. We were we were exposing confidence and we were exposing like filter minimum filter size, right? Yeah.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** So, so I mean that's fine then we are we are showing this. So

**Sachin Pandey:** And like one more thing uh this uh sand patches are not like we we don't want this

**Geoff Horowitz:** hey Sachin,

**Sachin Pandey:** right.

**Geoff Horowitz:** can you can you do uh Okay, hold on.

### **00:53:50** {#00:53:50}

**Geoff Horowitz:** You asked me a question. Um, sand patches. We don't want them. Which one are sand patches?

**Sachin Pandey:** Because

**Pratyaksh Singh:** Oh, hey Jeff. Uh, sand. They don't care about sand rippers like right. They only care about AI and mines.

**Geoff Horowitz:** Correct. She for the first project she was kind of interested in what we could do with sand ripples but she she didn't care that we excluded them from the uh from the training set. So oh uh until he comes back. Satcha can can we add something to this um to this table which is improvement over like so if you can imagine kind of in parentheses next to the numbers maybe in green or in red we could do improvement against the baseline model do you understand what I'm saying?

**Sachin Pandey:** Yeah. In in this one,

**Geoff Horowitz:** Yeah.

**Sachin Pandey:** right?

**Geoff Horowitz:** Like like plus 002 or something like that, you know.

**Sachin Pandey:** Yeah. And like how did you cater this table?

**Geoff Horowitz:** Yeah.

### **00:55:07**

**Sachin Pandey:** Is this like you copied the HTML

**Pratyaksh Singh:** Yeah,

**Geoff Horowitz:** Uh I if I recall correctly,

**Pratyaksh Singh:** exactly.

**Geoff Horowitz:** I copied and pasted the table into this thing and then I had Gemini reformat it. But I'm not positive about that.

**Pratyaksh Singh:** What's your name?

**Sachin Pandey:** something.

**Geoff Horowitz:** This might have been the one that I just copied and pasted. You're right.

**Sachin Pandey:** Okay. Yeah, you copied the the top one. I went

**Geoff Horowitz:** Oh, okay. Cool. project I don't know if you heard the answer to my question before or your question rather which was bedrock did not care about sand ripples but if we so that's why we moved it to a different class initially but if we can predict on them then I think she was interested in seeing those results so it's

**Pratyaksh Singh:** got it.

**Geoff Horowitz:** up to us

**Pratyaksh Singh:** Yeah, I think like I would start with just predicting those simple object because since sand ripples are like very big, they give a model a lot of signals,

### **00:56:14** {#00:56:14}

**Geoff Horowitz:** Okay.

**Pratyaksh Singh:** right? So and that's why you know that focus on what matters and then we can do rest of the

**Geoff Horowitz:** Okay.

**Pratyaksh Singh:** things.

**Geoff Horowitz:** That's

**Sachin Pandey:** like we can increase the prediction like sand ripple can be predicted easily just that like

**Geoff Horowitz:** reasonable.

**Sachin Pandey:** we need to drop the like low signals one like this one and these ones they are little by little bit like sand ripple but they don't have like strong signals like these where modul can easily pick them and the matrix is going down because of these files where we are like pulling each and every small signal something like these

**Pratyaksh Singh:** But anyways like you know it doesn't matter so you don't have to focus on sand ripples more I think the UXO and small patch black uh sorry small black patch that matters more right

**Geoff Horowitz:** Yeah.

**Sachin Pandey:** And like a

**Pratyaksh Singh:** Sachin I also saw one thing that you know in the VW data set there weren't any AOI small black like everything was in AOI support. Can you go through it?

### **00:57:42**

**Sachin Pandey:** device model.

**Pratyaksh Singh:** Can I go through the data set and see because uh

**Sachin Pandey:** So

**Pratyaksh Singh:** can I show the image possible?

**Sachin Pandey:** yeah. Uh it will be only Yeah.

**Pratyaksh Singh:** Yeah. Okay. Can you go to next? So, see there are only seven images, right?

**Sachin Pandey:** Yes.

**Pratyaksh Singh:** And uh and if you'll just uh can you open AI support? Yeah. Okay. Go to next. Next.

**Sachin Pandey:** We need like

**Pratyaksh Singh:** Next. No, no. Go to next. Okay. So, you see this top image?

**Sachin Pandey:** small.

**Pratyaksh Singh:** Okay. Go to next. I think it's fine. Go to next. Go to next. I share one example too. Uh maybe next. Yeah. Yeah. Okay. Next. Maybe. Yeah, these examples, right?

**Sachin Pandey:** Yes,

**Pratyaksh Singh:** So here uh I don't understand like should they be in AOI small black or should they be in support these black patches?

### **00:59:29** {#00:59:29}

**Sachin Pandey:** these ones.

**Pratyaksh Singh:** No. No.

**Sachin Pandey:** These

**Pratyaksh Singh:** One in the starboard. Okay. Okay. Leave it. I'll find find example and I'll share with you that particular one.

**Sachin Pandey:** Yeah, generally like uh because like these features are these are AI supports but because they are like very similar to the black patch. So in this iteration we like combine both of them generally like uh if AI big is there there will be four uh of these things in a rectangular way.

**Pratyaksh Singh:** Uh and S also like if you're updating the annotation like uh update the

**Sachin Pandey:** Yes. Uh in this file

**Pratyaksh Singh:** update the latest annotation on the on the viewer.

**Sachin Pandey:** right I'll just drop the file

**Pratyaksh Singh:** Yeah.

**Sachin Pandey:** here.

**Pratyaksh Singh:** All right. Perfect.

**Sachin Pandey:** You can also use this one. I this is only for the training data and like you can select the classes here. So like black hat smooth black it doesn't do the filtering on data set level it will like store the files I will move

### **01:00:48**

**Pratyaksh Singh:** Got

**Sachin Pandey:** the data we want with the UXO right where the UXO is marked

**Pratyaksh Singh:** Yeah, the one where UXO is marked and then I think in your update you said that uh cleaning the data set improved performance too. That thing I shared an image where uh where I do I think you know AOI support black is marked incorrectly. if you'll scroll through VWA, I think I'm sure you will be able to find more images too. But anyways,

**Sachin Pandey:** You shared it on

**Pratyaksh Singh:** no on on the mid

**Sachin Pandey:** WhatsApp.

**Pratyaksh Singh:** chat.

**Sachin Pandey:** The one was this image

**Pratyaksh Singh:** If you just Press next. I think it's that image. I just randomly shared it with you.

**Sachin Pandey:** Oh.

**Pratyaksh Singh:** I think I found it on more images. I shared one is a similar example on on our WhatsApp. Yeah, here also.

**Sachin Pandey:** So

**Pratyaksh Singh:** Yeah.

**Sachin Pandey:** this

**Pratyaksh Singh:** My point being is that you know the model has no way to differentiate between a support and a black patch.

### **01:03:28** {#01:03:28}

**Sachin Pandey:** Yeah, that's why we we merged it in the latest one. I will update this

**Pratyaksh Singh:** Okay,

**Sachin Pandey:** soon.

**Pratyaksh Singh:** I'm sorry.

**Sachin Pandey:** Um I want to train one more model where we will like only choose the like featur high visible features. I think it will really help because the mistakes we see in the model are like where the features are not strong.

**Pratyaksh Singh:** Understood.

**Sachin Pandey:** So like if we just train the model to choose like these high features and not any any shade like these. So I think the values will be like will increase a lot

**Pratyaksh Singh:** Yeah, but like one thing to consider also is that uh if they're actual contact,

**Sachin Pandey:** more.

**Pratyaksh Singh:** you're not training the model on it. Even if you even if you you know increase the performance, it won't be useful to them. So if you remove annotation, make sure that you know those are not actual ones, right? Actual ones that in the sense that the one that Bedrock gave us or the one that Bedrock uses All

### **01:04:39** {#01:04:39}

**Sachin Pandey:** Yeah. So okay those are those are not getting removed for VW data set all of the annotations are in like this one and for a tx and brn all are in this one. These two class contains like all the almost all the annotation that we got from the

**Pratyaksh Singh:** right.

**Sachin Pandey:** client.

**Pratyaksh Singh:** Got it. So for rest of them I think you can we the reason that we added it was to improve model performance. So you can remove them as you see fit.

**Sachin Pandey:** Yeah, I will be dropping the sand patch. Actually, there is let me just check it. I train started a training model where I dropped the sand patch one.

**Pratyaksh Singh:** Okay.

**Sachin Pandey:** Uh there's two models. One where I drop the sand patch and other I just merge it with the sand ripples. So at least just

**Pratyaksh Singh:** Perfect.

**Sachin Pandey:** that I will predict on this to see the like object wise classification. Practice learning.

**Pratyaksh Singh:** Okay, makes sense.

**Sachin Pandey:** Yeah, like adding filter was like helping a lot.

### **01:06:17** {#01:06:17}

**Sachin Pandey:** So, this is just a graph. Uh, I need to simplify it even more. I I'm not able to understand it properly but like then these numbers are at least good. So at least the the like default value of 10 pixels there's a lot of false positive which are getting performed and this much we can increase without like affecting the true positives. Even in this like if we like it even in this specific example if I increase it to even 100 the correct class were not reduced at all. So in this one like two classes are getting dropped but overall the pretty left one score jump is quite like 20%.

**Geoff Horowitz:** Anything else we needed to discuss on that item?

**Sachin Pandey:** Jeff, uh, do I need to test the F1 score in

**Geoff Horowitz:** Say, say once

**Sachin Pandey:** this?

**Geoff Horowitz:** more.

**Sachin Pandey:** Do I have to add the S F1 score only or

**Geoff Horowitz:** Support precision recall F1. What's the second line?

**Sachin Pandey:** This is

**Geoff Horowitz:** Oh, no.

**Sachin Pandey:** flag.

**Geoff Horowitz:** Oh, for V2.

### **01:09:32** {#01:09:32}

**Geoff Horowitz:** All the stuff to the left is for V1 and you're asking if you should add it for V2.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** So SA I here's the thing.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Adding it right there is just going to confuse us, right? Because the point of that table is to address one

**Sachin Pandey:** something

**Geoff Horowitz:** question. That question is the baseline.

**Sachin Pandey:** else.

**Geoff Horowitz:** Does that make sense? I I'm not opposed I'm not opposed to another table elsewhere that show,

**Sachin Pandey:** Yes.

**Geoff Horowitz:** you know, compares the baseline to the to the updated model. I also think maybe we can um like like I mentioned before, we can kind of condense that information by just showing like a a diff type thing. Do you know what I mean? You do know what I mean by a diff.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Okay. Um, but I I I think we should organize this information in a way that's very easy to follow. Um, yeah, like you're doing there.

**Sachin Pandey:** Do we need to update the baseline like instead of this should

### **01:10:42** {#01:10:42}

**Geoff Horowitz:** Do we need

**Sachin Pandey:** we take uh like baseline for this one updated data same pipeline

**Geoff Horowitz:** updated data, same pipeline. Um, meaning updated for the the reabeling that we did, right?

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Yeah. I I I think I think the updated data should be our baseline.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Yes. Um, right. like like we should use we should assume that the baseline stems from from the best quality data that we have that we're going to use throughout and that's our baseline everything from there ideally we're not touching the data anymore right we're just touching the model do you agree with that yeah

**Sachin Pandey:** Yeah. So then we need multiple

**Geoff Horowitz:** Okay.

**Sachin Pandey:** baseline

**Geoff Horowitz:** So then we need multiple baseline. What do you mean?

**Sachin Pandey:** because I will be making few more changes in the data set.

**Geoff Horowitz:** Okay. I've Look, it's it's not and you you know this suction,

**Sachin Pandey:** So,

**Geoff Horowitz:** it's not like great practice to be updating, you know, your baseline be because we we want to do all these comparisons with if we're changing the data and we're changing the model and we're changing all these other things, then we don't really know improvement, right?

### **01:12:19**

**Geoff Horowitz:** That said,

**Sachin Pandey:** here we go.

**Geoff Horowitz:** I mean, you know, that said, we're trying to get apples to apples comparisons here. And so, if we do need to update the baseline because we updated an underlying annotation, then that will that helps tell the story in the most accurate way possible. Do you follow me here? Okay.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** S and does this make sense how I'm thinking through

**Sachin Pandey:** Yeah. Like then Yeah,

**Geoff Horowitz:** this?

**Sachin Pandey:** I get it. Like when we change the data we like the baseline the same like just by changing the data set base data set the difference is like quite huge and like then we will not be able to compare

**Geoff Horowitz:** Yeah. Yeah.

**Sachin Pandey:** it but this the thing we are struggling with is like the better the data

**Geoff Horowitz:** I mean, it's not great practice.

**Sachin Pandey:** the like the good the predictions are and because we didn't get like uh like most of these classes labeled by the client we are like not sure whether like some of these are even true or not.

### **01:13:24** {#01:13:24}

**Geoff Horowitz:** Uh-huh.

**Sachin Pandey:** What to include it? What to include? What not to include. So those are the like issues which we are like trying to fix by changing the data set base data

**Geoff Horowitz:** Sachin, I'm gonna say the same thing that I always say.

**Sachin Pandey:** set.

**Geoff Horowitz:** If we have a specific list of questions, right, let's include them in a a PowerPoint, right?

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** Ask the specific question which is, you know, we think this looks like such and such. Do you agree? Right? And I will bring I'll bring that up to Bedrock. I'll or I'll share the I'll share the deck with Bedrock and I'll ask them for clarification.

**Sachin Pandey:** budget is bad or better tech.

**Geoff Horowitz:** Bridget is Bedrock.

**Sachin Pandey:** Okay. When is the meeting?

**Geoff Horowitz:** Uh, Thursday the

**Sachin Pandey:** 23rd.

**Geoff Horowitz:** 23rd.

**Sachin Pandey:** Okay. I will I will share a doc with you like for something yeah for mainly like sand ripples and black

**Geoff Horowitz:** Okay.

**Sachin Pandey:** patches I will get a doc where like what to include in the data and what not

### **01:14:27** {#01:14:27}

**Geoff Horowitz:** Okay. She's Yeah, obviously Sachin, she's gonna she's going to need some sort of like file reference, data set reference, and then like um you know, some way to reference in that file where we're looking. Um could do that.

**Sachin Pandey:** So like Jio location.

**Geoff Horowitz:** You know, we could just we give her an annotated file. We could I mean there's there's a few options here. I just want to as we do this, we're going to need to give her some information to be able to look at it offline.

**Sachin Pandey:** Yeah. Uh the task will be to uh create a report and also the JSON file which is gio reference so that they can drag and drop on the XTF directly or

**Geoff Horowitz:** Yeah. Yeah, I think that makes sense.

**Sachin Pandey:** mosaic.

**Geoff Horowitz:** I think that makes sense. Yeah,

**Sachin Pandey:** Okay.

**Geoff Horowitz:** that's a good way. Um, okay. You're way over time, but that always happens. That's okay. Any other questions here? Satchin, one other thing.

### **01:15:47** {#01:15:47}

**Geoff Horowitz:** Um, are these reports that you make are they are they static? Do they live forever?

**Sachin Pandey:** that yeah they are like posted on portry I can just share the link with

**Geoff Horowitz:** like poetry.

**Sachin Pandey:** you yeah I've ced this folder and all

**Geoff Horowitz:** Um I So I imagine it

**Sachin Pandey:** the HTMLs live Good.

**Geoff Horowitz:** would be good to kind of in a dock or something be documenting the progress and improvement that you're making over time. Um, so I don't I don't really know what that would look like, but let me kind of show you at least what I'm what I'm thinking here. Um, there's our running notes. So, I mean, here's here's an example. So, we're doing the metrics um for something like, you know, model trading progress, right? And so something where like you could it it might just be as simple as adding you know the date and then you know link to report right and then what's the TLDDR here right um and so for TLDDR what are we thinking we're thinking like the why right so why why did we run you know this experiment Um what were the and this is like uh you know I don't know um what's what's an example like uh UXO recall was very low right um looking to improve I don't know false positive whatever

### **01:17:40**

**Geoff Horowitz:** the case is right so why did we do it what were the results

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** right and Um, I don't know. Any other notes, comments, maybe next steps if you if you know them. Uh very short, but just something that like, you know, we can kind of look at this and say, "Oh, you know, last week you were working on this. Um, you know, this is what it was. You want more detail? Go to the report." I I I'm not even sure how we would use it, but you're doing all this work anyway, and I don't want it to get lost. And I think that as we over time, you know, have a lot of these stacked up, like it's very kind of easy to see how that progress improved over time. Um,

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** if you have a better idea or a better setup or whatever, by all means, use it.

**Sachin Pandey:** No,

**Geoff Horowitz:** This is just something that comes comes

**Sachin Pandey:** I'm doing the same thing but only for like tracking the training and what things we are

### **01:18:41** {#01:18:41}

**Geoff Horowitz:** from

**Sachin Pandey:** changing, where the changes files are.

**Geoff Horowitz:** Uhhuh.

**Sachin Pandey:** Uh these are like mainly for training. I didn't included a matrix. uh I will include those two like old data old metrics are there but new metrics are not yet updated in

**Geoff Horowitz:** Yeah.

**Sachin Pandey:** the file

**Geoff Horowitz:** Gotcha. Gotcha. Okay. That's so that's a thought that I have. Um as Yeah, you could put this in the report too, but ah okay. Not not trying to throw too much at you. That's a thought. Um, okay. Rul, did you get a chance to start testing out some of the MAD stuff that we talked about on Friday?

**Ratul Shashank:** Yeah. So the problem uh I mean we have not seen much uh improvement. I tried a bunch of stuff uh but uh the location accuracy uh it is still the same like 5 to 10 m.

**Geoff Horowitz:** Do you have this overlaid on side scan data?

**Ratul Shashank:** uh I am right now I'm using for entx data set

### **01:20:11** {#01:20:11}

**Geoff Horowitz:** Okay. Do you so do Do you have it over?

**Ratul Shashank:** and

**Geoff Horowitz:** Do you have the location of the MAG data overlaid on the ENTX size scan

**Ratul Shashank:** I I I have not overlaid But uh I can do

**Geoff Horowitz:** data?

**Ratul Shashank:** that. It won't be a

**Geoff Horowitz:** Okay. Okay. I do not anticipate discussing unless Rul unless we have specific questions

**Ratul Shashank:** problem.

**Geoff Horowitz:** for Bridget. I do not anticipate discussing the mag data with her. Again, I'm going to repeat that. I can discuss it if we have specific questions that we want to ask, but right now I don't anticipate discussing saying our progress

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** there. Um, happy to happy to discuss more with you guys why project option might be the most interested, but uh but that's that's the plan right now.

**Ratul Shashank:** I understand. I understand. And uh as far as the location accuracy goes as we mentioned uh even 5 to 10 m I mean it is uh pretty useful at this point.

### **01:21:28** {#01:21:28}

**Geoff Horowitz:** I agree with

**Ratul Shashank:** So we don't we don't uh we might not need

**Geoff Horowitz:** you.

**Ratul Shashank:** any uh input from bedrock. Uh but yeah uh I uh just to clarify when you say overlay the sides scan data you mean to like create a report kind where image is on top and the metadata is on bottom. Is that what you are

**Geoff Horowitz:** I what am I saying? I'm saying let me share

**Ratul Shashank:** saying?

**Geoff Horowitz:** this. What I'm saying at least right now could be something as simple as like you've got a series of images and you know we know we know our object is right here and the the mag data says the object is right here for

**Ratul Shashank:** Okay. Select two panes, right?

**Geoff Horowitz:** example.

**Ratul Shashank:** Uh one pane would be the XTF image and another pane would be the mag data uh the amplitude, right?

**Geoff Horowitz:** Sure. I uh one will be the mag data, one will be the amplitude. So I think go

**Ratul Shashank:** uh like like they share the like the images that bedrock shared we

### **01:22:41**

**Geoff Horowitz:** ahead.

**Ratul Shashank:** can it would be also easier to understand visually

**Geoff Horowitz:** Yes. Okay. Yes. Yes. Yes. But yes,

**Ratul Shashank:** Health.

**Geoff Horowitz:** but I also want you to create some sort of marker, some marker that actually shows up on the sides scan image wherever wherever we would predict that object

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** to be.

**Ratul Shashank:** Okay. Okay. I understand. I understand.

**Geoff Horowitz:** You follow me?

**Ratul Shashank:** Yeah. So I can do one thing. I can create two planes uh and I can highlight the area where in the image I can highlight the area where mag is showing. So everything would be segregated and also it would be understandable.

**Geoff Horowitz:** Where?

**Ratul Shashank:** It's understandable.

**Geoff Horowitz:** Where the peak is? Where the peak is.

**Ratul Shashank:** Yeah.

**Geoff Horowitz:** Oh, you can't see my mouse,

**Ratul Shashank:** Yeah.

**Geoff Horowitz:** can you?

**Ratul Shashank:** Yeah.

**Geoff Horowitz:** Oh,

**Ratul Shashank:** It is visible.

**Geoff Horowitz:** you can. Okay. Yeah.

### **01:23:41**

**Geoff Horowitz:** Yeah. Only where the peak is, not where all the metad data is.

**Ratul Shashank:** Yeah. on only where the amplit a amplitude is showing the peak. Uh I will highlight that particular

**Geoff Horowitz:** Yeah,

**Ratul Shashank:** area.

**Geoff Horowitz:** cool. Okay.

**Ratul Shashank:** Yeah. Buddy.

**Geoff Horowitz:** Um I do think at least right now at least right now I do think that whatever you're doing with Pratio needs to take priority. Uh but in your in your spare time or while you're waiting for models to

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** train or things like that uh you know work on

**Ratul Shashank:** Yeah.

**Geoff Horowitz:** this.

**Ratul Shashank:** I mean there is not uh the uh the majority of work is done so it won't be a

**Geoff Horowitz:** Okay, great. Okay, guys.

**Ratul Shashank:** problem

**Geoff Horowitz:** Uh, anything else anybody wants to bring up?

**Ratul Shashank:** on my Thank

**Geoff Horowitz:** Okay.

**Sachin Pandey:** No.

**Geoff Horowitz:** All right. Hey, Pia,

**Ratul Shashank:** you.

**Geoff Horowitz:** why don't you call into these meetings?

**Pratyaksh Singh:** Why don't I call into these meetings?

### **01:24:54** {#01:24:54}

**Geoff Horowitz:** Yeah.

**Pratyaksh Singh:** I don't know. There's something weird like my internet is good right now but after some time it will just disconnect on its own and then it

**Geoff Horowitz:** I just don't you guys I tell me if I'm

**Pratyaksh Singh:** will

**Geoff Horowitz:** wrong. Don't you have like a you know at least in the States we have like a call-in number so like I can call in and then and then log in on my computer for the video but then like it won't drop

**Pratyaksh Singh:** Uh-huh.

**Geoff Horowitz:** my audio at least.

**Pratyaksh Singh:** got it.

**Geoff Horowitz:** Do you do you guys do

**Pratyaksh Singh:** I I'll try it out. try the calling and out but I think it's usually US number right so I don't know if that will work for

**Geoff Horowitz:** that? Ah, got it. Got it. Okay. So,

**Pratyaksh Singh:** India

**Geoff Horowitz:** then maybe it won't work. Um, well, it was just a thought. But, all right, guys. Uh, thanks for everything. Let me know. Let me know. Um I guess both project and Sachin if you if you get anything tomorrow and you know we want to iterate on it and get some feedback we can do that too. Just ping me.

**Ratul Shashank:** All

**Geoff Horowitz:** All right. Thanks guys. Bye.

**Sachin Pandey:** Okay.

**Ratul Shashank:** right.

### **Transcription ended after 01:27:23**

*This editable transcript was computer generated and might contain errors. People can also change the text after it was created.*
