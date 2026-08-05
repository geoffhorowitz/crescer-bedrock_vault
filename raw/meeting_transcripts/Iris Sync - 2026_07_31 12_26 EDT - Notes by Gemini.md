# **📝 Notes**

Jul 31, 2026

## **Iris Sync**

Invited [Sachin Pandey](mailto:sachin@crescer.ai) [Pratyaksh Singh](mailto:pratyaksh@crescer.ai) [Hemanth Sarabu](mailto:hemanth@crescer.ai) [Geoff Horowitz](mailto:geoff@crescer.ai) [Ratul Shashank](mailto:ratul@crescer.ai)

Attachments [Iris Sync](https://calendar.google.com/calendar/event?eid=NnNzMHVxNzk3MmJqZGVwNXFoN2J1Mjd1OTdfMjAyNjA3MzFUMTYzMDAwWiBnZW9mZkBjcmVzY2VyLmFp)

Meeting records [Transcript](https://docs.google.com/document/d/1l_FF_ggA9XbU_QljVFN5kHQFaibT-PsvKiGTHrCaklQ/edit?usp=drive_web&tab=t.qtq39wpxqi6v) [Recording](https://drive.google.com/file/d/1Wlf5qi5rs2G8Zxo5Iv--_7FXPfkKrD5D/view?usp=drive_web) 

### **Summary**

The team reviewed data documentation, corrected model bugs, and discussed synthetic data generation strategies for project development.

**Data Documentation and Validation**  
Participants confirmed configuration file locations and verified object grouping logic for sonar data. They decided that a map of identified objects is unnecessary for identification.

**Model Updates and Performance**  
Updates addressed bugs in metrics and overlaps, while training for the K-fold model was paused due to performance issues. The July 27 version remains the current performance baseline.

**Synthetic Data Generation Strategy**  
The team pivoted to using pixel crops and a low-rank adaptation model for object generation. Discussions focused on optimizing diffusion model efficiency and dataset quality control.

### **Decisions**

## Aligned

* **File categorization documentation protocol** The file documentation protocol is established to split files into groups where each group is defined as a unique object, with duplicates from multiple scan sonar passes accounted for accordingly.

* **Pixel cropping object manipulation methodology** Pixel cropping is adopted as the standard methodology for object manipulation, replacing the raw XTF value manipulation approach due to its increased effectiveness.

* **Latent diffusion model validation strategy** The team will utilize latent diffusion models and latent distance metrics to evaluate, compare, and prune generated data sets.

We've **updated the Decisions section** using your feedback.

Let us know what you think: [Helpful](https://google.qualtrics.com/jfe/form/SV_5bXzKQfylMIhSXc?isHelpful=True&entryPoint=decisions&confid=qQJrqeZ6xRGt0zfKG1DODxIUOBEBMgUIigIgABgBCA&isGoogler=False) or [Not Helpful](https://google.qualtrics.com/jfe/form/SV_5bXzKQfylMIhSXc?isHelpful=False&entryPoint=decisions&confid=qQJrqeZ6xRGt0zfKG1DODxIUOBEBMgUIigIgABgBCA&isGoogler=False)

### **Next steps**

- [ ] \[Ratul Shashank\] Cross check objects: Verify the orientation and XTF source of the objects to confirm they are not from the calibration path.

- [ ] \[Sachin Pandey\] Update k-fold results: Update the k-fold model results in the Bedrock channel and notify Geoff Horowitz and Hemanth Sarabu once the underlying data set issues are resolved.

- [ ] \[Sachin Pandey\] Resolve data issues: Resolve the underlying data set issues by Monday.

- [ ] \[Pratyaksh Singh\] Refine background model: Refine the dataset for the background generation model and proceed with fine-tuning.

- [ ] \[Pratyaksh Singh\] Setup latent diffusion: Set up a latent diffusion model for training.

- [ ] \[Pratyaksh Singh\] Compute latents: Compute latents on generated images to measure distribution distances and prune similar data.

- [ ] \[Pratyaksh Singh\] Investigate diversity techniques: Investigate FID and related techniques for ensuring generation of diverse examples.

- [ ] \[Geoff Horowitz\] Schedule Ulyses meeting: Schedule a meeting with Hemanth Sarabu to discuss the Ulyses project before next Monday.

- [ ] \[Pratyaksh Singh\] Build EMD app: Build an EMD decomposition application where users can select source images and modify parameters. Research the underlying code to determine how to increase the number of generated IMFs.

### **Details**

* **File Sharing and Documentation**: Sachin and Geoff discuss the sharing of model configuration and hash files. Sachin confirms that the agent successfully located the requested files, and they agree to document them for future review ([00:00:34](#00:00:34)).

* **Object Grouping and Unique Objects**: Geoff and Ratul review object groups and unique objects. They clarify that the file is split into XTF and DRN groups, where each group represents a unique object, accounting for duplicates from multiple sonar passes ([00:01:56](#00:01:56)).

* **Object Mapping Utility**: Ratul asks if a map of the identified objects is needed. After discussion, they conclude that a map is not helpful because the current table serves solely for identification purposes ([00:03:01](#00:03:01)).

* **Object Orientation and Segregation**: Ratul notes a need to cross-check object orientations, as some appear vertical while most are horizontal. The group agrees that while segregation is technically complete, a sanity check is required to verify the results before considering the task finalized ([00:04:57](#00:04:57)).

* **V4 Model Metric Bug Fixes**: Sachin provides updates on bugs affecting V4 metrics, specifically noting issues with how annotations were handled and how overlaps less than 0.1 were processed. They agree that these calculations must be corrected to ensure consistent results ([00:07:23](#00:07:23)).

* **K-Fold Model Training Status**: Sachin reports that the K-fold model training was stopped mid-process as it was not reaching a 50% intersection over union. Sachin aims to resolve underlying dataset issues, including incorrect markings in the base ground truth, and will provide an update by the meeting on Monday ([00:10:19](#00:10:19)) ([00:15:05](#00:15:05)).

* **V4 Model Performance Baseline**: The team confirms that the July 27 V4 model is currently their best-performing model. While work on K-fold validation and class merging continues, the V4 model remains updated in the Bedrock application, and no further immediate changes are required until the identified bugs are resolved ([00:12:38](#00:12:38)).

* **Object Simulation Strategy**: Ratul shifts the strategy for object simulation from manipulating raw values in XTF files to utilizing pixel crops. The team agrees this approach is sufficient, as high physics accuracy for shadows is not required for the current project goals ([00:17:05](#00:17:05)).

* **Novel Object Generation via LoRA**: Ratul explains the pivot to training a LoRA model on a dataset of 144 object examples to generate novel object data. They discuss the challenges of the output appearing overly refined compared to the project's specific dataset ([00:21:20](#00:21:20)).

* **LoRA Model Performance and Biases**: The team discusses potential biases in the generated images, noting that the model seems optimized for natural-looking images. They explore strategies such as adding noise to latents and continuing to refine the training process to improve results ([00:26:18](#00:26:18)).

* **Background Generation Issues**: Pratyaksh reports on training a diffusion model for background generation, noting artifacts like black regions in the output. The team concludes these issues stem from the dataset, and Pratyaksh plans to fine-tune the model with corrected data ([00:32:28](#00:32:28)).

* **Diffusion Model Architecture and Efficiency**: Hemanth recommends evaluating the generated images using latent space statistics, such as FID-like scores, and suggests testing a latent diffusion model rather than training from scratch on a 128 by 128 pixel space. They also discuss reducing diffusion steps to optimize training efficiency ([00:36:39](#00:36:39)).

* **Dataset Pruning and Quality Control**: Hemanth proposes using latent representations to measure distances between images, enabling semi-automated dataset pruning and ensuring generated examples effectively cover the distribution space ([00:45:27](#00:45:27)).

* **EMD Decomposition Development**: Pratyaksh presents on the Empirical Mode Decomposition (EMD) approach, which is currently generating only two components. Hemanth requests the development of an application to visualize these decompositions and interact with parameters, while the team plans to move the discussion regarding the "Ulyses" project to a separate meeting ([00:47:25](#00:47:25)).

*You should review Gemini's notes to make sure they're accurate. [Get tips and learn how Gemini takes notes](https://support.google.com/meet/answer/14754931)*

*How is the quality of **these specific notes?** [Take a short survey](https://google.qualtrics.com/jfe/form/SV_5bXzKQfylMIhSXc?confid=qQJrqeZ6xRGt0zfKG1DODxIUOBEBMgUIigIgABgBCA&detailLevel=standard&hasImages=False&entryPoint=footerMain&isGoogler=False) to let us know your feedback, including how helpful the notes were for your needs.*

# **📖 Transcript**

Jul 31, 2026

## **Iris Sync \- Transcript**

### **00:00:34** {#00:00:34}

**Sachin Pandey:** Hi Jeff.

**Geoff Horowitz:** He's our

**Sachin Pandey:** Hi.

**Geoff Horowitz:** channel.

**Sachin Pandey:** Uh the agent was able to find the like things that you asked for. It was the IANA.

**Geoff Horowitz:** What?

**Sachin Pandey:** You want me to you are you want me to zip everything like make a doc and share it with

**Geoff Horowitz:** Uhhuh.

**Sachin Pandey:** you?

**Geoff Horowitz:** Uh, the

**Sachin Pandey:** model configuration model hash.

**Geoff Horowitz:** f\*\*\*

**Sachin Pandey:** Uh

**Geoff Horowitz:** the hell?

**Sachin Pandey:** f\*\*\*.

**Geoff Horowitz:** Um, the agent was able to find all of that stuff. Is that what you said?

**Sachin Pandey:** Yes,

**Geoff Horowitz:** Yeah. Let's

**Sachin Pandey:** like I told him where to look generally like I first tell tell like inform him about the

**Geoff Horowitz:** Okay.

**Sachin Pandey:** main zip lo in the SHTP folder and then he once he get all the files name I searched like I searched like all the folders where I generally save the files in flexion links and all and provided all the folders to it. So it has created all of

**Geoff Horowitz:** Got it.

### **00:01:56** {#00:01:56}

**Geoff Horowitz:** Yeah. I mean um we let's talk about this a little bit later just for um you know for appropriately grouping meeting notes but uh but yes just

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** document it somewhere and then we'll we'll get back to it a little bit later. Okay.

**Sachin Pandey:** Okay.

**Geoff Horowitz:** Right.

**Ratul Shashank:** Hey

**Geoff Horowitz:** Rul. Hey. Um, okay. So, I'm looking at this. Which of these are the same objects?

**Ratul Shashank:** Uh, every group is the unique object.

**Geoff Horowitz:** So, group A,

**Ratul Shashank:** So yeah.

**Geoff Horowitz:** these are all the same object.

**Ratul Shashank:** Yeah.

**Geoff Horowitz:** Okay.

**Ratul Shashank:** Just duplicates.

**Geoff Horowitz:** And group B, these are all the same object. Okay.

**Ratul Shashank:** Yeah.

**Geoff Horowitz:** But we have but we have 11 unique objects. So, these are two unique objects.

**Ratul Shashank:** Uh, it is it has it not updated yet?

**Geoff Horowitz:** Uh oh.

**Ratul Shashank:** Uh,

**Geoff Horowitz:** Oh, here it is. Here it is. Here it is. Sorry. I guess I guess I didn't I just didn't scroll down.

### **00:03:01** {#00:03:01}

**Geoff Horowitz:** My bad.

**Ratul Shashank:** Yeah, I think I thought it the dog did not update when I changed it.

**Geoff Horowitz:** Group B. I I I see group B.

**Ratul Shashank:** So,

**Geoff Horowitz:** Hold on. Because this is a different file. DRN. I see. I see. Sorry for my confusion, Ritual. This clears it up. Let's just write that at the top. So this file is split intox and DRN groups. Uh each group is a unique object. um duplicates each object from um multiple scan sonar passes. That's sufficient.

**Ratul Shashank:** Uh Jeff, would you uh do you need me to add uh map of these objects as well? like a rough

**Geoff Horowitz:** Um,

**Ratul Shashank:** map.

**Geoff Horowitz:** what am I thinking about? Uh, I on one hand it wouldn't hurt, but I'm trying to think if it's actually useful, if it's

**Ratul Shashank:** Yeah. I mean,

**Geoff Horowitz:** helpful.

**Ratul Shashank:** if uh I just asked because I don't think it would be useful because we are making this table for identification purposes,

### **00:04:57** {#00:04:57}

**Geoff Horowitz:** Yeah, like I can't think of why we would use that,

**Ratul Shashank:** right?

**Geoff Horowitz:** but unique one UXO. What is this?

**Ratul Shashank:** Uh so this one was only uh there was no duplicate for that.

**Hemanth Sarabu:** Let's

**Geoff Horowitz:** No duplicates. Okay. Uh so this is what do I say?

**Hemanth Sarabu:** go.

**Geoff Horowitz:** surprised you have so many of the same. It's just interesting.

**Hemanth Sarabu:** Let's

**Geoff Horowitz:** Okay.

**Ratul Shashank:** Uh I need to cross check this as well like uh like if you can some of the objects their orientation does not

**Hemanth Sarabu:** go.

**Ratul Shashank:** make very like most of the object would be horizontal then some of the bunchs would be vertical. So I need to prop check that uh these are on like

**Geoff Horowitz:** Yes.

**Ratul Shashank:** the which type of XTF these objects are from if they are from the calibration path that Pedro is doing then it's fine otherwise there must be

**Geoff Horowitz:** They they should not be from the calibration path.

**Ratul Shashank:** a problem. Yeah, that is something that I need to

### **00:06:27**

**Geoff Horowitz:** The whole point the whole point of the calibration is that there's no objects

**Ratul Shashank:** check. Yeah, that is why it's uh it was confusing to me and I was discussing this with

**Geoff Horowitz:** there.

**Ratul Shashank:** Sachin and uh I need to cross check this. I have not done yet but I will do

**Geoff Horowitz:** Okay.

**Ratul Shashank:** that.

**Geoff Horowitz:** Fine. So then this is still an open item, right?

**Ratul Shashank:** Uh as far as segregation is concerned, segregation is done. We are just uh doing a sanity check if this is actually true or not. Segregation is done.

**Geoff Horowitz:** I mean, I hear you, but but if we're not confident that it's right,

**Ratul Shashank:** They are Yeah.

**Geoff Horowitz:** then it's not done.

**Hemanth Sarabu:** It's

**Geoff Horowitz:** Does that make sense?

**Ratul Shashank:** Yeah. It

**Geoff Horowitz:** So,

**Hemanth Sarabu:** not

**Geoff Horowitz:** so,

**Ratul Shashank:** does.

**Geoff Horowitz:** you know, remember Rachel, when when we say something's done, I'm not tracking it anymore, right?

**Ratul Shashank:** I

**Geoff Horowitz:** So, so it's not done until it's done.

### **00:07:23** {#00:07:23}

**Ratul Shashank:** understand.

**Geoff Horowitz:** Um, okay. Uh, Somebody sent me something funny. Um, okay. Uh, train of thought. Sachin, you are you're you're still updating your notes. Is that right?

**Sachin Pandey:** the running notes. Yeah.

**Geoff Horowitz:** Yeah.

**Sachin Pandey:** Like so reason I removed it because first when I checked the like the actual data it was like annotations were not looking correct.

**Hemanth Sarabu:** What's

**Sachin Pandey:** Maybe there were some issues because the original like the annotations which were added artificially added have annotations but the the base image already have a UXO. it was not marked. So maybe that was the reason why we were like not getting the same like precision and recall percentage uh we were getting earlier. And also one mistake was if like overlap was less than

**Geoff Horowitz:** Okay,

**Sachin Pandey:** 0.1 it was ignoring it. So once it ignore it it will like increase the counter for false negative as well as the false positive.

**Geoff Horowitz:** Right.

**Sachin Pandey:** So that was also affecting the overall

### **00:09:18**

**Geoff Horowitz:** So, so Sachin, I I just want to recap kind of what what you're working on.

**Sachin Pandey:** value.

**Geoff Horowitz:** There are there are some bugs in how we're calculating these metrics for V4. You're working through these bugs, making sure that everything is consistent. That's number one. Correct.

**Sachin Pandey:** Uh this was for the kfold matrix.

**Geoff Horowitz:** Correct. on the V4 on the V4

**Sachin Pandey:** The base the H has few issues.

**Geoff Horowitz:** model.

**Sachin Pandey:** Yeah. On the both on the and the cable.

**Geoff Horowitz:** Understood. Understood. Yeah, because you you had also said something and it's it's gone now in the notes, but from our last meeting, you also said something else about the V4 model that was inconsistent.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** I I don't remember exactly what it was, but I remember we were Yeah. Yeah. Here we go. Right. About the merging. That was That was right.

**Hemanth Sarabu:** Can you share your

**Sachin Pandey:** Yeah.

**Hemanth Sarabu:** screen?

**Geoff Horowitz:** Yeah, Ham, I I don't want to waste too long discussing this because I I I mean,

### **00:10:19** {#00:10:19}

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** unless unless you want to, which I'm okay with it,

**Sachin Pandey:** It's my

**Geoff Horowitz:** but uh I'd like Sachin to like organize this information,

**Sachin Pandey:** dad.

**Geoff Horowitz:** make sure it's consistent, do all the work that he needs to do, and then we can spend time discussing it. Um, I would rather spend the time going over the synthetic data stuff with project

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** tool.

**Hemanth Sarabu:** So I I guess what is the status on on V4 in the first

**Sachin Pandey:** Yeah, the the Kfold was trained

**Hemanth Sarabu:** minute?

**Sachin Pandey:** on like the Gfold matrix. So like I I did another keyfold model with like with updated data set where I removed the small uh mainly remove the AI big ones which were like which were not like which don't have any strong features and also inverted the like alpha and beta like which loss or like false positive should be affected more or false negative should be affected more. So this training was not like performing very well compared to the like old F uh twofold model.

### **00:11:37**

**Sachin Pandey:** So I I stopped it. I stopped it midway like after two model I stopped it. It was not reaching not even reaching the 50% IOU.

**Hemanth Sarabu:** Okay. So, what's the headline? We've saturated model performance.

**Geoff Horowitz:** So,

**Sachin Pandey:** Yeah. Uh so in short like the matrix you are seeing the actual matrix will be much later because uh first there was some issue in the actual data so not all the UXO or UI were marked so the base ground truth is also incorrect so once that fixed we I will like update the main

**Geoff Horowitz:** again.

**Sachin Pandey:** data that

**Geoff Horowitz:** Suction,

**Hemanth Sarabu:** Oh,

**Geoff Horowitz:** that's for the K-fold model, right?

**Sachin Pandey:** that's for the like the whole section this is correct this is correct you can ignore this the one on the kfold was uh only have mistakes This is also updated.

**Geoff Horowitz:** So,

**Hemanth Sarabu:** heat.

**Sachin Pandey:** The V2 is also updated with the new thing.

**Geoff Horowitz:** okay.

**Sachin Pandey:** If you open it, you will see the note like why it was why it was updated and the updated matrix also.

### **00:12:38** {#00:12:38}

**Geoff Horowitz:** Yeah,

**Sachin Pandey:** So this is done.

**Geoff Horowitz:** that's that's that unders.

**Sachin Pandey:** I was talking about the K4

**Geoff Horowitz:** Okay. So, this is this is why I want to summarize it.

**Sachin Pandey:** one.

**Geoff Horowitz:** Th this right here, this uh July 27 V4 model. Okay. where we're we're doing we're doing pretty well on all these classes, right?

**Sachin Pandey:** Yes.

**Geoff Horowitz:** This is right now our best model without some additional augmentation, synthetic data, whatever.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** We think this is the best model that we can get. Right. Okay.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** What you're working on now is implementing the K-fold validation. There are some issues there. There are some bugs. you're working through them. We also discussed merging UXO and AOI small black and there's also some bug there.

**Sachin Pandey:** mainly

**Geoff Horowitz:** So we have in the ground. So we have a baseline model that we're confident about.

**Sachin Pandey:** like

**Geoff Horowitz:** I'm calling not a baseline, not not the right word.

### **00:13:43**

**Geoff Horowitz:** We have kind of our our best possible model right now.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** That's this this this kind of base B4 model B4 model and then we're messing around with it using some K-fold validation uh merging these classes and that's that's what you're working on now. Did I summarize all that correctly? Okay.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Come on. Does that clarify things on your end or are you still do you still have a source of confusion?

**Hemanth Sarabu:** Um I think there's still some confusion but I I'll catch up with you later on to clear it. Um Sachin when will we have like a full set of comparable results as in like when will this be You think

**Sachin Pandey:** So like full set of comparison like in like can you elaborate a little

**Hemanth Sarabu:** I just just resolving everything the tables whatever Jeff

**Sachin Pandey:** Yeah, I like Like the main model which uh which is also updated in the like bedrock app is the V4 one. We are just testing more things to figure out if we can get more better performance or not.

### **00:15:05** {#00:15:05}

**Hemanth Sarabu:** Mhm.

**Sachin Pandey:** Till now like V4 is the best one we have and we have also already updated it in the bedrock apps and other

**Hemanth Sarabu:** So only Kfold metrics are uh not to be

**Sachin Pandey:** things.

**Hemanth Sarabu:** trusted.

**Sachin Pandey:** Yeah. Not for this one. Yeah. It's not

**Hemanth Sarabu:** Okay. So, when will we fix

**Sachin Pandey:** retested.

**Hemanth Sarabu:** that?

**Sachin Pandey:** So once I get the like correct like artificial data to test out the model uh these metrics will get updated.

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** Sergeant, do you do you think that by mon by our meeting time on Monday you'll have sorted through the underlying data set issues?

**Sachin Pandey:** Yeah. Yeah.

**Geoff Horowitz:** Okay. If you what uh what am I trying to say?

**Sachin Pandey:** Nice.

**Geoff Horowitz:** One second.

**Sachin Pandey:** Okay.

**Geoff Horowitz:** If if you if you have results before Monday, Sachin, uh update them here and send us a Slack message. Ping uh you know, put it in the Bedrock channel and ping both me and him, please.

### **00:17:05** {#00:17:05}

**Sachin Pandey:** Okay.

**Geoff Horowitz:** Thanks.

**Hemanth Sarabu:** So if we're done with such things actually can we start with RTL today because every time RTL goes last and we don't have enough time to talk about his

**Geoff Horowitz:** Absolutely.

**Hemanth Sarabu:** stuff. So can we quickly go through RTL stuff first?

**Ratul Shashank:** Yeah, let me uh let me just pick up from where we were discussing last meeting.

**Hemanth Sarabu:** Yeah.

**Ratul Shashank:** Uh

**Hemanth Sarabu:** Yeah. Just uh situate us uh a twoline recap and then and

**Ratul Shashank:** unfortunately,

**Hemanth Sarabu:** then yeah share share your stuff.

**Ratul Shashank:** yeah. Uh so just a recap. Initially what I was doing was uh So what I wanted to do is simulate sorry what I wanted to do was simulate if an object if I crop the raw values of object from XDF and place it somewhere in the background and I wanted to simulate If

**Hemanth Sarabu:** Yeah,

**Ratul Shashank:** that object was naturally present in that background,

**Hemanth Sarabu:** right.

**Ratul Shashank:** what it would look like and what I was using was I subtracted the median of background.

### **00:18:41**

**Ratul Shashank:** So median of the amplitude of the background with the amplitude of the uh object cropped object and I I was placing that object over over that process. So that was the entire process right and and by doing

**Hemanth Sarabu:** Right. Right.

**Ratul Shashank:** that since I am copying the the raw values I can also change the height the the length I I can mix two objects.

**Hemanth Sarabu:** Right.

**Ratul Shashank:** So this was my entire reasoning. Uh and I discussed this with Pratex as well and he mentioned that this would be this and performing a pixel

**Hemanth Sarabu:** Yeah.

**Ratul Shashank:** crop would be more or less the same thing.

**Hemanth Sarabu:** Yeah.

**Ratul Shashank:** Like even if we crop a pix crop the pixel of the

**Hemanth Sarabu:** Yeah.

**Ratul Shashank:** object, we can also perform operations for changing heights and uh any any operation that we are doing there doing here we can do on pixel crop as well and pixel crop would be better because there is much data available uh rather than this stuff. So,

**Hemanth Sarabu:** Right.

**Ratul Shashank:** so like that was uh considering that

### **00:20:04**

**Hemanth Sarabu:** And it is a fine project. There's no there's no trigonometric functions at

**Ratul Shashank:** uh

**Hemanth Sarabu:** all.

**Pratyaksh Singh:** Yeah, it's it's totally a fine.

**Hemanth Sarabu:** Wow. Okay. Okay.

**Ratul Shashank:** yeah, I mean this uh since we don't need very physics accurate uh pictures like even the shadows are

**Hemanth Sarabu:** Yeah.

**Ratul Shashank:** uh uh a little off we it it won't matter to us. So uh performing this XTF uh the raw changing of values would not be

**Hemanth Sarabu:** Yeah.

**Ratul Shashank:** of like it would be pretty much same that compared to the pixel problem.

**Hemanth Sarabu:** Okay.

**Ratul Shashank:** So all of this like changing the height uh

**Hemanth Sarabu:** So what RT let's uh what's next?

**Ratul Shashank:** comparing uh

**Hemanth Sarabu:** So what what uh do we have any updates?

**Ratul Shashank:** so what I was doing uh like I I was trying to gather as much examples of objects as possible. So if what I wanted was I want if I have enough examples of the objects I can train a model on the objects. Why I wanted to do that?

### **00:21:20** {#00:21:20}

**Ratul Shashank:** I will show you

**Hemanth Sarabu:** So, wait, wait, wait. Riddle,

**Ratul Shashank:** just

**Hemanth Sarabu:** you're going into the weeds. What is the You were You were reshaping the objects.

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** Now, what is the problem? like um you you've ditched that idea. What is uh what are

**Ratul Shashank:** No. Uh that is something that that is exactly what I'm working on. I'm uh like uh I I am using the uh

**Hemanth Sarabu:** you

**Ratul Shashank:** gem nano banana models and I will gather as much as these grids. I will crop them uh like as much examples as possible. I will gather them and I will train a Lora model on that. Uh because uh earlier when I tried to train the LoRa model on the object that we have the output was very refined. uh uh I will I will show you an example since

**Hemanth Sarabu:** I don't follow I don't understand the connection between

**Ratul Shashank:** the

**Hemanth Sarabu:** your object reshaping object extraction work and what you're showing here.

### **00:22:32**

**Hemanth Sarabu:** How do they relate to one another?

**Ratul Shashank:** uh so these are two different thing because mentioned that I should focus on this uh object's novelty because the uh raw XTF stuff that I was doing before um that we can perform that even later that is not that is not a bottleneck for us. So Pratak suggested that uh it is best to find as much data of the objects as possible be it through close source uh open uh we can't use open-source models because as you can see if uh if we train objects on the open source models they are very refined. So that is why uh I am taking a little tangent and going this

**Hemanth Sarabu:** Okay. So, it's I want I want uh this is fine. This is fine to do.

**Ratul Shashank:** path.

**Hemanth Sarabu:** I understand. Just want to make sure. So, this is not a tangent. This is this is a different thing and you you start working on that for the time being, which is okay. I want to make sure that I understand the the effort, the work you're doing.

### **00:23:48**

**Ratul Shashank:** Yeah. Uh yeah. uh this this is not a tangent uh you are right this is a completely different

**Hemanth Sarabu:** Yeah.

**Ratul Shashank:** part so that is in summary I uh what I I'm trying I am trying to gather as much novel examples of the objects and I will run a lora model on those objects so that we can gather much more better results for the model generate the model because these would not work. These are too much defined. So that is

**Hemanth Sarabu:** So these are what what Okay.

**Ratul Shashank:** this.

**Hemanth Sarabu:** So the the images you're showing here were generated

**Pratyaksh Singh:** Hey.

**Hemanth Sarabu:** by uh by big lab VLMs. Big Lab

**Ratul Shashank:** Uh so yeah the this image was uh like I

**Hemanth Sarabu:** models.

**Ratul Shashank:** trained a Laura model on flux uh uh and I and I I trained them on the 144 examples that we have uh and and when I tried to generate the objects using prompt like uh uh instead of image to image I tried text to image and I tried to generate them using a using prompts and the output this is the output and these are very refined.

### **00:25:17**

**Hemanth Sarabu:** Oh wait. So but the the base data the training data set is not our data set. It is the training data set is from Google.

**Ratul Shashank:** uh for this example it was for our data set.

**Hemanth Sarabu:** Oh this look very different right?

**Ratul Shashank:** Uh I have not trained that.

**Hemanth Sarabu:** This looks very different than our

**Ratul Shashank:** Yeah, that is the problem.

**Hemanth Sarabu:** model.

**Ratul Shashank:** That is the problem because uh that is why I need more examples like

**Hemanth Sarabu:** Okay.

**Ratul Shashank:** uh uh

**Hemanth Sarabu:** Have you tried training for longer and things like that?

**Ratul Shashank:** uh for

**Hemanth Sarabu:** To me it feels like Yeah.

**Ratul Shashank:** longer.

**Hemanth Sarabu:** making your lura bigger,

**Geoff Horowitz:** Wait,

**Hemanth Sarabu:** things like that because to me it feels like it is.

**Geoff Horowitz:** Rel is this the output of the trained Laura model or is this the output from the nano banana

**Ratul Shashank:** No,

**Geoff Horowitz:** model?

**Ratul Shashank:** this is the output for Laura models trained on the 144

**Geoff Horowitz:** Uh,

**Ratul Shashank:** objects.

**Geoff Horowitz:** okay. Thanks.

### **00:26:18** {#00:26:18}

**Hemanth Sarabu:** that are ours or like are yeah so I'm not I'm not an

**Ratul Shashank:** Yeah. Yeah. That

**Hemanth Sarabu:** expert in these models uh hopefully we all become experts in this in the next

**Ratul Shashank:** was

**Hemanth Sarabu:** month or two but um it seems to me that it's pretty biased towards natural looking images, which is probably what Flux was trained

**Ratul Shashank:** Yeah.

**Hemanth Sarabu:** on.

**Ratul Shashank:** Uh I was I discussed this with Taty like what why what could be the problem with this? Uh he mentioned this could be the reason because we have a very small data set like only 144 images. Uh so

**Hemanth Sarabu:** But are we doing any augmentations to that data or are we just

**Ratul Shashank:** no in this example there were no

**Hemanth Sarabu:** playing?

**Ratul Shashank:** augmentations.

**Hemanth Sarabu:** Okay. Okay. Let's Okay, let's move on.

**Ratul Shashank:** Yeah. I mean uh uh like I tried to like add noise to the to the generated object but even that did did not work like I I tried to crop the object.

### **00:27:35**

**Ratul Shashank:** I I will I will look into if there is a uh like if training a Lora model differently could be the key or at the same time also generating novel examples. So he would

**Hemanth Sarabu:** I mean something about this doesn't add up like at the very least you should be able to generate

**Ratul Shashank:** have

**Hemanth Sarabu:** uh not novel but uh indistribution looking images even with them

**Ratul Shashank:** uh like that is

**Hemanth Sarabu:** tumbles.

**Ratul Shashank:** uh like we are able to generate if if we are generating a background for example then it is very like uh I will give you the example. This is text to image using Lora model that I was that I trained on DRN DRN data set and these images are very close to the DRN's background but when I trained for the objects I I don't know if the size of the object is the problem or the size of the data set. But the background when I was Gemini generated for DRN data set it is giving pretty good results and these are all just text to image.

### **00:29:10**

**Ratul Shashank:** uh I will try to add like uh uh latent like

**Hemanth Sarabu:** Okay.

**Ratul Shashank:** uh a noisy latent and then add generation on top of that but I don't have an answer if that would work or not.

**Hemanth Sarabu:** Okay.

**Ratul Shashank:** Yeah, that is the update on my end.

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** Rul, I'm sorry I missed. Did you have any success generating the object with any of the model the novel object generation that you talked about?

**Ratul Shashank:** uh like not very like I am trying first I I I am trying to add the crops like I have cropped the uh objects and then I'll I am adding that uh and generating a grid. So my reasoning is even though some of the images are very refined like this uh when I increase the grid scale and I asked it to decrease the rest uh some of some of the images do look like it could be used in our data set but

**Pratyaksh Singh:** Mhm.

**Ratul Shashank:** some like this one and this one these are not very useful but my reasoning is if I have enough data uh even if uh some of them are not directly useful for us but uh if if we have enough data uh we could be the the Laura model trained on that could be helpful in generating decent text to image models.

### **00:31:01**

**Ratul Shashank:** So that is my reasoning. So I I tried to combine two images, two objects. Some of them are useful, some of uh uh this would need a little bit of more prompt engine. So yeah, that is uh still an open item.

**Pratyaksh Singh:** So do you have any examples of like objects which look like in our data set? Do you have uh are you maintaining any data set for it?

**Ratul Shashank:** uh um I'm not like uh I'm not getting any decent examples as of yet. So once I find a workflow that is that is working I will keep uh keep a record for all the generation that I'm making and the prompts that I'm using. As of yet, I don't have I'm trying uh different workloads which would work and which would

**Hemanth Sarabu:** Okay,

**Ratul Shashank:** not

**Hemanth Sarabu:** I got to run soon. Rel, thanks. Thanks for your update. Can do you want to do you want to share your

**Pratyaksh Singh:** Yeah. Uh I put the diffusion model in training for the background generation with uh it was it was without any object and only for the training set.

### **00:32:28** {#00:32:28}

**Pratyaksh Singh:** There were some issues. uh the model did perform good for some classes and it didn't perform good for some other classes. We traced back the issue with the data set. The issue was that give me a minute. I'll share my screen and I show it to you. How on my screen is visible. the screen visible.

**Hemanth Sarabu:** Yeah. You okay? Yeah. What are we looking at?

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** So, so just to recap,

**Pratyaksh Singh:** So

**Hemanth Sarabu:** you are training a diffusion model on no objects.

**Pratyaksh Singh:** on no objects. Yeah. And only on background for only only for background generation. So that we can use the whole object as validation set.

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** So because of these kind of lines you see these lines when we slid this

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** image there were a lot of black region in the image and this is why like if I'll show you some images that it is generating specifically for VW it is a little bit black which is which is you know worse than the previous data previous images that it was generating.

### **00:34:06**

**Hemanth Sarabu:** What what are we looking at here?

**Pratyaksh Singh:** So this is the images the image generated by by the currently trained diffusion model which had

**Hemanth Sarabu:** So left initial state right is ground truth.

**Pratyaksh Singh:** uh right most of the generated

**Hemanth Sarabu:** Oh, okay.

**Pratyaksh Singh:** image.

**Hemanth Sarabu:** Doesn't look like there's a Are there three images here or there two images

**Pratyaksh Singh:** So the bit the one in between is just uh is just in space for the mask since we

**Hemanth Sarabu:** here?

**Pratyaksh Singh:** aren't giving any object so it is always

**Hemanth Sarabu:** Wow. Okay.

**Pratyaksh Singh:** flat.

**Hemanth Sarabu:** Um, sorry. I don't see what the issue with the third column is.

**Pratyaksh Singh:** It doesn't look like VW data set. That is the problem. That's so and it is because of like

**Hemanth Sarabu:** Oh,

**Pratyaksh Singh:** you know we gave it a lot of these kind of examples the black examples and that is why I think I think it messed up uh we're fixing the data set I'll feed it back I think hopefully on

**Hemanth Sarabu:** okay.

### **00:35:14**

**Hemanth Sarabu:** It shouldn't it shouldn't, right? Like if you go back um go back to your

**Pratyaksh Singh:** weekendh

**Hemanth Sarabu:** um do you

**Pratyaksh Singh:** okay

**Hemanth Sarabu:** think what makes you think the black areas

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** is is the the cause?

**Pratyaksh Singh:** Why do I think the black area is the cause? Because everything else is same as the first experiment. This is like the very naive answer like everything is same as the first experiment. Only the data set has changed, right?

**Hemanth Sarabu:** I see.

**Pratyaksh Singh:** only only the data set has seen and we have made things simpler for the model because now it doesn't have to condition on the mass right

**Hemanth Sarabu:** Right.

**Pratyaksh Singh:** and for some uh let me show you something.

**Hemanth Sarabu:** Right.

**Pratyaksh Singh:** So for example, let's say you see these examples of BW, the ones that are below, these examples are darker, right? Usually VW data set is uh

**Hemanth Sarabu:** You're you computing any like uh FID score type stuff metrics between generated

**Pratyaksh Singh:** VW

**Hemanth Sarabu:** and u reference

### **00:36:39** {#00:36:39}

**Pratyaksh Singh:** Am I computing?

**Hemanth Sarabu:** distribution.

**Pratyaksh Singh:** No, I'm

**Hemanth Sarabu:** I think I think you should I think you should uh basically it's like a a statistic to measure the

**Pratyaksh Singh:** not.

**Hemanth Sarabu:** distri it's not perfect and there are others also which we should use and we should like plot all of them

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** but what it does is it'll attempt to see if what you're generating with your diffusion model follows the distribution of your reference data set or your training data

**Pratyaksh Singh:** about

**Hemanth Sarabu:** set and it does use I believe like uh

**Pratyaksh Singh:** it.

**Hemanth Sarabu:** Luigi or Alexet features as uh yeah as the features and then it computes distributions.

**Pratyaksh Singh:** Got it.

**Hemanth Sarabu:** So then you'll know at least at you might also be able to another thing you can do is you can compute the latence of all your whole training data set compute latence of your generated models and then you can actually ask which one am I close to am I actually far am I close this actually works I've used latence to determine um in in data sets what images are what are not close and it works really

### **00:37:55**

**Pratyaksh Singh:** So so actually

**Hemanth Sarabu:** Oh,

**Pratyaksh Singh:** like this isn't a latent diffusion model.

**Hemanth Sarabu:** this is not a latent diffusion

**Pratyaksh Singh:** No,

**Hemanth Sarabu:** model.

**Pratyaksh Singh:** this is just image image to image diffusion mode. The reason for it is that you know the image size is only 128 \+ 128\. So it's already pretty small.

**Hemanth Sarabu:** Uh,

**Pratyaksh Singh:** So I didn't see the need of having a VA on top of it.

**Hemanth Sarabu:** I think you should try

**Pratyaksh Singh:** And the reason it is you think even with 128 \+ 128 VA will help.

**Hemanth Sarabu:** Sorry,

**Pratyaksh Singh:** Even with like 128 \+ 128 image VA will help. A latent diffusion model will

**Hemanth Sarabu:** I uh I I don't actually know but I think we should try uh and and learn

**Pratyaksh Singh:** help.

**Hemanth Sarabu:** learn based on data. Uh what is the space of latent right?

**Pratyaksh Singh:** Got it.

**Hemanth Sarabu:** What is uh it depends on what what autoenccoder you Right. Um,

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** so does that mean this is training from scratch?

### **00:39:06**

**Pratyaksh Singh:** So it is training from scratch. Yes.

**Hemanth Sarabu:** I

**Pratyaksh Singh:** Do you want to what do you want to do? Flora finder. The reason I'm training from scratch is

**Hemanth Sarabu:** don't have to do Laura finetuning. We can do normal fine tuning.

**Pratyaksh Singh:** same.

**Hemanth Sarabu:** But so here here's the thing. You can even if this is not a latent firstly I I would I would train I would also train a a latent diffusion model

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** because because I'm new to generative modeling I I don't have a strong intuition for hey this should work and this should not work right it's a maybe

**Pratyaksh Singh:** Got

**Hemanth Sarabu:** they're weak intuitions and they need to be validated. So that is my that is my my uh perspective with the generative

**Pratyaksh Singh:** it.

**Hemanth Sarabu:** modeling. Um and experiments should be relatively should be basically free for us. We have enough compute.

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** Um

**Pratyaksh Singh:** about that like it takes this training the diffusion model it takes a lot of time.

### **00:40:21**

**Hemanth Sarabu:** how long are we talking?

**Pratyaksh Singh:** So uh 1 and a half 2 days on five

**Hemanth Sarabu:** Damn.

**Pratyaksh Singh:** GPUs five five if I leave one

**Hemanth Sarabu:** On six GPUs.

**Pratyaksh Singh:** one weekend so on five GPUs it takes so per epoch time is small

**Hemanth Sarabu:** Okay. What?

**Pratyaksh Singh:** like 2 minutes per epoch but I usually have to do like thousand

**Hemanth Sarabu:** Yeah. Yeah.

**Pratyaksh Singh:** epochs

**Hemanth Sarabu:** How many How many diffusion steps?

**Pratyaksh Singh:** 25

**Hemanth Sarabu:** Whoa. That's really high. I think that's really high. You might be able to get away with fewer.

**Pratyaksh Singh:** Yeah, but that but like diffusion step will help during inference,

**Hemanth Sarabu:** Um

**Pratyaksh Singh:** right?

**Hemanth Sarabu:** uh what do you mean?

**Pratyaksh Singh:** I mean do do you think they will reduce the time for training also?

**Hemanth Sarabu:** Yeah. Uh Yeah, I think so. It's a good question. I I do think I do right like first of all your distribution will be smaller like uh if you're doing 25 steps it means you're learning to d noiseise in the time domain you're adding noise uh up to levels uh 1 to

### **00:41:40**

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** 25 something like that right so and then when

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** you're doing evals you're you're actually doing a 25 step um is 25 default Still.

**Pratyaksh Singh:** It's 25 default still like as as much as I have read like people will train with this many steps and then they will either distill it to smaller which they do for world models or they will use some other some other uh what

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** sampler during inference

**Hemanth Sarabu:** Yeah. So, I' I've seen between five and 15,

**Pratyaksh Singh:** to

**Hemanth Sarabu:** but for video models and but video models, it makes sense because they're way more expensive and you if you want it to run quickly,

**Pratyaksh Singh:** Uh-huh.

**Hemanth Sarabu:** you're you're really trying to reduce the number of time steps. I get that. So this is um okay so here's what I will say I suspect that the the fact that you're not using a latent diffusion model is also slowing you down uh because how big are latence if you're doing diffusion in latent it might be smaller than doing diffusion on a 128 cross 128 pixel space right what is the size

### **00:42:55**

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** of uh 1.1 any legups.

**Pratyaksh Singh:** 256, right? I think 64 cross 64 there,

**Hemanth Sarabu:** Um,

**Pratyaksh Singh:** I think.

**Hemanth Sarabu:** we need to take a look. Uses a compression ratio of 488\.

**Pratyaksh Singh:** Four

**Hemanth Sarabu:** 488\. And I think one of those is temporal. So we need to look at we need to look at like H.

**Pratyaksh Singh:** is four is temporal.

**Hemanth Sarabu:** This is video though,

**Pratyaksh Singh:** Yeah, four is temporal.

**Hemanth Sarabu:** right?

**Pratyaksh Singh:** And then 8 I think they usually do it with 5.2, right? 64 cross 64\.

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** At least four times smaller than what you're running,

**Pratyaksh Singh:** Yeah. So,

**Hemanth Sarabu:** right?

**Pratyaksh Singh:** see uh my idea was that we have a model that worked, right? The only problem with it was data leakage, right? We had a model that generated good examples which we saw in the uh in the app that I that I showed in previous meetings.

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** So I just want to feed it new correct data and then train it so that we get at least a baseline model.

### **00:44:29**

**Pratyaksh Singh:** So that's why like I continued my training with the with with everything like being the same.

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** But I think it's because of data set that it's messing up. I will try fixing the data set and I will see like if it if it

**Hemanth Sarabu:** H.

**Pratyaksh Singh:** improves. I think this time the iteration should be faster because I'm just going to fine-tune the model that we have right now. Right?

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** I can finetune it because there is no data leakage here. So, I'll fine-tune it on model. So I think it should be faster. We should have at least some some uh yeah some bas basic results. I think morning my time and after that I will set up a

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** diffusion model because by the time I think uh sorry a latent diffusion model because by the time we will review the data generated by that model will also be there

**Hemanth Sarabu:** Okay. Okay. Uh, sounds good.

**Pratyaksh Singh:** sometimes.

### **00:45:27** {#00:45:27}

**Hemanth Sarabu:** Hey, um, that's fine. But if you want to answer things like is this looking close to the distribution or not,

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** you can run those experiments by com doing FID type stuff, uh, fads type stuff, and there's other ideas.

**Pratyaksh Singh:** Okay.

**Hemanth Sarabu:** Even though you're not training a latent diffusion model, you can actually compute latent on these images and compare uh actually use that as a way to prune data sets that are too similar.

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** It it works. You have to you have to play with the thresholds. There are some tricks, but try it out once and you'll be surprised how uh how well it works as as yeah as simple as that

**Pratyaksh Singh:** Oh, I'll try it out. I'll try it out.

**Hemanth Sarabu:** is like you all you need to do is compute latence and then measure distances somehow and then you you get a pretty nice a pretty usable I it's not perfect but it's pretty

**Pratyaksh Singh:** Yeah,

**Hemanth Sarabu:** usable.

**Pratyaksh Singh:** that's that's really good. I think one of the thing I was thinking about was when I generate example because I thought that the model will train good.

### **00:46:33**

**Pratyaksh Singh:** So one of the thing that I was thinking about is when we generate examples from this model right we can generate unlimited example. So how would we ensure that we are generating different examples in that case I

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** think FID and other things can help I I will look through

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** those.

**Hemanth Sarabu:** You exactly. So you can actually use latent and some you can do some crazy s\*\*\*

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** like you can actually create a graph uh that says you like a max span graph, right? basically saying, "Hey, this is my full data set. I have a budget of a thousand. Pick latents that are that cover the most distance, right?

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** You can do stuff like that. Um,

**Pratyaksh Singh:** Oh,

**Hemanth Sarabu:** and you can do that almost semi-automatically,

**Pratyaksh Singh:** yeah.

**Hemanth Sarabu:** you know what I mean?" So, I think it's a powerful idea.

**Pratyaksh Singh:** Yeah. Yeah.

**Hemanth Sarabu:** Yeah. So, let's explore.

**Pratyaksh Singh:** Uh-huh.

### **00:47:25** {#00:47:25}

**Hemanth Sarabu:** It's not perfect, but it is it it is I think at least uh it semi-automates things if not automate.

**Pratyaksh Singh:** Yeah, that's really good. Yeah, thanks for sharing

**Hemanth Sarabu:** Yeah, of course

**Pratyaksh Singh:** it.

**Hemanth Sarabu:** not.

**Geoff Horowitz:** month. Um, two things. Number one, you you guys were talking about the EMD approach. I don't know if you want to talk about that,

**Pratyaksh Singh:** Oh yeah,

**Hemanth Sarabu:** Oh yeah.

**Geoff Horowitz:** but also also if you're time limited,

**Pratyaksh Singh:** I have some

**Geoff Horowitz:** Hammon, I I I want you for five or 10 minutes on Ulyses.

**Hemanth Sarabu:** uh on Ulyses. Today might be hard.

**Geoff Horowitz:** Yeah.

**Hemanth Sarabu:** It'll have to be tomorrow. Um

**Geoff Horowitz:** Okay.

**Hemanth Sarabu:** yeah.

**Geoff Horowitz:** Okay. I I don't want When did they They sent the email? Monday, I think.

**Hemanth Sarabu:** Yeah. Yeah.

**Geoff Horowitz:** I don't want to keep them waiting too long.

**Hemanth Sarabu:** That's great.

**Geoff Horowitz:** I would like to respond to them no later than Monday.

### **00:48:25**

**Hemanth Sarabu:** Yeah, do did you have something for

**Pratyaksh Singh:** Yeah, I'm just sharing it on the Slack

**Hemanth Sarabu:** EMD?

**Pratyaksh Singh:** channel. I I don't know how to use this information though.

**Geoff Horowitz:** Um,

**Hemanth Sarabu:** H

**Pratyaksh Singh:** And uh for all the images, it only generated two IMFs.

**Hemanth Sarabu:** interesting. Uh you can play with the parameters.

**Pratyaksh Singh:** Uh I

**Hemanth Sarabu:** Would you be any any way would you be able to make an app for your EMD decomposition

**Pratyaksh Singh:** mean

**Hemanth Sarabu:** thing where people can select the images, play with the parameters and it will show the reconstructions and rescues etc.

**Pratyaksh Singh:** Yeah. uh one thing I can make that app one thing I would ask you is because I don't know much about EMD so what I did was I used one implementation from

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** PIMD right

**Hemanth Sarabu:** Okay. Yeah.

**Pratyaksh Singh:** and it doesn't like it doesn't talk a lot about it because it is the experimental

**Hemanth Sarabu:** Uhhuh.

**Pratyaksh Singh:** feature I I

**Hemanth Sarabu:** I see.

**Pratyaksh Singh:** have set the max IMF to minus one which was supposed to generate the maximum number of IMF but

### **00:49:47**

**Hemanth Sarabu:** Oh, okay.

**Pratyaksh Singh:** uh but it's only generating two so I have no idea like there is only one parameter

**Hemanth Sarabu:** Damn.

**Pratyaksh Singh:** here I I'll show you the link to the document also

**Hemanth Sarabu:** Thank you. Um, okay. Can we let's spend five minutes on us.

**Geoff Horowitz:** Oops.

**Hemanth Sarabu:** project. If if you can do the app, that'll be great. I think uh yeah, I'll be

**Pratyaksh Singh:** Okay. Okay.

**Hemanth Sarabu:** grateful.

**Pratyaksh Singh:** I'll I'll I'll make the make the app. But again, I don't I don't know the parameters. I'll try to figure it out.

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** But all

**Hemanth Sarabu:** Yeah. Uh so my basically my idea is with this if it can extract somewhat meaningful

**Pratyaksh Singh:** right.

**Geoff Horowitz:** Uh,

**Hemanth Sarabu:** components like IMF1 is somewhat meaningful so is IMF2. IMF2 is a constant gradient which it it pulled out. IMF1 is more of a it's brighter on the outside and then darker on the middle and um and it's gotten that black patches uh at

### **00:50:52**

**Geoff Horowitz:** heat.

**Hemanth Sarabu:** the at the top and bottom edge. So you can start like adding if it created more IMFs that feel like useful and then the residue is basically noise. It decided that whatever is remaining is noise, right?

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** So now you have a somewhat noisefree two component representation of this image. And now if you keep doing a lot of images, it is possible uh oh s\*\*\*. Um yeah it's possible that we can recombine them from different from different images. We can recombine these uh components that that is the idea but you know it's still idea stage.

**Pratyaksh Singh:** Got it. I will I'll try to I'll try to build that app. I'll see if there is a way to I'll go through its code. I'll see if there is a way to increase the number of IMFs that it generates.

**Hemanth Sarabu:** Okay, thank you. I mean, yeah, whatever you can and if it's possible, just like make it easy for someone to select the image, the source image for it and then uh that'll be great.

**Geoff Horowitz:** Hold

**Hemanth Sarabu:** That'll be enough for me.

**Pratyaksh Singh:** Okay, got

**Hemanth Sarabu:** Okay, let's talk about

**Pratyaksh Singh:** it.

**Geoff Horowitz:** on.

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** Can we do you guys you guys can we jump to the other meeting to discuss Ulyses?

**Hemanth Sarabu:** the other meetings.

**Geoff Horowitz:** Is that okay? Yeah.

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** I sent you another one just to differentiate our transcripts.

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** I'll see y'all there.

**Hemanth Sarabu:** Bye-bye.

### **Transcription ended after 00:52:47**

*This editable transcript was computer generated and might contain errors. People can also change the text after it was created.*