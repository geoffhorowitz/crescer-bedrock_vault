Jul 8, 2026

## Iris Sync

Invited [[Sachin Pandey]{.underline}](mailto:sachin@crescer.ai)
[[Pratyaksh Singh]{.underline}](mailto:pratyaksh@crescer.ai) [[Niveta
Iyer]{.underline}](mailto:niveta@crescer.ai) [[Hemanth
Sarabu]{.underline}](mailto:hemanth@crescer.ai) [[Geoff
Horowitz]{.underline}](mailto:geoff@crescer.ai) [[Siddharth
Soni]{.underline}](mailto:siddharth@crescer.ai) [[Ratul
Shashank]{.underline}](mailto:ratul@crescer.ai)

Attachments [[Iris
Sync]{.underline}](https://calendar.google.com/calendar/event?eid=NnNzMHVxNzk3MmJqZGVwNXFoN2J1Mjd1OTdfMjAyNjA3MDhUMTYzMDAwWiBnZW9mZkBjcmVzY2VyLmFp)

Meeting records
[[Transcript]{.underline}](https://docs.google.com/document/d/1B4pXv5XEtTpw1LgOPNNTOYEAoqWxy9MuW5sLSWU8Pok/edit?usp=drive_web&tab=t.muo3vc6aylxj)
[[Recording]{.underline}](https://drive.google.com/file/d/1xGT2DPmqfyHqDoT-qPX4_DhUtjVbV8f_/view?usp=drive_web)

### Summary

Technical discussions on pipeline standardization and model architecture
optimization aligned with data training and evaluation strategies.\
\
**Pipeline and Data Training**\
The team reviewed pipeline documentation and initiated multi-class and
binary model training. The team agreed to create a geographically
distinct test set to improve evaluation accuracy.\
\
**Diffusion Model Strategy**\
Engineers are preparing data for a 256 by 256 patch U-Net model.
Implementation of Comfy User Interface and Low-Rank Adaptation will
proceed in parallel with training.\
\
**Classification Model Finalization**\
The team debated technical performance issues including data frequency
and model variance. A formal decision was made to finalize the
classification structure between binary and multi-class outputs.

### Decisions

Needs Further Discussion

-   **Target class requirements clarification** The project requires
    > further clarification regarding whether the model output should be
    > multiclass or single-class, necessitating a follow-up inquiry on
    > Slack.

Aligned

-   **Open source data excluded from training** The open source data set
    > is excluded from the current training pipeline to ensure alignment
    > with the processed data distributions.

-   **VW data set for model comparison** The comparison between the new
    > model and the legacy model is restricted to the VW training data
    > set to ensure accurate ground truth validation.

-   **Geographically distinct test set implementation** The test set
    > creation strategy is modified to prioritize geographically
    > distinct areas based on geo-referencing, rather than random
    > selection, to prevent data leakage.

-   **Dual training approach for diffusion models** The team will
    > execute parallel training efforts for the diffusion model,
    > utilizing both training from scratch and fine-tuning with LoRA to
    > determine the optimal approach.

We\'ve **updated the Decisions section** using your feedback.

Let us know what you think:
[[Helpful]{.underline}](https://google.qualtrics.com/jfe/form/SV_5p6FWBVWvynleNU?isGoogler=no&isHelpful=yes)
or [[Not
Helpful]{.underline}](https://google.qualtrics.com/jfe/form/SV_5p6FWBVWvynleNU?isGoogler=no&isHelpful=no)

### Next steps

-   \[Sachin Pandey\] Share Model Data: Post the model summary
    > information including paths and metrics to the shared location.

    > \[Sachin Pandey\] Create Test Set: Create a geographically
    > distinct test set to prevent training data overlap during model
    > evaluation.

    > \[Sachin Pandey\] Clarify Class Requirement: Post a question on
    > Slack to clarify with the client whether they require multiclass
    > or single-class detection for the new data.

    > \[Pratyaksh Singh, Ratul Shashank\] Train Diffusion Models: Set up
    > model training using both a scratch-built approach and the LoRA
    > finetuning method to compare performance.

    > \[Sachin Pandey\] Investigate Model: Investigate the mixed data
    > variation and hypothesis. Confirm the multiclass classification
    > logic.

### Details

-   **IIC North America Pipeline**: Geoff Horowitz requests that Ratul
    > Shashank review comments on a specific pipeline document for the
    > IIC North America client. There are previous \"last files\"
    > available to use for comparison, and Sachin Pandey is available to
    > assist Ratul Shashank in locating these files if needed
    > ([[00:01:12]{.underline}](#section)). The team agrees to
    > coordinate later to discuss their shared understanding of the
    > pipeline ([[00:06:38]{.underline}](#section-1)).

-   **Diffusion Model Data Preparation**: Pratyaksh Singh and Ratul
    > Shashank are working on preparing data for a diffusion model. They
    > plan to begin with a simple U-Net model to establish a baseline
    > before considering a Diffusion and Transformer model if necessary
    > ([[00:08:02]{.underline}](#section-2)).

-   **Pipeline Training Status**: Sachin Pandey is currently training
    > two models using the old pipeline: one multi-class model and one
    > binary model. They have included a port dataset as a background
    > dataset, although it currently lacks annotations
    > ([[00:08:53]{.underline}](#section-3)).

-   **Dataset Inclusion Strategy**: Geoff Horowitz discusses the
    > potential benefits of adding open-source datasets to help the
    > model generalize, noting that they should revisit this possibility
    > later. Currently, the team is not including open-source data in
    > the active training ([[00:10:20]{.underline}](#section-4)).

-   **Model Performance Metrics**: Sachin Pandey notes that the binary
    > model is currently not performing as well as expected compared to
    > the multi-class model. Geoff Horowitz observes in the training
    > logs that the loss is rising, and Sachin Pandey intends to examine
    > the predictions on the test set once training is complete to
    > investigate further ([[00:13:10]{.underline}](#section-6)).

-   **Sharing Model Reports**: Sachin Pandey agrees to post the current
    > training reports, which are in Markdown format, to a shared
    > location so that the team can access the model information,
    > metrics, and training paths
    > ([[00:14:27]{.underline}](#section-7)).

-   **Model Comparison Strategy**: To compare the new model with the
    > older version, the team will use the VW data test set, as the old
    > model was not trained on the new datasets
    > ([[00:15:29]{.underline}](#section-8)). Geoff Horowitz emphasizes
    > the importance of comparing standard metrics such as recall,
    > precision, and F1 scores ([[00:18:13]{.underline}](#section-10)).

-   **Test Set Selection**: Geoff Horowitz raises concerns that the
    > current random selection process for the test set might lead to
    > geographic overlap with the training data
    > ([[00:23:27]{.underline}](#section-14)). Sachin Pandey agrees to
    > create a new, geographically distinct test set to ensure the model
    > is tested on data that was not used during training
    > ([[00:25:35]{.underline}](#section-15))
    > ([[00:30:01]{.underline}](#section-18)).

-   **Handling Non-Annotated Data**: Geoff Horowitz suggests that the
    > port dataset, which was not used in the training set for the old
    > model, could be utilized as a test set to assess performance on
    > varied backgrounds and monitor false positives
    > ([[00:25:35]{.underline}](#section-15)).

-   **ML Intern Pipeline Progress**: Sachin Pandey confirms that the
    > team will continue with the U-Net model training while maintaining
    > the option to compare its final results against the output from
    > the ML intern pipeline and the old legacy pipeline
    > ([[00:31:05]{.underline}](#section-19)).

-   **Target Class Clarification**: There is a discussion regarding
    > whether the client requires multi-class or single-class output
    > ([[00:32:43]{.underline}](#section-20)). Hemanth Sarabu advises
    > Sachin Pandey to clarify this requirement on Slack, noting that
    > while the original request for the VW dataset was for a single
    > class, they must ensure they are meeting current contract
    > specifications ([[00:35:10]{.underline}](#section-21)).

-   **Challenges with Mine Data**: Pratyaksh Singh reports difficulty in
    > identifying mines, noting that they have limited, small, and
    > varied annotations, which makes it challenging to achieve
    > consistent identification across images
    > ([[00:36:40]{.underline}](#section-22)).

-   **Diffusion Model Architecture**: Pratyaksh Singh outlines the
    > technical strategy for the diffusion model: stacking port and
    > starboard images (removing the water surface gap), creating
    > 256x256 patches, and using a U-Net conditioned on both the mask
    > and the dataset to generate contact images
    > ([[00:36:40]{.underline}](#section-22)).

-   **Fine-tuning and Optimization Recommendation**: Hemanth Sarabu
    > recommends using existing open-source workflows, such as Comfy UI
    > and Low-Rank Adaptation, for fine-tuning instead of training from
    > scratch to achieve faster results
    > ([[00:41:44]{.underline}](#section-25)). Pratyaksh Singh agrees to
    > pursue this approach in parallel with training from scratch
    > ([[00:48:49]{.underline}](#section-30)).

-   **Parallel Augmentation Strategy**: Pratyaksh Singh intends to
    > explore generating data as augmentations in parallel to the
    > diffusion model training, as the generative model might default to
    > producing the most probable images without sufficient conditioning
    > ([[00:48:49]{.underline}](#section-30)).

-   **Mixed Data and Model Variation**: Ratul Shashank and Sachin Pandey
    > identify the primary technical issues as low frequency and mixed
    > data within the model. They discuss the possibility of
    > hypothesis-based errors and examine \"type variation batch,\"
    > alongside potential issues with the model\'s random learning
    > process ([[00:54:00]{.underline}](#section-32)).

-   **Learning Rate and Model Metrics**: The discussion moves to
    > performance monitoring, where Sachin Pandey mentions a rate of
    > \"85 cash per second\" and suggests a change to the \"point
    > learning rate\". They evaluate the model\'s performance,
    > specifically analyzing \"False Positive\" results and the
    > \"negative area\" ([[00:54:00]{.underline}](#section-32)).

-   **Selection of Classification Model Type**: Ratul Shashank and
    > Sachin Pandey debate the appropriate structure for the
    > classification model, specifically deciding between a binary model
    > or a multiclass model. They discuss existing smoothness in the
    > model and address input ground truth requirements, questioning
    > whether the output should be multiclass or single class. The
    > conversation concludes with a focus on whether the prediction unit
    > should be binary or multiclass
    > ([[00:54:00]{.underline}](#section-32)).

*You should review Gemini\'s notes to make sure they\'re accurate. [[Get
tips and learn how Gemini takes
notes]{.underline}](https://support.google.com/meet/answer/14754931)*

*How is the quality of **these specific notes?** [[Take a short
survey]{.underline}](https://google.qualtrics.com/jfe/form/SV_9vK3UZEaIQKKE7A?confid=Xft-Qp3gyf7j8bBdMvj1DxIUOAIIigIgABgECA&detailid=standard&screenshot=false)
to let us know your feedback, including how helpful the notes were for
your needs.*

**📖 Transcript**

Jul 8, 2026

## Iris Sync - Transcript

### 00:01:12

**Ratul Shashank:** Searching for

**Sachin Pandey:** Hello. Um,

**Ratul Shashank:** It\'s just very for

**Sachin Pandey:** wait.

**Geoff Horowitz:** Hi guys.

**Sachin Pandey:** Exactly.

**Geoff Horowitz:** Um,

**Sachin Pandey:** CL

**Geoff Horowitz:** Rick Tulle, I have a hard stop in 30 minutes today.
So, I I I don\'t think we should talk about the S7K stuff,

**Sachin Pandey:** Eyes very

**Geoff Horowitz:** but I want to bring up one one point quickly.

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** Did you have a chance to look at my comments on that
document?

**Ratul Shashank:** Um yeah, I I

**Geoff Horowitz:** Okay. Um, so I just want to clarify that for that
specific pipeline,

**Ratul Shashank:** hand.

**Geoff Horowitz:** we\'re actually looking at a different client. It\'s
IIC North America. Um, for that client, we already have last files that
we should be able to compare against.

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** Um, and if you need help looking for those files,
Suction should be able to to guide you.

**Ratul Shashank:** Okay. I I I also have a question I will ask you
separately. Uh regarding this um I I have looked into the files.

### 00:06:38

**Geoff Horowitz:** Okay.

**Ratul Shashank:** So that is the

**Geoff Horowitz:** Okay. Great. Great. We can we can connect um either
what you I don\'t know.

**Ratul Shashank:** question.

**Geoff Horowitz:** Do you do you have the same schedule as Sachin? Uh
I\'ll be free in in a few hours. uh we can either connect later today
for me um early tomorrow for you or uh I can connect you know in in
about 24 hours too if that\'s

**Ratul Shashank:** Uh so I I can also do that.

**Geoff Horowitz:** better.

**Ratul Shashank:** uh I can uh like I can just give you a text on slack
regarding the basic understanding that I have and you uh you understand
that and if uh we can then we can just hop on the call and sort this

**Geoff Horowitz:** Sure,

**Ratul Shashank:** out.

**Geoff Horowitz:** that works too.

**Ratul Shashank:** Okay.

**Geoff Horowitz:** Okay, great. Okay. Um, so Son, I think I think I
want to spend most of the time talking about um the baseline
performance. Uh but before we do that project, anything you want to
discuss about um the diffusion data.

### 00:08:02

**Pratyaksh Singh:** No, nothing. Uh me and Rasul are working on getting
the data ready.

**Geoff Horowitz:** Okay.

**Pratyaksh Singh:** As soon as I have the result,

**Geoff Horowitz:** Nice.

**Pratyaksh Singh:** I will share it with

**Geoff Horowitz:** Nice.

**Pratyaksh Singh:** you.

**Geoff Horowitz:** Nice. What uh what model are you guys working with?

**Pratyaksh Singh:** Uh I\'m going to start with uh simple a unit based
model

**Geoff Horowitz:** Can you spell

**Pratyaksh Singh:** right because this is the first

**Geoff Horowitz:** it?

**Pratyaksh Singh:** time.

**Geoff Horowitz:** Can you Yeah.

**Pratyaksh Singh:** Hello.

**Geoff Horowitz:** Can you Can you spell it? I couldn\'t hear the name.

**Pratyaksh Singh:** unit.

**Geoff Horowitz:** Oh, Unet.

**Pratyaksh Singh:** Yes. Yeah.

**Geoff Horowitz:** Okay,

**Pratyaksh Singh:** So there is this unit option and then there is this
D which is diffuse and transport which is attention based. Right.

**Geoff Horowitz:** got it.

**Pratyaksh Singh:** I want to start with unit based model to get a
baseline and then I can shift to DIT if needed. But in a sense it\'s my
first time training it.

**Geoff Horowitz:** Got it.

### 00:08:53

**Pratyaksh Singh:** I will just use the simplicity.

**Geoff Horowitz:** Simplest. That\'s what you said. trying to figure
out what you said earlier.

**Pratyaksh Singh:** Yes.

**Geoff Horowitz:** You said simplest. Yeah. Okay, cool.

**Pratyaksh Singh:** Yes.

**Geoff Horowitz:** Sweet. Okay. Um, so I guess protection tool, unless
there\'s something else that you guys want to bring up that\'s that\'s
relatively quick. Um, give you a few seconds to chime in if you do. I
think then the show is suctions.

**Ratul Shashank:** Not at the moment.

**Geoff Horowitz:** Okay, great. Sin, all

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** you.

**Sachin Pandey:** So I started a training with the old pipeline which I
have which was used for the last model. So we are training like two
different model.

**Geoff Horowitz:** Mhm.

**Sachin Pandey:** Let me see next to please. So we are training two
different model. one with like a multi-class model, one is binary model
where everything is uh in a single class. Uh I also added the code data
set into this training which is uh used as a background code data set
which doesn\'t have any

### 00:10:20

**Geoff Horowitz:** You you had a which data

**Sachin Pandey:** annotation.

**Geoff Horowitz:** Oh, the port data set.

**Sachin Pandey:** the one.

**Geoff Horowitz:** Yep.

**Sachin Pandey:** Yeah, these are the main uh objects we are main
classes we are uh

**Geoff Horowitz:** Yeah.

**Sachin Pandey:** using like these six

**Geoff Horowitz:** Such an do we also include the open source data set
in

**Sachin Pandey:** classes.

**Geoff Horowitz:** this?

**Sachin Pandey:** No, we don\'t include open source data in

**Geoff Horowitz:** Okay, I think that\'s okay.

**Sachin Pandey:** this

**Geoff Horowitz:** But at some point we should see if that if adding in
that data set helps generalization.

**Sachin Pandey:** Yeah, we we can try. But generally like the open
source data are much cleaner like looking similar looking to the process
data. We have like mines data which we downloaded.

**Geoff Horowitz:** Mhm.

**Sachin Pandey:** Uh it was looking similar to that one. I think I have
it downloaded. open source data to see. So this is like uh it is for the
mind data

**Geoff Horowitz:** Mhm.

**Sachin Pandey:** and there are some other datas too which uh Sidhart
merged into this one.

### 00:11:44

**Geoff Horowitz:** I

**Sachin Pandey:** Some are from plane and emerge 23 data set with some
plane

**Geoff Horowitz:** Yeah.

**Sachin Pandey:** artifact and and then mines they all merge in this
data set.

**Geoff Horowitz:** Okay. And this one is not included. This is Yeah.

**Sachin Pandey:** Yeah, this one is not

**Geoff Horowitz:** Yeah. Yeah. All All I\'m saying is I don\'t think we
you know we can throw all

**Sachin Pandey:** true.

**Geoff Horowitz:** the annotations there in like some I don\'t know you
know various class, right? Some like unneeded class or whatever. I would
just imagine that seeing data that\'s pretty far out of the normal
distribution could help the model generalize. But we we can look into
that later. I just wanted to make a note so that we don\'t

**Sachin Pandey:** Yeah,

**Geoff Horowitz:** forget.

**Sachin Pandey:** I will I will make a note of that. I will add it
somewhere. Okay. Uh yeah, currently these are getting trained. I was
looking at the logs where the blue one is the multiclass one and pink
one is the binary one.

### 00:13:10

**Sachin Pandey:** So

**Geoff Horowitz:** The you said blue is multiclass and pink is binary.
Yeah. Yeah,

**Sachin Pandey:** yes,

**Geoff Horowitz:** I see it now.

**Sachin Pandey:** I shared this with projects. He like generally the
binary one should perform better. I I need to check whereby this is the
case here. But I\'m not sure why it\'s not performing

**Geoff Horowitz:** It also looks like the loss is rising.

**Sachin Pandey:** well.

**Geoff Horowitz:** Oh. Oh. Oh. Oh.

**Sachin Pandey:** Uh this is the cause.

**Geoff Horowitz:** Oh, that\'s the Okay. Yeah. Yeah. There you go.
There\'s the loss.

**Sachin Pandey:** This is the

**Geoff Horowitz:** Yeah.

**Sachin Pandey:** loss.

**Geoff Horowitz:** Okay. I see now. I see.

**Sachin Pandey:** I think once it\'s done training the predictions can
or the test set can give us some ideas for now I will try to look into
it so

**Geoff Horowitz:** Okay,

**Sachin Pandey:** these were all the classes but this was the table
that you asked for like

### 00:14:27

**Geoff Horowitz:** sweet.

**Sachin Pandey:** uh each classes uh in which data that they are and
then total count of each classes. So we generally use like the major
ones which have a large number of J count

**Geoff Horowitz:** Nice.

**Sachin Pandey:** large number of annotations you

**Geoff Horowitz:** Sergeant,

**Sachin Pandey:** use.

**Geoff Horowitz:** are the are these reports pushed to GitHub or
something? These markdown files.

**Sachin Pandey:** No these are these are not distributed.

**Geoff Horowitz:** These are all local.

**Sachin Pandey:** These are on body.

**Geoff Horowitz:** These are Wally. Can you um you put a print out or
something in in our running notes. Um, whatever it is, as long as it\'s
kind of sharable, right?

**Sachin Pandey:** Okay, I will I will post it in location. I will uh
put this one too.

**Geoff Horowitz:** Yeah.

**Sachin Pandey:** This is the one the model. This is the information
all the information you need about the model which are currently in
training.

**Geoff Horowitz:** Great.

**Sachin Pandey:** Where are all the path and what are the

**Geoff Horowitz:** Fantastic. Fantastic.

### 00:15:29

**Geoff Horowitz:** Fantastic. Yeah, I mean,

**Sachin Pandey:** metrics?

**Geoff Horowitz:** whatever even if you I you know me, I I don\'t
really care where it is as long as it\'s on a drive and accessible and
organized in some way that we can kind of keep track of

**Sachin Pandey:** Yeah. And for the older model which we train there is
also

**Geoff Horowitz:** it.

**Sachin Pandey:** a a link which like we can see the difference between
both the models.

**Geoff Horowitz:** Nice.

**Sachin Pandey:** the HTML page that it

**Geoff Horowitz:** Cool.

**Sachin Pandey:** generated. These are generally good but you want to
let currently we want to compare how it\'s performing with our older
model. Right?

**Geoff Horowitz:** Mhm.

**Sachin Pandey:** Once you train it on a same pipeline, you can just
compare compare on the VW uh test set because all the other other data
sets are new to the old model. I don\'t think we trained on any data
train on

**Geoff Horowitz:** You said we didn\'t train on any ANTX data.

**Sachin Pandey:** yes like we got the data but I don\'t think we
trained and updated the model with it.

### 00:16:56

**Geoff Horowitz:** I I don\'t understand. We got the data, but we
didn\'t You just didn\'t include it in the training.

**Sachin Pandey:** the steam net application which we shared with the
drop I

**Geoff Horowitz:** Uh-huh.

**Sachin Pandey:** don\'t think we included the ent data in the training
for that

**Geoff Horowitz:** Wait, for the stream app that we shared with
Bedrock, it\'s only VW data. There\'s not even Danish

**Sachin Pandey:** yes that we can\'t judge that model with

**Geoff Horowitz:** royalty.

**Sachin Pandey:** on these two data set. So we have to only use the
training set from VW data to compare for comparison the new model

**Geoff Horowitz:** Um, you\'re saying for like a Hold

**Sachin Pandey:** for the comparison between the model which we are
training right now and the one we shipped we will be

**Geoff Horowitz:** on.

**Sachin Pandey:** only using the VW data

**Geoff Horowitz:** Okay.

**Sachin Pandey:** Play.

**Geoff Horowitz:** for a for like a like a for comparison on the ground
truth you\'re saying. Okay, fine. Understood.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** I also think that it\'s worthwhile to actually
compare the metrics that we\'re getting, right?

### 00:18:13

**Geoff Horowitz:** Um, so like, you know, we\'ll have a held out set.
Uh, I think our metrics, if I recall correctly, we were looking at
recall precision F1. Um, I mean I I\'d have to go back and look at the
uh the report directly. I think I\'ve I think you guys have access to

**Sachin Pandey:** I think this is the matrix for the old model.

**Geoff Horowitz:** it.

**Sachin Pandey:** But let me just double check. It was in the same
directory. There it was.

**Geoff Horowitz:** Okay.

**Sachin Pandey:** Locked training matrix take it out. Yeah, this was
the directory. It was logged

**Geoff Horowitz:** Okay.

**Sachin Pandey:** earlier.

**Geoff Horowitz:** Um, hey, something else I was thinking about. How
are we picking the test set?

**Sachin Pandey:** It\'s

**Hemanth Sarabu:** Hey, uh, can someone catch me up real quick?

**Sachin Pandey:** random.

**Geoff Horowitz:** Yeah.

**Hemanth Sarabu:** Also,

**Geoff Horowitz:** Um,

**Hemanth Sarabu:** what is this cool app in the back? Ground QC model
comparison.

**Sachin Pandey:** It\'s just HTML.

**Hemanth Sarabu:** Okay. Okay.

**Sachin Pandey:** These are just to compare the model predictions.

### 00:19:25

**Geoff Horowitz:** Um

**Hemanth Sarabu:** I see.

**Geoff Horowitz:** so we spent a little bit of time just discussing
some some random

**Hemanth Sarabu:** That\'s

**Geoff Horowitz:** things. Um Rula and I need to connect on the S7K
pipeline briefly mentioned um progress with the diffusion model.

**Hemanth Sarabu:** Oh.

**Geoff Horowitz:** Uh no just just progress that he\'s starting to work
with rotul to um to get the data ready. They\'re going to start with a
simplified uh unit model and then uh expand from there as needed.

**Hemanth Sarabu:** Okay. Um, okay.

**Geoff Horowitz:** Um

**Hemanth Sarabu:** Okay. I don\'t know if that is going to be core to
this meeting, but if if it is, I\'ll wait. If it\'s not, we\'ll set up
some time to quickly chat about that.

**Geoff Horowitz:** We we can get back to it.

**Pratyaksh Singh:** All right.

**Geoff Horowitz:** I just I want to make sure that we\'re on path for
the for the training.

**Hemanth Sarabu:** Sounds good. Transit.

**Geoff Horowitz:** So then such and such and sort of are presenting um
we are so we\'ve got two pipelines working.

### 00:20:39

**Geoff Horowitz:** One is the ML intern pipeline. The second one is
training our old pipeline on the new data. uh for this for training our
old pipeline on the new data that\'s going now. Um, a few minor weird
things that we\'re seeing. Satchin\'s looking into uh Sachin I assume
we\'ll have more information on Friday, right?

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** Yeah, we\'ve been going through the ML intern
outputs. Um, actually what what he\'s showing us right now is the Okay,

**Sachin Pandey:** You

**Geoff Horowitz:** what he was showing us summary of the the
annotations that we were doing.

**Sachin Pandey:** don\'t

**Geoff Horowitz:** we were discussing that we were looking at the ML
intern outputs. That\'s what we can see here where we\'re comparing the
outputs of each of the models. That\'s mostly what we talked about. Um,
we haven\'t really gotten into the the results yet. I mean,
qualitatively they look pretty good, but do you have any summary
statistics too?

**Sachin Pandey:** No in this data set. So it was struggling for few uh
few classes which I has like dropped some of like line black which were
like it was confusing between line black.

### 00:22:10

**Sachin Pandey:** So, so one issue we spotted was suppose this was the
marked as line black in one data set but when we switched only different
data set the same annotation may be represented uh same class have a
different feature. So model is little confused about those classes and
we don\'t have like a lot of data for uh all the classes it will be
easily in this one. Suppose we take example of a a y this is the main
one. Sorry not this one. This one it is uh not represented well in vw
but has a lot of annotations in other class and something like this
triple this which is only marked in vw and this is not represented
there. Not able to find the actual data to prove. Yeah, something like
this. So sand patch.

**Geoff Horowitz:** Oh,

**Sachin Pandey:** So if we see let\'s check it out, I think. So if we
see the sand patch at uh in multiple data set, we will see.

**Geoff Horowitz:** heat.

**Sachin Pandey:** Yeah. So this is in DW data set.

### 00:23:27

**Sachin Pandey:** It\'s not noticeable, right? It\'s very faint. And if
we go to the ENTX data set, it has a very like very high feature like it
will pop out more from the background like these ones. So like the same
annotation in different different uh data set are a little different and
model is struggling. He to learn the feature

**Geoff Horowitz:** Sanjan, I I I just don\'t want to forget to ask
about this. How are we doing the how are we picking the test set

**Sachin Pandey:** These are random.

**Geoff Horowitz:** random? Um the thing about random is that you know
they

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** they go over the same areas multiple times, right?
So it\'s possible that we could be that we could not really have a a a
geographically distinct test set, right? We could, our test set could
include some of the training data

**Sachin Pandey:** Yeah, because of the same location.

**Geoff Horowitz:** because of the same location. Um, I think it would
be worthwhile to think it would be worthwhile to pick a geographically
distinct area based on the geo referencing.

### 00:25:35

**Sachin Pandey:** Yes. Uh I will I will make note of that

**Geoff Horowitz:** Okay.

**Sachin Pandey:** also. Uh yeah, I I will I will create a different
test set for

**Geoff Horowitz:** Okay,

**Sachin Pandey:** that.

**Geoff Horowitz:** cool.

**Sachin Pandey:** It\'s

**Geoff Horowitz:** um in the interim in the interim section because the
port data set was

**Sachin Pandey:** very

**Geoff Horowitz:** not part of the training set at all. We could
actually use that as a test set too. It won\'t it won\'t give us
detections obviously. So it\'ll be limited, but it will give us a sense
of the false positives, right? How well it\'s performing on these varied
backgrounds.

**Sachin Pandey:** That\'s for the old model, right? The old model be
checked with comparison with the new

**Geoff Horowitz:** um for the old

**Sachin Pandey:** one.

**Geoff Horowitz:** model. Yeah. Yeah. I mean, we could use it on the
new one, too. The new one, you\'re also not using the port data set. Is
that correct?

**Sachin Pandey:** The latest one I included the port data set in it.

### 00:27:24

**Sachin Pandey:** So it runs back from

**Geoff Horowitz:** Oh, okay. the latest ML intern or the latest
s\*\*\*. We got to create names for each of these.

**Sachin Pandey:** The latest one which the unit one which we are
running right now is

**Geoff Horowitz:** The unit the legacy pipeline,

**Sachin Pandey:** includes yeah it includes

**Geoff Horowitz:** right? Okay. Yeah.

**Sachin Pandey:** the end

**Geoff Horowitz:** Okay.

**Sachin Pandey:** data.

**Geoff Horowitz:** That you all right understood. Okay. Well,

**Sachin Pandey:** So yeah,

**Geoff Horowitz:** then yeah.

**Sachin Pandey:** I was saying like something like this the same object
like there were only uh four or seven annotations like they they marked
right uh seven instance of these objects unique seven instance but when
we

**Geoff Horowitz:** Mhm.

**Sachin Pandey:** like draw them all out like they were present in
multiple images there are multiple one of them so it it will be hard to
pick a area which is not represented. We can just choose one object and
pull out all the especially for this data set. We can like choose one
annotation and pull out all the files which are which have gone through
those areas.

### 00:28:36

**Geoff Horowitz:** Is it bad to have multiple examples of the same
object?

**Sachin Pandey:** No, this was for the test that you told me to make a
test set where the A is not getting repeated. So, we are not testing on
the same data area which we trained

**Geoff Horowitz:** Yes.

**Sachin Pandey:** on.

**Geoff Horowitz:** But I I guess for that I was saying couldn\'t we
just look at an entirely like we could pull out we could pull out by
geography, right? Does that make sense? Or draw it out. But um

**Sachin Pandey:** If we pull but it\'s also important that the the test
set should have the features which we want

**Geoff Horowitz:** like

**Sachin Pandey:** pretype. If you pull out like randomly from any
location we are not certain like the area will have the annotation which
we want to target the objects which we want to

**Geoff Horowitz:** so. So,

**Sachin Pandey:** target.

**Geoff Horowitz:** I wish I had uh I had the Mosaic Gotham, but like my
recollection of Mosaic, you can see my screen. My recollection of Mosaic
is, you know, they went through they having a whole a whole area like
this.

### 00:30:01

**Geoff Horowitz:** But in this area, they you know, they maybe went
over this and there\'s an object right here and they went over this and
there\'s an object right here, right? And they went over this area and
there\'s an object right here and so on and so forth. That\'s my
recollection. And so so what I\'m proposing is that we just take one or

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** two or something of these areas like and basically
say you know this is the test set right and this is the train set.

**Sachin Pandey:** Okay. All the files in that will

**Geoff Horowitz:** Yeah. So that we\'re actually segmenting it
geographically as opposed

**Sachin Pandey:** be

**Geoff Horowitz:** to I don\'t know in any other

**Sachin Pandey:** let me.

**Geoff Horowitz:** way.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** Okay,

**Hemanth Sarabu:** Excuse

**Geoff Horowitz:** that\'s that\'s clear.

**Sachin Pandey:** Yeah. Let\'s

**Geoff Horowitz:** Okay. Um I I\'m going to need to run in a minute and
he you guys can

**Hemanth Sarabu:** me.

**Geoff Horowitz:** uh shift the conversation if you want if you have
time you want to stay on.

### 00:31:05

**Geoff Horowitz:** But Sachin, what are the next steps um with the ML
intern pipeline?

**Sachin Pandey:** uh I don\'t think we are working on emer uh we are
like testing we are getting the final model we will compare the model
from the old pipeline the MLM10 pipeline as well but ideally we will be
going with the the unit model which we we are in training process right

**Geoff Horowitz:** Um, okay.

**Sachin Pandey:** now

**Geoff Horowitz:** I mean, that does make sense, but if if we\'re
getting better results with the ML intern, I guess I guess we can
compare that to to what we get from the legacy pipeline after it\'s done
training. Um, so we can revisit that.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** But the ML intern pipeline that\'s that\'s done
training now, right? Okay.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Okay. I got to drop guys. Um, I\'m going to start
recording so that I can catch up on the conversation if you guys have it
on diffusion

**Hemanth Sarabu:** Okay,

**Geoff Horowitz:** models.

**Hemanth Sarabu:** Ro, you want to take it away?

**Pratyaksh Singh:** Yeah, I I will share the plan.

### 00:32:43

**Hemanth Sarabu:** Mhm.

**Pratyaksh Singh:** Let me know when you\'re doing is it

**Hemanth Sarabu:** Um, not yet. Is it visible to anyone else?

**Sachin Pandey:** Yes,

**Hemanth Sarabu:** Give me one sec.

**Sachin Pandey:** I got it.

**Ratul Shashank:** I can\'t see anything.

**Sachin Pandey:** All right.

**Ratul Shashank:** Yeah, it\'s visible

**Hemanth Sarabu:** Uh, I can see

**Ratul Shashank:** Oh,

**Hemanth Sarabu:** it. protection still. Is uh is project still for
everyone or just me?

**Ratul Shashank:** I\'m not coming to I can\'t see anything.

**Sachin Pandey:** Hey, uh one question for you. Do you know like better
is better accounts like multiclass or just they just want target any
target?

**Hemanth Sarabu:** That\'s a good question actually. Um,

**Pratyaksh Singh:** I think we just want one class. We we are just
adding classes up. We have created these classes because so it\'s easier
for

**Sachin Pandey:** What\'s

**Pratyaksh Singh:** us and they I think

**Sachin Pandey:** right?

**Hemanth Sarabu:** picture breaking up.

**Pratyaksh Singh:** point of contact and then results. Oh, I was saying
that they only want like one class,

### 00:35:10

**Hemanth Sarabu:** So,

**Pratyaksh Singh:** right? Point of contact and maybe sand ripple.

**Hemanth Sarabu:** so Sachin, can you pose this question on Slack and
add Jeff? I\'ll tell you what I remember and I think is reasonable.
Initially it was single class. Initially was

**Sachin Pandey:** VW data set. for VW data set,

**Hemanth Sarabu:** sorry wait.

**Sachin Pandey:** the wind turbine one.

**Hemanth Sarabu:** Uh what are you talking about?

**Sachin Pandey:** Originally the when we ship the model for data set,
right,

**Hemanth Sarabu:** Can we Oh,

**Sachin Pandey:** the first data set that they shared So for

**Hemanth Sarabu:** yes. Yes. Yes.

**Sachin Pandey:** that

**Hemanth Sarabu:** They we right so they didn\'t ask for multiclass but
like project said we were doing multiclass for other reasons

**Sachin Pandey:** one,

**Hemanth Sarabu:** but now since we\'re building on top of that they
want ATR specifically for mines and stuff. Um, now I cannot recall if
they want explosives in a separate class or not and I I don\'t believe
seeing that in the contract. Um, so I think Project\'s statement is
still true, but I would just double check with Yeah, if you can just
make a post on Slack, the output will be just single.

### 00:36:40

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** Also for mines I just wanted to add one thing that
for mines I don\'t think we have the data like we only have six contacts
and

**Hemanth Sarabu:** Gone.

**Pratyaksh Singh:** out of those like only two or three are visible and
they are like really small so it\'s very hard to identify I Jeff knows
about this.

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** Anyway,

**Sachin Pandey:** Like they shared only six context, six images and we
we try to find that location and look at the if they

**Pratyaksh Singh:** uh

**Sachin Pandey:** contains the same area or not. were able to increase
the like count of the annotations of the object detections. But like in
each image it looks different.

**Pratyaksh Singh:** Hey, is my screen visible?

**Hemanth Sarabu:** Mhm.

**Pratyaksh Singh:** All right. Okay. So my plan was that we will have
the image as one channel. the uh so first like for data processing uh I
am taking the port and start board image and then stacking them you them
side by side like port and so the water surface in between I am removing
that entirely so for example let\'s say previously if our data was
something like this right this was port and then this was starboard and
then there was this uh gap in between which was for water surface so I
am removing this gap and I\'m treating port and starboard as as the

### 00:39:23

**Pratyaksh Singh:** image that we want to generate So

**Hemanth Sarabu:** Okay. Mhm.

**Pratyaksh Singh:** I take that image and then I take the image as one
channel and then I take the mask as like another channel right so the
mask will be the annotation mask associated with that image. So once I
once I take this image I break it out into into the small patches that
we have like 256 cross 256 patches and then that that works as an image.
Similarly the annotation that we have Similarly the annotation that we
have uh I also create a binary mask with it and then image as one
channel and then binary mask as another channel goes into the goes into
the unit and the idea is that conditioned on the condition conditioned
on the mask the the unit will generate an image which looks like uh
which looked like the image that we have along with the annotation mask
uh sorry along with the contact generated. So the conditioning based on
mask will be used to generate the contact and then I have another

**Hemanth Sarabu:** Yeah.

### 00:40:42

**Pratyaksh Singh:** conditioning here which will be data set because
data is different looks different from POE and from BW.

**Hemanth Sarabu:** Yes.

**Pratyaksh Singh:** So there will be another data conditioning and
during inference the idea is that you know I can use the mask to to
basically generate uh to basically generate the content I I\'ll have to
think of something so that you know uh so currently it\'s just image and
noise right uh so I

**Hemanth Sarabu:** Yep.

**Pratyaksh Singh:** will train it with flow matching so it will start
with noise but I want to have one more conditioning where I can give it
give it a clean image right I can give it a clean image And then on that
clean image it can generate this uh generate the mask condition. I I
have to think of something to do

**Hemanth Sarabu:** Okay. So, Pra,

**Pratyaksh Singh:** that.

**Hemanth Sarabu:** my recommendation for you and if this is what I
would do if I were if I were like looking at this is there are a a lot
of open source libraries that train Lauras and you can do whatever
conditioning

### 00:41:44

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** variables you want.

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** They\'re pretty good. They\'re pretty good. like um
I looked into this sometime last year,

**Pratyaksh Singh:** Uhhuh.

**Hemanth Sarabu:** didn\'t really dive into it, but you know, for
example, Comp UI um is a is a way to like Okay, so let me let me back up
a little bit. People have been surprisingly successful at

**Pratyaksh Singh:** Huh?

**Hemanth Sarabu:** training slashfinetuning when I say training
Laura\'s fine-tuning models, image generation models on like cra and
I\'m I\'m not talking about

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** engineers. talking about like normal people. They
figure out these recipes for for things that are not what we\'re doing.
Not like scientific stuff,

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** more like uh social media, content generation, etc.
like so there\'s a lot there\'s there\'s you can actually start off if
you actually spend some time on Reddit you will learn

**Pratyaksh Singh:** Huh?

**Hemanth Sarabu:** a lot about how to quickly tune these models using
existing techniques all you I would do what I would do is I would figure
out what are the different recipes people are using and most of these
are open source they they have a UI but you don\'t we don\'t care about
the UI they\'re open source so you can

### 00:43:05

**Pratyaksh Singh:** Uhhuh.

**Hemanth Sarabu:** just plug in your a agent,

**Pratyaksh Singh:** Uhhuh.

**Hemanth Sarabu:** pull all the pieces and replicate a recipe similar
to the similar to that to start and I think you will see much I feel
you\'ll see much more you\'ll see

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** very quick success that way 100%

**Pratyaksh Singh:** Got it. instead of training from scratch,

**Hemanth Sarabu:** 100% especially since there are other issues
obviously because you know these

**Pratyaksh Singh:** right?

**Hemanth Sarabu:** what people typically use are like the Chinese image
generation models for stable diffusion uh midjourney, right? These are
standard. Now,

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** um you know, they\'re they\'re really good uh
pre-trained models. You get very good results. Of course, with what
we\'re doing that is out of distribution, but if I had to guess, it\'ll
still do better than training from scratch. I\'m not certain, but I
it\'s a pretty I would it\'s a pretty good guess.

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** That\'s where I would start. You\'ll actually
you\'ll see results very quickly. A lot of these are Lauras, right?

### 00:44:12

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** And they very they train much quicker than firstly
training a full diffusion

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** model plus training from

**Pratyaksh Singh:** Mhm. Got it.

**Hemanth Sarabu:** scratch.

**Pratyaksh Singh:** Uh I think I agree with you and I was going to try
with hugging face recusive which I think I think is pretty good but like
my problem was all these images or image generation they are trained
with natural images right and the image that we have it is it is like
weird do you see this I\'m I\'m showing some images

**Hemanth Sarabu:** Yes.

**Pratyaksh Singh:** of the patches.

**Hemanth Sarabu:** Wait, what is what are we looking at?

**Pratyaksh Singh:** So these These are from the data set.

**Hemanth Sarabu:** Uh, are we zoomed in? Are we very zoomed in or what
are we looking at?

**Pratyaksh Singh:** Uh it is like 256 cross 256 of the data set.

**Hemanth Sarabu:** Um,

**Pratyaksh Singh:** So let\'s say this is the image right. I can get
you the name of the image too. BRX AU I think this this image right
it\'s just 256 plus 256 patch patch of those right this is why like I
was thinking of maybe training from scratch because they look very out
of distribution and the order that we have they are like quite something
big, right?

### 00:46:00

**Hemanth Sarabu:** I I still think my guess would be that

**Pratyaksh Singh:** I can try it out.

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** Try it

**Ratul Shashank:** We can finetune it for our purpose in comi

**Pratyaksh Singh:** out.

**Ratul Shashank:** UI like for some stable diffusion like fucus they
allow that you can train loras to using fucus uh fukus is

**Hemanth Sarabu:** Using what?

**Ratul Shashank:** a like opensource uh plat gen ai model based on
stable decision

**Hemanth Sarabu:** Mhm.

**Pratyaksh Singh:** What\'s what

**Ratul Shashank:** and F triple O C

**Pratyaksh Singh:** model?

**Ratul Shashank:** U S

**Pratyaksh Singh:** Hey, wasn\'t comfy UI for generating personalized
image? Like so for example, if you want to generate images uh keyword
dog, you could do

**Ratul Shashank:** like Comfy UI is uh Comfy UI is like a control panel
for gen.

**Pratyaksh Singh:** that.

**Ratul Shashank:** You can use any workflow like for model or like for
image

**Hemanth Sarabu:** Yeah.

**Ratul Shashank:** or video even DTS people have created different
workflows for uh different models and you can just pull out any safe
tensor available and you can train your own pipeline.

**Pratyaksh Singh:** What was I eating?

### 00:47:45

**Hemanth Sarabu:** It\'s yeah it\'s a it\'s like an orchestration
layer.

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** So I I read some paper I think which was about I
don\'t know like if you have few images of your dog then you can most of

**Hemanth Sarabu:** Yeah, I think that may have been where it started,

**Pratyaksh Singh:** the that you generate will be of that.

**Hemanth Sarabu:** but it\'s grown from it.

**Pratyaksh Singh:** Okay.

**Hemanth Sarabu:** So all I\'m saying is um all I\'m saying is

**Pratyaksh Singh:** All right.

**Hemanth Sarabu:** that with you will be able to get results in one day
or two days. Taking the Laura and using the tricks that people on Reddit
are using and the

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** tools they\'re using,

**Pratyaksh Singh:** Uh-huh.

**Hemanth Sarabu:** you\'ll be able to get results in one two days and

**Pratyaksh Singh:** Got it.

**Hemanth Sarabu:** even Yeah. Yeah. And then if you have to train from
scratch, maybe we should really be training a small model,

**Pratyaksh Singh:** Uh-huh.

**Hemanth Sarabu:** small diffusion model.

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** Anyway,

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** like the moment you start training from scratch,

### 00:48:49

**Pratyaksh Singh:** I will

**Hemanth Sarabu:** you get into this you get into this complex
territory which we we should

**Pratyaksh Singh:** And I know

**Hemanth Sarabu:** figure out and learn, but it\'ll just take longer to
learn. That\'s all.

**Pratyaksh Singh:** got yeah uh I will set I think we have the GPU for
it. I\'ll set both of them up right from scratch as well as as well as
using

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** Laura and his refusal for compi. I think I will
take help of Ratul since he knows about it more. We can maybe set it up
and yeah.

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** Okay. And then I think parallelly we are also
exploring if we can generate these things algorithm. Yeah. With with
algorithms basically with as augmentations because

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** the thing is that uh my concern is that most of the
images that I saw right it looked like kind of like Gaussian noise only.
And if we train a generative model on the complete image,

**Hemanth Sarabu:** Hey

**Pratyaksh Singh:** it will most probably generate the most probable
images only, right?

### 00:50:00

**Pratyaksh Singh:** Without without a lot of condition. So plan is that
you know keep it keep it running keep this fusion model training and
then parallelly also try to generate these things generate these

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** as augmentations if possible.

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** All

**Hemanth Sarabu:** Okay. Sounds good. Sounds good. Okay. Keep us
posted. We\'ll chat again Friday.

**Pratyaksh Singh:** right.

**Hemanth Sarabu:** All right. Thanks, guys. Speak later. Bye.

**Pratyaksh Singh:** All space.

**Ratul Shashank:** FC discuss Hello.

**Sachin Pandey:** Six. This is what I like.

**Ratul Shashank:** Hello.

**Sachin Pandey:** Recording stop.

**Ratul Shashank:** media. Is that

**Sachin Pandey:** Say binary

**Ratul Shashank:** A

**Sachin Pandey:** model

**Ratul Shashank:** deep

**Sachin Pandey:** binding class

**Ratul Shashank:** binary.

**Sachin Pandey:** model learning because everybody

**Ratul Shashank:** Present clearing.

**Sachin Pandey:** Uh recall lost recall precision jump.

**Ratul Shashank:** Hypothes hypothetical enough or

**Sachin Pandey:** Huh?

**Ratul Shashank:** rather than that. For example, loweritude, higher
altitude. Artifacts we change.

### 00:54:00

**Sachin Pandey:** H.

**Ratul Shashank:** Uh or frequency low. Sorry.

**Sachin Pandey:** Main issue.

**Ratul Shashank:** mixed data. Possible hypothetically.

**Sachin Pandey:** She

**Ratul Shashank:** Mixed data

**Sachin Pandey:** I have Green variation

**Ratul Shashank:** variation.

**Sachin Pandey:** model.

**Ratul Shashank:** Type variation batch

**Sachin Pandey:** Yes, somebody\'s coming.

**Ratul Shashank:** hypothesis. possible. Randomly learn model same.
Fore! Foreign! Foreign! roads. Hypothesis

**Sachin Pandey:** Checking card.

**Ratul Shashank:** Yes. But possible. Please check but minute.

**Sachin Pandey:** 85 cash per second. a

**Ratul Shashank:** Uh

**Sachin Pandey:** point learning rate

**Ratul Shashank:** we call

**Sachin Pandey:** change.

**Ratul Shashank:** for a big

**Sachin Pandey:** Confirm. False. Positive. No. False.

**Ratul Shashank:** negative area.

**Sachin Pandey:** Negative.

**Ratul Shashank:** Well, jeez. Cleass

**Sachin Pandey:** Binary model

**Ratul Shashank:** honey s Last 8 minute. Your

**Sachin Pandey:** already smooth. Multiclass model classification

**Ratul Shashank:** last

**Sachin Pandey:** objects. learning.

**Ratul Shashank:** multi multiclass or binary class multiclass Sorry.
Sorry classes or

**Sachin Pandey:** glass. Sorry.

**Ratul Shashank:** binary. up.

**Sachin Pandey:** You see here input groundut multiclass multiclass or
single class output

**Ratul Shashank:** Okay.

**Sachin Pandey:** model. Segment

**Ratul Shashank:** algorithm. algorithm say

**Sachin Pandey:** Uh but in general binary class 0 Objective may

**Ratul Shashank:** last last unit prediction binary class

**Sachin Pandey:** have

**Ratul Shashank:** Multiclass.

**Sachin Pandey:** Oh, come here. But this is a message.

**Ratul Shashank:** We might text the

**Sachin Pandey:** Okay.

**Ratul Shashank:** ground.

**Sachin Pandey:** Take two.

**Ratul Shashank:** Bye-bye.

### Transcription ended after 01:03:03

*This editable transcript was computer generated and might contain
errors. People can also change the text after it was created.*
