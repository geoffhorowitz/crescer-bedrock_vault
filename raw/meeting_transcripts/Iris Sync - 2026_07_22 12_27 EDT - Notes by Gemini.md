# **📝 Notes**

Jul 22, 2026

## **Iris Sync**

Invited [Pratyaksh Singh](mailto:pratyaksh@crescer.ai) [Niveta Iyer](mailto:niveta@crescer.ai) [Hemanth Sarabu](mailto:hemanth@crescer.ai) [Geoff Horowitz](mailto:geoff@crescer.ai) [Siddharth Soni](mailto:siddharth@crescer.ai) [Ratul Shashank](mailto:ratul@crescer.ai) ~~[Sachin Pandey](mailto:sachin@crescer.ai)~~

Attachments [Iris Sync](https://calendar.google.com/calendar/event?eid=NnNzMHVxNzk3MmJqZGVwNXFoN2J1Mjd1OTdfMjAyNjA3MjJUMTYzMDAwWiBnZW9mZkBjcmVzY2VyLmFp) [Iris Sync - 2026/07/22 12:27 EDT - Recording](https://drive.google.com/file/d/1IPhA-R8z8f_3_ccuLeqBJ6suZPocRGeA/view?usp=drive_web)

Meeting records [Transcript](https://docs.google.com/document/d/1BpUqLl40_o-ZJ_RXnBM3gE6n9oFuhkp-m0lJPoOYXN4/edit?usp=drive_web&tab=t.c547tj6y6wl) [Recording](https://drive.google.com/file/d/1IPhA-R8z8f_3_ccuLeqBJ6suZPocRGeA/view?usp=drive_web) 

### **Summary**

Experiments explored hyperparameter optimization and data cleaning techniques for improving model object detection accuracy via performance comparisons.

**Performance and Augmentation Experiments**  
Models utilizing 512-pixel inputs and specific blending combinations achieved the highest object-level scores. The team identified that data cleaning negatively impacted object-level metrics due to ground truth alterations.

**Evaluation and Model Failure**  
The current iterations underperformed compared to legacy baselines, with missed detections primarily occurring near image borders. Researchers determined geographic overlaps require manual partitioning for valid cross-validation testing.

**Strategic Improvement Directions**  
The team decided to introduce a Probable UXO class to better capture ambiguous objects. This category aims to improve recall while addressing visual discrepancies between open-source mine data and project imagery.

### **Decisions**

## Aligned

* **K-fold validation strategy adopted** K-fold cross-validation is adopted as the standard validation strategy to address the small sample size in the validation set.

* **Probable UXO class inclusion** A "probable UXO" classification category is created to capture ambiguous objects that resemble UXO, replacing the previous practice of removing these items.

* **Port and starboard class separation** Model training will be updated to treat "port" and "starboard" as separate categories.

We've **updated the Decisions section** using your feedback.

Let us know what you think: [Helpful](https://google.qualtrics.com/jfe/form/SV_5bXzKQfylMIhSXc?isHelpful=True&entryPoint=decisions&isGoogler=False) or [Not Helpful](https://google.qualtrics.com/jfe/form/SV_5bXzKQfylMIhSXc?isHelpful=False&entryPoint=decisions&isGoogler=False)

### **Next steps**

- [ ] \[Geoff Horowitz\] Follow up with Sachin: Follow up with Sachin later today regarding project progress.

- [ ] \[Pratyaksh Singh, Sachin Pandey\] Share slides: Share the slide deck containing images of potential UXO to Geoff for review.

- [ ] \[Pratyaksh Singh\] Perform cross validation: Execute K fold cross validation comparing the baseline model and the best performing model using varied data splits.

- [ ] \[Pratyaksh Singh\] Test border sensitivity: Reposition objects near the image border and re run predictions to test model sensitivity to edge placement.

- [ ] \[Pratyaksh Singh\] Clean image data: Remove black regions from the image dataset and combine segments to improve object detection.

- [ ] \[Pratyaksh Singh\] Verify Failure Case: Investigate the cause for missing detections of specific objects.

- [ ] \[Pratyaksh Singh\] Augment Depression Data: Increase data variety for depression regions to improve model detection.

- [ ] \[Pratyaksh Singh\] Train Separate Models: Utilize separate categories for port and starboard inputs during training.

- [ ] \[Pratyaksh Singh\] Evaluate UXO Class: Test the effectiveness of the probable Unexploded Ordnance class in the model.

- [ ] \[Pratyaksh Singh\] Cross-Validate Results: Conduct a cross-validation process to ensure model accuracy.

- [ ] \[Sachin Pandey\] Update Classification: Move missed or mislabeled Unexploded Ordnance objects into the probable Unexploded Ordnance class.

- [ ] \[Sachin Pandey\] Refine Augmentation: Apply changes in the augmentation script to enhance binary performance.

### **Details**

* **Hyperparameter Search and Augmentation Experiments**: Pratyaksh Singh conducted a hyperparameter search using ResNet 50, comparing image sizes of 256 and 512 pixels, with findings indicating that 512-pixel models outperformed 256-pixel models ([00:04:55](#00:04:55)). The team experimented with various transformation techniques, including perspective, "poison" (blending), roll, cut mix, and soft mix, with a model utilizing a combination of poison, roll, and cut mix achieving the highest object-level F1 score of 0.49 ([00:06:30](#00:06:30)).

* **Annotation Standards and Baseline Comparison**: Geoff Horowitz confirmed that the reported object-level F1 scores were based on a 20% Intersection Over Union (IOU) threshold ([00:08:56](#00:08:56)). Pratyaksh Singh explained that "sand ripple" classes were removed from training to prevent them from dominating the segmentation task. The team discussed the necessity of an "apples-to-apples" comparison against the baseline model from the first project to ensure performance gains are accurately measured, noting that the baseline data is available in the project documentation ([00:09:58](#00:09:58)).

* **UXO Model Performance and Error Analysis**: The team compared current models against the previously developed multiclass Unexploded Ordnance (UXO) V2 model ([00:16:13](#00:16:13)). Sachin Pandey noted that the baseline model currently performs better on UXO classification compared to the newer iterations ([00:14:59](#00:14:59)). Pratyaksh Singh identified nine false negative missed objects in the current test set and emphasized the need to focus on specific UXO samples to address these classification errors ([00:18:13](#00:18:13)).

* **Impact of Data Cleaning on Metrics**: Sachin Pandey detailed the removal of approximately 1,300 noisy or small black patch annotations from the training dataset to improve model focus. While this cleaning resulted in high pixel-level performance reaching the 90th percentile, it adversely affected object-level metrics because the underlying ground truth objects were altered ([00:19:59](#00:19:59)). Hemanth Sarabu clarified that the change in the denominator (number of objects) explains the discrepancy between high pixel-level performance and lower object-level results ([00:24:10](#00:24:10)).

* **Feasibility of K-Fold Cross-Validation**: Hemanth Sarabu proposed performing K-fold cross-validation to gain a better understanding of model performance, given the limited validation support ([00:25:46](#00:25:46)). The team calculated that with six available Graphics Processing Units (GPUs) and a training time of three hours per epoch, they could potentially complete these experiments within 15 hours ([00:27:01](#00:27:01)). However, Pratyaksh Singh cautioned that because the data tiles contain geographic overlaps, they cannot perform a naive automatic split and must manually partition the data to maintain geographic distinction ([00:29:26](#00:29:26)).

* **Proposal for "Probable UXO" Classification**: Pratyaksh Singh proposed introducing a "Probable UXO" class to accommodate objects that visually resemble UXO but were previously labeled as AOI small black patches ([00:34:10](#00:34:10)). This approach aims to prevent the total removal of these objects, instead allowing the model to learn them as a category, which Hemanth Sarabu agreed was a positive direction for improving recall ([00:32:48](#00:32:48)). The team discussed using embedding spaces to determine if UXO and AOI small objects overlap visually ([00:35:34](#00:35:34)).

* **Investigation of Environmental Patterns and Model Failures**: Pratyaksh Singh highlighted a discrepancy where open-source mine data is cylindrical with shadows, whereas the project's UXO data often appears as pits or depressions in side-scan sonar imagery ([00:39:33](#00:39:33)). The team analyzed instances where the model failed to detect objects, observing a recurring pattern where objects located near the image borders were frequently missed ([00:43:20](#00:43:20)). Pratyaksh Singh hypothesized that the model might be overly conservative near borders, and agreed to test this by augmenting the data to remove black edge regions ([00:44:27](#00:44:27)) ([00:46:27](#00:46:27)).

* **Planned Next Steps**: The team established a plan for Pratyaksh Singh to test processing port and starboard data as separate entities, incorporate the "Probable UXO" class, and conduct K-fold cross-validation to confirm model improvements ([00:50:27](#00:50:27)). Additionally, Pratyaksh Singh will experiment with augmenting the "pit" or "depression" features found in the side-scan imagery ([00:48:49](#00:48:49)). Geoff Horowitz requested that Pratyaksh Singh share updated slides and promised to coordinate with the team via Slack to review the progress ([00:30:37](#00:30:37)).

* **Image Generation Parameters**: Pratyaksh Singh discusses the generation of images at 128, 256, and 512 dimensions for starboard usage. They focus on resolving technical issues related to "path center" alignment and removing black areas from the generated images. The participants address blending and visibility settings within the context of Gemini and Slack to improve the output ([00:59:08](#00:59:08)).

* **Model Performance and Augmentation**: Pratyaksh Singh and Sachin Pandey evaluate strategies to improve binary performance. They decide to implement "cut and paste" augmentation methods and identify the \`augmentation.py\` file as the specific location for applying these updates to establish a project baseline ([01:03:47](#01:03:47)).

* **Data Annotation and Raster Image Handling**: Ratul Shashank and Sachin Pandey discuss the processing of ground truth data, specifically regarding input ranges and annotations. They address the technical requirement for identifying object locations using formats such as XTF, PNG, and raster images. The discussion includes references to data file sizes in megabytes (MB) and confirms the necessity of accurately capturing these targets for the model ([01:09:09](#01:09:09)).

* **Server Hosting and Recording**: Sachin Pandey and Ratul Shashank deliberate on API-based hosting solutions and the associated performance constraints for the A3 model. They discuss preferences regarding hosting configurations and conclude the meeting discussion by confirming that the session is being recorded via WhatsApp ([01:15:05](#01:15:05)).

# **📖 Transcript**

Jul 22, 2026

## **Iris Sync \- Transcript**

### **00:03:04**

**Geoff Horowitz:** Hey guys.

**Ratul Shashank:** Hey guys.

**Geoff Horowitz:** Um,

**Sachin Pandey:** Hi everyone.

**Geoff Horowitz:** so I have a hard stop in 30 minutes.

**Hemanth Sarabu:** Hey,

**Geoff Horowitz:** Um, so what I'd like to do is pratak start with you and we'll uh we'll go through everything or as much as we can. Sachin, um, if we run out of time, I will follow up with you later today. I I I assume you'll be awake, so

**Hemanth Sarabu:** Sessions always

**Geoff Horowitz:** Exactly.

**Sachin Pandey:** Okay.

**Geoff Horowitz:** Okay. Uh, project,

**Hemanth Sarabu:** work.

**Geoff Horowitz:** you want to take it away. project, you're muted if you can hear us.

**Pratyaksh Singh:** Hello.

**Geoff Horowitz:** Hey.

**Pratyaksh Singh:** Hi guys. Did you ask something?

**Geoff Horowitz:** Yeah. Do you want to start?

**Pratyaksh Singh:** I actually joined right up.

**Geoff Horowitz:** Oh, no worries. Do you want to start?

**Pratyaksh Singh:** Yeah. Uh, so I just did like kind of a hyperparameter search on the whole. Give me a moment. Wait.

**Hemanth Sarabu:** I could hear the hyper volume was buzzing.

### **00:04:55** {#00:04:55}

**Pratyaksh Singh:** Hello.

**Hemanth Sarabu:** Hey, can you can you hear us?

**Geoff Horowitz:** Hey.

**Hemanth Sarabu:** I don't think Hey,

**Pratyaksh Singh:** Hello.

**Hemanth Sarabu:** brother.

**Geoff Horowitz:** Hello. a month while he was whispering at you. You know, learning rate 0.01 learning rate. No, I'm just

**Hemanth Sarabu:** No, no, not whispering. It was It was buzzing. It was screaming.

**Geoff Horowitz:** kidding.

**Hemanth Sarabu:** It was going. It was very hot and it was a hot day as well in SF.

**Pratyaksh Singh:** Okay.

**Geoff Horowitz:** Hey

**Hemanth Sarabu:** Can you hear

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** us?

**Pratyaksh Singh:** things. Uh so what I was saying is that I did kind of a search on all the augmentation right and the chain I have this Good. comparison table here.

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** So, uh I didn't I didn't search on the model.

**Geoff Horowitz:** Nice.

**Pratyaksh Singh:** I'm just training ResNet 50 and then I searched on 256 uh image size 256 and 512\. The summary is that for my analysis 512 all the 512 size model outperform the 256 pixel model for reset 50\. Right.

### **00:06:30** {#00:06:30}

**Pratyaksh Singh:** And then I tried a bunch of transform and their combination. So perspective I think we know it is a classical transformation. Poison poison is the blending that we discussed on role is roll is uh you know the sonar role augmentation that we discussed and then cut mix is just you know cut image and then paste it on another as simple as that. Very stupid augmentation. And then last one is soft mix. In soft mix uh it is similar to classification but used on segmentation where you you alpha blend two images as well as their mask. So it's not only a binary mask. It is it is kind of uh weight between them. All the models are all the models are trained on all the models are trained on binary classes. So they only predict you know if it is a point of contact or if it's not point of contact and the best model I think is this one which was combination of poison roll and cutmix unfortunately one more thing is that this perspective transformation model it also performed very well as well as if you see the first one is just normal perspective.

### **00:07:46**

**Hemanth Sarabu:** What? What if you mix

**Pratyaksh Singh:** Yeah exactly.

**Hemanth Sarabu:** those?

**Pratyaksh Singh:** So poison roll perspective it comes on third

**Hemanth Sarabu:** Interesting.

**Pratyaksh Singh:** right and I I would like if you look at the graphic right you will see that the object F1 here right the object F1 so there are two annotation annotation one is the one that we trained the model

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** on that I trained the model on and then object uh annotation two is something that such clean things up. So for example some augmentations sorry some objects that weren't actually object such in remove those objects right so in that case what you'll see is that yeah

**Hemanth Sarabu:** So the size threshold

**Geoff Horowitz:** No.

**Pratyaksh Singh:** uh yeah you mostly size threshold type where you know wherever there were so many black

**Geoff Horowitz:** Heat.

**Pratyaksh Singh:** patch the labelers were just calling them as as you know kind of like small patch they were considering them as contact such I think removed some of those examples so The case to note is this here the object level F1 for this and it is basically for poison rule and perspective transform.

### **00:08:56** {#00:08:56}

**Hemanth Sarabu:** Mhm.

**Pratyaksh Singh:** So this one has the best uh you know on annotation. to this performed the best 0.49.

**Hemanth Sarabu:** I

**Pratyaksh Singh:** Okay. Uh so I don't have I think one thing that I

**Geoff Horowitz:** Uh, wait.

**Hemanth Sarabu:** see.

**Geoff Horowitz:** project protection.

**Pratyaksh Singh:** missed.

**Geoff Horowitz:** A few clarifications here number one um the object level F1

**Pratyaksh Singh:** Mhm.

**Geoff Horowitz:** I assume that's using 50% IOU. Is that correct?

**Pratyaksh Singh:** It's using 20% IU.

**Geoff Horowitz:** 20% IOU. Okay.

**Pratyaksh Singh:** Yeah. which is more than because previously the data that we shared with them was 10%

**Geoff Horowitz:** Uh

**Pratyaksh Singh:** IU because I think it was

**Geoff Horowitz:** I think it was I think it was 1% IOU.

**Pratyaksh Singh:** 1% IU.

**Geoff Horowitz:** I think it was

**Pratyaksh Singh:** All right.

**Geoff Horowitz:** 01\.

**Pratyaksh Singh:** Okay. But I think 20% is a safe one especially for segmentation.

**Geoff Horowitz:** Okay. Uh number two,

**Pratyaksh Singh:** That's what I got.

**Geoff Horowitz:** are we using you said we're doing binary are we doing all of the annotation classes or do we remove for example samples?

### **00:09:58** {#00:09:58}

**Geoff Horowitz:** I you

**Pratyaksh Singh:** Yeah, I removed sand ripple and yeah,

**Geoff Horowitz:** know

**Pratyaksh Singh:** I removed sand ripple. The reason for removing sand ripple was that you know sand ripples are so big that they usually dominate the segmentation task.

**Geoff Horowitz:** Mhm.

**Pratyaksh Singh:** So,

**Geoff Horowitz:** Yeah.

**Pratyaksh Singh:** so that's why I removed the sand

**Geoff Horowitz:** Understood.

**Pratyaksh Singh:** ripple.

**Geoff Horowitz:** Is that the only thing that was, is that the only class that was removed?

**Pratyaksh Singh:** Yeah, that was that's the only class that was removed.

**Geoff Horowitz:** Okay.

**Pratyaksh Singh:** only.

**Geoff Horowitz:** Okay. And my last question is, so we're, you know, we're looking at all these uh we're looking at all these different approaches. Do we I I think Hemant asked last time that we do a baseline.

**Pratyaksh Singh:** Mhm.

**Geoff Horowitz:** Is that right? Uh do we have what's what are I mean are all these improvements along the baseline what was the baseline

**Pratyaksh Singh:** Okay.

**Geoff Horowitz:** result

**Pratyaksh Singh:** So, baseline baseline is the default one. Default 5.2, right? So yeah, there is certainly improvement from

### **00:10:47**

**Geoff Horowitz:** okay

**Hemanth Sarabu:** So uh I mean like by baseline I mean if we

**Pratyaksh Singh:** the

**Hemanth Sarabu:** train this model the way we trained it last time

**Pratyaksh Singh:** uh so last time we added one more thing I remember last time uh so if we add the direct copy paste augmentation that we used last Okay. You You meant that.

**Hemanth Sarabu:** I

**Pratyaksh Singh:** You

**Hemanth Sarabu:** so whatever you when I say last time I mean for the first statement of work for our first project

**Pratyaksh Singh:** uh-huh. So the best model from our first project is the baseline. Is that what you Okay.

**Hemanth Sarabu:** correct correct exactly

**Pratyaksh Singh:** So for that I think Sachin can give you the number because he trained on it.

**Hemanth Sarabu:** So, so do we have apples to apples? We can compare object F1 on annotation two and so on.

**Pratyaksh Singh:** Do we have Apple shut? I think I think we will because they they use the same val

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** set.

**Hemanth Sarabu:** Okay,

**Pratyaksh Singh:** Yeah,

**Hemanth Sarabu:** perfect.

### **00:12:04**

**Pratyaksh Singh:** they use the same val set. So that's why that's why we should

**Hemanth Sarabu:** Is it possible to do we have that information

**Pratyaksh Singh:** have such you have that

**Hemanth Sarabu:** handy?

**Pratyaksh Singh:** right? We were discussing before the meeting.

**Sachin Pandey:** the original. What is it?

**Pratyaksh Singh:** Yeah.

**Sachin Pandey:** The basement. It's on the document. Uh let

**Geoff Horowitz:** I think we have it for we have it for a.5 IOU.

**Sachin Pandey:** me

**Geoff Horowitz:** Is that right, Sergeant?

**Sachin Pandey:** the baseline. Yes. Uh if you want for lesser uh it's on this

**Geoff Horowitz:** Mhm.

**Sachin Pandey:** document. Wait. Uh it is there in this HTML.

**Pratyaksh Singh:** Is it this one? All right.

**Sachin Pandey:** Yes.

**Pratyaksh Singh:** I think this is 0.1.

**Geoff Horowitz:** I thought you were doing 2, weren't you?

**Pratyaksh Singh:** I think I can change mine also to one.

**Geoff Horowitz:** I don't really think it matters. I think we just need apples to apples, whatever it is, right?

### **00:13:50**

**Pratyaksh Singh:** Yeah. All right. Okay. So, this is the previous

**Geoff Horowitz:** Hit hit binary up at the top.

**Pratyaksh Singh:** one.

**Geoff Horowitz:** Do you see it next to 0.1? Oh, a little bit down.

**Hemanth Sarabu:** to the right next to next.

**Geoff Horowitz:** Are

**Pratyaksh Singh:** Uh I don't want to do binary.

**Geoff Horowitz:** you

**Pratyaksh Singh:** I don't want to do binary because you know it was trained on sand patches and sand ripples also which I think is

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** going

**Sachin Pandey:** Uh it's object level so like difference will be not

**Pratyaksh Singh:** to no but still it will affect the numbers which what I'm saying is that let's say for example I think we can it's fine it's okay because I have I have the numbers not

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** for binary but like for other things for for class-based basically.

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** All right. Uh so I think this is one of the important one.

**Sachin Pandey:** Are you cool?

**Pratyaksh Singh:** The number of false negatives, right?

**Hemanth Sarabu:** Yeah.

### **00:14:59** {#00:14:59}

**Pratyaksh Singh:** So there are like 11 objects that were missed.

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** Yeah. So for UXO I think this one this is what we discussed right in UXO the baseline that we had was doing better.

**Sachin Pandey:** UX model is uh on different.

**Pratyaksh Singh:** Can you share that

**Sachin Pandey:** Yes. So yeah,

**Pratyaksh Singh:** one?

**Sachin Pandey:** UXO model is the one that we like that I showed in the last meeting.

**Pratyaksh Singh:** Can you share that because I think that is the baseline.

**Sachin Pandey:** Yeah. Uh

**Hemanth Sarabu:** But we have a model that is better.

**Pratyaksh Singh:** Yeah, it's it's like surprisingly very good. I think we miss only one GXO.

**Hemanth Sarabu:** What is the um it might be good to part like a like

**Sachin Pandey:** What is

**Hemanth Sarabu:** a curve ROC car curve A curve F1 curve something like

**Sachin Pandey:** this?

**Hemanth Sarabu:** that. Um is it better in F1 score as well?

**Pratyaksh Singh:** Is it better in F1 score? Yes, I think so.

**Hemanth Sarabu:** Damn. All good.

### **00:16:13** {#00:16:13}

**Hemanth Sarabu:** Wait, this is a vanilla

**Pratyaksh Singh:** Yeah,

**Sachin Pandey:** That is the model.

**Pratyaksh Singh:** because

**Sachin Pandey:** This is the binding model.

**Hemanth Sarabu:** model.

**Sachin Pandey:** You have to select the different one.

**Pratyaksh Singh:** how can I select it the or

**Geoff Horowitz:** Is it the

**Sachin Pandey:** Just click on multiclass UXO V2. Yeah. V2.

**Geoff Horowitz:** top?

**Pratyaksh Singh:** with?

**Sachin Pandey:** V2.

**Pratyaksh Singh:** Okay. One moment.

**Sachin Pandey:** You want me to share it? I It's already loaded on my

**Pratyaksh Singh:** Okay. Can you please I will show you the model which I want you to compare

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** with.

**Sachin Pandey:** So on the right side the That's the model we are looking at. I 0.1 and for you. So it's missing around six of them and uh mclassifying one in other class

**Hemanth Sarabu:** Um, what can can you are you able to summarize The numbers. What numbers can we compare

**Sachin Pandey:** So because we are like treating it as a binary so like even this was deducted so we will not be counting this one.

### **00:18:13** {#00:18:13}

**Sachin Pandey:** So false uh negatives are like count is six out of like 15

**Hemanth Sarabu:** For the baseline model,

**Sachin Pandey:** for UX. Yeah, for

**Hemanth Sarabu:** the false negative is okay.

**Sachin Pandey:** the

**Hemanth Sarabu:** And then for the best current model,

**Pratyaksh Singh:** It is uh nine.

**Sachin Pandey:** rest

**Pratyaksh Singh:** There are nine missed objects. Sar link if you can open it.

**Sachin Pandey:** this one like this

**Pratyaksh Singh:** Yeah. Uh not not perspective 5.2.

**Sachin Pandey:** model.

**Pratyaksh Singh:** It is poison roll cutm mix. Yeah, there are these are the object and I think like there is one object object get repeated too in the validation

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** set. So the same object is in two different I just

**Sachin Pandey:** And like in short the new model we trained is like the training matrix looks good. It was looking better like it they were in 98 and 99 but the performance on like object level performance is bad. This is the pixel level but on object level they are uh like

### **00:19:59** {#00:19:59}

**Hemanth Sarabu:** for which one.

**Sachin Pandey:** the one where like I cleaned a lot of data uh I removed around 1,300 annotations from the annotations and then trainer another model. These are the V3 models.

**Hemanth Sarabu:** Okay, these are baseline but you cleaned up the

**Sachin Pandey:** No, these are Yeah,

**Hemanth Sarabu:** data. Okay. And

**Sachin Pandey:** but it it was not performing good on the like pixel level like the

**Hemanth Sarabu:** the

**Sachin Pandey:** precision were very bad for all of them model is

**Hemanth Sarabu:** what annotations did you

**Sachin Pandey:** predicting.

**Hemanth Sarabu:** remove?

**Sachin Pandey:** So if you see here,

**Hemanth Sarabu:** Just just uh just

**Sachin Pandey:** so there were good of yeah in words like first there were the

**Hemanth Sarabu:** worse.

**Sachin Pandey:** mistakes which are like random noises because the like we uh one data set was not classifi like labeled So to speed up the labeling I predicted on it and share the prediction with the labelers so they can fix it. There were like few like these small mistakes which were present in the data set which was not spotted in the sew.

### **00:21:11**

**Sachin Pandey:** So those were like those were removed and also with that the most of the AY small or black patches were removed. So only small black objects will be AI and uh UXO sorry AI small and UXO. So most of most of the uh point annotations were removed from black patch and mistakes. So like anything like these all things are removed because they were very

**Hemanth Sarabu:** But your val your validation also

**Sachin Pandey:** small.

**Hemanth Sarabu:** change these

**Sachin Pandey:** No validation set is still same. All the files are same just the annotation annotations are

**Hemanth Sarabu:** the validation

**Sachin Pandey:** different.

**Hemanth Sarabu:** annotations have also changed right so the way you compute your metrics

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** the the the the data set you're computing your metrics against has changed

**Sachin Pandey:** Yeah. Like the grounded object is 240 255 then

**Hemanth Sarabu:** different

**Sachin Pandey:** yeah it is also changed.

**Hemanth Sarabu:** which means that for an applesto apples comparison you need to rerun your validation um predictions of the other models on the new corrected annotations Thanks.

### **00:22:49**

**Pratyaksh Singh:** I think what he's saying is some different problem. His pixel level matrix is pretty good in the '90s, but when he converts it into object level matrix, it goes down considerably.

**Hemanth Sarabu:** That that uh that's um that is not my understand. Okay, here's my understanding. My understanding is there were a lot of these small annotations over there in the data set. Sachin asked the labelers to remove those smaller noisy annotations, right?

**Sachin Pandey:** uh including the noisy annotation. I removed all of these also. These any small patches which can be confused as a UXO or AI

**Hemanth Sarabu:** Small.

**Sachin Pandey:** small those were also removed. So only small objects black small objects will be only classified as either UXO or AI small blacks. So all of these you're seeing all the like small a black patches were removed from uh training data. So model model learns that black patches will be only blue. Yeah. Both of them.

**Hemanth Sarabu:** Okay. So the number of objects has also changed.

### **00:24:10** {#00:24:10}

**Hemanth Sarabu:** Your denominator has changed. So with these small objects,

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** your number of pixels doesn't actually change a lot, but the number of objects changes a lot, right?

**Sachin Pandey:** Yeah.

**Hemanth Sarabu:** So that could that could explain why your pixel level performance is good but your object level performance suddenly changed because previously maybe you were getting all these small objects and because their number was huge. Um you know

**Sachin Pandey:** Previously the pixel level were better and object level was bad because

**Hemanth Sarabu:** the

**Sachin Pandey:** of the mistakes or small very small mistakes because if you see the pixel level matrix these are very very good like these are the pixel matrix of the same model.

**Hemanth Sarabu:** Okay. I want to understand one thing. So I Well, so what are we saying? The baseline model is still better. We doing an apple comparison or no

**Sachin Pandey:** Uh, it's not Apple to app.

**Pratyaksh Singh:** for apples to apples only for UXO the baseline model

**Sachin Pandey:** Yeah, go ahead.

**Pratyaksh Singh:** is better if you only consider the true UXO that they gave us and not like the other classes that we added.

### **00:25:46** {#00:25:46}

**Pratyaksh Singh:** Does it make sense?

**Hemanth Sarabu:** Okay. But overall performance the newer model is

**Pratyaksh Singh:** Yeah. Yeah. Because this these black patch so AI small black or things that

**Hemanth Sarabu:** better.

**Pratyaksh Singh:** Sachin removed there this model is performing pretty good.

**Hemanth Sarabu:** What do you mean by there this models for these small

**Pratyaksh Singh:** So the new model that we train the EOI small black uh so these are like small black object which may look like UXOS but they haven't labeled it as UXO if you considered that then the current model is is doing pretty good.

**Hemanth Sarabu:** So the support for UX is very small,

**Pratyaksh Singh:** Yeah,

**Hemanth Sarabu:** right?

**Pratyaksh Singh:** it's only I think 13 object 13 or 14 object in the whole trading set. Sorry, in the whole validation

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** set.

**Sachin Pandey:** Yeah.

**Hemanth Sarabu:** Can we do K for K4 validation? Can't believe I'm saying it,

**Pratyaksh Singh:** Can we do K4 validation?

**Hemanth Sarabu:** but I guess

**Pratyaksh Singh:** We can. Yeah, we can. We'll take

### **00:27:01** {#00:27:01}

**Hemanth Sarabu:** The reason I say that is because uh yeah it will take time but just take

**Pratyaksh Singh:** time.

**Hemanth Sarabu:** just take the you don't have to do all models just take the two the baseline and your best model and cycle through different

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** uh basically train val splits right

**Pratyaksh Singh:** Okay.

**Hemanth Sarabu:** um the idea just being can you cycle through different UXO samples invalidation and retrain each time and maybe com so okay I'll we actually have a classic problem which is our support is so small validation so do we

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** actually know which model is better so and if

**Pratyaksh Singh:** Understood.

**Hemanth Sarabu:** it's actually going to take just a few hours uh how many hours for a full training of one

**Pratyaksh Singh:** So I trained only 75 epox which I think hasn't saturated yet but it had started to. So for 75 epoch it took around 3 hours.

**Hemanth Sarabu:** Okay, let's say 75\. I would do this for 3 hours.

**Pratyaksh Singh:** So,

**Hemanth Sarabu:** Uh, we have six GPUs, right? Five, six GPU 60\.

### **00:28:20**

**Geoff Horowitz:** project. Was that using all the GPUs or one GPU or what was the one

**Hemanth Sarabu:** Um

**Pratyaksh Singh:** one GPU, one GPU. I was running experiments

**Geoff Horowitz:** GPU?

**Pratyaksh Singh:** parally.

**Hemanth Sarabu:** okay do you think okay so each each experiment is three GPU hours we have six GPUs let's say we want to do 15 per model that's 30 \* 3 90 GPU hours divided by 6 is 15 right so we could potentially get an answer to this 15 hours or

**Pratyaksh Singh:** Yeah, one more thing but I also want to bring out is that before this

**Hemanth Sarabu:** so.

**Pratyaksh Singh:** meeting we were discussing we were like going through the prediction and the images and like there are a lot of objects that look like UXO which they haven't marked as marked as UXO right like uh do you agree with it like you know there are a lot of object which which you can't differentiate

**Sachin Pandey:** Yeah.

**Pratyaksh Singh:** from the from from the actual that they marked as UX

**Sachin Pandey:** Like Yeah. Most of the things in a small black it looks like

### **00:29:26** {#00:29:26}

**Pratyaksh Singh:** and

**Sachin Pandey:** Excellent.

**Pratyaksh Singh:** So one thing that we were thinking is and a like one more thing one more problem with the

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** kful cross validation that you're talking about is that there is a lot of overlap between the tiles. So the images are not unique.

**Hemanth Sarabu:** Mhm.

**Geoff Horowitz:** Oh, Wait.

**Pratyaksh Singh:** Go ahead J.

**Hemanth Sarabu:** The images are locations are not unique.

**Pratyaksh Singh:** Yeah the location are not unique.

**Geoff Horowitz:** So just just to recap here, project the the existing validation set is geographically bound, right? We yeah,

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** we we took a geographic area and made that the validation set.

**Pratyaksh Singh:** Mhm.

**Geoff Horowitz:** You're saying that by doing a K-fold validation,

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** uh, we're going to end up mixing these geographies and it won't be as um, geographically distinguished as it is right now.

**Pratyaksh Singh:** Yeah. I mean like we can't do it naively, right? we'll have to maybe manually split it into six sets and then do it. So we'll we can't we can't do like automatic split.

### **00:30:37** {#00:30:37}

**Pratyaksh Singh:** But like these are some examples. If you see the below images, they look a lot like UXO but they kind of are not marked not marked as

**Sachin Pandey:** This one.

**Geoff Horowitz:** Um,

**Sachin Pandey:** We

**Pratyaksh Singh:** UXO.

**Geoff Horowitz:** can you can you can you bring can you throw these on a slide? Make sure that they have their,

**Sachin Pandey:** got

**Geoff Horowitz:** you know, their their source locations, right? Um, and I I can also bring this up to Bridget and just say,

**Pratyaksh Singh:** Mhm.

**Geoff Horowitz:** you know, this is going to be a a known issue. Um,

**Pratyaksh Singh:** Yeah. And also

**Geoff Horowitz:** but also project I'm gonna need to run in one second,

**Pratyaksh Singh:** like

**Geoff Horowitz:** but um did you did you get a chance to generate some slides

**Sachin Pandey:** That's what we got.

**Geoff Horowitz:** for Okay,

**Pratyaksh Singh:** Yes.

**Geoff Horowitz:** you did.

**Pratyaksh Singh:** Yes. All

**Geoff Horowitz:** Can can you just can you share them with me and I'll uh I'll respond on Slack and uh we can connect we can connect you know tomorrow morning your time or uh or

### **00:31:25**

**Pratyaksh Singh:** right.

**Geoff Horowitz:** tomorrow around this time too if needed.

**Pratyaksh Singh:** All right. All

**Geoff Horowitz:** Okay. All right. I'm going to drop off.

**Pratyaksh Singh:** right.

**Geoff Horowitz:** Uh I'm recording so I'll I'll review everything later. Also, Sachin, I will um I'll connect with you later also. Thanks, guys.

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** Yeah, one more thing I also wanted to bring out is that the objects are not unique. So those 13 objects that are in validation set I think there are

**Sachin Pandey:** Oops.

**Pratyaksh Singh:** like six six uniques unique UXOs five or six unique. So then correct me if I'm wrong, but how many unique UXOs are there in the 13

**Hemanth Sarabu:** I thought it was 15\.

**Pratyaksh Singh:** objects?

**Sachin Pandey:** Yeah. 13 to 15 in

**Pratyaksh Singh:** So in the validation set or everything combined.

**Sachin Pandey:** total every everything combined.

**Pratyaksh Singh:** So I mean there were like only 15 15 like unique UX everything combined.

**Hemanth Sarabu:** So, so this crossful validation is actually I think it is better.

### **00:32:48** {#00:32:48}

**Hemanth Sarabu:** It is actually the reason I've never suggested this is because

**Pratyaksh Singh:** Mhm. Because of the time, right?

**Hemanth Sarabu:** um not not uh not just the time We usually have enough of a data set to be relatively confident that one model is better than the other, right? Our validation set is big enough. You get what I mean?

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** Our support is big enough,

**Pratyaksh Singh:** Got

**Hemanth Sarabu:** but now it's not big enough. So,

**Pratyaksh Singh:** it.

**Hemanth Sarabu:** it may be worth like cycling through doing cross validation. Um,

**Pratyaksh Singh:** Got it.

**Hemanth Sarabu:** you think we shouldn't do

**Pratyaksh Singh:** No, no. Uh I don't think we shouldn't do it.

**Hemanth Sarabu:** it?

**Pratyaksh Singh:** I'm just, you know, I'm just I'm noting my concern so that we can discuss and do it correctly. So I'm just coming up with things that can go wrong so that we fix it before we do it.

**Hemanth Sarabu:** Got it. Um,

**Pratyaksh Singh:** So one thing that I was thinking of is instead of having this AI black which we consider as useless right because these are classes that we add to help the model learn and to increase the recall right so

### **00:34:10** {#00:34:10}

**Hemanth Sarabu:** Yes.

**Pratyaksh Singh:** instead of doing that I was thinking of coming up with one something like probable uxo

**Hemanth Sarabu:** Yes.

**Pratyaksh Singh:** class right which contains object which look a like UXO and in our internal evaluation evaluation we can treat it as UXO.

**Hemanth Sarabu:** H. That's a interesting idea.

**Pratyaksh Singh:** Does that make

**Hemanth Sarabu:** It's an interesting idea. Yeah. Yeah. Yeah.

**Pratyaksh Singh:** sense?

**Hemanth Sarabu:** No, I I think that sounds like a good idea. Hey, yeah, it's a good idea. Actually, if you look at the confusion matrix and see what what is our we predicting any do we have any predictions that are actually AOI but we put in UXO and maybe the that'll be interesting to look at to see if it actually looks like UXO. The model is putting it in UXO.

**Sachin Pandey:** Uh we have few and then which is marked as a and model is putting into UX. So like this

**Hemanth Sarabu:** Yeah.

**Sachin Pandey:** one.

**Hemanth Sarabu:** Do you guys think that that looks like UXO or No.

### **00:35:34** {#00:35:34}

**Sachin Pandey:** UX

**Hemanth Sarabu:** This is cool, by the way. Like being able to click on the confusion measure.

**Sachin Pandey:** UXO is uh it is marked as UX model moved it to Y class.

**Hemanth Sarabu:** Mhm.

**Sachin Pandey:** Alternative will

**Hemanth Sarabu:** Uh, do you have the transfer?

**Sachin Pandey:** be

**Pratyaksh Singh:** The search in the background one.

**Hemanth Sarabu:** So,

**Pratyaksh Singh:** Search in go up the top right one. The top right.

**Hemanth Sarabu:** See you

**Pratyaksh Singh:** Yeah, that one. Here your prediction is UX.

**Sachin Pandey:** Let me

**Pratyaksh Singh:** No, that's

**Hemanth Sarabu:** guys.

**Sachin Pandey:** these where ground is background and model put it into

**Pratyaksh Singh:** incorrect.

**Sachin Pandey:** UXO. This was the one we just saw here.

**Hemanth Sarabu:** Wow, that is um really small. Okay. Yeah, that sounds like a good idea. Sounds like a good idea. Sounds like a good idea. I wonder if you could also look at the embeddings.

**Pratyaksh Singh:** But how will like embedding help in case of segmentation?

**Hemanth Sarabu:** Um I'm I'm curious to see if in embedding space there are the UXO and AOI small are actually close and there are a bunch of um points that overlap and that is Actually, those are actually the examples you're looking for which are in embedding space close and they're close in embedding space because they're visually

### **00:37:27**

**Hemanth Sarabu:** similar.

**Pratyaksh Singh:** Got it. Compare

**Hemanth Sarabu:** You don't have to do it. It's just an idea.

**Pratyaksh Singh:** it.

**Hemanth Sarabu:** I mean, if we want to go label it or tag it, that's totally fine.

**Pratyaksh Singh:** Uh if we can get like that's also not possible like if we can get objects we can face them. if we get like UXO objects.

**Hemanth Sarabu:** If we can get objects.

**Pratyaksh Singh:** So for example like even if you don't get the whole data set if you can

**Hemanth Sarabu:** Huh?

**Pratyaksh Singh:** just get uh get like you know how UX or looks different cases right we can aug

**Hemanth Sarabu:** Mhm.

**Pratyaksh Singh:** data set by pasting it but I don't know how to get

**Hemanth Sarabu:** Yeah. Yeah.

**Pratyaksh Singh:** it

**Hemanth Sarabu:** You mean from outside? Outside outside this data set.

**Pratyaksh Singh:** yeah from open source or in any other way

**Hemanth Sarabu:** We I thought we already pulled the open source stuff,

**Pratyaksh Singh:** yeah but here what they described as mines was

**Hemanth Sarabu:** right?

**Pratyaksh Singh:** completely different.

### **00:39:33** {#00:39:33}

**Pratyaksh Singh:** In fact like we were able to uh in fact like we were able to generate it procedurally but so their mines what they classified as mines were cylindrical and yeah it was cylindrical and there was a shadow to it. But here what they describe as mines is one of the pattern that I've saw is I've seen is it's kind of a pit in the in the side scale owner. It looks something like

**Hemanth Sarabu:** This this is not bedrock.

**Pratyaksh Singh:** that.

**Hemanth Sarabu:** This is outside.

**Pratyaksh Singh:** So no so in outside it is uh for open source it is elongated with a shadow.

**Hemanth Sarabu:** Oh, okay. Okay.

**Pratyaksh Singh:** So it is cylindrical with a shadow. For bedrock it is something like a pit or you know sudden depression in

**Hemanth Sarabu:** Yeah,

**Pratyaksh Singh:** the in the sides scan

**Hemanth Sarabu:** got it. Got it.

**Pratyaksh Singh:** image.

**Hemanth Sarabu:** And also these these these objects are these uh renders are lower res, right? So it's that's why you're saying it doesn't actually look like an object object.

### **00:40:39**

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** It looks like whatever you describe. It's like a pit.

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** Is that right? The low resolution makes it look like AOI

**Pratyaksh Singh:** Yeah. Yeah, it does.

**Hemanth Sarabu:** small.

**Pratyaksh Singh:** And I think the model has a lot of false the model has like kind of a lot of false positive. Sorry. Uh what do you say?

**Hemanth Sarabu:** What is the Yeah.

**Pratyaksh Singh:** No,

**Hemanth Sarabu:** What is the

**Pratyaksh Singh:** not false positive. So false negative to learn from.

**Hemanth Sarabu:** precision?

**Pratyaksh Singh:** So that's why it's object-wise precision is higher than its recall.

**Hemanth Sarabu:** Um Oh, I I lost you there. I lost

**Pratyaksh Singh:** Okay,

**Hemanth Sarabu:** you.

**Pratyaksh Singh:** I'll show it to you. Right, can you see my screen?

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** So, these are the UXOs that the model missed. Do do you see the slides?

**Hemanth Sarabu:** Yes. Yes. Yes. Yes.

**Pratyaksh Singh:** Okay.

**Hemanth Sarabu:** Yes.

**Pratyaksh Singh:** Now if I show it to you on

### **00:41:54**

**Hemanth Sarabu:** It just put it in background.

**Pratyaksh Singh:** maybe yeah it put it in background.

**Hemanth Sarabu:** Okay. Uh, sorry I couldn't play with this for a little longer.

**Pratyaksh Singh:** because

**Hemanth Sarabu:** What What is the it put it in

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** background pre size based filtering. So it didn't even get to the size based. There's no mask at all.

**Pratyaksh Singh:** No, no.

**Hemanth Sarabu:** And um what what is surprising to me is that the other model is okay. Okay. So Okay, fine. You're saying that these are these are

**Pratyaksh Singh:** These are like really tiny.

**Hemanth Sarabu:** tiny.

**Pratyaksh Singh:** If I show it to you on the uh is it here? Yeah. Like so this is here a small one.

**Hemanth Sarabu:** Where? Where is it?

**Pratyaksh Singh:** So it's here right here.

**Hemanth Sarabu:** Uh, your cursor is

**Pratyaksh Singh:** So the uh I don't know why I'm so sorry.

**Hemanth Sarabu:** in.

**Pratyaksh Singh:** to the green one that you see in the below image.

**Hemanth Sarabu:** Yeah,

### **00:43:20** {#00:43:20}

**Pratyaksh Singh:** Can you map it?

**Hemanth Sarabu:** that one. Yeah,

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** I see it. Okay, that is not Yeah,

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** that's not I guess that's not that small but

**Pratyaksh Singh:** And this is this is the model

**Hemanth Sarabu:** yes.

**Pratyaksh Singh:** prediction.

**Hemanth Sarabu:** Uh, okay. And even if you mess with confidence,

**Pratyaksh Singh:** It doesn't predict anything.

**Hemanth Sarabu:** there's nothing. What if you mess with

**Pratyaksh Singh:** There is something.

**Hemanth Sarabu:** confidence?

**Pratyaksh Singh:** No, there is nothing here. And then for other examples, let me see this.

**Hemanth Sarabu:** Nice. Very nifty. You can just copy it.

**Pratyaksh Singh:** Yeah, great use of again it's something similar. I think it's the same object from the previous image.

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** The model didn't predict anything

**Hemanth Sarabu:** Hey, uh but I know you're removing that black area,

**Pratyaksh Singh:** yet.

**Hemanth Sarabu:** right? Is it possible that some of the black area was removed and

**Pratyaksh Singh:** I'm removing the bracket.

**Hemanth Sarabu:** you the border?

### **00:44:27** {#00:44:27}

**Pratyaksh Singh:** No, no, not not in this iteration. Not in this iteration.

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** One thing that might have happened is when I was augmenting it, right? I so when I was copy pasting it I made sure that no object was added in the black region. So wherever there is padding or this kind of black region in the middle nothing gets added there.

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** So it might be possible that the model got you know very conservative and it

**Hemanth Sarabu:** Hello.

**Pratyaksh Singh:** Don't add objects here,

**Hemanth Sarabu:** Yeah. Can we look at the other ones to see if that is the pattern?

**Pratyaksh Singh:** right? Yeah. Yeah. Uh, no,

**Hemanth Sarabu:** It is missing.

**Pratyaksh Singh:** that's not the pattern actually. I think this is where it missed it and then there was so this

**Hemanth Sarabu:** Mhm. Look, look, look like uh uh two three of those are around the

**Pratyaksh Singh:** one

**Hemanth Sarabu:** border. Four.

**Pratyaksh Singh:** two around the border.

**Hemanth Sarabu:** Look.

### **00:45:20**

**Pratyaksh Singh:** This one also you're adding content.

**Hemanth Sarabu:** So, I'm looking at uh row one, column 2, 3, 4\.

**Sachin Pandey:** Five are around the border.

**Hemanth Sarabu:** And then row two, column two and

**Pratyaksh Singh:** I got it.

**Hemanth Sarabu:** four.

**Pratyaksh Singh:** Okay. I think it's not I think we can look at the whole thing. There's only 13 images instead of copy pasting. So this one it got right.

**Hemanth Sarabu:** Yeah, good. Good.

**Pratyaksh Singh:** Now going on to the next one. This one it didn't get.

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** Let's go with the theory that if it's near border it it doesn't get it right.

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** But I think this is like very faint and difficult example maybe.

**Hemanth Sarabu:** Okay. Okay.

**Pratyaksh Singh:** Anyways,

**Hemanth Sarabu:** Hey.

**Pratyaksh Singh:** this

**Hemanth Sarabu:** Um. Okay.

**Pratyaksh Singh:** one.

**Hemanth Sarabu:** It didn't get Hey, actually one thing is can it got this right?

**Pratyaksh Singh:** Mhm. Yeah.

**Hemanth Sarabu:** Can you go back to the previous one?

**Pratyaksh Singh:** Okay.

### **00:46:27** {#00:46:27}

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** Uh, okay. This guy. So,

**Pratyaksh Singh:** This

**Hemanth Sarabu:** and you did a cut mix, a copy paste of this all of these, right?

**Pratyaksh Singh:** a copy paste of all of these objects. Yes.

**Hemanth Sarabu:** Okay. One easy test is you actually grab this, pull it a little away from the border and re repredict and see if it starts to to predict it.

**Pratyaksh Singh:** Okay, I can do that.

**Hemanth Sarabu:** That is

**Pratyaksh Singh:** What I will do is I will fill this hole.

**Hemanth Sarabu:** one.

**Pratyaksh Singh:** I will remove the black area. I will join these two together.

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** Right. Okay.

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** This one it got right. It's really funny that why did it not predict the one at the just if you if you see just below

**Hemanth Sarabu:** Mhm.

**Pratyaksh Singh:** it right.

**Hemanth Sarabu:** Yeah. Yeah.

**Pratyaksh Singh:** It It's interesting that it didn't get

**Hemanth Sarabu:** Yeah,

**Pratyaksh Singh:** it.

**Hemanth Sarabu:** I mean that it could easily look be noise.

### **00:47:27**

**Hemanth Sarabu:** I actually didn't even know those were two different objects.

**Pratyaksh Singh:** Yeah, exactly. And this kind of things worries me.

**Hemanth Sarabu:** Okay. Mhm. And only one of them got it.

**Pratyaksh Singh:** Yeah,

**Hemanth Sarabu:** Okay. At least one got

**Pratyaksh Singh:** this is very weird. Uh yeah,

**Hemanth Sarabu:** it.

**Pratyaksh Singh:** this I think it got partially test one,

**Hemanth Sarabu:** Mhm.

**Pratyaksh Singh:** right?

**Hemanth Sarabu:** A couple of them got okay. Hey, it might be good to expose the confidence.

**Pratyaksh Singh:** This one is near the borders,

**Hemanth Sarabu:** This one.

**Pratyaksh Singh:** so it didn't get it. Okay.

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** This one is same object near the border. Didn't get it. This one is near the center. It got it. Nice.

**Hemanth Sarabu:** H.

**Pratyaksh Singh:** Didn't get it again.

**Hemanth Sarabu:** Well, I guess we could call that maybe maybe near the border.

**Pratyaksh Singh:** But I think I think I confirmed for it.

**Hemanth Sarabu:** Hey, uh I have a call coming up.

### **00:48:49** {#00:48:49}

**Hemanth Sarabu:** I need to go in like two minutes to prepare.

**Pratyaksh Singh:** Okay. Okay. I I will I'll verify the case for I think that is one of the most plausible reasons we have right this it didn't get for some reason again this depression here right I think I think I can augment this maybe I can augment this depression I mean I can

**Sachin Pandey:** terminal is visible.

**Pratyaksh Singh:** generate

**Sachin Pandey:** Only terminal is visible.

**Pratyaksh Singh:** Wow I've got stuck Let me switch. Is it I was saying that this it didn't

**Sachin Pandey:** Yeah.

**Pratyaksh Singh:** get and this is pretty interesting because it is just depression. There should be a way to augment this. Sorry. Like generate this. Try it out. And then this is like just unbelievable.

**Hemanth Sarabu:** What do you

**Pratyaksh Singh:** There are two there are two objects here which are not

**Hemanth Sarabu:** mean?

**Pratyaksh Singh:** visible. Right? And it got one of them but not the other one.

**Hemanth Sarabu:** See, can't actually see, but hey, I got to draw.

### **00:50:27** {#00:50:27}

**Hemanth Sarabu:** It looks like it looks like there's a strong uh a strong hypothesis that we can test

**Pratyaksh Singh:** All right. Mhm.

**Hemanth Sarabu:** out, right?

**Pratyaksh Singh:** Got it. Okay. I'll also I'll also train with uh port and starboard as

**Hemanth Sarabu:** Nice.

**Pratyaksh Singh:** separate as we discussed previously. And then the probable UXO1 UXO class we I'll I'll give that

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** a try too. And then I think once we have once we have that once we have like one of our model we will end it with a cross validation to confirm everything good.

**Hemanth Sarabu:** Okay, sounds good. Thanks. Thanks,

**Pratyaksh Singh:** Okay.

**Hemanth Sarabu:** guys. I'll talk to you later. Yeah, can you drop a an update once you have some results?

**Pratyaksh Singh:** All right. Yeah, I

**Hemanth Sarabu:** Thanks a lot,

**Pratyaksh Singh:** will.

**Hemanth Sarabu:** guys.

**Pratyaksh Singh:** Okay. Byebye.

**Sachin Pandey:** Open

**Pratyaksh Singh:** Uh you

**Sachin Pandey:** text.

**Ratul Shashank:** Uh

**Pratyaksh Singh:** have that script to generate uh port and starboard as separate right Sachin once you are done with this probable UXO

### **00:51:38**

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** class I I won't suggest that you know don't move the black patch or AOI small right don't move it can you just uh uh don't remove Can you just move things that look like UXO or things that the labelers missed to the UXO class if possible? Does it make sense?

**Sachin Pandey:** Yeah,

**Pratyaksh Singh:** Or sorry to the probable UXO

**Sachin Pandey:** that's Yeah.

**Pratyaksh Singh:** class.

**Sachin Pandey:** So like that's the question like when I uh let me know when screen is visible.

**Pratyaksh Singh:** Okay.

**Sachin Pandey:** Uh give me a second. It's shorter.


### **01:46:11**

**Sachin Pandey:** Okay. So in the V3 uh version three of the model training we updated the annotation by removing

### **01:46:16**

**Geoff Horowitz:** Okay.

**Sachin Pandey:** a lot of blacks patches which were which we thought will confuse were confusing the

**Geoff Horowitz:** Okay.

**Sachin Pandey:** model where model was not able to perform well on uh like AOI. So this was the old model.

**Geoff Horowitz:** Okay.

**Sachin Pandey:** If you see like these black patches, a lot of like background was classified as black patches. So we wanted to reduce these things. So model can like don't confuse with other but like we removed a lot of it like around 1,300 annotations were removed in the previous round.

**Geoff Horowitz:** Okay.

**Sachin Pandey:** But it it like oh the what's the pixel wise validation were good but in object level it was not performing well

**Geoff Horowitz:** Right.

**Sachin Pandey:** and lot of uh false positive are there so like so the plan because it didn't work out next plan is to like only remove the ones which are required so if I show you the gallery like what type of mistakes I'm removing uh only so the which I have removed till now. So these things these are all the mistakes uh

### **01:47:35**

**Geoff Horowitz:** So, so you're saying you're adding back in some of the ones that you removed.

**Sachin Pandey:** I'm redoing it again like I uh I'm redoing the like removal again from scratch.

**Geoff Horowitz:** Hey

**Sachin Pandey:** because these small mistakes were small parts. So it can be done quickly instead of removing the black patches which we removed earlier. So like these mistakes which we are removing this only like uh pollute the matrix it is like a mistakes uh

**Geoff Horowitz:** Wait,

**Sachin Pandey:** and

**Geoff Horowitz:** can you can you show me one example like that?

**Sachin Pandey:** yeah so these things are like

**Geoff Horowitz:** Okay.

**Sachin Pandey:** not correct.

**Geoff Horowitz:** Yeah.

**Sachin Pandey:** These are like random noises which like which model is predicting

**Geoff Horowitz:** Yeah.

**Sachin Pandey:** these small ones. So these which we are removing right now and once it's done I will just

**Geoff Horowitz:** Yes.

**Sachin Pandey:** quickly fix few of these also because there are uh like if there are few I will skip transform if

**Geoff Horowitz:** So what what what were we doing before that we are redoing now?

### **01:48:47**

**Sachin Pandey:** uh

**Geoff Horowitz:** That's my question. my

**Sachin Pandey:** what we were doing before

**Geoff Horowitz:** question.

**Sachin Pandey:** uh

**Geoff Horowitz:** Let me let me back up. Sin, you just said that you went through and you removed, you know, whatever you said,500 annotations,

**Sachin Pandey:** 1 1300\.

**Geoff Horowitz:** 1300 annotations,

**Sachin Pandey:** So if you see these all of these I have removed all of

**Geoff Horowitz:** but now now we're re Uhhuh. Yeah.

**Sachin Pandey:** these because like any small m

**Geoff Horowitz:** Okay.

**Sachin Pandey:** annotation which could be similar to UXO or AY small black. I am removing those. Removing all the small black patches like all of these were

**Geoff Horowitz:** Okay.

**Sachin Pandey:** removed. So like

**Geoff Horowitz:** Are those are those just ground?

**Sachin Pandey:** model

**Geoff Horowitz:** Are those just background or any of those

**Sachin Pandey:** those were just background like they were present in the background.

**Geoff Horowitz:** those were Got it.

**Sachin Pandey:** None of this are like provided by the client. These are diagram that we just can

**Geoff Horowitz:** No. Got it.

### **01:49:55**

**Geoff Horowitz:** Okay.

**Sachin Pandey:** mark.

**Geoff Horowitz:** Fine. Okay. That that makes sense.

**Sachin Pandey:** This is looking like a UXO.

**Geoff Horowitz:** That seems reasonable.

**Sachin Pandey:** Is it looking like a UXO?

**Geoff Horowitz:** So that this this example is that one you just showed. This is just background, right? I think that's what you're saying.

**Sachin Pandey:** Yeah, these are like you see these small ones. There were lot of like black patches like these.

**Geoff Horowitz:** Yeah.

**Sachin Pandey:** So that's why I was removing it. So I was like trying to only keep the bigger ones.

**Geoff Horowitz:** Got it.

**Sachin Pandey:** The model only think like only bigger ones are the like things we want and skip start ignoring the

**Geoff Horowitz:** Uh-huh.

**Sachin Pandey:** small ones but it didn't work out that well.

**Geoff Horowitz:** I see.

**Sachin Pandey:** So like currently H.

**Geoff Horowitz:** And the ones in that image you just showed

**Sachin Pandey:** Yeah, this

**Geoff Horowitz:** Uh if we can see the the two marks on the

**Sachin Pandey:** one.

**Geoff Horowitz:** bottom on the bottom right hand.

### **01:50:54**

**Geoff Horowitz:** Yeah, those those are objects of some

**Sachin Pandey:** Yeah,

**Geoff Horowitz:** sort.

**Sachin Pandey:** these are yeah these are the AI supports which we have moved to black patch because they look like like

**Geoff Horowitz:** Okay, got it.

**Sachin Pandey:** black.

**Geoff Horowitz:** Okay. All right.

**Sachin Pandey:** So the next iteration we are we are just trying to increase these values as much as we can so we can like give this to client. Currently the recall are like very high. You just need to sorry this was the one here.

**Geoff Horowitz:** Those are object level or those are

**Sachin Pandey:** These are object level. These are pixel level is

**Geoff Horowitz:** okay. No, no.

**Sachin Pandey:** below.

**Geoff Horowitz:** I I think object level is better. Object is better.

**Sachin Pandey:** In pixel level we are already like we will be dropping these two things sand ripple and sand

**Geoff Horowitz:** Uh okay.

**Sachin Pandey:** patch and only we'll focusing on only these.

**Geoff Horowitz:** Um we

**Sachin Pandey:** So after dropping this because these are the bigger objects,

**Geoff Horowitz:** should we

### **01:51:48**

**Sachin Pandey:** the pixel level will also like start to make sense.

**Geoff Horowitz:** should we should call these when we give it to the client we should call these classes something else. Um I don't know what to call them.

**Sachin Pandey:** Yeah, it will be like windmill base or something like

**Geoff Horowitz:** Yeah. Yeah. Yeah. Something like that.

**Sachin Pandey:** that. Yeah.

**Geoff Horowitz:** Um, yeah, we got we got to think about that.

**Sachin Pandey:** So So that's the Yeah.

**Geoff Horowitz:** Okay, that's minor.

**Sachin Pandey:** So the new prediction will like only like we will first fix false uh and false positive

**Geoff Horowitz:** Um,

**Sachin Pandey:** annotations and then retrain the model by removing these two flags these two classes only focusing on the four main class.

**Geoff Horowitz:** okay.

**Sachin Pandey:** So what will it will do?

**Geoff Horowitz:** Okay.

**Sachin Pandey:** Basically it will help us increase the precision by like by like because we removed a lot of false positive the precision will like automatically improve and the mistakes like these uh I want to show it to you. So if you see the false positive number it start decreasing once we like even if you go 10 pixel you see the jump like almost half of like yeah around 600 400 were removed because only like like these were very small

### **01:53:00**

**Geoff Horowitz:** Yeah, cuz they're so

**Sachin Pandey:** noises which were which were like I think that these are the causes which are causing these like

**Geoff Horowitz:** small.

**Sachin Pandey:** small mistakes.

**Geoff Horowitz:** Got it.

**Sachin Pandey:** So after fixing it I think this will like drop huge it will hugely drop and even if some thing are there we can still use this annotation but we target is to keep it at

**Geoff Horowitz:** Okay.

**Sachin Pandey:** zero and reduce this as much as we can.

**Geoff Horowitz:** Okay. Um.

**Sachin Pandey:** So that's one thing and other is like I

**Geoff Horowitz:** Mhm. Go ahead.

**Sachin Pandey:** just shared like he's he was working on something like instead of XTF to PNG he is generating a waterfall that

**Geoff Horowitz:** Mhm.

**Sachin Pandey:** looks like PNG and it is much cleaner and like it has more feature. So I'm just I was just asking Rul if he can just plot the I just update the annotation and

**Geoff Horowitz:** Okay,

**Sachin Pandey:** share this annotations with Rul.

**Geoff Horowitz:** Rachel

**Sachin Pandey:** If we can just pl plot them correctly.

### **01:54:02**

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** there.

**Sachin Pandey:** Can Rul can share the screen and show that the idea is if we can plot them correctly on the objects we can train another model which predicts on waterfall. So because like it will be different like instead of XTF to PNG it will HTF to waterfall and then predict on it because client only needs the final output it doesn't matter like which way we go if a waterfall is given giving us more feature in the like same image without increasing the size or throughput uh it will be like better. So, we just want to test that out like a different PNG

**Geoff Horowitz:** Um

**Sachin Pandey:** at

**Ratul Shashank:** Yes. So, should I share my screen

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** yeah.

**Ratul Shashank:** now?

**Geoff Horowitz:** Yeah.

**Sachin Pandey:** Yeah.

**Ratul Shashank:** Yeah. So, uh this is the waterfall that su mentioned. This we are looking at we are looking for DW and these are with annotations. Most of most of the images are uh like they are clean rectangles. Suchin said that it would be better if it would be a great uh addition to use them.

### **01:55:53**

**Geoff Horowitz:** So,

**Ratul Shashank:** The only problem I was saying that the only problem

**Geoff Horowitz:** Mhm. Go ahead.

**Ratul Shashank:** with this waterfall is in some cases for entx I need to that but uh I need to find where the image is. But the problem is in some cases for the NTX the output is uh not very good to say the least. That is for entx only and in a few examples only not in not in men.

**Geoff Horowitz:** Rachel, Rachel, my my question here is how do we at the end of the day, the client wants a latl long position for each of the marked contacts. Um, when we were using the raster that was, you know, I mean, that was relatively

**Ratul Shashank:** Yeah. And and regarding that,

**Geoff Horowitz:** easy.

**Ratul Shashank:** I have also found something since our last conversation. Uh well it is true that waterfall even though we can close the gap but it won't

**Geoff Horowitz:** Mhm.

**Ratul Shashank:** be a true raster. So there would be uh scope for error but uh this is uh when you when you mentioned to use SSS data and combined it with map data.

### **01:57:35**

**Ratul Shashank:** So I was just experimenting uh how to do that.

**Geoff Horowitz:** Mhm.

**Ratul Shashank:** So what I found was this is X this this XTF this sides scan data when I plot it uh when I plot both of them together the black line that we saw it it is much reduced only to a narrow needle region and this is also So similar for DRN. So I think it can be possible to I it is a hypothesis but it can be possible to create a raster which does not has uh the black region that we have been encountering and and the problem is uh why we encountered that raspberry. I have also I was also looking at that is because the previous script that we were using it inputs a default it inputs a default range of around 10 m and it uh long story short it uh creates a range based on altitude. So it shows extra n region than it is supposed to be. I don't know why that was but when I created this uh raster from the scratch and combined it with nav data it it it does not contain that uh long of a black region.

### **01:59:31**

**Geoff Horowitz:** Here's

**Ratul Shashank:** So this can be used this this is a true raster and this also does not have that black region. So this solves both the

**Geoff Horowitz:** the thing about the black region.

**Ratul Shashank:** problems.

**Geoff Horowitz:** black region is right. So I think Sid said this and Sachin you you may remember this too that that we are purposely blocking out the you know that nater range. Um, so I'm not surprised, Raul, that you you you know, you found some some metric there. Um,

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** I thought there was a reason he did it. I I'm not opposed to going back and double checking and trying it, but I thought there was a reason that he did that.

**Ratul Shashank:** Yes,

**Geoff Horowitz:** Um,

**Ratul Shashank:** I I that was also my reason because uh this region this uh range of 10 I uh I think it it is

**Geoff Horowitz:** Uh-huh.

**Ratul Shashank:** 10 m because there is no limit but this is hardcoded in in the script.

**Geoff Horowitz:** Uh-huh.

**Sachin Pandey:** So Rul can you go like find the function where it is getting used where the weights

### **02:00:56**

**Geoff Horowitz:** Uh-huh.

**Sachin Pandey:** are returned

**Ratul Shashank:** Uh

**Sachin Pandey:** because what Sidhar told me like the reason it's hardcoded or these the variable you are seeing neither uh ground range is ignored completely.

**Ratul Shashank:** yeah,

**Sachin Pandey:** It the skip recalculated based on the data it

**Ratul Shashank:** it is going

**Sachin Pandey:** has. So even if you pass 100 it will be ignored. So like maybe that weight is not getting uh used anywhere.

**Ratul Shashank:** Yeah, I think this is the exact line because uh this is uh this is using any any weight which is beyond this region. It is considering that and it can completely ignoring anything past this

**Geoff Horowitz:** Rachel, where is that function being called? Compute

**Ratul Shashank:** region.

**Geoff Horowitz:** evaluates.

**Ratul Shashank:** So it is considering horizontal offset and primary

**Geoff Horowitz:** Always

**Ratul Shashank:** altitude. So, oh, so need a ground. Uh, okay. I think this is uh by default the 10 value it is taking 10 m as the as the needle region. If altitude is not given, if altitude is altitude is taken then it will take altitude and create a range of uh altitude in the region.

### **02:02:55**

**Geoff Horowitz:** Yeah, it never So it never uses that 10\. It uses whatever that ping altitude value

**Ratul Shashank:** Yeah,

**Geoff Horowitz:** is.

**Ratul Shashank:** I I I think it's just fail safe that he added 10 if there no

**Geoff Horowitz:** Yeah.

**Ratul Shashank:** altitude is registered.

**Geoff Horowitz:** Right.

**Ratul Shashank:** And here it's taking the weights where the absolute horizontal offset is less.

**Geoff Horowitz:** So it is still taking I mean it is still blocking out like if it's if it's going at a you know five meter altitude right it's going to block meters

**Ratul Shashank:** Yes. Uh so I think if the altitude is around 5 m so it would consider 5 m on port and 5 m on starboard because it is not uh specifying on just one area. So I'm assuming that it would offset uh

**Geoff Horowitz:** Okay. So, so what's the effect here?

**Ratul Shashank:** both.

**Geoff Horowitz:** So, what's the effect?

**Ratul Shashank:** So the problem is if if we are doing that then around 10 if if altitude is around 5 m then around 10 m of area would be in the black region.

### **02:04:14**

**Ratul Shashank:** So

**Geoff Horowitz:** What is the So, so let me let me try to let me try to say this back.

**Ratul Shashank:** that

**Geoff Horowitz:** So the reason that we want to use waterfall instead of the raster image is so that we can get access to this nater data.

**Ratul Shashank:** uh so Satan wanted to use waterfall because waterfalls are more uh clear.

**Geoff Horowitz:** They're more clear.

**Ratul Shashank:** Mosaics uh mosaics are uh they lack the clarity and if they are increasing the resolution then we would we would encounter these gaps. Waterfall don't have that

**Geoff Horowitz:** Fine, right? But but the downside is that the waterfalls like because they get rid of all these gaps,

**Ratul Shashank:** problem.

**Geoff Horowitz:** they also don't have the location data, right? They don't have the geoloccation data.

**Ratul Shashank:** uh uh that uh we can take that with a pinch of salt. I mean what waterfall is waterfall is

**Geoff Horowitz:** Hey.

**Ratul Shashank:** just uh draw data of things. So we can extract we can extract the geoloc.

**Geoff Horowitz:** Uhhuh.

**Ratul Shashank:** It's just an extra step.

### **02:05:29**

**Geoff Horowitz:** Okay. I I'm fine trying it if you guys want to do it as long as we can get the same output. Right. the output is um well number one you know they want to be able to visualize it through the bedrock viewer so but I I think we can we can solve that um right so it's it's the visualization with the overlaid detections but then number two is output the latl long for each of the um for each of the predictions so as long as we can do it I I'm okay with uh with reassessing. Have you talked to Project about this yet?

**Ratul Shashank:** Uh I I I need to discuss this and also a few other things with him. Uh this this idea we just gave I I was just showing Sachin the

**Geoff Horowitz:** Yeah.

**Ratul Shashank:** images. So he said that it is worth a try.

**Geoff Horowitz:** Yeah. Certainly worth a try. I mean the the I think it would be useful to try it sooner rather than later because all of our experimentation would need to be redone, right?

### **02:06:42**

**Geoff Horowitz:** Uh

**Ratul Shashank:** Uh uh I have a a question regarding that. Uh you mentioned bedrock would use the model from the bedrock view.

**Geoff Horowitz:** Mhm.

**Ratul Shashank:** Uh do we have uh do we know that what kind of uh visualizations they use? Do they use elasters? Do they use waterfalls? And the second part of that question is would uh suppose we train our model on raster and they they would use the bedrock viewer would use waterfalls. that effect in the overall detection of the

**Geoff Horowitz:** Uh I think that's a question for Sachin.

**Ratul Shashank:** model.

**Geoff Horowitz:** Sachin does the viewer does the viewer run the model independently?

**Sachin Pandey:** By vocal

**Geoff Horowitz:** Yes.

**Sachin Pandey:** it will have the same pipeline whichever pipeline we will use to generate the images which are used in the training the same pipeline will be added there.

**Ratul Shashank:** So it would not be on the go,

**Sachin Pandey:** No like if if we go with this route then we will update the pipeline to convert the image

**Ratul Shashank:** right?

**Sachin Pandey:** to waterfall then predict on it and then convert the like use the waterfall transformation again to convert the pixels to latl long and like client will only take the latl longl long and put it in their whatever they will do with the final uh location of the object.

### **02:08:31**

**Ratul Shashank:** So we can we can try we can try using the waterfall because Pax was also interested in using waterfalls. we uh we just uh don't have enough data of using water for uh and I can also look into this if uh if that black region is of importance to us I can I mean if removing that will improve our model I can try because if this is producing no black region then it is uh possible that flag region can be removed. If removing it would help us. I can try

**Sachin Pandey:** uh we need to test it like uh after you you will give me the images where the back legion is removed.

**Ratul Shashank:** that.

**Sachin Pandey:** I will uh run it through the pipeline to see if like old model was not predicting there. So the new image is predicting or not the hypothesis which we talked about like if the UXO is on the side near the black region the model is not predicting it. We just want to test it out and if it is then like we like pex is looking to argumenting it more.

### **02:09:50**

**Sachin Pandey:** So model is putting like objects on the side more but not on the black region.

**Ratul Shashank:** It is confusing the empty area and the area with

**Sachin Pandey:** Yeah,

**Ratul Shashank:** pixels,

**Sachin Pandey:** like as Pat told like he wanted the argumentation to not be

**Ratul Shashank:** right?

**Sachin Pandey:** in the black region but maybe some mistake in the code that model is not rooting the uh UXO or argumentation near the black region even on the like The the white area you are seeing on the center. So that's why like and model is not learning to predict there. So maybe that's the reason that's why we are just checking

**Ratul Shashank:** What does it mean? What does it mean?

**Sachin Pandey:** it.

**Ratul Shashank:** Augmentation in the black region.

**Sachin Pandey:** So because black the if you see the normal image there is a black region in the center right we don't want to like cut the UXO and put paste it in the center of the black

**Ratul Shashank:** Mhm.

**Sachin Pandey:** region because it's not possible. So we are trying to avoid the black region and what is causing it?

### **02:10:54**

**Sachin Pandey:** It is not even touching the edge of the white line where the actual uh area is. And if if you see the the mainly mistakes were happening because the object is very close to the edge. So that's that's the hypothesis we want to test. If you merge the if you reduce the gap between the object if it's is it working or not. If you move the object from the side to the center will it work working or not? By center I mean the gray patch center not the black one. So these are the two thing we have to test right

**Ratul Shashank:** understand.

**Sachin Pandey:** mode.

**Ratul Shashank:** And what do you need uh need to uh provide

**Sachin Pandey:** You just have to give me the like join image, the starboard and the one. I've shared you the list of the files.

**Ratul Shashank:** up?

**Sachin Pandey:** Yeah. Yeah.

**Ratul Shashank:** Okay, I can do that.

**Sachin Pandey:** Yeah. And Jeff, it is like we have the free GQ. We can just test it out because maybe the higher resolution can give us more uh can give the model more feature for like very small object like UXO.

### **02:12:08**

**Geoff Horowitz:** Fine, let's do it. I But Son, here's my here's my one caveat. One caveat. Let me let me share my screen so that I'm very clear about this.

**Sachin Pandey:** like whether we were able to convert the annotation to latl

**Geoff Horowitz:** No. Well, yes.

**Sachin Pandey:** long.

**Geoff Horowitz:** Yes. I should I I guess I have two caveats. One, one caveat is we need to be able to convert to number two is guys, I I can't I can't keep track of all of the experiments we're doing. Maybe you guys are, but I I need some centralized place where we're going through this. Um Sachin, we talked about this last time. Uh, and I think we need to do it here too where again I feel free to do this in a different way if you think it's better. But until you guys give me a better way to do it,

**Sachin Pandey:** We need to track the failed experiment as well.

**Geoff Horowitz:** say again I

**Sachin Pandey:** We need to track the failed experiment as well like the removal of sand

### **02:13:09**

**Geoff Horowitz:** I look I think what I think we might as well I I just want to be

**Sachin Pandey:** patch.

**Geoff Horowitz:** systematic about what we train and how we train, right? So, so we have here are models. Right? We have our baseline model. Okay? You know, this is link to report. Same thing. What's the outcomes? The outcomes, right? Or what's what's the TLDDR from the report? Okay. you know, and maybe that's maybe that's not even important for baseline, but you know, experiment one, this is uh we're using the baseline um data and baseline model, but using um waterfall images instead of raster. That's the experiment, you know. So, what does this tell us? It tells us where our starting point is, baseline, baseline data, baseline model, and then it tells us what the change is. You know, link to report. Uh what's the outcome, right? The outcome is results are way better. We should use this one going forward.

### **02:14:34**

**Geoff Horowitz:** Something like this. I just there's and we even saw this on the call earlier today Sachin is like there's all these models in all these different places and I maybe you guys have a sense but certainly I don't have a sense of where we are what works what doesn't work how does it compare to baseline things like that

**Sachin Pandey:** Yeah. Like I am uh keeping track of the like if it is work and it is better then

**Geoff Horowitz:** is

**Sachin Pandey:** I will like make a note like this is the model path. These are the like things

**Geoff Horowitz:** Okay,

**Sachin Pandey:** and can you

**Geoff Horowitz:** fine. So, just make it make it even if you copy it.

**Sachin Pandey:** share me this this one? I will start adding the details here also

**Geoff Horowitz:** Yeah. Yes. It's just the running notes.

**Sachin Pandey:** please.

**Geoff Horowitz:** You want to share it in the meeting or in Slack? Share it in Slack.

**Sachin Pandey:** Uh don't worry

**Geoff Horowitz:** Ed rock running.

### **02:15:29**

**Sachin Pandey:** I found it. Bad drop SEO.

**Geoff Horowitz:** Oh,

**Sachin Pandey:** It's the same one where we were updating right model baseline

**Geoff Horowitz:** same one where we were updating.

**Sachin Pandey:** matrix where we updated the model baseline.

**Geoff Horowitz:** Exactly.

**Sachin Pandey:** Okay, I I have

**Geoff Horowitz:** I I just want to be organized about we can run all these experiments but

**Sachin Pandey:** it.

**Geoff Horowitz:** you know in two weeks when we don't remember which experiments we ran and what was the data and where's the link to the whatever like uh I I just want to I hope I'm being clear here.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** I This shouldn't take you more than four minutes, maybe even two, right? This this should be so quick. It's just kind of saying what we're doing. That's it. Um and then a link to the report. Um, Okay. Do you want me to leave this or or delete it?

**Sachin Pandey:** uh leave it. Uh I will it will work as a

**Geoff Horowitz:** Okay. Um, so Redul,

### **02:16:28**

**Sachin Pandey:** blueprint.

**Geoff Horowitz:** I'll say this to you, too. Yeah, let's do it. Let's test it. Just document document the results.

**Ratul Shashank:** Thank

**Geoff Horowitz:** Um, and such. And I think I think to answer your question about like even failures,

**Ratul Shashank:** you.

**Geoff Horowitz:** I think it's useful to say what we tried, right? This was our experiment. This is what we tried. What's the outcome? It failed. Results were bad. It failed. Move on. Right. At least we've gotten the At least we've documented it

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** somewhere.

**Ratul Shashank:** Uh this is just an idea.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** Yeah. Go ahead,

**Ratul Shashank:** Uh uh I so what I can

**Geoff Horowitz:** Rachel.

**Ratul Shashank:** do for the time being uh like this won't be a problem when we have our agent set up for the company.

**Geoff Horowitz:** Right.

**Ratul Shashank:** But for the time being we can do is uh just how I'm I'm using my workflow creating a few context files and the agent will take care of of everything.

### **02:17:29**

**Ratul Shashank:** You can just uh create a short folder like that and agent can segregate everything in its place. We won't need we would just need to instruct it.

**Geoff Horowitz:** I don't understand.

**Ratul Shashank:** So like how I use my workflow uh it is just a bunch of context files. The folders knows what to write, what to store. So we can create a context file and instruct them to store uh what you want like we can instruct we can store the experimentation the outcomes the tlddr

**Geoff Horowitz:** Yeah.

**Ratul Shashank:** so it would be in a place it would be handled by the agent we won't have to uh we won't have to do it manually we would just have to instruct agent that here is the model, here's the result. Uh you understand and you just get it. It should not take very

**Geoff Horowitz:** Um,

**Ratul Shashank:** long.

**Geoff Horowitz:** hold on. Um, look, I I hear what you're saying, Rul. I am I I don't care about I I don't care about how this is done, but what I'm saying is is that this is the information that I want to be able to see quickly, right?

### **02:19:10**

**Geoff Horowitz:** And so, so if you have an agent do it, if you do it, it doesn't matter to me, but it should be short. It should be concise. It should be complete. And by complete I meaning you know having whatever this relevant information and it should be in a place where I can access it. I don't need to say hey Rul where's you know give me a print out of all the the you know the progress. Does that make sense?

**Ratul Shashank:** Yes, it makes a

**Geoff Horowitz:** So so so I'm going to kind of circumvent your question and I'm going

**Ratul Shashank:** bit

**Geoff Horowitz:** to say or your your idea rather. I'm gonna say if this is the outcome, I don't care who does it. The agent can do it, you can do it, it doesn't matter, but this is the outcome that I want to be able to see.

**Ratul Shashank:** all in one place.

**Geoff Horowitz:** Yeah. In well, in one place, meaning like, you know, I can just open up a document, right?

### **02:20:08**

**Geoff Horowitz:** and I can like scroll through the document as opposed to having to open up this document and then having another link to a different document and another link,

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** you know, just like one one place. Seriously, like no more than a few lines, right? That just I can read this very quickly and see what the results were. Um, does that make sense?

**Ratul Shashank:** Yeah, it make it makes sense. It makes sense. And yeah, I mean uh it's it's very doable. Even Sachin is kind of doing that with his HTMLs. It's all in

**Geoff Horowitz:** I agree with you. He's doing that. I agree with you. He's doing that.

**Ratul Shashank:** place.

**Geoff Horowitz:** But so you know what I saw even in the meeting today is the HTMLs are like they're organized for Satcha. But then when Protach needs to find them, he doesn't know exactly where to go. When I want to find them, I don't know where to go. you have to go and look through the you have to look through the HTMLs and kind of um infer your own results.

### **02:21:07**

**Geoff Horowitz:** Does that make sense? Um you know which model are you supposed to go to,

**Ratul Shashank:** Yes.

**Geoff Horowitz:** which one's the baseline? So just having two lines, one line, you know, what is this experiment? What was the change, right?

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** What what what was the change that we were seeing? a link to the report in case you want to dig into it and what's the outcome, right? What's the outcome? Results were better. These should be the next steps. I mean, we don't need to be too rigid, but um I think this will

**Sachin Pandey:** Uh Jeff the the simplest thing I can think of is like you can

**Geoff Horowitz:** help.

**Sachin Pandey:** make a MD agent MD file with all the instruction and we will all put in in our agents and whenever agent run something it will like find the location because

**Geoff Horowitz:** Uh-huh.

**Sachin Pandey:** agent like main MD file will always be passed in each prompt and it will just update it right away. We don't even have to think about it

### **02:22:08**

**Geoff Horowitz:** So when you run a new experiment, how does that get updated on my end?

**Sachin Pandey:** like uh like if there's the MD file knows the location of a central server where like where it has Like it can figure out the basic like which project it will go in. But if it know the instruction like you have to update these things when this instruction is run or any experiment is run and just push it there the get commit or I

**Geoff Horowitz:** So, so, so Sasha, if it's again, I I'm not trying to say how you should do it,

**Sachin Pandey:** think.

**Geoff Horowitz:** right? If if this isn't the best, let me let me and I don't really want to waste too much time on this, but uh SC

**Ratul Shashank:** uh I think I have I understood uh what you mean there

**Geoff Horowitz:** So give me one sec. Okay. So Sachin, even if you have if that's what you have going on in the background, right, and you have your agent, right, and it's looking at, you know, I don't know, it's it's looking at Wall-E, right?

### **02:23:11**

**Geoff Horowitz:** And it's uh, you know, trying to pick all those things and then, you know, that agent looks at Wall-E and then it generates this report, right? It generates this report or it updates this report. And then I Okay. So then that gets pushed to GitHub, right? And uh then we have a like a I don't know a GitHub page, right? Git page. Do you know what I'm talking about? Like a like GitHub. So fine.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** Fine. As long as it has this information, that's perfectly fine with me. It's one link. You go to one link. It's got all this stuff. Fine. But I don't think it makes Go

**Sachin Pandey:** So, yeah.

**Geoff Horowitz:** ahead.

**Sachin Pandey:** So currently I'm doing it two different ways. One is the in the agent folder I just put everything like these are this is completely managed by agent. Whatever I did,

**Geoff Horowitz:** Uhhuh.

**Sachin Pandey:** I will just put the agent like pass this folder and want it just put it tell it to update it and like I was just testing it out like if you just pass the folder and check what is the latest update what is it

### **02:24:16**

**Geoff Horowitz:** Yeah.

**Sachin Pandey:** showing it is showing of like tomorrow details but because I haven't updated it right now but one thing is this which is managed by agent and other will be like the obsidian where I only keep the important things which I want to pull. So, so something like these where all the matrices are here uh updated data distribution what was changed uh based on training data the models all the parts of the model uh class distribution train valves separation like all the things are like noted down here. These are like all the the v2 model you see like what are the changes in the par hyperparameters of the v2 model. So like I'm pulling the important details here but all these things should be available in the uh in this also.

**Geoff Horowitz:** Okay.

**Sachin Pandey:** So

**Ratul Shashank:** Uh Sachin I I think that is pretty doable. Better. uh we can just create a folder on volume and we can we can

**Geoff Horowitz:** All

**Ratul Shashank:** just add a MD file and anyone can access that MD file and any anyone can update.

### **02:25:36**

**Ratul Shashank:** Uh it's not it's not that difficult. We can we can do

**Geoff Horowitz:** right. That's reasonable,

**Ratul Shashank:** that.

**Geoff Horowitz:** too.

**Sachin Pandey:** Mhm.

**Geoff Horowitz:** That's reasonable, too. Right. All this is Yeah. an MD or an HTML file that that has this

**Ratul Shashank:** Yeah,

**Geoff Horowitz:** information.

**Ratul Shashank:** that's what I meant when I said that every in any instruction should be on a con context file. So the context file would just contain the data of the HTML and the data of report. So report could be other data and HTML could be like like it's not it's not very difficult. It's it's very doable.

**Geoff Horowitz:** Okay. So, fine. So, Rul, you seem to have a sense of of what I want and how to do it. So, um I agree with you. I I don't think it should be super hard. Uh so,

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** so can you take that

**Ratul Shashank:** Yeah,

**Geoff Horowitz:** on?

**Ratul Shashank:** I I can do that.

### **02:26:32**

**Ratul Shashank:** I can create uh uh I can I can create a context file and I can share that with Sachin and uh he can just put it in folder under home folder or under root folder and anyone can access that and any agent will always

**Geoff Horowitz:** Perfect.

**Ratul Shashank:** read that ND file without before doing anything. So it won't be uh too much of a too much of a task.

**Geoff Horowitz:** Okay. Fine.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** Um. All right. Sachin, were you able to update the Streamlit app with the new models that we discussed?

**Sachin Pandey:** Uh, no, not yet. Currently like we are not decided on the model. So if tomorrow experiment goes well then that will be the final model which we will be putting in

**Geoff Horowitz:** So,

**Sachin Pandey:** there because like the current model V2 model which I was just showing earlier is performing good like uh it was identifying most of the UXO but few mistakes are like first the training data have issues. I want to just fix it and then train a new model on the same architecture.

### **02:27:48**

**Geoff Horowitz:** Understood.

**Sachin Pandey:** We just we are just confident about it.

**Geoff Horowitz:** Understood. But Sachin understood.

**Sachin Pandey:** So once that done that model will be going into the uh

**Geoff Horowitz:** So So that's that's I think what I'm saying is I I understand that you're kind of working on these models

**Sachin Pandey:** app.

**Geoff Horowitz:** simultaneously. Um but adding in a model is plugandplay, right?

**Sachin Pandey:** Yeah, we can just like Yeah,

**Geoff Horowitz:** So,

**Sachin Pandey:** it's it's simple.

**Geoff Horowitz:** so that's my question. Is this tool? Is this tool? Can I show Bridget this tool?

**Sachin Pandey:** Uh these are which port is it?

**Geoff Horowitz:** This is five 8505\.

**Sachin Pandey:** Yeah it it also contains model prediction like uh 85 can you click on the model either it will be 20 models or six models.

**Geoff Horowitz:** Six models.

**Sachin Pandey:** These are the six more. So you can show it like change the data set to train val set uh or training data. So select training data then split by val set and annotation will be the uxo1 which is the current one which model was trained on and you can filter out by

### **02:29:05**

**Geoff Horowitz:** Okay. Okay. and

**Sachin Pandey:** class.

**Geoff Horowitz:** then

**Sachin Pandey:** These are the model the UXO V2 is working best then on the top if V1 binary is also the best one overall matrix the binary is the best but

**Geoff Horowitz:** so

**Sachin Pandey:** class wise the V2 UXO is

**Geoff Horowitz:** binary is the baseline,

**Sachin Pandey:** best

**Geoff Horowitz:** right?

**Sachin Pandey:** baseline model yeah you you can treat it as a baseline

**Geoff Horowitz:** V the one binary is our baseline. That's my recollection. What you said I think on

**Sachin Pandey:** Yeah,

**Geoff Horowitz:** Friday.

**Sachin Pandey:** V1 all all V1 are baseline just the like these ones the annotations were different all will

**Geoff Horowitz:** What happens when I click multiple models?

**Sachin Pandey:** appear if you scroll side uh just click show

**Geoff Horowitz:** Let's try it out. All right. And filter images containing types.

**Sachin Pandey:** overlay

**Geoff Horowitz:** Okay. Select. Oh, this is kind of cool. UXO filter logic. Any selected? Oh, all.

**Sachin Pandey:** Uh you need to click on the

### **02:30:07**

**Geoff Horowitz:** Okay, got it. Showing 15 images.

**Sachin Pandey:** show predictions

**Geoff Horowitz:** Oh, dude. I like this.

**Sachin Pandey:** overlay

**Geoff Horowitz:** Good. This is an improvement of our tool. Um, I haven't played with it yet. Okay. What were you saying?

**Sachin Pandey:** in the sidebar you have to click on the prediction overlay.

**Geoff Horowitz:** Still prediction. Isn't that the

**Sachin Pandey:** If you scroll on, yeah, if you scroll down,

**Geoff Horowitz:** prediction?

**Sachin Pandey:** you will see the mask on the main view. In the main view, if you scroll down,

**Geoff Horowitz:** I

**Sachin Pandey:** you will see the mask below.

**Geoff Horowitz:** see.

**Sachin Pandey:** You can change the orientation by clicking on the left.

**Geoff Horowitz:** Uh view mode annotated only.

**Sachin Pandey:** These are for the top one.

**Geoff Horowitz:** Oh, okay. I see side by side. Okay. uh side by side layout. This was the Oh,

**Sachin Pandey:** This is for the main input one, the raw one, the ground

**Geoff Horowitz:** I see. Okay,

### **02:31:07**

**Sachin Pandey:** truth.

**Geoff Horowitz:** fine. So, you're saying I can change the orientation of these two

**Sachin Pandey:** Yeah,

**Geoff Horowitz:** somehow.

**Sachin Pandey:** it was in the prediction section. If you go more Yeah. stack option instead of side by side.

**Geoff Horowitz:** It's actually too many options. I I think there might be a bug there. No.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** Yeah. Oh, now it works. Okay, cool. Uh, all right. I think that's what I need. So, this is pretty good. I can show her the training data. Uh, roll data.

**Sachin Pandey:** It's only ground truth. No prediction on this

**Geoff Horowitz:** Uh,

**Sachin Pandey:** one.

**Geoff Horowitz:** no predictions because this is only to see the background, but that's okay. So, this is the new this is the new data set she sent us, right?

**Sachin Pandey:** Yes. 25\.

**Geoff Horowitz:** Um, Sachin, could you do me a favor? Could you could you add in a toggle to hide this data set ro data?

### **02:32:36**

**Geoff Horowitz:** Yeah, I think training use these two kind of um okay I have a small so when we look at this we can see failed to view. So, um, these don't show the data set that they're from. Is that right?

**Sachin Pandey:** Yeah, they don't show

**Geoff Horowitz:** Can we add that in?

**Sachin Pandey:** it.

**Geoff Horowitz:** Is that easy to add in?

**Sachin Pandey:** I think so. I can just give you the cheat sheet of like 006 is V will be a N and

**Geoff Horowitz:** even

**Sachin Pandey:** TX 000 will be VW something like

**Geoff Horowitz:** okay so so so that's what I'm going to say is just add that in just like we have data set

**Sachin Pandey:** that.

**Geoff Horowitz:** training here add that in um I don't know source data set whatever your mapping is

**Sachin Pandey:** Can you tell me the port again? Like similar application is running on multiple

**Geoff Horowitz:** uh oh yeah well which you first of all you tell me which one do you want me to

**Sachin Pandey:** port.

**Geoff Horowitz:** use

### **02:34:13**

**Sachin Pandey:** Uh 8505 8507 like

**Geoff Horowitz:** which which one 05 or 07

**Sachin Pandey:** Pex is using 8507\. I am using 850 files and

**Geoff Horowitz:** the difference just so that you don't like override each

**Sachin Pandey:** almost yeah like in this one it was mainly

**Geoff Horowitz:** other.

**Sachin Pandey:** targeted for open source data and this has the like class by class but it doesn't have the latest prediction or annotation like these are this is mainly for viewing

**Geoff Horowitz:** Um,

**Sachin Pandey:** uh uh ground truth and data.

**Geoff Horowitz:** so this doesn't have models.

**Sachin Pandey:** Yeah,

**Geoff Horowitz:** We can't choose models.

**Sachin Pandey:** this doesn't this doesn't have

**Geoff Horowitz:** Fine.

**Sachin Pandey:** models

**Geoff Horowitz:** Then I need to be able to choose models. So 8505, right?

**Sachin Pandey:** 8505\. Okay.

**Geoff Horowitz:** I mean,

**Sachin Pandey:** All the all the changes you suggested to done on

**Geoff Horowitz:** we can make we can okay with you.

**Sachin Pandey:** 8505\.

**Geoff Horowitz:** Is that all right?

**Sachin Pandey:** Yeah. Yeah,

**Geoff Horowitz:** Okay.

**Sachin Pandey:** it's okay.

**Geoff Horowitz:** So, yeah. I mean, I think just showing the data set name is fine,

### **02:35:30**

**Sachin Pandey:** If I will

**Geoff Horowitz:** but if you if you want to show them like list them all out,

**Sachin Pandey:** try.

**Geoff Horowitz:** I guess that would be a I I think we should show the data set. Um because then then it's all easy to track, right? It's all at the top here. Uh the second thing is do you mind just putting in like a I don't know

**Sachin Pandey:** Yeah,

**Geoff Horowitz:** a checkbox or something so that I can hide the full

**Sachin Pandey:** I will I will remove the full

**Geoff Horowitz:** path.

**Sachin Pandey:** path.

**Geoff Horowitz:** If you if you use it, I have no issues with you keeping the full path there. For me, I think internally it'd be useful to keep full path there. That said, I don't want to show Bridget the full path. So, even just a checkbox that says hide

**Sachin Pandey:** I don't think I I use it that much.

**Geoff Horowitz:** it.

**Sachin Pandey:** I I will remove it.

**Geoff Horowitz:** Okay.

**Sachin Pandey:** I have make a note of it.

### **02:36:16**

**Sachin Pandey:** I

**Geoff Horowitz:** Do we have do we have a way to like check where these images

**Sachin Pandey:** will

**Geoff Horowitz:** are from if we need

**Sachin Pandey:** uh it's all are mainly in same

**Geoff Horowitz:** to

**Sachin Pandey:** folder. uh training data open source like most of the training data is in with the one

**Geoff Horowitz:** Okay. I I mean I'm not touching the training data.

**Sachin Pandey:** folder

**Geoff Horowitz:** you're touching the train data. So, I'll trust you here. My instinct says there's no harm in leaving the full path somewhere to be accessible if we want it. But, but at the end of the day, it's your decision session.

**Sachin Pandey:** I will be removing it so I will let's set few default you don't have

**Geoff Horowitz:** Okay. Fine.

**Sachin Pandey:** to move everything again and again and uh in the training data I will remove the path but in other data it will be visible because you will only

**Geoff Horowitz:** Okay.

**Sachin Pandey:** be showing the training data so

**Geoff Horowitz:** I don't know. I don't know.

### **02:37:22**

**Sachin Pandey:** Okay. Uh I will move it somewhere or in the sidebar very below the

**Geoff Horowitz:** Yeah, that's fine. That's fine. Move it into the side bar.

**Sachin Pandey:** sidebar.

**Geoff Horowitz:** That's good. Yeah. Uh, what does fail to fuse mean?

**Sachin Pandey:** It was the name of the

**Geoff Horowitz:** Oh, okay.

**Sachin Pandey:** file.

**Geoff Horowitz:** Um, let me just This is all open

**Sachin Pandey:** I will also update it maybe like there was a feature where the file name like

**Geoff Horowitz:** source.

**Sachin Pandey:** there will be a unique file name for each setting and everything but it's lost. I will add it back. So you can just find the ones and copy the link so it can be reopened

**Geoff Horowitz:** Uh either way, I mean I Okay,

**Sachin Pandey:** again.

**Geoff Horowitz:** it's fine with me. I can also just set it up. Uh annotation viewer. Oh, so this is also for annotations, right? So, all right. So, I have two models here. So, I've got the binary V1 and I also have multiclass V2 UXO.

### **02:38:37**

**Geoff Horowitz:** How do I know what I'm seeing? How do I know which one's which?

**Sachin Pandey:** uh if turn on the prediction overlay the name will be displayed side by

**Geoff Horowitz:** Turn on.

**Sachin Pandey:** side.

**Geoff Horowitz:** Okay. So, I turned on prediction

**Sachin Pandey:** If you scroll down,

**Geoff Horowitz:** overlay.

**Sachin Pandey:** so scroll down on the main

**Geoff Horowitz:** Oh, I see.

**Sachin Pandey:** view.

**Geoff Horowitz:** I see. Binary. Okay. I see what you're saying. I see what you're saying. Binary image. Multiclass image. I don't get it. It doesn't seem to align with What is

**Sachin Pandey:** You need to change it to uh prediction ones layout.

**Geoff Horowitz:** this?

**Sachin Pandey:** Change it to stack prediction layout on the

**Geoff Horowitz:** prediction layout predict model predictions layout

**Sachin Pandey:** top.

**Geoff Horowitz:** set right

**Sachin Pandey:** It's only finding the black patch,

**Geoff Horowitz:** but

**Sachin Pandey:** not the UXO.

**Geoff Horowitz:** so black patch it's not seeing the UXM

**Sachin Pandey:** There will be six files where the UXO isn't identified and nine where it is.

### **02:40:01**

**Geoff Horowitz:** uh do you know which ones are which this one? So this is green is UXO, right?

**Sachin Pandey:** Yes.

**Geoff Horowitz:** UXO. I don't know how it's getting this. This is so hard to see. Where is this? Wait a

**Sachin Pandey:** These are mostly because we know the location where the UX and we are like we just plot it

**Geoff Horowitz:** second.

**Sachin Pandey:** on the XTS.

**Geoff Horowitz:** Well, I guess it is kind of visible. I can't make this one bigger.

**Sachin Pandey:** Hi.

**Geoff Horowitz:** f\*\*\*. What did I do? Ah.

**Sachin Pandey:** No, you're on a different

**Geoff Horowitz:** Oh.

**Sachin Pandey:** page.

**Geoff Horowitz:** Oh, no. Okay. Yeah, I guess I guess that setting would be useful. What is it? It's going to go back to the last thing that it was at.

**Sachin Pandey:** uh it will have a unique link for all the setting and the view.

**Geoff Horowitz:** Is that difficult to do?

**Sachin Pandey:** I was doing it for the view. Uh I need to check for a setting like it will it can put it but it it makes the URL very messy like each flag is shown there each like all the setting will be in the URL.

### **02:41:37**

**Geoff Horowitz:** Look,

**Sachin Pandey:** It it is

**Geoff Horowitz:** maybe maybe this is easier. Maybe what's easier is just to like keep the last setting.

**Sachin Pandey:** good.

**Geoff Horowitz:** Like whatever it was on, just keep the last one and then put a reset button on top here.

**Sachin Pandey:** Yeah,

**Geoff Horowitz:** Oh.

**Sachin Pandey:** that that's also simple.

**Geoff Horowitz:** Oh, but you're saying because then I could have a link for each one and just go to the

**Sachin Pandey:** Yeah,

**Geoff Horowitz:** link.

**Sachin Pandey:** just if you open the link everything will be preconfigured and all the view

**Geoff Horowitz:** I hear you. I don't know. I It's not clear to me what would be.

**Sachin Pandey:** everything.

**Geoff Horowitz:** I mean, obviously that would be best, but it's not clear to me if that's worth the headache, you know.

**Sachin Pandey:** Uh I will not be doing it. I will just telling the agent to do it.

**Geoff Horowitz:** All right,

**Sachin Pandey:** Either way will be fine.

**Geoff Horowitz:** then. It's up to you. So just let me know what we end up doing.

### **02:42:23**

**Sachin Pandey:** Okay.

**Geoff Horowitz:** So one is good, two is no good. Oh, but this might all change with the other model. So that's fine.

**Sachin Pandey:** Yeah, this might

**Geoff Horowitz:** Hopefully it will change.

**Sachin Pandey:** change.

**Geoff Horowitz:** Okay. All right. I will spend some time with this tonight uh and work on a story.

**Sachin Pandey:** Yeah. Also like uh if you see the small black AI ai small black those are like also similar to UXO. So if you are identifying that also like that also uh like you can also show that

**Geoff Horowitz:** And just so that I'm I guess I have that document somewhere, but that's actually from the VW data set. That's fine. I Can't I can't find the BW data. Well, it won't have UX nodes, but I can do small black and then that should show up. Okay.

**Sachin Pandey:** zero. If you select the image, you have to select the AOI big and then the the like

**Geoff Horowitz:** Uh-huh.

**Sachin Pandey:** AUV0 or the uh the UV BW data.

### **02:43:51**

**Geoff Horowitz:** AUV. This is also VW, is it not?

**Sachin Pandey:** This is I guess it's ent.

**Geoff Horowitz:** Oh, this is because this is 006\. Okay.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Uh, all right. Well, I see what you're saying, though. But so because AOI big was only in the VW data.

**Sachin Pandey:** No.

**Geoff Horowitz:** Why isn't this update? What do I

**Sachin Pandey:** You need to remove the UI

**Geoff Horowitz:** do?

**Sachin Pandey:** small.

**Geoff Horowitz:** I thought AOI small was also in AW.

**Sachin Pandey:** Okay.

**Geoff Horowitz:** It's not anymore.

**Sachin Pandey:** No. Uh I guess I was wrong. 006 is also VW.

**Geoff Horowitz:** Oh yeah.

**Sachin Pandey:** This is the VW data.

**Geoff Horowitz:** Yeah.

**Sachin Pandey:** So I will

**Geoff Horowitz:** This is definitely the BW data. This is also 00\.

**Sachin Pandey:** I will put uh like I have the name I will just put it

**Geoff Horowitz:** Okay, that's useful.

**Sachin Pandey:** there

**Geoff Horowitz:** Um maybe we can also add a filter even if it's just in the annotation function. Or is that going to be too much?

### **02:45:11**

**Sachin Pandey:** for which kind of filter?

**Geoff Horowitz:** A filter for the data set the data set name like

**Sachin Pandey:** Okay.

**Geoff Horowitz:** the if we only wanted to look at entx for example.

**Sachin Pandey:** Uh I can like add a data selector there. Not in this one,

**Geoff Horowitz:** Okay.

**Sachin Pandey:** but just below it like inside training data you want to see only the only

**Geoff Horowitz:** Yeah. Yeah. Yeah. Sure.

**Sachin Pandey:** like

**Geoff Horowitz:** just like we can call it data set source or something. Um,

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** whatever makes sense. But yeah, okay, these are the things that stand out. Uh, if you can make those updates, I appreciate it. I will spend some time just kind of going through this tonight so that I have a good story for Bridget and I'll ping you if I notice any other things. Um but then other than that, you know, just uh tomorrow when whenever we have a whatever the best model is, let's add it in here. I do think having the baseline model will be good.

### **02:46:19**

**Geoff Horowitz:** Um.

**Sachin Pandey:** baseline model or the last one we shared S1.

**Geoff Horowitz:** the baseline model. No, I think it's the V1 where we trained the new data on the baseline or sorry,

**Sachin Pandey:** Yeah, we all all the V1 are the

**Geoff Horowitz:** we train the Yeah. So, I think that would be a good thing to show.

**Sachin Pandey:** baseline.

**Geoff Horowitz:** Um, I'm just going to have to dig through. I'd like to see a few places where the base where the V1 model does not get something and our updated model does get it. Does that make any sense?

**Sachin Pandey:** V1 updated model is the V2.

**Geoff Horowitz:** In this case, it is. I mean, I guess you're going to have a V3 tomorrow, right? Yeah. So,

**Sachin Pandey:** Yes.

**Geoff Horowitz:** okay. I'll um I'll spend some time with this tonight and we can connect tomorrow uh if needed to go through this. But in the meantime, just keep me updated on Slack if you can.

**Sachin Pandey:** Okay.

**Geoff Horowitz:** Does that work?

### **02:47:38**

**Geoff Horowitz:** Right. Cool.

**Sachin Pandey:** Yeah. Uh yeah. One more thing I will just repeat the task. Uh 8505 on port 8505\.

**Geoff Horowitz:** Yeah.

**Sachin Pandey:** Remove the full path. Uh remove the color. The spelling of the color will be the different one. Unique links. So, and the history that it will remember the setting and then add the data set name. Never missing anything.

**Geoff Horowitz:** add data set name, repeat setting.

**Sachin Pandey:** I remember

**Geoff Horowitz:** Um,

**Sachin Pandey:** setting.

**Geoff Horowitz:** if we can also do a a filter by data set name in

**Sachin Pandey:** Yeah, that will be available like like the

**Geoff Horowitz:** addition, yeah, in addition to showing it.

**Sachin Pandey:** date.

**Geoff Horowitz:** Does that make sense?

**Sachin Pandey:** Okay.

**Geoff Horowitz:** Let me show you what

**Sachin Pandey:** If you okay so if you have selected all the data set then it should show the name of the data set which you are

**Geoff Horowitz:** it

**Sachin Pandey:** going like name of the file with the data set.

**Geoff Horowitz:** Yeah.

### **02:48:39**

**Sachin Pandey:** Okay

**Geoff Horowitz:** Exactly. Just like we're doing just like we're doing with data set training here.

**Sachin Pandey:** name

**Geoff Horowitz:** Exactly the same.

**Sachin Pandey:** okay done.

**Geoff Horowitz:** Yeah, those are the things.

**Sachin Pandey:** I will just add instead of data set training I will just add the name there some

**Geoff Horowitz:** Uh, okay. Okay. Whatever works. And I think you you said you wanted to move this to the sidebar, didn't

**Sachin Pandey:** Okay.

**Geoff Horowitz:** you?

**Sachin Pandey:** Uh yeah. Uh let me

**Geoff Horowitz:** Yeah. Those are the things that I can think

**Sachin Pandey:** Nothing that you can try rejecting the image. It was like I copied over the file but rejecting

**Geoff Horowitz:** What did I do? Did I f\*\*\*\*\*\* your data set?

**Sachin Pandey:** image will no it will hide the image I

**Geoff Horowitz:** Oh.

**Sachin Pandey:** think.

**Geoff Horowitz:** Oh, cool. Cool. So,

**Sachin Pandey:** I'm not sure whether it's working correctly or not,

**Geoff Horowitz:** I Yeah,

**Sachin Pandey:** but it should hide the

### **02:49:52**

**Geoff Horowitz:** but now this is the wrong image,

**Sachin Pandey:** image.

**Geoff Horowitz:** isn't it? Maybe.

**Sachin Pandey:** Can you try hiding it

**Geoff Horowitz:** Yeah.

**Sachin Pandey:** again?

**Geoff Horowitz:** So, let me do let me do one.

**Sachin Pandey:** 130\. Yeah, it's getting hidden.

**Geoff Horowitz:** It's still there, though.

**Sachin Pandey:** No,

**Geoff Horowitz:** This is two.

**Sachin Pandey:** the count changes.

**Geoff Horowitz:** Oh,

**Sachin Pandey:** It's 129 instead of

**Geoff Horowitz:** what?

**Sachin Pandey:** 130\.

**Geoff Horowitz:** But it says one and actually one doesn't exist.

**Sachin Pandey:** The order has changed after removing the

**Geoff Horowitz:** Okay. Because one is just Yeah,

**Sachin Pandey:** file.

**Geoff Horowitz:** one is just an index.

**Sachin Pandey:** Yeah,

**Geoff Horowitz:** Fine.

**Sachin Pandey:** one is just templates.

**Geoff Horowitz:** Okay. All right.

**Sachin Pandey:** I will need to see how to reward it, guys.

**Geoff Horowitz:** Yeah. Yeah. Yeah. Yeah, now that I've rejected your images. Uh, undo. All right. Uh, okay. I think that's everything.

**Sachin Pandey:** Okay.

**Geoff Horowitz:** Oh, Satcha,

**Sachin Pandey:** Okay.

### **02:51:09**

**Geoff Horowitz:** can you uh you give me the link to data?

**Sachin Pandey:** link to

**Geoff Horowitz:** Link to the normal data.

**Sachin Pandey:** Yeah. Okay. You need the zip location.

**Geoff Horowitz:** I I don't care. I just want something so that Yeah, fine. Give me the zip location.

**Sachin Pandey:** I shared it in the chat.

**Geoff Horowitz:** Great. Thank you. Okay, that's done. Uh I'm talking to protect about the role data or the data. Okay. Um actually Rul since you're on the call me ask about this. Uh, have you have you been helping Protex with this with these two or you've been on a different uh

**Ratul Shashank:** Yeah, I am I'm using company UI for this.

**Geoff Horowitz:** Okay,

**Ratul Shashank:** He's doing the vanilla

**Geoff Horowitz:** fine. Then I am going to CC you.

**Ratul Shashank:** and

**Geoff Horowitz:** I'm going to CC you on this. Um, CC So shared this with me. Uh what we have discussed on the call maybe it was on Friday was this is the original fine this is the generated

### **02:54:24**

**Ratul Shashank:** Uh

**Geoff Horowitz:** object fine but number one I need the source for all of

**Ratul Shashank:** f\*\*\*.

**Geoff Horowitz:** these. So I need to know where these images came from and I don't know Number two, uh I want to compare it to like the real world example, right? And I don't see that now. I actually think that maybe maybe slide eight is like the real world example. Um,

**Ratul Shashank:** Real world example.

**Geoff Horowitz:** so like this is the synthetic this is the synthetically generated example, right? This is copy and paste, but I want to compare it to the real the real

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** raster.

**Ratul Shashank:** I am the Uh so you

**Geoff Horowitz:** Does that make sense? Which I can do.

**Ratul Shashank:** want I was just saying

**Geoff Horowitz:** Go ahead. I can do that.

**Ratul Shashank:** you sorry I I would just complete that sentence.

**Geoff Horowitz:** Yeah. Go ahead. Yes,

**Ratul Shashank:** Uh I was saying that you you just want the original source image and the

### **02:55:33**

**Geoff Horowitz:** please.

**Ratul Shashank:** synthetic image in one page. Am I understanding it

**Geoff Horowitz:** Not quite.

**Ratul Shashank:** correctly?

**Geoff Horowitz:** We already have the source image and the synthetic image. We already have those,

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** right? What what we don't have is the original image that the copy and pasted data came from.

**Ratul Shashank:** the annotation and

**Geoff Horowitz:** Yeah. Yeah.

**Ratul Shashank:** that

**Geoff Horowitz:** And that's what I want. Oh, actually it looks like project is adding that right now. What's up?

**Ratul Shashank:** uh regarding that uh uh to just finish what you were saying. I mean uh this would a pretext would be able to uh like he knows what images he is using.

**Geoff Horowitz:** Fine.

**Ratul Shashank:** So he would be uh much

**Geoff Horowitz:** Okay. Okay.

**Ratul Shashank:** uh

**Geoff Horowitz:** I think he's he's doing it right now. He's adding these in right now. So, I was asking you because I I thought you might have insight on that,

**Ratul Shashank:** better at that.

### **02:56:45**

**Ratul Shashank:** And yeah and and uh uh no I I

**Geoff Horowitz:** too.

**Ratul Shashank:** am like can I share what I am working it would be much more uh clear.

**Geoff Horowitz:** Yeah. Yeah. Go ahead. I also don't want to take too much longer. I know I've basically taken what is this almost three hours of your time today. So, I'd rather you guys spend it working.

**Ratul Shashank:** It's all right. It's all right. Uh so what Pratesh is uh training an entire stable diffusion model. What I did I I instead of training an entire uh

**Geoff Horowitz:** Yeah.

**Ratul Shashank:** complete new model, I just used an existing model that uh Z image

**Geoff Horowitz:** Good.

**Ratul Shashank:** turbo and I created a lower on our data set uh for over that stable diffusion model. So I I can just show you some examples of what it's generating. It would be very good at creating backgrounds which are

**Geoff Horowitz:** Yeah.

**Ratul Shashank:** not uh sorry the wrong uh it's everything is everything is red at this point.

### **02:58:16**

**Ratul Shashank:** So it would be a hassling to finding which image So this this is some this is what I what I tried something what project did uh but I pasted the annotation on uh different syntactically generated background.

**Geoff Horowitz:** Oh.

**Ratul Shashank:** So all of these

**Geoff Horowitz:** Huh?

**Ratul Shashank:** backgrounds, this is for the same file, but the background is different. To give you more examples, Uh this would be also a great example.

**Geoff Horowitz:** Right.

**Ratul Shashank:** Uh this this gap is just because I was using a res.1. Uh so it it is it can be in the remote but the background it it you can see it is it is not uh overly generating new features and it is not it it is not just uh copy pasting that exact background. So I was that's what I wanted to ask like is this something that can be used or like this can be used? Uh I wanted to know from you. I I would also share this with text because uh uh I need to work more on these

### **03:00:37**

**Geoff Horowitz:** Hey, I think ultimately we need to compare it against the underlying data and say, hey, does this resemble the underlying data, right? One thing that one thing that stands out to me is that that object uh on the left hand side there maybe stands out even more than an object would in the underlying data. That could be an issue. But um with without comparing it kind of firsthand,

**Ratul Shashank:** Yeah.

**Geoff Horowitz:** the backgrounds look somewhat realistic, at least to me.

**Ratul Shashank:** Yeah. I mean uh I I I uh since I have not talked to Pratips on this regard, so we have a gap on this.

**Geoff Horowitz:** Okay.

**Ratul Shashank:** But since you know uh since you also know what his pipeline what what stage this pipeline is. So the this does this this background thing is actually a problem

**Geoff Horowitz:** Yeah.

**Ratul Shashank:** or it's just

**Geoff Horowitz:** Um I think it is more for the role data than the underlying background data.

**Ratul Shashank:** hidden.

**Geoff Horowitz:** Um I think that we have enough basic background data but the problem is with the role data.

### **03:01:42**

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** I think the problem was with the role data.

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** Uh but project should be able to say more about

**Ratul Shashank:** Okay. I um uh yeah I we I need to discuss this

**Geoff Horowitz:** that.

**Ratul Shashank:** with him. I will. So this the this is uh better example because I was uh experimenting different types of like blending and generating different backgrounds. So this is still in uh a work in progress. I was not uh since was uh spearheading the stable decision part and uh that output is pretty good. So I was not giving this much attention but if it needs then I can I can work on it better. So that's is what I wanted to ask if this was uh relevant

**Geoff Horowitz:** Um I I I don't actually know the answer. I think it's important to talk to a project about it. I can see how I think it's important to be able to like generate this data, but it's not clear to me if we're if it's going to be critical because lack of data or not.

### **03:03:20**

**Geoff Horowitz:** Um, yeah,

**Ratul Shashank:** Uh when we say lack of data,

**Geoff Horowitz:** I I just don't know the answer.

**Ratul Shashank:** uh do we mean lack of the novelty in data or just uh features? Do we need more examples, more variance? Do we need more features? Do we not need more

**Geoff Horowitz:** I think in general we need more of the existing training data,

**Ratul Shashank:** combination?

**Geoff Horowitz:** right? But what makes a good training set is that it has within the same distribution, it has a variety of features, right? like it's not just duplicate images of the same exact feature. Does that make sense?

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** Um, I think it would be great for us to have like a wider distribution, but I don't think we can generate that necessarily based based on the data we have. Meaning so far the way we're doing this is to learn even from the diffusion models. We're learning from the underlying we're learning from the underlying training data. Right? So if we don't have an example of it in this pipeline, it might be difficult to generate it.

### **03:04:49**

**Geoff Horowitz:** Right? Can you guys hear me? S can you hear me?

**Sachin Pandey:** Yes.

**Geoff Horowitz:** I'm gonna Sin, you can drop if you want. I'm going to try to wrap this up. I feel bad for taking three hours of your time.

**Sachin Pandey:** Okay. Okay. Bye.

**Geoff Horowitz:** Bye. Hey, Rachel.

**Ratul Shashank:** Hey, sorry my internet cut off.

**Geoff Horowitz:** That's okay. What of that did you hear?

**Ratul Shashank:** Uh I was not able to hear your scripts. Uh like uh you were saying something and my internet just cut off in the middle. How can you feel

**Geoff Horowitz:** Yeah, I was just saying that um I think our immediate need

**Ratul Shashank:** just

**Geoff Horowitz:** is more data within kind of the generalized distribution of what we have. I think we'd love to have more like out of distribution data, but I don't think that we can I don't think that we can necessarily train a diffusion model on data we don't have. That's one thing. And then number two is how do we validate that that that that like out ofdistribution data is actually reliable, right?

### **03:06:33**

**Geoff Horowitz:** So for those reasons, I think that's going to be harder. Um, did that answer your

**Ratul Shashank:** Yeah,

**Geoff Horowitz:** question?

**Ratul Shashank:** I I understand that. So we we just uh in in summary, we need more novelty so or more variance in data.

**Geoff Horowitz:** I I think so. Yeah. Um, I think that's reasonable.

**Ratul Shashank:** Yeah, I will I will talk with Pratik on this. I think because we the backgrounds that we have is very similar to the original background. We are just pasting the objects on the background. But yeah, I I will talk to him regarding this.

**Geoff Horowitz:** I Okay. Uh, Rachel, I'm gonna go. Thanks for uh thanks for the time today and I will talk to you either tomorrow or Friday. All right. Thanks.

**Ratul Shashank:** Oh,

**Geoff Horowitz:** And let me know let me know if you need any clarification on the agent or let me know if you have any updates on it.

**Ratul Shashank:** I actually have I just like I can share a quick uh summary of what of what stage it is in.

### **03:07:48**

**Geoff Horowitz:** Uh I'm talking about the agent for generating this uh this model tracking status.

**Ratul Shashank:** Oh. Oh. Okay. Okay.

**Geoff Horowitz:** Yeah,

**Ratul Shashank:** It's um I think I think I can it it should be up and running like tomorrow. It won't be a

**Geoff Horowitz:** sounds good. In terms in terms of the other one,

**Ratul Shashank:** problem.

**Geoff Horowitz:** um I don't know, man. Either either share an update with me or we can we can set aside some time to discuss it when I have a little bit more time. Does that work?

**Ratul Shashank:** Yeah. that that's why I was not sharing anything with you because we are all occupied.

**Geoff Horowitz:** I know we

**Ratul Shashank:** So I I thought it was not a good time to share this with

**Geoff Horowitz:** are it's not it's not so I

**Ratul Shashank:** you.

**Geoff Horowitz:** appreciate that but uh but we can talk about it uh at least after my meeting with

**Ratul Shashank:** Yeah, no problem.

**Geoff Horowitz:** Bedrock.

**Ratul Shashank:** Uh and in the meantime, I'm just making a few changes here and there. Uh and when whenever whenever you want,

**Geoff Horowitz:** Sounds good.

**Ratul Shashank:** I can just share it.

**Geoff Horowitz:** Sounds crazy. Thank you, Rachel.

**Ratul Shashank:** Okay,

**Geoff Horowitz:** Okay,

**Ratul Shashank:** thank you.

**Geoff Horowitz:** byebye.

**Ratul Shashank:** Bye.

### **Transcription ended after 03:09:04**

*This editable transcript was computer generated and might contain errors. People can also change the text after it was created.*
