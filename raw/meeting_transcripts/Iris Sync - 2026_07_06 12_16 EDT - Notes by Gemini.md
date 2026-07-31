Jul 6, 2026

## Iris Sync

Invited [[Sachin Pandey]{.underline}](mailto:sachin@crescer.ai)
[[Pratyaksh Singh]{.underline}](mailto:pratyaksh@crescer.ai) [[Niveta
Iyer]{.underline}](mailto:niveta@crescer.ai) [[Hemanth
Sarabu]{.underline}](mailto:hemanth@crescer.ai) [[Geoff
Horowitz]{.underline}](mailto:geoff@crescer.ai) [[Siddharth
Soni]{.underline}](mailto:siddharth@crescer.ai) [[Ratul
Shashank]{.underline}](mailto:ratul@crescer.ai)

Attachments [[Iris
Sync]{.underline}](https://calendar.google.com/calendar/event?eid=NnNzMHVxNzk3MmJqZGVwNXFoN2J1Mjd1OTdfMjAyNjA3MDZUMTYzMDAwWiBnZW9mZkBjcmVzY2VyLmFp)

Meeting records
[[Transcript]{.underline}](https://docs.google.com/document/d/1rc-4Hfjjur7mNFLiqcVN6uF0wCNYFGGWC6L9wsttcK0/edit?usp=drive_web&tab=t.ayrla95bzea3)

### Summary

The team discussed software infrastructure, data processing pipelines,
synthetic generation strategies, and established a new delivery
timeline.\
\
**Infrastructure and Pipeline Processing**\
Technical constraints regarding storage capacity triggered a shift
toward validating a new multi-beam processing pipeline. This transition
addresses licensing difficulties and stabilizes the data workflow for
upcoming milestones.\
\
**Model Development and Augmentation**\
Strategy centers on a tiered synthetic data generation approach to
improve model performance. Comparison testing between different
architectures continues to refine baseline benchmarks and object
detection accuracy.\
\
**Milestone Timeline and Strategy**\
A 4 to 6 week project timeline aligns expectations with recent external
delays. The team confirmed that prioritizing image data for current
milestones takes precedence over secondary detection signals.

### Decisions

Needs Further Discussion

-   **Confidence signal functionality implementation** The team needs to
    > further evaluate the implementation and priority of using multiple
    > geo-detections as confidence signals for the model.

Aligned

-   **Parallel synthetic data generation strategy adopted** The
    > synthetic data generation strategy will utilize a parallel
    > approach, prioritizing simpler methods like augmenting existing
    > backgrounds while simultaneously running a generative diffusion
    > model in the background as a contingency.

-   **Patch-based training methodology established** The training
    > methodology is established to use patch-based image processing,
    > with the optimal grid size determined through empirical
    > experimentation across multiple configurations (64 to 512 pixels).

-   **Establishing initial model baseline** The team will establish the
    > highest possible model accuracy as an initial baseline benchmark
    > for future training.

-   **Legacy pipeline inclusion in benchmarks** The legacy model and
    > pipeline with added data are set to be included as a required
    > benchmark for the project.

-   **Milestone project completion timeline** The project milestone
    > completion timeline is set for a four to six-week range.

We\'ve **updated the Decisions section** using your feedback.

Let us know what you think:
[[Helpful]{.underline}](https://google.qualtrics.com/jfe/form/SV_5p6FWBVWvynleNU?isGoogler=no&isHelpful=yes)
or [[Not
Helpful]{.underline}](https://google.qualtrics.com/jfe/form/SV_5p6FWBVWvynleNU?isGoogler=no&isHelpful=no)

### Next steps

-   \[Sachin Pandey\] Explain Threshold Logic: Connect with Ratul to
    > identify the location of the 60 degree edge filtering threshold in
    > the code and explain the logic behind it.

    > \[Pratyaksh Singh\] Implement Diffusion Model: Implement a
    > diffusion model for synthetic data generation while using
    > class-based conditioning to focus on generating rare data types
    > like RO and surface artifacts.

    > \[Sachin Pandey\] Summarize Results: Prepare a document that
    > summarizes the recent performance results of the trained model.

    > \[Sachin Pandey\] Document Label Summary: Generate a table
    > summarizing labels by class and dataset including total counts and
    > examples.

    > \[Sachin Pandey\] Update Training Data: Add missing annotations
    > for the fourth dataset to ensure it is included in the training
    > process.

    > \[Geoff Horowitz\] Review Map Report: Examine the shared report
    > regarding map data and provide feedback on the process.

    > \[Ratul Shashank\] Investigate Pipeline Anomalies: Determine if
    > the reported variations in anomalies are caused by the processing
    > pipeline.

    > \[Sachin Pandey\] Validate Annotation Quality: Evaluate the
    > performance of recent annotations on the training data and remove
    > them if they degrade model results.

    > \[Pratyaksh Singh\] Develop Diffusion Model: Proceed with work on
    > the diffusion model project.

### Details

-   **Volley Storage Configuration**: Geoff Horowitz and Sachin Pandey
    > discussed a technical issue where the Volley software stops
    > functioning when storage capacity reaches between 75% and 80%.
    > Sachin Pandey suggested reviewing the configuration and
    > potentially adding an external drive for root storage, noting that
    > replacing the main drive is cost-prohibitive, with prices around
    > 25K rupees per TB in India ([[00:00:23]{.underline}](#section)).
    > Sachin Pandey confirmed they recently resolved an issue where they
    > accidentally consumed 300 GB of storage by copying a folder to the
    > wrong location ([[00:01:35]{.underline}](#section-1)).

-   **S7K Processing Status**: Ratul Shashank is working independently
    > to generate a .las file from S7K data
    > ([[00:02:30]{.underline}](#section-2)). They are improving an
    > existing script that had previously failed to correctly read the
    > ping size or maintain a fixed distance between pings
    > ([[00:03:42]{.underline}](#section-3)).

-   **S7K Edge Filtering**: Geoff Horowitz and Sachin Pandey discussed
    > the 60-degree threshold applied to multi-beam data to remove the
    > edges of the swath where uncertainty is higher. Geoff Horowitz
    > noted that they need to ensure this threshold is properly
    > implemented in the current code and requested that Sachin Pandey
    > connect with Ratul Shashank to clarify exactly where this
    > filtering occurs ([[00:05:07]{.underline}](#section-4)).

-   **ISA North America Project Pipeline**: Geoff Horowitz provided
    > context for Pratyaksh Singh regarding the ISA North America
    > project. Because the team is experiencing difficulty licensing the
    > CARIS SDK, they are validating a new pipeline to process
    > multi-beam data directly from S7K files
    > ([[00:08:00]{.underline}](#section-6)). If this validation is
    > successful, ISA North America intends to use this pipeline in
    > August ([[00:09:47]{.underline}](#section-7)).

-   **Synthetic Data Generation Strategy**: Pratyaksh Singh, Geoff
    > Horowitz, and Ratul Shashank discussed the requirements for
    > synthetic data generation ([[00:11:04]{.underline}](#section-8)).
    > Geoff Horowitz established a hierarchy of difficulty for the task:
    > first, copying existing contacts onto existing backgrounds;
    > second, generating new contacts for existing backgrounds; and
    > third, training a model to generate both backgrounds and contacts
    > ([[00:24:26]{.underline}](#section-17)). The team agreed to start
    > with the lowest difficulty option to see if it provides sufficient
    > data to create a balanced dataset
    > ([[00:26:52]{.underline}](#section-18)).

-   **Diffusion Model Implementation**: Pratyaksh Singh plans to utilize
    > available GPUs to implement a diffusion model for synthetic data
    > generation ([[00:40:57]{.underline}](#section-28)). The goal is to
    > condition the model to generate specific classes of data---such as
    > contacts or rare artifacts---rather than just random examples, to
    > ensure the training data addresses areas where the current model
    > underperforms ([[00:43:17]{.underline}](#section-30)).

-   **Image Striping for Data Augmentation**: Ratul Shashank suggested
    > that instead of generating entire new images, the team should
    > divide existing images into smaller strips or grids, hypothesizing
    > that generative models might introduce artifacts that confuse the
    > existing model ([[00:32:19]{.underline}](#section-22)). Pratyaksh
    > Singh confirmed they are already splitting images into 256 or 512
    > grid sizes for training and will experiment with different strip
    > sizes to maximize performance
    > ([[00:35:37]{.underline}](#section-24)).

-   **Model Underperformance and Artifacts**: Pratyaksh Singh and Geoff
    > Horowitz identified areas where the model underperforms,
    > specifically regarding \"RO\" (or \"role\") data, surface shading
    > artifacts, and dredging areas
    > ([[00:37:05]{.underline}](#section-25)). Pratyaksh Singh intends
    > to explore deterministic, non-generative methods to simulate these
    > artifacts to improve model robustness
    > ([[00:40:57]{.underline}](#section-28)).

-   **Labeling Status and Documentation**: Sachin Pandey confirmed that
    > labelers have finished work on the previous two datasets and have
    > transitioned to cleaning the photo map dataset
    > ([[00:49:10]{.underline}](#section-35)). Geoff Horowitz requested
    > that Sachin Pandey create a summary table detailing the number of
    > labels for each class across all datasets to document the end of
    > the current EDA process ([[00:50:27]{.underline}](#section-36)).

-   **Model Comparison (U-Net vs. YOLO V8)**: Sachin Pandey provided an
    > update on model training, comparing the U-Net ResNet 50 model
    > previously used for Vineyard Winds with a new YOLO V8 model
    > ([[00:54:16]{.underline}](#section-38)). The YOLO V8 model has
    > undergone multiple training iterations, including one where the
    > class count was reduced to focus on the most important features
    > ([[00:55:38]{.underline}](#section-39)). Sachin Pandey is
    > currently evaluating the performance differences between models
    > trained on raw data versus those trained on combined raw and
    > processed data ([[00:54:16]{.underline}](#section-38)).

-   **Model Training and Baseline Benchmarks**: Pratyaksh Singh and
    > Geoff Horowitz discussed establishing a baseline by searching for
    > the best model accuracy ([[00:59:15]{.underline}](#section-41)).
    > Geoff questioned the reliability of the ML intern, to which
    > Pratyaksh responded that they plan to use the ML intern for
    > hyperparameter optimization and identifying error patterns,
    > eventually transitioning to their own pipeline for training. Geoff
    > requested that the legacy model pipeline used for \"vineyard
    > winds\" be maintained as a secondary benchmark, specifically to
    > demonstrate performance improvements to Bedrock when adding new
    > data ([[01:00:21]{.underline}](#section-42)).

-   **Map Data and Anomaly Detection Review**: Ratul Shashank reported
    > on their work regarding map data, specifically addressing
    > \"despiking\" processes, and requested a review of the shared
    > report to confirm if their methodology is correct
    > ([[01:01:44]{.underline}](#section-43)). Ratul noted a specific
    > problem where the magnetometry data showed large variations while
    > the RN data did not, and they need to verify if this discrepancy
    > is an issue within the pipeline. Geoff agreed to review the
    > findings and suggested scheduling a separate meeting if further
    > clarification is required ([[01:03:06]{.underline}](#section-44)).

-   **Milestone Timeline and Expectations**: Geoff stated a need to
    > provide Bridget with an updated timeline for the current
    > milestone. A four-to-six-week range was proposed and agreed upon
    > by Pratyaksh Singh, Sachin Pandey, and Geoff, accounting for
    > previous delays of approximately one month on the client side
    > ([[01:04:39]{.underline}](#section-45)). Geoff emphasized that the
    > output must meet or exceed previous benchmarks to satisfy
    > expectations ([[01:06:19]{.underline}](#section-46)).

-   **Annotation Consistency and Data Signals**: Sachin Pandey raised
    > concerns regarding annotations that appear across multiple files,
    > noting that they have been marking object locations even when
    > image quality is low. Sachin expressed they will monitor
    > performance in the training data and remove annotations if they
    > cause issues ([[01:07:28]{.underline}](#section-47)). Geoff
    > clarified that while magnetometry data is not required for the
    > current milestone requested by Bridget, the team may incorporate
    > it earlier if it provides a clear signal, especially in instances
    > where image data is ambiguous
    > ([[01:08:46]{.underline}](#section-48)).

-   **Multi-Pass Detection and Confidence Scoring**: Sachin suggested
    > utilizing information from multiple passes of the same region to
    > store latitude and longitude data, which could hint to the model
    > that an object might be present
    > ([[01:10:12]{.underline}](#section-49)). Geoff agreed this could
    > improve results and noted that overlapping geo-detections could
    > serve as a confidence signal. However, Geoff categorized this as a
    > lower priority because it exceeds the current requirements for
    > Bedrock ([[01:11:38]{.underline}](#section-50)). Sachin and Geoff
    > agreed to discuss the implementation details for tracking these
    > annotations at a later time
    > ([[01:13:10]{.underline}](#section-51)).

-   **Closing and Future Coordination**: Geoff concluded the meeting to
    > attend a separate session that requires recording. Pratyaksh Singh
    > indicated they would focus on the diffusion model and review the
    > meeting recording later ([[01:13:10]{.underline}](#section-51)).

*You should review Gemini\'s notes to make sure they\'re accurate. [[Get
tips and learn how Gemini takes
notes]{.underline}](https://support.google.com/meet/answer/14754931)*

*How is the quality of **these specific notes?** [[Take a short
survey]{.underline}](https://google.qualtrics.com/jfe/form/SV_9vK3UZEaIQKKE7A?confid=ODiFQuVK6i9aKe5X84KrDxIUOAIIigIgABgBCA&detailid=standard&screenshot=false)
to let us know your feedback, including how helpful the notes were for
your needs.*

**📖 Transcript**

Jul 6, 2026

## Iris Sync - Transcript

### 00:00:23

**Sachin Pandey:** Hi.

**Geoff Horowitz:** Hey, Sen.

**Sachin Pandey:** Hi.

**Geoff Horowitz:** How\'s your week? How\'s your weekend?

**Sachin Pandey:** It was good. I cleaned up volley a

**Geoff Horowitz:** Nice. Uh,

**Sachin Pandey:** little.

**Geoff Horowitz:** thanks for doing that. It\'s uh I wonder why why
does Cat have this thing where it stops working when like you know 75 or
80% is

**Sachin Pandey:** No idea. We need to check its configuration.

**Geoff Horowitz:** full.

**Sachin Pandey:** Maybe we can uh change it to some other value like we
should increase some like for the at least for the main root storage we
should put some other drive on it.

**Geoff Horowitz:** Yeah, I\'ve been telling him about that for a while.

**Sachin Pandey:** But

**Geoff Horowitz:** Uh I don\'t know why he\'s like I think I think he
thinks it\'s going to be a pain in the ass to like move the main drive.
I think that\'s what\'s going on with him. But yeah,

**Sachin Pandey:** Uh it will be more plain because of the pricing.

**Geoff Horowitz:** well I

**Sachin Pandey:** It\'s very expensive like 5K SSD which

### 00:01:35

**Geoff Horowitz:** mean uh for how

**Sachin Pandey:** was costing 5K is now 25K one

**Geoff Horowitz:** big?

**Sachin Pandey:** TB.

**Geoff Horowitz:** No way.

**Sachin Pandey:** Yeah,

**Geoff Horowitz:** Oh. Oh.

**Sachin Pandey:** it is in India.

**Geoff Horowitz:** Oh. Five 5k rupees. 5k rupees.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** Okay. Yeah, got it. That that is a lot though.
still.

**Sachin Pandey:** Rupees.

**Geoff Horowitz:** Um, that might be why. It might be because this
drive is like an M2. Um, and I think maybe the others are just like, you
know, external. So, that might be why he\'s a little more resistant.

**Sachin Pandey:** Yeah, like I generally like mount everything and work
on the external drives.

**Geoff Horowitz:** Uhhuh.

**Sachin Pandey:** Uh like on that day I accidentally copied the wrong
folder like it was

**Geoff Horowitz:** Uh,

**Sachin Pandey:** mounting mounted it was the external drive which was
mounted and it has a lot of data but I thought it was the

**Geoff Horowitz:** Yeah.

**Sachin Pandey:** the drive in the this root folder. So I copied the
data folder to delete the remaining files but the data folder was very
big that

### 00:02:30

**Geoff Horowitz:** Got it.

**Sachin Pandey:** like it used around 300 something GBs of

**Geoff Horowitz:** Whatever.

**Sachin Pandey:** storage.

**Geoff Horowitz:** That\'s okay. That\'s not that much. Actually, you
know, it only brought us to like 80s something percent.

**Sachin Pandey:** Yeah, I I fixed it.

**Geoff Horowitz:** My only concern is is the seat stuff.

**Sachin Pandey:** It was a mistake. See that? Yeah,

**Geoff Horowitz:** So

**Sachin Pandey:** we can set it up on a different machine. Okay, try to
change its

**Geoff Horowitz:** you can do that, too.

**Sachin Pandey:** config.

**Geoff Horowitz:** Um, all right. Okay. Um, where are we? So, actually,
let\'s take a second. You\'ve been working with her tool on this S7K
stuff.

**Sachin Pandey:** No, Ratul is like handling it on its

**Geoff Horowitz:** He\'s doing it. Okay. He\'s doing it all fine.

**Sachin Pandey:** own.

**Geoff Horowitz:** Um, but he was also doing he mentioned uh he was
trying to generate a last file. He\'s also doing that independently.

**Sachin Pandey:** Yes. 7k less.

### 00:03:42

**Geoff Horowitz:** Yeah.

**Sachin Pandey:** Yes, like I shared the older script I found which uh
like which doesn\'t have those mistakes. It was looking good.

**Geoff Horowitz:** Okay.

**Sachin Pandey:** I asked him to like because I guess it was not uh
reading the ping correctly. It was using a fixed fixed size fixed uh
distance between two ping. Rul was like improving that script.

**Geoff Horowitz:** Okay. I um there is one thing he was can you can see
my screen maybe he was

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** we were talking about this um this uh like the the
edges of the swap and I was asking him if we\'re still using the 60
degrees as a like a threshold. He asked me can can I point can I point
to where we\'re using the 60° or I think Sachin I think it\'s like 59.9
or something like that right do you know what I\'m talking about here

**Sachin Pandey:** Yeah. Yeah. Uh it was for the Hello.

**Geoff Horowitz:** Sen

**Sachin Pandey:** Yeah. Yeah. Uh it was for the like baki data
underwater data where we are removing the sides based on angle.

### 00:05:07

**Geoff Horowitz:** I thought it was for the multi-beam data.

**Sachin Pandey:** Yeah. GSF and yeah.

**Geoff Horowitz:** Uh-huh.

**Sachin Pandey:** Yeah. We we we are doing

**Geoff Horowitz:** Right.

**Sachin Pandey:** that.

**Geoff Horowitz:** And it was 60° that we or approximately 60 degrees
was what we thresholded. Right.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Okay. I\'m going to tag you on this. Um, please
connect with at sin uh to find where the approximately 60°. Is that
okay? Um,

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** because I I I know I I know you and I discussed
this, but I don\'t actually know where we\'re doing it in the code. I
think you may know or I don\'t know or

**Sachin Pandey:** Maybe like if I remember like we we calculated it
based on the classification in

**Geoff Horowitz:** you

**Sachin Pandey:** GSF.

**Geoff Horowitz:** if so if I recall if I recall we we either heard it
from somebody maybe we heard it from Jose or we saw it in either Jose\'s
data or maybe we saw it in the McKim and Creed data that like somebody
was was applying this thresholding and that that aligned with our that
aligned with our existing knowledge of like you know as you get to the
edges of the swath the um the uncertainty becomes much greater right and
so within that kind of 30° on each side or whatever it

### 00:06:39

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** was uh you know we had much higher uncertainty so so
somehow I think we like independently saw that 60° made sense and then
we confirmed it with somebody\'s data.

**Sachin Pandey:** So,

**Geoff Horowitz:** That\'s my recollection. Um but I don\'t exactly
know where uh I don\'t I don\'t know I don\'t know how that has
propagated through our existing um pipeline at all. So, so anyway, I
think the point here is just if you can connect with Ratul and just tell
him whatever you know about these this this edge filtering, I think
that\'d be helpful for him. Cool.

**Sachin Pandey:** Okay.

**Geoff Horowitz:** All right, I think that\'s enough with S7K. Ratula
and I are working on this independently then. Um, I think we\'re mostly
there. I think we\'re almost ready to uh do some followup with Jose. I
think we have a little bit more, but I think we\'re going to I\'d like
to try to do I\'d like to try to get in touch with Jose like the end of
this week or early next week.

### 00:08:00

**Geoff Horowitz:** um uh end of this week or early next week. Um yeah,

**Pratyaksh Singh:** Hey guys,

**Geoff Horowitz:** that was it. That was the end of my comment.

**Pratyaksh Singh:** uh sorry for which I\'m doing

**Geoff Horowitz:** Hey, Proto say once

**Pratyaksh Singh:** S7 K to L for uh

**Geoff Horowitz:** more.

**Pratyaksh Singh:** S7 K to L conversion. Uh we are working on it for
which plan?

**Geoff Horowitz:** for IIC North America

**Pratyaksh Singh:** for ISA North America,

**Geoff Horowitz:** for the MBEs data. Yeah. So,

**Pratyaksh Singh:** right?

**Geoff Horowitz:** project just to get you up to speed, we let me let
me let me pyramid this for you. Previously, IIC North America wanted
some help with their multi-beam data. Um, we worked with them, as you
know, we worked with them to process that multi-beam data, but part of
that pipeline was using Terraas\'s SDK. uh we are having some trouble
licensing the SDK from CARiS and so we had discussed previously with IIC
um if we could just use the S7K data directly IIIC is okay with that We
haven\'t validated that we can work out that pipeline correctly without
the CARIS SDK.

### 00:09:47

**Geoff Horowitz:** That\'s what RTOL\'s working on. Assuming we can do
that, IA North America is interested in using Iris uh I think they said
in August to process their multi-beam data. They\'re doing collection in
June and July and maybe the the beginning of August. Um, and so in the
interim, we want to validate that we can do this directly from S7K and
not need to use the CARIS SDK. I think that\'s a summary. Questions?

**Pratyaksh Singh:** Okay.

**Geoff Horowitz:** Did I anything I missed?

**Pratyaksh Singh:** No, no. I just forgot why we were working on S7 GB.

**Geoff Horowitz:** Yeah. Okay, that clarifies it.

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** Sweet. Okay. Um, here we\'re tool.

**Pratyaksh Singh:** Hey guys

**Ratul Shashank:** Hey. Hello, guys.

**Pratyaksh Singh:** before

**Geoff Horowitz:** Go ahead project.

**Pratyaksh Singh:** I have some question about synthetic data
generation for birds. Can you help me address

**Geoff Horowitz:** Okay.

**Pratyaksh Singh:** those?

**Geoff Horowitz:** Yeah, let\'s do it. Let\'s discuss bedrock. Let\'s
move on. I think that was on our list.

### 00:11:04

**Geoff Horowitz:** project was you wanted to present and discuss the
synthetic data

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** today.

**Pratyaksh Singh:** So,

**Pratyaksh Singh:** Hello.

**Geoff Horowitz:** I can hear you.

**Pratyaksh Singh:** Yeah, maybe I should Okay. So what do we want to
generate? There are two things. One is the background, right? That we
have gotten from that we have gotten from bedrop and then another thing
is these contexts on the background. Right. So, do we want to generate
only the contacts or do we want to generate the background plus the
contact? What do you want to generate?

**Geoff Horowitz:** What is the Okay. Do we want to generate the
backgrounds? Sorry. Do we want to generate the contacts independently or
do we want to generate the backgrounds plus the contacts together?

**Pratyaksh Singh:** Yeah. So there are two things right? Yeah. Yeah.

**Geoff Horowitz:** Right.

**Pratyaksh Singh:** So back uh so sorry bedrock sh bedrock sharers data
and on their data we can artificially augment the augment the contacts

### 00:13:13

**Geoff Horowitz:** Uhhuh.

**Pratyaksh Singh:** right this is one thing we can do and then another
thing is that we generate

**Geoff Horowitz:** Uhhuh.

**Pratyaksh Singh:** the XF file or the PNG from scratch and then we
generate the context on top of it.

**Geoff Horowitz:** Protect, did you stop talking or are we having audio

**Pratyaksh Singh:** Yeah,

**Geoff Horowitz:** issues?

**Pratyaksh Singh:** I did. No, no.

**Geoff Horowitz:** Okay.

**Pratyaksh Singh:** Did you guys hear my question? I was just saying
that you know the shared XTF files there are lot of XT sites without any
contact. to just add contacts on those XTF files or do we want to
synthetically generate the XTF files, the background plus the contacts?
What do we want to do?

**Geoff Horowitz:** I I guess I\'m I guess I\'m struggling. Okay, let me
just let me think this out loud. Project. So, in my head, as long as the
output is the same, it doesn\'t really matter the process. Unless I\'m
misunderstanding you. So the output is going to be that we have, you
know, varying backgrounds and varying contacts.

### 00:14:52

**Geoff Horowitz:** Whether we do that by taking an existing background
and putting a contact on top of it or generating a new background with
contact embedded like that\'s a process question, not a result question.
Is am I misunderstanding your question?

**Pratyaksh Singh:** Uh I think I think I think I got my answer. So you
so your answer is that given the XTF you just want to generate the
context so that you can train uh so that we can train our unit on it.
Right? It doesn\'t matter if we synthetically generate the background or
if we don\'t synthetically generate the background. So see uh there are
two is

**Geoff Horowitz:** Cor Yeah,

**Pratyaksh Singh:** that correct?

**Geoff Horowitz:** go ahead.

**Pratyaksh Singh:** Is my understanding

**Geoff Horowitz:** I think so. I I think so.

**Pratyaksh Singh:** correct?

**Geoff Horowitz:** I think I think the understanding is correct, but
let me let me repeat it just to there might there might be some nuance
here that I\'m missing and so I I want to repeat it back to you to make
sure we\'re on the same page and Sachin and Ratul break in if you guys
are understanding this differently.

### 00:16:06

**Geoff Horowitz:** So, so our goal, our end goal is to learn various
backgrounds, various negatives and various positives, right? So, various
backgrounds which will provide the negatives and various contacts on
various backgrounds

**Pratyaksh Singh:** Okay.

**Geoff Horowitz:** which will help us learn the positives, the contacts
and the negatives,

**Pratyaksh Singh:** And

**Geoff Horowitz:** the backgrounds behind them. I in my head we don\'t
have enough backgrounds. So we\'ll need to generate some backgrounds. We
also don\'t have enough contacts. So we\'ll need to generate some
contacts. Whether we generate them together or independently or use some
real backgrounds and you know some generated contacts, whatever. Like it
doesn\'t seem to matter as long as we have enough data to be able to get
the

**Pratyaksh Singh:** I see.

**Geoff Horowitz:** objective that we need to get.

**Pratyaksh Singh:** So if you need to generate more backgrounds then I
think you will need another model that generates a background. Right? If
you want to use existing background then the 410 files that you have
that\'s it right you can add you can add noise on top of it but that\'s
all you have do you get what I mean

### 00:17:33

**Geoff Horowitz:** I do. I\'m thinking specifically of like these high
roll backgrounds, right, where we actually don\'t have enough of them.
So, do we need to generate those?

**Pratyaksh Singh:** So see uh do we need to generate those those high
roll backgrounds right? Weren\'t you going to ask more data for them for
it?

**Geoff Horowitz:** Yes. Yes. And I did. And Bridget is still trying to
get us more data.

**Pratyaksh Singh:** Okay. So that means we won\'t get a lot of data for
it. I think

**Geoff Horowitz:** That that\'s my concern is I think that we should
plan for not getting the data and if she surprises us

**Pratyaksh Singh:** uh

**Geoff Horowitz:** and does get us a lot of good data then

**Pratyaksh Singh:** got it.

**Geoff Horowitz:** awesome.

**Pratyaksh Singh:** So I will tell you what my thought process was
right. My thought process was that you train a model to generate the
backgrounds

**Geoff Horowitz:** Sure.

**Pratyaksh Singh:** right give uh you will train a model that will
generate a background right that will be your image generation kind of a
model right and then you can condition those image generation models to
generate

### 00:18:48

**Geoff Horowitz:** Okay.

**Pratyaksh Singh:** the context too right does it make sense

**Geoff Horowitz:** Yes. So you end up generating both the contacts and
the mo and the backgrounds in a single model, right?

**Pratyaksh Singh:** Yeah, that is correct.

**Geoff Horowitz:** Yes. Okay.

**Pratyaksh Singh:** And but the problem with it is that you need a lot
of data for it. For any kind of generative model to perform well,

**Geoff Horowitz:** Mhm.

**Pratyaksh Singh:** you need a lot of data for it. Right? So one of the
thing that I was trying to do was to break these images into multiple

**Geoff Horowitz:** Uh-huh.

**Pratyaksh Singh:** patches, multiple small patches, right? Overlapping
so that I can generate a lot of data. But this is how the image
basically looks. So our we can teach our generative model to generate
backgrounds like these and these are like very

**Geoff Horowitz:** Mhm.

**Pratyaksh Singh:** repetitive, right? But anything if you want to
learn with learn with model I think you are going to need a lot more
data a lot of data because uh you know a lot of data because these are
not natural images right so your pre-trained model I don\'t think will
perform that good on it unless it is like very big model the commercial
models from other companies right so this is why I was I We\'re
generating these small images so that we can use these to train our
model to generate the

### 00:20:27

**Pratyaksh Singh:** background right.

**Geoff Horowitz:** Uhhuh.

**Pratyaksh Singh:** So this is one thing that I can do right and which
in fact I think I should do I will put it to train since the GPUs are
free if it works all good like right I will put it train I will see how
it performs but if we but like if in

**Geoff Horowitz:** Uh-huh.

**Pratyaksh Singh:** our case let\'s say we want to generate some
specific data set right so for example given a background we want to
create a role data set synthetically generated role data set uh to
simulate role basically. So I think there can be some physics based
simulation that we can use.

**Geoff Horowitz:** Uh-huh.

**Pratyaksh Singh:** I\'m not sure but I think there is some physics
based simulation that we might be able to use to kind of convert these
images to road you can do it with generative model with conditioning too
but then again that will require some data which I don\'t think we have
right and then another thing is that which I think is important is to
generate

**Geoff Horowitz:** Uh-huh.

### 00:21:33

**Pratyaksh Singh:** the contacts right so again you can condition the
model to generate contacts which which obviously should better. But
another thing you can do is you know you can take the contact you can
maybe you can learn the shape and size of the contact and then you can
just add it to the images right to the already existing background that
you have right so this is your fully automated way where you forget
about everything you just you know train a model and then hopefully if
the model learns well then you get the desired result out of the box
right you will ask it to generate an image of role it will generate an
image

**Geoff Horowitz:** Mhm.

**Pratyaksh Singh:** of image of role right but it will require a lot of
data which I don\'t think we have like it will require a lot of quality
data too but I\'ll still try to train this model but if there are any
particular things that we want to augment let me know I will try to see
if there are other ways to generate those kind of data I will see if
there are you know there uh I\'ll try to explore some other ways to
generate those

### 00:22:42

**Geoff Horowitz:** Okay.

**Pratyaksh Singh:** data.

**Ratul Shashank:** Good

**Pratyaksh Singh:** So uh can you tell me what the other things

**Geoff Horowitz:** Let me let me try to let me try to summarize let me
try to summarize

**Ratul Shashank:** night.

**Pratyaksh Singh:** are?

**Geoff Horowitz:** this. Um sorry give me a second. Can I share my
screen

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** pro?

**Pratyaksh Singh:** Yeah. Fix.

**Geoff Horowitz:** Can you guys see? I\'m working in this background
PowerPoint just cuz all the rest of our notes are in here.

**Pratyaksh Singh:** Okay.

**Geoff Horowitz:** So, you know, why not, right?

**Pratyaksh Singh:** Okay.

**Geoff Horowitz:** Um, okay. So, static. All right. Uh, let me just add
a date because why not? 20 6. So, all right. The question on the table
is what exactly are we generating, right? Is it background? Uh I
actually project now that I kind of talked through it I think you\'re

**Pratyaksh Singh:** Yes.

**Geoff Horowitz:** actually seeing something else but let me let me
write and then direct it and by all means feel free to enter the
document.

### 00:24:26

**Geoff Horowitz:** So background or

**Pratyaksh Singh:** Yeah. I I want Can you

**Geoff Horowitz:** contact including background plus share

**Pratyaksh Singh:** uh

**Geoff Horowitz:** it.

**Pratyaksh Singh:** No, I I have it open.

**Geoff Horowitz:** Um okay so issue that we\'re saying is um may be
difficult to generate the backgrounds because of a lack of sufficient
background data. I know I\'m being a little reductive here but this is
kind of the point of what you\'re saying. So, so in terms of difficulty
perspective, right? Um, lowest difficulty to highest, right? Um, copy
existing contacts, put them on existing background. Uh, I should
probably make these numbered, but whatever. What\'s going on here? put
them on existing background. Uh two would be I think you said this part
actually generate um new contacts and then put them on existing
background. on existing background. Three is learn to generate both
background plus contacts. Okay. Did I summarize the options correctly?

**Pratyaksh Singh:** Yeah. Uh but I think okay I will try to maybe
difficult because of lack of sufficient data.

### 00:26:52

**Geoff Horowitz:** Just edit it. Don\'t worry about commenting. Just
edit

**Pratyaksh Singh:** All right.

**Geoff Horowitz:** it.

**Pratyaksh Singh:** Uh, I\'ll use blue because it\'s

**Geoff Horowitz:** Whatever.

**Pratyaksh Singh:** it\'s basically questions,

**Geoff Horowitz:** It should just It should just be right.

**Pratyaksh Singh:** right?

**Geoff Horowitz:** If what I wrote is wrong, change

**Pratyaksh Singh:** No, no,

**Geoff Horowitz:** it.

**Pratyaksh Singh:** it\'s it\'s questions. It\'s kind of questions,
right? So, uh, sufficient data for specific. So I\'m adding more contact
sorry context

**Geoff Horowitz:** Okay.

**Pratyaksh Singh:** basically I think this is not the problem with
generator model but we can\'t basically if we don\'t have enough data
set or anything. We can\'t we won\'t we won\'t be able to generate it
like role

**Geoff Horowitz:** Okay.

**Pratyaksh Singh:** like

**Geoff Horowitz:** So, so, so here\'s what my instinct is.

**Pratyaksh Singh:** features.

**Geoff Horowitz:** Pra, my instinct is basically let\'s start with the
lowest difficulty. options and see what results we get, right? Um, and
then, you know, if we if we start with one and we decide, look, you
know, we\'re we\'re really getting a lot of false positives because
it\'s picking up a lot of these background artifacts, then that tells us
we need more background images, right?

### 00:28:36

**Pratyaksh Singh:** Thank you.

**Geoff Horowitz:** And so then we might have to I you know I maybe I
mean I don\'t know maybe we can go to two or maybe maybe I\'m missing
one in here which is you know learn to generate only backgrounds uh
combine um synthetic background with you know one or two above right
I\'m just I\'m kind of musing here Um but so so I think if

**Pratyaksh Singh:** Hey,

**Geoff Horowitz:** these are increasing in level of diff both both
level of difficulty and uh like guar guarantee of success right like if
we just started with number four it might both be difficult and we
wouldn\'t be sure that we\'d be successful right so I don\'t want to put
all of our eggs in basket number

**Pratyaksh Singh:** Thank

**Geoff Horowitz:** for um this is the way that I\'m thinking through

**Pratyaksh Singh:** you.

**Geoff Horowitz:** it. Uh the only caveat here is like if number four
is going to take a lot of GPU time then it might be worth setting it up
now even if we don\'t spend a lot of time on it right setting it up
starting to learn something letting it run in the background while we
actually work on one or maybe two.

### 00:30:00

**Geoff Horowitz:** Uh that\'s the only caveat I can think

**Pratyaksh Singh:** Got it.

**Geoff Horowitz:** of.

**Pratyaksh Singh:** Got it. Uh see the question isn\'t uh even if uh
let\'s say if I put it to train, right? So let\'s say I put the
generator model to train. The thing is that it will generate images like
most of the image in the data

**Geoff Horowitz:** Uh-huh.

**Pratyaksh Singh:** set right I will I will I think I have some plan
where I can where maybe I will be able to use it

**Geoff Horowitz:** Hey. Okay.

**Pratyaksh Singh:** but uh my problem is that only that you know if you
don\'t have enough data set then it won\'t be able to generate data set
uh generate the required data set right because it\'s its distribution
will be very small. So for example, let\'s say you have only 10 images
of roles,

**Geoff Horowitz:** Well,

**Pratyaksh Singh:** right?

**Geoff Horowitz:** uhhuh.

**Pratyaksh Singh:** If you only have 10 images of ro then a

**Geoff Horowitz:** But no, no, no. I mean, I I hear what you\'re
saying,

### 00:30:59

**Pratyaksh Singh:** model.

**Geoff Horowitz:** but it it will I think I hear what you\'re saying,
but it will generate I I agree with you. It\'ll be narrow in its
distribution but it will generate across that distribution of the 10 10
10 images that we have

**Pratyaksh Singh:** Mhm.

**Geoff Horowitz:** right

**Pratyaksh Singh:** Uh uh I don\'t know if it it will learn. I think
the best way is that I will set it up to train.

**Geoff Horowitz:** so so I agree

**Pratyaksh Singh:** I\'ll see I\'ll see what

**Geoff Horowitz:** Hey.

**Pratyaksh Singh:** happens.

**Geoff Horowitz:** Okay. I did I mean did this provide any clarity or
or not?

**Pratyaksh Singh:** Uh I think see my again like my biggest question
still is what are we what are we generating the synthetic data for? Do
you get what I mean?

**Geoff Horowitz:** for more training data and a more

**Pratyaksh Singh:** Is it so for example let\'s say

**Geoff Horowitz:** balanced.

**Pratyaksh Singh:** I\'ll finish finishing. Okay.

**Geoff Horowitz:** I was just going to say I think we\'re generating it
for for a bit a a bigger data

### 00:32:19

**Pratyaksh Singh:** Right.

**Geoff Horowitz:** set and b a more balanced data set as opposed to an
imbalanced data set.

**Pratyaksh Singh:** Perfect.

**Geoff Horowitz:** Would you agree with that?

**Pratyaksh Singh:** I agree with it. But you know we should generate
data where the model is underperforming. Right. Right.

**Ratul Shashank:** Uh can I add to that question or this entire line of
questions?

**Geoff Horowitz:** of course. Of

**Ratul Shashank:** uh like uh my what I was thinking like uh instead of

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** course,

**Ratul Shashank:** creating an uh an entire new uh image or uh the
background or the contacts uh instead of doing

**Pratyaksh Singh:** Mhm.

**Ratul Shashank:** that should we just divide the existing the images
that we already have from the XTFS into smaller strips so that the model
that so that our model can understand the uh image much better because
my understanding is if we generate uh an image from a model from an AI
model it could contain features or artifacts that uh in future might
confuse our existing model like this is my hypothesis instead of
generating a completely new image Should we not just uh divide our
existing images into smaller pieces and feed them instead to the model
for learning purposes and for learning the artifacts of role or it?

### 00:34:23

**Ratul Shashank:** uh we can try creating a mask for such data set and
then uh superimposing that mask on the images that we have. like my my
thought process is to minimize this uh extra

**Pratyaksh Singh:** Mhm.

**Ratul Shashank:** uh feature creation because I think if we generate
any image from a model it might create artifacts which will confuse the
model that we have. This is my hypothesis is is

**Pratyaksh Singh:** Yeah.

**Ratul Shashank:** this

**Pratyaksh Singh:** So to answer your first I I get I get what you are
suggesting to answer your first question. I think we are all that is
splitting the images and feeding it to model. That is correct. Right
Sash? We have gr size grid size of I think 256 or

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** 500.

**Sachin Pandey:** for like training model

**Pratyaksh Singh:** So

**Sachin Pandey:** training.

**Pratyaksh Singh:** yeah, we don\'t feed the whole XTF image as one,

**Sachin Pandey:** Yes.

**Pratyaksh Singh:** right? We split it into grid of 512 or 256 and then
use it to train the model. Was that your first

### 00:35:37

**Sachin Pandey:** Yes.

**Pratyaksh Singh:** suggestion?

**Ratul Shashank:** Mhm. Uh-huh. Like uh uh even uh narrower strips if
that is possible so that we can get as much we can squeeze out as much
data as we can.

**Pratyaksh Singh:** What does narrow stripe

**Ratul Shashank:** Uh so it\'s uh it\'s kind of

**Pratyaksh Singh:** means?

**Ratul Shashank:** an arbitrary suggestion but like suppose if an
artifact is uh a uh if an artifact is contained in a box of 50 by 50
pixel. So if we create an if we create a strip of let\'s suppose 100
pixels by 100 uh 100 100 pixels by 200 pixels. Uh so overall we can
squeeze out more such smaller images which uh which contains the

**Pratyaksh Singh:** Got it.

**Ratul Shashank:** artifacts and the

**Pratyaksh Singh:** Got it. So yeah.

**Ratul Shashank:** contacts.

**Pratyaksh Singh:** Uh so rattle would do kind of something like this
where we will search through the possible range and we\'ll use the one
which gives us best performance. So we will try 128 256 512 64 maybe and
whichever gives us the best performance we use that we use that bit
size.

### 00:37:05

**Pratyaksh Singh:** So this is something that we do. Coming to your
second suggestion that was that you know instead of generating the image
we should uh generate mass to superimpose things

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** right.

**Ratul Shashank:** like ro and s artifacts.

**Pratyaksh Singh:** Yeah.

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** Yeah. I I I get what you mean and that that was
like my that was my that was also my discussion that you know instead of
generating the whole thing from scratch why don\'t we try to do some
predict simulation to maybe create these artifact right and but for
those we need to know where the model underperforms so one thing that I
think bedrock has told us that for role the model underperforms right
Jeff is Is there anything else that they told us where the model
underperforms

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** role was a big one also. Um just generally like
background uh like surface artifacts um you know I I I have here I have
some examples here but basically like surface artifacts they were saying
that we underperformed um you can see like a lot oh this is actually
mostly RO but uh I guess I don\'t have an example there there were some
surface artifacts like various ious types of shading.

### 00:38:30

**Geoff Horowitz:** Some of the things that in Vineyard Winds were not
contacts um but were just, you know, various types of shading.

**Pratyaksh Singh:** Mhm.

**Geoff Horowitz:** We picked those up. Um those are the examples that
they gave us an

**Pratyaksh Singh:** Any chance do you have do you have uh you know if
you have recordings

**Geoff Horowitz:** example.

**Pratyaksh Singh:** go through? Huh?

**Geoff Horowitz:** She She did She didn\'t let us record.

**Pratyaksh Singh:** Oh s\*\*\*.

**Geoff Horowitz:** She didn\'t let us record.

**Pratyaksh Singh:** Do you remember

**Geoff Horowitz:** We um I think we can find some

**Pratyaksh Singh:** examples?

**Geoff Horowitz:** examples, but So, this is this is an example that
she showed us. I I do see like high roll here, but like where we\'re
where we\'re getting a lot of these contacts. Um, this is an example.
She didn\'t show us, but she mentioned that like she thinks that the
model would pick up a lot of these dredging areas as contacts.

**Pratyaksh Singh:** Mhm. Got it.

**Geoff Horowitz:** Does that make sense?

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** Um, those are the examples like like this too.

### 00:39:48

**Geoff Horowitz:** I don\'t know exactly what this is, but I assume our
model would pick up these as potential contacts. Um, hard to see outside
of the waterfall images since this is a mosaic, but like that\'s my
instinct.

**Pratyaksh Singh:** Okay. So, these are these are three or four
examples.

**Geoff Horowitz:** Do you do you guys agree with that?

**Pratyaksh Singh:** These are three or four examples, right?

**Geoff Horowitz:** Yes.

**Pratyaksh Singh:** So,

**Geoff Horowitz:** Yeah.

**Pratyaksh Singh:** Jeff, uh, I don\'t think generator model will help
it. I\'m not sure, but uh, I think we\'ll have to label it out. Noodle
how can how can we do it? Okay, let me see if I can. So by synthetic
data generation you mean generating these kind of artifacts so that our
model is robust to it right.

**Geoff Horowitz:** I I I also I think what I\'m trying to emphasize
here is let\'s not put the cart before

**Pratyaksh Singh:** Uh uh.

**Geoff Horowitz:** the horse so to say, right?

**Pratyaksh Singh:** No,

**Geoff Horowitz:** Like let\'s see where exactly this is exactly what
you\'re saying project.

### 00:40:57

**Pratyaksh Singh:** no.

**Geoff Horowitz:** failing and then generate data to help support
learning better

**Pratyaksh Singh:** Uhhuh. Yeah.

**Geoff Horowitz:** performance.

**Pratyaksh Singh:** Yeah. Uh so what I will do is I will you know I
will just since the GPUs are free I will just train a generative model.
I will train a model to generate the data set right I don\'t know how
useful it will be but you know it will be there just in case if we need
more data set and then for the four or five cases that you discussed I
will try to see if there are you know

**Geoff Horowitz:** Yeah.

**Pratyaksh Singh:** non nond based method that we can use to generate
those kind of data set there are if there are deterministic method to
generate those data set right to generate

**Geoff Horowitz:** Yeah.

**Pratyaksh Singh:** those artifacts maybe. And yeah,

**Geoff Horowitz:** project.

**Pratyaksh Singh:** and this

**Geoff Horowitz:** This is this is a diffusion model that you\'re
implementing.

**Pratyaksh Singh:** is Yeah, this is a diffuser model that I\'m trying
to implement.

**Geoff Horowitz:** Have you have you implemented a diffusion model yet
or modified or

### 00:42:10

**Pratyaksh Singh:** No, no, no.

**Geoff Horowitz:** implemented?

**Pratyaksh Singh:** I I still have to I still have to I was looking at
the data set, right? And I didn\'t

**Geoff Horowitz:** So, so project Oh, I didn\'t mean for this project.

**Pratyaksh Singh:** know

**Geoff Horowitz:** I just mentioned general.

**Pratyaksh Singh:** this is the first time I\'m doing

**Geoff Horowitz:** Yeah. So, so look,

**Pratyaksh Singh:** it.

**Geoff Horowitz:** so so there\'s no the worst case scenario is that we
don\'t end up using that model because we have sufficient data or one of
these other methods work and and you get the opportunity to like really
learn about a diffusion model which in the future at some point. So
there\'s no

**Pratyaksh Singh:** Yeah, that\'s

**Geoff Horowitz:** badity here, right?

**Pratyaksh Singh:** yeah that\'s why I am like that\'s why I\'m excited
to implement it you know anyone

**Geoff Horowitz:** Yeah. Yeah. Great.

**Pratyaksh Singh:** so like I anyway the the thing is that you know if
you\'ll tell me the if if I

**Geoff Horowitz:** Fantastic.

**Pratyaksh Singh:** know the requirements beforehand I can I can you
know maybe I can I can consider those requirement before setting up the
model training.

### 00:43:17

**Pratyaksh Singh:** So for example let\'s say I will give you an
example right. So uh during the weekend I I\'ve learned about diffusion
models right

**Geoff Horowitz:** Uhhuh.

**Pratyaksh Singh:** and what people do is there is one thing where
everything is unconditioned right like you train a model and then once
you have trained the model it will generate random examples right so for
example I train it on I train it on the sidescan data set it will
generate random examples okay the next thing is that you can condition
it so for example that will be a text to image model.

**Geoff Horowitz:** Mhm.

**Pratyaksh Singh:** So you can you can guide it basically you can guide
the model with text where given the text the model will try to generate
examples like this right so similar to this what I can do is I can try
to while training the model I can try to add these kind of guidance so
for example let\'s say I will I will give the model some input right
where when I give it class zero it generates any random example when I
give it class one it generates examples also with the role when I give
it class two it generate those kind of artifacts right the line based
artifacts or the artifacts in POE kind of data set those

### 00:44:31

**Geoff Horowitz:** Mhm.

**Pratyaksh Singh:** kind of thing right so yeah I I\'m going to
implement the model it\'s just the thing that you know what are the
things that we want to condition on because if we just let it

**Geoff Horowitz:** Uh-huh.

**Pratyaksh Singh:** generate if let it generate without any guidance
then what it will do is it will generate those those data data sets
which are most likely in the in the training data. So it will generate
you know the most likely training data which I don\'t think we want
right we want we want data that that is rare right and we want data that
that is rare right

**Geoff Horowitz:** Yes. Yes. We agree.

**Pratyaksh Singh:** so that\'s why need to we need to do conditioning
and and I

**Geoff Horowitz:** We agree.

**Pratyaksh Singh:** think and I think yeah the way that we will
condition that will that will matter. So let me let me get I will try to
get an initial run with some simple conditioning to generate the
contacts right and and once that is done

**Geoff Horowitz:** Okay.

**Pratyaksh Singh:** uh once that is done I I mean we can we can decide
on more advanced one at least I will know how much time it takes and how
much time it takes to train these models and stuff.

### 00:45:51

**Geoff Horowitz:** Sounds good. I I think that\'s reasonable. I think
that\'s reasonable. Um that will give us a leg up,

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** you know,

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** if we get to the point where we really do need it
anyway. Uh I recognize projects you\'re saying this incurs a little bit
of technical

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** debt. I recognize that and that might just be the
cost of, you know,

**Pratyaksh Singh:** Uhhuh.

**Geoff Horowitz:** putting this item lower on the priority list. So,

**Pratyaksh Singh:** Yeah. Anyways,

**Geoff Horowitz:** Uh, okay.

**Pratyaksh Singh:** uh so see this is uh this is what

**Geoff Horowitz:** Anything else? Go ahead. Go

**Pratyaksh Singh:** I was I was saying you know this is what I wanted
to discuss is because what what do we want to

**Geoff Horowitz:** ahead.

**Pratyaksh Singh:** generate right like you know if you want to
generate random examples then it\'s all well and good but if you want to
generate some particular examples then we will have to force the model
to learn And I think I think I

### 00:46:48

**Geoff Horowitz:** Okay. I the the best guidance that I think the best
guidance that I think

**Pratyaksh Singh:** somewhat

**Geoff Horowitz:** we can give right now is we want to be able to
generate contacts. I can imagine that, right? I can imagine a use case
where we want to be able to generate contacts.

**Pratyaksh Singh:** All

**Geoff Horowitz:** I think specific backgrounds that are that are

**Pratyaksh Singh:** right.

**Geoff Horowitz:** um that we can imagine that the model will get
confused on. So RO is one of them, right? Um, some of these like very
scarred backgrounds is another. I can imagine the model will get
confused. I\'m not sure we have a ton of examples of that, right? These
types of backgrounds I can imagine we may want to have synthetic data

**Pratyaksh Singh:** Mhm.

**Geoff Horowitz:** for. We may not, but we

**Pratyaksh Singh:** Got it. And Sachin,

**Geoff Horowitz:** may

**Pratyaksh Singh:** the labelers have labeled these kind of things,
right? The the weird patterns and all.

**Sachin Pandey:** Uh yeah there are multiple classes which line

### 00:47:50

**Pratyaksh Singh:** So the line like

**Sachin Pandey:** like artifact black lines I just predicted on the uh
code data set.

**Pratyaksh Singh:** okay

**Sachin Pandey:** So it is picking the like the shadows regions with or
the black line in original data set black lines were the wires extending
from the like the windmill

**Pratyaksh Singh:** All

**Sachin Pandey:** base. So those were the features and it is picking up
the same similar thing in

**Pratyaksh Singh:** right.

**Sachin Pandey:** your code data set. I can share one example in the
chat. So it\'s not like very common.

**Pratyaksh Singh:** What?

**Sachin Pandey:** Not all files have have it, but it is still present.

**Pratyaksh Singh:** Okay. All right. Thanks. I think I have What the
hell?

**Geoff Horowitz:** Okay.

**Pratyaksh Singh:** It shouldn\'t,

**Geoff Horowitz:** What\'s

**Pratyaksh Singh:** you know.

**Geoff Horowitz:** wrong?

**Pratyaksh Singh:** Lines black. Oh, yeah. It\'s fine. If it\'s picking
lines black, that is fine. We are going to drop the this class anyway,
right? The black lines.

**Sachin Pandey:** Yeah,

**Pratyaksh Singh:** This is okay.

### 00:49:10

**Pratyaksh Singh:** This

**Sachin Pandey:** it is it was mainly for the wires like wires pipes.

**Pratyaksh Singh:** Okay.

**Geoff Horowitz:** Um, Sachin, I would like to go over the results that
we\'re seeing.

**Pratyaksh Singh:** Heat.

**Geoff Horowitz:** Well, I guess two questions. Number one, did the
labelers finish up the last two data sets?

**Sachin Pandey:** Yes, I edit and edit trained another model with it.

**Geoff Horowitz:** Okay, great. Great. What are the out of curiosity,
what are the labelers working on now then?

**Sachin Pandey:** I shared the they were cleaning the photo map data
set on portry.

**Geoff Horowitz:** Okay, great. Great. So, they moved on to other
things. All right.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** Uh so number two, you mentioned that you could throw
together a document that summarizes how we\'re performing right Were you
able to do that?

**Sachin Pandey:** No, not yet. The like the things is not set up. But I
can like give you the overview. I pasted the overview in the notion. I
can show it from

### 00:50:27

**Geoff Horowitz:** Okay. Okay.

**Sachin Pandey:** there.

**Geoff Horowitz:** There\'s there\'s one other thing I\'m going to ask
you to to document, which is a summary of of what we have from our
labels. Does this make sense? So, we\'ve got a bunch of different labels
for a bunch of different classes. Um, can we summarize all that in a
table uh by maybe by class, by data set, things like that?

**Sachin Pandey:** Good examples,

**Geoff Horowitz:** Sure. Sure.

**Sachin Pandey:** Okay.

**Geoff Horowitz:** But yes. Yes. Sure. With examples, but also one like
summary table that shows um number of labels for each of these classes
in each of these data sets. Do you know what I\'m saying or no?

**Sachin Pandey:** No, I can see my

**Geoff Horowitz:** Okay. That\'ll Yeah. Yeah. Go ahead.

**Sachin Pandey:** screen.

**Geoff Horowitz:** That\'ll that\'ll I think help us kind of document
um maybe the end of this EDA

**Sachin Pandey:** Well, I was making something like this.

**Geoff Horowitz:** process.

**Sachin Pandey:** Suppose like this AOI small like same classification
but in different data set it may look different.

### 00:51:49

**Sachin Pandey:** So because it contains mainly uh images, we want main
uh one table also which contains like each data set has how many uh and
types of annotation and what was the what are the counts for those like
One more thing I haven\'t like didn\'t label anything on data set
because we want any annotation mainly

**Geoff Horowitz:** Sin for for me your voice is going in and

**Sachin Pandey:** we have three

**Geoff Horowitz:** out. I don\'t know if you guys are hearing that too.

**Sachin Pandey:** Uh, is it clear now?

**Geoff Horowitz:** Yeah. What were you saying,

**Sachin Pandey:** I was saying uh we only have like three data set four
data set is not included in the training data because it

**Geoff Horowitz:** Sergeant?

**Sachin Pandey:** doesn\'t like we don\'t have any annotations for it
and the few annotations we find we didn\'t include

**Geoff Horowitz:** It should be in the training data though because
we\'re learning the backgrounds, right?

**Sachin Pandey:** Yeah, for for that I can edit I can add few examples
for these also.

**Geoff Horowitz:** Okay. I mean to your to your point or to what I
think your point is Sachin like we should be cognizant of uh you know
the the balance of the data sets but we\'ve we\'ve worked with
imbalanced data sets a ton and so I think we\'re I think we\'re
comfortable working with imbalanced data sets.

### 00:54:16

**Sachin Pandey:** Okay. Anything other than this? My classes are empty.

**Geoff Horowitz:** Um just some summary on like where we are on
training, what areas we\'re doing well on, what areas we\'re doing
poorly Um so that like for example we can share a document with with Hem
and get his feedback

**Sachin Pandey:** Yeah, I was just generating the the comparison

**Geoff Horowitz:** to

**Sachin Pandey:** version for like two models.

**Geoff Horowitz:** to Bedrock.

**Sachin Pandey:** Yeah. So these are like old and new models which new
model uh this

**Geoff Horowitz:** I couldn\'t hear the end of what you said.

**Sachin Pandey:** is the comparison between like old and new model. Old
model is trained on all the annotations on all the files sorry on the
all the files including raw and process data. This one is trained on
only the raw files. So like uh there is some difference but I want to
see the actual difference in

**Geoff Horowitz:** Oh,

**Sachin Pandey:** the

**Geoff Horowitz:** sorry. YOLO V8. When did we do old with YOLO

**Sachin Pandey:** It\'s not old like it\'s day before yesterday.

### 00:55:38

**Geoff Horowitz:** V8?

**Sachin Pandey:** This is the fourth fourth model. This is the third
model. The data set is different like this contains the raw plus
process. It only contains the row.

**Geoff Horowitz:** Hold on. I\'m looking at the metrics you\'re
showing. I see the unit res 50. That\'s that\'s the model that we were
using for vineyard winds that we gave last time. Where\'s the YOLO V8
coming in?

**Sachin Pandey:** YOLO V8 is the model I trained like few days ago on
on all the data set. There were three iterations. One was all the data
set all the classes. Other was like uh other was like reduce the class
count to like from 14 to eight to only focus on the important class so
the matrix can improve and in on in that iteration like we we go two
ways. One was to use the older model with from 13 classes and reduce it
to 18 classes. Other was to train a new fresh one from the scratch. So
those are the

### 00:57:11

**Geoff Horowitz:** You you kind of cut in and cut out a little bit.
What I Why did we dec I\'m not I\'m not fighting it.

**Sachin Pandey:** models.

**Geoff Horowitz:** I\'m just trying to understand. Why did we decide to
add another model?

**Sachin Pandey:** By adding the model you mean like yellow instead of
unit.

**Geoff Horowitz:** Yes.

**Sachin Pandey:** Uh I\'m not sure like I it picked the model on
itself. I basically like given the training data and the annotations.

**Geoff Horowitz:** Oh, this is this is ML intern.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** Okay. Is ML intern also doing the our unit res 50
model?

**Sachin Pandey:** Yeah, it\'s using the same code base. Uh this is the
uh report base that Pat shared with me. He used for training like I I
asked him to like use this uh data this scripts for

**Geoff Horowitz:** So, so I I\'m

**Sachin Pandey:** training.

**Geoff Horowitz:** resulting on YOLO V8.

**Sachin Pandey:** Your voice is cracking. Can you repeat it again?

**Geoff Horowitz:** Mine is maybe it\'s an internet issue on my

### 00:59:15

**Pratyaksh Singh:** Chef uh let\'s search through the model.

**Geoff Horowitz:** side.

**Pratyaksh Singh:** Let\'s see what\'s the best uh what\'s the best you
know what\'s the best best we can get and then maybe then we

**Geoff Horowitz:** Can you guys hear me now? Is this any better?

**Pratyaksh Singh:** can yeah I

**Geoff Horowitz:** Okay.

**Pratyaksh Singh:** can the question was that

**Geoff Horowitz:** All right. Sorry, guys. I guess it was a Wi-Fi on my

**Pratyaksh Singh:** about

**Geoff Horowitz:** side.

**Pratyaksh Singh:** hello Yeah,

**Geoff Horowitz:** Yeah, I can hear you.

**Pratyaksh Singh:** I was saying your question was about license,
right?

**Geoff Horowitz:** Yeah.

**Pratyaksh Singh:** I was saying you know let\'s try to get the best
accuracy that we can and then then you know we can have that as a
benchmark to train one of our

**Geoff Horowitz:** Fine. Okay,

**Pratyaksh Singh:** model like this is this is initial

**Geoff Horowitz:** that\'s reasonable. Um,

**Pratyaksh Singh:** baseline right I think we should focus on where the
model is making mistake like even where the best model is

**Geoff Horowitz:** fine.

**Pratyaksh Singh:** making mistakes so that we can augment those

### 01:00:21

**Geoff Horowitz:** Fine. I agree with that project. Here\'s my
question. and tatchin. Do we trust do we trust ML intern? Do we how much
do we trust ML intern? And do we want to do at least one training round
if not more with our kind of legacy pipeline where we control the whole
thing?

**Pratyaksh Singh:** David

**Geoff Horowitz:** Okay, that\'s my that that was my concern uh and my
question.

**Pratyaksh Singh:** I think this you know ML intern is uh my plan is of
using it as a as a better hyperparameter search kind of a thing right
you let it find find the best hyperparameter you let it find where the
model

**Geoff Horowitz:** Okay.

**Pratyaksh Singh:** is making mistake you augment it you do everything
and then finally when you have all the necessary recipe ready. You can
train with your own P to make sure that everything is good. But it can
basically give

**Geoff Horowitz:** Fine. Fine.

**Pratyaksh Singh:** you

**Geoff Horowitz:** I\'m also interested maybe maybe as a secondary
benchmark for you. I\'m interested to train like using the model that we
had for vineyard winds, right?

### 01:01:44

**Geoff Horowitz:** Using the old model. Um I\'m interested to know if
we train on additional data how that model would perform on the entire
data set. Uh and the reason is because I think bedrock is also
interested in that.

**Pratyaksh Singh:** Go.

**Geoff Horowitz:** They want us they want to say hey you gave us this
existing model you know h how is this working when you just add new
data.

**Pratyaksh Singh:** Gosh.

**Geoff Horowitz:** Uh so to

**Pratyaksh Singh:** Sachin that should be easy to run right.

**Geoff Horowitz:** summarize

**Sachin Pandey:** Yeah.

**Pratyaksh Singh:** Okay.

**Geoff Horowitz:** okay just just to summarize quickly I am all for all
of these approaches.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** Um but I think that it\'s critical that we we we
make our

**Pratyaksh Singh:** Uh-huh.

**Geoff Horowitz:** old model old pipeline added data one of the
benchmarks.

**Pratyaksh Singh:** Got make sense.

**Geoff Horowitz:** Yeah. Okay.

**Ratul Shashank:** And just I would like to just inform you like uh uh
I I was working on the map data. Uh I have shared a report in the thread
where asked a few questions.

### 01:03:06

**Geoff Horowitz:** Great.

**Ratul Shashank:** So uh please uh review that report. Uh and what I
wanted to know is I tried my best to figure out what they what uh they
uh their despite what their process is like they are talking about
despiking and uh and all that

**Geoff Horowitz:** Uh-huh.

**Ratul Shashank:** right so I tried from what I what I understood uh
just uh review that and let me know if I am on the right path or uh if
something needs to be uh look in

**Geoff Horowitz:** Sounds good.

**Ratul Shashank:** a different

**Geoff Horowitz:** Sounds good. Rotul, I\'ll look at that too.

**Ratul Shashank:** okay

**Geoff Horowitz:** Thanks. Um, Rul, if we need to set up a separate
call to talk through this, we can do that also. Yeah.

**Ratul Shashank:** uh I will I will Uh the the problem is like at this
point it is able to find uh uh like anomalies in the ent data set. Like
in that data set there are uh uh very the magnet the mag data is seeing
a huge variations but uh in the RN data set the variations is not very
high.

### 01:04:39

**Ratul Shashank:** So I need to confirm if this is a problem with the
pipeline or if once I figure that out we can uh we can look into it.

**Geoff Horowitz:** Okay. Okay. Um, okay. All that works. Uh, one last
thing. I need to give Bridget an update on when I need to give Bridget
an updated timeline. Um, specifically for kind of this this um this
milestone here. Um, I think it\'s reasonable for us to say that we can
have this done in four to six weeks. Um, what do you guys think?

**Pratyaksh Singh:** That is good. I think that\'s a lot. So that\'s

**Geoff Horowitz:** Yeah. Um,

**Pratyaksh Singh:** good.

**Geoff Horowitz:** yeah, we might, you know, we might need to push a
little, but uh, but yeah, I think it\'s reasonable. Okay.

**Pratyaksh Singh:** So the current timeline was for July like end of
July.

**Geoff Horowitz:** Yes, but that was, you know, they they had a delay
on their end of about a month. Um, and so, so that\'s why everything
just got kind of got pushed a month or so.

### 01:06:19

**Pratyaksh Singh:** Okay.

**Geoff Horowitz:** Maybe maybe it took them six weeks to to give us the
go-ahad. Something like that. Um, the key here is I want to be able to
whatever we give

**Pratyaksh Singh:** Okay.

**Geoff Horowitz:** them has to be at least as good as our benchmarks,
right? At least as good as what we gave them last time. Um, and ideally
better. And so I mean you we\'ve all been through this many times,
right? It might take us some time. It might take us some iteration.

**Pratyaksh Singh:** Okay.

**Geoff Horowitz:** Um uh yeah, I I want to make sure that we have
enough time. I don\'t want to tell them, yeah, we think we can do it in,
you know, four weeks and it actually takes us six, right?

**Pratyaksh Singh:** Okay.

**Geoff Horowitz:** Um I would I would rather give them an upper bound
than a lower bound, right? Um, okay. So, so I think you know I think a
four to six week range is reasonable. Do you guys do you guys agree?

### 01:07:28

**Geoff Horowitz:** Is that something that we think we can meet project?
I think this is really a question for you guys.

**Pratyaksh Singh:** Yeah,

**Geoff Horowitz:** The mag data.

**Pratyaksh Singh:** I

**Geoff Horowitz:** Oh, yeah. Yeah. Okay. All right.

**Pratyaksh Singh:** said

**Geoff Horowitz:** Great.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** Okay. Awesome. All right. Any other questions before
we wrap up? Any other concerns here?

**Sachin Pandey:** I have one concern with the annotations in the data
set.

**Geoff Horowitz:** Sure. What\'s up,

**Sachin Pandey:** So like we don\'t just rely on the visuals from the
file itself. So you remember like I told you like the same annotation is
present in multiple files and so yeah I I generated the images for those
files and try to

**Geoff Horowitz:** Yes.

**Sachin Pandey:** mark the same location in the image also. So even
though like it was like not giving the like high quality feature

**Geoff Horowitz:** Okay.

**Sachin Pandey:** but the object was there so I have marked it. So I
will see how it\'s performed the training data and if it is creating
issues then we may have to remove it

### 01:08:46

**Geoff Horowitz:** Okay. Okay. That\'s that\'s reasonable. Um I will
also go

**Sachin Pandey:** because not every I was saying like because not

**Geoff Horowitz:** ahead.

**Sachin Pandey:** every uh like annotation was every object was giving
the like the and the the the feature which was like black in the center
and then gray surrounding. Some were like gray and white something like

**Geoff Horowitz:** Understood. Understood. So for the milestone that I
just showed,

**Sachin Pandey:** that.

**Geoff Horowitz:** Bridget does not need mag data incorporated. But if
we find, you know, again, I I\'ll be working with mag data does give us
a helpful signal. We can incorporate it. We can fuse that data earlier.
Um, so Sachin, just something to kind of keep in mind as you go through
this. If it\'s not clear in the image, but it is more clear in a mag
data signal, um,

**Sachin Pandey:** Hello.

**Geoff Horowitz:** I can hear you.

**Sachin Pandey:** Uh, your voice dropped off.

**Geoff Horowitz:** Oh, sorry,

**Sachin Pandey:** I don\'t know whether it\'s my internet

### 01:10:12

**Geoff Horowitz:** guys. I don\'t know what\'s going on.

**Sachin Pandey:** connection.

**Geoff Horowitz:** I don\'t know what\'s going on. Uh, what did you
hear?

**Sachin Pandey:** I forgot.

**Geoff Horowitz:** Basically, I\'m saying I hear what you\'re saying. I
I think that that\'s reasonable. Also something to keep in mind is that
we do not need the mag data for this milestone that Bridget wants first,
but if we find internally that it gives us a helpful signal, we can use
it and incorporate it sooner.

**Sachin Pandey:** Yeah. Okay.

**Geoff Horowitz:** Okay. All right. Just a note there.

**Sachin Pandey:** Okay.

**Geoff Horowitz:** Okay, guys. Um, S, anything else you want to bring
up?

**Sachin Pandey:** Uh no like uh they do

**Geoff Horowitz:** Okay,

**Sachin Pandey:** multiple pass of the same reason, right?

**Geoff Horowitz:** cool.

**Sachin Pandey:** Can\'t we use like even if we detect in one single
pass, can\'t we just save that uh save that latl long for future use? So
if some image is has stores later on like we should like give some hint
to the model that there could be something here because we detected it
last

### 01:11:38

**Geoff Horowitz:** I think we need to think uh let me hold on. Yes, if
we could implement something like that absolutely we can do it. No
question. Um it will like that only helps us right that said we could
also they\'re also interested in confidences do you remember that Sachin
so like we can that could be part of a confidence signal too right like
if we only have one known observation then maybe that\'s um you know
that gets described a lower confidence. But if we if we have like
multiple geo detections that we think are the same, maybe that\'s a
higher confidence. Um I think it\'s good. I think it will give us better
results. I think it\'s also kind of over and above what Bedrock needs.
So I would put that functionality at a lower priority. Um those are some
of my thoughts.

**Sachin Pandey:** Uh it will be hard to implement if we have to do we
need to see how it could be

**Geoff Horowitz:** Yeah. Yeah.

**Sachin Pandey:** done.

### 01:13:10

**Geoff Horowitz:** Exactly.

**Sachin Pandey:** But at least from for simple implementation we can at
least just track uh annotations and let down and the overlapping will
increase the confidence as you said at least we can just give it some
kind of

**Geoff Horowitz:** Okay.

**Sachin Pandey:** table.

**Geoff Horowitz:** Okay. We can Sergeant if you want to we can talk
about this later

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** too.

**Sachin Pandey:** Okay.

**Geoff Horowitz:** Any other thoughts, questions, concerns? Okay. All
right. Uh, I\'m going to jump on to the other meeting. I want to do it
on a separate meeting so that I can record it. Um, anybody who wants to
join, I\'ll see you there,

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** Hey, can you please record it?

**Geoff Horowitz:** guys.

**Pratyaksh Singh:** I think I will work on that diffusion model.

**Geoff Horowitz:** Yes,

**Pratyaksh Singh:** I\'ll catch up on

**Geoff Horowitz:** no problem. Yep.

**Pratyaksh Singh:** later.

**Geoff Horowitz:** It\'ll be recorded, so you\'ll you\'ll have access
to it. uh you know in the meeting link.

**Pratyaksh Singh:** Okay, thank you.

**Geoff Horowitz:** Cool. Thanks guys. Bye.

### Transcription ended after 01:15:22

*This editable transcript was computer generated and might contain
errors. People can also change the text after it was created.*
