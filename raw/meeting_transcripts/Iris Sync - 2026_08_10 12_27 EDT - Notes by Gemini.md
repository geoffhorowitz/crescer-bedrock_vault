# **📝 Notes**

Aug 10, 2026

## **Iris Sync**

Invited [Sachin Pandey](mailto:sachin@crescer.ai) [Pratyaksh Singh](mailto:pratyaksh@crescer.ai) [Hemanth Sarabu](mailto:hemanth@crescer.ai) [Geoff Horowitz](mailto:geoff@crescer.ai) [Siddharth Soni](mailto:siddharth@crescer.ai) [Ratul Shashank](mailto:ratul@crescer.ai)

Attachments [Iris Sync](https://calendar.google.com/calendar/event?eid=NnNzMHVxNzk3MmJqZGVwNXFoN2J1Mjd1OTdfMjAyNjA4MTBUMTYzMDAwWiBnZW9mZkBjcmVzY2VyLmFp)

Meeting records [Transcript](https://docs.google.com/document/d/1q4esv6dDmgP5hPGjw8-8JENvmrYe6iejhC0AOzpEYBA/edit?usp=drive_web&tab=t.5f738xmuqmte) [Recording](https://drive.google.com/file/d/1ThlJqsaSqhVF8GaITpVkU9E1zJGFF4DQ/view?usp=drive_web) 

### **Summary**

Meeting focused on model selection for Milestone 2 and optimizing synthetic data generation parameters via automated strategies.

**Milestone 2 Model Selection**  
The team decided to adopt Version 4 model augmentation with cut and paste as the final model configuration. Precision remains a concern that will be addressed through post processing analysis.

**Synthetic Data Generation Strategy**  
Members agreed to move from manual tuning to automated evolutionary strategies for parameter optimization. The team set a 24 hour deadline to validate synthetic sample viability.

**Procedural Pipeline and Documentation**  
Participants established new hyperparameter ranges for blend masks and shape generation to enhance output quality. The team confirmed active training runs and committed to maintaining comprehensive research documentation.

### **Decisions**

## Aligned

* **Milestone 2 final closure plan** The team will proceed with one final iteration of data re-labeling and cleaning to finalize Milestone 2 before transitioning into production status.

* **Inclusion of V4 AUG model** The V4 AUG model with cut and paste will be added to the training stack as the final model for Milestone 2\.

We've **updated the Decisions section** using your feedback.

Let us know what you think: [Helpful](https://google.qualtrics.com/jfe/form/SV_5bXzKQfylMIhSXc?isHelpful=True&entryPoint=decisions&confid=a58-cw-Yt44_vIbR1w_dDxIUOBEBMgUIigIgABgECA&isGoogler=False) or [Not Helpful](https://google.qualtrics.com/jfe/form/SV_5bXzKQfylMIhSXc?isHelpful=False&entryPoint=decisions&confid=a58-cw-Yt44_vIbR1w_dDxIUOBEBMgUIigIgABgECA&isGoogler=False)

### **Next steps**

- [ ] \[Sachin Pandey\] Update Meeting Notes: Update the meeting notes with the change log and results report links.

- [ ] \[Sachin Pandey\] Document Model Details: Add documentation for model configuration details for all evaluated models into the report.

- [ ] \[Sachin Pandey\] Review Unlabeled Contacts: Review all model predictions to identify and log potentially unlabeled contacts.

- [ ] \[Sachin Pandey\] Share Result Tables: Share four result tables, covering both processed and unprocessed results, on the project Slack.

- [ ] \[Sachin Pandey\] Train V4 Model: Train the V4 augmentation model including the cut and paste configuration.

- [ ] \[Ratul Shashank, Pratyaksh Singh\] Discuss Tuning Approach: Discuss the approach for testing and tuning parameters for synthetic sample generation.

- [ ] \[Ratul Shashank\] Share Synthetic Updates: Share the status updates on synthetic sample progress on the project Slack.

- [ ] \[Ratul Shashank\] Share Hyperparameters: Provide the hyperparameters for synthetic data training to enable the setup of the training pipeline.

- [ ] \[Pratyaksh Singh\] Implement Optimization Loop: Implement an optimization loop for synthetic data generation using evolutionary strategies.

- [ ] \[Pratyaksh Singh\] Iterate Model: Run 1 or 2 iterations of the model. Finalize this task by Wednesday.

- [ ] \[Hemanth Sarabu\] Test Suggestion: Experiment with the proposed method when time allows. Communicate the findings to the team.

- [ ] \[Sachin Pandey\] Share Tables: Upload the tables to the group chat. Perform this action as soon as possible.

- [ ] \[Geoff Horowitz\] Retrieve Models: Obtain the Bedrock models within the current week.

- [ ] \[Geoff Horowitz\] Finish Testing: Complete the Jetson testing. Lead this effort with the necessary support.

- [ ] \[The group\] Report Findings: Document detailed research and improvement progress in a report. Upload the final document to Google.

### **Details**

* **Meeting Documentation Standards**: Geoff Horowitz requested that the team maintain a consistent format for the running notes, ensuring they include clear summaries of changes, results, and links to relevant reports. Sachin Pandey agreed to update the notes with the necessary model details following the meeting ([00:02:59](#00:02:59)).

* **Milestone 2 Objectives**: The team centered their focus on three open items required to finalize Milestone 2: deciding on the final model, assessing the sensitivity of each model to the training set through cross-validation, and analyzing the performance impact of including cut-and-paste in the training set ([00:07:05](#00:07:05)).

* **Model Performance Analysis**: Sachin Pandey reported that the V4 model with image augmentation is currently the highest-performing option, particularly in terms of recall. Precision is currently lower but is expected to be improved through post-processing, and the team can verify rankings by sorting the results by F1 score in the provided report ([00:08:27](#00:08:27)).

* **Clarification of Model Configurations**: Pratyaksh Singh requested clarification regarding the different model versions, and the team confirmed that V3 includes copy-paste augmentation, while V4 relies on image augmentation filters without copy-paste ([00:12:11](#00:12:11)). Geoff Horowitz later instructed the team to add V4 augmentation with cut-and-paste to the testing stack as the final model for this round ([00:30:58](#00:30:58)).

* **False Positive and Data Quality Concerns**: During a review of false positive results, Pratyaksh Singh noted that many objects flagged by the model resemble UXOs but lack labels, raising concerns that the dataset might have missing information ([00:16:51](#00:16:51)). Hemanth Sarabu suggested that relying on a high-recall model is an acceptable strategy to identify these unlabeled contacts, with the expectation that the labeling error will diminish with successive iterations ([00:22:45](#00:22:45)).

* **Moving to Shipping Mode**: Hemanth Sarabu advised the team to transition from research mode to shipping mode, concluding that while they can afford one final, rapid iteration of re-labeling to improve precision, they should prioritize closing the milestone ([00:26:02](#00:26:02)) ([00:30:58](#00:30:58)).

* **Model Validation Next Steps**: To confirm the model is ready, Hemanth Sarabu requested that Sachin Pandey share two sets of tables on Slack—one showing unprocessed results and another showing the results after applying post-processing filters—to allow the group to verify if the precision can be improved without sacrificing recall ([00:28:34](#00:28:34)).

* **Synthetic Data Development Status**: Ratul Shashank provided an update on fine-tuning synthetic samples, noting that noise and contrast parameters are being addressed, but shape parameters remain an open item ([00:32:09](#00:32:09)). Pratyaksh Singh critiqued the current drop percentage of 0.1, arguing it prevents shape variation, and requested further discussion on testing and tuning procedures ([00:35:46](#00:35:46)).

* **Synthetic Shape Optimization Methods**: Ratul Shashank explained that the current approach for shape generation involves analyzing the distance of the edge from the center of the object ([00:37:00](#00:37:00)) ([00:41:52](#00:41:52)). Hemanth Sarabu emphasized that the team should be more aggressive, aiming to confirm the viability of these synthetic samples within 24 hours ([00:43:21](#00:43:21)).

* **Procedural Generation Architecture**: Pratyaksh Singh described the current pipeline, where backgrounds are handled by a diffusion model and objects are procedurally generated on top ([00:47:57](#00:47:57)) ([00:50:26](#00:50:26)). Pratyaksh Singh also noted a dependency on Ratul Shashank to provide hyperparameters for the synthetic data training ([00:44:39](#00:44:39)).

* **Optimization Strategy for Synthetic Data**: Hemanth Sarabu proposed moving away from manual parameter tuning and instead utilizing structural or color-based loss functions combined with sampling-based evolutionary strategies, such as the cross entropy method, to automate the search for optimal parameters ([00:52:59](#00:52:59)) ([00:54:53](#00:54:53)). Pratyaksh Singh agreed to implement this optimization approach to see if it improves the synthetic generation process ([00:53:55](#00:53:55)).

* **Projected Timeline and Closing**: Geoff Horowitz reiterated the goal of finalizing the model selection and wrapping up Jetson testing, while Sachin Pandey confirmed that the requested performance tables would be shared on Slack as soon as possible ([00:57:57](#00:57:57)).

* **Data Volume Assessment**: Sachin Pandey stated that there are currently 57 files available, with an objective to reach a total of 600 files ([01:00:50](#heading=h.sexdpuk0kbxw)).

* **Image Generation and Functionality**: Ratul Shashank and Pratyaksh Singh discussed the configuration of image generation parameters, including establishing a default drop percentage of 0.9 and managing blur sizes. Pratyaksh Singh noted the importance of utilizing notebooks and specific functions to control blend mask intensity for the generation of shapes, such as circles and water drops ([01:00:50](#heading=h.sexdpuk0kbxw)).

* **Hyperparameter Range Optimization**: Pratyaksh Singh and Ratul Shashank reviewed necessary parameters for mask and shape generation, with Pratyaksh Singh proposing the testing of drop percentages at 0.3, 0.5, 0.6, 0.7, 0.8, and 0.9. The participants agreed to use a random uniform drop percentage between 0.7 and 0.9 for background image processing, along with specific blend mask multiply factors ([01:07:16](#heading=h.iuphxig0qexz)).

* **Image Synthesis and Implementation Timeline**: The participants discussed refining parameters for highlight and shadow effects within the blend mask settings to improve image outcomes. Pratyaksh Singh emphasized that these modifications are required to be completed within a 24-hour window ([01:12:43](#heading=h.uc2xo7qc9x9n)).

* **Research Documentation and Training Progress**: Pratyaksh Singh requested the creation of a detailed report to document the research and hyperparameter tuning. Sachin Pandey prompted for an update on training, and Pratyaksh Singh confirmed that training is currently running, with the team actively comparing images within the notebooks ([01:12:43](#heading=h.uc2xo7qc9x9n)).

* **Meeting Conclusion**: The meeting concluded following technical connectivity issues experienced by the participants ([01:12:43](#heading=h.uc2xo7qc9x9n)).

*You should review Gemini's notes to make sure they're accurate. [Get tips and learn how Gemini takes notes](https://support.google.com/meet/answer/14754931)*

*How is the quality of **these specific notes?** [Take a short survey](https://google.qualtrics.com/jfe/form/SV_5bXzKQfylMIhSXc?confid=a58-cw-Yt44_vIbR1w_dDxIUOBEBMgUIigIgABgECA&detailLevel=standard&hasImages=False&entryPoint=footerMain&isGoogler=False) to let us know your feedback, including how helpful the notes were for your needs.*

# **📖 Transcript**

Aug 10, 2026

## **Iris Sync \- Transcript**

### **00:02:59** {#00:02:59}

**Geoff Horowitz:** here at

**Ratul Shashank:** Hey

**Sachin Pandey:** Hi

**Geoff Horowitz:** all.

**Sachin Pandey:** Geoff.

**Hemanth Sarabu:** Hey guys,

**Geoff Horowitz:** I'm you're a little soft,

**Sachin Pandey:** I

**Ratul Shashank:** AM. Amen.

**Geoff Horowitz:** but uh can hear you.

**Hemanth Sarabu:** um I think I hope it will fix itself.

**Geoff Horowitz:** I like how you um well, you and I can chat about this later, but uh you probably know what I'm referencing. I like how you um you have streak installed uh as a default here.

**Hemanth Sarabu:** Oh, is it

**Geoff Horowitz:** I thought that was a very he thing to do.

**Hemanth Sarabu:** totally? Okay, that's pretty

**Geoff Horowitz:** All right,

**Hemanth Sarabu:** join us.

**Geoff Horowitz:** fellas. Sa thanks for adding this in to the running notes. Um, but we had like a consistent format here, right? So basically like what changed? Um here we go. What changed? What were the results? Link to the report. Right.

**Sachin Pandey:** Yeah, because um yeah, I will add it after the meeting.

**Geoff Horowitz:** Okay.

### **00:05:57**

**Sachin Pandey:** In short like we want to First we decide on which model to go with and then I will add those model

**Geoff Horowitz:** First we decide which model we want to go with.

**Sachin Pandey:** details.

**Geoff Horowitz:** Yeah. But this is also a summary of your results, right? Which is okay. So you know what changed was uh basically we stratified the data, right?

**Sachin Pandey:** Yes.

**Geoff Horowitz:** We we created you know created folds whatever we stratified the data and then you ran the folds on I mean you you had you had written this briefly like what each of these what's model one you know

**Sachin Pandey:** Yeah. Yeah. Uh yeah,

**Geoff Horowitz:** what's first circles so like it doesn't need to

**Sachin Pandey:** I I will add it. What

**Geoff Horowitz:** be I mean again look at these others right it doesn't need to be crazy just like a little so we can glance at it

**Sachin Pandey:** the?

**Geoff Horowitz:** and see what's going

**Sachin Pandey:** Yeah, I already have noted it somewhere.

**Geoff Horowitz:** Um,

**Sachin Pandey:** I will just add it.

### **00:07:05** {#00:07:05}

**Geoff Horowitz:** all right. Thank you. Uh, so I guess Sachin, do you want to start just talk us through?

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** Actually,

**Sachin Pandey:** So in short,

**Geoff Horowitz:** let me Sachin,

**Sachin Pandey:** yes.

**Geoff Horowitz:** give me one second. Let me let me center us all here. So we're we're really trying to wrap up milestone 2, right? So the the open items are um which model do we want to use, right? How sensitive are each of these models to the underlying training set? Um for for all of this, this is why we we're looking at this um cross validation That's number one. Additional number two is uh seeing the results on the new data set that they provided, the Treasure Island data set. And um number three that was an open item was uh including cut and paste in a training set and seeing how that um I mean we expect it to improve results but you know I'm I'm going to say that more broadly seeing how that uh impacts um performance.

### **00:08:27** {#00:08:27}

**Geoff Horowitz:** So, those are the three things that are still open that we need in order to finish up milestone 2\. Okay. Are we all centered there? Great. Okay. Sachin, all

**Sachin Pandey:** Yeah. So we finished training all the models.

**Geoff Horowitz:** you

**Sachin Pandey:** Uh we trained around 20 models for each fold. And from what I'm getting the B4 model with argumentation is doing the best. It has in general it has the highest uh recall and for

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** precision we can like improve it by adding some filters but like precisions can be improved in post-processing so we are targeting on higher recalls in general and next best model will be uh wait a second some model from M1 and like the base the base model. So if you go to the full report there is uh like a table for all 20 models. You can just sort them based on F1 score and you can get the list out there. So like for this we can so we in overview like V4 argumentation is doing the best.

### **00:09:57**

**Sachin Pandey:** So we can train uh we can train this on a whole data set and in the meantime I am running more tests to see if we can improve it more but uh don't have any results from those. Okay.

**Geoff Horowitz:** Um,

**Sachin Pandey:** Okay. Any questions? Yeah, if you click on the UXO F1 score, it will sort it all.

**Hemanth Sarabu:** So this um Okay, let's um let's go back. Can Can we go back to that table real quick? Yeah.

**Geoff Horowitz:** the You mean this table?

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** Make it bigger. Give me a second.

**Hemanth Sarabu:** So we actually don't care which f is the best. We generally care which version is the best. Right.

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** Okay. What is your what is the conclusion?

**Sachin Pandey:** Uh I think V4 with argumentation is the best because in general it has the highest recall and precision precision is something which we can like fix or improve in post-processing.

**Hemanth Sarabu:** Okay. Um so let's I don't I know that we can leave this probably for discussion here but what are the next steps given this information?

### **00:12:11** {#00:12:11}

**Sachin Pandey:** Uh like the idea was to train once we got which uh which is working the best idea was to train the whole train it on the whole data set.

**Hemanth Sarabu:** Okay. Okay. And then and that's it. Right. After that, we will just fine tune that model or whatever.

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** Okay. Okay.

**Pratyaksh Singh:** And what is V4? Hey, sorry I forgot what was V4.

**Hemanth Sarabu:** So,

**Pratyaksh Singh:** Is this with the copy paste augmentation or was that

**Sachin Pandey:** V3 is the copy paste commentation.

**Pratyaksh Singh:** V3

**Sachin Pandey:** We uh V4 doesn't have V4 is the image argumentation like what kind of filters are applied on the like changes on the images. Uh it doesn't have any copy paste. Just if you scroll up there is the like rough summary of each config. So yeah copy paste for V4 augmentation is done.

**Pratyaksh Singh:** Okay. And for B3, I think the recall is pretty good, right? for all the fold is very low.

### **00:13:30**

**Sachin Pandey:** Yes.

**Pratyaksh Singh:** Any predictions from it if possible? How does it

**Sachin Pandey:** Yeah.

**Pratyaksh Singh:** look

**Sachin Pandey:** Uh if uh in the end there are like some samples of the

**Hemanth Sarabu:** Oops.

**Sachin Pandey:** predictions. Let's go

**Geoff Horowitz:** Explore model one.

**Sachin Pandey:** more.

**Geoff Horowitz:** I don't want model one. What? What are we seeing here? Oh, wait. Model 3\. Wait, this is confusing. Model three.

**Sachin Pandey:** Wait.

**Geoff Horowitz:** We want a model two. Forgot which one's which already.

**Sachin Pandey:** M2 is the

**Geoff Horowitz:** B3 is model two.

**Sachin Pandey:** B31.

**Geoff Horowitz:** Okay. So, model two. This was the one with copy and paste.

**Sachin Pandey:** Yes. If you scroll more there will be more uh like other options as well. It will be

**Geoff Horowitz:** two and these are different folds.

**Pratyaksh Singh:** radio means that it was missed. Was it missed? What does red

**Geoff Horowitz:** Yeah. What is red

**Pratyaksh Singh:** mean?

**Geoff Horowitz:** green?

### **00:15:43**

**Hemanth Sarabu:** I think it's just Oh, never

**Geoff Horowitz:** Cuz in this case, they're both green.

**Hemanth Sarabu:** mind.

**Geoff Horowitz:** But in this case, one's green and one's red.

**Sachin Pandey:** Uh, I need to check that was for I guess it was for

**Geoff Horowitz:** I yeah, I can see some red over here.

**Sachin Pandey:** overlap.

**Geoff Horowitz:** So, I'm I'm guessing that this actually means that it missed the prediction. But then what is this here? I don't know what that is because you can

**Pratyaksh Singh:** But even if it missed it

**Sachin Pandey:** Oh,

**Geoff Horowitz:** see what did you say,

**Sachin Pandey:** red is a black.

**Geoff Horowitz:** Sin?

**Sachin Pandey:** Ay black. Red is a black. Uh the object which is similar to ux show

**Geoff Horowitz:** Oh, so green is UXO,

**Sachin Pandey:** and that is a y black.

**Geoff Horowitz:** red is AOI.

**Sachin Pandey:** So model is predicting it as a

**Geoff Horowitz:** So in this,

**Sachin Pandey:** black.

**Geoff Horowitz:** so in this case where we have red and green, it means the model is predicting it both as AOI black and UXO, which is okay for us.

### **00:16:51** {#00:16:51}

**Geoff Horowitz:** And in this case,

**Sachin Pandey:** Yes.

**Geoff Horowitz:** it's only predicting AOI black, not UXOs.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** I see.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** But in all of these cases, it actually is a UXO because they're green.

**Sachin Pandey:** Yes. down to this

**Geoff Horowitz:** I see. Sachin, were you able to

**Sachin Pandey:** ang

**Geoff Horowitz:** generate?

**Pratyaksh Singh:** I think we going to say the same

**Geoff Horowitz:** Oh, well, were you able to generate that table that He asked you for last time in the it's in the chat?

**Sachin Pandey:** uh yeah I I don't have the table but

**Geoff Horowitz:** He put an image of it in the

**Sachin Pandey:** like I was working on this uh you can get a rough idea like I was what uh you can like visit this URL. It has all the false poet predictions and I was like categorizing it with if it is like like UXO which actual UXO it is matching with. So we have like some actual ground tooth which we can say like this was you which you have marked And this object is matching similar to this.

### **00:18:03**

**Sachin Pandey:** If you just uh in turn turn off TP and FN and press G.

**Geoff Horowitz:** Turn off. Turn off E. S E.

**Sachin Pandey:** Just click just click and positive first one.

**Geoff Horowitz:** Oh,

**Sachin Pandey:** Yes.

**Geoff Horowitz:** TP and press G like on my

**Sachin Pandey:** And press G. Yes. So these are all the false pointing objects.

**Geoff Horowitz:** keyboard.

**Sachin Pandey:** And most of it is like gxo and if you press uh f h I don't have

**Hemanth Sarabu:** What is the what is the summary before you show us?

**Sachin Pandey:** the table I was working on it but it will take some time to make the table in general

**Hemanth Sarabu:** It's okay. What is the

**Sachin Pandey:** like in general the our like hypothesis where is

**Hemanth Sarabu:** worm?

**Sachin Pandey:** correct because if you see just a gallery most of the objects looks like UXO. So those will be like already in the like those UX like UXO category.

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** We just need to work on this to get the actual count.

**Hemanth Sarabu:** Um,

### **00:19:09**

**Sachin Pandey:** But in general just from the view you can see like most of our looks like

**Hemanth Sarabu:** okay.

**Sachin Pandey:** UXO.

**Hemanth Sarabu:** This is for V4G. This is for

**Geoff Horowitz:** So,

**Sachin Pandey:** Yeah,

**Hemanth Sarabu:** V4.

**Sachin Pandey:** this is for V4 augmentation. These are all the false positives from B4 admination from all

**Hemanth Sarabu:** I see.

**Sachin Pandey:** folds.

**Hemanth Sarabu:** Okay. Um so such

**Geoff Horowitz:** two

**Pratyaksh Singh:** Hey,

**Hemanth Sarabu:** an

**Pratyaksh Singh:** now I was just saying that uh we asked the labelers to basically label everything, right? Uh if they if it's not UXO, it went to AOI small black or AI packs and all those things, right? I'm wondering if they mislabeling those or are they in some other class which we

**Sachin Pandey:** Yes.

**Pratyaksh Singh:** dropped? What's what's the thing there?

**Sachin Pandey:** There will be high chance that they have missed it because the classes which we have dropped are generally like big

**Pratyaksh Singh:** Because

**Sachin Pandey:** classes like sand patch sand ripples and even like they can't mclassify it as those classes.

### **00:20:27**

**Pratyaksh Singh:** So guys, like what do we need to do then? Like I mean

**Hemanth Sarabu:** for one.

**Pratyaksh Singh:** we can't trust the metrics then, right? Like I mean what Sachin is looking at is looking at all the false positive and he's finding out that they are correct. But that doesn't mean that there are some that the model missed and then we aren't even looking at it.

**Hemanth Sarabu:** They're not

**Pratyaksh Singh:** Like this should have been you know I was

**Sachin Pandey:** Five.

**Hemanth Sarabu:** even

**Pratyaksh Singh:** saying like this should have been labeled during the labeling process right where all of these should have been if not UXOS

**Sachin Pandey:** Uhoh.

**Pratyaksh Singh:** they should have been in AOI small black which was which is basically your UXO like class right and if it's not labeled

**Hemanth Sarabu:** project.

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** Um I sorry I'm I I want to move on to the generative stuff you're working on to or you and your are working on this. So I I want to push through this conversation a little bit. Let me see if I understand your concern.

### **00:21:45**

**Hemanth Sarabu:** Right. Your concern is we're seeing these instances where the model is picking up objects. We're looking at it and saying,

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** "Yeah, they look like they look like uh UXO like objects, but they haven't been labeled.

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** There's no mask at all." So, is there a problem with the data set?

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** That is your concern.

**Pratyaksh Singh:** Yeah. And I mean like if that is the case,

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** how do we even know that the V2 model or M2 model is performing poorly than the other model? Because that model also has high recall and it is only bad in precision.

**Hemanth Sarabu:** That's true. Um, that is true. So, here's here's what I'd like us to do. Um, okay. Uh, I mean, we we don't have an M2, right? It's just we only care about the row, not the column. Is that right? Do you mean me too?

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** Okay.

### **00:22:45** {#00:22:45}

**Hemanth Sarabu:** Okay. Um how I think okay I'm just going to say what we should do either Sachin or the labelers need to go through all the predictions and see if the model is picking up unlabelled contacts. Hello.

**Pratyaksh Singh:** Hello.

**Hemanth Sarabu:** Hey, I don't know if you guys heard me.

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** It was a pretty

**Pratyaksh Singh:** Yeah.

**Sachin Pandey:** Let's see.

**Pratyaksh Singh:** Yeah, I get your point.

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** But the problem is that there are some there may be some contacts which the model also missed and then which will again go into the data set without being marked.

**Hemanth Sarabu:** You're saying that? Okay. I don't think I don't think that the question is of what is the labeling error? Is the labeling error closer to 50% 10% 5% 2% 1%? Right? My guess is that it's pretty low. It's not not 50%, it's not maybe not even 10%, maybe five or 2%. Does that make sense? Now

**Pratyaksh Singh:** Okay.

**Hemanth Sarabu:** intuitively if we are generally upporting a high recall model the high recall model is going to pick up both true contacts and false contacts and unwanted contacts.

### **00:24:45**

**Hemanth Sarabu:** Right? So I think using that proof mine for unlabeled contacts is okay. There will be some bias there, but I think that's okay. And we I'm thinking that every iteration of this we go through and I'm guessing we went through one or two iterations of this already, right? Maybe with the model, maybe without the model, whatever. We went looking for contacts, right? I'm guessing that the labeling error will come down to a very small number.

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** Uh does that make sense?

**Pratyaksh Singh:** I I get what I mean. Yeah, it makes sense.

**Hemanth Sarabu:** So do do you have any qualms with this approach of Sounds

**Pratyaksh Singh:** No,

**Hemanth Sarabu:** like you're not Yeah.

**Pratyaksh Singh:** I think it's fine. I think it's fine like u I agree with the fact that after one or two iteration or three iteration we will have clean data, right? Because progressively we will have our model have high recall, right? Because as you keep training on the on better data set, it will start to predict more

### **00:26:02** {#00:26:02}

**Hemanth Sarabu:** right? I mean, we're already at I think a high recall. We've been biasing this so heavily towards high recall.

**Pratyaksh Singh:** hopefully.

**Hemanth Sarabu:** My guess would be that recall won't change, precision would change, precision would improve slightly. Okay, the jump in precision would be correlated with the labeling error that got fixed. Right? Follow follow what I'm saying?

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** Because all those things that were incorrectly unlabelled,

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** basically unlabelled are now um what Okay. Um, so does that make sense?

**Pratyaksh Singh:** There it

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** Okay. I guys,

**Pratyaksh Singh:** is.

**Hemanth Sarabu:** I think we're getting to a point where we should close this milestone out. So we we should start we should start um uh kind of packaging things. What do I mean by that? I think we we need to start going from research mode to ship ship mode. Um we can afford maybe one more iteration of re labeling and it has to be done really quickly, but that's probably all we can afford right now.

### **00:27:31**

**Hemanth Sarabu:** You guys with me?

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** Now,

**Sachin Pandey:** Right.

**Hemanth Sarabu:** I want to talk about something. Oh, we're we're running out of time. I want to talk about a couple things.

**Sachin Pandey:** I wanted to add one more thing.

**Hemanth Sarabu:** Yes.

**Sachin Pandey:** So at least for UXO I tried like capturing all of them by like first creating the mask of all the like all the files which have which were present on those areas and like marking them manually if labelers have missed it. So we there's chance we have mixed missed as like a small black but for UXO I I think we we have captured it all.

**Hemanth Sarabu:** Okay. Um I I will Okay. I think you pr such can you guys have a follow-up call basically discussing this I think it's important I don't want to dismiss it I think these details are

**Sachin Pandey:** Okay.

**Hemanth Sarabu:** important um but I want to discuss a little more high level okay I'm going to I'm going to consider I'm going to like I'm going to

### **00:28:34** {#00:28:34}

**Sachin Pandey:** Okay.

**Hemanth Sarabu:** basically say you guys got this right you'll you'll figure out how to deal with this but I'm saying let's not aim for perfection uh we need to s\*\*\*. Okay. So, what I sin, you said something that is pretty important. You said we have high recoil and we'll deal with precision by post-processing, right? We need to test that hypothesis. Um,

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** can we actually is are we actually able to postprocess using size or confidence or whatever other features without losing recall but improving precision?

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** I don't

**Sachin Pandey:** We we have the results from like last V4 training where the filtering were helpful a

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** lot.

**Hemanth Sarabu:** Okay. Do you have numbers?

**Sachin Pandey:** Yes, it was in the V4

**Hemanth Sarabu:** Okay. Great. So,

**Sachin Pandey:** report.

**Hemanth Sarabu:** let's um once we're done with this call, can you share those tables that we discussed in the last call?

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** Okay. And then so you can share those tables in you can share two versions of those two tables.

### **00:29:50**

**Hemanth Sarabu:** So four tables in total. One is unpush processed results. which I believe you're already working on, right?

**Sachin Pandey:** Yeah. And then after filtering.

**Hemanth Sarabu:** Exactly.

**Sachin Pandey:** Okay.

**Hemanth Sarabu:** You be able to share those two.

**Sachin Pandey:** Share my screen.

**Hemanth Sarabu:** No, no. Would you be able to share those two tables after this call?

**Sachin Pandey:** Yes. Yes.

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** Share them on Slack section.

**Hemanth Sarabu:** Yes.

**Sachin Pandey:** Okay.

**Hemanth Sarabu:** on Slack just with the group, you know, on the in the project Slack. And so that will tell us whether we're ready hopefully.

**Sachin Pandey:** Okay.

**Hemanth Sarabu:** So protection concern is legitimate that there's maybe we're missing a lot of labels potentially or significant. My guess is that uh it's pretty small and it'll only improve precision, which is a good place to be. Um, so I'm planning for this as if this is going to be close to the last iteration for this milestone. Do you guys agree? Great. Okay.

### **00:30:58** {#00:30:58}

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** So Sachin, once you post those tables, it'll hopefully confirm that we're close to the end and then we can do one more round of uh this reabeling or cleaning process and then we should be we should be we should kind of package everything up to deliver this milestone.

**Sachin Pandey:** Okay.

**Hemanth Sarabu:** Okay. Yeah. Okay. Everyone's aligned. So I know I took up some time uh but maybe 10 minutes or so let's spend on uh show your your guys' efforts.

**Geoff Horowitz:** Hand I'm really sorry. I I just need one confirmation. Sachin,

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** are we creating a V4 AUG model with cut and base?

**Sachin Pandey:** Uh not now like we haven't trained on

**Pratyaksh Singh:** Set it to train.

**Sachin Pandey:** it.

**Geoff Horowitz:** Okay.

**Pratyaksh Singh:** Set it to train.

**Sachin Pandey:** Okay. And

**Pratyaksh Singh:** Set it to train.

**Geoff Horowitz:** Okay.

**Pratyaksh Singh:** Let's see what happens.

**Geoff Horowitz:** Yeah, I think we should just add it to the stack. I I think that should be the last the last model for round two.

### **00:32:09** {#00:32:09}

**Geoff Horowitz:** He I sorry if I just stepped on your toes there,

**Hemanth Sarabu:** No,

**Geoff Horowitz:** but yeah.

**Hemanth Sarabu:** no, no. That's fine.

**Geoff Horowitz:** Okay.

**Hemanth Sarabu:** I I just I just don't want to be in we don't know what will shift

**Geoff Horowitz:** Yes.

**Hemanth Sarabu:** mode.

**Geoff Horowitz:** Yeah. Um, okay. That's all I had.

**Ratul Shashank:** Okay. So, can I go? I just have a quick update and you can take over.

**Hemanth Sarabu:** Yes.

**Ratul Shashank:** So,

**Hemanth Sarabu:** Okay.

**Ratul Shashank:** just a few updates on my end. Ratak shared the code that he was uh that he he displayed in the last meeting and asked me to finetune for the parameters uh that uh that is undergoing it is not finished. I have this I have uh fine- tuned for the noise levels and uh the contrasts but the shape and other parameters are left and also using that I am also looking at if like considering the shape if other metric can be used. So it is it is all in the product it is not in the production level yet.

### **00:33:41**

**Ratul Shashank:** I am only looking. So that is all the update on money regarding it.

**Hemanth Sarabu:** How's it uh how are the synthetic samples looking right now?

**Ratul Shashank:** I will share my screen.

**Hemanth Sarabu:** Okay.

**Ratul Shashank:** So I this was the port what shared I uh if you look at the row for synthetic tune. So, as I said, the shape is not tuned yet. I was looking at the noise levels and the contrast to to get uh like how it would look if uh tuned. So this this is the uh this is what fat shared and regarding the other like when the other approach that I mentioned like the different uh shape uh

**Hemanth Sarabu:** Hey guys, sorry. Give me one second.

**Ratul Shashank:** example.

**Hemanth Sarabu:** I need to be right back.

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** Can you explain more on it like what is done, what is

**Ratul Shashank:** Yeah. I mean uh I have also shared a short update on this lab. So for this I have uh fine- tuned for uh the blur and noise and drop percentage.

### **00:35:46** {#00:35:46}

**Ratul Shashank:** Uh I have not touched for the other parameters yet. So that is this is still an open item.

**Pratyaksh Singh:** So,

**Ratul Shashank:** This entire finetuning is an

**Hemanth Sarabu:** Okay,

**Ratul Shashank:** Don't

**Pratyaksh Singh:** Ratul uh a few things that I don't like.

**Hemanth Sarabu:** back.

**Pratyaksh Singh:** For example, drop percent the status adopted is 0.1 which I don't think should be used because with 0.1 you would get like real shapes uh very real shape like always circle or always oval the shape won't change.

**Ratul Shashank:** m

**Pratyaksh Singh:** So drop version 0.1 I don't think should be there. Blur K size is just for mixing.

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** So the more that you increase it, it should mix more.

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** But uh drop percentage I think

**Ratul Shashank:** should

**Pratyaksh Singh:** 0.1. Yeah.

**Ratul Shashank:** be.

**Pratyaksh Singh:** Yeah. Let's think up again after this meeting to see uh let's discuss how you are how you are testing it out, how you are tuning these

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** parameters.

**Ratul Shashank:** All right. All right.

### **00:37:00** {#00:37:00}

**Ratul Shashank:** Uh yeah, I mean this is uh still an open item even. So yeah, this needs this needs work. Uh and regarding the other shape that I mentioned, this uh this is using the same approach that you used. Uh I just changed the like I was looking if the shape can if the shape change another metric can be used. So not much of an update in here. The only change is that the shape is derived from the like it first it finds the uh the values of how far the edge of the real object is on the uh on the real object. How far is the edge of the mask and using that is it is making shapes rather than choosing for a few combination of shapes like oval and triangle.

**Hemanth Sarabu:** Hey.

**Ratul Shashank:** Uh,

**Hemanth Sarabu:** Uh, sorry. Really quickly, what is how does it optimize?

**Ratul Shashank:** nothing.

**Hemanth Sarabu:** Can you zoom in again? Zoom in. How does it optimize for um Oh, okay. The bottom the bottom ones are all synthetic.

### **00:38:34**

**Hemanth Sarabu:** The top one I'll do.

**Ratul Shashank:** Yeah.

**Hemanth Sarabu:** Okay. Okay.

**Ratul Shashank:** Yeah.

**Hemanth Sarabu:** So, how does it optimize? How does it what is the loop it uses to improve the objects?

**Ratul Shashank:** Yeah. So it is not it is not improving the objects as of this moment. It is uh like I I I am just testing

**Hemanth Sarabu:** We sent

**Ratul Shashank:** what shapes what kind of shapes like what are the options for shapes that we can use. So Pratak shared he he he took a few examples of oval and triangles and tried to drop a few edges. Uh and what I did was I took uh like on the real object I I I took the percentage of what the boundary is from the center and that is used for the outline of the object. This is only difference in the in the two examples. So yeah, this this is an open item. This is this has this has much work to do. So yeah,

**Pratyaksh Singh:** So,

### **00:40:03**

**Ratul Shashank:** this is

**Pratyaksh Singh:** I like some of these examples that it generates like

**Ratul Shashank:** all.

**Pratyaksh Singh:** the middle leftmost one. That looks pretty good. This one.

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** Yeah, this is pretty good. And I think it is generating some I'm like maybe it is generating some weird shapes which can be useful. I don't understand what you mean by boundary from the center. Dropping the boundary from the

**Ratul Shashank:** Uh I I will I will draw it out.

**Pratyaksh Singh:** center.

**Ratul Shashank:** So Suppose this is the object and what it would do

**Pratyaksh Singh:** Okay.

**Ratul Shashank:** is it takes what

**Pratyaksh Singh:** All

**Hemanth Sarabu:** Come on.

**Ratul Shashank:** is the distance from the center to the edge of the object. And it

**Pratyaksh Singh:** right.

**Ratul Shashank:** it uh makes a function of distance the elongation uh

**Hemanth Sarabu:** Mhm.

**Ratul Shashank:** uh I've not implemented the degree the radian but basically it it it takes the distance from the center to the edge and gives a number and what

**Pratyaksh Singh:** in all direction.

### **00:41:52** {#00:41:52}

**Ratul Shashank:** my uh yeah,

**Pratyaksh Singh:** Okay.

**Ratul Shashank:** so it uh it will it uh it will take for elongation to from here to here and height it will it will have one number.

**Pratyaksh Singh:** All

**Ratul Shashank:** Uh so I would basically get a function of length to

**Pratyaksh Singh:** right.

**Ratul Shashank:** height and using that I can change uh I can change that function to get new shapes. I have not uh for this I have not implemented for other like radian uh angle or any other uh metrics. But yeah this this I I need to finish finish this. So before I can give you any meaningful insight on this this is an open item. This and the one that you saw both are an open item.

**Pratyaksh Singh:** We are taking the mask from the training data, right?

**Ratul Shashank:** from the object.

**Pratyaksh Singh:** Uh that is from the data set,

**Ratul Shashank:** Yeah.

**Pratyaksh Singh:** right?

**Ratul Shashank:** Yeah. Yeah.

**Pratyaksh Singh:** That is from data.

**Ratul Shashank:** Yeah.

**Pratyaksh Singh:** And then from what you're seeing I feel like you're sc are you scaling the mask out like increasing the length height all these

### **00:43:21** {#00:43:21}

**Ratul Shashank:** No.

**Pratyaksh Singh:** things.

**Ratul Shashank:** Uh uh I I'm not doing that. Uh what would

**Hemanth Sarabu:** Yeah, I think you should uh maybe take this offline.

**Ratul Shashank:** uh

**Pratyaksh Singh:** All right. Yeah. Okay. All right.

**Ratul Shashank:** yeah I will I will share both the updates on Slack.

**Hemanth Sarabu:** Um,

**Pratyaksh Singh:** Perfect.

**Ratul Shashank:** Uh I will try to do it uh have it done by tomorrow but before the next meeting I will have both the updates.

**Hemanth Sarabu:** quick. Um, Roto, I think you should aim to be more aggressive. Um, you should be able to know by in 24 hours or so whether you can generate meaningful samples, background objects, everything. You should not need more than 24 hours to

**Ratul Shashank:** Yeah, I mean I am taking a buffer time like if it takes me because uh

**Hemanth Sarabu:** know.

**Ratul Shashank:** like uh if it would take me more than that like but yeah I I can I can share the updates. It's tomorrow itself. Um,

**Hemanth Sarabu:** Okay.

### **00:44:39** {#00:44:39}

**Ratul Shashank:** no, not a

**Hemanth Sarabu:** Yeah. Yeah.

**Ratul Shashank:** problem.

**Hemanth Sarabu:** So, aim aim to like have uh have this working

**Ratul Shashank:** Yeah,

**Hemanth Sarabu:** tomorrow.

**Ratul Shashank:** I will I will share it on Slack.

**Hemanth Sarabu:** Okay.

**Ratul Shashank:** Okay.

**Pratyaksh Singh:** Yeah. Uh I was trying to set up the training

**Hemanth Sarabu:** What's

**Pratyaksh Singh:** for with the synthetic data. I still need those hyperparameters from brethul. I will set it up once I get that get those numbers get those hyperparameters from it. uh apart from that huh

**Hemanth Sarabu:** okay

**Pratyaksh Singh:** what I'm saying apart from that for synthetic data I don't have any

**Hemanth Sarabu:** Go.

**Pratyaksh Singh:** update right Oh.

**Hemanth Sarabu:** Okay. Um um so you're blocked.

**Pratyaksh Singh:** Yeah. for for training I am and for synthetic data uh I mean currently I don't have any more ideas on how to generate

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** them

**Hemanth Sarabu:** Can you share the code? So my gut says that you should be able to if you have something that actually kind of works and if you have something that will work, an approach that will work, um you should be able to find out very quickly by setting up setting up an optimization loop.

### **00:46:46**

**Hemanth Sarabu:** Um is the project is the code very complex?

**Pratyaksh Singh:** Ron, it's not complex. It's in a notebook. I shared it on Slack channel.

**Hemanth Sarabu:** Oh. Uh,

**Pratyaksh Singh:** It's not Yeah.

**Hemanth Sarabu:** is it self

**Pratyaksh Singh:** Yeah. It's just uh two notebooks.

**Hemanth Sarabu:** self-contained?

**Pratyaksh Singh:** That's it. I mean like every cell block has every cell block has one. So you are saying that I should embed Roxan in the last

**Hemanth Sarabu:** So this is in

**Pratyaksh Singh:** message.

**Hemanth Sarabu:** I see

**Pratyaksh Singh:** So you're saying that like I can set up an agent in an optimization loop to figure out the hyperparameters.

**Hemanth Sarabu:** I think even simpler than that. My gut says that you should My gut says number one we we need to figure out our objects what we want and then backgrounds or backgrounds what we want and then

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** objects bec because uh okay that's number one. Number two, we can use something this once we decide one of them is more important I then we split them.

### **00:47:57** {#00:47:57}

**Hemanth Sarabu:** You have background generation procedural generation pieces and then you have uh object procedural generation pieces.

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** I think you should treat them separately and then there are okay then the question is what is the actual loop let's say

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** you pick objects there are different filters you can use again this could I have a very decomposition kind of biosphere there you can split it up into

**Pratyaksh Singh:** Wait. uh let me give you more information. So for background we have the diffusion based model. So that doesn't need any optimization right we have the data for it and for synthetically that we want to add for any procedural generation that we want to do for roll and pitch I have the parameters figured figured out and for sand ripples you already have the changes up you already uh you already have shared me the shared with the ch changes to introduce sand ripples and for other things like contrast and images and all those things. Suchin has figured out uh the augmentations which he's using in his V4 model.

### **00:49:14**

**Pratyaksh Singh:** So background stuff is figured out. What is left is figuring out the parameters for generation of object. So for different object what should be the parameters be and uh that's what like I'm waiting on ratul for. The first idea is to use real data with artificial object to get the first set of metrics and then slowly add more synthetic background data with these procedural object to see if like if the information uh if like if the model

**Hemanth Sarabu:** Right. Okay.

**Pratyaksh Singh:** improves

**Hemanth Sarabu:** So, let me I I understand what you have. I think uh so I'll revise what I was saying. It sounds like if you're trying to It sounds like Okay. If you don't remove the background as a layer, if you don't separate that from the object, then I'm guessing that whatever you're using to generate that square image is trying to do both generate the background and the object, right? Which is why

**Pratyaksh Singh:** So the square image that I showed in the previous meeting is that what you what you meant?

### **00:50:26** {#00:50:26}

**Hemanth Sarabu:** even

**Pratyaksh Singh:** No.

**Hemanth Sarabu:** whatever was showing down

**Pratyaksh Singh:** So that already no. So, so the script that I shared with RTOL, it takes in background as an input and then it procedurally generates object on top of it. It doesn't do both at the same time.

**Hemanth Sarabu:** How are Okay,

**Pratyaksh Singh:** It it will take any

**Hemanth Sarabu:** how are we doing?

**Pratyaksh Singh:** background.

**Hemanth Sarabu:** How are we closing the loop then?

**Pratyaksh Singh:** How are we closing the loop? Uh, Hot loop are you talking

**Hemanth Sarabu:** So if you're trying to generate objects,

**Pratyaksh Singh:** about

**Hemanth Sarabu:** is it manual manually checking if it looks visually similar to the train data sets?

**Pratyaksh Singh:** if it looks m. So see my plan is that we figure out some like range of parameters not one particular parameter but range of parameters so that it can be implemented as an augmentation and for that I think the plan is that initially you can have you know a vision model in a loop to perform that and then apart from that uh you know you can use some statistics to figure out the size location of the object object and then for color or contrast in these kind for these kind of things you'll have to check some images manually.

### **00:51:52**

**Pratyaksh Singh:** Yes. I mean for final confirmation you'll have to check some manually.

**Hemanth Sarabu:** Okay, so here's an idea. Yeah. And I would I mean I don't know if it'll work or not but um see the thing you can do is if you believe I have the right

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** primitives right uh if I I'm just going to like draw let's say you have that

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** and it's like darker here or something like that and it's like lighter here and this is actually and if you believe oh I can actually I have all the primitives to I have all the

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** primitives to uh to draw this stuff. Okay, basically I have the shapes,

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** I have the blending functions, etc. There are ways where you can say here is my training data and I'm for each sample I will combine my

**Pratyaksh Singh:** H.

**Hemanth Sarabu:** primitives. I will use my primitives to generate that picture and then you need to figure out the loss function. So you can use some structural loss functions and like color based loss functions and

### **00:52:59** {#00:52:59}

**Pratyaksh Singh:** Okay.

**Hemanth Sarabu:** then you can run these algorithms sampling based algorithms. One of them is called CMAS. Uh it's an evolutionary strategy. ES is evolutionary strategy. So basically it will just search it will just search within your primitive space and as long as you give it a way to measure cost like loss

**Pratyaksh Singh:** H.

**Hemanth Sarabu:** it will just search it continue to search and it'll try to combine your uh your primitives. So that's what I thought that's what you guys were doing but it sounds like you're you're manually trying to get it to look similar.

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** Now I don't know if this will actually work this is but it is not hard to try.

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** You know what I mean? It's not hard to go from, oh, I have this idea for for a solution. Within two hours,

**Pratyaksh Singh:** Uh-huh.

**Hemanth Sarabu:** two hours, you'll find out if this will work or if you have to go back to manual or some other shops.

**Pratyaksh Singh:** All right.

### **00:53:55** {#00:53:55}

**Pratyaksh Singh:** Okay. We'll set it up. We'll try it out. If it doesn't work, We'll figure it out manually or whatever way. I think by Wednesday I'll try to get one or two iteration of the model on

**Hemanth Sarabu:** Yeah. Okay. Sounds

**Pratyaksh Singh:** this.

**Hemanth Sarabu:** good. I mean, since you shared the notebook, I mean, do what you guys think is best.

**Pratyaksh Singh:** All

**Hemanth Sarabu:** This is my this is what my hunch says but I can if I have some time I can try it out share with you that works or not you if you want to try

**Pratyaksh Singh:** right. Yeah, I think uh All right.

**Hemanth Sarabu:** it do it just let me know so I

**Pratyaksh Singh:** Yeah. Uh yeah,

**Hemanth Sarabu:** can

**Pratyaksh Singh:** we'll try it out. We'll try it out. I think if anything like this works, it will be really helpful. Like For future also it will be really

**Hemanth Sarabu:** Yeah, and there are it is main there. Yeah,

### **00:54:53** {#00:54:53}

**Pratyaksh Singh:** helpful.

**Hemanth Sarabu:** I mean the two main pieces are how do you initialize so your optimizer won't get stuck in a local minimum. There is a really bad answer to that which is do a lot of random trials, random initializations, right? Which is which sucks. But at least you're trading off compute for human time. This is very CPU intensive usually. And then the other option is uh and the other problem is can you come up with a good loss function and uh so once you so in many ways actually I would say coming up with a good loss function is the most important problem to solve once you figure that out you can start you can start like searching searching the the hypothesis space uh with your optimizing

**Pratyaksh Singh:** Got it. Now you answer M A right

**Hemanth Sarabu:** That is one that I know it's coarian matrix adaptation

**Pratyaksh Singh:** algorithm.

**Hemanth Sarabu:** evolutionary strategy. There's it's very simple. There's also there's also one called CS you know CM cross entropy method which is even even simpler.

### **00:56:09**

**Hemanth Sarabu:** These are all very simple sampling based ones.

**Pratyaksh Singh:** Got it.

**Hemanth Sarabu:** Um yeah, there the the thing is you just want something that

**Pratyaksh Singh:** It basically tells which one is better,

**Hemanth Sarabu:** doesn't need gradients. Exactly. But does not need gradients. So you can use everything in the sci optimize kit uh except the ones that require gradients.

**Pratyaksh Singh:** right?

**Hemanth Sarabu:** Right. They're meant for meant for more smoother loss landscapes. Um it it it's it's a whole thing

**Pratyaksh Singh:** All

**Hemanth Sarabu:** like you could even use gradient based ones to to fine-tune them right at the end. But yeah, so that's what I would do. That's what I would try actually.

**Pratyaksh Singh:** right.

**Hemanth Sarabu:** Okay, got to drop guys. Any any questions, thoughts? I think we should go.

**Geoff Horowitz:** Okay.

**Hemanth Sarabu:** Okay. All right. Speak one sec.

**Geoff Horowitz:** Okay, Sachin. Um, again, just throw throw those tables to the group chat whenever you get them and ping me if you have any questions or any updates or anything.

### **00:57:57** {#00:57:57}

**Geoff Horowitz:** I I think I mentioned this to you on Friday. I I would I really really really want to try to uh get Bedrock the models this week and hopefully wrap up the um the Jetson testing too. Um I will spearhead the Jets and testing. I'll just need I'll need your support a little bit, but I'll I'll reach out for that.

**Sachin Pandey:** I will share the the table as soon as

**Geoff Horowitz:** Okay, great.

**Sachin Pandey:** possible.

**Geoff Horowitz:** Cool. All right. Uh, I'm going to drop unless unless you guys need me.

**Pratyaksh Singh:** straight up. We can just finish

**Geoff Horowitz:** Okay, thanks a lot, guys.

### **Transcription ended after 01:26:36**

*This editable transcript was computer generated and might contain errors. People can also change the text after it was created.*