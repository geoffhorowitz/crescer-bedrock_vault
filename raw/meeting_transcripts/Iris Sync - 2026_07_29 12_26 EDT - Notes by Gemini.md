# **📝 Notes**

Jul 29, 2026

## **Iris Sync**

Invited [Sachin Pandey](mailto:sachin@crescer.ai) [Pratyaksh Singh](mailto:pratyaksh@crescer.ai) [Hemanth Sarabu](mailto:hemanth@crescer.ai) [Geoff Horowitz](mailto:geoff@crescer.ai) [Ratul Shashank](mailto:ratul@crescer.ai)

Attachments [Iris Sync](https://calendar.google.com/calendar/event?eid=NnNzMHVxNzk3MmJqZGVwNXFoN2J1Mjd1OTdfMjAyNjA3MjlUMTYzMDAwWiBnZW9mZkBjcmVzY2VyLmFp)

Meeting records [Transcript](https://docs.google.com/document/d/1yXHPlHAGEiuUzoijN7FOETPj2LR29I0J4B_RITFY-fI/edit?usp=drive_web&tab=t.iy6af5u9umdn) [Recording](https://drive.google.com/file/d/1rHlHvBVERkmPHGyN2pAHmXci8igptA1Z/view?usp=drive_web) 

### **Summary**

Technical discussions explored V4 model improvements and diffusion model synthetic data generation strategies.

**V4 Model Optimization Strategies**  
The team refined false positive reduction strategies using focal dice loss functions and decided to standardize K-fold data splits across model recipes. Prioritizing low false negatives for UXOs remains the primary performance objective.

**Diffusion Model Data Synthesis**  
Participants established a workflow for using diffusion models to generate synthetic training data while preventing data leakage. They agreed to implement inpainting techniques to integrate objects into backgrounds for improved model robustness.

**Image Transformation and Blending**  
The team finalized methods for object blending using image domain transformations like Poisson copy-paste and shadow augmentation. Technical standards for patch sizes and directory structures were confirmed to streamline dataset management.

### **Decisions**

## Aligned

* **Screen recording enabled for meetings** Screen recordings are enabled for all meetings in the current series to improve documentation capabilities.

* **Kfold validation methodology standardized** The team adopted a standardized Kfold validation methodology, utilizing consistent data splits across all models to ensure accurate performance comparisons.

* **Image domain augmentation adopted** The team chooses to utilize image domain augmentation, such as poison copy paste, to handle object placement and robust transformations during training instead of relying on XTF domain operations.

* **Mean pixel calculation chosen for blending** The team decides to calculate the mean of pixel values when overlapping or blending images to prevent overflow issues associated with summing pixels.

We've **updated the Decisions section** using your feedback.

Let us know what you think: [Helpful](https://google.qualtrics.com/jfe/form/SV_5bXzKQfylMIhSXc?isHelpful=True&entryPoint=decisions&confid=W33tc7BIp8ZxkFqU1HV1DxIUOBEBMgUIigIgABgBCA&isGoogler=False) or [Not Helpful](https://google.qualtrics.com/jfe/form/SV_5bXzKQfylMIhSXc?isHelpful=False&entryPoint=decisions&confid=W33tc7BIp8ZxkFqU1HV1DxIUOBEBMgUIigIgABgBCA&isGoogler=False)

### **Next steps**

- [ ] \[Geoff Horowitz\] Add Screen Recordings: Include video captures for all meetings in the series.

- [ ] \[Sachin Pandey\] Update Report: Refine the V4 results report to ensure the narrative matches the presented metrics and data.

- [ ] \[Sachin Pandey\] Ping Geoff: Notify the team once the documentation updates are finalized.

- [ ] \[Pratyaksh Singh\] Share Link: Distribute the access link for the diffusion model examples to the team via Slack.

- [ ] \[Pratyaksh Singh\] Train New Model: Create a model using a clean split to prevent data leakage during evaluation.

- [ ] \[Ratul Shashank\] Share Examples: Upload before and after images of the object scaling to Slack to allow for further review of the blending issue.

- [ ] \[Pratyaksh Singh\] Share Decomposition: Post the images of the EMD decomposition results on Slack for the team to evaluate.

- [ ] \[Ratul Shashank\] Research Augmentations: Investigate the implementation of image domain augmentation techniques to improve object blending.

### **Details**

* **Meeting Recording and Scheduling**: Geoff Horowitz and Sachin Pandey discuss recording settings for future meetings, and Geoff agrees to add screen recording to the meeting series. During this conversation, it is identified that Sachin has encountered issues with the meeting calendar; Geoff removes and re-adds Sachin to the meeting invite to resolve the access problems ([00:01:36](#00:01:36)).

* **V4 Model False Positive Reduction**: Sachin Pandey details the implementation of a new loss function in the V4 model to address false positives. Sachin reports that false positives dropped significantly, with UXO results at 12, AOI big at 83, and black patch at 179 ([00:05:41](#00:05:41)). While recall saw an 8% hit for the AOI big class, it improved for other classes. Pratyaksh Singh questions the stability of using the "focal dice" loss function alone and suggests verifying if it should be paired with binary cross entropy, while Hemanth Sarabu suggests the ML intern may have provided a successful solution ([00:07:44](#00:07:44)).

* **K-Fold Model Evaluation Methodology**: Sachin Pandey presents k-fold results using synthetic data generated by Ratul Shashank to compare models. Hemanth Sarabu critiques the comparison method, noting that relying on different train and validation splits makes it difficult to compare models directly ([00:13:32](#00:13:32)).

* **Comparison Strategy for Models**: Hemanth Sarabu suggests keeping k-fold data splits consistent across different model recipes to allow for direct F1, precision, and recall comparisons, rather than relying on an average score ([00:22:50](#00:22:50)). To better evaluate different models, Hemanth suggests running multiple models using these consistent k-fold splits. Sachin Pandey confirms that parallel processing across available GPUs would make this approach feasible ([00:27:17](#00:27:17)). They emphasize the need to prioritize low false negatives for UXOs, even if false positives remain relatively high ([00:28:16](#00:28:16)).

* **Merging Classes and Performance**: Sachin Pandey and Geoff Horowitz discuss the decision to merge UXO and AOI small black classes, which increased true positives from 3 to 23 ([00:29:32](#00:29:32)). Geoff expresses concern regarding the recall metrics after the merge, noting that the reported recall appears lower than the baseline ([00:33:22](#00:33:22)). Geoff tasks Sachin with updating the report to provide better clarity and context regarding these results ([00:34:52](#00:34:52)).

* **Diffusion Model Data Generation**: Pratyaksh Singh discusses using a trained diffusion model to generate synthetic training data but expresses concern regarding potential data leakage if trained on all bedrock data ([00:37:12](#00:37:12)). Pratyaksh proposes a new experiment: splitting the data so that no real objects are in the training set for the diffusion model, then generating backgrounds and using an external model to place objects ([00:39:14](#00:39:14)). They also discuss leveraging external tools like ChatGPT or procedural generation to create the objects ([00:44:59](#00:44:59)).

* **Diffusion Model Refinement Techniques**: Hemanth Sarabu suggests an inpainting-like technique to integrate objects into generated backgrounds. The process involves generating a background, pasting an object, adding slight noise to the latent space, and using the diffusion model for a few steps to bring the object into the distribution ([00:47:13](#00:47:13)). Pratyaksh Singh agrees to train another model following these guidelines ([00:50:03](#00:50:03)).

* **Ratul Shashank's Object Augmentation Experiment**: Ratul Shashank presents an experiment on modifying raw data to create new object variations, specifically focusing on changing height and length ([00:51:50](#00:51:50)). The methodology involves isolating the object by subtracting the median intensity of the background ([00:54:47](#00:54:47)). Hemanth Sarabu describes this as a clever approach and notes that it is a promising idea for generating novelty in the data ([00:57:50](#00:57:50)).

* **Gradient Matching and Scaling Adjustments**: Ratul Shashank reported an issue with a gradient mismatch when placing objects as overlays, which they attempted to address by implementing an extra function for gradient matching. Ratul Shashank also noted that they are currently increasing the height of the AI small black by 1.3 times ([00:58:51](#00:58:51)). Hemanth Sarabu requested that Ratul Shashank share "before and after" examples on Slack to provide a clearer demonstration of the progress ([01:00:05](#01:00:05)).

* **ENTx Dataset Scaling Discrepancy**: A problem was identified regarding the scaling of objects when transferred between datasets, specifically when cropping an object from the VW dataset to place on the ENTx background. Ratul Shashank explained that because the ENTx sample size is significantly smaller than the VW dataset, the metric values cause the objects to appear "exceptionally large" when pasted ([01:00:05](#01:00:05)). Hemanth Sarabu advised that regardless of the scale, the object must be made to blend into the background effectively ([01:02:52](#01:02:52)).

* **Image Domain Transformations and Blending**: Pratyaksh Singh recommended utilizing the image domain rather than alternative transformation methods to achieve better results ([01:02:52](#01:02:52)). Pratyaksh Singh suggested using Poisson copy-paste techniques, as provided by OpenCV, which utilize gradients to help objects blend seamlessly into the background. They emphasized that working in the image domain allows for real-time augmentation, such as resizing, rotating, and adjusting brightness or contrast during training, rather than relying on static images ([01:04:50](#01:04:50)).

* **Rotation and Augmentation Testing**: Pratyaksh Singh guided Ratul Shashank through an online resource to test various augmentation techniques, including rotation and scaling ([01:07:03](#01:07:03)). Pratyaksh Singh confirmed that when applying rotations, the system correctly tracks the coordinates of bounding boxes, such as eyes and body parts, ensuring they rotate in alignment with the object ([01:08:09](#01:08:09)). Ratul Shashank confirmed they are currently using rotation matrices involving sine and cosine values to achieve these transformations ([01:05:55](#01:05:55)).

* **Merging and Overlapping Pixel Logic**: The team discussed the methodology for merging overlapping image areas ([01:09:20](#01:09:20)). Ratul Shashank proposed adding the values of overlapping dark areas, but Pratyaksh Singh cautioned that summing pixel values (e.g., 255 \+ 255\) would lead to overflow errors. Pratyaksh Singh recommended calculating the mean of the overlapping pixels instead to ensure the output remains within valid ranges ([01:10:36](#01:10:36)).

* **Shadow Augmentation Strategy**: Pratyaksh Singh suggested that shadow directions should be included as part of the augmentation process to help the model learn more robust features. They explained that by providing a high volume of varied examples, including different shadow directions, the model can become more effective. Ratul Shashank considered using these examples to create a Low-Rank Adaptation (LoRA) on an existing stable diffusion model ([01:11:40](#01:11:40)).

* **Data Structure and Dataset Management**: The team concluded the meeting by discussing the technical organization of the data, specifically regarding directory structures, dataset splitting, and image patch sizes for the VW and ENTx datasets ([01:18:08](#01:18:08)). They verified the use of 128 by 128 or 256 by 256 pixel patch sizes and discussed the process of saving masks as PNG files ([01:22:09](#01:22:09)). The participants confirmed the validation and training folder structures needed to support the project workflow ([01:27:50](#01:27:50)).

*You should review Gemini's notes to make sure they're accurate. [Get tips and learn how Gemini takes notes](https://support.google.com/meet/answer/14754931)*

*How is the quality of **these specific notes?** [Take a short survey](https://google.qualtrics.com/jfe/form/SV_5bXzKQfylMIhSXc?confid=W33tc7BIp8ZxkFqU1HV1DxIUOBEBMgUIigIgABgBCA&detailLevel=standard&hasImages=False&entryPoint=footerMain&isGoogler=False) to let us know your feedback, including how helpful the notes were for your needs.*

# **📖 Transcript**

Jul 29, 2026

## **Iris Sync \- Transcript**

### **00:00:21**

**Sachin Pandey:** Hi Jeff.

**Geoff Horowitz:** what the resolution was. Did we Did we want to record all these meeting? Did you want us to record all these meetings or not like with video?

**Sachin Pandey:** Uh I don't know like if we can we delete the recording afterwards once we got all the things

**Geoff Horowitz:** What do you

**Sachin Pandey:** like so like a agent can go through the like

**Geoff Horowitz:** mean?

**Sachin Pandey:** not go through the recording but it can use the transcript to find the area and like capture the frame and then put it in the notes. But also one more thing is like how well the like transcribe is working because I use uh like text speech to text and it it makes a lot of mistake and not able to like get

**Geoff Horowitz:** Wait, wait, let me let me back up a second.

**Sachin Pandey:** the

**Geoff Horowitz:** We We transcribe all of these meetings. All these meetings get transcribed automatically.

**Sachin Pandey:** but like uh

**Geoff Horowitz:** What what I'm asking about is like screen

**Sachin Pandey:** So screen recording will

### **00:01:36** {#00:01:36}

**Geoff Horowitz:** recording.

**Sachin Pandey:** be helpful like if we can use it somehow in the like with the transcript and once once we done like we can delete

**Geoff Horowitz:** Okay, I will add screen I'll add screen recordings to all these

**Sachin Pandey:** it.

**Geoff Horowitz:** then.

**Sachin Pandey:** Okay.

**Geoff Horowitz:** Okay. But how do I do it?

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** Also, you said you're not attending any of these meetings.

**Sachin Pandey:** H

**Geoff Horowitz:** You said no to this meeting series.

**Sachin Pandey:** uh wait is I think that's the reason why like in the section where the meeting should pop up this doesn't appear.

**Geoff Horowitz:** Yeah.

**Sachin Pandey:** I just have bookmarked the meeting link and I just log in through that.

**Geoff Horowitz:** Oh, you said no to

**Sachin Pandey:** Uh I I don't remember saying no to it.

**Geoff Horowitz:** it.

**Sachin Pandey:** uh updated rock this anyway

**Geoff Horowitz:** Manage settings. Take record the meeting.

**Sachin Pandey:** anyway to fix

**Ratul Shashank:** Hey guys.

**Geoff Horowitz:** Uh,

**Sachin Pandey:** it.

**Geoff Horowitz:** say this event and follow Okay. Send. Did you just get a new check your email.

### **00:02:59**

**Geoff Horowitz:** Did you just get a new meeting?

**Sachin Pandey:** Uh,

**Geoff Horowitz:** No.

**Sachin Pandey:** no.

**Geoff Horowitz:** Okay, I'm going to remove you and then add you again. Okay.

**Sachin Pandey:** Okay. Okay,

**Geoff Horowitz:** And do it.

**Sachin Pandey:** I got it.

**Geoff Horowitz:** Oh, you got it now.

**Sachin Pandey:** Yeah. Uh,

**Geoff Horowitz:** Can you say yes to it?

**Sachin Pandey:** yes.

**Geoff Horowitz:** All right. Fine.

**Sachin Pandey:** Then

**Geoff Horowitz:** Okay, there you go.

**Sachin Pandey:** you Hi, Adam.

**Ratul Shashank:** Hey face.

**Sachin Pandey:** Jeff about your question for weight penalty like because we are facing issues with lot of false positive.

**Geoff Horowitz:** Uh

**Sachin Pandey:** So like this uh the change was suggested

**Hemanth Sarabu:** Let's

**Sachin Pandey:** by ML intern to like try like this can fix the like the false positive rate.

**Geoff Horowitz:** okay. Is it implemented?

**Sachin Pandey:** Yeah, in V4 it's

**Geoff Horowitz:** implemented in

**Hemanth Sarabu:** go.

**Sachin Pandey:** implemented.

**Geoff Horowitz:** V4. Um, and what were the results there?

**Sachin Pandey:** The first part are like very low.

### **00:05:41** {#00:05:41}

**Sachin Pandey:** We are not like earlier we were like in 1,00

**Hemanth Sarabu:** Sorry. Can I be uh can can I can you catch me up real

**Sachin Pandey:** to,500. Amen.

**Hemanth Sarabu:** quick?

**Geoff Horowitz:** Um, we had brought up this thread of um implementing a false positive penalty waiting because of the class imbalance for UXOs.

**Hemanth Sarabu:** Okay,

**Geoff Horowitz:** Um and I was asking Satchin what the where we are on that.

**Hemanth Sarabu:** I see.

**Geoff Horowitz:** So he was filling us in and telling us where we are. Sergeant

**Sachin Pandey:** Yeah, like we we change we it's already implemented in the V4 that's why like it is not predicting as much false positive like even for UX. So uh let me add the matrix positive. So even for years the false positive rate has declined like it's like 10 false positives wait uh

**Geoff Horowitz:** So, are you are you trying to share

**Sachin Pandey:** No, I'm I'm just finding the section in the you know

**Geoff Horowitz:** thing.

**Sachin Pandey:** report. Yeah, for for V4 the false party for USO were dropped to 12 and for AOI big

### **00:07:44** {#00:07:44}

**Geoff Horowitz:** Wow.

**Sachin Pandey:** like 83 for black patch 179\. So it's like in the range of 200 in total their range of 200 but earlier it were in like 1100 or 1500 range. We were predicting a lot of false positive. So that has like uh reduced that's why the precision has increased in general.

**Hemanth Sarabu:** Have we taken a hit on recall?

**Sachin Pandey:** Uh no recall has also increased for

**Hemanth Sarabu:** Oh.

**Sachin Pandey:** AI big there is a hit for about like 8%. But in in other classes uh the recall has also

**Hemanth Sarabu:** What what was this?

**Sachin Pandey:** improved.

**Hemanth Sarabu:** What was this trick to improve uh precision? What was it?

**Sachin Pandey:** Uh it was the change the the loss function was changed to to like key loss. There it is. Uh the global t was sky loss. I hope I'm pronouncing it

**Pratyaksh Singh:** focal towards you

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** right

**Sachin Pandey:** right.

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** Sachin is this with the color augmentation that we discussed

**Sachin Pandey:** No, this was this was for the V4.

### **00:09:20**

**Sachin Pandey:** Uh we haven't Yeah,

**Pratyaksh Singh:** Okay, this is only with this is only with change and loss function,

**Sachin Pandey:** this was for the old model.

**Pratyaksh Singh:** right? All

**Sachin Pandey:** Yes.

**Pratyaksh Singh:** right.

**Hemanth Sarabu:** That's good. What was the last function to pull?

**Sachin Pandey:** It was focal dice.

**Pratyaksh Singh:** Is it like with only with diversity loss or is it combination of two loss?

**Sachin Pandey:** Only with this loss key

**Pratyaksh Singh:** Wow.

**Sachin Pandey:** loss.

**Pratyaksh Singh:** We use this loss for iris but from what I have read it's like it is unstable. It is it's usually unstable on its own. So people use it with binary cross entropy global tok should

**Hemanth Sarabu:** I see.

**Pratyaksh Singh:** it be such an it should be focal to

**Sachin Pandey:** Where?

**Pratyaksh Singh:** it focal I think it should be focal towards global global tourist

**Hemanth Sarabu:** Maybe uh maybe ML intern came up with a good

**Pratyaksh Singh:** maybe. Yeah,

**Hemanth Sarabu:** idea.

**Pratyaksh Singh:** that's why that's why like I want to confirm it.

**Sachin Pandey:** Okay.

### **00:11:07**

**Pratyaksh Singh:** It's just a did it modify the loss or it just you

**Geoff Horowitz:** Ready?

**Pratyaksh Singh:** know

**Hemanth Sarabu:** That would be I would be surprised if it invented a

**Pratyaksh Singh:** sorry it got invented a

**Sachin Pandey:** Thank you.

**Hemanth Sarabu:** loss.

**Pratyaksh Singh:** lot

**Sachin Pandey:** No, like these are two different kind of laws.

**Pratyaksh Singh:** local and global.

**Sachin Pandey:** Yeah.

**Pratyaksh Singh:** Can I show like Wait. priority rep. Okay.

**Geoff Horowitz:** Such an I'm looking at the latest your latest update the kfold model is this kffold plus cut and paste data.

**Sachin Pandey:** uh like I ran experiment like with the Kboard model like the the data split I showed in the last meeting.

**Geoff Horowitz:** Uh-huh.

**Sachin Pandey:** This was uh like so to like to test out the model like to

**Geoff Horowitz:** All

**Sachin Pandey:** give uh like appletole comparison I used the the synthetic data generated by ratul like with the cutbase method because it was not in either of the training set like maybe the like the main objects were there but it will be little different than the training set.

### **00:13:32** {#00:13:32}

**Sachin Pandey:** So it can give us like balance idea about like which model is doing better. And these are the like the results

**Geoff Horowitz:** right. I I'm not following Sachin because if you if you did kfold and cut and paste

**Sachin Pandey:** from

**Geoff Horowitz:** then you might have taken some of the validation samples and put them in the training set, right?

**Sachin Pandey:** Yeah, let uh let me show it to you. So these results are generated uh on a different data set like uh like even uh Rul generated these with using like cut and paste method. So it is not exactly same as which was in the training or in the validation. It is like little different.

**Hemanth Sarabu:** You I'm seeing what what are you guys seeing? I'm seeing uh Google Meet.

**Sachin Pandey:** Is it visible

**Geoff Horowitz:** I still see Google

**Sachin Pandey:** now?

**Pratyaksh Singh:** You didn't

**Hemanth Sarabu:** Yeah. Don't come in

**Geoff Horowitz:** Meet.

**Pratyaksh Singh:** know

**Hemanth Sarabu:** here.

**Geoff Horowitz:** Now I see the running notes.

**Hemanth Sarabu:** Yeah.

### **00:15:07**

**Sachin Pandey:** Okay, now it's so yeah like because all of the like there was no like I can't pick any files from the from the training data cuz like if it was not included in this it would be in any of the other files. But that's why I use like a different set of files and these are like the prediction on those files.

**Hemanth Sarabu:** What is your What is your What is your K?

**Sachin Pandey:** Take us five

**Hemanth Sarabu:** Uh, sorry. I guess different. Oh, okay. Five five. So you're cycling through 20%. Validation,

**Sachin Pandey:** uh roughly like because it's hard to like exactly match the number because we are doing a top on cropping.

**Hemanth Sarabu:** right?

**Sachin Pandey:** So if one reason has a lot of overlap,

**Hemanth Sarabu:** Right.

**Sachin Pandey:** the file will like generally increase. So like roughly 80 to 80

**Hemanth Sarabu:** I see. So, sorry.

**Sachin Pandey:** 20%.

**Hemanth Sarabu:** Can you What are you saying about K4? Actually, how long did fivefold take you to run?

### **00:16:51**

**Sachin Pandey:** Around one day

**Hemanth Sarabu:** One day. Okay, that's not bad.

**Sachin Pandey:** This is just to get an idea like how the like model are

**Hemanth Sarabu:** Yeah.

**Sachin Pandey:** performing

**Hemanth Sarabu:** Yeah, that makes sense.

**Sachin Pandey:** and because the data was not in like not part of the training or well so like it was a better way to judge the that two different

**Hemanth Sarabu:** These are okay.

**Sachin Pandey:** models.

**Hemanth Sarabu:** And so how so a couple of questions can we actually keep the so you have 4 zero 41 and so on right the the data sets that were used can

**Geoff Horowitz:** Ouch.

**Sachin Pandey:** Yeah.

**Hemanth Sarabu:** you keep them constant across experiments meaning okay what I mean by that is you have you're testing a model uh actually let's say V4 model V4 model has certain recipe, right? Cut, paste, copy, paste, whatever.

**Sachin Pandey:** Yeah.

**Hemanth Sarabu:** But maybe there's value in and let's say you have a new recipe as well. Okay. Uh heavy augmentations. I'm just making it up. Two two different models, but you can run that on the same folds.

### **00:18:23**

**Hemanth Sarabu:** Sure. You get what I mean?

**Sachin Pandey:** like this recipe with like these models.

**Hemanth Sarabu:** So each fold is each fold is actually a data set samples sample, right? Basically a split a train val split, right? That's the main difference.

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** And but you actually run the same training uh

**Sachin Pandey:** Yeah.

**Hemanth Sarabu:** recipe, right?

**Sachin Pandey:** Yeah.

**Hemanth Sarabu:** So I'm wondering if um if we wanted to compare two models, we actually um basically use the same data sets. The data set splits you got in 0 1 2 3 4\. So,

**Sachin Pandey:** Yeah, this was the like the split is not balanced like if you see like how many images were like like it was divided by area but like because of the overlap some region have like high images some I think I generated a matrix yeah I will generate a matrix for each with their respective uh validation

**Geoff Horowitz:** question. I think you had a visual of it too,

**Hemanth Sarabu:** Okay,

**Geoff Horowitz:** like a map you shared in the last

### **00:20:14**

**Hemanth Sarabu:** the respective validation set.

**Geoff Horowitz:** meeting.

**Sachin Pandey:** Yeah.

**Hemanth Sarabu:** So I mean it must it it you basically should have trained using those fold folds, right? Say you have a new model but you trained on 18020\.

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** You cannot you cannot do predictions on the zero validation set one validation set. You can't compare them because that model might have seen those validation samples

**Sachin Pandey:** Yeah, that's why I I used like a completely different files which were not part of the even the training or or the

**Hemanth Sarabu:** training.

**Geoff Horowitz:** H.

**Sachin Pandey:** valu validation like these are somewhat synthetic like we like cut paste uh like not normal crop and paste but

**Geoff Horowitz:** Okay.

**Sachin Pandey:** like blend it. Do you have some examples which we can

**Hemanth Sarabu:** can you can you explain the methodology?

**Sachin Pandey:** show?

**Hemanth Sarabu:** I think I'm lost. I mean uh what what is this there? So you you're doing train val split and there's a test set like a separate test set.

**Sachin Pandey:** uh like this like this data was uh let me just this data was mainly like the argumentation or like try to replicate the UXO like putting it into multiple files or multiple backgrounds.

### **00:21:40**

**Sachin Pandey:** uh like there were 33 UXO which like Ratul created and I was using that because it was not included in any of the data like the object no I it's

**Hemanth Sarabu:** You were using that as what?

**Sachin Pandey:** just for like getting the idea like because these are like for kfold the validation set were like split and there is no easy way to compare like compare these all the models so like using

**Hemanth Sarabu:** There is there is I mean the way to do that is basically

**Sachin Pandey:** the data

**Hemanth Sarabu:** For each four you you've done five fours for some model, right? You do five four for another model, but you need to keep the fours the

**Sachin Pandey:** Yeah.

**Hemanth Sarabu:** same, but you Yeah. You're saying that you have a synthetically generated test data set, right? That is sub.

**Sachin Pandey:** Yeah, mainly for

**Hemanth Sarabu:** Yes. Yeah. You that is al that is also good. You can do that too. But I would be pretty interested in seeing how once you you've

**Sachin Pandey:** UXO.

### **00:22:50** {#00:22:50}

**Hemanth Sarabu:** created these five holes, how do they compare? We can do both.

**Sachin Pandey:** like running each fold on their own validation set and averaging out the like score like FM

**Hemanth Sarabu:** Uh so one thing you could do

**Sachin Pandey:** score.

**Hemanth Sarabu:** is you have this table, right? Imagine now you have this same like a copy of this table to the right. Basically you're adding columns for a second model and then you're adding columns for a third model. You follow?

**Sachin Pandey:** Uh little bit.

**Hemanth Sarabu:** Okay. So,

**Sachin Pandey:** So like uh each fold is each model,

**Hemanth Sarabu:** such an you.

**Sachin Pandey:** right?

**Hemanth Sarabu:** Yeah. Yeah. Okay. Hold on. Hold on. Let me let me share my screen.

**Sachin Pandey:** What?

**Hemanth Sarabu:** So you have actually going to struggle to type on this but so you have the F1 score for one M. What's going on? Give me one second, guys. Okay. So you have fold zero 1 2 3 4 right.

### **00:25:09**

**Hemanth Sarabu:** The main difference is how the train val are split. Correct. That is the main difference.

**Sachin Pandey:** Yeah.

**Hemanth Sarabu:** Okay. Now you have model one, model two and so on. For each one you can take this fold train predict on val compute metrics F1 precision recall. Right? You can do the same here here. Right? And you can do the same here here. Now you can com you can compare the F1 precision recall between these two models for each of these for each of these folds. Now there is a there'll be good cases and there will be bad cases. The good case uh as in like the the helpful case will be model 2 is generally better than model one in all these folds and that is a very strong signal that model 2 is actually better or you'll see that model 2 is it is very confusing some places model one is better some places model 2 is better and that is actually a signal for us that is telling us that there's it's unclear which model is better maybe some places we'll see model 2 is a majority improvement over model one.

### **00:26:30**

**Hemanth Sarabu:** Maybe that is also useful for us. So we don't have to average across all of this. We can if we want, but we can also present them line by line. You know, think of these as when we were doing iris stuff. Model one is good in in the shore area and model 2 is better in the

**Sachin Pandey:** Yeah.

**Hemanth Sarabu:** offshore area. Right? Think of it like that. It's not exactly like that, but you know, think of it like that. So we don't actually you don't have to average.

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** You don't need to reduce these numbers to a single number. You can compare them and that will tell us a

**Sachin Pandey:** Yeah,

**Hemanth Sarabu:** lot.

**Sachin Pandey:** I get it. Like this is the case when we like we have two models uh trained on like Kfold but like V4 is only V4 is not like V4 is a normal model which is like single

**Hemanth Sarabu:** Correct.

**Sachin Pandey:** 8020 which we like selected the validation set we have selected and

### **00:27:17** {#00:27:17}

**Hemanth Sarabu:** Right. Right.

**Sachin Pandey:** the other one is K4.

**Hemanth Sarabu:** Right. In that case we cannot do that.

**Sachin Pandey:** So

**Hemanth Sarabu:** Then the only op option is to do what you're saying which is this where there is this like separate held out set.

**Sachin Pandey:** a new files.

**Hemanth Sarabu:** Yeah, you tested on that. But my point is,

**Sachin Pandey:** Yeah.

**Hemanth Sarabu:** um, if you're if you're doing K4,

**Sachin Pandey:** Yeah.

**Hemanth Sarabu:** might as

**Sachin Pandey:** Like if we have another Yeah.

**Hemanth Sarabu:** well,

**Sachin Pandey:** If you want to test another another like loss or something in the kfold, we can use this metrics to like get an idea how the models are performing.

**Hemanth Sarabu:** right? And you can also rerun V4 K4 style.

**Sachin Pandey:** Yeah.

**Hemanth Sarabu:** Shouldn't take long, right? We have five, six GPUs.

**Sachin Pandey:** Yes. If you run in parallel,

**Hemanth Sarabu:** Well, then we should just do

**Sachin Pandey:** it will be faster.

**Hemanth Sarabu:** that.

**Sachin Pandey:** Okay.

**Hemanth Sarabu:** So, I I don't actually know what what will end up happening.

### **00:28:16** {#00:28:16}

**Hemanth Sarabu:** But if we see that one model is better than all the other models, that that is usually a strong signal. Then we don't have to like worry about worry about things purely because we don't have a lot of data. But you you the having the synthetic held out data set approach is also good.

**Sachin Pandey:** Yeah, like mainly ideally we want to see how well it's doing on UXO. So we we want uh like low false negative as well as false positive like even relatively false positive higher it we are okay but false negative should be

**Hemanth Sarabu:** Yeah. Right.

**Sachin Pandey:** minimum

**Hemanth Sarabu:** Okay. So, where where are we then?

**Sachin Pandey:** like some of the folds are giving better result like in B4 normal B4 the first negative are like 10 and false positive are 32\. And closest is will be the fold three where uh the false negative is 9 and false positive is 33 like almost same.

**Hemanth Sarabu:** Okay. So again this scold uh yeah I mean on its own I don't

### **00:29:32** {#00:29:32}

**Sachin Pandey:** And

**Hemanth Sarabu:** know how much we can do like we it we should really be be comparing multiple multiple like models using kfold.

**Sachin Pandey:** multiple Yeah. Okay. So this one has the highest F1 score, but because of high like we will like not be choosing this one is the closest to the like for model but this is also better but the false positive are much higher

**Hemanth Sarabu:** Okay. Okay.

**Geoff Horowitz:** So, what is that next point about? Uh, when you merge the classes, performance went down.

**Sachin Pandey:** And we merge the classes. Uh where

**Geoff Horowitz:** Um, that he said merging US

**Sachin Pandey:** uh where uh where did we the UXO and AI small black?

**Geoff Horowitz:** That's what That's what you put in this in this report here. Merging

**Sachin Pandey:** Yeah. So like so the ground truth which like the synthe data ground truth was all

**Geoff Horowitz:** UXO

**Sachin Pandey:** the classes all the objects were in UX uh a small black class and model was predicting them as UXO so that's why we like we merge both the classes into a single class we can just get an object to object idea

### **00:31:28**

**Geoff Horowitz:** Right. So the results looked tell me about the results.

**Sachin Pandey:** So true positive like so the above one where we were using the ground root as it is and not converting the prediction UXO to AI small black the true positive were only three like rest 20 were predicted as UX but it was not matched so it got rejected but once we start matching the politive were like goes to 23\. Is this what we are asking for?

**Geoff Horowitz:** Are you saying Yeah. Are you saying that before we merged these we were getting like a 9% recall on AOI small

**Sachin Pandey:** So model so issue with this was the ground truth were like all the class all the objects in

**Geoff Horowitz:** black

**Sachin Pandey:** the ground truth were classified as uh a small model and model was predicting those object as uxo. So in the first case because the like classes were not matching that's why we were getting like low recalls and See you then.

**Geoff Horowitz:** It looks to me like we're doing worse on this UXO class here.

### **00:33:22** {#00:33:22}

**Geoff Horowitz:** Is that correct?

**Sachin Pandey:** Uh I don't get your question uh how we are

**Geoff Horowitz:** Okay.

**Sachin Pandey:** doing worst.

**Geoff Horowitz:** Ready. Okay. I I actually need to drop in a second, but let me show this briefly. So before before we were getting like

**Sachin Pandey:** Okay.

**Geoff Horowitz:** 80% recall on the UXO class and 70% on AOI small black, right?

**Sachin Pandey:** Wait, I was looking at a different matrix. I thought you were like talking about the like V4 in the synthetic

**Geoff Horowitz:** So now you're now you're showing that if we only had a the way I read this,

**Sachin Pandey:** data.

**Geoff Horowitz:** if we only had AI small black alone, we would have 9% recall. And when we combine these two together, we have 70% recall. Both of these to me look worse than kind of our baseline.

**Sachin Pandey:** Okay.

**Geoff Horowitz:** Does my question make sense now?

**Sachin Pandey:** Yeah. So is 80% and 50 recall.

**Geoff Horowitz:** question.

**Sachin Pandey:** Okay. Yeah. Yeah, it makes sense now.

### **00:34:52** {#00:34:52}

**Geoff Horowitz:** Okay. So, so I actually do need to drop, but um Sachin, can you just update this update this this whole update this whole update that you added here to to give more guidance, more like use the same approach that we've been looking at, you know, add the report like what what is going on here, right? I think I'm guessing that this is not the story you're trying to tell, but that's the story I'm reading. Does that make sense? Okay. So, update this. Ping me when it's done.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** I'll ask you. I'll review it and ask some questions later. Um, he do you have time to stay on and talk about the uh follow up with

**Hemanth Sarabu:** Yeah, I have a few

**Geoff Horowitz:** project? Okay.

**Hemanth Sarabu:** minutes.

**Sachin Pandey:** It's fine.

**Geoff Horowitz:** Okay. All right. I will uh I'll review the recording after. Thanks, guys.

**Hemanth Sarabu:** Okay, the extra

**Pratyaksh Singh:** Yeah, I think Rahul has some interesting update but I just want to take few

### **00:36:05**

**Hemanth Sarabu:** take

**Pratyaksh Singh:** minutes to discuss something. Let me share my screen. So for synthetic data generation I tried the the EMD algorithm that you told about but you know it it was able to break it down into I think just six images which was much better but I didn't know how to use it to generate synthetic data.

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** Meanwhile,

**Hemanth Sarabu:** Okay. I'm just seeing Google Meet,

**Pratyaksh Singh:** uh yeah,

**Hemanth Sarabu:** by the way.

**Pratyaksh Singh:** I'm just giving short updates and then I I have to ask some question.

**Hemanth Sarabu:** Yes,

**Pratyaksh Singh:** I'll shift to it.

**Hemanth Sarabu:** that's good.

**Pratyaksh Singh:** Uh open source data for open source data, I think we can't use it as it is because the data that we collected has a lot of coral reef in them. So we might we will have to either filter that out or we will have to label them for the training data. And again it looks a little bit out of distribution.

**Hemanth Sarabu:** See?

**Pratyaksh Singh:** So uh one thing that I was thinking is the diffusion model that we trained.

### **00:37:12** {#00:37:12}

**Pratyaksh Singh:** Can you can you see another browser with examples? Yeah.

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** So the diffusion model that we trained can we use it to generate examples generate synthetic examples and then while we are doing other things give it to labelers to maybe kind of label label or just verify that the images look good.

**Hemanth Sarabu:** Sounds

**Pratyaksh Singh:** So for example this is okay now the question that I have I will I'll

**Hemanth Sarabu:** good.

**Pratyaksh Singh:** share this link with you guys so that if you guys want you can play around with it too.

**Hemanth Sarabu:** Yeah. Can you put this on

**Pratyaksh Singh:** uh the yeah I'll I'll put it I'll put it in a minute.

**Hemanth Sarabu:** Slack?

**Pratyaksh Singh:** Now the question that I have is that I trained the model on the whole data. This uh this diffusion model I trained it on the whole data and what I'm planning to

**Hemanth Sarabu:** the whole bedrock data.

**Pratyaksh Singh:** do is I want to the whole all of the bedro data not

**Hemanth Sarabu:** All of the bedrock data.

**Pratyaksh Singh:** test like it was trained on the whole data.

### **00:38:05**

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** Now what I'm thinking is that the classification model I will use the synthetically. So there are few caveats here. First we are limited by image size. So it's only it can only generate 128 \+ 128 images right so that's why like such what is the image size that you used if you can answer that too but this I think there is this limit here on the image size and then another thing is that uh I used the whole data right so I was wondering if we use the synthetic data the synthetic data that we use sorry the data generated by diffusion model to train our classification model can we

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** evaluate it on can we evaluate it on the bedrock data or do you think it will be called as you know data leakage.

**Hemanth Sarabu:** Yeah, I that that feels like data leakage right

**Pratyaksh Singh:** Okay. Okay. So, what I

**Hemanth Sarabu:** um so here protect so the question is uh I

**Pratyaksh Singh:** think

**Hemanth Sarabu:** think you want to maybe reframe that that experiment and the reframing could be something like I will I will do a good split when I say good split it's not like by

### **00:39:14** {#00:39:14}

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** area it is by examples or variety something like that I'll do a proper split

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** of 7525 of the original data. I will train the diffusion model on the 75% and I will get the I will get uh

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** I'll get whatever I'll make it generate a lot of training data for the classifier. Classifier gets trained on that and then you evaluate on the remaining 25% that the diffusion model has not

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** seen and your classifier has not seen.

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** I think that feels more that that can test your hypothesis because there is a there is a held out data set there right um there's that

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** now I actually but you know like I I don't know what will work what won't work we just have to

**Pratyaksh Singh:** Okay.

**Hemanth Sarabu:** try

**Pratyaksh Singh:** So one thing that I was thinking of uh of doing the split was uh so okay it might take some time to generate but one more thing that I trained the model with was with mask right where given the mask uh so like if you can uh let's okay no data set class if I just draw out some mask it's a classifi if I draw something out here.

### **00:40:39**

**Pratyaksh Singh:** Okay. And then here something for class two and so this was also trained right so that it can take mask as condition and then generate the example.

**Hemanth Sarabu:** Yeah,

**Pratyaksh Singh:** What I was thinking is what if I

**Hemanth Sarabu:** just give me one second. One second.

**Pratyaksh Singh:** Okay.

**Hemanth Sarabu:** Okay, I'm back.

**Pratyaksh Singh:** I think this looks like uh POE data right sorry DRN data

**Hemanth Sarabu:** Okay, I'm back.

**Pratyaksh Singh:** okay yeah so what I was saying is that this is also generated conditioned on mask right and that is why I had the observe data too so what I was thinking can I split the data in such a Okay, that I don't take any object any object level data in my training. So what I basically want so for example let's say you you see this these images so these are like conditioned on this mask it is trying to generate objects

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** at the location that I have masked right so uh so see what I don't uh what I want is that all the objects that I have I want to put it into right I want I want that in the I want that in val because the number of objects that we have is pretty less.

### **00:42:40**

**Pratyaksh Singh:** So to you know to increase the size

**Hemanth Sarabu:** Can you can you go through your full recipe from start for what you want to

**Pratyaksh Singh:** of

**Hemanth Sarabu:** do?

**Pratyaksh Singh:** okay so so let's say uh I I have these use XTF images right and then there is an

**Hemanth Sarabu:** Uh-huh.

**Pratyaksh Singh:** object here okay what I want to do is I want to split it up

**Hemanth Sarabu:** Yeah. Yeah.

**Pratyaksh Singh:** right but I will never put the data with object inside my training inside the the diffusion training. I will always put the split with the object in uh in in my validation set and the idea is that I will train the diffusion model to just generate the background and then I will use the object copy pasting with

**Hemanth Sarabu:** right?

**Pratyaksh Singh:** objects that I generate using uh you know closed source model like chat GPT and all these things which are good at

**Hemanth Sarabu:** Ah.

**Pratyaksh Singh:** it and then I will just copy paste those objects there. So whole of my object data will be in validation.

### **00:43:41**

**Pratyaksh Singh:** So I can basically get my

**Hemanth Sarabu:** H for for diffusion for diffusion or

**Pratyaksh Singh:** huh for classification also.

**Hemanth Sarabu:** classification.

**Pratyaksh Singh:** So for classification also let's say

**Hemanth Sarabu:** But for class uh you're not going to show it to any objects

**Pratyaksh Singh:** so I'm not going to show it any real object.

**Hemanth Sarabu:** classifier.

**Pratyaksh Singh:** What I'll do to the classifier I'll show it that background generated by the diffusion model and then object generated by you know uh some vision model and then those object will be copy pasted here.

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** Do you get what I mean? And this I'm doing this because uh I don't want to lose any of the object from the validation set because I think you know the validation set is very small to to trust those metrics right and another reason is that uh so for example here you see that the objects are the objects that are generated look real but if you change the data set because it is condition it is currently not conditioned on

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** a data set But if you will condition it on entx, vw or pee, then these objects won't be this good because uh because like you know uh because there wasn't that many examples.

### **00:44:59** {#00:44:59}

**Pratyaksh Singh:** with object in those data

**Hemanth Sarabu:** Okay. Uh,

**Pratyaksh Singh:** set.

**Hemanth Sarabu:** so what do you think that these what do you think Chad GPD's role is here? Like how are you going to actually ask it to generate examples?

**Pratyaksh Singh:** So uh I think we tried it out in one of the meetings where you will give it basically one example. Let's say you give it one example, right? You describe that example and then you ask it to generate maybe 15 or 20 more objects like that. Or you can generate these examples with procedural generation too,

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** right? Where you just create some area and then try to uh try to generate it out.

**Hemanth Sarabu:** Okay. I'm open to trying trying that out. Let's try it out. Um, it is cool to see the It is cool to see this though. This uh this picture the just the

**Pratyaksh Singh:** What? Yeah. Yeah, it does. It is doing kind of good like the CFG also.

### **00:45:59**

**Hemanth Sarabu:** generation

**Pratyaksh Singh:** So, for example, it's a this is the ENTX data without any without any guidance. But as you increase the guidance, so for example here the guidance is five and it just starts fitting this ton of image.

**Hemanth Sarabu:** interesting

**Pratyaksh Singh:** Yeah. And I think like you know between data sets too the it looks like the data set. So for example this is part of DRN data. This is VW where it's also generating the sand patches.

**Hemanth Sarabu:** Crazy

**Pratyaksh Singh:** So I think I'll have to train another model right with the train test

**Hemanth Sarabu:** crazy. Have you Have you tried the thing that I said where you copy paste take a couple of steps?

**Pratyaksh Singh:** split.

**Hemanth Sarabu:** Copy paste, add noise, take a couple of diffusion steps.

**Pratyaksh Singh:** Copy paste.

**Hemanth Sarabu:** Um so you would you would generate the background and then you would copy paste uh an object and then you would add a little noise. You would basic yeah you would noise the later Wait,

**Pratyaksh Singh:** Uh-huh.

**Hemanth Sarabu:** let me restart.

### **00:47:13** {#00:47:13}

**Pratyaksh Singh:** Mhm. So impending kind of thing,

**Hemanth Sarabu:** Um

**Pratyaksh Singh:** right? Imprinting kind of thing, right?

**Hemanth Sarabu:** it is it it is kind of in painting but it's not exactly in painting. So you you generate your background like you were saying and then you copy paste

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** your object somewhere and then you

**Pratyaksh Singh:** Okay. So,

**Hemanth Sarabu:** create this is with a train diffusion model so far.

**Pratyaksh Singh:** this is with the train model.

**Hemanth Sarabu:** Yes.

**Pratyaksh Singh:** Okay.

**Hemanth Sarabu:** You generate your background. You copy paste the object. Now the object doesn't look like it belongs.

**Pratyaksh Singh:** Okay. Mhm.

**Hemanth Sarabu:** So you uh you know you depending on what model you're using most likely you're using a latent diffusion So you convert this into a latent. You autoenccode it. You create get your latent and then you slightly noise your latent

**Pratyaksh Singh:** So do you know the whole the whole latent or only that part where the object is added?

**Hemanth Sarabu:** uh the whole latent the whole latent I actually don't

### **00:48:17**

**Pratyaksh Singh:** The whole latent. Okay.

**Hemanth Sarabu:** know I'm not I'm not not an expert. So I don't know how you would noise in latent space only that patch. Maybe it is possible but I don't know how to do it. You get what I mean? Because latent Yeah.

**Pratyaksh Singh:** I I get what you mean.

**Hemanth Sarabu:** So I'm presuming you you noise the whole latent not a lot just a little

**Pratyaksh Singh:** I use this.

**Hemanth Sarabu:** bit and then you d noiseise it with your diffusion model which has seen uh

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** objects. Now it may not have to be conditional objects but it has seen objects.

**Pratyaksh Singh:** It has

**Hemanth Sarabu:** So what it it it is trying to do is basically you said hey I've got this latent it

**Pratyaksh Singh:** option.

**Hemanth Sarabu:** is a little out of distribution bring it into distribution and so its job will

**Pratyaksh Singh:** Uh

**Hemanth Sarabu:** become uh and and it doesn't have a lot of budget right you added a little bit of noise and you're doing not many steps do like one or two steps max I believe so it will it will try to like bring it

### **00:49:10**

**Pratyaksh Singh:** Mhm. Mhm.

**Hemanth Sarabu:** into distribution by changing how how the uh yeah how basically the object looks in the

**Pratyaksh Singh:** Got it. So is this like something that I've drawn here?

**Hemanth Sarabu:** image.

**Pratyaksh Singh:** So you start with the blue pads, right? And then you move it to generate your final image which is the which is the orange background which is the orange box. And then you add your object here which will look out of dis which will you know like look like

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** you added something there. And then you move it few step back to the red one.

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** And then you and you and then you d noiseise again right adding

**Hemanth Sarabu:** Move it few step back is by adding noise to the latent. Yeah.

**Pratyaksh Singh:** noise. Yeah. Yeah.

**Hemanth Sarabu:** Yeah. Yes.

**Pratyaksh Singh:** And then you you den noise it for a few more steps. Right. I think this can be done with a trained model too.

### **00:50:03** {#00:50:03}

**Hemanth Sarabu:** Yes.

**Pratyaksh Singh:** This can be done with a trend model.

**Hemanth Sarabu:** Yes.

**Pratyaksh Singh:** Yeah. Because so for example even in these unconditioned generation right the reason that I was asking it to be uh looked at by labelers was because even in these unconditioned generation I'm seeing like maybe maybe some valid object. for example. Okay, you can't see my pointer but

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** anyways. Okay, I will I will train another model then.

**Hemanth Sarabu:** Okay. Okay.

**Ratul Shashank:** Hey guys, can I share my update?

**Hemanth Sarabu:** Uh yes, please.

**Ratul Shashank:** Share my screen. Is my screen visible? Uh so just a quick update on what I was

**Pratyaksh Singh:** Yes.

**Ratul Shashank:** trying uh like what Ratash was doing copy and paste. He was copying the object from an image and then pasting it on another background. Right.

**Hemanth Sarabu:** Yeah.

**Ratul Shashank:** I I tried that but uh I copied the raw

**Pratyaksh Singh:** No.

**Ratul Shashank:** amplitude in the HTF where the annotations were and then I tried uh not tried but then I overlaid that

### **00:51:50** {#00:51:50}

**Pratyaksh Singh:** Heat.

**Ratul Shashank:** amplitude on the background and how I did it was I uh well there are

**Hemanth Sarabu:** What's the What's the result?

**Ratul Shashank:** a quite a few So to to give you uh one more uh one more information that if we are changing the raw raw data then we can also apply changes right to the height to the length of the object that was my goal for the entire uh experiment.

**Hemanth Sarabu:** So

**Ratul Shashank:** So this uh

**Hemanth Sarabu:** okay remind remind me

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** again what were you trying what were you trying to achieve like what is the goal?

**Ratul Shashank:** Uh in my head I wanted to like change the dimension of the object like either length uh height

**Hemanth Sarabu:** Right.

**Ratul Shashank:** uh uh uh these were the changes that I had in mind.

**Hemanth Sarabu:** Wait. Okay. Okay. Okay. So, we still need to stay a little high level. You're you're exploring you're exploring a way to do augmentations. Are you doing generative modeling? Are you doing both?

### **00:53:16**

**Hemanth Sarabu:** What is what uh remind us what you're working

**Ratul Shashank:** No right uh in in in this part I am doing

**Hemanth Sarabu:** on?

**Ratul Shashank:** augmentation on the object on the actual data. So changing maybe trying to change a few metrics to get a new

**Hemanth Sarabu:** Okay,

**Ratul Shashank:** object,

**Hemanth Sarabu:** I see.

**Ratul Shashank:** changing the height, length, uh comp uh mixing two amplitudes and finding out what objects it would generate. So that was the entire goal of what I was trying

**Hemanth Sarabu:** Understood. No, it makes sense. Sorry. Give me Oh, never mind. Yeah.

**Ratul Shashank:** Yeah. So just uh just an example contact sheet

**Hemanth Sarabu:** coming.

**Ratul Shashank:** like the the this left most is the uh this this is blurred because this was uh highly probed image. Please uh take a look at this control image. This is this is supposed to be the control variable to understand what changes is

**Hemanth Sarabu:** Okay.

**Ratul Shashank:** happening. uh TLDDR we can change height if the value is compar comparable like in this if we see uh if height is.7x uh it's it's

### **00:54:47** {#00:54:47}

**Hemanth Sarabu:** Let's go.

**Ratul Shashank:** it's not very different right uh compared to if If I in in this one it is 1.5 but uh I have also tested with 2x. So the point is if the augmentations level is higher we can see novelty in the data. This was for height. And another important finding was if we mix two amplitudes.

**Hemanth Sarabu:** two amplitudes. So, how are you doing this, Rol?

**Ratul Shashank:** Yeah.

**Hemanth Sarabu:** You're uh finding out where the Yeah, actually I don't know how how this is cool. I actually think this is cool. Um how how are you doing this at the X

**Ratul Shashank:** So,

**Hemanth Sarabu:** level?

**Ratul Shashank:** so I am taking I am using the help of the annotations to find out where the objects are in the XT and uh I uh I just took a small box like uh a small part and what I do is uh I first take the median of the amplitude uh

**Hemanth Sarabu:** H.

**Ratul Shashank:** the me uh I take the median of the amplitude of for the background where I'm going to place this and then I am subtracting that median of the background uh in subtracting that median of the background with the amplitude of

### **00:56:36**

**Hemanth Sarabu:** H.

**Ratul Shashank:** the object that I am placing. So my reasoning was I need the amplitude to be as close as possible. So that is why I was subtracting the median of the background. phone.

**Hemanth Sarabu:** That makes sense. God. Got it. Got it. Makes sense.

**Ratul Shashank:** All right.

**Hemanth Sarabu:** Rul, I just want to ask Pratak, how did the EMD decompositions

**Ratul Shashank:** So,

**Hemanth Sarabu:** look?

**Pratyaksh Singh:** Uh, so the decomposition that I ran, it looked like kind of weird. I mean, you couldn't make sense of it. It looked like some signals. I'll show you the image of it on Slack. Give me a

**Hemanth Sarabu:** Okay. Anyway, I was wondering if we could combine some ideas,

**Pratyaksh Singh:** minute.

**Hemanth Sarabu:** but go ahead.

**Ratul Shashank:** Yeah, I mean I uh this is very uh preliminary.

**Hemanth Sarabu:** Well,

**Ratul Shashank:** This uh I I really need uh like you guys can provide me valuable feedback because

**Hemanth Sarabu:** no,

**Ratul Shashank:** uh

**Hemanth Sarabu:** I think there's a good there there's a good this is a good idea actually.

### **00:57:50** {#00:57:50}

**Hemanth Sarabu:** This is a good idea. So I think um what you know when you remove the median actually let's do you have any pictures where let me see if I understand what you're doing. You're finding out where the object is and then you're kind of backtracking which pings create that object uh around and then you have a bounding box.

**Ratul Shashank:** Uh-huh.

**Hemanth Sarabu:** You compute the mean of the intensity.

**Ratul Shashank:** Uh-huh. Medium.

**Hemanth Sarabu:** you remove that value of the pings and then basically you've isolated the uh roughly you've isolated the intensity values for the object and then you shape it differently and then you add it back.

**Ratul Shashank:** Uh on the on the uh background.

**Hemanth Sarabu:** Okay, nice.

**Ratul Shashank:** Yes.

**Hemanth Sarabu:** That's cool. I think that's actually a very clever idea. Um could be

**Ratul Shashank:** I mean uh my point for choosing the median was because uh like in the XTF we don't have any other value other than amplitude. So

**Hemanth Sarabu:** So here's the thing you that is I think chameleon could work but the places

### **00:58:51** {#00:58:51}

**Ratul Shashank:** uh

**Hemanth Sarabu:** where I don't expect it to work is say like the top left image the top left image uh has a gradient. Yeah,

**Ratul Shashank:** this one.

**Hemanth Sarabu:** there's a gradient. Do you see a

**Ratul Shashank:** Yeah. Uh uh that was uh that that was a problem a bottleneck that

**Hemanth Sarabu:** gradient?

**Ratul Shashank:** I encountered. So I was also like this and I added an extra function to kind of gradient match the entire thing. Uh let me let me share you the final product that would be more

**Hemanth Sarabu:** Nice. Yeah. Always start with the final product.

**Ratul Shashank:** apparent. Uh overlays would be more easy to Yeah,

**Hemanth Sarabu:** I have to go in 2 minutes. So, you have 2 minutes to show the fun.

**Ratul Shashank:** I'll be I'll be quick. So,

**Hemanth Sarabu:** Yeah.

**Ratul Shashank:** this is the object that we are placing. So we are uh we are increasing the height of the AI small black by 1.3x and this would it this is how it would

### **01:00:05** {#01:00:05}

**Hemanth Sarabu:** Mhm.

**Ratul Shashank:** look

**Hemanth Sarabu:** So, okay.

**Ratul Shashank:** um

**Hemanth Sarabu:** So what what what can you show us the the real one?

**Ratul Shashank:** uh I can but uh it is uh I I I need to find the photo of that I don't have like it is saved but it would take some

**Hemanth Sarabu:** Okay, fine. Okay,

**Ratul Shashank:** time.

**Hemanth Sarabu:** maybe post post on Slack um before after, right?

**Ratul Shashank:** Yeah.

**Hemanth Sarabu:** That'll be pretty good.

**Ratul Shashank:** Yeah. Yeah. Uh uh just uh just a caveat in this the problem with uh the uh uh uh problem that I need uh feedback is with like intx like the entx is a smaller sample compared to the others. So suppose I am cutting I am cropping an object from let's say VW and the object is let's say X length but the ENTX entire sample is half of BW. So if I place that I if I place that object from BM Lulu on the ENT background it is exceptionally large to give you a better visual understanding like this this is something that I don't know how to fix this is exceptionally

### **01:01:42**

**Hemanth Sarabu:** Uh is this large in pixels or is that true to scale? Like is it is that true to the metric value the uh

**Ratul Shashank:** uh this is true to metric value because if I like I am copying the uh raw values from another data set and if

**Hemanth Sarabu:** Actually,

**Ratul Shashank:** it yeah that

**Hemanth Sarabu:** I want to point out so this this is sticking out quite a bit,

**Ratul Shashank:** is the that is the problem that I wanted to flag this is something that I

**Hemanth Sarabu:** right?

**Ratul Shashank:** need like I don't know how to fix this. This is pro purely the problem of sample size. ENTx is low uh has smaller sample size compared to the others. Right? So like it is it is kind of like if we have a strip of paper and the strip of paper has some polar dots and I want to cut that polar dot and

**Hemanth Sarabu:** Yeah.

**Ratul Shashank:** paste it on another strip of paper.

**Hemanth Sarabu:** Yeah.

**Ratul Shashank:** So like if I'm cutting the polar dot from a larger strip of paper and placing this on a smaller paper the polar dot would uh would sore out right.

### **01:02:52** {#01:02:52}

**Ratul Shashank:** So so that is the problem.

**Hemanth Sarabu:** So I I don't know if like I'm saying I don't know if this is purely a scale problem. If this is an object, the object is this big then it is this big right so you could make it smaller but I'm I guess uh you

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** guys continue discussing I need to drop but for to me it feels like uh it needs to blend in more

**Pratyaksh Singh:** Hey hey

**Hemanth Sarabu:** even if it's large it needs to blend in more

**Ratul Shashank:** Yeah. I mean that the only thing that I thought was don't do augmentations with

**Hemanth Sarabu:** uh

**Ratul Shashank:** multiplications. That was what I thought for Indians.

**Hemanth Sarabu:** what

**Pratyaksh Singh:** hey I had hey

**Ratul Shashank:** I mean not in

**Hemanth Sarabu:** Hey,

**Pratyaksh Singh:** sorry I just wanted to bring something out that was I had some

**Ratul Shashank:** Uh-huh.

**Pratyaksh Singh:** uh some you know some questions with this which I discuss with you. The problem is that the transformation from XTF to image domain is completely a fine right it's it's I mean we don't do any

### **01:03:50**

**Hemanth Sarabu:** heat.

**Pratyaksh Singh:** nonlinear I don't remember doing any nonlinear changes here

**Hemanth Sarabu:** Oh, is it actually is it No,

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** so no sign cause there is

**Hemanth Sarabu:** there's no sign cost.

**Pratyaksh Singh:** nothing like the only thing is I think so it's just that

**Ratul Shashank:** No.

**Pratyaksh Singh:** uh you have the watershed which is just uh

**Hemanth Sarabu:** You guys, I have to I have to drop. Sorry. You guys can Okay,

**Pratyaksh Singh:** Okay.

**Hemanth Sarabu:** bye.

**Pratyaksh Singh:** Yeah. Yeah. So like the question just remains that you know the same thing that we discussed previously that isn't it same as just copying in the image domain if everything is is the same. Do you get what I mean?

**Ratul Shashank:** Yeah. Yeah. I mean that

**Pratyaksh Singh:** And okay uh just let me finish my thoughts.

**Ratul Shashank:** Uh-huh.

**Pratyaksh Singh:** So what I was saying is that and the and the good thing with image domain is there are few good things when you are working within image domain there are a lot of research.

### **01:04:50** {#01:04:50}

**Pratyaksh Singh:** So for example let's say this thing this thing is uh this thing is like kind of you know it's visibly direct copy paste right but if you apply the poison distribution to

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** it it will blend into the background and another thing is that

**Ratul Shashank:** Mhm. Mhm.

**Pratyaksh Singh:** if you want to change in your dimension and all those things you can just resize it right any object you can resize it you can increase its height you can change its color uh The poison copy paste which CV2 provides it it is much more robust. It it uses the gradient to paste in the object. So it completely blends in. And then the one more advantage with your copy paste in image domain is that you can do it at runtime. So during training so you don't have to create a static images. You can just have your object and during training you can paste it anywhere and let the model figure it out.

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** And since each of these individual object will be image to you can augment those objects.

### **01:05:55** {#01:05:55}

**Pratyaksh Singh:** So for example, you can resize it, you can translate it, you can rotate it. You can change its color, you can increase its contrast, you can change it brightness and all those things and you get all of these things inbuilt, right?

**Ratul Shashank:** I mean yeah I I I want to double down on that.

**Pratyaksh Singh:** Who?

**Ratul Shashank:** uh when you mention this uh like the immediate question that I have

**Pratyaksh Singh:** Uh,

**Ratul Shashank:** is uh uh like how I don't know so this is purely uh purely a curious level question so are we able to control

**Pratyaksh Singh:** sorry.

**Ratul Shashank:** the augmentations like uh uh are we able to control what is the height change or What is the rotation based on cosine or sorry cos theta or sin theta?

**Pratyaksh Singh:** Yeah. Yeah, you can. You can you can. So if you want to rotate an image,

**Ratul Shashank:** Uh

**Pratyaksh Singh:** you just have to multiply it with uh there is a matrix uh sin theta cos theta minus cos theta minus sin theta something like this.

**Ratul Shashank:** yeah I yeah that is exactly what I am doing.

### **01:07:03** {#01:07:03}

**Pratyaksh Singh:** Just search for a rotation matrix.

**Ratul Shashank:** Yeah,

**Pratyaksh Singh:** Uh so you can do it in image

**Ratul Shashank:** that's what Yeah, that's what exactly what I wanted to discuss with you and I want to spend a little bit of more time

**Pratyaksh Singh:** too.

**Ratul Shashank:** with this like I want to know like really

**Pratyaksh Singh:** Mhm.

**Ratul Shashank:** uh so uh this is not a good example for this.

**Pratyaksh Singh:** Again I'll show you this link. Okay.

**Ratul Shashank:** Uh-huh.

**Pratyaksh Singh:** You can try out all these augmentation on any random events right. So if you'll go to this link I shared the link with you.

**Ratul Shashank:** Oh, I I see you have shared this before,

**Pratyaksh Singh:** Yeah. So just go to that link and search for rotate.

**Ratul Shashank:** right?

**Pratyaksh Singh:** Ctrl F. Search for rotate. Do Ctrl F. I think it will be better. Yeah, you see that rotate augmentation? Go there. Just click on that. Uh no, the below one only. Not random rotate 90\. Just rotate.

### **01:08:09** {#01:08:09}

**Pratyaksh Singh:** Yeah. Okay. Now just say to try the uh just press on apply.

**Ratul Shashank:** Nice.

**Pratyaksh Singh:** Yeah. You see these people are rotated,

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** right?

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** You can you can do do a lot of things in image. If you just go back there is shift scale and all those things. So you can scale those things these people up,

**Ratul Shashank:** Like this is something interesting.

**Pratyaksh Singh:** right?

**Ratul Shashank:** the the when I rotate it is also tracking the eyes and like left eyes

**Pratyaksh Singh:** Yeah. Yeah.

**Ratul Shashank:** and

**Pratyaksh Singh:** It's it's it's uh it's simple like uh you know when you rotate so these eyes body these are our bounding boxes right? So you have coordinates of these coordinates of these.

**Ratul Shashank:** oh I I I understand it is it is applying a

**Pratyaksh Singh:** You can rotate those two.

**Ratul Shashank:** su a sin theta rotation on every bounding box not just the outside.

**Pratyaksh Singh:** Yeah.

**Ratul Shashank:** Uh so uh just give me a couple of minutes.

### **01:09:20** {#01:09:20}

**Ratul Shashank:** uh so let's suppose we we do two things one is one

**Pratyaksh Singh:** Oh,

**Ratul Shashank:** is basic rotate right but we

**Pratyaksh Singh:** okay.

**Ratul Shashank:** uh we try to merge two images I mean if this image and this image would be merged it would be like like just overlap this this

**Pratyaksh Singh:** What do you mean by merge? Okay.

**Ratul Shashank:** and this uh the these blue boundary ones.

**Pratyaksh Singh:** Mhm. Mhm.

**Ratul Shashank:** So if you just overlap these

**Pratyaksh Singh:** Mhm.

**Ratul Shashank:** and

**Pratyaksh Singh:** By overlap you mean you put them on top of one another or by overlap you mean?

**Ratul Shashank:** no on top of one

**Pratyaksh Singh:** What do you mean brother? On top of Okay, fine.

**Ratul Shashank:** another

**Pratyaksh Singh:** And the way that you overlap them is for each pixel you take in the max value or do you add them up sum them up? It

**Ratul Shashank:** uh what uh like we can

**Pratyaksh Singh:** mean

**Ratul Shashank:** Just in this case we we have the dark areas and we are overlapping the dark areas.

### **01:10:36** {#01:10:36}

**Ratul Shashank:** So we can just crop the dark area from this place and and crop the dark areas from this place and just add them up.

**Pratyaksh Singh:** add them up. Okay. So you're taking mean. All right. Fine.

**Ratul Shashank:** Uh and

**Pratyaksh Singh:** So you you normally you don't add them up. You take mean because let's say there are two white pixels, right? So 255 \+ 255 will go to what? 510,

**Ratul Shashank:** Uh yeah,

**Pratyaksh Singh:** right?

**Ratul Shashank:** it it so it will it not just tap at

**Pratyaksh Singh:** It will overflow. So take me now.

**Ratul Shashank:** 255\.

**Pratyaksh Singh:** You'll have to clip it. But sum of 255 and 255 will be 510, right? and you'll have to clip everything out.

**Ratul Shashank:** Oh,

**Pratyaksh Singh:** So what will happen is that 125 \+ 125 will result in 250\. So if two 125 125 pixels are added, they will be equivalent to adding two 225 225 pixels because you're clipping them them up. So usually you take mean of

### **01:11:40** {#01:11:40}

**Ratul Shashank:** mean of what exactly

**Pratyaksh Singh:** these two things. So the two things that you are overlapping you will take the mean of them. So what you are summing instead of summing you will just divide it by 22\.

**Ratul Shashank:** Uh I see I see. Uh and since we are uh Like for our case is this direction of shadow very important? I mean not

**Pratyaksh Singh:** not really even even direction of shadow right you can I told you right before you can add

**Ratul Shashank:** really.

**Pratyaksh Singh:** those direction of shadows too right you remember you can add shadows too and when you augment the model augment you give it give it s\*\*\* ton of example you can we don't know what the model is learning to you give it from every direction to teach the model.

**Ratul Shashank:** Okay.

**Pratyaksh Singh:** If it's a shadow, you just have to pick the object. Okay.

**Ratul Shashank:** So,

**Sachin Pandey:** Huh?

**Pratyaksh Singh:** Sinack.

**Sachin Pandey:** Okay.

**Ratul Shashank:** final thought. Final thought. and we feed that to a model like create a lower on an existing stable defeated model.

### **01:13:09**

**Pratyaksh Singh:** Uh

**Ratul Shashank:** So genuine. Uh-huh.

**Pratyaksh Singh:** most of the rotations

**Ratul Shashank:** Uh.

**Pratyaksh Singh:** 3 \+ 3 matrix

**Ratul Shashank:** Uhhuh.

**Pratyaksh Singh:** model.

**Ratul Shashank:** Sorry. Get

**Pratyaksh Singh:** But augmentation

**Ratul Shashank:** said was double

**Pratyaksh Singh:** Huh. Huh.

**Ratul Shashank:** text to images. Try

**Pratyaksh Singh:** Focus Chad GPT. Gemini. Yeah.

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** object.

**Ratul Shashank:** blow back

**Pratyaksh Singh:** object.

**Ratul Shashank:** color. Uh purely Laura

**Pratyaksh Singh:** Huh?

**Ratul Shashank:** buscessed.

**Pratyaksh Singh:** Huh.

**Ratul Shashank:** So

**Pratyaksh Singh:** Huh.

**Ratul Shashank:** Put augmentation

**Pratyaksh Singh:** Augmentations run.

**Ratul Shashank:** model examples.

**Pratyaksh Singh:** Mhm. H

**Ratul Shashank:** Highly processed.

**Pratyaksh Singh:** yeah

**Ratul Shashank:** Mhm. H 144 cut out

**Pratyaksh Singh:** But usually for example,

**Ratul Shashank:** background.

**Pratyaksh Singh:** A background examples but kind of out of distribution.

**Ratul Shashank:** NTX grainy grainy

**Pratyaksh Singh:** Dr.

**Ratul Shashank:** dr.

**Pratyaksh Singh:** Sa and

**Ratul Shashank:** Okay.

**Pratyaksh Singh:** but

**Ratul Shashank:** Hello. Mhm.

**Pratyaksh Singh:** unique object Object. Augmentation.

### **01:18:08** {#01:18:08}

**Ratul Shashank:** No example object. It's a

**Pratyaksh Singh:** Exactly. Exactly.

**Ratul Shashank:** principle.

**Pratyaksh Singh:** XF different. Okay.

**Ratul Shashank:** Some

**Pratyaksh Singh:** Huh? Let's say x sin

**Ratul Shashank:** little

**Pratyaksh Singh:** x2

**Ratul Shashank:** Yeah.

**Pratyaksh Singh:** by

**Ratul Shashank:** Uhhuh. Yeah. Yeah. Uh,

**Pratyaksh Singh:** objective focus please focus

**Ratul Shashank:** XTF She

**Pratyaksh Singh:** Sachin Sachin port or

**Ratul Shashank:** go.

**Pratyaksh Singh:** starboard separate Take us callus

**Ratul Shashank:** Okay.

**Pratyaksh Singh:** take. Ah

**Ratul Shashank:** I will bring

**Pratyaksh Singh:** button uh

**Ratul Shashank:** you.

**Pratyaksh Singh:** reply

**Sachin Pandey:** Hello starboard.

**Pratyaksh Singh:** or starboard separate 256 6 128\. Huh? location, please.

**Sachin Pandey:** Huh? Sorry.

**Pratyaksh Singh:** NTX part.

**Sachin Pandey:** ent to bark Okay.

**Pratyaksh Singh:** Diffusion

**Sachin Pandey:** Slim.

**Pratyaksh Singh:** model

**Sachin Pandey:** Oh. Oh.

**Pratyaksh Singh:** type of data set conditioning. variable. Uh modeling again. Hello.

**Sachin Pandey:** Huh?

**Pratyaksh Singh:** Huh?

**Ratul Shashank:** Hello.

**Sachin Pandey:** Let me check.

**Pratyaksh Singh:** Okay.

### **01:22:09** {#01:22:09}

**Pratyaksh Singh:** Diffusion

**Sachin Pandey:** Object.

**Pratyaksh Singh:** model.

**Sachin Pandey:** Uh,

**Pratyaksh Singh:** Take

**Sachin Pandey:** oops.

**Pratyaksh Singh:** VW part two part three data split

**Sachin Pandey:** Roll

**Pratyaksh Singh:** data generate

**Sachin Pandey:** data classification background. annotations.

**Pratyaksh Singh:** annotations. Hearts

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** screenshot.

**Sachin Pandey:** Oh.

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** Data for data name data/ bedrop patches datim images U VW RON entit. datim.

**Sachin Pandey:** I watch video

**Pratyaksh Singh:** Hello 128 128 128\. Hello.

**Sachin Pandey:** or split I don't think 128 generate

**Pratyaksh Singh:** Uh uh

**Sachin Pandey:** hello 2562

**Pratyaksh Singh:** hello 256 or

**Sachin Pandey:** generate

**Pratyaksh Singh:** 5.2 generator

**Sachin Pandey:** uh

**Pratyaksh Singh:** size equal to p size not overlap. Uh

**Sachin Pandey:** Get him.

**Pratyaksh Singh:** 128\. Yeah. Examples training. So

**Sachin Pandey:** Uh, okay.

**Pratyaksh Singh:** let's

**Sachin Pandey:** Better.

**Pratyaksh Singh:** Huh? Ch. or screen.

**Sachin Pandey:** I say that couldn't do that,

**Pratyaksh Singh:** Huh?

**Sachin Pandey:** man. By the way,

**Pratyaksh Singh:** Cut this port starboard separate.

### **01:27:50** {#01:27:50}

**Pratyaksh Singh:** Train

**Sachin Pandey:** How folder

**Pratyaksh Singh:** associated mask.

**Sachin Pandey:** validation 256 valid

**Pratyaksh Singh:** Say similarly

**Sachin Pandey:** Verify

**Pratyaksh Singh:** location.

**Sachin Pandey:** WhatsApp.

**Pratyaksh Singh:** GPU rap.

**Sachin Pandey:** Hello. Ascending order by name. Sorry.

**Pratyaksh Singh:** Um, shiny example.

**Sachin Pandey:** Three.

**Pratyaksh Singh:** H

**Sachin Pandey:** Sudo.

**Pratyaksh Singh:** old mega sir.

**Sachin Pandey:** 21\.

**Pratyaksh Singh:** Screen

**Sachin Pandey:** Oh.

**Pratyaksh Singh:** patches depth.

**Sachin Pandey:** minus uh h L 3 minus

**Pratyaksh Singh:** HL

**Sachin Pandey:** uh chip L2

**Pratyaksh Singh:** 3 \- L2

**Sachin Pandey:** And so where producer

**Pratyaksh Singh:** the art capital.

**Sachin Pandey:** you

**Pratyaksh Singh:** Yeah, they go here.

**Sachin Pandey:** Maybe

**Ratul Shashank:** Robot robotic sex.

**Sachin Pandey:** it's

**Pratyaksh Singh:** That's format. Huh?

**Sachin Pandey:** near

**Pratyaksh Singh:** for WhatsApp.

**Sachin Pandey:** you guys. 128

**Pratyaksh Singh:** Yeah. Sorry. PNG

**Sachin Pandey:** m.

**Pratyaksh Singh:** 01\. Sorry. But

**Sachin Pandey:** Nothing

**Pratyaksh Singh:** uh Yeah. Hello mask. Mask

**Sachin Pandey:** here.

**Pratyaksh Singh:** mask. function. PNG

**Sachin Pandey:** It's a

### **01:33:09**

**Pratyaksh Singh:** mask for

**Sachin Pandey:** folder.

**Pratyaksh Singh:** load.

**Sachin Pandey:** It's a folder based.

**Pratyaksh Singh:** This is np.form patch mask dot sype np.

**Sachin Pandey:** M directly uh PNG save.

**Pratyaksh Singh:** PNG

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** last mask mask 128\.

**Sachin Pandey:** Okay, take

**Pratyaksh Singh:** Save. Save.

**Sachin Pandey:** three.

**Pratyaksh Singh:** trainer

**Sachin Pandey:** Okay. split mastery.

**Ratul Shashank:** See?

**Pratyaksh Singh:** folder format

**Sachin Pandey:** Oh,

**Pratyaksh Singh:** entwin.

**Sachin Pandey:** good morning. HTML.

**Pratyaksh Singh:** HTML.

**Sachin Pandey:** Uh open gray.

**Pratyaksh Singh:** Uh log like

**Sachin Pandey:** doesn't uh

**Pratyaksh Singh:** Catch it.

**Ratul Shashank:** Oh, okay.

**Pratyaksh Singh:** Simple log.

**Sachin Pandey:** Uh

**Pratyaksh Singh:** Anyways,

**Sachin Pandey:** better beach.

**Pratyaksh Singh:** Mhm. 128 size 128 256\.

**Sachin Pandey:** Sorry key

**Pratyaksh Singh:** Uh take

**Sachin Pandey:** model.

**Pratyaksh Singh:** take Yeah, maybe. Take

**Sachin Pandey:** See, two split

**Pratyaksh Singh:** care.

**Sachin Pandey:** data.

**Pratyaksh Singh:** Hey guys. Huh? Uh 512

**Sachin Pandey:** 225

**Pratyaksh Singh:** char 256

**Sachin Pandey:** extra.

**Pratyaksh Singh:** Huh?

**Sachin Pandey:** Someone

**Pratyaksh Singh:** Model black predict.

**Sachin Pandey:** here. Okay.

**Pratyaksh Singh:** by us.

**Ratul Shashank:** Bye-bye.

**Pratyaksh Singh:** data set 1 2 3

**Sachin Pandey:** That's Here you go.

**Pratyaksh Singh:** Take it. Take it. Bye-bye.

**Sachin Pandey:** Okay.

**Ratul Shashank:** Bye-bye. PNG networking

**Sachin Pandey:** Last

**Ratul Shashank:** networking.

**Sachin Pandey:** speed.

**Ratul Shashank:** Split

**Sachin Pandey:** Here

**Ratul Shashank:** Four star. Okay.

**Sachin Pandey:** you go. Bye.

### **Transcription ended after 01:40:57**

*This editable transcript was computer generated and might contain errors. People can also change the text after it was created.*