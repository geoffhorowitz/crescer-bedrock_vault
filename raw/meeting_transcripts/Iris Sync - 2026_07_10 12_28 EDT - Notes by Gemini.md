Jul 10, 2026

## Iris Sync

Invited [[Sachin Pandey]{.underline}](mailto:sachin@crescer.ai)
[[Pratyaksh Singh]{.underline}](mailto:pratyaksh@crescer.ai) [[Niveta
Iyer]{.underline}](mailto:niveta@crescer.ai) [[Hemanth
Sarabu]{.underline}](mailto:hemanth@crescer.ai) [[Geoff
Horowitz]{.underline}](mailto:geoff@crescer.ai) [[Siddharth
Soni]{.underline}](mailto:siddharth@crescer.ai) [[Ratul
Shashank]{.underline}](mailto:ratul@crescer.ai)

Attachments [[Iris
Sync]{.underline}](https://calendar.google.com/calendar/event?eid=NnNzMHVxNzk3MmJqZGVwNXFoN2J1Mjd1OTdfMjAyNjA3MTBUMTYzMDAwWiBnZW9mZkBjcmVzY2VyLmFp)

Meeting records
[[Transcript]{.underline}](https://docs.google.com/document/d/1pD5NAeK5fi91a71mwpPIpyS-DqeqKmPrKmB9-mcDzUI/edit?usp=drive_web&tab=t.rytjl66zfknn)

### Summary

The team assessed data integration and model performance while
strategizing on synthetic workflows and future agentic systems.\
\
**Data and Pipeline Validation**\
The team excluded unsuitable open source data and corrected metric
errors caused by mismanaged background classes in the legacy pipeline.
They also opted to transition to an 80/20 or 90/10 data split to improve
statistical reliability.\
\
**Synthetic Data and Benchmarking**\
The team committed to running baseline inference on the legacy model and
exploring two-stage inpainting approaches for synthetic data generation.
This will improve model performance on underrepresented data
distributions.\
\
**Workflow and Agentic Systems**\
Participants established requirements for documenting Comfy UI workflows
and proposed developing a secure, containerized agentic operating
system. A decision was made to compile a product requirements document
to formalize the agentic system architecture.

### Decisions

Needs Further Discussion

-   **Agentic OS implementation strategy** The implementation strategy
    > for an Agentic OS to synthesize meeting data is deferred pending
    > the development of a formal PRD, which will serve as the basis for
    > a future group discussion on requirements and risks.

Aligned

-   **Open-source data exclusion from baseline** The team decided to
    > exclude open-source data from the training baseline to avoid
    > out-of-distribution noise, while retaining it as a backup option
    > if needed.

-   **Data split ratio adjustment** The team decided to adopt an 80/20
    > train-to-validation data split to mitigate issues caused by small
    > dataset size and geographic overlap.

-   **Legacy pipeline benchmarking strategy** The team decided to run
    > the new dataset through the legacy pipeline to establish a
    > performance benchmark for comparison.

-   **Synthetic data generation strategy** The team aligned on the
    > strategy to pursue synthetic data generation for background and
    > context variation, distinct from the current diffusion-based
    > experimental approach.

-   **Communication protocol set to public channels** Project reporting
    > and team updates must be shared within public channels rather than
    > via personal direct messages to ensure transparency and team
    > visibility.

We\'ve **updated the Decisions section** using your feedback.

Let us know what you think:
[[Helpful]{.underline}](https://google.qualtrics.com/jfe/form/SV_5p6FWBVWvynleNU?isGoogler=no&isHelpful=yes)
or [[Not
Helpful]{.underline}](https://google.qualtrics.com/jfe/form/SV_5p6FWBVWvynleNU?isGoogler=no&isHelpful=no)

### Next steps

-   \[Sachin Pandey\] Mark Test Area: Capture a screenshot of the Mosaic
    > test area and add a visual marking to identify the geographic test
    > region.

    > \[Sachin Pandey\] Generate Project Report: Generate a sharable
    > report documenting the training progress and model performance by
    > Monday.

    > \[Sachin Pandey\] Run Legacy Inference: Run inference on all new
    > data sets using the legacy model pipeline and compile the metrics
    > by Monday.

    > \[Ratul Shashank, Geoff Horowitz\] Finalize S7K Pipeline: Complete
    > the remaining steps for the S7K pipeline by Monday.

    > \[Ratul Shashank\] Create Synthetic Report: Generate a report
    > detailing synthetic data workflows, including specific graph
    > visualizations, transformation methods, input-output examples, and
    > the underlying logic used in Comfy UI.

    > \[Ratul Shashank\] Share Synthetic Report: Share the completed
    > synthetic data report in the Bedrock channel to ensure team
    > visibility.

    > \[Ratul Shashank\] Draft Agentic PRD: Draft a PRD-style report
    > outlining thoughts, risks, requirements, and considerations for
    > implementing an agentic operating system for the team to
    > synthesize tribal knowledge and meeting transcripts.

    > \[Ratul Shashank\] Share Agentic PRD: Share the agentic OS PRD in
    > the compute channel.

    > \[Hemanth Sarabu, Geoff Horowitz\] Discuss Compute: Discuss the
    > potential need for new GPU compute resources.

    > \[Hemanth Sarabu\] Review Teledyne: Review the Teledyne
    > information previously sent.

    > \[Geoff Horowitz\] Review MA Report: Review the latest MA report
    > located in the EDA folder.

### Details

-   **Open Source Data Integration**: Sachin Pandey evaluated the open
    > source data and determined that because the data used bounding
    > boxes rather than the required masks, and because the samples were
    > highly variable, noisy, and out-of-distribution, it was not
    > suitable for the current training set. They decided to exclude
    > this data for now but keep it as a backup option if needed
    > ([[00:02:47]{.underline}](#section))
    > ([[00:06:53]{.underline}](#section-3)). The sand ripple data,
    > which possessed strong features, was handled independently and was
    > easy to predict, so it was already labeled and included in the
    > training ([[00:08:04]{.underline}](#section-4)).

-   **Test and Validation Set Selection**: Sachin Pandey explained that
    > they extracted bounding boxes for all XDF files and separated the
    > validation and test sets based on latitude and longitude
    > coordinates ([[00:08:04]{.underline}](#section-4)). Geoff Horowitz
    > requested that Sachin Pandey provide a visual representation or
    > screenshot of the geographic area used for testing within their
    > notes to ensure the team has a clear understanding of the test
    > data location ([[00:09:34]{.underline}](#section-5)).

-   **Legacy Pipeline Performance and Metric Errors**: Sachin Pandey
    > reported that initial results from the legacy pipeline were
    > unreliable because the background class was incorrectly included
    > in the metric calculations, distorting the results
    > ([[00:11:06]{.underline}](#section-6)). Consequently, Sachin
    > Pandey performed a model retraining to address the potential for
    > data leakage, specifically ensuring the test set was not included
    > in the training data ([[00:15:24]{.underline}](#section-9)). While
    > the training loss showed some fluctuations, the team noted this is
    > a normal occurrence during the training process
    > ([[00:16:29]{.underline}](#section-10)).

-   **Dataset Splitting Strategy**: Hemanth Sarabu critiqued the current
    > train, validation, and test split, noting that with a small
    > dataset, a three-way split results in noisy and unreliable
    > statistics ([[00:18:15]{.underline}](#section-11)). Hemanth Sarabu
    > advised that they should move to an 80/20 or 90/10 split instead,
    > and once the hyperparameters are finalized, they should train on
    > the entire dataset ([[00:20:05]{.underline}](#section-12))
    > ([[00:22:52]{.underline}](#section-14)). Pratyaksh Singh confirmed
    > that because the dataset has overlap issues, they had already
    > implemented a geographic split to ensure the validation set size
    > is sufficient ([[00:23:54]{.underline}](#section-15)).

-   **Reporting and Documentation Standards**: Geoff Horowitz emphasized
    > the need for consistent, sharable reporting, noting that the
    > reports created by Ratul Shashank are effective for documenting
    > progress and communicating the full story of the project. Although
    > Sachin Pandey prefers to work with local tools, Geoff Horowitz
    > insisted that Sachin Pandey generate a report that documents the
    > dataset sizes, training progress, and results, with a deadline to
    > complete this by Monday ([[00:30:43]{.underline}](#section-19)).

-   **Legacy Model Benchmark Plan**: The team discussed the value of
    > running inference on the new dataset using the original legacy
    > model to establish a clear baseline
    > ([[00:33:05]{.underline}](#section-21)). Hemanth Sarabu noted that
    > inference is inexpensive, making this a useful exercise for
    > storytelling and benchmarking purposes
    > ([[00:34:27]{.underline}](#section-22)). Sachin Pandey agreed to
    > perform this task and provide the metrics by Monday
    > ([[00:35:31]{.underline}](#section-23)).

-   **Workflow Tooling Preferences**: The team engaged in a discussion
    > regarding their preferred terminal and workflow management tools,
    > with Sachin Pandey sharing that they use a tool called Harder,
    > which allows for agent tracking and mouse-based editing. Hemanth
    > Sarabu, Pratyaksh Singh, and Ratul Shashank discussed their
    > varying preferences for using vanilla terminal configurations,
    > tmux, and fuzzy search shortcuts, noting the importance of
    > organization to avoid clutter during development
    > ([[00:36:39]{.underline}](#section-24))
    > ([[00:39:35]{.underline}](#section-27)).

-   **Diffusion Model Experimentation**: Pratyaksh Singh presented
    > TensorBoard results for a fine-tuned diffusion model trained on
    > five graphics processing units
    > ([[00:44:21]{.underline}](#section-31)). The experiment involved
    > conditioning the model on the dataset and specific target masks,
    > though Pratyaksh Singh noted that the model struggles when
    > conditioning on masks for which there is no corresponding training
    > data ([[00:47:04]{.underline}](#section-33)). Unconditional
    > generation performed well, but the team identified that further
    > work is required to improve generation when masks are present
    > ([[00:48:01]{.underline}](#section-34)).

-   **Synthetic Data Strategy and Compute Needs**: Hemanth Sarabu
    > suggested that the team explore a two-stage approach for
    > inpainting, rather than attempting joint generation, to improve
    > performance on data-poor distributions
    > ([[00:51:23]{.underline}](#section-37)). Pratyaksh Singh agreed to
    > experiment with this approach to see if it generalizes better
    > ([[00:53:48]{.underline}](#section-39)). Regarding synthetic data
    > generation, Ratul Shashank reported on their exploration of Comfy
    > UI ([[00:58:00]{.underline}](#section-42)). Additionally, the team
    > briefly discussed the need for further compute resources, with
    > Geoff Horowitz and Hemanth Sarabu agreeing to discuss the
    > potential need for a new graphics processing unit later in the
    > evening ([[00:55:04]{.underline}](#section-40)).

-   **Comfy UI Image Generation Workflows**: Ratul Shashank described
    > utilizing three distinct Comfy UI workflows to process data. They
    > utilized \"Z Image Turbo\" as the base model, applying denoising
    > and random seed adjustments to generate image variations. To
    > ensure the images retained features from the original dataset
    > while introducing variety, Ratul Shashank created a binary image
    > and superimposed it onto a background generated by the model
    > ([[01:00:41]{.underline}](#section-44)).

-   **Workflow Documentation and Reporting**: Pratyaksh Singh requested
    > that Ratul Shashank create a report documenting these workflows.
    > The documentation must include images of the underlying graphs,
    > descriptions of the specific transformations applied to the
    > images, and examples showing the progression from the raw image
    > and mask to the final model output
    > ([[01:03:48]{.underline}](#section-46))
    > ([[01:07:30]{.underline}](#section-49)). Pratyaksh Singh expressed
    > interest in potentially using these transformations as
    > augmentations for training if the process is efficient and simple
    > ([[01:04:48]{.underline}](#section-47)). The report is to be
    > shared in the team channel to allow for broader feedback rather
    > than via personal direct message
    > ([[01:08:31]{.underline}](#section-50)).

-   **Synthesis of Knowledge and Agentic Systems**: Geoff Horowitz
    > initiated a discussion regarding how to synthesize \"tribal
    > knowledge\" and the large volume of data stored on the drive and
    > in recorded meeting transcripts
    > ([[01:08:31]{.underline}](#section-50)). Ratul Shashank proposed
    > an agentic operating system where agents could be deployed to
    > handle tasks such as reading transcripts, recording meetings,
    > creating notes, and generating visual representations of ongoing
    > tasks ([[01:09:42]{.underline}](#section-51)). They emphasized the
    > importance of security, suggesting that these agents be deployed
    > in dockerized containers to ensure they remain under strict
    > control ([[01:10:59]{.underline}](#section-52)).

-   **Agentic System Development Next Steps**: Geoff Horowitz requested
    > that Ratul Shashank document their thoughts, considerations,
    > risks, and requirements regarding the proposed agentic system when
    > they have time. Ratul Shashank committed to compiling a Product
    > Requirements Document (PRD) report containing these details and
    > sharing it in the compute channel
    > ([[01:12:13]{.underline}](#section-53)).

-   **MAG Report and Communication Empowerment**: Ratul Shashank
    > inquired whether Geoff Horowitz had reviewed the MAG report
    > previously shared in the EDA folder and the Bedrock channel,
    > specifically asking if the data analysis was aligned with the work
    > conducted by Bedrock. Geoff Horowitz acknowledged the request and
    > encouraged Ratul Shashank to feel empowered to follow up or
    > \"bump\" them in threads if they are waiting for feedback or
    > information ([[01:13:15]{.underline}](#section-54)).

*You should review Gemini\'s notes to make sure they\'re accurate. [[Get
tips and learn how Gemini takes
notes]{.underline}](https://support.google.com/meet/answer/14754931)*

*How is the quality of **these specific notes?** [[Take a short
survey]{.underline}](https://google.qualtrics.com/jfe/form/SV_9vK3UZEaIQKKE7A?confid=_w7sD3RCDFsHPewPXHJhDxIUOAIIigIgABgBCA&detailid=standard&screenshot=false)
to let us know your feedback, including how helpful the notes were for
your needs.*

**📖 Transcript**

Jul 10, 2026

## Iris Sync - Transcript

### 00:02:47

**Geoff Horowitz:** Hey guys.

**Sachin Pandey:** Thank you. I think

**Ratul Shashank:** Hey Guys,

**Geoff Horowitz:** Um, okay. Uh let\'s jump in. Satch, can you

**Sachin Pandey:** Yeah. So I will start with the task that you given
me.

**Geoff Horowitz:** start?

**Sachin Pandey:** So include open source data. So I looked at the open
source data and first it was like bounding boxes not not mask which we
need and second like uh I I like try I try to add the data which
doesn\'t have any annotations but

**Geoff Horowitz:** Sergeant, Sergeant, give me give me just one second.

**Sachin Pandey:** h

**Geoff Horowitz:** I\'m struggling to hear. I\'m going to put my
headphones in. Give me one sec. Uh, okay. Let\'s try now.

**Sachin Pandey:** Okay. So I was saying that uh in open source data the
annotations were in bounding boxes. So I tried to find the data which
doesn\'t have any bounding boxes. So we can just add it so models can
learn the background. But issue with that was like each and every data
was different to each

### 00:04:10

**Geoff Horowitz:** Good.

**Sachin Pandey:** other like even in the open source data like there
was uh like they vary a lot. So I can just with the name and like each
and every one looks very different. So

**Geoff Horowitz:** So such an I I might have not been clear on
Wednesday. I I do think we should include open source. Um but I\'m okay
with getting a baseline without it. Does that make

**Sachin Pandey:** Yes. Like it was looking very weird that\'s why I
didn\'t edit it.

**Geoff Horowitz:** sense?

**Sachin Pandey:** So like something like this. So you see like so VP is
these ones like I try to find all the data set and with the folder that
S created. So like suppose this is one group and this near sore is other
group and re is other group. So each of them has like very distinct view
and they they don\'t match with each other at all and there are not many
examples of each one.

**Geoff Horowitz:** What does that mean? A distinct view.

### 00:05:27

**Geoff Horowitz:** What does this mean?

**Sachin Pandey:** So let me just open like few one at a time. One will
be this. This will be like two different one. And let\'s find one more.
You see like I have opened three and all three are like very different
to each other.

**Geoff Horowitz:** I do

**Sachin Pandey:** You\'re not and like some are like from the starting
there

**Geoff Horowitz:** see

**Sachin Pandey:** were some these ones artificial

**Geoff Horowitz:** and these are all background.

**Sachin Pandey:** grief these are our background like I didn\'t found
anything these

**Geoff Horowitz:** around.

**Sachin Pandey:** text files are empty like something like

**Geoff Horowitz:** Uhhuh.

**Sachin Pandey:** these so they are object uh like they artificially
maybe they were they were like the cages where they grow Um

**Geoff Horowitz:** Uhhuh. Um,

**Sachin Pandey:** plant.

**Geoff Horowitz:** okay. So your your point is is this data is going to
be too it\'s going to be too far out of distribution. It\'s going to be
too noisy. It\'s it\'s really going to mess mess our model up.

### 00:06:53

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Okay, fine.

**Sachin Pandey:** So that\'s why like I haven\'t added I didn\'t add
these for background too cuz these were like very out of distribution
and not a whole lot example like if we find this there are only like few
files I don\'t think like there is also mistake because these are
clearly object manmade object and they are labelled we want to get them
labelled

**Geoff Horowitz:** Mhm. Yeah. Right.

**Sachin Pandey:** correctly but we are not in these objects at

**Geoff Horowitz:** Fine. So in Yeah. So, so in order to incorporate
these into our training set, we\'d have to get our labelers to go in and
mess with

**Sachin Pandey:** Sure.

**Geoff Horowitz:** it. Um, okay. Let\'s keep it as a backup option. Uh,
let\'s keep it as a backup option in case we need it. I I guess I mean,
look, we we know we need more data, right? So,

**Sachin Pandey:** Yes.

**Geoff Horowitz:** so our options are open source, but even if we get
our labelers to do this, like you know, some of the stuff is going to be
obvious to us, but some of it is not, right?

### 00:08:04

**Geoff Horowitz:** Um,

**Sachin Pandey:** Yes. Someone some files uh have objects which look
like

**Geoff Horowitz:** yeah.

**Sachin Pandey:** uh send ripples. Yeah. Send ripples.

**Geoff Horowitz:** Okay. Um, fine.

**Sachin Pandey:** But most of the data like we these are like very out
of distribution. So uh unless we really need it, I don\'t think it makes
sense to add

**Geoff Horowitz:** Okay.

**Sachin Pandey:** them.

**Geoff Horowitz:** What did we end up doing with the sand ripple data

**Sachin Pandey:** Uh we are pretty on it like send data is uh like
features are very strong.

**Geoff Horowitz:** from?

**Sachin Pandey:** So it\'s easy to predict.

**Geoff Horowitz:** Okay. Did we uh in the sand ripple data the features
are very strong so it\'s easy to predict meaning we We labeled them
independently as sand rebels in the training. Okay, good.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Um, I hear what you\'re saying about the the open
source data. Um,

**Sachin Pandey:** The other task was to pick the test set.

**Geoff Horowitz:** I

**Sachin Pandey:** I I I did it. I extracted the bounding boxes for all
the uh XDF files and separated it based on latl long and selected the
validation set and test set which are

### 00:09:34

**Geoff Horowitz:** fantastic.

**Sachin Pandey:** not.

**Geoff Horowitz:** Fantastic.

**Sachin Pandey:** So this is done

**Geoff Horowitz:** uh in in in wherever you\'re wherever you\'re
keeping all of your

**Sachin Pandey:** and

**Geoff Horowitz:** notes. Can you can you take the mosaic? Um what am I
trying to say? Give me a second. Show you what I\'m trying to say. Say
it. Oh, I don\'t have link. Um, well, here I\'ll show you here. Can you
just take a screenshot of the area in Mosaic and um, you know, some
somehow make a marking that says, you know, best area or something like
that. Do you do you understand what I\'m saying?

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Yeah.

**Sachin Pandey:** With the

**Geoff Horowitz:** Uh yeah.

**Sachin Pandey:** background.

**Geoff Horowitz:** I mean or just just something so that something in
your notes so that we can look at it and say, \"Oh, this this geographic
area was the test area.\" Does that make sense?

**Sachin Pandey:** Yeah. I I have the like names of the save file which
I used like I renamed the save file to PNG and just use those names to
create a test and set it.

### 00:11:06

**Geoff Horowitz:** Okay.

**Sachin Pandey:** I can use those to generate this. Okay, I I can do
that.

**Geoff Horowitz:** Yeah. Okay. I mean, it doesn\'t, you know, it\'s up
to you.

**Sachin Pandey:** Sure. Is

**Geoff Horowitz:** It doesn\'t need to be perfect perfect,

**Sachin Pandey:** that

**Geoff Horowitz:** but as long as we have a visual sense, I think
that\'ll be helpful.

**Sachin Pandey:** Yeah. Yeah, I can

**Geoff Horowitz:** Cool.

**Sachin Pandey:** do.

**Geoff Horowitz:** Um, okay. What are the results on the what are the
results on the existing pipeline? The uh legacy

**Sachin Pandey:** So all model old models were like bad.

**Geoff Horowitz:** pipeline.

**Sachin Pandey:** the they were predicting it but the matrix were
messed up because I included the background and background like
background like interfered with the other classes and like but um

**Geoff Horowitz:** The you included the background from the open source
data.

**Sachin Pandey:** No background as a class. So it it like it affected a
matrix a lot. So all m like those metrics are not usable. But we can see
the prediction predictions on the other classes are good but like

### 00:12:14

**Geoff Horowitz:** How did we include?

**Hemanth Sarabu:** What do you mean added background of the class?

**Sachin Pandey:** metric.

**Geoff Horowitz:** Yeah, exactly.

**Sachin Pandey:** So uh I changed it in the new pipeline new model but
we see we see the same like issue with the like fluctuation in the
learning learning

**Hemanth Sarabu:** Wait, what what do you mean you added

**Sachin Pandey:** loss.

**Hemanth Sarabu:** background? If it\'s segmentation, there\'s a
background class implicitly already.

**Sachin Pandey:** So like background was used in calculating the
matrix. So if you see these like where IO is one there is no class but
still if you see the so this is uh this was a mistake and

**Hemanth Sarabu:** Mhm.

**Sachin Pandey:** it is not usable but we can still see the predictions
of other classes those were like what this is a multiclass prediction
and this is a ground truth.

**Hemanth Sarabu:** Okay, I just want to make sure. Do you predict a
background class?

**Sachin Pandey:** No, but it was included in the like it calculates if
doesn\'t print

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** anything. So that\'s why we are getting like so high
high ranges.

### 00:13:47

**Hemanth Sarabu:** So I Oh, you just need to remove the you should just
calculate on on uh files that are not like fully that have no ground
root targets or something like that. something like that.

**Sachin Pandey:** I don\'t have any background

**Hemanth Sarabu:** Not background targets, targets.

**Sachin Pandey:** something like this.

**Hemanth Sarabu:** Okay, I we need to take a step back. Can you tell me
what? Okay. So Jeff fast the the first project model pipeline. How did
it do? Right. Does that am I understanding? Are you just running
inference on the on the new data set? Has it been trained jointly with
the old data set and then we run inference like what or am I missing
something because I I\'m late to the meeting.

**Sachin Pandey:** the new data set. You mean the old data that we just

**Hemanth Sarabu:** Okay, ignore what I\'m asking.

**Sachin Pandey:** got

**Hemanth Sarabu:** Jeff,

**Geoff Horowitz:** No, no, no. Sergeant,

**Hemanth Sarabu:** can you catch me up?

**Geoff Horowitz:** yeah, you\'re you\'re you\'re pretty much catching
caught up, Sasha.

### 00:15:24

**Geoff Horowitz:** We ran we ran the data through the legacy pipeline,
right? We ran the new data through the legacy pipeline. Is that correct?
Okay.

**Sachin Pandey:** Yes,

**Hemanth Sarabu:** What does John mean? Inference only or training and

**Geoff Horowitz:** What?

**Sachin Pandey:** we trained and inference on it. The predictions are
like looking good.

**Hemanth Sarabu:** inference.

**Sachin Pandey:** These are the these are the predictions. We train two
model the binary and multiclass and ignore if you ignore the matrix like
the prediction like viewing them predictions are like actually

**Geoff Horowitz:** Okay.

**Sachin Pandey:** good.

**Geoff Horowitz:** Yeah. Hand we Yes.

**Hemanth Sarabu:** I see.

**Geoff Horowitz:** Okay. So So do we do we have summary statistics?

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** So

**Geoff Horowitz:** Are those the are those the statistics on top

**Sachin Pandey:** these are wrong.

**Geoff Horowitz:** there?

**Sachin Pandey:** So reason why I retrained it again because as Jeff
said there is a high chance that the training data also include the test
set because we were randomly distributing it. So the new model should
have a test set which is not included in the training based data.

### 00:16:29

**Sachin Pandey:** So that\'s why we uh started the new training and
this is this is the first iteration where there was a mistake in the
data set. This is So you see like the fluctuation that\'s what I\'m
trying to solve earlier because if we see the the binary one it was also
similar similar to this last time we trained the two model the binary
loss was also like fluctuating on lot when

**Hemanth Sarabu:** The fluctuation is normal.

**Sachin Pandey:** these ones Piper is the latest one.

**Geoff Horowitz:** You\'re seeing the purple the purple

**Sachin Pandey:** Yes,

**Geoff Horowitz:** section

**Hemanth Sarabu:** It\'s okay. I was

**Sachin Pandey:** I made some changes in config and running it again.
It\'s not the green one is

**Hemanth Sarabu:** trained.

**Sachin Pandey:** the one I have just started with the change in
config.

**Geoff Horowitz:** section. How does the training curves, how do the
training loss losses look?

**Hemanth Sarabu:** How big is the validation set? How big is the
training set? I guess let me ask, is it big? Are they both pretty large?

### 00:18:15

**Hemanth Sarabu:** Or are they both pretty small? Or is one

**Sachin Pandey:** Uh test set is 55 52 files and validation set 72

**Hemanth Sarabu:** Why is there we have a test and

**Sachin Pandey:** files.

**Hemanth Sarabu:** validation?

**Sachin Pandey:** Yes. and

**Hemanth Sarabu:** We don\'t we don\'t we don\'t need to do that.

**Sachin Pandey:** 320

**Hemanth Sarabu:** Um, what is a what is a split train valve test?

**Sachin Pandey:** we need to calculate it because like uh I selected
them manually using like their latl long positions.

**Hemanth Sarabu:** Mhm.

**Sachin Pandey:** I need to calculate

**Hemanth Sarabu:** But what is what is a rough what is a rough uh
percentage

**Sachin Pandey:** the

**Hemanth Sarabu:** split

**Sachin Pandey:** 30% 30

**Hemanth Sarabu:** 30? What is 30? What is 30?

**Sachin Pandey:** uh 70% uh train set and 30 including B test

**Hemanth Sarabu:** Okay. So, okay.

**Sachin Pandey:** 125.

**Hemanth Sarabu:** Do you what what is the thinking behind valent test?
Okay. Okay. I will I will I will kind of I\'ll just uh run through this
very quickly.

### 00:20:05

**Sachin Pandey:** B.

**Hemanth Sarabu:** Um you can you know you can the the reason you you
did balance test is uh is reasonable if we have a large enough data set.
When we have such a small data set every time you split up the split
split it up and then compute any statistics it\'ll be extremely noisy.
So you lose your signal from your test set and similarly from your
validation set because the data set is so small. So we just do typically
8020 9010 split. Do you remember how we train Iris? We don\'t do this.
We don\'t do train val. We do a 8020 or 9010 something like that. And
once we find a good parameter set, hyperparameter set, we just train on
everything. We should train on everything. We may not have done that for
time reasons, but that\'s what we should do. Does that make sense?

**Sachin Pandey:** uh a little bit like the reason we don\'t want to
split it because the model is not able to get large data to learn.

### 00:21:29

**Sachin Pandey:** So things

**Hemanth Sarabu:** Um, so people in the machine learning community
introduced this split for train validation. in test for the following
reason. The idea was your test set would never would never you would
actually never use your test set until you do your final final
benchmarking. Meaning you only use the test set at the at the end. That
was the original intention for the test set. And then you use the train
and val to figure out what your hyperparameters are, what your model is,
whatever, right? to your validation set is not seen during training. But
as a human, you would try to increase your validation performance. And
once you figure out what your model is, what your hyperparameter is, you
combine the train and validation uh data sets and use the best best
configuration you found, best model you found and train it. And then at
the end and only once you would

**Sachin Pandey:** That\'s

**Hemanth Sarabu:** predict on the test set and you would know what is
your um generalization

**Sachin Pandey:** it.

### 00:22:52

**Hemanth Sarabu:** performance. Now people stopped doing that. No one
does that anymore because that is not what people started doing was they
will do that train val they\'ll predict on test. They\'re like oh this
is not good. I\'m going to go back and change something else. And then
the question becomes what is the difference between your validation and
test set? If you\'re not going to do that thing where you only test once
at the end, what\'s the point? Your training set has become smaller
because you\'re now splitting it into valid validation and test. And if
your data set is very small, then any metrics you generate on your
validation set are going to be very noisy and not as reliable. And so
people stop doing that. So now people don\'t train valid test. Your test
is basically deploying the model and seeing what the customer says.

**Sachin Pandey:** Okay. So, so we want to increase uh we want to do
9010

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** split.

**Hemanth Sarabu:** 80 8020 is good.

### 00:23:54

**Hemanth Sarabu:** 8515 is good. I don\'t know if we have a we have a
very large data set. We could do a 9010 955, but we have a small data
set. So maybe I\'m leaning 8020. Perfect. What are your thoughts?

**Pratyaksh Singh:** Yeah, I mean the 70 files that he has for
validation that is good. Rest he can put it into test. So it will yeah
it will correspond to I think 8020. This data set has a problem of
overlap also that\'s why the val validation should

**Hemanth Sarabu:** Oops.

**Pratyaksh Singh:** validation set should be bigger or

**Geoff Horowitz:** We corrected for that. That\'s what didn\'t we Sen
that was that was the split that was the the geographic

**Pratyaksh Singh:** what

**Geoff Horowitz:** split

**Pratyaksh Singh:** yeah yeah yeah we corrected for it that\'s why I
can so for example what one file in

**Sachin Pandey:** Yes.

**Pratyaksh Singh:** validation would have been two files or one and a
half files

**Geoff Horowitz:** actually the very the end of your statement broke up
for me. What\' you say?

### 00:25:19

**Pratyaksh Singh:** I was saying that the that you know we will have to
make the validation set longer because of the overlap. For example,
let\'s say previously we used to do 50 but because of the overlap it
will automatically increase something like 70 or something.

**Geoff Horowitz:** Got it. So, so Sachin, what was So, right now for
for this model that you\'re showing us, you you trained you you you
trained the model on like 60% of the data. Is that right? Approximately.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Okay. And what were the results from that from that
training round?

**Sachin Pandey:** Uh the predictions were like good. It were like the
object detections were decent.

**Geoff Horowitz:** This is on the vineyard winds.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Okay. Um, are the false

**Pratyaksh Singh:** So then there for add and dr also the

**Geoff Horowitz:** positives

**Sachin Pandey:** Yes, for

**Pratyaksh Singh:** visualization because I think for group it will

**Sachin Pandey:** Christmas.

**Pratyaksh Singh:** perform.

**Sachin Pandey:** like this was the feature which require

**Pratyaksh Singh:** It\'s it\'s interesting that the multiclass
prediction performs better than the

### 00:27:30

**Geoff Horowitz:** Mhm.

**Pratyaksh Singh:** binary.

**Geoff Horowitz:** What does that mean? Multiclass as binary.

**Pratyaksh Singh:** What\'s

**Sachin Pandey:** The color

**Geoff Horowitz:** Uh,

**Pratyaksh Singh:** up?

**Geoff Horowitz:** I\'m looking above per image metrics multiclass as

**Sachin Pandey:** map.

**Geoff Horowitz:** binary. Scroll up.

**Hemanth Sarabu:** I think uh Uh I I\'ll let I\'ll let them I\'ll let
Sin

**Geoff Horowitz:** Son, do you see on the left hand side it says per
image metrics?

**Hemanth Sarabu:** respond.

**Geoff Horowitz:** I\'m sorry. I\'m sorry. I\'m sorry. The right hand
side it says per image metrics model binary multiclass as

**Sachin Pandey:** Yes.

**Geoff Horowitz:** binary. What is what is multiclass as binary.

**Sachin Pandey:** Uh, not sure.

**Geoff Horowitz:** Hey.

**Sachin Pandey:** H I I\'m not sure

**Geoff Horowitz:** Okay.

**Sachin Pandey:** about

**Geoff Horowitz:** Um, I mean, look, I I certainly believe that we
should go through and kind of qualitatively look at these to make sure
that that they look good, that they make sense. On top of that, I also
believe that quantitative measurements are helpful, right? So, so
Sachin, I guess it sounds like we don\'t have, you know, recall,
precision, F1 scores that we can rely on, right?

### 00:29:09

**Geoff Horowitz:** You said those top metrics were unreliable. Yeah.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** So, I think we should get those. Um, I I get it that
it would just be, you know, for binary, right? Um, but let\'s split it
up into I mean let\'s let\'s group them in whatever way makes sense,
right? Things that are that are man-made versus things that are not
man-made or um or similar. I s how did we compute those statistics for
uh for vineyard quins in the first project?

**Sachin Pandey:** Uh, it goes like the overlapping of the areas like
the model prediction versus the ground noise.

**Geoff Horowitz:** Oh, that\'s right. It was pixel wise. Pixeliz
metric.

**Sachin Pandey:** I was also like go through the training data once
again to like make sure all the strong features are fast from the model
and just to just cross checking like whether the training data we are
trained on is actually like good enough to like the training data
doesn\'t have any mistakes in them because we already reduced the count
because we are not including the raw data set.

### 00:30:43

**Sachin Pandey:** It\'s almost half uh data.

**Geoff Horowitz:** So, so Sachin, I I want to push you to do one other
thing. We\'ve talked about this a few times. Um, I think that these
reports that Ratul puts together are really really helpful both for
documenting what we do, but also for just kind of communicating results,
right? Like like it it summarizes how big the data sets are, you know,
what what the metrics are. I mean, all all these things um are
documented and then I think it\'s easier certainly since Rul has been
sharing them. I found it easier for me to look through and it it tells a
full story. Um I know that you document a lot of this in uh notion but
it it it\'s not in a sharable format, right? Like it\'s not easy to
share. It doesn\'t necessarily tell as good of a story. I I I\'m not
going to say you have to do it the same way that RTOL does, but I really
want to push you to to get some report together that makes sense um and
that tells the story.

### 00:31:55

**Geoff Horowitz:** And I think that\'ll help all of us follow the story
and then ask more relevant questions.

**Sachin Pandey:** Okay. But I have set up the tool like similar to like
he help me set up

**Geoff Horowitz:** Uh

**Sachin Pandey:** but it is like locally. So uh I still need a way to
like link the data which what is trained on

**Geoff Horowitz:** yeah,

**Sachin Pandey:** the server and what is like pulled

**Geoff Horowitz:** sounds good. Sounds good.

**Sachin Pandey:** locally.

**Geoff Horowitz:** Um again, I want to emphasize, I mean, you could do
it his way or you could do it your way, whatever. But you\'ve you\'ve
seen the reports and you\'ve seen the story that they tell, and I think
that\'s the outcome that matters.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** Yeah. Okay. Um, yeah, I think I think that at least
for me that would really help that would help me follow the story of how
the training is going, what we\'re seeing, um, and then ultimately, you
know, how we can communicate that. either internally or to bedrock.

### 00:33:05

**Sachin Pandey:** Yeah, it it will really be helpful. I will start
dumping dumping all the things on the locally.

**Geoff Horowitz:** Okay,

**Sachin Pandey:** We can generate a report based on that data.

**Geoff Horowitz:** perfect. Perfect. Do you think you could do that by
Monday?

**Sachin Pandey:** Yes, I

**Geoff Horowitz:** Okay, great. Now um so specifically what what what I
am looking

**Sachin Pandey:** will.

**Geoff Horowitz:** for is um you know this is our benchmark right how
is this data doing on our legacy pipeline before we\'ve made any
modifications or added additional data or any I think that\'s really
important um you know that that\'s where we start hemoth actually
brought something up that I I guess I forgot to think about earlier
which Is um is it worthwhile to run to run all of the new data inference
only on the legacy model meaning the model that we delivered for bedrock
for the first project? I assume the results are going to be poor but is
that going to be useful or interesting? Uh, is that going to be a useful
or interesting benchmark for us?

### 00:34:27

**Sachin Pandey:** The benchmark compared to what like because like new
model will include those data in them. So it will like perform
relatively well compared to the old

**Geoff Horowitz:** We we agree that I\'m I\'m asking if we think that
that\'s going to be is that going to give us any insight at all? That\'s
the question I\'m asking or do we do we find that a useless

**Hemanth Sarabu:** It won\'t be useless.

**Geoff Horowitz:** exercise?

**Hemanth Sarabu:** And it\'s also Let\'s see what is the expensive
part. Inference is cheap. It is QA that\'ll be expensive.

**Geoff Horowitz:** Uhhuh.

**Hemanth Sarabu:** Um

**Pratyaksh Singh:** that can also be automated. But we have already
labeled the data.

**Sachin Pandey:** Yeah, we have

**Hemanth Sarabu:** True. Well, there you go. Then it\'s it\'s cheap to
do.

**Geoff Horowitz:** It\'s

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** easy.

**Sachin Pandey:** the

**Hemanth Sarabu:** So, it\'ll be net neutral or net

**Geoff Horowitz:** Okay. Can Can we add that in?

**Hemanth Sarabu:** positive.

**Geoff Horowitz:** I I can\'t imagine it\'ll be too hard then at least
looking at summary statistics, maybe glancing through the results.

### 00:35:31

**Geoff Horowitz:** Do you think we could do that by Monday too,
Suction?

**Sachin Pandey:** Yeah. Old model prediction in all the old model
prediction on

**Geoff Horowitz:** Say once more.

**Sachin Pandey:** all the data sets and matrix all the metrics for uh
predictions.

**Geoff Horowitz:** Yeah.

**Hemanth Sarabu:** it.

**Geoff Horowitz:** Yeah.

**Hemanth Sarabu:** Um, it might actually it could depending on what the
results are, it could help us tell a story to the customer.

**Geoff Horowitz:** Yes.

**Hemanth Sarabu:** I don\'t know what that story is,

**Geoff Horowitz:** I agree with that.

**Hemanth Sarabu:** but some depending on the results. Um, hey, what do
you guys use for multi- like if you have multiple cloud code sessions
going on or anti-gravity sessions? Do you guys just use plain demox? Do
you use something like uh conductor um you guys use or do you just use a
terminal like just barebones terminal? No demox.

**Sachin Pandey:** I don\'t know something like this is helpful.

**Hemanth Sarabu:** What is what are you using here?

**Sachin Pandey:** Uh this is like updated version of

**Hemanth Sarabu:** Wow. When you say updated,

### 00:36:39

**Sachin Pandey:** teamm

**Hemanth Sarabu:** you mean you is this is your your config or has
T-Mox actually

**Geoff Horowitz:** What?

**Hemanth Sarabu:** updated default?

**Sachin Pandey:** it\'s the tool name is uh harder the harder so it is
similar

**Geoff Horowitz:** Huh?

**Sachin Pandey:** to harder

**Hemanth Sarabu:** Purdle.

**Sachin Pandey:** h

**Geoff Horowitz:** Here,

**Hemanth Sarabu:** Harder. H E R D R

**Sachin Pandey:** Yeah.

**Hemanth Sarabu:** actually.

**Geoff Horowitz:** I\'ll I\'ll send it to you,

**Hemanth Sarabu:** Oh,

**Geoff Horowitz:** Emma.

**Hemanth Sarabu:** you know he already shared it with

**Geoff Horowitz:** Yeah. Yeah. It was from this guy\'s video that
Satchin shared with me.

**Hemanth Sarabu:** you.

**Geoff Horowitz:** I I thought I I thought it was a pretty interesting
video, actually.

**Hemanth Sarabu:** Harder. Okay, makes sense. It\'s hurting all the
agents.

**Geoff Horowitz:** You want me to uh S should I share the new video
with him or the old

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** one?

**Hemanth Sarabu:** Wow.

**Sachin Pandey:** And you

**Hemanth Sarabu:** What is this? This is

**Geoff Horowitz:** You think the new one? Okay. I haven\'t seen the new
one yet.

### 00:37:34

**Hemanth Sarabu:** cool.

**Geoff Horowitz:** How about this is

**Sachin Pandey:** It reloads everything. So generally like these are
this side it tells the all the all the agent which I have active

**Geoff Horowitz:** what

**Hemanth Sarabu:** Wow.

**Sachin Pandey:** and like I can just click there. It is similar to
teamwork like all the key bindings work but it is also like mouse first.
So I can do editing with mouse too if

**Hemanth Sarabu:** I had to manually configure my T-Max to be mouse

**Sachin Pandey:** needed and the

**Hemanth Sarabu:** enabled.

**Sachin Pandey:** scroll is also not think of it.

**Geoff Horowitz:** Oh, scroll scroll work

**Hemanth Sarabu:** Scroll work.

**Geoff Horowitz:** session.

**Hemanth Sarabu:** You can make scroll work. It\'s just like T-Mox by
default won\'t won\'t do it.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Oh my gosh.

**Hemanth Sarabu:** You can do a lot with it.

**Geoff Horowitz:** I I was telling Sachin I\'ve been using T-Mox for
years years and I actually really like

**Hemanth Sarabu:** Man,

**Geoff Horowitz:** it.

**Hemanth Sarabu:** T-Mox was not meant to be used like vanilla, like
like Vim. You You have to You You\'re supposed to like It\'s a It\'s
like a canvas.

### 00:38:30

**Geoff Horowitz:** You\'re supposed to modify it.

**Hemanth Sarabu:** You\'re

**Geoff Horowitz:** Oh, that\'s that\'s that\'s why I never used it like
first.

**Hemanth Sarabu:** Yeah,

**Geoff Horowitz:** I only used it when I needed it because I never
modified it.

**Hemanth Sarabu:** this is cool.

**Sachin Pandey:** So it is similar like this will be the the tabs in
team access like 0 1 2 3 and

**Hemanth Sarabu:** Yeah.

**Sachin Pandey:** this is like the completely different the the groups
that we do.

**Hemanth Sarabu:** Uh that\'s like a is that like project you would
your space would be pro. So each space will have multiple tabs. Uh,

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** I see I see I see. And you can attach to this
session from like a new terminal or whatever like

**Sachin Pandey:** Yeah.

**Hemanth Sarabu:** Demox.

**Sachin Pandey:** Like you don\'t have to do like team anything like
suppose all these four files are just here. We just need to write the
herder and it will open this whole thing.

**Hemanth Sarabu:** Ah, I see.

**Sachin Pandey:** So everything inside this will be each separate tab
and similar to like similar to teams but much easier to

### 00:39:35

**Hemanth Sarabu:** Interesting. And you can name each of the sessions
and stuff. Okay. Spaces. Wow. What is What is that? What are agents? Oh,
it\'s past 10. Okay.

**Sachin Pandey:** agent this can like if I start a let\'s say new

**Hemanth Sarabu:** Yeah.

**Sachin Pandey:** a so it will appear here so if I give him a task it
will show the realtime status and if it is like blocked or need some
assistant it will like pop out the it can help you like track all the
agent which need the like permissions or

**Hemanth Sarabu:** Nice. Super cool. Maybe I should give this a shot.
I\'m afraid that if it becomes easy to do this uh my my harder session
will look like my Chrome session which is 100 tabs you know um nice okay
cool thanks for

**Geoff Horowitz:** There

**Hemanth Sarabu:** showing project you guys using some different tools
or similar tools

**Ratul Shashank:** No, I personally just use vanilla.

**Geoff Horowitz:** you

**Ratul Shashank:** Nothing

**Pratyaksh Singh:** Yeah,

**Hemanth Sarabu:** I see.

### 00:40:58

**Ratul Shashank:** specific.

**Pratyaksh Singh:** I am also I\'m also happy with testing.

**Hemanth Sarabu:** Well, you you have to use T-max at

**Pratyaksh Singh:** One few changes. Yeah. Yeah.

**Hemanth Sarabu:** least.

**Pratyaksh Singh:** So few changes I have done is that uh I I have a
shortcut which is just d and in any directory if I\'ll just press t what
happens is that what happens is that it will either open a new team of
session or it will connect to an existing team success session with the
name of the same directory right so if there are any running session it
will connect to it and then I have uh this I

**Hemanth Sarabu:** Mhm.

**Pratyaksh Singh:** don\'t know this fuzzy search right which you can
use to which you can use to you know connect to multiple which you can
just use to switch the session window and all these things.

**Hemanth Sarabu:** M

**Pratyaksh Singh:** So, uh I mean like you know I I personally don\'t
like having a lot of text and tabs, right? I mean, even in my editor,
I\'ll just have one. I I won\'t have taboo.

### 00:42:03

**Pratyaksh Singh:** So,

**Hemanth Sarabu:** I

**Pratyaksh Singh:** this this lets me focus.

**Hemanth Sarabu:** mean

**Pratyaksh Singh:** I don\'t like it.

**Hemanth Sarabu:** that makes sense.

**Pratyaksh Singh:** Like for example, the the thing that Sachin had, I
will I will just I will be I think I\'ll be less productive in that
because I will be just worrying about things going on there.

**Hemanth Sarabu:** Yeah, it is. Um, so it\'s similar for VS Code for me
where if I have too many tabs open,

**Pratyaksh Singh:** So,

**Hemanth Sarabu:** uh, it\'ll be cluttered. Um, but the nice thing
about T-Max is you can you can do control a Z and then you\'re you\'ll
you\'ll be in in that uh terminal, right? Like it\'ll be zoomed in. You
won\'t see the other stuff. Yeah. Um Yeah.

**Pratyaksh Singh:** Makes sense. The way I have my like the way I have
my editor browser

**Hemanth Sarabu:** Right.

**Pratyaksh Singh:** everything set up is all like I\'ll just have a
shortcut. For example, it\'s usually control V or control D which will
show all the tabs or the recent files that I that I added.

### 00:43:19

**Hemanth Sarabu:** Nice.

**Pratyaksh Singh:** And I think that\'s

**Hemanth Sarabu:** Nice.

**Pratyaksh Singh:** switch.

**Hemanth Sarabu:** Well, that\'s pretty cool. You should show us
sometime. Oh, actually, do you guys talk about uh the the diffusion
stuff today already? Did I invest that?

**Geoff Horowitz:** Not yet.

**Hemanth Sarabu:** Uh, have we spent some time on it?

**Geoff Horowitz:** We were talking about the Yeah.

**Hemanth Sarabu:** Or actually, Jeff, is there other uh are there other
critical items on the

**Geoff Horowitz:** No, the the most critical is getting this baseline
stuff.

**Hemanth Sarabu:** agenda?

**Geoff Horowitz:** That\'s why we jumped into it first. Um I think
Ratul,

**Hemanth Sarabu:** Got it.

**Geoff Horowitz:** you you and I are still working on the S7K. I think
Rachel, I think we I think we\'re aligned now uh through Slack and I I
think the plan is

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** uh to get something by Monday. Is that

**Ratul Shashank:** Yeah.

**Geoff Horowitz:** correct?

**Ratul Shashank:** Uh just uh just final steps are left in the
pipeline.

**Geoff Horowitz:** Okay. All right. Just ping me.

### 00:44:21

**Geoff Horowitz:** Ping me if you have additional questions or if you
want to get on a call. We can do it ad hoc.

**Ratul Shashank:** Okay. I will

**Geoff Horowitz:** Cool. Thanks. Yeah, other than that project all you

**Pratyaksh Singh:** Um I just you know finished with this few extra
just so this is the

**Geoff Horowitz:** Invisible.

**Pratyaksh Singh:** So this the experiment right uh this is on tensor
board you can you guys can access it on poly I\'ve shared the link here

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** it so you guys can access it

**Hemanth Sarabu:** Okay. Tens are bored.

**Pratyaksh Singh:** here yeah I mean

**Hemanth Sarabu:** You\'re going the way of Sid.

**Pratyaksh Singh:** uh I didn\'t want to but my epoch takes

**Hemanth Sarabu:** It\'s fine. It\'s fine. Oh.

**Pratyaksh Singh:** 2 minutes no I I wanted to tell the reason my epoch
takes 2 minute and then logging the model

**Hemanth Sarabu:** Oh.

**Pratyaksh Singh:** and logging all images and more of images I wanted
to it takes around 3 minutes and after some epox like for consistency
clear ML stops and just focuses the problem so that\'s why I

### 00:45:42

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** used so uh these are

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** basically I think I discussed how I was able to set
up the fine tune version of the model because I wasn\'t able

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** to find a effective model for it which can which
which can do both image transitioning as well as store I\'m searching
for it and I think flux flux

**Hemanth Sarabu:** Really?

**Pratyaksh Singh:** can I will set it up we will set it up this was
easy and

**Hemanth Sarabu:** Okay. Okay.

**Pratyaksh Singh:** then to get the results I I ran it on all the 5
GPUs of so these images here these are these

**Hemanth Sarabu:** So, training ran training ran on 5GPs of Wally.

**Pratyaksh Singh:** Yeah,

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** running uh training ran on 5G of it\'s still
running and I so every 20 epochs it logs these images from the latest
model. So what you see here the images that it logs is the first
conditioning based on the data set and then on the mask right on each of
the mask. So let\'s say class one mask it will it will present an image
class two mask at 12 for class three mask it will and for class four it
will for class which if you want I

### 00:47:04

**Hemanth Sarabu:** So sorry, sorry. Hold on. Hold on.

**Pratyaksh Singh:** can

**Hemanth Sarabu:** Can you Sorry. Can you start over just in in words?
Can you tell us what is going on before showing

**Pratyaksh Singh:** okay yeah I

**Hemanth Sarabu:** it?

**Pratyaksh Singh:** wanted to so uh every 20 images are logged on
tensorboard for visualization And these are the images.

**Hemanth Sarabu:** Okay. Okay.

**Pratyaksh Singh:** The images are logged for based on data set
conditioning and then based on

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** mass conditioning for each of the classes where
classes are AOI small, AOI big, mines and all these classes. And these
are the images here,

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** right?

**Hemanth Sarabu:** So there are two conditioning variables which is the
data set and the

**Pratyaksh Singh:** The

**Hemanth Sarabu:** target. Is that right?

**Pratyaksh Singh:** Yes.

**Hemanth Sarabu:** Okay. Is that right?

**Pratyaksh Singh:** Uh one is data set.

**Hemanth Sarabu:** Two conditioning variables.

**Pratyaksh Singh:** Yeah. And one is a yeah two. is the data set and
another is the target box.

### 00:48:01

**Pratyaksh Singh:** So in these images what you\'ll see is the initial
noise that it started with which I don\'t think is

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** relevant the mask that was used and then finally
the generated

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** image. Now uh so the high level summary is

**Hemanth Sarabu:** Okay. Right.

**Pratyaksh Singh:** that the high level summary is that unconditional

**Hemanth Sarabu:** Show us the money.

**Pratyaksh Singh:** generation sorry when it is only conditioned on the
data set it performs very well but when you start to condition it on
mass

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** what happens is that so I will share you one
example which will make things more clear. So POE data set the port of
iceberg didn\'t have any point of contact any area of interest sorry
right so when you will see the

**Hemanth Sarabu:** M.

**Pratyaksh Singh:** unconditional generation data of port of iceberg it
looks something like that it looks something it looks like that data let
me just run a new tab so you see these these kind of marks those are
available in that data So it kinds of look like that data set but when
you condition it

### 00:49:11

**Hemanth Sarabu:** Mhm.

**Pratyaksh Singh:** on some class labels right so for example let\'s
say when you condition it on class one it won\'t you know it doesn\'t
generate the data set like that because there is no data in the training
set where there is conditioning but the good thing that I see here is
that for

**Hemanth Sarabu:** Let me ask you this.

**Pratyaksh Singh:** some

**Hemanth Sarabu:** Go ahead and finish your thought.

**Pratyaksh Singh:** Okay. So my my plan was that if I train a model
like this, what I could do on both of I square data set, I could
condition on this mask and then it will generate annotations for that
for those data set. But those don\'t seem to happen. It just it will
sample from another distribution where it is not where it\'s where it\'s
not even part of the data set. There are some positives like these
examples here where you know where

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** things may be may be better.

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** Another thing is that similarly since we have
didn\'t have a lot

### 00:50:13

**Hemanth Sarabu:** So, wait. Okay. So, sorry Pra.

**Pratyaksh Singh:** of

**Hemanth Sarabu:** what works, what doesn\'t work. And if you if you
had to say that is it uh data set conditioning works uh condition on
data set and target if there is no example of uh target in that data set
it doesn\'t work.

**Pratyaksh Singh:** It doesn\'t and also if there are not there is

**Hemanth Sarabu:** Is that it? Are there any more insights?

**Pratyaksh Singh:** one more thing so for target let\'s say mines right
there there

**Hemanth Sarabu:** H.

**Pratyaksh Singh:** weren\'t much data set with mines I think there
were only four or five examples so for mines also it doesn\'t

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** do a good job. That\'s something that I was these
other things. But I\'m going to keep it. So I\'m going to keep it
running. I will see I\'ll see what happens. One thing I think we can
certainly do is we can generate a

**Hemanth Sarabu:** Oh.

**Pratyaksh Singh:** lot of data like this. We can have QC by the labels
and then we can feed it.

### 00:51:23

**Pratyaksh Singh:** I didn\'t really good good kind of data data set
that that I wear the

**Hemanth Sarabu:** Yeah. Yeah, let\'s do it.

**Pratyaksh Singh:** mask which I think will be

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** faster.

**Hemanth Sarabu:** Okay. So, a couple of questions. One question is um
couple of questions.

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** One is you\'re jointly generating baseline. So,
you\'re conditioning on bas uh data set and um target in a joint fashion
in a one shot or one stage.

**Pratyaksh Singh:** Yes.

**Hemanth Sarabu:** Right? So thought one thought is what happens when
you make it two- stage you train you train it to be somewhat two-stage
as in maybe that is

**Pratyaksh Singh:** Yes.

**Hemanth Sarabu:** yeah let\'s let\'s say it\'s two-stage because there
are in there are like these tools for inpainting and things like that
where the background is fixed and wherever you inp it its job is to make
the object work with the background. around right so there\'s a lot of
work in in painting where you don\'t jointly generate joint generation
is a is a more diff it\'s a more difficult distribution I think to learn
for our case than than uh than like a two-stage

### 00:52:39

**Pratyaksh Singh:** So so from what I know what people do in painting
is They will like you know instead of noising the whole image they will
only noise the mask that you do and they will train it to only generate
for this mask.

**Hemanth Sarabu:** Mhm.

**Pratyaksh Singh:** But the thing with them is that have you know that
training data right they

**Hemanth Sarabu:** Correct.

**Pratyaksh Singh:** will have before and after data

**Hemanth Sarabu:** Yeah,

**Pratyaksh Singh:** it\'s fine I I

**Hemanth Sarabu:** you\'re right. You you you still need correct the
you\'re the problem you\'re bringing up is for this for this pair the P
the POE uh POE and target data doesn\'t exist, right? The problem still
exists. That problem is still valid. Yes.

**Pratyaksh Singh:** No,

**Hemanth Sarabu:** Um

**Pratyaksh Singh:** I think I think what I can do is I can do something
like this. Wherever there is mask I can noise that mask and then I can d
noiseise it to to you know generate those artifacts right so instead of
like I\'m having a channel I can I can do something like

### 00:53:48

**Hemanth Sarabu:** correct. Exactly.

**Pratyaksh Singh:** this and I can train it on VW I can run it on VW
and then DRN data set or whatever data set that I I can try it on POE
and see if it generalizes to

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** PU. If it doesn\'t, if it doesn\'t.

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** And uh for another thing uh what I did was 20% of
the

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** time I wasn\'t conditioning on the data set.

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** So these last images the generation unconditional
these are when you don\'t condition on the data set. So you know it can
generate any of the any random So these are some examples of but I think
I can do I will set up something like

**Hemanth Sarabu:** Nice.

**Pratyaksh Singh:** this. So let it rain. I think I it is been running
for 16 or now I can try something like see if that works.

**Hemanth Sarabu:** You guys using the black well.

**Pratyaksh Singh:** I am not using the blackwell. I think black will is
being used for running all these AI apart from

### 00:55:04

**Hemanth Sarabu:** Okay. Um Jeff, uh if we want to get a new GPU, now
is the time. It\'s the prices are going up. Um, but I would also have to
figure out I\'ll have to bring Ninja down and see if how to get it to
work with uh to black holes, which is not impossible, but I think it
needs some fiddling around.

**Geoff Horowitz:** Uh, let\'s Can we talk about it tonight or
something?

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** Do you guys do you guys think we need more compute
project?

**Pratyaksh Singh:** right now I don\'t know right now right now I
don\'t know the reason for it is because they\'re training a very simple
unit model right so that doesn\'t require a lot of GPU but when you

**Hemanth Sarabu:** So what I\'m hearing Pat is right now you\'re
training just one model when you could be training multiple models. I
don\'t think it\'s even a joke.

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** It\'s not even a joke.

**Pratyaksh Singh:** Yeah. Yeah.

**Hemanth Sarabu:** Um, yeah,

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** we we could be running more

### 00:56:34

**Sachin Pandey:** You also

**Hemanth Sarabu:** experiments.

**Pratyaksh Singh:** Yeah.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Come on. Let\'s talk about it

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** tonight.

**Hemanth Sarabu:** Okay, I got to drop. Um, so for the So, Okay, I
gotta go. Shrier wants to

**Geoff Horowitz:** Ham Ham.

**Hemanth Sarabu:** talk.

**Geoff Horowitz:** Uh, don\'t forget to look at that Teladine thing
that I sent you.

**Hemanth Sarabu:** Yeah, yeah, yeah. Okay.

**Geoff Horowitz:** All right.

**Hemanth Sarabu:** All right, guys. Bye-bye. Thanks,

**Geoff Horowitz:** All right.

**Hemanth Sarabu:** brother. You should you should uh host like an app
that allow people to generate and play with this.

**Pratyaksh Singh:** Huh?

**Hemanth Sarabu:** Okay. All right.

**Pratyaksh Singh:** Yeah,

**Hemanth Sarabu:** Cut it up. Bye.

**Pratyaksh Singh:** that that can

**Geoff Horowitz:** Right.

**Hemanth Sarabu:** Okay. Nice.

**Geoff Horowitz:** Uh, all right guys. So, projects, do you need any
additional input from us right now for like next

**Pratyaksh Singh:** No, I don\'t need any input.

**Geoff Horowitz:** steps?

**Pratyaksh Singh:** I think but I think you know we\'ll have to we\'ll
have to do some synthetic data generation that\'s not based on the fus

### 00:58:00

**Geoff Horowitz:** Yeah. which which was the plan anyway.

**Pratyaksh Singh:** yeah you know this this this worked quite well I
wasn\'t expecting it to

**Geoff Horowitz:** Yeah.

**Pratyaksh Singh:** work this so I\'m I\'m

**Geoff Horowitz:** Yeah. So,

**Pratyaksh Singh:** surprised

**Geoff Horowitz:** so I mean this, you know, this is the same thing we
spoke about when we were planning this out is like good now, now we have
something that we think maybe works and then we\'ll go through we\'ll
start with the easiest stuff and once we once we get

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** to this point at least we at least we have, you
know, some idea of how we can start improving it and uh you know
eventually getting to the goal.

**Pratyaksh Singh:** Yeah. Yeah.

**Geoff Horowitz:** I

**Pratyaksh Singh:** At least I was saying at least with this we can
generate a lot of backgrounds to make the model robust. There\'s

**Geoff Horowitz:** Okay. Uh, all right. Anything else? Anybody else
wants to bring up

**Ratul Shashank:** uh regarding the synthetic data uh predict asked me
to look into comfy UI uh to find a way to like generate uh data on that.

### 00:59:11

**Ratul Shashank:** So I wanted to ask like what are we looking for uh
in synthetic data? What are the prime uh principles that we want to be
in that?

**Pratyaksh Singh:** Hey, so rul for synthetic data we want to generate
new backgrounds right so some variation in the background so that our
model can be

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** robust to to the new data that that it\'s evaluated
on those

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** thing we want to do another thing is that similar
to background for contacts also, right? I want to generate new cortex
which look like so for example it\'s a P data it doesn\'t have any
contact right so we want to generate synthetic contact on that data set
so that context and data set like those it is it is able to declare

**Ratul Shashank:** So uh like I let me show my screen.

**Pratyaksh Singh:** also

**Ratul Shashank:** I was trying something similar on company UI. Uh
just my screen visible.

**Pratyaksh Singh:** Yes, it

**Ratul Shashank:** So like these are all the images that I generated
from

**Pratyaksh Singh:** is.

### 01:00:41

**Ratul Shashank:** comi and uh huh and I have also shared a folder in
bedrock channel.

**Pratyaksh Singh:** Okay.

**Ratul Shashank:** So what I uh what I did was I used three workflows.
One workflow is just basic uh comfy UI node like I I\'m using Z image
turbo as my base model and I\'m just denoising it like reducing the
noise and adding random speed to it and I\'m getting the value. That is
one workflow. Another workflow is uh I\'m creating a binary image of
like for this uh sorry this is a generated uh this is not a real uh POE
data set. This is this was generated by comfy UI.

**Pratyaksh Singh:** How you

**Ratul Shashank:** So what I did was I uh first created a binary

**Pratyaksh Singh:** doing?

**Ratul Shashank:** image on the actual data. I created a background for
that uh using the Z image turbo and I just superimposed both of them uh
onto each other. So uh because my reasoning was I wanted the image to
retain as much feature of the original data set as possible but also to
have certain variations.

### 01:02:21

**Ratul Shashank:** So to give you a visual example, I have also
downloaded

**Pratyaksh Singh:** Okay.

**Ratul Shashank:** some. Yeah, let\'s look for DRN. So these are uh for
uh these are different seeds seed generation for the same data set. For
each image generation I am using uh three different seed values. So this
is for one uh seed input. This is for another and this is for another.
All of these are uh using the same base image

**Pratyaksh Singh:** Roger.

**Ratul Shashank:** as the input. I\'m just changing the seed and uh how
they are generating backgrounds. And we can also change

**Pratyaksh Singh:** Got can you please make a dot for it and then

**Ratul Shashank:** uh

**Pratyaksh Singh:** note down the transformations that you\'re using
the image model and everything.

**Ratul Shashank:** yes I uh I\'m

**Pratyaksh Singh:** Did you share this talk with

**Ratul Shashank:** I am like I am in the process of figuring this out

**Pratyaksh Singh:** me?

**Ratul Shashank:** like what are the nitty-g gritties of it. So that is
why I\'m not I don\'t think I should but I can share it like it\'s a
preliminary dog.

### 01:03:48

**Ratul Shashank:** I mean this is it\'s that is why I don\'t I have not
shared it but I will if you want

**Pratyaksh Singh:** Okay. Yes.

**Ratul Shashank:** to.

**Pratyaksh Singh:** Uh and can you please add some images also? image
image of your workflow. So, for example, open your workflow, right? Open
your workflow,

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** right? So, I want to see the I want to I want to
you know I want to understand the workflow like what each of the
transformation do for example just open your open your workflow not this
page the with the graph

**Ratul Shashank:** Uh I\'m not using the graph right now because uh
like do

**Pratyaksh Singh:** right?

**Ratul Shashank:** you are you talking about this one because I\'m not
using any graph.

**Pratyaksh Singh:** Yeah. Yeah,

**Ratul Shashank:** Oh yeah.

**Pratyaksh Singh:** this this this graph I was saying that you know so

**Ratul Shashank:** Okay. Mhm.

**Pratyaksh Singh:** this graph is generating the images right. So first
paste an image of this graph and then if possible show you know what
transformation each of these are doing because it it it will be

### 01:04:48

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** much easier to understand and you see things

**Ratul Shashank:** Yeah. I at this point uh uh at this point I have
segregated that uh I will

**Pratyaksh Singh:** better.

**Ratul Shashank:** share that with you like uh I have segregated that
for three uh workflows.

**Pratyaksh Singh:** Okay.

**Ratul Shashank:** Uh the this one is just uh the v1 row is just
basically this one. the V1 composited is the one that I sh uh that I
talked about. I will compile all of them in a report and I will share
that with you.

**Pratyaksh Singh:** Yeah, in that report also like past paste images
also right what graph was used and then what

**Ratul Shashank:** Uh

**Pratyaksh Singh:** transformation that it did to the image and all
those things.

**Ratul Shashank:** okay, I will I will. So, okay. So I mean that was
just uh like I wanted to share that.

**Pratyaksh Singh:** that it looks good like it can it does minor
distortion in the images which which can be robust.

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** I want to see if you know if those can be added as
augmentation to the augmentation to the data you know if they\'re if
they\'re fast and simple I\'ll see if those can be added as oblation to
the training.

### 01:06:02

**Pratyaksh Singh:** And another thing is that

**Ratul Shashank:** That is that is uh one uh like I was also just
adding that that that is also my thought process

**Pratyaksh Singh:** no

**Ratul Shashank:** like uh to figure out like uh how to um minimize
this uh noise and and all that like that was also because uh it\'s not
finished

**Pratyaksh Singh:** Okay.

**Ratul Shashank:** yet.

**Pratyaksh Singh:** Yeah. And so yeah, just put it in the dock. And
then one thing I also would like you to try out is that see if you can
generate the contacts like you can use a mask

**Ratul Shashank:** Aha yes I I uh I have also generated the proper
contacts like uh

**Pratyaksh Singh:** to

**Ratul Shashank:** I use the mask that I created and uh I just super
impose those contacts like if uh let me show you uh for it I it\'s it\'s
not showing with the mask on but in this image it is it has the contact
superimposed on a background. So my logic was if I just use uh if I just
superimpose the contact on a different background so that contact with
like not just contact but contact along with a certain pixel a certain
uh box.

### 01:07:30

**Ratul Shashank:** So the feature is carried out but the background is
changed. That was my

**Pratyaksh Singh:** Got it. Got it.

**Ratul Shashank:** reason.

**Pratyaksh Singh:** Can you can you you know can you for this can you
also add this into the doc and there also show what kind of
transformation that you do and then also add some example of the

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** original image the raw image and the mask that you
use and the and you know

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** whatever was input to the model and then what was
the output

**Ratul Shashank:** Okay. I will I will uh and and just for uh just for
preliminary purpose like uh I will uh I in this message I have given uh
like the original image how it looks and the generations that uh I am
doing. This was for one workflow.

**Pratyaksh Singh:** Uh-huh.

**Ratul Shashank:** This was for another and this was for the third one.
I will compile everything in the doc and I will should I share it with
you or in the channel my

### 01:08:31

**Pratyaksh Singh:** Yeah. No, share it with the team.

**Ratul Shashank:** channel okay

**Pratyaksh Singh:** Share it with the channel. I think I think that
will that will make things work. Yeah.

**Ratul Shashank:** okay

**Pratyaksh Singh:** I would I would like you know if you I would rather
have you communicating in the group than in personal DM because then you
know more people can give

**Geoff Horowitz:** I agree.

**Ratul Shashank:** got it

**Geoff Horowitz:** I\'m interested in seeing this stuff, too. So,

**Ratul Shashank:** Okay, I will share the new report in the channel.

**Pratyaksh Singh:** What?

**Geoff Horowitz:** uh the very last thing, Rachel, we we talked about
this briefly. Um but we\'ve just got a lot of information out there on
drive and I don\'t know a lot of like tribal knowledge going on. Um this
is this is not high priority virtual.

**Ratul Shashank:** Yeah.

**Geoff Horowitz:** This is lower than kind of all the other things that
we\'re doing. But I am interested in your ideas about how we can like
this is a ton of data, right?

### 01:09:42

**Geoff Horowitz:** So how can we um how can we

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** best synthesize this data into you know some like
cresser knowledge base?

**Ratul Shashank:** Uh, I go

**Geoff Horowitz:** Um I I\'ll even add to that we we record every
single

**Ratul Shashank:** on.

**Geoff Horowitz:** meeting we do right so like we\'ve got all this like
discussion that oftentimes doesn\'t

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** even get written down. Um,

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** but there\'s just there\'s a ton a ton a ton of
data. So, yeah, I\'m interested in the thoughts there, too.

**Ratul Shashank:** Yeah. So, uh when we uh had that meeting,

**Geoff Horowitz:** Um,

**Ratul Shashank:** when I shared my workflow, I uh I kind of like
created uh like a plan in my head

**Geoff Horowitz:** okay,

**Ratul Shashank:** what we can do for uh like uh like what I talked
about an agentic

**Geoff Horowitz:** great.

**Ratul Shashank:** OS for the forresser.

**Geoff Horowitz:** Yeah.

**Ratul Shashank:** So uh it\'s not very difficult like the agents can
be deployed very easily and and and even I have I had thought for the
meetings and the tri and the transcriptions like we can have a separate
agent to uh like dedicated for reading the transcripts.

### 01:10:59

**Ratul Shashank:** We can even deploy an agent to record the meetings
and create notes. We can have an agent for creating a bun boards and
share sharing that with uh you and him so that you would have a visual
representation of what everything is going on the we can extract from
the transcription uh

**Geoff Horowitz:** right?

**Ratul Shashank:** like what the task is h is handed down to any and
everybody else like that is easy stuff the hard problem is like I mean
we can\'t trust these agents, right?

**Geoff Horowitz:** All

**Ratul Shashank:** Uh so the uh in in my opinion these agents

**Geoff Horowitz:** right,

**Ratul Shashank:** should be running in a dockerized container or if
not that uh like these should be on a tight leash in any way possible.

**Geoff Horowitz:** Rachel, I I I agree with you. I I I love this line
of thinking. I uh but I I do need to run. Um so I I don\'t want to have
this complete conversation now,

**Ratul Shashank:** Okay.

**Geoff Horowitz:** but uh I I I really like this line of thinking. Um
same thing, you know, that we talked about before.

### 01:12:13

**Geoff Horowitz:** When you find yourself with some free time,

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** I\'d love it if you could kind of write down some of
these thoughts, considerations, um you know, risks, uh um you know,

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** requirements, things like that. Um, and then I think
that\'ll give us a good starting point to have a fuller discussion about
it. Does that work?

**Ratul Shashank:** I will I will compile a report uh like a PRD kind of
report and I will share it with

**Geoff Horowitz:** Yeah.

**Ratul Shashank:** you.

**Geoff Horowitz:** Cool.

**Ratul Shashank:** Sorry you you asked me to share it in the compute
channel right?

**Geoff Horowitz:** I did. Yeah.

**Ratul Shashank:** Uh I will I will share that uh PRD report in the
compute

**Geoff Horowitz:** Yeah.

**Ratul Shashank:** channel.

**Geoff Horowitz:** Great. Okay. All right. Anything?

**Ratul Shashank:** topic.

**Geoff Horowitz:** Anything else

**Ratul Shashank:** Not at the moment.

**Geoff Horowitz:** urgent?

**Ratul Shashank:** Uh uh Jeff uh I forgot uh did you had the chance to
look at the mag report like uh the latest one that I shared

### 01:13:15

**Geoff Horowitz:** The one. Uh, I might have

**Ratul Shashank:** uh like uh in the MA report uh like my question was
is this kind of data analysis is this close to what bedrock was doing.
The report is also in the EDA folder

**Geoff Horowitz:** Oh, this is this is the one that was in the meeting.

**Ratul Shashank:** uh

**Geoff Horowitz:** Uh I I lost that thread. I lost that thread, but I
will um I\'ll try to go back and look

**Ratul Shashank:** uh I will I will share it.

**Geoff Horowitz:** at

**Ratul Shashank:** I will uh you can also find it in the uh folder EDF
folder but I can also share it with in the bedrock channel I shared it
in the

**Geoff Horowitz:** I I think you did, didn\'t you?

**Ratul Shashank:** thread of uh when you uh

**Geoff Horowitz:** In the thread. I see what you\'re saying. Okay. You
should also, RTL, I want to I want to empower you to, you know, if
you\'re waiting on like if you\'re waiting on, you know, information
from me and I don\'t get back to you, you know, bump at me in in a in a
thread to wherever wherever the information should be.

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** Like, you should feel uh you should feel empowered
to to follow up and, you know,

**Ratul Shashank:** Okay, that makes sense.

**Geoff Horowitz:** All right. Okay. I\'m I\'m really sorry. I do need
to run. Um but uh thanks for the discussion, guys. Um have a great
weekend. Uh you know, I\'m around if anybody needs anything, so Okay.
Bye, guys.

**Ratul Shashank:** Bye.

### Transcription ended after 01:16:20

*This editable transcript was computer generated and might contain
errors. People can also change the text after it was created.*
