# **📝 Notes**

Aug 5, 2026

## **Iris Sync**

Invited [Sachin Pandey](mailto:sachin@crescer.ai) [Pratyaksh Singh](mailto:pratyaksh@crescer.ai) [Hemanth Sarabu](mailto:hemanth@crescer.ai) [Geoff Horowitz](mailto:geoff@crescer.ai) [Siddharth Soni](mailto:siddharth@crescer.ai) [Ratul Shashank](mailto:ratul@crescer.ai)

Attachments [Iris Sync](https://calendar.google.com/calendar/event?eid=NnNzMHVxNzk3MmJqZGVwNXFoN2J1Mjd1OTdfMjAyNjA4MDVUMTYzMDAwWiBnZW9mZkBjcmVzY2VyLmFp)

Meeting records [Transcript](https://docs.google.com/document/d/1__ZUcWgISwI1x7_cqAgcGn4UQ32eEv30BxuYO1B2ATY/edit?usp=drive_web&tab=t.xdt15q285jjm) [Recording](https://drive.google.com/file/d/1R6jI27Bu6pIfro39iaRZrqj4mCNS6BUo/view?usp=drive_web) 

### **Summary**

Technical data processing shifts and generative modeling strategies are reviewed for improved model evaluation and performance.

**Technical Methodology and Metrics**  
Data processing transitioned from pixel grids to geographic grids to resolve boundary issues. The team decided to shift focus toward object level precision and recall metrics.

**Inference and Configuration Requirements**  
Filters will exclude small objects to refine area of interest classifications. The team will prioritize direct performance visualization over K fold cross validation for current data.

**Synthetic Data Generation Techniques**  
Generative model development is shifting toward decomposition techniques to better simulate seabed imagery. Previous methods like LoRa and GANs were deemed inefficient for current needs.

### **Decisions**

## Aligned

* **Adoption of 100m geographic grid** The team shifted the data processing methodology from a 128x128 pixel-based grid to a 100m x 100m geographic grid to prevent data loss.

* **V4 model adoption as standard** The V4 model is confirmed as the gold standard for current development, superseding the V3 model due to the latter's high false-positive rate.

## Shelved

* **Discontinuation of GAN-based generation** The use of GAN-based methods for synthetic data generation is ruled out due to insufficient data availability and model instability.

We've **updated the Decisions section** using your feedback.

Let us know what you think: [Helpful](https://google.qualtrics.com/jfe/form/SV_5bXzKQfylMIhSXc?isHelpful=True&entryPoint=decisions&confid=NstR_jNQUrPW8rHCnu0HDxIUOBEBMgUIigIgABgECA&isGoogler=False) or [Not Helpful](https://google.qualtrics.com/jfe/form/SV_5bXzKQfylMIhSXc?isHelpful=False&entryPoint=decisions&confid=NstR_jNQUrPW8rHCnu0HDxIUOBEBMgUIigIgABgECA&isGoogler=False)

### **Next steps**

- [ ] \[Sachin Pandey\] Share Performance Report: Share the HTML report detailing V4 model performance on new data. Include object-level results across folds to allow for direct comparisons.

- [ ] \[Sachin Pandey\] Run Inference: Perform inference on new data using the V4 model.

- [ ] \[Sachin Pandey\] Update Model Overview: Update the model overview in Notion with K-fold and inference metrics. Summarize findings in a format consistent with previous model documentation.

- [ ] \[Ratul Shashank\] Generate Synthetic Objects: Produce remaining synthetic UXOs and AOI small black objects.

- [ ] \[Ratul Shashank\] Create Comparison Slides: Compile original and generated object images into a PowerPoint presentation.

- [ ] \[Ratul Shashank\] Explore Generative Methods: Evaluate the suggested generative prototypes found in Wally and discuss the findings in the next meeting.

### **Details**

* **Ratul Shashank's Personal Status**: Ratul Shashank shares a personal update confirming that they have completed their move, though they have left some items at Sachin Pandey's house. They plan to move back to Delhi around September or October ([00:00:00](#00:00:00)).

* **Sachin Pandey's Technical Methodology Update**: Sachin Pandey explains a shift in their data processing approach. Initially, they utilized a 128-by-128 pixel grid to separate port and starboard data and eliminate black regions, but this caused issues with grid boundaries and overlapping ([00:01:25](#00:01:25)). To ensure no targets are lost, they have transitioned to a new method using a 100-meter by 100-meter geographic grid, which involves cropping the base image to match this specific map grid rather than using pixel-based cropping ([00:06:49](#00:06:49)).

* **Model Training and Evaluation Metrics**: Sachin Pandey notes that the model is currently training on the new data, with the V2 model performing best on the previous iteration due to high intersection over union (IoU) scores ([00:08:56](#00:08:56)). Hemanth Sarabu emphasizes that the team must prioritize object-level precision and recall metrics rather than pixel-level metrics for accurate comparisons, as pixel-level analysis has caused confusion regarding model superiority ([00:10:07](#00:10:07)). Sachin Pandey confirms they currently lack these object-level metrics and will need to evaluate them before verifying the accuracy of the current iteration ([00:11:21](#00:11:21)).

* **Inference and Model Configuration Requirements**: Regarding predictions on new data, Sachin Pandey identifies the need for a filter for areas of interest (AOI) to exclude items smaller than 2,000 to 3,000 pixels. Geoff Horowitz advises creating a configuration to manage class outputs, specifically to focus on unexploded ordnance (UXO) and combined small black classes while excluding other classifications like AOI big ([00:13:17](#00:13:17)). Sachin Pandey plans to use an older script pipeline to visualize masks for the team, as an automated feature for this is not yet available ([00:14:33](#00:14:33)).

* **Clarification on K-Fold Relevance**: Regarding the use of K-fold cross-validation on the new data, Hemanth Sarabu and Sachin Pandey discuss the necessity of the fold structure. They conclude that because they are not training on this specific new dataset, the K-fold framework is less relevant, and the team will focus on visualizing model performance on the new data directly ([00:16:00](#00:16:00)).

* **Reporting and Next Steps**: Geoff Horowitz mandates that Sachin Pandey must share object-level results for the new K-fold iterations and perform inference on the new data using the V4 model to ensure apples-to-apples comparisons ([00:17:25](#00:17:25)). Sachin Pandey is to document these results, including summaries for K-fold and inference, within the model overview in the team's Notion platform ([00:21:24](#00:21:24)).

* **Synthetic Data Generation Progress**: Ratul Shashank provides an update on synthetic object generation, noting a shift from copy-paste documentation to using models like GPT to create novel examples that retain the original blob-like structures of UXOs. Ratul Shashank has shared these generated crops with the team for composition on background imagery, and they plan to generate examples for AOI small black tonight ([00:24:59](#00:24:59)) ([00:30:54](#00:30:54)).

* **Exploration of Synthetic Data Techniques**: Ratul Shashank discusses the limitations of using LoRa, which was unsuccessful, and GANs, which require too much data ([00:34:17](#00:34:17)). Hemanth Sarabu presents a prototype using decomposition techniques—breaking images into structure and speckle components—to improve the placement of objects into new images ([00:38:17](#00:38:17)). Ratul Shashank and Hemanth Sarabu discuss the potential of this method to maintain object identity while simulating realistic placement in the seabed ([00:40:50](#00:40:50)).

* **Additional Research and Future Methods**: Hemanth Sarabu introduces further generative methods, including creating sand ripples using VGG statistics and using style transfer-based remixing, noting that while fast Fourier transform (FFT) was previously attempted without success, the team can review the code path provided in the discussion threads regarding Wall-E resources ([00:44:45](#00:44:45)). Ratul Shashank agrees to investigate these suggestions and discuss the findings with Pratyaksh before the next meeting ([00:45:44](#00:45:44)).

*You should review Gemini's notes to make sure they're accurate. [Get tips and learn how Gemini takes notes](https://support.google.com/meet/answer/14754931)*

*How is the quality of **these specific notes?** [Take a short survey](https://google.qualtrics.com/jfe/form/SV_5bXzKQfylMIhSXc?confid=NstR_jNQUrPW8rHCnu0HDxIUOBEBMgUIigIgABgECA&detailLevel=standard&hasImages=False&entryPoint=footerMain&isGoogler=False) to let us know your feedback, including how helpful the notes were for your needs.*

# **📖 Transcript**

Aug 5, 2026

## **Iris Sync \- Transcript**

### **00:00:00** {#00:00:00}

**Ratul Shashank:** think I did too much but

**Geoff Horowitz:** Say that again. Too much traveling.

**Ratul Shashank:** yeah it is

**Geoff Horowitz:** What? What did you say? Too much

**Ratul Shashank:** uh uh I said I am better

**Geoff Horowitz:** what?

**Ratul Shashank:** now I think I did too much traveling and I exhausted my body so that's

**Geoff Horowitz:** Oh no. Oh no. So did you you finished the move? Everything's all done now.

**Ratul Shashank:** Yeah. Yeah. I mean uh I have uh I have uh uh I have kept few stuff at Sachin's house. So I plan on moving back to Delhi uh somewhere around

**Geoff Horowitz:** Uh-huh.

**Ratul Shashank:** September or October. So yeah,

**Geoff Horowitz:** Nice.

**Ratul Shashank:** it's it's

**Geoff Horowitz:** Nice.

**Ratul Shashank:** done.

**Sachin Pandey:** I

**Geoff Horowitz:** It's our turn. Okay. Um, all right. Let's I know protection isn't going to be here. Um, and Ratul I know He is going to want to uh hear what you have to say. So, Sachin, let's start with you.

### **00:01:25** {#00:01:25}

**Geoff Horowitz:** Excuse me. Um, Sachin, why don't you fill out my my tracker for me?

**Sachin Pandey:** Where is the

**Geoff Horowitz:** I'm

**Sachin Pandey:** tracker?

**Geoff Horowitz:** here. I'm just looking through your report. Why do we need two meters around the image?

**Sachin Pandey:** Uh where do

**Geoff Horowitz:** Okay.

**Sachin Pandey:** we

**Geoff Horowitz:** Why don't you talk me through Why don't you talk me through this report

**Sachin Pandey:** so should I share my

**Geoff Horowitz:** if you want to?

**Sachin Pandey:** screen?

**Geoff Horowitz:** I don't really care as long as as long as you're explaining it to me in words that I understand. I don't really care how you do

**Sachin Pandey:** Okay.

**Geoff Horowitz:** it.

**Sachin Pandey:** So the main idea before training the data was to like split the data equally. So the like each validation set like each pole represent the data in a meaningful

**Geoff Horowitz:** Uh

**Sachin Pandey:** way. So earlier we tried to do it something like this. uh this the base data was the cropped images which I prepared for cutex where we we segregated the seabboard and port separately cropped them remove the black region completely and then cropped them out and even when cropping the padding was to

### **00:03:33**

**Geoff Horowitz:** Mhm.

**Sachin Pandey:** overlap not to create a black region. So this is how the base image were created 128 across 128 and I

**Geoff Horowitz:** One second. One second. One second.

**Sachin Pandey:** use

**Geoff Horowitz:** Even when cropping, it was to create o to avoid overlap. Say, say the last

**Sachin Pandey:** to avoid like black region like there because like

**Geoff Horowitz:** question.

**Sachin Pandey:** complaining like there were a lot of like black region in the data

**Geoff Horowitz:** Uh, okay.

**Sachin Pandey:** so that model was not able to learn it because of those black areas.

**Geoff Horowitz:** Okay.

**Sachin Pandey:** So we try to minimize those black region like completely by trimming in out and when like

**Geoff Horowitz:** Right.

**Sachin Pandey:** adding a padding for uh to make the like 128 grid we are like

**Geoff Horowitz:** Okay.

**Sachin Pandey:** overlapping the region instead of adding the black region as a padding. So this was the base data which we used to separate it out.

**Geoff Horowitz:** Okay.

**Sachin Pandey:** The idea was simple like we want to categorize like uh grid by grid.

### **00:04:37**

**Sachin Pandey:** uh we will put the grid on the map and then pull all the like boxes or like the 128 grid images inside it. And the reason it was like lefting out these gaps because it we don't won't want any overlap because there is like two type of grid. One is the like the actual geographical grid which is creating the like boundary and other is like the 128 grid which is already there in the image. That's why like we can't get like cleaner cut and we have to like remove a lot of points here.

**Geoff Horowitz:** Okay,

**Sachin Pandey:** This was this is a zoomed in image of the same area.

**Geoff Horowitz:** I see. Hey,

**Sachin Pandey:** So I so

**Geoff Horowitz:** ammo.

**Hemanth Sarabu:** Hey,

**Geoff Horowitz:** Uh Sachin,

**Sachin Pandey:** I

**Geoff Horowitz:** do do a very do a very very quick re recap for Hemanth,

**Hemanth Sarabu:** thanks guys.

**Geoff Horowitz:** please.

**Sachin Pandey:** Yeah. So base image. So remember we all the all all data we in the base data we have 128 \+ 128 grid of cropped images without any black region and

### **00:05:43**

**Hemanth Sarabu:** without any water regions.

**Sachin Pandey:** we without any black region like we split the starboard input separately and trim

**Geoff Horowitz:** black regions.

**Sachin Pandey:** down the like black region and then cropped the like 128 grits. This was used to like generate the mass uh like use the as a base data. Then we like plot the then we draw a grid on like act map and then pull the like pull like small 128 images into that grid and classified it as the like in which fold it will be going. So this is the like short overview. We were missing a like lot of images on the empty region you are seeing we were removing it because we don't want any overlap. So this is highly related to how many like overlap region there are. So same grid could have like lose suppose 10 images where there's high overlap and like only one image if there's a low overlap. So

**Geoff Horowitz:** Um just so but to be clear Sachin and we didn't

**Sachin Pandey:** so

**Hemanth Sarabu:** Okay,

**Geoff Horowitz:** lose the the areas that we lost back we

### **00:06:49** {#00:06:49}

**Sachin Pandey:** no we didn't we didn't lose the actual data.

**Geoff Horowitz:** didn't lose any targets we didn't lose

**Sachin Pandey:** Yes, we

**Hemanth Sarabu:** we didn't lose any what,

**Geoff Horowitz:** any targets.

**Hemanth Sarabu:** Jeff?

**Sachin Pandey:** didn't.

**Geoff Horowitz:** We didn't lose any UXOs. We only lost background

**Hemanth Sarabu:** All right.

**Geoff Horowitz:** areas.

**Sachin Pandey:** So like if you see like most of the loss was in P data set because it was like very concentrated in one area and with a lot of overlap. So other uh PX told me like it may not work. So we like split it again. Instead of using the like the 128 grid, we use the whole image as this and started cropping like 100 plus 100 m uh on the map. And we will be like cropping the base image, the actual image with with this grid to get

**Geoff Horowitz:** So, so instead of doing it by pixels 128 by 128,

**Sachin Pandey:** the

**Geoff Horowitz:** you move to doing it in a geographic grid of 100 meters by 100 meters.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** Okay.

### **00:07:49**

**Sachin Pandey:** So instead of earlier like mapping two grid and matching whichever is the best like edge we are like only focusing on one grid which will be the map grid and we will crop the base image to match with the grid the actual map grid. So this is like how it looks. So it it reduced yeah we we changed the data.

**Hemanth Sarabu:** So this is a different iteration.

**Sachin Pandey:** So this one because we are

**Hemanth Sarabu:** So the first one you showed is no longer

**Sachin Pandey:** only

**Hemanth Sarabu:** relevant.

**Sachin Pandey:** uh yeah it was like that was the first iteration of the breaker.

**Hemanth Sarabu:** Okay. I just want to make sure that we don't have to worry about that anymore. Is that right? Like we're not going to use it for anything, etc.

**Sachin Pandey:** So like I did train the train the model on that until this data was ready. So like we can just check if how it's performing because like this

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** way like this will be on the old data was like using the grid where the starboard and port are separated and this was is like this is similar to the original image which we are passing and yeah one more thing like

### **00:08:56** {#00:08:56}

**Hemanth Sarabu:** But you don't have the you don't have the training done on this.

**Sachin Pandey:** yeah I I started a training on this it's still running. So the main like uh reason for this was to be we don't want to lose any

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** of the images. So we like we drop the like grid instead of choosing the grid we will choose the whole image and drop the image as for our needs based on the what we the grid we get from the map. So this was how like this data was created and

**Hemanth Sarabu:** Okay. Okay.

**Sachin Pandey:** yeah it is representing like all the uh points roughly like two minimum two UXOs are present in all the like folds

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** and currently like model is

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** training on uh this one. We have the result for this one where like the B1 model was doing best around yeah like

**Geoff Horowitz:** V1. Are we on V4?

**Sachin Pandey:** because we we the idea was to we will test all the model on same Kfold pipeline.

### **00:10:07** {#00:10:07}

**Geoff Horowitz:** Yeah. Okay.

**Sachin Pandey:** So sorry not V1 the base V2 was doing the best like it was getting a like very high IOU. Maybe one reason will be because the like the loss in the the B4 they target

**Geoff Horowitz:** Each

**Sachin Pandey:** more about like the object level not on the pixel level.

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** And but that was the result for the like

**Hemanth Sarabu:** Wait, wait. Listen.

**Sachin Pandey:** the

**Hemanth Sarabu:** Do you have object level precision recall results?

**Sachin Pandey:** not now

**Hemanth Sarabu:** In the previous meetings, what metric have we used to measure performance?

**Sachin Pandey:** it was object

**Hemanth Sarabu:** Why are we talking about pixel level metrics right now?

**Sachin Pandey:** So we we don't have that matrix yet.

**Hemanth Sarabu:** Okay. So that's what that's what I want you to say.

**Sachin Pandey:** Uh

**Hemanth Sarabu:** If you start talking about pixel level, all of a sudden you've confused us saying, "Oh, Wii1 is better. W2 is better." Right? We're not comparing

**Sachin Pandey:** yeah that's why like I want to test it out on the like object level to see whether like how many calls

### **00:11:21** {#00:11:21}

**Hemanth Sarabu:** apples.

**Sachin Pandey:** positive or UX we are getting or we we are missing We are missing on IOU overlaps. Uh the B yeah the older model were doing

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** better.

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** It was for this data set. Uh the new training is still running.

**Hemanth Sarabu:** Fine.

**Sachin Pandey:** We will get the results soon for this data set where there is no loss in the

**Hemanth Sarabu:** Okay,

**Sachin Pandey:** data.

**Hemanth Sarabu:** that's fine. Do you have object level precision recall metrics for your first iteration of splitting?

**Sachin Pandey:** Uh, no, not yet.

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** I will test it out before like saying it's correct.

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** Uh, Sachin, did you get a chance to look through the new

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** data?

**Sachin Pandey:** Yeah. Uh, I predicted on it, but I don't Yeah, these are the predictions on the like on the new data.

**Geoff Horowitz:** These are the predictions in the new data. What are we seeing?

**Sachin Pandey:** uh the image is too small.

### **00:13:17** {#00:13:17}

**Sachin Pandey:** We can get an idea about like the from these numbers because we don't have any ground to

**Geoff Horowitz:** I would be shocked if we have AOI

**Sachin Pandey:** yeah we need to add the filter too because the filter we were using at the

**Geoff Horowitz:** big

**Sachin Pandey:** minimum the AI bit should be at least like 2,000 pixel or 3,000 pixel. So we will add the filter here too.

**Geoff Horowitz:** Sachin, I think when we deliver this model, we need to have a a config or something to say which classes we want to output and which ones we don't.

**Sachin Pandey:** Suppose bank is only interested in UXO. So we will only deliver

**Geoff Horowitz:** UXO.

**Sachin Pandey:** that.

**Geoff Horowitz:** Well, we've we've combined UXO and small black, right? Right.

**Sachin Pandey:** Yeah.

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** So, I guess I need to get a better understanding of Black Hatch. I forgot which one Black Hatch was,

**Hemanth Sarabu:** Oops.

**Geoff Horowitz:** but I know we don't want AOI big.

**Hemanth Sarabu:** So, is there a way you can make you can um you can rerun these in a way that we can

### **00:14:33** {#00:14:33}

**Geoff Horowitz:** Um,

**Hemanth Sarabu:** actually inspect the masks like we can actually see them.

**Sachin Pandey:** uh so I can put it into the like older script older pipeline.

**Hemanth Sarabu:** Yeah. Can we not pass it? Uh yeah. Okay. Can we not pass it through our app or

**Sachin Pandey:** Yeah,

**Hemanth Sarabu:** something?

**Sachin Pandey:** it will be similar like the way we are we were viewing it earlier. I can put it like that where you can just select the model and the mask will display on the bottom right.

**Hemanth Sarabu:** Okay, great.

**Sachin Pandey:** Do we want like offer all of them like

**Hemanth Sarabu:** uh any pick an interesting one and then we'll look at it

**Sachin Pandey:** this will be the main one like the B4 base and from fold we have to choose

**Hemanth Sarabu:** for world.

**Sachin Pandey:** one.

**Hemanth Sarabu:** So these are four um this is the new data right.

**Sachin Pandey:** Yeah, this is the new No,

**Hemanth Sarabu:** So this is not part of the training set.

**Sachin Pandey:** it's not.

**Hemanth Sarabu:** So the for the fold is just there's meaningless here right we don't have to worry about for here.

### **00:16:00** {#00:16:00}

**Sachin Pandey:** India we can say that so we only want to see the V4

**Geoff Horowitz:** Son, does that make sense?

**Sachin Pandey:** performance

**Geoff Horowitz:** Does that make sense? Why though?

**Sachin Pandey:** because like we will not be delivering the fold and we want to see the model we like we may deliver how it is doing on the new data

**Geoff Horowitz:** Uh I mean what you're saying is true but the purpose of the folds are so that you can train on you know in in this case you can train on four of them and predict on one and then kind of keep rotating it right but that's what he is saying since we're not training on this data it doesn't that that whole schema doesn't make any sense does does this make sense

**Sachin Pandey:** Yeah. then it it will be simpler. We just have to plot one images.

**Hemanth Sarabu:** Wait,

**Sachin Pandey:** I

**Hemanth Sarabu:** wait.

**Sachin Pandey:** can

**Hemanth Sarabu:** Sachin, why are those plots in falls?

**Sachin Pandey:** via those.

**Hemanth Sarabu:** Why Why are there falls here?

**Sachin Pandey:** I thought like we want to see the performance on like all the models like all the latest models like there will be a like I think there will be a chance where the V4 is not doing well and some of the code will do well on this data.

### **00:17:25** {#00:17:25}

**Hemanth Sarabu:** Okay. Sachin have you have you spent any time looking at uh cross validation careful cross validation? concepts. Okay.

**Sachin Pandey:** Yeah,

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** I will uh share the report with the HTML for like on how the V4 is performing on the new data.

**Geoff Horowitz:** Uh, okay. So, so let's recap. Satchin, you you're gonna share. Let me let me just update my notes quickly. One second. Um, okay. So, you're going to share the results from the new from the new K-fold um, iterations, right? Object level results so that we can get kind of apples to apples.

**Sachin Pandey:** Okay.

**Geoff Horowitz:** And that's going to be results for each of the folds on each of the models um that we're that we're looking at. Is that correct?

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Okay. Um when you do that, make sure to kind of look through and make sure it makes sense, right? Uh, I I would expect I mean maybe we'll have some outliers, but I would expect at least some of the results to look very similar to the baseline V4 results that we already have.

### **00:19:26**

**Geoff Horowitz:** Uh, and if it doesn't, I mean, you know, you should you should have a very compelling reason about why why it doesn't and why that makes sense to you. Is that you you following me?

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Okay.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** So you have the kayfold. Um you're also going to run inference on the new data and give us the results for that,

**Sachin Pandey:** Okay.

**Geoff Horowitz:** right?

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** Which which model are you going to use?

**Sachin Pandey:** V4.

**Geoff Horowitz:** You're going to use the V4 model. Okay. Um,

**Sachin Pandey:** Yes.

**Geoff Horowitz:** is there is there an open question about like maybe the V3 model is better,

**Sachin Pandey:** Uh no like B3 was predicting a lot of false positives. So,

**Geoff Horowitz:** right,

**Sachin Pandey:** like I don't think it's a good

**Geoff Horowitz:** right, right. Okay. Yeah.

**Sachin Pandey:** model.

**Geoff Horowitz:** I I thought we were all kind of on the same page that V4 is is the gold standard right now. Uh,

### **00:20:24**

**Hemanth Sarabu:** I mean, we didn't do K4 on it,

**Sachin Pandey:** Yeah.

**Hemanth Sarabu:** right? So,

**Geoff Horowitz:** we did not do a on it.

**Hemanth Sarabu:** we don't Yeah.

**Geoff Horowitz:** So, we don't know. Um, I mean then I guess if it's just inference, it wouldn't hurt to run V3 on the the

**Hemanth Sarabu:** Yeah, I mean on the new data why why not just uh if we have we

**Geoff Horowitz:** old

**Hemanth Sarabu:** should have a way to just run it and visualize the data right that does not look like um like an interactive version. Do we not have that?

**Sachin Pandey:** We have like we can like upload here even the XDF for the image and it will show you

**Geoff Horowitz:** But we don't need to do it one by one,

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** right?

**Sachin Pandey:** But

**Geoff Horowitz:** Can't you just send it to a whole folder and it'll run the results and save them? You know, save the results, save the mask, save all the things that it's it's outputting here. Now,

**Sachin Pandey:** no, that that feature is not yet

### **00:21:24** {#00:21:24}

**Hemanth Sarabu:** Got it.

**Sachin Pandey:** available.

**Hemanth Sarabu:** But But can we just take a look? Can we put one through here and see how it

**Sachin Pandey:** Yeah.

**Hemanth Sarabu:** looks?

**Geoff Horowitz:** Um I I have to leave in about 10 minutes. Um Sachin, do you want to look for this while tool gives an

**Sachin Pandey:** Yeah,

**Geoff Horowitz:** update?

**Sachin Pandey:** I I will post the image in the

**Geoff Horowitz:** Okay, fine.

**Sachin Pandey:** chat.

**Geoff Horowitz:** Um Sachin even even if you talk about it with Hemanth here I today if possible I want you to I want you to update our you know model overviews with these metrics right it should be very easy for us to look at this and understand the results quickly uh Even if you have to link a report that goes into more detail elsewhere in the

**Sachin Pandey:** model overview in the learning notion.

**Geoff Horowitz:** running notes, that's what I'm talking about. In the same way that we've done,

**Sachin Pandey:** Okay.

**Geoff Horowitz:** you know, the baseline, we did a summary for the baseline, we did a summary for V2, we did a summary for V3.

### **00:24:59** {#00:24:59}

**Geoff Horowitz:** I think we have a summary for V4 there also. Uh, you know, we should have a summary for for the K-fold. We should have a summary for the inference. Uh,

**Sachin Pandey:** Okay.

**Geoff Horowitz:** okay.

**Sachin Pandey:** Yeah, I will get

**Geoff Horowitz:** Okay. All right.

**Sachin Pandey:** it.

**Geoff Horowitz:** Uh, Rachel, do you want to give us an

**Ratul Shashank:** Yeah. Yeah. Uh just a short update on my end.

**Geoff Horowitz:** update?

**Ratul Shashank:** Uh let me just recap what we talked about since the meeting on 31st. Uh in the last meeting I shared that uh we were we were done using the copy paste documentation and as the text mentioned that that can that is fine so we can do this later. uh and then shifted to generating the objects generating the objects using the models like GPT or open uh nano banana. So I have a few examples. Let me just share my screen. Uh my screen is visible right?

**Hemanth Sarabu:** It's Jeff. Damn.

### **00:26:34**

**Geoff Horowitz:** I cannot see it. Can you Oh,

**Hemanth Sarabu:** No, it's coming up now. Guys,

**Geoff Horowitz:** it's coming up now.

**Hemanth Sarabu:** did Jeff Dean leave Google? What?

**Ratul Shashank:** What?

**Geoff Horowitz:** What did you say?

**Hemanth Sarabu:** Jeff Dean left Google now.

**Ratul Shashank:** Uh yeah. So

**Hemanth Sarabu:** s\*\*\*. Okay.

**Ratul Shashank:** So like these are the option these are the generated

**Geoff Horowitz:** launch discovery.

**Hemanth Sarabu:** Okay.

**Ratul Shashank:** objects. Like the reasoning behind changing the path was uh we can do this copy paste augmentation and changing the height and those values even later. Pratyaksh wants novel examples of the objects. So, so he asked if it is possible to create novel examples or close to the real examples like as close as possible. So I created a master prompt and uh did a quick image to image generation keeping that master prompt so that GPT can create this grid of 10 images as close as the original but like keeping the original images blob like like structure. uh and in making it as novel as it it can be.

### **00:28:17**

**Geoff Horowitz:** Ratul, can you show me the

**Ratul Shashank:** Yeah. Uh this is UX

**Geoff Horowitz:** original.

**Ratul Shashank:** 0\. This folder is a mess. I

**Hemanth Sarabu:** Open.

**Ratul Shashank:** just

**Hemanth Sarabu:** Yeah, he did leave Google. That is crazy.

**Geoff Horowitz:** Looks like his own friend's own startup.

**Hemanth Sarabu:** I mean, yeah, it's child. It's been there since the '9s.

**Geoff Horowitz:** What did it say? 23

**Hemanth Sarabu:** Um, let me see.

**Geoff Horowitz:** years.

**Hemanth Sarabu:** Uh, it's been with Google since 1999\. Crazy.

**Geoff Horowitz:** 26 years.

**Hemanth Sarabu:** 20\. Yeah. 27 years 1 month. He took he took what he took all the all the strong scientists with him.

**Geoff Horowitz:** Okay, Rachel. Well, I don't want to take too long. Just throw this together in a PowerPoint at some point where you have you have the generated and you have the original,

**Ratul Shashank:** Yeah.

**Geoff Horowitz:** right?

**Ratul Shashank:** Yeah.

**Geoff Horowitz:** That's exactly how we show just like you can see in this PowerPoint.

**Ratul Shashank:** Uh

**Geoff Horowitz:** That's how we show it to Bedrock 2, where we show the original and we show the the

### **00:30:54** {#00:30:54}

**Ratul Shashank:** yeah,

**Hemanth Sarabu:** You got

**Ratul Shashank:** I mean I I am having trouble finding that exact uh

**Geoff Horowitz:** synthetic.

**Hemanth Sarabu:** one.

**Ratul Shashank:** document. I think this is it. This is it.

**Geoff Horowitz:** Oh, it's that one.

**Ratul Shashank:** Yeah. I mean this is UXO001 and this is the original image and this is

**Geoff Horowitz:** Yeah.

**Ratul Shashank:** the generated examples. to give you a little more examples. So,

**Geoff Horowitz:** Okay.

**Ratul Shashank:** this this has both of them this folder. This is the generated examples and this is the original image.

**Hemanth Sarabu:** So what's the what's the what's the

**Geoff Horowitz:** Okay.

**Hemanth Sarabu:** conclusion

**Ratul Shashank:** uh so the conclusion is just we wanted step A we wanted novel objects and the next step would be we would add we would be adding augmentations like changing height and other stuff later. So this was the this was the first step I have generated for the UFXOs and the AOI small black are left. I will do that tonight. Yeah, I mean that is the update.

### **00:33:00**

**Hemanth Sarabu:** Okay. Okay.

**Ratul Shashank:** Uh, and I also have a question

**Geoff Horowitz:** So R tool, oh sorry, Ratul,

**Ratul Shashank:** like

**Geoff Horowitz:** the the objective here is as I recall brat is generating backgrounds and we're going to use this to generate the objects and then we'll combine the

**Ratul Shashank:** yeah I

**Geoff Horowitz:** two, right?

**Ratul Shashank:** mean I have I have shared the crops with him. like I I sh I have shared the this grid and he shared that the objects

**Geoff Horowitz:** Okay.

**Ratul Shashank:** look good. So I have shared the crops of each objects and he will composite them on the background

**Geoff Horowitz:** Okay.

**Hemanth Sarabu:** Nice.

**Ratul Shashank:** and you will

**Geoff Horowitz:** Okay.

**Ratul Shashank:** see uh and the question that I had

**Geoff Horowitz:** But none of this is blocking our I think none of this is blocking our milestone too.

**Ratul Shashank:** was uh

**Geoff Horowitz:** Yep.

**Ratul Shashank:** not to my knowledge

**Geoff Horowitz:** What? Oh, is there a delay?

**Ratul Shashank:** My wifi is lagging. Can you please repeat? Sorry.

### **00:34:17** {#00:34:17}

**Geoff Horowitz:** Go ahead. You had a question.

**Ratul Shashank:** Oh. uh like I the question that I had was this is just generating

**Hemanth Sarabu:** Oops.

**Ratul Shashank:** objects using a prompt and the image of the uh actual object like image to image generation. Uh we tried LoRa and it was not very successful. Um is there any other path that uh that can be explored like I asked using GAN and P mention that it is it it it's not useful for us because it requires too much data. Is there something else that that can be used regarding JIP specifically?

**Hemanth Sarabu:** Uh is the question diffusion requests too much data? Is there something else we can do?

**Geoff Horowitz:** Oh,

**Hemanth Sarabu:** Is that the

**Ratul Shashank:** Uh no uh the question is regarding the path of uh like what else can we

**Hemanth Sarabu:** question

**Ratul Shashank:** try?

**Hemanth Sarabu:** to generate new data?

**Ratul Shashank:** So we yeah we already tried Laura and it was not it was not very successful. Um I I I asked I Googled and I asked uh these agents what can we try and they mentioned that uh some uh industries like medical and those industries they use GAN to generate data.

### **00:35:57**

**Ratul Shashank:** But this is not uh this is not very helpful for us because uh as uh I discussed this with script and he said that GAN would require uh too much data and we lack that.

**Hemanth Sarabu:** Yeah, Gan is GA requires a lot of data is unstable as

**Ratul Shashank:** So yeah so that is why I

**Hemanth Sarabu:** well.

**Geoff Horowitz:** Uh,

**Ratul Shashank:** wanted to ask is there something else that we can try

**Geoff Horowitz:** Wait,

**Ratul Shashank:** because

**Geoff Horowitz:** sorry. Sorry guys, I need to drop um Hemanth one, I think this goes into the question, although please keep having the conversation. One of the things that Hemoth asked projects to look into, which I still think is a good idea, is injecting injecting some of these targets in the latent space and then um uh you know decencing them to kind of see see how they come out. I I still think that's pretty cool idea. I'm not I haven't seen any updates on them. How about maybe project told you?

**Hemanth Sarabu:** No, no, no. I don't think I don't think he's done

### **00:37:01**

**Geoff Horowitz:** Okay. Uh I just wanted to throw that out there.

**Hemanth Sarabu:** that.

**Geoff Horowitz:** Keep having the conversation. I'll review the recording later. Uh thanks guys. Bye.

**Hemanth Sarabu:** Yeah.

**Ratul Shashank:** Yeah. So uh the question was just regarding the path like is there because as far as I've seen we can't trust these models like GPT and nano banana they we don't have much control some of objects they look different and some they don't you can only control using the prompt and image feed data so that was my

**Hemanth Sarabu:** Yeah,

**Ratul Shashank:** question.

**Hemanth Sarabu:** show you something that I prototyped yesterday. Showed it to Prat. Um, it is a little different than what you're looking at.

**Ratul Shashank:** Yeah.

**Hemanth Sarabu:** So I have like uh three tools. So the first tool is actually a copy paste tool for objects. Now I don't know if this is if this is useful or not. I don't know if this is better than existing copy paste tools we already use or not.

### **00:38:17** {#00:38:17}

**Hemanth Sarabu:** I'm not sure. Uh this was just something

**Ratul Shashank:** Uh just to interrupt just sorry to interrupt. This is Bobby P based on pixel crop or raw data.

**Hemanth Sarabu:** Pixel crop.

**Ratul Shashank:** Okay.

**Hemanth Sarabu:** So, but the way this works is a little different. Um, you can actually do things to the image where you try to decompose it into multiple components. uh there. So these are called decomposition techniques and what this uses is it it decomposes the image into structure speckle and

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** uh one more thing which I'm forgetting and then you basically try and recombine it while you copy paste the object. So here it's this is the original image the object is here and this is where we will be placing the the object in the new image and this is a new image. So this is naive copy paste and then this is this is the layered

**Ratul Shashank:** M

**Hemanth Sarabu:** composite. So it'll put it here and then it'll apply it'll basically do some normalization and it'll apply the speckle etc etc. So it looks more like it's part of this image.

### **00:39:41**

**Hemanth Sarabu:** Um, so this is something I've been playing with. Obviously, you can you can also rotate the image and rotate the image. You can also like uh place the image in a specific location, right? So there's some control, but this is mainly a prototype. I was seeing if this could work. Uh, I don't know the answer for whether this is useful. The only way to find out is for you guys to tell me or we train train test and the results tell us. So this is one idea I showed it to Pratyaksh.

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** I'm not I'm not uh I'm not sure if he determined it to be useful, but uh this is one

**Ratul Shashank:** Yeah. I mean this is something that I like this is something close to what I was doing

**Hemanth Sarabu:** um

**Ratul Shashank:** using amplitude like uh I was just uh just in place of pixel crop I was taking the row amplitude and uh normalizing before like the pixelization of the image so

**Hemanth Sarabu:** Yes. So this this I actually started doing this after your idea.

### **00:40:50** {#00:40:50}

**Ratul Shashank:** that.

**Hemanth Sarabu:** After you said your idea, I was reminded of this algorithm called EMD,

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** which basically can decompose. Um and then yeah,

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** I tried a few other decomposition techniques to see if any of them will actually generate anything interesting. Um, but yes, this is actually an extension of what you were looking at.

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** So, I don't I don't know if you want the code to this,

**Ratul Shashank:** Uh

**Hemanth Sarabu:** but I can share it with you if uh if you want to play with uh with it.

**Ratul Shashank:** I mean it would be useful. It could be. I mean uh if I were to share you uh share with you my reasoning like uh what

**Hemanth Sarabu:** Mhm.

**Ratul Shashank:** I wanted uh what I wanted to create uh in terms of synthe data was uh I want in my head I want the object to be as close as the original with some change which which a two parameters tuned like height or uh length or combining the two objects and

### **00:42:13**

**Hemanth Sarabu:** Okay,

**Ratul Shashank:** trying and looking at sorry and trying to find a

**Hemanth Sarabu:** you're you're breaking up.

**Ratul Shashank:** new object. So these were what I had in mind. Uh and the reason because I thought if uh give me a minute. I think this uh is uh is my voice uh fine right now?

**Hemanth Sarabu:** Yeah, I think I think so. Yes.

**Ratul Shashank:** Uh I was I was saying that uh like the reasoning behind that was I wanted to preserve the original objects uh original objects identity as much as possible and trying to simulate what it would be like if that original object was in the uh seabed with a few changes. Uh, is that a good direction for synthetic object

**Hemanth Sarabu:** I think I mean why not? So I I couldn't actually tell you I I think yes I think that is worth trying out.

**Ratul Shashank:** or

**Hemanth Sarabu:** The only way to find out is to do some train val you know collect metrics.

**Ratul Shashank:** PSTR like train on synthetic and test on

### **00:43:41**

**Hemanth Sarabu:** some something like that. Yes, some uh something like something something like that. Yes,

**Ratul Shashank:** Yeah.

**Hemanth Sarabu:** we don't actually I don't think we can tell if uh maybe Sachin has looked at a lot of data and he can tell but I don't know how to tell if an object is a good if an example that is generated is a good example or not. I don't know how to tell. We can ask the customer maybe actually give me uh

**Ratul Shashank:** What?

**Hemanth Sarabu:** tell me Sachin where what background should I put to see if uh we can create a plausible looking example

**Ratul Shashank:** Uh I think VW and DR in my opinion VW and DRN are better options because ENTX has entx a part of entx like every image is created by BRB 006\. ICS. are very bad and POE there are too many chains

**Hemanth Sarabu:** Okay.

**Ratul Shashank:** like uh artifacts it's it would be a

**Hemanth Sarabu:** Okay. Okay. Maybe can you play with this if you think it's useful?

### **00:44:45** {#00:44:45}

**Ratul Shashank:** mess.

**Hemanth Sarabu:** If you don't think it's useful, no problem. But it's an 854 8504 on Wall-E.

**Ratul Shashank:** Okay, I will I will

**Hemanth Sarabu:** Yeah. And then the you were asking are there other methods? This is another method I played with. I do have to I do have to go but um this is another method I played with. The uh I can share the code with you.

**Ratul Shashank:** Okay.

**Hemanth Sarabu:** And this is a gener this is a generative method. It's not a diffusion based method. It's a generative method. It generates sand ripples. Um,

**Ratul Shashank:** and

**Hemanth Sarabu:** it uses VGG statistics to basically create sand ripples from

**Ratul Shashank:** then

**Hemanth Sarabu:** noise.

**Ratul Shashank:** and then collapse those individual

**Hemanth Sarabu:** You can yes you can do that. I don't have a good implementation of that last part but uh yes you can do that.

**Ratul Shashank:** tiles.

**Hemanth Sarabu:** And then there's this style remix which is uh inspired again it's similar to the previous idea.

### **00:45:44** {#00:45:44}

**Hemanth Sarabu:** It is inspired by style transfer type uh implementations. So you take a a content image and a style image and then it'll put those two together. And yeah, again you can like you can choose which data set randomly you want to put one or the other. The problem is I actually don't know which is which are good examples, right? So I will it's unclear to me but I was just exploring some ideas for

**Ratul Shashank:** Yeah, I will I will also talk to practice regarding this.

**Hemanth Sarabu:** fund

**Ratul Shashank:** Uh uh like I I al when I was looking for new uh new waves, the agent also recommended FFT. Is that

**Hemanth Sarabu:** I've already tried. I don't think you'll have anything meaningful come out of it.

**Ratul Shashank:** okay? Okay.

**Hemanth Sarabu:** Yeah.

**Ratul Shashank:** Okay.

**Hemanth Sarabu:** Um but you you can still explore. This one is on 8502\. So you look at 8502 and 8504\. And I shared the code. Where is the code? Uh ah I shared the code here. I'm just tagging you. Okay. In the in the in the threads where we discussed this

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** Okay. Uh, sorry guys. I do have to drop. Um,

**Ratul Shashank:** Okay. Okay. I will I will I will discuss this and let you know in the next

**Hemanth Sarabu:** okay.

**Ratul Shashank:** meeting.

**Hemanth Sarabu:** Okay, great. Thanks. It will keep us posted.

**Ratul Shashank:** Okay.

**Hemanth Sarabu:** So, 8502 and 8504 in Wally. And I I added to to the thread where proction and I discuss some stuff and the uh the code path is also there.

**Ratul Shashank:** Okay. Yeah, I I I am looking at that.

**Hemanth Sarabu:** All right. Thank you.

**Ratul Shashank:** Okay. Thank you.

**Hemanth Sarabu:** Thanks guys.

**Ratul Shashank:** Bye-bye.

### **Transcription ended after 00:48:05**

*This editable transcript was computer generated and might contain errors. People can also change the text after it was created.*