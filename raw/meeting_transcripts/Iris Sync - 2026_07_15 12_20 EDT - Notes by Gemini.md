Jul 15, 2026

## Iris Sync

Invited [[Pratyaksh Singh]{.underline}](mailto:pratyaksh@crescer.ai)
[[Niveta Iyer]{.underline}](mailto:niveta@crescer.ai) [[Hemanth
Sarabu]{.underline}](mailto:hemanth@crescer.ai) [[Geoff
Horowitz]{.underline}](mailto:geoff@crescer.ai) [[Siddharth
Soni]{.underline}](mailto:siddharth@crescer.ai) [[Ratul
Shashank]{.underline}](mailto:ratul@crescer.ai) [~~[Sachin
Pandey]{.underline}~~](mailto:sachin@crescer.ai)

Attachments [[Iris
Sync]{.underline}](https://calendar.google.com/calendar/event?eid=NnNzMHVxNzk3MmJqZGVwNXFoN2J1Mjd1OTdfMjAyNjA3MTVUMTYzMDAwWiBnZW9mZkBjcmVzY2VyLmFp)

Meeting records
[[Transcript]{.underline}](https://docs.google.com/document/d/1nIYuQccLgZRVX8s3R2Ryrgq6ZxFqY1IAuxp0IIE_LvM/edit?usp=drive_web&tab=t.dj71z24377gi)
[[Recording]{.underline}](https://drive.google.com/file/d/181DWgMghMsgsrZS0POtwg2La2v2tKcE_/view?usp=drive_web)

### Summary

Team prioritized improving data quality, evaluating synthetic
augmentation strategies, and decided against new hardware purchases.\
\
**Improving Data Integrity Standards**\
The team identified data cleanliness and accurate labeling as the
primary drivers for better model performance. Standardizing dataset
archiving effectively resolved existing versioning and file count
discrepancies.\
\
**Developing Synthetic Augmentation Techniques**\
Experiments with Poisson blending and latent noise denoising were
adopted to address data scarcity and object class imbalances. These
techniques serve to increase dataset diversity for sonar object
detection.\
\
**Evaluating Resource and Process**\
Adopting unified reporting frameworks was proposed to streamline
communication across technical workflows. The purchase of additional
graphics processing units was rejected as data availability remains the
primary bottleneck.

### Decisions

Needs Further Discussion

-   **Update reporting standardization process** The proposal to adopt a
    > unified system for team updates is under consideration, with
    > further discussion required regarding the scope and implementation
    > of such a system.

Aligned

-   **Classify distinct objects into separate classes** The team decided
    > to segregate similar-looking objects into separate classes
    > initially to maintain data granularity, with the strategy to merge
    > them into single classes only if needed later.

-   **Clean input data annotations** The team decided to have labelers
    > correct input data annotations by comparing model predictions
    > against manual labels to improve training data quality.

-   **Data set transformation evaluation strategy** The team agreed to
    > transform the VW data set into DRN and POE formats to utilize new
    > data as a robust evaluation test set.

We\'ve **updated the Decisions section** using your feedback.

Let us know what you think:
[[Helpful]{.underline}](https://google.qualtrics.com/jfe/form/SV_5p6FWBVWvynleNU?isGoogler=no&isHelpful=yes)
or [[Not
Helpful]{.underline}](https://google.qualtrics.com/jfe/form/SV_5p6FWBVWvynleNU?isGoogler=no&isHelpful=no)

### Next steps

-   \[Sachin Pandey\] Investigate File Count: Review why the file count
    > changed during data processing. Identify the discrepancy in the
    > documentation.

    > \[Sachin Pandey\] Fix Unzip Error: Cross check the unzip process
    > for potential data loss. Ensure all files are present after
    > extraction.

    > \[Sachin Pandey, Pratyaksh Singh\] Trace Annotation Usage:
    > Identify the path for the ground truth and annotation data used in
    > previous training models. Trace back the specific files used.

    > \[Pratyaksh Singh\] Upload Solution: Provide the local annotation
    > path or relevant file solution used during testing.

    > \[Sachin Pandey\] Share Layout: Provide an image of the geographic
    > layout after updating polygons. Ensure no data is overlapping.

    > \[Ratul Shashank\] Draw Pipeline: Illustrate the current
    > processing pipeline using Excalidraw. Document the workflow for
    > team review.

    > \[Pratyaksh Singh\] Explain Augmentation: Describe the cut paste
    > augmentation method to the team. Detail why it improves model
    > performance.

    > \[Pratyaksh Singh\] Request Mine Data: Message Jeff on Slack to
    > request additional mine data examples.

    > \[Pratyaksh Singh\] Enhance Blending Code: Implement rotation and
    > size augmentation to the blending algorithm to increase object
    > diversity.

    > \[Pratyaksh Singh\] Generate Synthetic Artifacts: Create synthetic
    > line artifacts for the mine separation task and small black
    > objects for the AOI task.

    > \[Pratyaksh Singh\] Augment Sonar Data: Implement random line
    > dropping as an augmentation technique to improve model robustness
    > across different sonar speeds and altitudes.

    > \[Ratul Shashank\] Share Seed Images: Post the created seed images
    > on Slack for team review.

    > \[Ratul Shashank\] Share Project Updates: Post a concise update on
    > Slack regarding DRN performance and current alert status.

    > \[Hemanth Sarabu\] Evaluate GPU Purchase: Assess existing data
    > bottlenecks versus potential advantages of acquiring more compute
    > capacity to determine whether to proceed with the purchase.

### Details

-   **Model Comparison Discrepancies**: Sachin Pandey reports that when
    > comparing the old model on old data versus new iterations,
    > precision increased by 8% while recall decreased by 7%
    > ([[00:12:24]{.underline}](#section-2)). Geoff Horowitz expresses
    > concern regarding the validity of this comparison, noting that
    > because the images, resolutions, and annotation classes have
    > changed, the comparison may not be as direct or accurate as
    > required ([[00:11:04]{.underline}](#section-1)).

-   **Dataset Organization and Archive Management**: The team identifies
    > a lack of a clear, organized archive for datasets, making it
    > difficult to pinpoint which iterations of annotations are the
    > correct ones. Geoff Horowitz emphasizes the need for a systematic
    > \"file cabinet\" approach to group and organize data properly to
    > avoid confusion during future training iterations
    > ([[00:16:31]{.underline}](#section-5)).

-   **Investigation into Missing File Counts**: Sachin Pandey notes a
    > discrepancy where the current folder contains approximately 345
    > files, whereas the original dataset contained 463 files. They
    > suspect the issue may be related to an incomplete unzipping
    > process and commit to cross-checking the files to resolve the
    > mismatch in file counts ([[00:17:59]{.underline}](#section-6)).

-   **Requirement for Systematic Data Logging**: Hemanth Sarabu suggests
    > that the team should be \"paranoid\" about logging dataset paths
    > and configurations in the absence of a formal automated system.
    > They argue that even if they cannot build a perfect system
    > immediately, consistent logging and naming conventions would allow
    > agents to eventually retrieve the correct data, even if it has
    > been moved to different paths
    > ([[00:22:26]{.underline}](#section-9)).

-   **Clarification of Baseline Metrics Tables**: The team clarifies
    > that \"Table 1\" represents the old model on old data used to
    > replicate previous results, while \"Table 2\" represents the old
    > model performing inference on a mixture of datasets without
    > retraining ([[00:27:51]{.underline}](#section-12)). This
    > distinction resolves the confusion regarding why performance
    > metrics differed between the two sets of data
    > ([[00:29:01]{.underline}](#section-13)).

-   **Class Merging and AOI Support**: Sachin Pandey explains that they
    > removed a \"noise\" class and merged several artifacts, including
    > \"black patches,\" into a single class
    > ([[00:29:01]{.underline}](#section-13)). This decision was made
    > because the model was frequently misclassifying \"AOI support\"
    > (Area of Interest support) as \"black patches,\" likely because
    > the model only viewed cropped versions of the input and could not
    > identify the surrounding context
    > ([[00:30:54]{.underline}](#section-14)).

-   **Annotation Labeling Strategy**: The team agrees that segregating
    > objects into specific classes during labeling is a robust strategy
    > because it allows them to merge classes later if needed, whereas
    > trying to separate them retroactively is significantly more
    > difficult. Sachin Pandey confirms they will instruct labelers to
    > draw annotations cleanly to help reduce loss and improve model
    > training ([[00:35:14]{.underline}](#section-17)).

-   **Data Quality as a Limiting Factor**: Sachin Pandey argues that the
    > current pipeline is correct and that performance issues stem from
    > the quality of the input data and annotations
    > ([[00:38:10]{.underline}](#section-19)). They plan to have
    > labelers review and correct existing annotations, focusing on
    > objects with strong features while removing those that lack clear
    > definition to improve the model\'s learning outcomes
    > ([[00:39:19]{.underline}](#section-20)).

-   **Data Split Verification**: Sachin Pandey confirms that the data
    > split has been completed and that polygons have been drawn around
    > the data to ensure there is no longer any overlap. Geoff Horowitz
    > requests an image of the geographic layout to finalize this
    > verification ([[00:41:15]{.underline}](#section-22)).

-   **Evaluation of the Impainting Model**: Pratyaksh Singh updates the
    > team on the \"impainting model\" discussed previously, noting that
    > it failed to perform well because it was trained on a very small
    > dataset containing only 800,000 patches
    > ([[00:41:15]{.underline}](#section-22)). They explain that the
    > previous approach of jointly generating images conditioned on
    > masks and data was ineffective due to this data scarcity
    > ([[00:42:51]{.underline}](#section-23)).

-   **Synthetic Data and Augmentation Strategies**: To address data
    > scarcity, the team discusses using classical machine learning and
    > copy-paste augmentations to generate more annotations
    > ([[00:44:19]{.underline}](#section-24)). Hemanth Sarabu suggests
    > exploring a technique involving latent noise denoising, which
    > allegedly helps diffusion models create more realistic images that
    > align better with the data distribution
    > ([[00:45:57]{.underline}](#section-25)).

-   **Reviewing Comfy UI Workflows**: Ratul Shashank describes their
    > attempts to generate meaningful iterations using Comfy UI by
    > applying masks and adding noise to backgrounds
    > ([[00:47:08]{.underline}](#section-26)). However, the results
    > preserved too many features from the source image
    > ([[00:55:27]{.underline}](#section-30)). Hemanth Sarabu clarifies
    > that the goal of the latent noise technique is distinct from
    > Ratul's method, as it involves converting cut-paste images into
    > latents, adding noise, and then denoising to force the model to
    > create a realistic, in-distribution image
    > ([[00:56:43]{.underline}](#section-31)).

-   **Poisson Blending for Data Augmentation**: Pratyaksh Singh
    > demonstrates a \"cut-paste\" augmentation strategy to solve class
    > imbalance, comparing \"blend direct,\" \"blend alpha,\" and
    > \"blend poisson\" techniques
    > ([[01:01:28]{.underline}](#section-34)). They conclude that
    > \"blend poisson\" is the most effective method because it uses
    > image gradients to create a smooth, natural transition, making the
    > pasted objects look as though they belong to the new background
    > ([[01:02:57]{.underline}](#section-35)).

-   **Data Augmentation and Synthetic Data Generation for Sonar
    > Objects**: Pratyaksh Singh outlined a task to use classical
    > methods to establish performance baselines for the DRN and POE
    > datasets, noting that these datasets lack necessary object
    > annotations ([[01:04:09]{.underline}](#section-36)). Pratyaksh
    > Singh plans to improve code robustness by implementing
    > augmentations, including rotation and modifications to object
    > shape and size, to increase dataset diversity. Regarding datasets
    > with limited examples, specifically for \"mine\" separation and
    > small Area of Interest (AOI) dark regions, Pratyaksh Singh aims to
    > generate synthetic artifacts to improve detection
    > ([[01:05:27]{.underline}](#section-37))
    > ([[01:09:44]{.underline}](#section-40)). Pratyaksh Singh shared
    > visual examples on Slack to illustrate current progress and agreed
    > to request additional mine data from Jeff to improve the training
    > set ([[01:08:07]{.underline}](#section-39)).

-   **Cross-Dataset Transformation Strategy**: Pratyaksh Singh proposed
    > a plan to transform VW data into the DRN and POE datasets using
    > specific augmentations. The objective of this approach is to
    > create a more robust test set and to increase the overall volume
    > of usable data by framing the conversion as an augmentation task
    > ([[01:11:02]{.underline}](#section-41)).

-   **Sonar Image Augmentation Techniques**: Pratyaksh Singh discussed
    > applying augmentations directly to XTS watershed images,
    > specifically by randomly dropping sonar lines to simulate varying
    > path speeds. Addressing the issue of variable scan widths, which
    > fluctuate between approximately 130 and 650 pixels, Ratul Shashank
    > suggested clustering images by altitude to handle these shape
    > variations effectively ([[01:12:07]{.underline}](#section-42)).

-   **Coaching on Effective Update Reporting**: Hemanth Sarabu coached
    > Ratul Shashank on delivering progress updates, suggesting they
    > adopt an \"Instagram reel\" style approach that leads with results
    > and the problem being solved rather than a long-form narrative
    > ([[01:16:21]{.underline}](#section-45)). Hemanth Sarabu also
    > critiqued a recent report for sounding \"falsely confident,\"
    > noting that such language undermines trust in the findings
    > ([[01:17:19]{.underline}](#section-46)). Ratul Shashank clarified
    > that the report\'s claims were based on specific fine-tuning work
    > performed for DRN, though they acknowledged that some features in
    > the generated images were over-preserved and required further work
    > ([[01:18:44]{.underline}](#section-47)).

-   **Standardizing Reporting Frameworks**: Hemanth Sarabu proposed that
    > the team adopt a uniform, concise framework for writing updates,
    > such as the Mutually Exclusive, Collectively Exhaustive (MECE)
    > framework, to improve information delivery
    > ([[01:19:53]{.underline}](#section-48)). Ratul Shashank expressed
    > skepticism, noting that a single system might conflict with
    > individual workflows and suggested an umbrella system might be
    > needed for the entire team to effectively adopt such a change
    > ([[01:21:24]{.underline}](#section-49)).

-   **Technical Coordination and File Management**: Pratyaksh Singh,
    > Sachin Pandey, and Ratul Shashank conducted a brief review of
    > technical specifications, including mask resolution settings of
    > 0.1, file naming conventions, and location paths for annotations
    > ([[01:22:44]{.underline}](#section-50)).

-   **GPU Compute Resource Evaluation**: Hemanth Sarabu inquired whether
    > the team should purchase additional Black Hole Pro 6000 GPUs,
    > citing rising prices and the potential need for more compute to
    > support generative work ([[01:32:38]{.underline}](#section-52)).
    > Pratyaksh Singh stated that additional compute would not provide
    > an immediate benefit because the current project is bottlenecked
    > by data availability rather than processing power. Consequently,
    > Hemanth Sarabu decided to delay a decision on the purchase
    > ([[01:33:56]{.underline}](#section-53)).

-   **Utilization of Server Resources**: Pratyaksh Singh asked if the
    > team would utilize the H1 servers. Hemanth Sarabu confirmed that
    > they cannot use these resources for Bedrock, but they may be able
    > to utilize them for specific Iris tasks
    > ([[01:35:09]{.underline}](#section-54)).

-   **Finalization of Sonar Augmentation Strategy**: Pratyaksh Singh and
    > Ratul Shashank concluded the discussion by confirming the approach
    > for sonar data, which involves using altitude and horizontal range
    > to inform the random generation of gaps in the data as a form of
    > augmentation ([[01:35:09]{.underline}](#section-54)).

*You should review Gemini\'s notes to make sure they\'re accurate. [[Get
tips and learn how Gemini takes
notes]{.underline}](https://support.google.com/meet/answer/14754931)*

*How is the quality of **these specific notes?** [[Take a short
survey]{.underline}](https://google.qualtrics.com/jfe/form/SV_9vK3UZEaIQKKE7A?confid=imaWkaHHyb6IMVhHuYj0DxIUOAIIigIgABgECA&detailid=standard&screenshot=false)
to let us know your feedback, including how helpful the notes were for
your needs.*

**📖 Transcript**

Jul 15, 2026

## Iris Sync - Transcript

### 00:07:01

**Ratul Shashank:** Hello su.

**Sachin Pandey:** My voice is clear. Is my voice clear?

**Ratul Shashank:** Yes, it is.

**Sachin Pandey:** Okay.

**Ratul Shashank:** Birthday one.

**Sachin Pandey:** birthday. Mhm. But they don\'t

**Ratul Shashank:** like

**Sachin Pandey:** transcribe. Transcribe what I\'m

**Ratul Shashank:** Yeah.

**Sachin Pandey:** meeting offline. Default 0.1 to The

**Ratul Shashank:** Yeah, it is.

**Sachin Pandey:** default XTF to PNG default 0.25olution

**Ratul Shashank:** And now we just check

**Sachin Pandey:** 0.1 default 0.25 25.

**Ratul Shashank:** 0.1 resolution. WhatsApp 0.1 pixel information.

**Sachin Pandey:** data.

**Ratul Shashank:** 0.2 compared to 0.12 0.2 There you go.

**Geoff Horowitz:** Hey guys.

**Sachin Pandey:** Hi

**Geoff Horowitz:** Hey S.

**Ratul Shashank:** Hey

**Geoff Horowitz:** Hey.

**Sachin Pandey:** Jeff.

**Geoff Horowitz:** Um, dude. Sucken. What? Uh, I thought we were
aligned at the end of the last meeting, but now I think we aren\'t

**Sachin Pandey:** Uh why

**Geoff Horowitz:** because because of those because of those questions
I was asking. Um,

**Sachin Pandey:** uh were you able to recreate s is the one like this
is the name for

### 00:11:04

**Geoff Horowitz:** you

**Sachin Pandey:** the last model we shared right?

**Geoff Horowitz:** Yeah. Yeah. Yeah.

**Sachin Pandey:** Okay.

**Geoff Horowitz:** S stands for statement of work. Uh, so we\'re using
it I Hemoth and I have been using it as shorthand for the first project
that we did with

**Sachin Pandey:** Okay.

**Geoff Horowitz:** them versus the the one that we\'re doing now, which
is the second project S. So2.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** Does that make

**Sachin Pandey:** like uh yes like when I got into like generating the
matrix I realized like it is

**Geoff Horowitz:** sense?

**Sachin Pandey:** not just like appletoapple comparison like we we
change the images we like we increase the resolution we redo the all the
annotations like even added multiple classes so it\'s like it may not
give the perfect uh picture or comparison that we want Back.

**Geoff Horowitz:** Um, okay. I hear what you\'re saying. Uh, I mean,
look, I I think I think we need to ask these questions and get as close
as we can and

**Hemanth Sarabu:** And then I\'m

**Geoff Horowitz:** then um, how I\'m getting some feedback from

### 00:12:24

**Hemanth Sarabu:** getting some feedback.

**Geoff Horowitz:** you. All right. uh I think we need to get as close
as we can and then when when we see the differences these are these are
how we explain them right this is kind of explanability make sense

**Sachin Pandey:** Yeah, like yeah,

**Geoff Horowitz:** section

**Sachin Pandey:** like these are generally to tell the bedrock like we
improve this much in these

**Geoff Horowitz:** yeah but this this is exactly why we discussed you

**Sachin Pandey:** areas.

**Geoff Horowitz:** know getting these baseline metrics in the first
place right um we need

**Sachin Pandey:** Yes.

**Geoff Horowitz:** to know what we\'re dealing with and what our what
our baseline

**Sachin Pandey:** So if we compare like old model on old data set like
old

**Geoff Horowitz:** is.

**Sachin Pandey:** annotations the precision is up by like 8%. And
recall is reduced by 7%.

**Geoff Horowitz:** I I\'m struggling to see it in this table that you
shared in

**Sachin Pandey:** Uh if you see the first table the first line is old
matrix from doc.

**Geoff Horowitz:** Slack.

**Sachin Pandey:** I I the matrix doc that you shared yesterday it
contains the screenshot of the like uh screenshot of matrix.

### 00:13:49

**Sachin Pandey:** So there was like I pulled it from let uh it was
polygon based in the first image where I pulled the two

**Geoff Horowitz:** Okay. That is that\'s this table.

**Sachin Pandey:** positive.

**Geoff Horowitz:** You said the first table. That\'s this table. What
are you saying?

**Sachin Pandey:** Uh yeah it\'s not formatted correctly.

**Geoff Horowitz:** Old metrics right here.

**Sachin Pandey:** Yeah, old matrix is this one. I don\'t know why it\'s
the formatting is

**Geoff Horowitz:** the the form is really funky.

**Sachin Pandey:** incorrect.

**Geoff Horowitz:** Do you can you show it in a way that\'s less

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** weird?

**Sachin Pandey:** Um, can I share my screen?

**Geoff Horowitz:** Yeah.

**Sachin Pandey:** It is formatted in

**Geoff Horowitz:** Yeah. Do it.

**Sachin Pandey:** my so think of it like a baseline which we like which
we got last time. And these are the new ones. So this is increased and
this is decreased. I need to look into look into why the like file count
change.

**Geoff Horowitz:** And it\'s the same model.

### 00:15:01

**Hemanth Sarabu:** Oops.

**Sachin Pandey:** Yeah, it\'s the same model. M model is same

**Geoff Horowitz:** Model\'s the same except we\'ve added classes.
That\'s what you were telling me before.

**Sachin Pandey:** except we uh I don\'t get it like can you repeat the
part

**Geoff Horowitz:** You were just telling me that the input data has
changed a little bit because we\'ve added

**Sachin Pandey:** again.

**Geoff Horowitz:** classes and added some annotations. Weren\'t you
just saying that it\'s the

**Sachin Pandey:** That will be this one because old model on new new
annotations or

**Geoff Horowitz:** new fine?

**Sachin Pandey:** new

**Geoff Horowitz:** Okay, understood. So,

**Sachin Pandey:** like

**Geoff Horowitz:** so metric on the VW data set. So, that\'s just
recreation of the old model. Fine. So,

**Sachin Pandey:** this

**Geoff Horowitz:** do we know why it\'s why is

**Sachin Pandey:** one.

**Geoff Horowitz:** it why is it different? What are you What are we
looking at? This is number two,

**Sachin Pandey:** uh these are Yeah,

**Geoff Horowitz:** right?

**Sachin Pandey:** this was the one I just shared.

### 00:16:31

**Geoff Horowitz:** Old model, old data set. Okay, fine. So you\'re
still looking into you\'re looking into why there\'s like differences in
number of images and all

**Sachin Pandey:** Yeah, like actually it\'s all come down to less
documentation because

**Geoff Horowitz:** this.

**Sachin Pandey:** we have uh so much we have multiple iterations of the
annotations. So it\'s hard to pinpoint which one is the correct one.

**Geoff Horowitz:** That\'s a big issue.

**Sachin Pandey:** Yeah. Like in this one there are like all these are
like for the same file and I also like I just stumble upon one more
thing. I need to also cross check that but uh

**Geoff Horowitz:** guys. I mean, we need a we need a final data set,
right? Uh, I I get it that we keep making updates and iterations, but we
need a way to like organize what what data sets we need like

**Sachin Pandey:** Well,

**Geoff Horowitz:** a, you know, like a file cabinet, like an archive of
some sort that groups all this stuff together.

**Sachin Pandey:** so like this is I just copied it from the the data we
like his father.

### 00:17:59

**Sachin Pandey:** like downloaded from the CNT. So this was the all
data that we trained. But if the current like currently we on the final
file we have we only have around 180 files not 463. I thought like uh it
was like some of it is because I dropped this process folder completely.
This has around 160 files but still like around 120 files are not
present. So in total this folder contains around 345s and the total
images we we last time had was is

**Geoff Horowitz:** Great. So, Sasha,

**Sachin Pandey:** 463.

**Geoff Horowitz:** so what\'s the So, what\'s the what\'s the point?
What\'s the headline there?

**Sachin Pandey:** Uh there are like in this folder there are around 120
to 130 extra files which don\'t we which we don\'t know where it came
from. either like we either like unzipping file doesn\'t

**Geoff Horowitz:** Okay. Okay.

**Sachin Pandey:** uh like completed it because uh this contains all the
XTF PNG that we have but the count is not matching either

**Geoff Horowitz:** So Sachin, I I\'m going to say I\'m going to say I
think I think this is really important that we figure this out.

### 00:19:13

**Sachin Pandey:** it\'s

**Geoff Horowitz:** I I do think it\'s really important that we figure
this out. That said, the metrics are close enough that I guess at least
I\'m okay going on to the the next step. But, you know, we like, you
know, how do we know? So, on step two, how do we know that we\'re
training on the right DW data set?

**Sachin Pandey:** I think it could be problem in the unzip because like
uh Ratul was also facing it earlier where where like one of the zip
folder was not working for him. I will just cross check that because uh
we don\'t even have the like this much XTF. We only has we only have
around 340 XTF file in total.

**Geoff Horowitz:** Um, okay. I I don\'t really know what else to say.
Are we going to figure this

**Sachin Pandey:** Yeah. Yeah. I was I was going to work on it,

**Geoff Horowitz:** out?

**Sachin Pandey:** but I didn\'t get time for

**Geoff Horowitz:** Okay. All right.

**Sachin Pandey:** it.

### 00:20:49

**Geoff Horowitz:** Let\'s move on to um let\'s move on to number two
then. I I again Yeah.

**Hemanth Sarabu:** So really quickly,

**Geoff Horowitz:** Go ahead.

**Hemanth Sarabu:** the problem the problem hands. We\'re establishing
baseline. We just don\'t remember what data set we trained on last year
or earlier this year.

**Sachin Pandey:** No,

**Hemanth Sarabu:** Is that

**Sachin Pandey:** we remember the data set uh like these are all the
files which we trained on.

**Hemanth Sarabu:** right?

**Sachin Pandey:** We have already but current like the the new images
we generated is not matching with the count of images that we have last
time.

**Geoff Horowitz:** But you also said we don\'t know which like training
data we were using right which which ground truth which annotation

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** set.

**Sachin Pandey:** Uh that is also the

**Geoff Horowitz:** So I mean at least in a general sense he is

**Sachin Pandey:** question.

**Hemanth Sarabu:** So,

**Geoff Horowitz:** correct.

**Hemanth Sarabu:** um, who who was training the models

**Sachin Pandey:** I am.

**Hemanth Sarabu:** back back then.

**Sachin Pandey:** Uh

**Pratyaksh Singh:** it.

**Hemanth Sarabu:** Did you happen to log Did you happen to log to clear
ML the data set path?

### 00:22:26

**Pratyaksh Singh:** Yeah, I\'m checking that.

**Hemanth Sarabu:** I think we should we should be very um like paranoid
about things like this and really log in the absence of a system which
we don\'t have a system. Um the nice thing is if we log this stuff you
can actually ask an agent to go figure it out.

**Geoff Horowitz:** Emma, that\'s assuming that we saved the data. Like
what what am I trying to say? It could be pointing to a path that
doesn\'t exist anymore because we moved that data elsewhere,

**Hemanth Sarabu:** Yeah, but I I do hope that we\'re giving them good
names,

**Geoff Horowitz:** right?

**Hemanth Sarabu:** you know, and then maybe it becomes look look go
look for this. Now, this is not a nice solution. It is it is it is a way
to unblock ourselves without establishing a system.

**Geoff Horowitz:** I agree with you. I think the question is why not
establish a system?

**Hemanth Sarabu:** I\'m I\'m I\'m okay with that.

**Geoff Horowitz:** Yeah. Such an you know we\'re we\'re running into
something similar where I know you and Rul have been talking about this
that we can\'t find the we can\'t find the original last files that we
used to send IIC the multi-beam data.

### 00:24:09

**Geoff Horowitz:** Um and I think this is a very similar similar
problem where we don\'t you know it probably exists somewhere on Wall-E
but we don\'t know where right

**Hemanth Sarabu:** Okay, at the very least Sajin, maybe this gives you
clues between you and Pratak. You guys can uh

**Sachin Pandey:** like uh

**Hemanth Sarabu:** trace back it was used.

**Sachin Pandey:** yeah like we have some idea like I have one final
annotation uh it\'s somewhere I need to look at

**Hemanth Sarabu:** Okay. Uh yeah, let\'s move on.

**Pratyaksh Singh:** I have the

**Geoff Horowitz:** Um,

**Pratyaksh Singh:** usually I can give you the you wanted the
annotation right which was used. Give it a little chance.

**Sachin Pandey:** I I found the path that I shared with you. Can you
confirm that it\'s that one? Local without triple

**Pratyaksh Singh:** Uh I have one I have

**Sachin Pandey:** IT10_m

**Pratyaksh Singh:** one that I have locally which I know I ran even.

**Hemanth Sarabu:** I

**Pratyaksh Singh:** I I\'m going to share that path with

**Hemanth Sarabu:** guess

**Sachin Pandey:** You did a better

**Pratyaksh Singh:** you.

### 00:25:48

**Sachin Pandey:** job.

**Pratyaksh Singh:** I\'m going to just upload the solution.

**Geoff Horowitz:** Sergeant, I am uh I I I I actually have a hard stop
at the top of the hour.

**Pratyaksh Singh:** Whatever.

**Geoff Horowitz:** Um and you guys can stay on, but can you can you and
project Josh work on this later?

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** Thanks. Um, very briefly, I just want to talk about
number two right there.

**Sachin Pandey:** Just

**Geoff Horowitz:** Yeah. So, you mentioned some differences in the data
set.

**Sachin Pandey:** one.

**Geoff Horowitz:** Um, I think I think what surprises me is that these
precision and recall numbers look like significantly worse than our than
our number one baseline, right? What\'s going on

**Sachin Pandey:** Yes.

**Geoff Horowitz:** here?

**Hemanth Sarabu:** So to to clarify two is old model no retraining
train uh inference on new

**Geoff Horowitz:** Uh,

**Hemanth Sarabu:** data.

**Sachin Pandey:** No old model on just like without any training just
prediction on the

**Geoff Horowitz:** no.

**Sachin Pandey:** new

**Geoff Horowitz:** Correct. For he for the for what you mentioned
inference only I think that\'s uh

### 00:27:51

**Sachin Pandey:** data

**Geoff Horowitz:** sin that\'s that\'s that second row in the first set
is that correct.

**Sachin Pandey:** and

**Hemanth Sarabu:** I thought it was the second table actually.

**Sachin Pandey:** And

**Hemanth Sarabu:** Sachin, why don\'t you explain what table one and
table two

**Geoff Horowitz:** Okay. Go

**Hemanth Sarabu:** are?

**Sachin Pandey:** table one is like uh we used the old model with old

**Geoff Horowitz:** ahead.

**Sachin Pandey:** annotation and old data where where the resolution of
the data was like

**Hemanth Sarabu:** Mhm.

**Sachin Pandey:** 0.25 to like to find out uh can we get the same
matrix that we are getting last time. So it is somewhat close but not
like accurate.

**Hemanth Sarabu:** Okay. So,

**Sachin Pandey:** And this one

**Hemanth Sarabu:** in wait, let me repeat uh one back and you tell me
if it\'s right or wrong.

**Sachin Pandey:** is

**Hemanth Sarabu:** old model, old data inference only. Basically just
reproducing what we already achieved or attempting to reproduce.

**Sachin Pandey:** yes.

**Hemanth Sarabu:** Okay. And what is

**Sachin Pandey:** Uh this was like the same old old model with the like
with pred prediction on all

### 00:29:01

**Hemanth Sarabu:** two

**Sachin Pandey:** the like mixture of all the data set to see like how
much uh like precision and recall we are getting without retaining.

**Geoff Horowitz:** with with retraining or without retraining.

**Sachin Pandey:** It\'s like just the same model is used in both uh

**Geoff Horowitz:** Ah, okay. Got it.

**Sachin Pandey:** matrix

**Geoff Horowitz:** Okay. So, yes, Emma, you were right. Okay, I guess
that clarifies number two for me then. So, I\'m interested in number

**Sachin Pandey:** and uh this is the base matrix which we

**Geoff Horowitz:** Three.

**Sachin Pandey:** can use. Uh diff like issue with the pixel level data
is like something like sand ripple which has a lot of like area it it
can dominate the like pixel values a lot. So like object level gives a
much better idea. So like we can treat this as a base uh matrix and like
uh for the next uh iteration of training what we changed was we removed
this noise class uh we don\'t need it and it was not even present in the
validation set like there was no annotation in the validation set
because it\'s so such small uh and we like I\'ve cleaned this up like
only keeping the ones which are important and merging this this and this
and also the black patch into a single class because these have a like
similar looking artifact can show some of the like AI support.

### 00:30:54

**Sachin Pandey:** So generally like it\'s a black patch in the like
surrounding and black patch is also looking similar like it can be like
this patch and also

**Geoff Horowitz:** Um,

**Sachin Pandey:** the like small circular patch because models only see
the cropped out version it cannot tell like whether this will be uh AI
support. Uh for better example AI support H yeah

**Hemanth Sarabu:** What is Hey, sorry. What is AO uh AOI

**Sachin Pandey:** I yes I am just going to tell you that AI support

**Hemanth Sarabu:** support?

**Sachin Pandey:** is

**Hemanth Sarabu:** So Sachin are you talking to us about the results of
ML intern.

**Sachin Pandey:** no these are not the results of ML in term these are
like we use the same pipeline that we used to train the other model and
uh just change the data set with it includes all the data set all new
data set.

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** Oh s this is what I this is what I want. So the

**Sachin Pandey:** So this will be the main object like AOI and these
are the supports which are generally like close to the windmill and
because we see this we will mark anything like this to the AI support
but if you don\'t see like any of any this like similar looking thing
will is marked as uh black patch.

### 00:32:40

**Sachin Pandey:** So that\'s why like merging those will gives better
result because AI support you see like it mistakes it made a mistake by
classifying these supports as a black patch First, like they are similar
looking.

**Hemanth Sarabu:** Sorry,

**Sachin Pandey:** So that\'s why like me.

**Hemanth Sarabu:** what is AOI support? Did he did he explain it or did
I miss

**Sachin Pandey:** Yeah. Uh this uh if you remember

**Hemanth Sarabu:** it?

**Sachin Pandey:** the

**Geoff Horowitz:** It\'s the surrounding of an area of interest. We put
that into a different

**Sachin Pandey:** I506.

**Geoff Horowitz:** class

**Hemanth Sarabu:** Oh,

**Sachin Pandey:** So there are like

**Hemanth Sarabu:** where is that? Where is that from? Is that like a
paper or what?

**Sachin Pandey:** general.

**Hemanth Sarabu:** Where is that come

**Geoff Horowitz:** that we put it into a different class.

**Sachin Pandey:** So,

**Hemanth Sarabu:** from?

**Geoff Horowitz:** Um,

**Sachin Pandey:** so then so this is generally the

**Geoff Horowitz:** go ahead.

**Sachin Pandey:** base of the windmill and there are like like four
object like this. Generally the pattern is there will be four like four
object like this which we call AOI support next to the like

### 00:33:50

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** windmills.

**Hemanth Sarabu:** What

**Geoff Horowitz:** Why is this

**Hemanth Sarabu:** the Jeff?

**Geoff Horowitz:** not

**Hemanth Sarabu:** Do you understand?

**Geoff Horowitz:** what this class is?

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** Uh yeah. Yeah. These were so the I

**Sachin Pandey:** Uh

**Geoff Horowitz:** guess section. So hold on. There there are a few
things going on.

**Sachin Pandey:** like

**Geoff Horowitz:** He um in in the first iteration of the statement of
work, we put everything into essentially contact and non-cont,

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** right? But for but if you remember like some of
these things we tagged some of these

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** things they tagged some areas we said well this
looks like something that the model will get and some areas we said they
won\'t and so so what like

**Hemanth Sarabu:** H

**Geoff Horowitz:** a month ago or so I asked the guys to put all these
things in different classes does this make sense So, so these are all
I\'m I\'m okay with these all being different

**Sachin Pandey:** Uh like the main idea behind this was like if we we
we should classify every object

### 00:35:14

**Geoff Horowitz:** classes.

**Sachin Pandey:** in every uh similar looking different looking object
into different class. So when needed like we can merge the two into a
single class but we cannot separate it. We are we need to ask the
labelers to separate it again.

**Geoff Horowitz:** Exactly.

**Sachin Pandey:** So that\'s why like these are segregated into
different different class and like merging thing

**Hemanth Sarabu:** I see.

**Sachin Pandey:** will like get us the like merging similar looking
objects into single class will get us the idea.

**Hemanth Sarabu:** Huh?

**Sachin Pandey:** It is helpful for us because we we we saw saw the
whole picture like we are seeing this then we are like marking these as
the AI support but like model is only seeing the crop out button. It is
getting confused with this and the black patch

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** Hannah,

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** does that answer your question? Are you okay with
that?

**Sachin Pandey:** something like

**Hemanth Sarabu:** Yeah. Yeah.

**Sachin Pandey:** this.

**Geoff Horowitz:** Fine.

**Hemanth Sarabu:** Yeah.

**Sachin Pandey:** So generally like these are the changes and we will
make in the other iteration and also I also like uh going to ask the
labelers to like draw it out cleanly so the loss is

### 00:36:34

**Geoff Horowitz:** So,

**Sachin Pandey:** reduced.

**Geoff Horowitz:** so suction here\'s here\'s ultimately my question.
My question is, do you think that the model learned these new classes
appropriately for us to say for us to call this a baseline model? What
do I mean by that? I mean, do you think that um do you think that this
is the limitation of what the model can learn without modifying the
training set like you said m making the labelers go back and making this
tighter or adding synthetic data or you know do doing some something
else to the model augmentations, color corrections, whatever it is we
need to do.

**Sachin Pandey:** Uh so if if the answer is like getting most of the
out of the same data uh no like there are some other hyperparameters
which are getting much higher result on the same data which I have
shared in the first messages these ones uh like it it was trained on the
same data with all the mistakes it has and everything same
classification and one thing we did differently was the merging few
classes but like overall the matrix increased so we can Yeah.

### 00:38:10

**Geoff Horowitz:** These are improvements on the bottle, right? Which
we should do.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** I I don\'t want to minimize this. Um, do you do you
think that the pipeline is learning the new data?

**Sachin Pandey:** Okay.

**Geoff Horowitz:** Do you think that the old pipeline, the legacy
pipeline is learning the new data and without changing the
hyperparameters or anything else?

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Do you think that this is the best? Do do you think
that it\'s it\'s working appropriately? That\'s my question.

**Sachin Pandey:** I think like the pipeline is correct.

**Geoff Horowitz:** Or is there a bug in there? Okay,

**Sachin Pandey:** The issue is generally in the annotations or the data

**Geoff Horowitz:** fine.

**Sachin Pandey:** because like mainly fixing those will like uh so if
You see example like these where like glers have marked everything as
the sand ripple but like these are not the generally the patterns of
sand ripple like I uh this is more which we can

**Geoff Horowitz:** See?

**Sachin Pandey:** like say confidently like this is the centrilele but
not like these ones.

### 00:39:19

**Sachin Pandey:** So that\'s why like if we like clean the input data
more we can get much more better result. So more like putting strong uh
like the objects with strong features into a single class and removing
the one which don\'t have any strong features and

**Geoff Horowitz:** Got

**Sachin Pandey:** cleaning the data a little more will like very help
the will very helpful for

**Geoff Horowitz:** it.

**Sachin Pandey:** the model. So it is learning the data but like the
mistakes is making

**Geoff Horowitz:** Okay.

**Sachin Pandey:** the

**Geoff Horowitz:** Okay, I understand what I at least I think I
understand what you\'re saying. So, are you having the labelers go back
and correct this?

**Hemanth Sarabu:** Clear.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Okay,

**Sachin Pandey:** So the idea was to pass like multiple annotations
like the which is which which

**Geoff Horowitz:** fine.

**Sachin Pandey:** model is predicting and which they made. So they can
instead of drawing each one they can just select the better one and
remove the to speed up the

**Geoff Horowitz:** Fine.

**Sachin Pandey:** process.

**Geoff Horowitz:** Fine, Sachin. I just want you to be systematic about
this, please.

### 00:40:23

**Geoff Horowitz:** So, so I I agree that we want to make these
improvements to the model. Okay. But I\'m also interested in seeing once
we fix up this data using the same pipeline that we\'re using here, how
does fixing up the data improve results without doing all this
hyperparameter tuning, whatever. Do you understand what I\'m saying?
I\'m trying to see apples to apples.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Okay.

**Sachin Pandey:** Yeah, I get it.

**Geoff Horowitz:** Okay, guys. I\'m really sorry.

**Hemanth Sarabu:** You have you have too much power.

**Geoff Horowitz:** I need to What did you

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** say?

**Hemanth Sarabu:** The assess got too much power.

**Geoff Horowitz:** Too much power. I just I really want to be
systematic about this.

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** Uh I need to run.

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** He can you I I promised I promised Pra actually that
we\'d go through

**Hemanth Sarabu:** Yes.

**Geoff Horowitz:** the Okay.

**Hemanth Sarabu:** Yes. I want to I want to go through the generative

**Geoff Horowitz:** Uh I\'m going to start recording so that I can catch
up on it too.

### 00:41:15

**Hemanth Sarabu:** stuff.

**Geoff Horowitz:** Um, okay.

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** Sachin,

**Hemanth Sarabu:** Protection.

**Geoff Horowitz:** I will also um I\'ll also look over that that report
and maybe message you with some questions.

**Sachin Pandey:** And uh Jeff one more thing uh the split is completed
like as you said I draw the

**Geoff Horowitz:** Yeah,

**Sachin Pandey:** polygon around the data and it\'s not overlapping
anymore.

**Geoff Horowitz:** perfect. Perfect.

**Sachin Pandey:** So that is

**Geoff Horowitz:** Perfect.

**Sachin Pandey:** also

**Geoff Horowitz:** Share share an image of the of the geographic
layout, too. All right. Okay. Thanks,

**Sachin Pandey:** Okay.

**Geoff Horowitz:** guys. Bye.

**Hemanth Sarabu:** Okay, action. I I wasn\'t here Monday,

**Pratyaksh Singh:** Hello.

**Hemanth Sarabu:** guys. So, can can one of you guys like catch me up
on Monday and then let\'s jump to

**Pratyaksh Singh:** Yeah. Um,

**Hemanth Sarabu:** today?

**Pratyaksh Singh:** so Monday we discussed about the impacting model,
right? And turned out that it wasn\'t performing. It wasn\'t performing
at all. I mean like it wasn\'t performing because like the number of
data points that we had annotated data points server were very like I
think only 800 or uh 800 to,000 that\'s it.

### 00:42:51

**Hemanth Sarabu:** Okay. So, can can you tell me some something? Can
you like uh Okay.

**Pratyaksh Singh:** So,

**Hemanth Sarabu:** I I\'m trying to remember before this before in
painting you would jointly generate the image conditioned on uh target
via a bounding box.

**Pratyaksh Singh:** so it was conditioned on mask and the data

**Hemanth Sarabu:** Okay. Mask and data set. All right. Um Okay. And so
you moved from kind of this one stage joint joint uh thing to you first
generate the background and then generate the

**Pratyaksh Singh:** Yeah,

**Hemanth Sarabu:** target.

**Pratyaksh Singh:** like you know you generate the background and then
you mask out those regions where you want the object to be and your
final image is

**Hemanth Sarabu:** Right.

**Pratyaksh Singh:** the complete object. But the thing was that there
were only like 800 to,000 images for you know with what we were
expecting like with mask and stuff with object

**Hemanth Sarabu:** 800 to,000 images or 800 to,000 masks

**Pratyaksh Singh:** patches 800,000 patches

**Hemanth Sarabu:** patch. Uh again when you say patch you mean like

### 00:44:19

**Pratyaksh Singh:** with

**Hemanth Sarabu:** object.

**Pratyaksh Singh:** Yeah. option. So the image is cut into small
batches and then for in

**Hemanth Sarabu:** Uh

**Pratyaksh Singh:** painting only those images are taken which have any
object in them right so that you can condition only to generate the ones
but since the number of object in the data set are very small that that
didn\'t work very well.

**Hemanth Sarabu:** Interesting.

**Pratyaksh Singh:** So our idea was so like our idea was to use
classical machine learning and the copy The kind of augmentation that we
do to generate to generate like more annotations and

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** then to generate more annotations and then you know
train another diffusion model if need if you want you know we can we\'ll
train another diffusion model otherwise we will use that as synthetic
data I

**Hemanth Sarabu:** Yes,

**Pratyaksh Singh:** mean

**Hemanth Sarabu:** that\'s actually an interesting idea. Do you know do
you know this trick that they use where you can actually there\'s papers
about this like I saw this at CVPR apparently it\'s a very common trick
I can maybe look up one one such paper so what you can do is I might be
misremembering but basically it\'s what you said you You can copy paste
copy paste it and then you can actually

### 00:45:57

**Pratyaksh Singh:** Perfect.

**Hemanth Sarabu:** pass that image to create your latent and you
actually add a little bit of noise to that latent and then you den
noiseise it and

**Pratyaksh Singh:** Okay.

**Hemanth Sarabu:** apparently what it does is the intuition is that I
don\'t know how stable it is but apparently it\'s a common trick. Um I I
will try to look up the name of this trick. What it does is when you
create that latent fine it is it is um uh it it basically it is now you
know very stupidly it is now a latent when you add noise it becomes a
noisy latent and I I get that it sounds pretty stupid but the dinoiser
in diffusion its whole job is to make it look like part of the
distribution it knows Right. So the idea is that when you when you dn
noiseise it again, it actually won\'t produce the cut the cut paste
image you put. It\'ll produce an image that is more like in
distribution. You get what I

**Pratyaksh Singh:** I get what you mean like I I have read that you
know diffusion and VA they

### 00:47:08

**Hemanth Sarabu:** mean?

**Pratyaksh Singh:** interpolate between classes very well right so

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** it it might I can try that

**Hemanth Sarabu:** Yeah. So I if you let me give you the name of that
trick or

**Pratyaksh Singh:** out.

**Hemanth Sarabu:** actually uh actually you should just ask sad GBT
about that trick and um yeah because I I don\'t want to misquote but
I\'m like I was talking to someone and I was very surprised that this
works and they were like oh it\'s a very common trick people use.
Anyway, my point is if you if you\'re doing that already.

**Pratyaksh Singh:** Okay.

**Hemanth Sarabu:** Um, if you\'re doing cut paste already, similar
results using that trick, what does that

**Ratul Shashank:** uh uh like what you mentioned I was

**Hemanth Sarabu:** mean?

**Ratul Shashank:** trying something like that on comfy UI.

**Hemanth Sarabu:** Okay.

**Ratul Shashank:** So what I did was like uh uh I to uh

**Hemanth Sarabu:** Mhm.

**Ratul Shashank:** preserve much of the features I created a mask of
these features using a binary and inverse images and uh I tried to add
noise to those masks and then I uh superimpose those onto a background
and try to a noisy background and try to den noiseise that uh the the
problem with that was uh we uh at least I don\'t get uh images that were
much uh different than what was already uh what what the source images
was like this the image that I have shared is

### 00:49:06

**Hemanth Sarabu:** I think

**Ratul Shashank:** the result I will also share the source image

**Hemanth Sarabu:** uh okay share the share the source, but also what is
your mask? What does the mask look like?

**Ratul Shashank:** Yeah,

**Hemanth Sarabu:** And are you actually copy pasting?

**Ratul Shashank:** I have uh I have uh added everything in the

**Hemanth Sarabu:** Okay.

**Ratul Shashank:** report like the mask is basically uh I I am creating
two images. One is a binary images for the uh for the shadows and one is
the inverse binary images for the uh points which are bright. Right? So
I am adding noise in the inverse so that I can get sim uh I can get more
points more iterations on the mask. on the

**Hemanth Sarabu:** What do you mean by more iteration?

**Ratul Shashank:** inverse.

**Hemanth Sarabu:** Uh what do you mean by more iterations in the

**Ratul Shashank:** Uh like let me share a mask with you

**Hemanth Sarabu:** mask?

**Ratul Shashank:** at like this is a mask that I am creating. So if uh
if I add noise to this uh if

### 00:50:51

**Hemanth Sarabu:** Mhm.

**Ratul Shashank:** I just add random noise to this mask my I mean my
theory was if I create a mask on the original limits And then I add
noise to the mask and then add that noisy mask on the other image other
background. So I can get a similar kind of image but preserving the
features but uh different

**Pratyaksh Singh:** Can you write it down if

**Ratul Shashank:** iteration.

**Hemanth Sarabu:** Yes, Please.

**Pratyaksh Singh:** possible?

**Hemanth Sarabu:** Yeah.

**Ratul Shashank:** Uh, can you repeat please?

**Hemanth Sarabu:** Can you draw the pipeline on Excalador

**Ratul Shashank:** Just I I don\'t have the images but like this is one
of the mask that I generate from the

**Hemanth Sarabu:** One sec. One sec. Uh, sorry guys. One sec. I lost
the I lost the tab. Okay, back. Okay.

**Ratul Shashank:** So I was saying like this is one of the mask that
I\'m generating and I would heat this image to conci and I would add
noise this random noise, right? And then create another background.

### 00:53:58

**Ratul Shashank:** and superimpose this mask on that background. So
what I

**Hemanth Sarabu:** Oh, wait, wait, wait, wait, wait, wait, wait. Go
back.

**Ratul Shashank:** found?

**Hemanth Sarabu:** Go back. This is only during inference or during
training and inference.

**Ratul Shashank:** No, only during inference like I\'m I\'m trying to
find a

**Hemanth Sarabu:** Okay.

**Ratul Shashank:** way to create meaningful images.

**Hemanth Sarabu:** But

**Ratul Shashank:** So I\'m still in this step and to give you a uh like
what this is presenting

**Hemanth Sarabu:** wait, sorry. Uh before let\'s not don\'t use any
don\'t use any images.

**Ratul Shashank:** uh

**Hemanth Sarabu:** Uh I mean other images just using Excaladra. Um,
you\'re saying you have not actually fine-tuned a model on comfy

**Ratul Shashank:** Mhm. I\'ve not find I I\'ve not found a proper
workflow that would

**Hemanth Sarabu:** UI?

**Ratul Shashank:** uh create meaningful iterations like the iterations
that I get are very uh like

**Hemanth Sarabu:** What is an What is an iteration?

**Ratul Shashank:** uh like uh to like like this. This was an image.
This was an iteration.

### 00:55:27

**Ratul Shashank:** If you can see this is it was created on this. This
is the source image.

**Hemanth Sarabu:** Okay.

**Ratul Shashank:** This is the actual swath and then this was the

**Hemanth Sarabu:** Mhm.

**Ratul Shashank:** iteration. So it is preserving too many features.
Like if you can see the only meaningful difference is this uh rocky kind
of pattern in between uh

**Hemanth Sarabu:** Um but this model has it been

**Ratul Shashank:** reds uh

**Hemanth Sarabu:** fine-tuned?

**Ratul Shashank:** not as of yet because I I don\'t I because I don\'t

**Hemanth Sarabu:** Okay. Okay. Okay. Okay.

**Ratul Shashank:** have Uh-huh.

**Hemanth Sarabu:** So I just want to highlight one thing. So two
things.

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** one is this is so in that case I think what you are
doing and what I\'m saying are different things you\'re actually adding
noise to the image and you\'re so

**Ratul Shashank:** Oh

**Hemanth Sarabu:** you\'re actually adding noise to the control
variable which is the mask right and

**Ratul Shashank:** yes.

**Hemanth Sarabu:** then you\'re expecting the model to generate
something different than the source image okay that is not what I\'m

### 00:56:43

**Ratul Shashank:** Yes. All

**Hemanth Sarabu:** saying so uh I I can look it up or you guys should
look it up.

**Ratul Shashank:** right.

**Hemanth Sarabu:** What I\'m saying is you actually cut paste

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** uh into an image. convert that into a latent, noise
the latent and then d noiseise the latent. These are different things.
They\'re different pipelines.

**Ratul Shashank:** Oh,

**Hemanth Sarabu:** Uh that may also not work,

**Ratul Shashank:** I I Okay,

**Hemanth Sarabu:** but I\'m saying it\'s

**Ratul Shashank:** I understand. I understand.

**Hemanth Sarabu:** different.

**Ratul Shashank:** I I was like, okay, I understand. I I misunderstood.

**Hemanth Sarabu:** Okay. And so the idea there is very the goal there
is also very different. The goal there is if if Pratik is doing cut
paste you know the when you copy paste a patch it doesn\'t look

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** realistic first of all apparently there is evidence
that just that works but copy paste doesn\'t look real what you can do
what the idea with that workflow is when you when you convert that into
latent noise and D noiseise the diffusion model will try to make that
look realistic so It is a little bit like in in painting but it\'s not
exactly in

### 00:58:03

**Ratul Shashank:** So I have a question regarding that like we are uh
what I understood is we cut

**Hemanth Sarabu:** painting.

**Ratul Shashank:** the images into several sections and then add noise
to those sections and and then club them. Is that the process? But I\'m
misunderstanding this.

**Hemanth Sarabu:** Um, I don\'t I\'m not sure I I\'m not sure I
understand your question.

**Ratul Shashank:** Um, late Uh what I understood is we create we cut
these cut the image source image into several parts.

**Hemanth Sarabu:** No, no, no, no, no.

**Ratul Shashank:** Right.

**Hemanth Sarabu:** Let\'s let\'s let\'s uh let\'s let let\'s let
project present the idea and then I think it\'ll become

**Ratul Shashank:** Okay.

**Hemanth Sarabu:** clear.

**Ratul Shashank:** Okay.

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** Hey. Yeah. So the cut based augmentation that we
were talking about that I think gave the biggest boost in performance
the

**Hemanth Sarabu:** That is crazy.

**Pratyaksh Singh:** previous

**Hemanth Sarabu:** Even today, cut paste is still king.

**Pratyaksh Singh:** it is like it\'s

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** not

**Hemanth Sarabu:** Can you can you explain to Rul what um what uh what
this is?

### 00:59:42

**Pratyaksh Singh:** just generating I think there Is my screen visible?

**Ratul Shashank:** Yeah.

**Pratyaksh Singh:** Okay. So there is this object here, right? MJ as an
object. Let me zoom so that it\'s

**Ratul Shashank:** He

**Pratyaksh Singh:** okay. Is this visible the image as an object right
and

**Hemanth Sarabu:** Uh for me it is coming up.

**Pratyaksh Singh:** then you have a

**Hemanth Sarabu:** It\'s uh Yeah.

**Ratul Shashank:** It\'s not shooting.

**Pratyaksh Singh:** mask.

**Hemanth Sarabu:** Yeah. Yeah. Yeah. I just got it. I just got it.

**Ratul Shashank:** Yeah.

**Pratyaksh Singh:** So image A has an object here right and then this
is the mask associated

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** with that object. Now image B doesn\'t have any
annotation which which causes class imbalance and then the model has
very less number of uh you know very less number of positives to learn
from. So one thing that we do is we copy this object onto a clean image
right and we basically train the model to learn this. So even if the
object is on a different background the model can learn it and this
blend direct is what happens when you you know just copy paste it.

### 01:01:28

**Pratyaksh Singh:** So you take this image out using the mask and then
you paste it at some location. This blend direct is uh is one example
and you can see here that it is like pretty clear that you know you have
added an object here because it creates effect. There is no smooth
transition like this. Right now there\'s this blend alpha which is kind
of like Okay, scroll down more. So I was different algorithm to you know
to have it in such a way that this blending is smooth so that it is
difficult for the model to learn and it looks like you know the object
belong to that to that exact background because in the direct blending
it was like pretty. So blendify is kind of this smooth uh smooth
blending where you take that image and then uh so where you take that
object you so that it m it you know it mixes in with the background. So
it was slightly better but you know still it was pretty visible. The
best one was the best one that I got was from blend poison where you can
see that you know it has completely mixed in the where it has completely
mixed in the background and then it looks like the object is object is
object actually belongs to this background.

### 01:02:57

**Pratyaksh Singh:** or distress is this uses uh the gradient of the
image and then it it will take the gradient of the object from here and
then it will apply those gradient on this image and this is why like it
looks pretty good and this was like this wasn\'t a problem previous time
because we only had one data set because with VW like you know there was
only one background so it was it was pretty easy like this kind of these
kind of even cutmix augmentation was giving scale but at least for uh as
we have increased the data set like having a having a good bending or
you know copy pasting algorithm was supported so I was actually
exploring it and I found out that you know this poison blending was
actually and it performed the well on all of the data set for example
like if I\'ll just take the ants data set right and I will run it You
will see that uh do you see the difference here? The blend direct is
pretty clear but this poison one is like you know it just blends

### 01:04:09

**Ratul Shashank:** blends.

**Pratyaksh Singh:** into this blends into yeah background pretty even
for

**Ratul Shashank:** Um

**Pratyaksh Singh:** a complex it.

**Hemanth Sarabu:** Uh re really sorry very quickly you tried each one
of these out you said

**Pratyaksh Singh:** Yeah,

**Hemanth Sarabu:** right training a

**Pratyaksh Singh:** I no I didn\'t train a model.

**Hemanth Sarabu:** Huh?

**Pratyaksh Singh:** I was just you know visually looking at these right
for that uh

**Hemanth Sarabu:** Okay. Okay.

**Pratyaksh Singh:** so I think before I cut off like this was the task
for Wednesday that we wanted

**Hemanth Sarabu:** Got

**Pratyaksh Singh:** to use this classical to get some to get some you
know good

**Hemanth Sarabu:** it.

**Pratyaksh Singh:** baseline so we can train a model because you know
some data sets like DRN and POE they don\'t have any augmentation at all
sorry any object at all so that uh so you know That\'s about and so for
example even for

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** POE is pretty good. So like this one right but this
poison it\'s like it blends into the background. So I think it is pretty
good.

### 01:05:27

**Pratyaksh Singh:** We can I will make this code more robust like I can
add these rotation and all these augmentation of changing shape and size
of the object so that we can generate more so that we can generate more
uh more diverse objects and then we can add it to the background. Uh and
as for like the next step there are

**Hemanth Sarabu:** What the f\*\*\*?

**Pratyaksh Singh:** these mind separation right where we only have
example of one object. So I think we\'ll have to figure out how to
generate this synthetically because from all the data set they have
given us there is only one line in the whole data set. So even this kind
of augmentation won\'t work here. So I\'ll try to see if you know there
is anything that can generate this line kind of artifacts uh line
artifacts automatically and this AOI is small which is like these dark
regions. Hey, hello. Am I audible?

**Hemanth Sarabu:** Yeah.

**Ratul Shashank:** Uh-huh.

**Pratyaksh Singh:** Yeah. So, these AOI is small.

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** Uh these black objects I think I can also generate
them artificially too.

### 01:06:55

**Pratyaksh Singh:** And these ones are like these ones will be the one
that will difficult to catch because these like mostly o shape and they
the you know black or some shade of black.

**Hemanth Sarabu:** Hey, you can\'t see uh can\'t see the blended stuff.

**Pratyaksh Singh:** Uh,

**Hemanth Sarabu:** I can only see image A, mask A, image B, and

**Pratyaksh Singh:** I think I should just

**Hemanth Sarabu:** you you shared it somewhere.

**Pratyaksh Singh:** No, no.

**Hemanth Sarabu:** So okay I guess my question is you said that there
are data sets where there are no

**Pratyaksh Singh:** Um

**Hemanth Sarabu:** targets right do you have do you have an instance
where you generated this this classical uh in painting basically right
what you\'re doing um do you have an example of

**Pratyaksh Singh:** yeah,

**Hemanth Sarabu:** that oh you sharing slack

**Pratyaksh Singh:** I will share it on. Yeah, I\'ll show it on. I will
I\'ll share it on

**Hemanth Sarabu:** Okay. Okay. Okay.

**Pratyaksh Singh:** Slack.

**Hemanth Sarabu:** But what what what are you finding so far? Does it
look good or

**Pratyaksh Singh:** It looks really good.

### 01:08:07

**Pratyaksh Singh:** I think this is the real

**Hemanth Sarabu:** nice?

**Pratyaksh Singh:** data. I shared it on Slack also. I I\'ll test it
out more on different checks. Do you see this

**Hemanth Sarabu:** Yeah. Taking a look.

**Pratyaksh Singh:** image?

**Ratul Shashank:** Yes.

**Hemanth Sarabu:** It takes a little while for me to for it to load for
me. Okay. Yeah. Yeah. Let me let me pull it up on Slack. Nice.

**Pratyaksh Singh:** Uh I was Yeah.

**Hemanth Sarabu:** Oh.

**Pratyaksh Singh:** Go

**Hemanth Sarabu:** Uh, no. I think it\'s cool.

**Pratyaksh Singh:** ahead.

**Hemanth Sarabu:** Um, I Yeah, I think it\'s cool.

**Pratyaksh Singh:** Yeah. What I\'m saying is that you know this will
solve AOI big AOI support. So these big these big annotation the small
ones I was saying these kind of small augmentations like you see these
objects these small objects can you see my cursor

**Hemanth Sarabu:** Uh, I do not see your

**Ratul Shashank:** Yeah.

**Hemanth Sarabu:** cursor.

**Pratyaksh Singh:** uh you see here okay you see the uh blue band of
mask

### 01:09:44

**Hemanth Sarabu:** Yes.

**Pratyaksh Singh:** here so these small object I think we can

**Hemanth Sarabu:** Yes.

**Pratyaksh Singh:** generate them synthetic ically do where you know
you take a small small circle and just color it with something. There is
one problem with these M data set. There aren\'t a lot of examples of
minds. I think there are only two minds object that we have. So we\'ll
have to figure something out to generate them artificially with some
classical technique or otherwise I don\'t think we will be able to do

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** mindset.

**Hemanth Sarabu:** Can you drop a message on Slack asking Jeff if we
can get more mines and I will catch

**Pratyaksh Singh:** Got it. Uh this is mine.

**Hemanth Sarabu:** it.

**Pratyaksh Singh:** This is an example of mine. Again, do you see this
purple kind of is this purple this?

**Hemanth Sarabu:** Yeah.

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** Yeah. So this purple example the line like feature
line kind of features uh I\'m not sure but I think we can generate this
synthetically too. So I\'ll try that out.

### 01:11:02

**Pratyaksh Singh:** This is the next step and then the last step would
be like the as the last step till Friday I want to do is that is there
any way to transform the VW data set into the data set and the DRN or
the POE data set. So what I\'m what I\'m basically saying is that is are
there some augmentations with which we can transform between the data
set because uh the reason for that

**Hemanth Sarabu:** I

**Pratyaksh Singh:** is that you know uh I think the reason I

**Hemanth Sarabu:** see.

**Pratyaksh Singh:** want to do that is because then I can just use
these entx and all these data set all the new data that we got from them
as just the test set and then we can evaluate it

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** which I think will be more robust. And then another
thing is that if we can if we can convert it as augmentation task then
we can generate a lot more data set and that that can be

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** useful.

**Hemanth Sarabu:** Yeah. I think that\'s a good

### 01:12:07

**Pratyaksh Singh:** one als one more augmentation that I have

**Hemanth Sarabu:** plan.

**Pratyaksh Singh:** been thinking was about not only on image but on
the on the XTS directly so these watershed images right these watershed
images uh we actually these aren\'t the real images from the sona right
we interpolate to get these image and the way

**Hemanth Sarabu:** Oh,

**Pratyaksh Singh:** that The sonar work is it will like if this is its
path it

**Hemanth Sarabu:** yeah.

**Pratyaksh Singh:** will it will throw sonar in these kind of
perpendicular lines right now depending on the speed of the sonar the
distance between these line can change so I want to maybe randomly drop
some of these lines and have it as an augmentation to the data

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** set this was one and then another one was One more
thing that

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** I have been noticing is that uh the size of their
whatever this port and starboard of their scan it varies a lot like this
dimension the width of it will sometime be like you know 600 or 650
pixel and then sometime it will be like only 130 pixel so I think we\'ll
have to augment it to to train our model to be robust shaped Apart from
like the obvious augmentations that we do for It\'s

### 01:13:40

**Hemanth Sarabu:** Got it. Got it.

**Ratul Shashank:** I I think that this uh width varies according to

**Pratyaksh Singh:** just

**Ratul Shashank:** height. So we can just uh club similar altitude
images and create their sensitive data and I think then it won\'t be a
problem.

**Pratyaksh Singh:** Wow. I think I think

**Ratul Shashank:** your voice.

**Pratyaksh Singh:** Hello.

**Ratul Shashank:** Yes. Good.

**Pratyaksh Singh:** Yeah, I was saying I get what you\'re saying but
the problem with it is that for different heights we will have to get
data right. So initially I was thinking about so for example let\'s say
these images are initially

**Hemanth Sarabu:** Hey guys.

**Pratyaksh Singh:** I was thinking uhhuh

**Hemanth Sarabu:** Hey. Sorry. I need to drop um Roto. I know we
didn\'t get to your update. updates. Actually, can you do me a favor? I
uh Pratak, you guys are talking. Rul, Praty, you guys are talking. Okay.
Okay. Yeah,

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** please discuss.

**Ratul Shashank:** Mhm.

### 01:15:12

**Hemanth Sarabu:** Pratak, can you uh guide Rul a little bit and uh
once you guys are done talking, Rul just drop a post on Slack with with
your update. Um yeah yeah yeah yeah yeah. So do do me like uh

**Pratyaksh Singh:** I think I shared I was saying that I shared a
report on

**Hemanth Sarabu:** sorry.

**Pratyaksh Singh:** petrol channel regarding company.

**Hemanth Sarabu:** Yeah man, but I know I those reports are really
good. Those reports are really good. But how do I learn as much as
possible in five minutes?

**Ratul Shashank:** I would I would do one thing like uh I have created
uh multiple

**Hemanth Sarabu:** Yeah.

**Ratul Shashank:** seed images. So I would share them in uh for one
file. So it would be much more uh apparent in one

**Hemanth Sarabu:** Okay. So,

**Ratul Shashank:** site.

**Hemanth Sarabu:** so let me say something. Okay. So, the report is
good especially if I want to dig deeper. So, this is perfect for that.
But if I want to understand like like this meeting um if

### 01:16:21

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** I wanted to know hey what are you working on? What
are the highlights? Think of it as an Instagram reel and not a
documentary.

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** What does the Instagram real contain?

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** So, you actually want to start with the result.

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** I am getting something or I\'m not getting something
and this is the problem I\'m trying to solve and here\'s how I\'m
solving it. This is what I\'m going to do next. So, try to structure it
that way. And in these meetings actually even if you do that, everyone
will ask questions and you will go you will go deeper as as time
permits. we we continue going deeper, right? But you want to deliver the
most information as quickly as possible

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** in your updates.

**Ratul Shashank:** Yeah, makes

**Hemanth Sarabu:** Yeah.

**Ratul Shashank:** sense.

**Hemanth Sarabu:** So that\'s why think of it as a as a real and and
not like a like a movie or a documentary. Um once you deliver your real,
people will have questions and we will dig deeper.

### 01:17:19

**Hemanth Sarabu:** But the best way to frame your update is as a rule.
So everything at once very quickly. Um and you I would recommend if I
saw the TLDDR uh of your report. I actually tried to spend some time
looking at it.

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** Um now I have a few problems. One is here\'s my main
problem with it.

**Ratul Shashank:** Uh-huh.

**Hemanth Sarabu:** Um, my main problem with it. It makes some claims.
Three distinct approaches are now working. Um something something DRN is
fully validated for production. Something something have provisional
settings. So you know when I see that I\'m thinking it\'s either one of
two things. One because the report says it has been validated for
production. It is very high confidence that this whatever you are saying
here works works. either that or the second thing is an AI wrote it and
it doesn\'t know it

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** does it is it is falsely confident and if I see I\'m
going to think it\'s a second right more likely especially because it um
we we know LLMs do

### 01:18:44

**Ratul Shashank:** Hello.

**Hemanth Sarabu:** that so immediately my my concern becomes okay how
much of this report uh do we do we really understand and we have
conference on and how much of this port do we not? So, uh does that make
sense?

**Ratul Shashank:** Yeah, it does. Uh and to add on that uh like this
report was just on the workflow.

**Hemanth Sarabu:** Yeah.

**Ratul Shashank:** So I what I did was I first first tried to finetune
for DRM. Uh I have not done that for ent. So that\'s the problem because
I have fine- tuned for DRM. So it can produce iterations for

**Hemanth Sarabu:** Okay, great. So,

**Ratul Shashank:** DRM.

**Hemanth Sarabu:** you\'re saying that actually this is not LM being
overconfident. You\'re you you\'re actually saying that this is true.

**Ratul Shashank:** Yeah.

**Hemanth Sarabu:** Okay,

**Ratul Shashank:** Uh uh one caveat is that like as I I will share some

**Hemanth Sarabu:** very good.

**Ratul Shashank:** photos like uh these images that it creates even

**Hemanth Sarabu:** Yeah.

**Ratul Shashank:** though these uh like the features are preserved but
they are too preserved if uh if that makes sense.

### 01:19:53

**Ratul Shashank:** I will share some photos.

**Hemanth Sarabu:** Okay.

**Ratul Shashank:** So so that that is something that I think needs to
work needs to be worked on on my side.

**Hemanth Sarabu:** Yeah. Hey, and um I don\'t know if you already do
this, but it might be useful for us to share a skill on how to write
short updates. Um, so the the thing that works for me is asking this is
not a skill. It\'s just a b like a poor poor prompt. I will say write
matter of fact, be concise, use simple terms. Uh, don\'t be verbose. Uh,
follow the MEI rule, MCI framework. MECE framework um and a few other
things like that. And generally the updates are good. Uh when I say
updates,

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** I\'m asking it to talk to me about results it finds
in that way. Um but I don\'t have a skill for it. Um I wonder if
there\'s value in like all of us

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** using one skill for updates.

### 01:21:24

**Ratul Shashank:** Never that. uh shouldn\'t that be a part of an
umbrella system like each of us would would use different systems so I
think that could clash in everyone\'s own workflow we would need to
create a system for the entire team to for that to

**Hemanth Sarabu:** Mhm. No, no, no. It\'s It\'s not It\'s not uh It\'s
only at the end. Um Yeah. Or maybe maybe you\'re right. Maybe you\'re
right. I I don\'t know. I don\'t know. Okay. I I do have to drop. Um I
do have to drop.

**Ratul Shashank:** Okay, I will share a byte-size uh update that I got
for

**Hemanth Sarabu:** Yeah.

**Ratul Shashank:** DRN and I will and I I will share if I get any

**Hemanth Sarabu:** Yeah.

**Ratul Shashank:** update on the alert.

**Hemanth Sarabu:** Got it. Thanks a lot. Uh I will talk to you guys
later. Yeah. Pratika, would you also be able to share an update? I know
we discussed a few things, but um I don\'t have a good sense of where we
are, what we\'re going to do next, and what we\'ll achieve.

### 01:22:44

**Pratyaksh Singh:** Got it.

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** Okay.

**Hemanth Sarabu:** Okay. Thanks a lot, guys. I\'ll look forward to
those updates. Speak soon.

**Pratyaksh Singh:** Okay. Um

**Sachin Pandey:** Uh location set. Sorry. Hello.

**Pratyaksh Singh:** Sorry. Hello.

**Sachin Pandey:** Uh

**Pratyaksh Singh:** You

**Sachin Pandey:** just

**Pratyaksh Singh:** can

**Sachin Pandey:** validation This

**Pratyaksh Singh:** share.

**Sachin Pandey:** please validation.

**Pratyaksh Singh:** Huh?

**Sachin Pandey:** Set this use

**Pratyaksh Singh:** 91 files.

**Sachin Pandey:** name

**Pratyaksh Singh:** annotation. What\'s

**Sachin Pandey:** to the fold.

**Pratyaksh Singh:** my name?

**Sachin Pandey:** That\'s local.

**Pratyaksh Singh:** for about

**Sachin Pandey:** Page one. Page two.

**Pratyaksh Singh:** location. Uh common annotation bedro.

**Sachin Pandey:** Okay, thank you.

**Ratul Shashank:** step function.

**Pratyaksh Singh:** Um

**Ratul Shashank:** Same mask resolution 0.1 check.

**Pratyaksh Singh:** problem function. smooth

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** compared to

**Sachin Pandey:** What\'s up?

**Pratyaksh Singh:** Yeah, choose.

**Ratul Shashank:** such. course confirm.

**Sachin Pandey:** Boundaries lines

**Ratul Shashank:** Huh.

**Sachin Pandey:** file name. So uh Straight line to move.

### 01:28:14

**Ratul Shashank:** manifest.

**Pratyaksh Singh:** Okay.

**Sachin Pandey:** Push

**Pratyaksh Singh:** Primary concern

**Sachin Pandey:** and location problem.

**Pratyaksh Singh:** annotations problem.

**Sachin Pandey:** Many links lines.

**Pratyaksh Singh:** Someone say

**Sachin Pandey:** Black points mistakes.

**Pratyaksh Singh:** Very

**Sachin Pandey:** This is okay.

**Pratyaksh Singh:** well.

**Sachin Pandey:** Bye.

**Ratul Shashank:** Mag. Uh, foreign.

**Pratyaksh Singh:** Come to

**Ratul Shashank:** Mhm. How I mean

**Pratyaksh Singh:** work. Apply please. 0.1 or

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** 0.2

**Ratul Shashank:** 0.1 KB 0.2.1 Uh-huh.

**Pratyaksh Singh:** Take

**Ratul Shashank:** Uh-huh. That\'s

**Pratyaksh Singh:** increase

**Ratul Shashank:** height.

**Pratyaksh Singh:** height transform. Perform

**Ratul Shashank:** Uh-huh. Uh-huh.

**Pratyaksh Singh:** height.

**Ratul Shashank:** Uh-huh. Uh-huh. confirm

**Pratyaksh Singh:** Huh?

**Ratul Shashank:** height.

**Pratyaksh Singh:** Huh?

**Ratul Shashank:** Uh-huh. altitude.

**Pratyaksh Singh:** Where is that sensor

**Hemanth Sarabu:** Hi guys.

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** located?

**Hemanth Sarabu:** Hey, really quickly want to ask you guys a question.

**Ratul Shashank:** Amen.

**Hemanth Sarabu:** Are you So this these uh we got a Black Hole Pro
6000, right? Those GPUs are going up in price.

### 01:32:38

**Hemanth Sarabu:** Um so if we need more compute, now is the time to
get it. And as we\'re if we\'re doing more generative stuff, that might
help us. So will more compute help? Should we get it now?

**Ratul Shashank:** I think in the long run it could help.

**Pratyaksh Singh:** So, Yeah, I agree with it. I want to know like when
you ask this question, will the computer tell like are you asking it in
the next month or are you asking it in the next four or five months?

**Hemanth Sarabu:** Sorry, what what was the

**Pratyaksh Singh:** Let\'s say I was asking that when you mean will it
help

**Hemanth Sarabu:** question?

**Pratyaksh Singh:** are you asking for like the next month or are you
asking in term of like next five six months something like that.

**Hemanth Sarabu:** um because at the rate at which these are going up,
if either of those is true, we should get it.

**Pratyaksh Singh:** I think this

**Hemanth Sarabu:** Okay. I also if we can if we get this extra GPU Can
we do more experiments and learn

### 01:33:56

**Pratyaksh Singh:** Can we do more experiment and learn quicker?

**Hemanth Sarabu:** quicker?

**Pratyaksh Singh:** Uh, not immediately.

**Ratul Shashank:** I think we can do more but like yeah in the long
term like we can try a bunch of

**Hemanth Sarabu:** Okay. What do you mean by

**Pratyaksh Singh:** What I mean by not immediately is because right now
we are more of data blocked than than you know experiment or computer. I
think right now the bottleneck is that we don\'t have enough data. uh
that is true for bedrock and maybe also true for Iris but

**Hemanth Sarabu:** Oh s\*\*\*.

**Pratyaksh Singh:** uh I think I think in the next two month I I think
we should we should we should we more data at least I don\'t know about
like you know what what\'s

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** our plan with drop but at least for like in the
next few months we\'ll find a way to get get a lot get lot more data So

**Hemanth Sarabu:** Okay. Okay.

**Pratyaksh Singh:** yeah.

**Hemanth Sarabu:** Sounds good. Thanks for letting me know. I think uh
I will think on it and make a call then.

### 01:35:09

**Hemanth Sarabu:** Okay. Bye. Thanks, guys.

**Pratyaksh Singh:** Hey, one more question.

**Hemanth Sarabu:** For me.

**Pratyaksh Singh:** Yeah, sorry. So we aren\'t going to use IC\'s H1
Android and the other

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** servers, right? or are going to continue

**Hemanth Sarabu:** With We can\'t use it for bedrock for some iris
stuff. We may be able to do it.

**Pratyaksh Singh:** okay

**Hemanth Sarabu:** Okay. An issue there. Um

**Pratyaksh Singh:** for bedrock I think it\'s more it\'s more related
with data I think I think even if we run

**Hemanth Sarabu:** any

**Pratyaksh Singh:** a lot of experiment because of the data constraint
the I don\'t think the numbers will vary that much even with a lot of
parameters

**Hemanth Sarabu:** okay,

**Pratyaksh Singh:** parameters.

**Hemanth Sarabu:** sounds Good. Um, that\'s good. Okay. Uh, was that
it?

**Pratyaksh Singh:** Yes.

**Hemanth Sarabu:** Okay, perfect.

**Pratyaksh Singh:** Next.

**Hemanth Sarabu:** Thanks for

**Pratyaksh Singh:** Okay. Yeah. So, what what I was talking about was
the height of the sonar where the sonar is

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** located. See

**Ratul Shashank:** Altitude.

**Pratyaksh Singh:** here

**Ratul Shashank:** Sorry. Horizontal range. sensor. Altitude.

**Pratyaksh Singh:** Altitude

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** increase.

**Ratul Shashank:** Uh, okay. Try cut. Okay. Try.

**Pratyaksh Singh:** Use

**Ratul Shashank:** Okay.

**Pratyaksh Singh:** why experiment.

**Ratul Shashank:** Huh? V. Sh. Uh

**Pratyaksh Singh:** as a randomly. Pinkhine

**Ratul Shashank:** randomly gaps create now.

**Pratyaksh Singh:** spring line drop.

**Ratul Shashank:** G. Yes. thought.

**Pratyaksh Singh:** Then

**Ratul Shashank:** process.

**Pratyaksh Singh:** augmented

**Ratul Shashank:** Okay. Mhm. Some of you some of

**Pratyaksh Singh:** altitude

**Ratul Shashank:** you

**Pratyaksh Singh:** speed. Sorry say feel free.

**Ratul Shashank:** Okay.

**Pratyaksh Singh:** Okay.

**Ratul Shashank:** Or okay.

**Pratyaksh Singh:** Okay.

**Ratul Shashank:** Okay. Bye.

**Pratyaksh Singh:** Okay.

### Transcription ended after 01:41:30

*This editable transcript was computer generated and might contain
errors. People can also change the text after it was created.*
