# **📝 Notes**

Jul 27, 2026

## **Iris Sync**

Invited [Pratyaksh Singh](mailto:pratyaksh@crescer.ai) [Niveta Iyer](mailto:niveta@crescer.ai) [Hemanth Sarabu](mailto:hemanth@crescer.ai) [Geoff Horowitz](mailto:geoff@crescer.ai) [Siddharth Soni](mailto:siddharth@crescer.ai) [Ratul Shashank](mailto:ratul@crescer.ai) ~~[Sachin Pandey](mailto:sachin@crescer.ai)~~

Attachments [Iris Sync](https://calendar.google.com/calendar/event?eid=NnNzMHVxNzk3MmJqZGVwNXFoN2J1Mjd1OTdfMjAyNjA3MjdUMTYzMDAwWiBnZW9mZkBjcmVzY2VyLmFp)

Meeting records [Transcript](https://docs.google.com/document/d/1Y01USZmQn1jRIGNTYtqarFCnWVQNNu2Tp8Vr7UcoDE4/edit?usp=drive_web&tab=t.ja5d4bsvob1p) 

### **Summary**

The meeting covered server maintenance strategies, V4 model development, and technical data processing for synthetic datasets.

**Infrastructure and Model Development**  
The team resolved server kernel panics using Keyboard Video Mouse tools and finalized the V4 model to address class imbalance in Unexploded Ordnance classification. These updates improve pipeline consistency.

**Synthetic Data and Augmentation**  
Researchers transitioned to agent-based synthetic data generation and initiated K-Fold cross-validation to prevent data overlap. The team agreed to trial object rotation and scaling to enhance model precision.

**Technical Analysis and Troubleshooting**  
Technical teams successfully isolated an unexpected data drop occurring within the system. Resolution was achieved by verifying processing steps and confirming the correct expression of the matrix analysis.

### **Decisions**

## Aligned

* **Model version documentation process established** The team will maintain a collapsible running list to document the purpose and specifications of each model version to improve reference tracking.

* **Training data annotation cleaning strategy** The team will remove small, irrelevant "footprint discoloration" annotations from the training data to prevent the model from creating false positives.

* **False positive augmentation strategy approved** The team will include morphed, rotated, and scaled annotations in the training data as "false positives" to improve the model's robustness and accuracy.

We've **updated the Decisions section** using your feedback.

Let us know what you think: [Helpful](https://google.qualtrics.com/jfe/form/SV_5bXzKQfylMIhSXc?isHelpful=True&entryPoint=decisions&isGoogler=False) or [Not Helpful](https://google.qualtrics.com/jfe/form/SV_5bXzKQfylMIhSXc?isHelpful=False&entryPoint=decisions&isGoogler=False)

### **Next steps**

- [ ] \[Hemanth Sarabu, Geoff Horowitz, Sachin Pandey\] Discuss Eval Agent: Clarify the role, logic, and effectiveness of the eval agent, as requested by Hemanth.

- [ ] \[Sachin Pandey\] Share KVM Tool: Send the name of the remote KVM tool discussed to Geoff.

- [ ] \[Sachin Pandey\] Document Model Versions: Maintain a collapsible list that documents the specifications and details of each model version.

- [ ] \[Hemanth Sarabu, Geoff Horowitz\] Discuss HDD Purchase: Coordinate a time to discuss purchasing additional hard drives for data storage.

- [ ] \[Hemanth Sarabu\] Fix Ninja Server: Attempt to bring the Ninja server back online and troubleshoot the kernel panic.

- [ ] \[Sachin Pandey\] Clean Training Data: Remove non-essential small annotations and add previously missed annotations to the training set.

- [ ] \[Sachin Pandey\] Investigate Synthetic Data: Confirm whether synthetic datasets were used in training and analyze the cause of model false positives.

- [ ] \[Pratyaksh Singh\] Evaluate Open Source Data: Determine if external open source data can be transformed for use in the project.

- [ ] \[Sachin\] Augment Training Data: Implement rotation and scaling of objects within the training set to improve data variety.

- [ ] \[Sachin\] Fix Validation: Resolve identified technical issues within the validation process.

- [ ] \[Sachin\] Separate Code Generation: Decouple the code generation process into a separate module or branch.

- [ ] \[Pratyaksh\] Compare Histogram Range: Conduct a comparison of histogram ranges and GLCM texture metrics.

### **Details**

* **Synthetic Data and Server Management**: Ratul Shashank explains that synthetic data generation was temporarily causing high storage consumption, but they have migrated the ComfyUI software to the Wally server to manage resources. Geoff Horowitz confirms that this does not currently block any team members ([00:01:24](#00:01:24)).

* **Water Safety Discussion**: The team briefly discusses personal anecdotes regarding swimming, local water safety, and the risks of drowning in natural water bodies, particularly during monsoon seasons ([00:02:44](#00:02:44)).

* **Ninja Server Outage and Hardware Solutions**: Hemanth Sarabu reports that the Ninja server experienced a kernel panic, likely triggered by a recent power outage ([00:06:05](#00:06:05)). Sachin Pandey suggests utilizing a Keyboard Video Mouse (KVM) tool, which allows for remote access to the server’s bootloader via an HDMI interface to troubleshoot and restart hardware without requiring operating system access ([00:07:08](#00:07:08)).

* **V4 Model Overview**: Sachin Pandey provides an overview of the V4 model, explaining that it addresses class imbalance issues with UXO (Unexploded Ordnance) and AI Small objects by adjusting penalty weights for false positives ([00:08:03](#00:08:03)). The project lineage includes V1 and V2 using one pipeline, and V3 and V4 using corrected training data annotations ([00:09:30](#00:09:30)).

* **Model Documentation and Versioning**: Geoff Horowitz and Hemanth Sarabu discuss the importance of maintaining a collapsible, tracked list of model versions and their associated data ([00:10:46](#00:10:46)). They explore the possibility of hosting documentation, such as HTML or Markdown reports, directly on GitHub to allow future AI agents to query past configurations and results ([00:11:54](#00:11:54)).

* **V4 Model Performance and Deployment**: Sachin Pandey confirms that the V4 model performs well for UXO classification ([00:13:07](#00:13:07)). The team plans to test the model within the main Bedrock application before sharing it with external stakeholders ([00:14:33](#00:14:33)).

* **Hardware Protection and Backup Strategy**: Hemanth Sarabu notes that the servers currently lack an Uninterruptible Power Supply (UPS) ([00:17:13](#00:17:13)). Geoff Horowitz and Hemanth Sarabu agree to discuss purchasing hard drives (HDDs) to implement a more robust data backup system for the team ([00:18:25](#00:18:25)).

* **Synthetic Data Generation Experiments**: Pratyaksh Singh reports that initial attempts at using physics-based simulations for synthetic data were unsuccessful due to noise, leading the team to explore an interactive, agent-based approach ([00:19:51](#00:19:51)). Sachin Pandey is setting up an LLM-based loop to compare synthetic images against reference data for refinement ([00:21:11](#00:21:11)).

* **Evaluation Methodology and Data Split**: The team discusses the current synthetic data, noting that the set is primarily composed of copy-pasted images rather than purely generative content. Geoff Horowitz confirms that the workflow for splitting data between port and starboard sides remains in place ([00:24:13](#00:24:13)).

* **Validation Agent Setup**: Sachin Pandey describes the validation agent's role, which utilizes similarity metrics to compare synthetic images against reference data. The team discusses adjusting the similarity threshold—initially set at 80%—to better align synthetic data with real-world examples ([00:26:52](#00:26:52)).

* **K-Fold Cross-Validation Progress**: Sachin Pandey has initiated K-Fold cross-validation using a latitude/longitude split to ensure no data overlap ([00:28:05](#00:28:05)). Training is currently underway for several folds, and Geoff Horowitz clarifies that the team should focus on overall bounding box boundaries rather than specific layer artifacts in the visualization ([00:31:24](#00:31:24)).

* **Improving V4 Model Precision**: Sachin Pandey proposes cleaning the training data by removing annotations for small, ambiguous, or washed-out features that currently contribute to false positives ([00:38:11](#00:38:11)). Geoff Horowitz and Pratyaksh Singh agree this is a reasonable approach to improve model accuracy while maintaining consistency in annotation practices ([00:40:38](#00:40:38)).

* **Analyzing Synthetic Data Inference Results**: Sachin Pandey reports the V4 model's performance on synthetic data, noting instances where objects were misclassified due to class overlap ([00:41:49](#00:41:49)). The team identifies a need to confirm whether these synthetic samples were included in the training set and to investigate the root cause of the observed false positives ([00:44:58](#00:44:58)).

* **Data Augmentation Strategy**: Sachin Pandey and Pratyaksh Singh discuss potential training enhancements, such as rotating or scaling objects in the training data to improve model robustness. The team agrees to trial these augmentation techniques given the current availability of GPU resources ([00:49:59](#00:49:59)).

* **Central Data Verification**: Sachin Pandey questions the methodology used to determine the central data and expresses uncertainty regarding the accuracy of that determination .

* **Code and Artifact Generation Strategy**: Pratyaksh Singh and Sachin Pandey discuss the approach for generating separate code and handling artifacts, specifically mentioning the use of DRN types .

* **SPD Port Data Analysis**: The speakers examine data coming directly from the SPD port, noting a specific value of 250 .

* **Identification of Data Drop**: Pratyaksh Singh identifies an unexpected drop in the data, prompting a discussion about a technical problem occurring within the system .

* **Technical Matrix Analysis**: Pratyaksh Singh and Sachin Pandey deliberate on technical processing steps, which include comparing the soft matrix histogram range, utilizing GLCM texture, and applying CV layout President .

* **Resolution and Expression Confirmation**: The conversation concludes with Pratyaksh Singh and Sachin Pandey resolving the technical issue and confirming the correct expression has been achieved .

*You should review Gemini's notes to make sure they're accurate. [Get tips and learn how Gemini takes notes](https://support.google.com/meet/answer/14754931)*

*How is the quality of **these specific notes?** [Take a short survey](https://google.qualtrics.com/jfe/form/SV_5bXzKQfylMIhSXc?confid=xaG45YtUgdIt0us9laPsDxIUOBEBMgUIigIgABgECA&detailid=standard&screenshot=false&entryPoint=footerMain&isGoogler=False) to let us know your feedback, including how helpful the notes were for your needs.*

# **📖 Transcript**

Jul 27, 2026

## **Iris Sync \- Transcript**

### **00:01:24** {#00:01:24}

**Geoff Horowitz:** Hey,

**Ratul Shashank:** Thank

**Geoff Horowitz:** Rachel.

**Ratul Shashank:** you.

**Geoff Horowitz:** Ortil, do you have um are you generating a lot of the synthetic data that we don't need?

**Ratul Shashank:** Uh can you elaborate? Uh like

**Geoff Horowitz:** Yeah, I let me ask that differently. You know how when you train like when we train we train machine learning models and we save like lots of different checkpoints for example, right?

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** Right. But we usually don't need all those checkpoints. Um, so I'm wondering if this is not critical right now because we don't have anybody working on

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** CVAT. Uh, can you see my

**Ratul Shashank:** Uh oh.

**Geoff Horowitz:** screen?

**Ratul Shashank:** Uh I think you need the volume notification, right?

**Geoff Horowitz:** Yeah.

**Ratul Shashank:** Uh yeah I mean since Ninja is down I have installed comfy UI on Voli but uh I the models that I have downloaded I am

**Geoff Horowitz:** Got it.

**Ratul Shashank:** already uh like initially I downloaded it on volley but now I am moving it in one of the mounts.

### **00:02:44** {#00:02:44}

**Ratul Shashank:** So it should the consumption should go

**Geoff Horowitz:** Okay.

**Ratul Shashank:** down.

**Geoff Horowitz:** Okay. I'm I'm also not concerned if this is temporary because of Ninja. I don't I don't think this is blocking anybody.

**Ratul Shashank:** Yeah, it it is temporary.

**Geoff Horowitz:** So, okay. Hey guys, everybody have a good weekend?

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** Nice. Anybody do anything uh I don't know, particularly fun or exciting? No.

**Sachin Pandey:** No.

**Geoff Horowitz:** Um, do any of you guys swim? Do you like live by a lake or river or anything like that?

**Sachin Pandey:** Like even if there is a lake, it's not like the water is not clean enough to swim in

**Geoff Horowitz:** Oh, that's too bad.

**Sachin Pandey:** it.

**Geoff Horowitz:** That's too bad. Okay.

**Sachin Pandey:** I used to do some swimming in

**Ratul Shashank:** uh that is the case of India

**Sachin Pandey:** college.

**Ratul Shashank:** mostly.

**Geoff Horowitz:** You said you did it in college.

**Sachin Pandey:** I did it in college.

**Geoff Horowitz:** Rachel,

**Ratul Shashank:** I mean this set I mean we we did a lot of zooming in early years college.

### **00:04:09**

**Geoff Horowitz:** nice. Nice. Um, well, cool.

**Pratyaksh Singh:** What are you guys talking about?

**Geoff Horowitz:** Yeah. I was just wondering if any if any of you guys live near like a you know

**Pratyaksh Singh:** Swimming.

**Geoff Horowitz:** a place where you go swimming, but uh they were saying that you know even if there's like a lake around it's usually not clean enough to swim in.

**Pratyaksh Singh:** Yeah, I I live around something like that.

**Geoff Horowitz:** Oh yeah, you go a

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** lot.

**Pratyaksh Singh:** Not a lot. Like I live around waterfall. There are lakes and waterfall but I don't know how to send that's something that I have to learn.

**Geoff Horowitz:** Oh my

**Pratyaksh Singh:** So I yeah I usually I usually will go to

**Geoff Horowitz:** gosh.

**Pratyaksh Singh:** like shallow waters but I mean you know these places

**Geoff Horowitz:** Yeah.

**Pratyaksh Singh:** in mansoon when you know when it's very good they usually close it because people just get drunk and

**Geoff Horowitz:** Uh yeah.

**Pratyaksh Singh:** then usually every year like someone drowns like three or four people drown

### **00:05:15**

**Geoff Horowitz:** Uh, crutch. Well, number one, I'll say you should really learn to swim for exactly that reason. Apparently, it's a it's like really dangerous to not know how to swim.

**Pratyaksh Singh:** Uh-huh.

**Geoff Horowitz:** People drown all the time because they don't know how to swim.

**Pratyaksh Singh:** Yeah. Yeah.

**Geoff Horowitz:** But, uh, but number two,

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** it might help with all this this heat these heat issues that you have. Just kind of, you know,

**Pratyaksh Singh:** Oh, yeah.

**Geoff Horowitz:** go in the lake.

**Pratyaksh Singh:** It it doesn't help then because you know it dries out during that

**Geoff Horowitz:** Oh.

**Pratyaksh Singh:** time.

**Geoff Horowitz:** Oh,

**Hemanth Sarabu:** And

**Geoff Horowitz:** that's too bad.

**Pratyaksh Singh:** Yeah. But still still like there is water there so it's good but you know it's not moving water.

**Hemanth Sarabu:** she's

**Pratyaksh Singh:** So use them

**Geoff Horowitz:** Yeah.

**Pratyaksh Singh:** awarded.

**Geoff Horowitz:** Yeah. Yeah. That'd be bad. Uh okay. Um Okay. All right. We talked about Wall-E Sachin.

### **00:06:05** {#00:06:05}

**Hemanth Sarabu:** Wall-E.

**Geoff Horowitz:** Uh he said he's going to nothing.

**Hemanth Sarabu:** Hey, what what did I miss about Wall-E?

**Geoff Horowitz:** We just uh you know trying to manage that space drive.

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** Sachin Hemmon is going to try to work on Ninja later today.

**Sachin Pandey:** Okay.

**Hemanth Sarabu:** That's so primarily coding agent. Are you losing anything

**Sachin Pandey:** Uh no like not about coding agent.

**Hemanth Sarabu:** else?

**Sachin Pandey:** Uh it was like all the open source that I downloaded was on Ninja. So other than that nothing imported on

**Hemanth Sarabu:** Oh yeah.

**Sachin Pandey:** Ninja.

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** I think Red Tool is using it

**Hemanth Sarabu:** the um there was a there was an outage.

**Sachin Pandey:** Yeah. Ratul was using country UI.

**Geoff Horowitz:** too.

**Hemanth Sarabu:** Okay. Ah okay. Okay. I see. Yeah, there was a there was an outage which is why Wally went down at the same time Ninja but Wally has a restart mechanism. It comes back up but Ninja I don't know what happened.

### **00:07:08** {#00:07:08}

**Hemanth Sarabu:** It it uh it went into kernel panic. So, it'll take some time to to figure that out.

**Sachin Pandey:** like the tool I shared with you like it could be helpful because you just ask a to like go through

**Hemanth Sarabu:** Yeah.

**Sachin Pandey:** it. It can also like boot into the grab loader and you can still have the

**Hemanth Sarabu:** Yeah. Yes. Yes. Yes. Yes. That's true. Yeah. That's a good idea. I I'll just get it.

**Sachin Pandey:** access.

**Hemanth Sarabu:** So,

**Geoff Horowitz:** What?

**Hemanth Sarabu:** Jeff,

**Geoff Horowitz:** What is it?

**Hemanth Sarabu:** I don't know if Sachin shared a KVM tool.

**Geoff Horowitz:** Yeah.

**Hemanth Sarabu:** Um, you can talk about it if you

**Sachin Pandey:** Yeah, think of it like a remote desktop but it it is it is taking it is sharing the output

**Hemanth Sarabu:** what?

**Sachin Pandey:** HDMI. So even the boot boot loader get displayed uh in the screen like you can access it through Wi-Fi you can do a hard restart and it doesn't need any kind of

### **00:08:03** {#00:08:03}

**Hemanth Sarabu:** So,

**Sachin Pandey:** software

**Hemanth Sarabu:** Wally has some uh Wally has this built in because it's a it has a server grade motherboard. But ninja does

**Geoff Horowitz:** This is cool.

**Hemanth Sarabu:** Oh,

**Geoff Horowitz:** This is cool. Sach, can you send me the name? I'd like to just like look at it briefly.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Um, okay. Uh I guess project let's uh let's start with you and then actually Sachin do you think that you could give us the and and I'm gonna I'm going to try to keep us all to this. Do you think you can give us the fiveinut overview of the V4 model that you shared and then we're going to put pin in it. I want project to to take over and then Sachin we can get back to to your updates at the

**Sachin Pandey:** Yeah. Yes. So V4 model was mainly like to uh to fix a few things like

**Geoff Horowitz:** end.

**Sachin Pandey:** I asked ML intern to run multiple test. Main issue was the UXO and AI small were not uh in much quantity and the the loss or the penalty on the false positive was like balanced between all the classes.

### **00:09:30** {#00:09:30}

**Sachin Pandey:** Uh like the penalty was not uh uh supporting model to predict uh UXO or like small classes or low pixel mode. So like it ran some test and like this was the best model which came out of all the test.

**Hemanth Sarabu:** How does it compare with um do we have a definition for what baseline is? So the the model we trained for S one, the model

**Geoff Horowitz:** I think I was just going to say baseline we've been using is V1.

**Hemanth Sarabu:** we uh V1 is uh what is the definition of

**Geoff Horowitz:** Um, Sachin,

**Hemanth Sarabu:** V1?

**Geoff Horowitz:** do you want to explain

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** it?

**Sachin Pandey:** So B1 will be the like same pipeline and just just

**Geoff Horowitz:** Sergeant,

**Sachin Pandey:** the new data sorry same pipeline

**Geoff Horowitz:** be a little more clear. It's the same pipeline that we used for for the first deliverable,

**Sachin Pandey:** that we use for uh s1 and we just updated a data

**Geoff Horowitz:** right?

**Sachin Pandey:** and then trained the model. So V2 model was also trained on the same uh pipeline.

### **00:10:46** {#00:10:46}

**Sachin Pandey:** Not this one. This V2 was uh like little bit of class change like adding the UXO and uh the learning rate. This was change in the V2. For V3 we fixed the training data because we found some mistakes in the data. So V3 and V4 are trained on the same training data and V\_sub1 and V2 are trained on the same training data. like the annotations by training the time in

**Geoff Horowitz:** Uh,

**Sachin Pandey:** annotations.

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** Sachin, I I just thought about it as we were discussing this. It It might help to it might help to just maybe keep a collapsible running list of like what each of these models are. Like you have the references down here. You see what I'm saying?

**Sachin Pandey:** Yes. Yes. I I can add

**Geoff Horowitz:** Yeah, I think it should be pretty easy to add now.

**Sachin Pandey:** it.

**Geoff Horowitz:** But I that's what I was saying.

**Hemanth Sarabu:** This is cool. This report is cool.

**Geoff Horowitz:** I think it's actually a really there's a lot that I really like on on top of everything kind of in the presenting mode.

### **00:11:54** {#00:11:54}

**Geoff Horowitz:** I like that a lot of this is just documented. Um even like when it comes down to I don't know if you saw this Hmon but like even if it comes down

**Hemanth Sarabu:** Yeah. Yeah.

**Geoff Horowitz:** to like where the checkpoints are you know where the data we're using is

**Hemanth Sarabu:** Yeah. Yeah. That's a good point actually. Hey, uh what is uh do we check this in to

**Geoff Horowitz:** uh

**Hemanth Sarabu:** GitHub?

**Sachin Pandey:** It is in the it it is stored in portry folder. So it it it can be hosted but not on the

**Hemanth Sarabu:** I think uh yeah I think it might make sense to check this

**Sachin Pandey:** GitHub.

**Hemanth Sarabu:** in. The nice thing about checking it in is um your agent at let's say it is October and third you know the third project and we're like oh what does uh you know something about this the config or data set something something your agent will be able to go through your GitHub history your git history results and uh and pull this

### **00:13:07** {#00:13:07}

**Sachin Pandey:** I haven't tried like pushing HTML but can we view it directly in like some kind of

**Hemanth Sarabu:** That's a good question.

**Sachin Pandey:** URL?

**Hemanth Sarabu:** I feel like think I think you do.

**Geoff Horowitz:** I

**Hemanth Sarabu:** But also um this could also be markdown though, right? Oh, I guess this is interactive. Is this interactive?

**Sachin Pandey:** No, not this

**Geoff Horowitz:** there's a component. There's a there's a minor component minor like drop down

**Sachin Pandey:** one.

**Hemanth Sarabu:** I mean, this feels like it could just be markdown.

**Sachin Pandey:** Yeah, it could be.

**Geoff Horowitz:** Son, I think there actually is a way to like host HTML on GitHub. I know you can do it for like personal pages. Um, but uh I don't know exactly.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** Anyway, I think this is a minor point. Um, so overall you think the V4 model is actually doing pretty well. Do you think that there are are there still next steps coming out from this?

**Sachin Pandey:** So like if you only focus on UXO uh this is like a good model because uh the falls negative rate was low for this one also.

### **00:14:33** {#00:14:33}

**Sachin Pandey:** And and if we for other classes I were testing the main the base binary model is doing also well for other classes like because it uh it can predict the rest of the classes but it's just binary. So like we can overlap those two to get the like uxos but for other classes I think binary will be Good.

**Geoff Horowitz:** Okay, I would like to pause there unless there are specific follow-up questions anybody has for Sachin?

**Hemanth Sarabu:** I guess um can we is this something we are ready to give to Bedra?

**Sachin Pandey:** Yeah, like we can test it out and like we I have added it in the main bedrock app. We can test it out and if it looks good, we can like share it with

**Geoff Horowitz:** So, so we have a little bit of time,

**Sachin Pandey:** them.

**Hemanth Sarabu:** Goodness.

**Geoff Horowitz:** he and I think I'd like to hear what product tools progress is because I wonder if like even if we used all the synthetic data that they're generating now as um like test data, I'm interested to see what those results would look like on this model.

### **00:16:01**

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** You have any thoughts there?

**Hemanth Sarabu:** No, that's fine. I just want to make sure we are approaching with MLM.

**Geoff Horowitz:** Yeah.

**Hemanth Sarabu:** Uh, we're still approaching deliverability.

**Geoff Horowitz:** Yeah.

**Hemanth Sarabu:** Um, that's all. So, I don't think I'm I'm not saying we should not saying we should push this right away, but that are we are we close to it. So, um I guess Yeah, I know we're switching. Rul,

**Geoff Horowitz:** Oh.

**Hemanth Sarabu:** does that mean you're pretty blocked because of Ninja? Don't do any more experiments,

**Ratul Shashank:** Uh I just I I just transferred

**Hemanth Sarabu:** right?

**Ratul Shashank:** Comfy UI to body today. So I should resume the

**Hemanth Sarabu:** Okay. Okay. Okay.

**Ratul Shashank:** work.

**Hemanth Sarabu:** I'll I'll try to bring it back up the next few hours. Um but no guarantees because Yeah. No guarantees because it's Colonel Panic. Not sure where the issue is.

**Ratul Shashank:** Yeah,

**Geoff Horowitz:** Do you guys

**Ratul Shashank:** I I on my end it is not a problem and I have transferred to it's

### **00:17:13** {#00:17:13}

**Geoff Horowitz:** know

**Ratul Shashank:** good.

**Hemanth Sarabu:** Okay. Okay, it's

**Geoff Horowitz:** was anybody running like specific experiments that

**Hemanth Sarabu:** good.

**Geoff Horowitz:** um I don't know was anybody running anything Ninja that like might

**Hemanth Sarabu:** No, no, no, no. There was an outage in the area.

**Geoff Horowitz:** have

**Hemanth Sarabu:** Power outage. And that's what that's most likely what caused it. As in at least that's most likely what triggered it.

**Geoff Horowitz:** understood. But it just I mean look I I get it that colonel panic can come from a lot of different sources. Could be hardware, could be software, right? But uh but if it was just like a surge. It feels like a restart should have helped. Um, unless something was burnt out, which you got it on surge protectors and everything.

**Hemanth Sarabu:** We'll see.

**Geoff Horowitz:** So,

**Hemanth Sarabu:** Yeah, we don't do that, right? We haven't done that.

**Geoff Horowitz:** we don't do what?

**Hemanth Sarabu:** We don't have search protectors.

**Geoff Horowitz:** You're joking.

**Hemanth Sarabu:** Um, okay.

### **00:18:25** {#00:18:25}

**Hemanth Sarabu:** We don't have Sorry. We don't have a an uninterrupted power supply system.

**Geoff Horowitz:** Oh yeah, yeah, yeah, yeah.

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** But but you have it in a surge protector.

**Hemanth Sarabu:** Yeah, it should be in the wall.

**Geoff Horowitz:** Yeah. Oh. Oh,

**Hemanth Sarabu:** Yes.

**Geoff Horowitz:** like a what do they call that? GFI or

**Hemanth Sarabu:** I I don't know. It's whatever whatever the the office has.

**Geoff Horowitz:** something.

**Hemanth Sarabu:** And then there's a power supply unit which maybe has some protection, but we don't have a separate piece of kit.

**Geoff Horowitz:** Okay. Okay.

**Hemanth Sarabu:** Okay. Yeah.

**Geoff Horowitz:** Let's uh very quickly let's you and I discuss at some point later just buying a

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** whole bunch of um HDDs and I can I

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** can set I can set up a backup on my

**Hemanth Sarabu:** Yeah. Yeah.

**Geoff Horowitz:** Okay.

**Hemanth Sarabu:** Sounds

**Geoff Horowitz:** All right. Uh project for

**Hemanth Sarabu:** good.

**Geoff Horowitz:** tool.

**Pratyaksh Singh:** Hey, just a short update from my side.

### **00:19:51** {#00:19:51}

**Pratyaksh Singh:** Uh I think over the weekend and today we were all focused on different part of synthetic data generation to augment the data. I was trying something that Amon said about uh forcing it to work as a you know trying to write a physics based simulation to to you know generate the whole image but uh I wasn't able to have it work like the images that it generates look like you know it looks very noisy and and it doesn't look like what it doesn't look like what uh you know what the image that bit gave us.

**Geoff Horowitz:** Can you show Can you show an example just for

**Pratyaksh Singh:** Uh another thing uh yeah let yeah let me

**Geoff Horowitz:** interest?

**Pratyaksh Singh:** see I'll try to find it.

**Hemanth Sarabu:** Well, I think he's pulling that up.

**Pratyaksh Singh:** I just can I just share it on Slack?

**Geoff Horowitz:** Yeah.

**Hemanth Sarabu:** What the heck? Apparently, uh, Opus 5 one-shotted Call of Duty. I don't know how much of it is true, but people have put up, uh, repos and stuff.

**Pratyaksh Singh:** Yeah, I saw Claude of duty, right?

### **00:21:11** {#00:21:11}

**Geoff Horowitz:** a lot of

**Pratyaksh Singh:** Lord of I saw that.

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** duty.

**Pratyaksh Singh:** So I was kind of working more in an interactive manner. I think uh I asked Sachin to set this up where you just email the agent,

**Hemanth Sarabu:** Mhm.

**Pratyaksh Singh:** right? I we just give an email to that agent where given the image and you know whatever output it generates and the current image you know whatever the reference image is the eval is that you know both the images will be passed through an LLM and then it will kind of like it will uh the LLM will tell the difference between that so that the coding agent can in a loop make it better such had already a lot of agents set up.

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** So I told him to set it up. I think the results on that he can share.

**Hemanth Sarabu:** Heat.

**Geoff Horowitz:** How many agents did we have? Sasha, I thought we just had uh Gemma and Quentin. Oh, we lost S. Never mind.

### **00:22:27**

**Sachin Pandey:** Hello.

**Geoff Horowitz:** Hey,

**Sachin Pandey:** Yeah. Did I miss anything? I just think in the connection right off

**Geoff Horowitz:** I was just asking if we had more agents set up than Gemma and Quen.

**Sachin Pandey:** currently two models are set up like 20 is set up on H100 and most of these agents are like these are like claude and gro are set up right now on my user. Local agents are only when models are only set up locally. I will share the reports from uh cloud 2\. It ran out of context so it stopped midway. Insert the AMTX uh like few images from ANTX are looking best and like similar to the original image we shared and uh VW data is also looking uh

**Hemanth Sarabu:** Interesting.

**Sachin Pandey:** decent not with yeah the the

**Hemanth Sarabu:** You you're you're talking about

**Sachin Pandey:** report I shared

**Hemanth Sarabu:** uh whatever project is talking

**Sachin Pandey:** data

**Hemanth Sarabu:** about.

**Sachin Pandey:** Yes.

**Pratyaksh Singh:** Oh. Yeah.

**Hemanth Sarabu:** I thought I thought uh I guess there's a little bit of a conflict right there cuz um you're saying it's not really

### **00:24:13** {#00:24:13}

**Pratyaksh Singh:** So yeah,

**Hemanth Sarabu:** working.

**Pratyaksh Singh:** I think for me what I was doing it's not working but the loop that Sachin set up on the end

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** seems like that is working.

**Hemanth Sarabu:** So what what what does working mean?

**Sachin Pandey:** So these are not looking good but uh the slim ones the ENT has two type of

**Hemanth Sarabu:** Slim.

**Sachin Pandey:** data one is this kind of thing and other is like very slim. Uh Jeff, you can filter on the top. Uh it uh if

**Geoff Horowitz:** What do you mean very slim? What does that mean?

**Sachin Pandey:** you can you instead of all type select the Yeah. Yeah.

**Geoff Horowitz:** uh I vaguely

**Sachin Pandey:** So these are I guess these are real real ones.

**Geoff Horowitz:** recall I think it was last Wednesday we were discussing actually splitting the data up between port and starboard.

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** What what was the status of that workflow?

**Pratyaksh Singh:** That is already like we have we have the data set for synthetic data generation. We were thinking of doing this.

### **00:25:21**

**Pratyaksh Singh:** We we already have like spread. We have the we have like the workload is editor. These are such generated images.

**Sachin Pandey:** Yeah, only five images were real. The rest are

**Pratyaksh Singh:** These

**Sachin Pandey:** generated.

**Pratyaksh Singh:** look have to simulate the light areas, right? If it's

**Sachin Pandey:** Yeah, these will be sand patches.

**Pratyaksh Singh:** missing

**Geoff Horowitz:** Everything's okay. You say it's awful. It's not

**Hemanth Sarabu:** Um, so this is what it's generating.

**Geoff Horowitz:** bad.

**Hemanth Sarabu:** Is that what you guys got?

**Geoff Horowitz:** Yeah.

**Hemanth Sarabu:** Hello. Um, okay. So oh interesting it actually generated

**Sachin Pandey:** No,

**Hemanth Sarabu:** these.

**Sachin Pandey:** these are like top ones are real. The rest are

**Geoff Horowitz:** I don't know if you can see my screen Hmon,

**Hemanth Sarabu:** Oh

**Geoff Horowitz:** but these these blue are real and then the green are

**Sachin Pandey:** generated

**Geoff Horowitz:** generated.

**Hemanth Sarabu:** okay. Um can you I mean I'm going to ask actually what does the eval agent do?

**Sachin Pandey:** for this.

### **00:26:52** {#00:26:52}

**Sachin Pandey:** I have no idea. Like I just give him the goal and he was like working on it.

**Hemanth Sarabu:** H.

**Sachin Pandey:** Like I told him to like either use physics simulation or modify XTF or even like

**Hemanth Sarabu:** H.

**Sachin Pandey:** generate the images if that's needed for

**Hemanth Sarabu:** But that's not Eval, right? That's not the EVA

**Sachin Pandey:** test for validation like checking whether it's was like it's matching or

**Hemanth Sarabu:** agent.

**Sachin Pandey:** not. It was using some kind of matrix on how similar the image is to the main image. So I set it to 80 like not too

**Hemanth Sarabu:** Um,

**Sachin Pandey:** much similar but I will try like setting it to 60 like which is like similar to the one I will see like

**Hemanth Sarabu:** okay.

**Sachin Pandey:** it because it was asking for more data also.

**Hemanth Sarabu:** Um,

**Sachin Pandey:** So I will see providing more data to it.

**Hemanth Sarabu:** so um, okay, let's let's talk about this. We can dig into this a little bit later. I actually have to run.

### **00:28:05** {#00:28:05}

**Hemanth Sarabu:** Uh, I've got a call starting in 4 minutes. Um, I will have some time in an hour. Maybe I can try to get on a call with you guys. But yeah. Yeah. Um, let's do that.

**Geoff Horowitz:** That works for me at

**Hemanth Sarabu:** I guess I'm surprised he went somewhere.

**Geoff Horowitz:** least.

**Hemanth Sarabu:** Okay. Yes. All right. Um, we got to drop. Good to later. Thank

**Geoff Horowitz:** projects. Were we also looking at the K-fold val Kfold um validation?

**Pratyaksh Singh:** crossation.

**Geoff Horowitz:** Yeah.

**Pratyaksh Singh:** Yeah, here we were. I think Satin model set up the cable crossation right with the lat long split.

**Sachin Pandey:** Uh I did set it up. Uh let me get the report further. IU were like around 50 55%. So on pixel levels I need to look here. So fold zero fold zero is 0.54 fold one is 0.52 fold two uh like

**Geoff Horowitz:** on what

**Sachin Pandey:** I let me let me share the image of split like I asked it to split the like all the like data data set by data set into five categories so they are not overlapping and use uh like each one for each fold like it will be using

### **00:29:57**

**Geoff Horowitz:** Mhm.

**Sachin Pandey:** four for training and one the remaining one for the testing. It will do for five times for each section.

**Geoff Horowitz:** But I I guess what I'm asking Sachin is like what should I be comparing that to? Right. So So I don't know. So I'm looking here, right? Is that should that be compared to the V4 model here? Like what what is it similar to and what are the differences?

**Sachin Pandey:** Is it similar? It was just yes.

**Geoff Horowitz:** Does that question make sense?

**Sachin Pandey:** Uh I don't have the like object level matrix yet. So we can't compare it with these models. And also I don't think like there is a validation set because all all

**Geoff Horowitz:** Okay.

**Sachin Pandey:** of the validation set has gone through the training. So we can just take the average of like them.

**Geoff Horowitz:** Yeah.

**Sachin Pandey:** We can do one thing like we can uh uh I will try to find out like where to validate them equally on equal like equal footing.

### **00:31:24** {#00:31:24}

**Sachin Pandey:** The image I shared is the like how it splitted the data into

**Geoff Horowitz:** Amy,

**Sachin Pandey:** categories different color different

**Geoff Horowitz:** you know, I'm not sleep in that

**Sachin Pandey:** data.

**Geoff Horowitz:** one. Oh, wait. Yeah. Yeah. So what I'm seeing here, what you're saying is that this is this is a visualization of the areas that were used for validation and each color is a different

**Sachin Pandey:** Yes. Each a different set.

**Geoff Horowitz:** And what are these ones where the like see how blue kind of whatever we've got like one two three or you could even look at the yellow here where there's clearly a few of them. How do we make sense of that?

**Sachin Pandey:** In in which data set? Port

**Geoff Horowitz:** Uh,

**Sachin Pandey:** one.

**Geoff Horowitz:** so I'm looking at port. I'm looking at fold one. And there's a few different iterations of fault one. Does that make sense? It doesn't make sense.

**Sachin Pandey:** No,

**Geoff Horowitz:** So,

**Sachin Pandey:** you

**Geoff Horowitz:** I have this.

### **00:33:28**

**Geoff Horowitz:** Okay. Can you see this? Oh, no. Do it here. Okay. So, I'm looking over here. Can you see what I just drew? And there's one,

**Sachin Pandey:** Yes.

**Geoff Horowitz:** two, three, four, at least four different kind of iterations of fold one. Can you see that on your end too?

**Sachin Pandey:** Yeah. like the layers,

**Geoff Horowitz:** Yeah,

**Sachin Pandey:** right?

**Geoff Horowitz:** there's layers. How do I make sense of the

**Sachin Pandey:** Yes.

**Geoff Horowitz:** layers?

**Sachin Pandey:** I think that will be the like file. So, I didn't do the split like I did last time like drawing a polygon and cropping it out.

**Geoff Horowitz:** Uhhuh.

**Sachin Pandey:** Uh I I had a data ready which I shared with with PEX where the the data was already cropped into the smaller regions. uh and it the port and starboard were separated. So I just asked it to like draw find the total area overlap area and divided it equally into like five categories and pull the like without dividing the image further like 512 by cross 512 images were already cropped off with the annotation ready.

### **00:34:53**

**Sachin Pandey:** So I just uh ask him to like group together the like these files and take it into one validation set.

**Geoff Horowitz:** I think I understand.

**Sachin Pandey:** So no additional

**Geoff Horowitz:** So what you're saying is what you're saying is I should ignore these I should ignore

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** these like layers here and instead I should just look at the overall bounding box.

**Sachin Pandey:** boundaries.

**Geoff Horowitz:** Okay.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Fine. Okay. Okay. I mean, that seems seems like a reasonable approach to me. Um seems like a reasonable approach to me. Okay. So you haven't you haven't gotten results from that K-fold then yet.

**Sachin Pandey:** Yeah, two, three,

**Geoff Horowitz:** Correct.

**Sachin Pandey:** and four are still in training right now.

**Geoff Horowitz:** Okay. Okay. All right. Um, Kach, was there anything else that you wanted to bring up?

**Sachin Pandey:** Oh,

**Geoff Horowitz:** I I'll shoot out a meeting. We can reconnect with him uh at the top of the hour, but was there anything else that you wanted to bring up?

### **00:36:14**

**Pratyaksh Singh:** No, I just looked uh in for open source data. There were some available.

**Geoff Horowitz:** Yeah.

**Pratyaksh Singh:** I'm going to see if I can uh you know if it will be possible to transform them into one that can be used that can be useless.

**Geoff Horowitz:** Okay. Um, this out Okay. Um Sachin, before we jump off, can we So let's let's revisit this quickly. Um, so to kind of summarize here, you know, when we're looking at UXOs as the as the thing we're really trying to optimize for because of the small sample size, 80% is going to be probably as close as we can get.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** Okay. So I I asked this at the end and you you briefly you briefly touched on um some areas that we could go but can you can you summarize what you view as the next steps from this V4 model

**Sachin Pandey:** like next improvement we can made made in this one.

**Geoff Horowitz:** if any or do you think that we're I mean I I can think of you know a few places to go but I want to hear your your

### **00:38:11** {#00:38:11}

**Sachin Pandey:** So uh we can try to fix the AI big one because

**Geoff Horowitz:** approach.

**Sachin Pandey:** the AI big has like generally the main center the bigger part is uh it will be easier if I show it.

**Geoff Horowitz:** I thought you discussed that down here on the size

**Sachin Pandey:** So

**Geoff Horowitz:** filter.

**Sachin Pandey:** yeah it it improved but like we can do it more because uh so see if we remove all the small annotations. So if you see if you have a example in mind like the in BW data set there's a big like circular thing right in the center and on one side the that is very obvious but on other side there is something like very little uh like part of it There. Uh, give me a second. Uh, annotation review. So something like this. So if you see this is the main object but like we also classify like little bit of this as the AI. So if we can just drop all those uh it will reduce the mistakes we make because if

### **00:39:29**

**Geoff Horowitz:** Uh-huh.

**Sachin Pandey:** you see the mainly mistakes are object where the model thinks like the small these areas are caused by these areas some like this part because we are only interested in this. If we only keep the bigger objects the like values will also increase if we drop like object like these.

**Geoff Horowitz:** So what what is your proposal then?

**Sachin Pandey:** Uh we can like for this one we can we can clean the data more like remove these objects which are not needed. Like if you only consider this or by removing these small ones the model will stop making the mistakes. So we don't even have to use the filter.

**Geoff Horowitz:** Got it. So you're saying actually remove it from the underlying annotations,

**Sachin Pandey:** model.

**Geoff Horowitz:** right?

**Sachin Pandey:** Yes. Uh the model model just learns like the features

**Geoff Horowitz:** Okay.

**Sachin Pandey:** like these parts will mod will start ignoring them like not this one like this.

**Geoff Horowitz:** I think that's reasonable.

**Sachin Pandey:** This is big like this has a black feature in it but some are like very

### **00:40:38** {#00:40:38}

**Geoff Horowitz:** Exactly.

**Sachin Pandey:** small where models generally make mistakes.

**Geoff Horowitz:** Exactly. So, so I think I think that's exactly my my concern is you showed a few examples where there actually does look like there's some some feature there, some black region, and I think those probably should not be removed, but just that kind of um I don't even know what to call it, like foot footstep uh footprint discoloration. I think your approach there is reasonable.

**Sachin Pandey:** So these are the mistakes which model makes and it will all be fixable if you just remove like similar things like in the train similar things like these from the training data.

**Geoff Horowitz:** Are we going to run into like a consistency issue where in some places that discoloration that uh I don't know what to call it that like washed out discoloration is tagged and in some places it isn't.

**Sachin Pandey:** No, it will be like anywhere where the AY is like the black thing is in center or like split equally between the two half then we will include it. Else anything which is like just changing the little bit color will not be included.

### **00:41:49** {#00:41:49}

**Geoff Horowitz:** just on itself.

**Sachin Pandey:** So things like these will not be included.

**Geoff Horowitz:** Okay, that seems reasonable to me. Protouch, you agree?

**Sachin Pandey:** The other

**Pratyaksh Singh:** Yeah, that's fine.

**Sachin Pandey:** classes

**Geoff Horowitz:** Yeah.

**Sachin Pandey:** like this is the only thing I can think of.

**Geoff Horowitz:** Okay. How much synthetic data have we incorporated if any?

**Sachin Pandey:** Uh till now we didn't added

**Geoff Horowitz:** So I mentioned this very briefly before.

**Sachin Pandey:** any

**Geoff Horowitz:** Um I think it would be interesting to run the model on some of the synthetic data as test data. Um and see what the results we get. projects. Do you have any thoughts there?

**Pratyaksh Singh:** I'm sorry. Can I repeat it? What is happen?

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Saying

**Sachin Pandey:** Yeah. Uh so I did predict on the the like centric

**Geoff Horowitz:** something

**Sachin Pandey:** data which which uh Rakul shared with me model was like capturing 22 out of 32 objects. The first quality was also high like around 33 objects were falsely classified.

### **00:43:59**

**Sachin Pandey:** Yeah, this was the one.

**Geoff Horowitz:** And do you have a sense? Do you have a

**Sachin Pandey:** So out of 33 ground truth to 23 were classified and 32 are false positive and

**Geoff Horowitz:** sense?

**Sachin Pandey:** 10 false

**Geoff Horowitz:** And do you have a sense if that's a gap in the model or a gap in the data?

**Sachin Pandey:** negative.

**Geoff Horowitz:** like that the data doesn't well represent what the real data is or is it actually we tripped the

**Sachin Pandey:** Oh it could be both because like the data

**Geoff Horowitz:** Oh.

**Sachin Pandey:** the data was generated using both UXO and AI small. So if if you see this the model only classified three out of 23 only three are classified

**Geoff Horowitz:** Huh.

**Sachin Pandey:** as a small and rest 20 are classified as UXO because in ground all of all of the classes are classifi moved into a single class AI small black that's why like after moving like after fixing this issue we get the 23 true positive

**Geoff Horowitz:** Son, do you think you can have your agent pull together a representative?

### **00:44:58** {#00:44:58}

**Geoff Horowitz:** of example of places where it did well, places where it did

**Sachin Pandey:** images.

**Geoff Horowitz:** poorly.

**Sachin Pandey:** I think Rul can share it because I shared the these files with him where the prediction were he was looking into it.

**Geoff Horowitz:** You followed what I was asking now or no?

**Pratyaksh Singh:** uh the reports, right?

**Geoff Horowitz:** What I was asking was since we did not use the synthetic data to train the V4 model,

**Pratyaksh Singh:** Mhm.

**Geoff Horowitz:** can we use the V4 model to predict it to can we can we run inference using the V4 model on the synthetic data and see what results we get? And that's what Sachin said he already did.

**Pratyaksh Singh:** We don't have any data right

**Geoff Horowitz:** We we do right

**Pratyaksh Singh:** the copy pasting one I think Sachin already uses those entering

**Geoff Horowitz:** in training suction.

**Sachin Pandey:** uh I will see what for this V4 model I think it dropped it because it was introducing more false positive. I will check the like the training metrics for this one.

**Geoff Horowitz:** So then what when we when you were just showing these 32 examples of

### **00:46:32**

**Sachin Pandey:** Oh these are generated by RTL. uh Rul can like provide more information how these were generated but I don't think these were these are

**Geoff Horowitz:** uh

**Sachin Pandey:** part of the training data

**Ratul Shashank:** Yeah, I just shared a small set of examples to get a view if the data gener I'm generating is actually any good. So that was

**Geoff Horowitz:** Wait. So,

**Ratul Shashank:** that.

**Geoff Horowitz:** so project we do have synthetic data. Red tool generated some of UXOs's and AOI small black.

**Pratyaksh Singh:** Those are just copy paste, right? Or are

**Ratul Shashank:** Yeah, it was it was it was what I shared with

**Pratyaksh Singh:** they?

**Ratul Shashank:** you.

**Pratyaksh Singh:** Yeah,

**Geoff Horowitz:** Those are copy paste.

**Pratyaksh Singh:** those are those are copy pasted also.

**Geoff Horowitz:** So, so actually Sachin, that's really good to know, right? Because the model should be able to pick that up. If it's just copy and paste, it's should really be within the distribution. Um, so I think it's worthwhile to dig into those results more.

### **00:47:36**

**Geoff Horowitz:** Number one, confirm that they were not in the training set, which hopefully they weren't. Um because if they were then it's even more concerning that we're messing those up. Stocking you with me there or no?

**Sachin Pandey:** Yeah,

**Geoff Horowitz:** Yeah. Okay. Um,

**Sachin Pandey:** I

**Geoff Horowitz:** so just to recap, Son, I think I think your uh your idea about cleaning up the underlying data is is reasonable. I see no reason not to clean it up, but but be very particular and conscientious about which annotations we choose to remove. Um and then number Oh,

**Sachin Pandey:** So the second thing was I will also like check the prediction where model is

**Geoff Horowitz:** sorry.

**Sachin Pandey:** predicting the false positive if it is it is like similar feature what we are marking at AI small even though if it's not UXO I will be adding it into the

**Geoff Horowitz:** Hold on. Hold on. On the synthetic data you're talking about or on the the the on the

**Sachin Pandey:** training on the original data I will be like pulling

### **00:48:49**

**Geoff Horowitz:** original

**Sachin Pandey:** the prediction mask there and if any areas like we because these were marked by labelers. So there is a chance like we have missed the missed any like annotation like small ones a

**Geoff Horowitz:** Understood.

**Sachin Pandey:** small things.

**Geoff Horowitz:** Understood.

**Sachin Pandey:** So if those are missed model is predicting this I will be adding those into the

**Geoff Horowitz:** Makes sense. Makes sense. Okay.

**Sachin Pandey:** data.

**Geoff Horowitz:** And then number two is to review I'm calling it synthetic, but I guess we're making a distinction. to review the cut and paste data that um that we used to to run inference and really understand number one is it included in training or not. And number two, uh you know, why why are we seeing false positives there if it's pretty darn close to the underlying training data? Yeah.

**Sachin Pandey:** Yeah, I will I will check those out.

**Geoff Horowitz:** Okay. All right,

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** guys. Oh, go

**Sachin Pandey:** Yeah, I think Rul suggested one more like thing we can try out in the training like

### **00:49:59** {#00:49:59}

**Geoff Horowitz:** ahead.

**Sachin Pandey:** the annotic data where the annotations are not looking like the the things we want we can put it into a training data and mark it as false positives. So like I think it will be helpful like morphing them out like

**Geoff Horowitz:** That's interesting.

**Sachin Pandey:** increasing the length or changing some kind of shape.

**Geoff Horowitz:** I see no harm in trying it and seeing what happens. Um I wonder if and marking it as a false positive. I mean, is that substantially different than like marking it as a false positive. Isn't that what we do

**Sachin Pandey:** like it will be in background.

**Geoff Horowitz:** anyway?

**Sachin Pandey:** There will be no class assigned to it.

**Geoff Horowitz:** I I see no harm in trying it. I can see some I can see some places where that might actually end up giving us poor results, but I you know, our approach is always let's let's try it. We've got the GPUs, so why not?

**Sachin Pandey:** Okay.

**Geoff Horowitz:** If you

**Pratyaksh Singh:** I think I discussed this with ratul.

### **00:51:50**

**Pratyaksh Singh:** Uh the question is such an if the shape of the annotation change change would you

**Geoff Horowitz:** agree.

**Pratyaksh Singh:** have not marked it? So let's say let's say you flatten out the qxo right but the colors are still the same.

**Sachin Pandey:** Yeah,

**Pratyaksh Singh:** Would you have still marked it or not?

**Sachin Pandey:** I will move it in a mode.

**Pratyaksh Singh:** So there is your answer right. You can't move it to background just by changing the shape and stuff.

**Sachin Pandey:** So like then should be the study in training like in UXO

**Pratyaksh Singh:** Yeah. In training edit. In training you can add it.

**Sachin Pandey:** plus.

**Pratyaksh Singh:** I think you should do it that you know you can you can change

**Sachin Pandey:** So

**Pratyaksh Singh:** the you can rotate the object you can scale it and do all those things. You should do it.

**Sachin Pandey:** Okay.

**Geoff Horowitz:** Okay, guys. Unless there's anything else you want to bring up. I sent out a meeting for uh 40 minutes or so from now.

### **00:53:19**

**Geoff Horowitz:** Can reconvene then.

**Sachin Pandey:** Okay.

**Geoff Horowitz:** Okay guys, I'll talk to you later.

### **Transcription ended after 01:10:02**

*This editable transcript was computer generated and might contain errors. People can also change the text after it was created.*