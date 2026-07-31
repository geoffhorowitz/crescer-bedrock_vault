Jul 17, 2026

## Iris Sync

Invited [[Pratyaksh Singh]{.underline}](mailto:pratyaksh@crescer.ai)
[[Niveta Iyer]{.underline}](mailto:niveta@crescer.ai) [[Hemanth
Sarabu]{.underline}](mailto:hemanth@crescer.ai) [[Geoff
Horowitz]{.underline}](mailto:geoff@crescer.ai) [[Siddharth
Soni]{.underline}](mailto:siddharth@crescer.ai) [[Ratul
Shashank]{.underline}](mailto:ratul@crescer.ai) [~~[Sachin
Pandey]{.underline}~~](mailto:sachin@crescer.ai)

Attachments [[Iris
Sync]{.underline}](https://calendar.google.com/calendar/event?eid=NnNzMHVxNzk3MmJqZGVwNXFoN2J1Mjd1OTdfMjAyNjA3MTdUMTYzMDAwWiBnZW9mZkBjcmVzY2VyLmFp)

Meeting records
[[Transcript]{.underline}](https://docs.google.com/document/d/1m1YN4Dw2Mk1rElACctgRpCOzloctpM33QMo3z6bqfQU/edit?usp=drive_web&tab=t.5wyl0ym9xtgc)

### Summary

The team discussed annotation refinements for unexploded ordnance and
strategies for synthetic sonar data generation and training.\
\
**Unexploded Ordnance Training Strategy**\
The team will maintain separate labels for unexploded ordnance and small
patches to ensure data integrity. They decided to train 2 models with
these classes combined to prevent potential confusion.\
\
**Sonar Data and Metrics**\
Project focus has shifted toward balancing recall and precision to
minimize false positives from background noise. Ongoing efforts include
automating data augmentation via copy-paste methods and synthetic
generation.\
\
**Generative Artificial Intelligence Implementation**\
Researchers will leverage artificial intelligence models to create
synthetic training examples from open-source datasets. New agents will
assist in automating the curation and quality classification of these
data sources.

### Decisions

Aligned

-   **High-specificity labeling strategy selected** The labeling
    > protocol is set to prioritize maximum specificity during
    > annotation to ensure flexibility for future data regrouping.

-   **Comparative training methodology experiment** The training
    > methodology is set to run two models in parallel, one with
    > separated UXO classes and one with combined classes, to evaluate
    > performance differences.

-   **Precision included in project success criteria** The project
    > success criteria are set to include a balance of both recall and
    > precision to effectively address false positives in new datasets.

-   **Project report format standardized** The reporting format is set
    > to include a simple, high-level takeaway summary at the top of
    > every report to guide readers.

-   **Image-space augmentation approach maintained** The data
    > augmentation strategy is set to continue using image-space methods
    > to prioritize development speed over XTF space corrections for the
    > current phase.

-   **Model training data augmentation strategy** The team will adopt a
    > pre-training strategy using a large corpus of open-source and
    > synthetically generated data, followed by fine-tuning models on
    > high-quality Bedrock-specific data.

We\'ve **updated the Decisions section** using your feedback.

Let us know what you think:
[[Helpful]{.underline}](https://google.qualtrics.com/jfe/form/SV_5p6FWBVWvynleNU?isGoogler=no&isHelpful=yes)
or [[Not
Helpful]{.underline}](https://google.qualtrics.com/jfe/form/SV_5p6FWBVWvynleNU?isGoogler=no&isHelpful=no)

### Next steps

-   \[Sachin Pandey\] Split Classes: Split AOI Small Black and UXO into
    > distinct categories for training purposes.

    > \[Pratyaksh Singh\] Share Paper: Post the link to the generative
    > model paper in the Slack channel.

    > \[Sachin Pandey\] Update Report: Include a takeaway conclusion at
    > the top of the project report page to guide the reader.

    > \[Pratyaksh Singh\] Test 2D EMD: Experiment with 2D Empirical Mode
    > Decomposition to isolate wave-like components from images.

    > \[Sachin Pandey\] Add UXO Toggle: Provide a JSON file enabling a
    > toggle to view UXO classifications directly.

    > \[Geoff Horowitz\] Update Bridget: Coordinate with the client next
    > week to provide project status and show the preliminary synthetic
    > data results.

    > \[Geoff Horowitz\] Create Slide: Include a comparison panel of
    > synthetic and real world examples for the presentation.

    > \[Ratul Shashank, Sachin Pandey\] Curate Datasets: Find diverse
    > backgrounds in open source imagery to augment training.

    > \[Ratul Shashank, Sachin Pandey\] Categorize Findings: Sort
    > samples into quality levels and summarize results in a brief 15
    > minute overview for Monday.

    > \[Sachin Pandey\] Automate Research: Utilize a deep research agent
    > to search for and compile relevant sonar information.

### Details

-   **Meeting Initialization and Audio Setup**: The participants worked
    > through initial technical difficulties regarding audio
    > connectivity before transitioning into the main agenda regarding
    > data annotation and project objectives
    > ([[00:02:55]{.underline}](#section)).

-   **Annotation Class Definitions**: Hemanth Sarabu sought
    > clarification on the purpose of the numerous semantic classes
    > identified in the VW dataset, confirming that the high level of
    > specificity in labeling is intended for internal team organization
    > rather than direct model training. The team discussed that
    > consolidating these labels for training purposes is a standard
    > procedure, as regrouping categories is easier than splitting them
    > retroactively ([[00:06:36]{.underline}](#section-2)).

-   **UXO and AOI Small Black Labeling Strategy**: Sachin Pandey and
    > Geoff Horowitz discussed the challenge of distinguishing UXOs from
    > \"AOI small black\" patches, noting that current labels group them
    > together despite potential differences. The team evaluated whether
    > to split these classes to improve model performance, with Geoff
    > Horowitz suggesting that magnetic data might eventually provide a
    > distinct signature for UXOs compared to random black patches
    > ([[00:07:40]{.underline}](#section-3)).

-   **Training Strategy for UXOs**: To address the ambiguity in
    > labeling, the team decided to maintain separate classes for UXOs
    > and \"AOI small black\" objects during the annotation phase, while
    > training models with both classes combined to prevent potential
    > model confusion ([[00:11:19]{.underline}](#section-6)). Sachin
    > Pandey agreed to create a toggleable JSON classification to
    > facilitate this, with the consensus being to train two models in
    > parallel---one with the original data and one with the
    > re-categorized UXO labels---to evaluate which performs better
    > ([[00:14:53]{.underline}](#section-9)).

-   **Performance Metrics: Recall vs. Precision**: Geoff Horowitz and
    > Hemanth Sarabu clarified that the project\'s focus has evolved
    > from a prior emphasis on pure recall to a more balanced approach
    > that incorporates precision. This shift is in response to current
    > data sets that contain a higher volume of false positives,
    > requiring the model to better distinguish actual objects from
    > background noise rather than simply identifying all potential
    > targets ([[00:17:36]{.underline}](#section-11)).

-   **Future Data Context**: Geoff Horowitz emphasized that while the
    > team should continue utilizing the VW dataset, they must avoid
    > over-indexing on these objects, as future production data will
    > likely feature different contexts. The team aims to remain mindful
    > of the need for realistic object representation for the UK Royal
    > Navy demonstration ([[00:24:04]{.underline}](#section-16)).

-   **Generative Modeling and Anomaly Detection**: Hemanth Sarabu
    > inquired about the potential for using Variational Autoencoder
    > (VAE) type models for anomaly detection, where the model trains on
    > non-target data to identify anomalies. Pratyaksh Singh noted that
    > while not currently implemented, research exists on using
    > generative models as discriminative ones through fine-tuning for
    > semantic segmentation ([[00:25:20]{.underline}](#section-17)).

-   **Segment Anything Model (SAM) Evaluation**: The participants
    > discussed the utility of the Segment Anything Model (SAM). While
    > Hemanth Sarabu recalled that previous attempts to fine-tune SAM
    > were ineffective compared to their existing architecture,
    > Pratyaksh Singh clarified that their past work using SAM for
    > building segmentation had actually performed well
    > ([[00:28:56]{.underline}](#section-19)).

-   **Documentation and Reporting Standards**: Geoff Horowitz and Sachin
    > Pandey reviewed baseline results, and Hemanth Sarabu advised that
    > reports should be structured to guide the reader clearly. The team
    > agreed that summaries should address high-level questions, such as
    > whether results are reproducible, and be written in accessible
    > language to ensure the information is actionable for all
    > stakeholders ([[00:32:19]{.underline}](#section-22)).

-   **Next Steps and UXO Data Limitations**: The group noted that UXO
    > data is extremely limited, with only about 11 unique objects
    > identified across the datasets
    > ([[00:38:49]{.underline}](#section-27)). To address this, the team
    > intends to use the existing data to generate synthetic examples
    > and ensure the annotation labels are accurate for future training
    > iterations ([[00:37:14]{.underline}](#section-26))
    > ([[00:39:47]{.underline}](#section-28)).

-   **Data Augmentation Progress**: Pratyaksh Singh provided an update
    > on data augmentation, confirming the completion of object
    > copy-pasting and the generation of synthetic mine examples based
    > on cylindrical shapes and shadows. The discussion highlighted the
    > distinction between working in image space versus XTF (sonar data)
    > space, with the team agreeing to focus on the fastest methods to
    > achieve measurable improvements while exploring more complex XTF
    > corrections for future iterations
    > ([[00:43:24]{.underline}](#section-31)).

-   **Compute Scaling and Synthetic Data Generation**: Hemanth Sarabu
    > and Pratyaksh Singh discussed leveraging compute resources to
    > generate a high volume of potential synthetic data samples. They
    > explored the concept of using generative AI to create novel
    > examples that can be reviewed by humans to populate the training
    > set, rather than relying solely on traditional data collection
    > ([[00:49:57]{.underline}](#section-37)).

-   **Project Updates Summary**: Geoff Horowitz summarized the current
    > status of project tasks: copy-paste object augmentation is
    > finished, and synthetic mine generation is underway, though
    > focused primarily on elongated mines for now
    > ([[00:55:23]{.underline}](#section-41)).

-   **Sonar Metric Impact and Terminology Clarification**: Ratul
    > Shashank reported that changes to sonar altitude and speed
    > significantly impact results, whereas changes to roll have
    > negligible effects on the images. The team clarified their
    > terminology: \"mosaic\" refers to the geo-referenced raster image,
    > while \"waterfall\" refers to the raw ping data printed as pixels
    > ([[00:57:01]{.underline}](#section-42)).

-   **Mosaic Terminology and Data Discrepancies**: Geoff Horowitz and
    > Ratul Shashank clarified that a mosaic involves stitching together
    > strips of data, with Ratul Shashank noting their understanding
    > that mosaics can be created for larger areas using multiple
    > Extended Triton Format (XTF) files
    > ([[01:01:33]{.underline}](#section-45)). Regarding data
    > exploration, Ratul Shashank reported that findings are consistent
    > only when altering altitude, while sensor speed values show
    > discrepancies: files in NDX and DW directories show zero sensor
    > speed, whereas DR and PWE files consistently show approximately
    > two meters per second ([[01:03:20]{.underline}](#section-46)).

-   **Image Generation and Data Roll Impact**: Pratyaksh Singh and Geoff
    > Horowitz discussed how updating roll data in XTF files does not
    > affect already collected data during the XTF to PNG conversion
    > process ([[01:03:20]{.underline}](#section-46)). While changing
    > altitude or velocity impacts the resulting image during the
    > conversion from XTF to PNG, roll is not currently considered in
    > this pipeline ([[01:04:52]{.underline}](#section-47)). Geoff
    > Horowitz confirmed that roll generation is complete and understood
    > that the current pipeline design prevents roll from affecting the
    > output images ([[01:06:01]{.underline}](#section-48)).

-   **Presentation Planning and Synthetic Data**: Geoff Horowitz plans
    > to meet with Bridget next week to share preliminary synthetic
    > data. Geoff Horowitz proposed creating a slide deck that compares
    > original images, synthetic data added to original images, and
    > real-world examples to demonstrate the similarity between
    > synthetic and real-world results
    > ([[01:07:53]{.underline}](#section-49)). Additionally, they
    > discussed the possibility of showing model recognition comparisons
    > between synthetic and real-world examples to tell a more complete
    > story ([[01:09:26]{.underline}](#section-50)). Pratyaksh Singh
    > noted they will be traveling to Bangalore this weekend, meaning
    > the meeting will occur after Monday
    > ([[01:10:39]{.underline}](#section-51)).

-   **Strategy for Data Sourcing and Augmentation**: Pratyaksh Singh
    > suggested that the team should reduce reliance on clients for data
    > and instead look for open-source datasets to curate. The goal is
    > to focus on finding distinct backgrounds in open-source data and
    > augmenting these with the team\'s objects. Pratyaksh Singh
    > instructed the team to look for a wide variety of open-source
    > datasets, use AI tools to assess if these images can be converted
    > to match their requirements, and use generative AI models to
    > create novel examples for training
    > ([[01:11:32]{.underline}](#section-52)).

-   **Generative AI for Novel Data Creation**: Pratyaksh Singh
    > emphasized the need for generative AI models to create novel
    > images rather than just re-processing existing training data,
    > specifically aiming to avoid duplication
    > ([[01:14:00]{.underline}](#section-54)). Ratul Shashank confirmed
    > that they are using open-source models like Z image turbo for
    > generation ([[01:12:45]{.underline}](#section-53)). Pratyaksh
    > Singh advised against conditioning the model on previous images
    > and recommended splitting images into port and starboard segments
    > before generation to prevent the model from wasting capacity on
    > water column gaps ([[01:14:00]{.underline}](#section-54)).

-   **Training and Fine-Tuning Methodology**: Pratyaksh Singh detailed a
    > strategy to train models on a massive amount of open-source data
    > first to pre-train them, followed by fine-tuning on high-quality
    > Bedrock data. The team discussed that if open-source data does not
    > perfectly match the appearance of Bedrock data, it can still be
    > used for pre-training to see how the model performs
    > ([[01:16:02]{.underline}](#section-56)). Pratyaksh Singh noted
    > that if more data exists in a different format, such as watershed,
    > they may consider switching the input format to improve model
    > performance ([[01:18:04]{.underline}](#section-58)).

-   **Data Curation and AI Research Agents**: Sachin Pandey and
    > Pratyaksh Singh discussed using the existing GitHub repository of
    > curated open-source data and supplementing it with new findings.
    > Pratyaksh Singh tasked the team with categorizing data into high
    > quality (similar to Bedrock data), medium quality (convertible to
    > Bedrock format), and low quality
    > ([[01:19:08]{.underline}](#section-59)). Sachin Pandey plans to
    > set up an AI agent, potentially using Deep Research features in
    > models like ChatGPT or Gemini, to search for and curate this data
    > automatically ([[01:20:21]{.underline}](#section-60)).

-   **Reporting and Tooling for AI Research**: Pratyaksh Singh requested
    > that findings be presented in a leadership brief format that
    > allows for a quick understanding of data quality and volume in
    > about 10 to 15 minutes ([[01:22:27]{.underline}](#section-62)).
    > Sachin Pandey shared that they are testing a new harness for
    > long-running tasks, noting it performs better than previous
    > open-code methods ([[01:23:53]{.underline}](#section-63)).
    > Pratyaksh Singh suggested that team members periodically meet to
    > discuss which AI prompts and tools are effective for their
    > workflow ([[01:22:27]{.underline}](#section-62)).

*You should review Gemini\'s notes to make sure they\'re accurate. [[Get
tips and learn how Gemini takes
notes]{.underline}](https://support.google.com/meet/answer/14754931)*

*How is the quality of **these specific notes?** [[Take a short
survey]{.underline}](https://google.qualtrics.com/jfe/form/SV_9vK3UZEaIQKKE7A?confid=h9Ujbfv6FPCwzh_bcG4xDxIUOAIIigIgABgECA&detailid=standard&screenshot=false)
to let us know your feedback, including how helpful the notes were for
your needs.*

**📖 Transcript**

Jul 17, 2026

## Iris Sync - Transcript

### 00:02:55

**Hemanth Sarabu:** Hey Nice.

**Geoff Horowitz:** Hey guys, you hear

**Hemanth Sarabu:** Can hear

**Geoff Horowitz:** me?

**Hemanth Sarabu:** you. Hey such an Yeah.

**Geoff Horowitz:** Can you guys hear me?

**Hemanth Sarabu:** Can you hear us? I I don\'t

**Ratul Shashank:** Yeah.

**Geoff Horowitz:** My audio messed up.

**Hemanth Sarabu:** think

**Geoff Horowitz:** Uh, okay. Hold on. Thanks. Thanks, Emma. All right.
Can you guys hear me now? I know you can. Can I hear you now?

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** Can\'t hear anything. Oh, I think my audio is bad.

**Sachin Pandey:** Hello.

**Hemanth Sarabu:** Yeah, probably.

**Geoff Horowitz:** Great.

**Sachin Pandey:** Can I

**Geoff Horowitz:** I I don\'t know what happened, but Okay. Uh um and I
were just chatting about something. I\'d like to wrap this up for
another minute if that\'s okay with the rest of you guys. Um, so Hemmon,
you had asked last time what each of the what each of the classes here
mean, right?

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** Um and so S and I were going through this object
object this

### 00:05:06

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** um this document and I\'ll share it here. um which
goes through you know what\'s a sand ripple right sand patches in
general um like the the AOI big is the are these objects from the VW
data set he we had mentioned this before but like the the AOI supports
are these um these objects around you know around the AOI Uh yeah, I
don\'t know how to describe those better,

**Hemanth Sarabu:** Mhm.

**Geoff Horowitz:** but uh Sachin and I were talking about these UXOs.
Um and I I actually have something I want to add here, but Satchin,

**Hemanth Sarabu:** Hey

**Geoff Horowitz:** let\'s let\'s finish up. You were trying to tell me
that they\'re not all the re restart what you were saying uh to give
everybody a little context there.

**Sachin Pandey:** Yeah. Can I share my screen? It will be much easier.

**Geoff Horowitz:** Yeah, go ahead.

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** So if

**Hemanth Sarabu:** So, Jeff, uh, who wait? So,

**Geoff Horowitz:** Yeah.

**Sachin Pandey:** you

**Hemanth Sarabu:** you you\'re you\'re showing me, tell me if I get
this correct.

### 00:06:36

**Hemanth Sarabu:** You were showing me all the different classes we we
annotated. Is that right?

**Geoff Horowitz:** Correct. Correct.

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** Yes.

**Hemanth Sarabu:** And and to I guess to make sure I understand the
reason we have so many semantic classes is primarily for our own sake.
Not necessarily to train the model with those semantic classes. We might
group them, combine them.

**Geoff Horowitz:** Correct.

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** Correct.

**Hemanth Sarabu:** All right. I just Yeah. I just want to make sure
I\'m following the

**Geoff Horowitz:** Yep. Yeah. Yeah. The idea was you have it exactly
right.

**Hemanth Sarabu:** thread.

**Geoff Horowitz:** The idea was while we\'re going through and doing
this, let\'s have the labelers label with as much uh specificity as
possible. And then if we want to regroup later,

**Hemanth Sarabu:** Yeah,

**Geoff Horowitz:** that\'s way easier than trying to split it up later.
Yeah.

**Hemanth Sarabu:** understood.

**Sachin Pandey:** So KY uh small blacks are these UXO in the RN data
set. So like this was the one then next image this is the one but
similar looking objects are also present in other data sets which are
not UXOS.

### 00:07:40

**Sachin Pandey:** So like these ones which are marked here. So we mark
because they have the similar patch similar features we marked as a
single uh kind of label which is all a area of in area of in which is
small and black. So that\'s why we I didn\'t mark it as a USO
specifically. If you want like we can move all the DRN annotations to
UXO whichever all all

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** Can Yeah. Can we The ones the ones that we know from
Bedrock are UXOs.

**Sachin Pandey:** these

**Geoff Horowitz:** Can we create another category for UXOs? And I mean,
same thing we\'re discussing right now. Maybe we combine them for
training, but um

**Sachin Pandey:** test out whether the splitting will like whether it
improve improve the performance or

**Geoff Horowitz:** well I yeah so so what am I thinking here? What I\'m
thinking here is what I\'m thinking here is first of all

**Sachin Pandey:** not.

**Geoff Horowitz:** I mean ma maybe there\'s like more information that
we\'re not seeing than a model would pick up.

### 00:08:49

**Geoff Horowitz:** I I don\'t think so but you know potentially. But
also if we start including additional data like mag data for example,
right?

**Sachin Pandey:** I\'m

**Geoff Horowitz:** Some of these these UXOs may when when you fuse this
data,

**Sachin Pandey:** guess

**Geoff Horowitz:** the UXOs\'s may have a distinctly different
signature than, you know, just these random black patches in the VW data
set.

**Sachin Pandey:** okay. Uh so I will like split it into the two groups.
Uh I will include both a entr uh a small black as a uxo and then train a

**Hemanth Sarabu:** So, okay. So,

**Sachin Pandey:** model.

**Hemanth Sarabu:** let me see if I understand this target that appears
roughly the same, but they\'re in different data sets. In one data set,
it is called AO AOI small black and in the other data set, it is called
UXO.

**Geoff Horowitz:** I think that\'s our objective.

**Hemanth Sarabu:** Uh, that is our

**Geoff Horowitz:** That\'s not how it exists right now. How it exists
right now,

**Hemanth Sarabu:** objective.

**Geoff Horowitz:** Sachin, break in if I\'m misunderstanding you.

### 00:10:08

**Sachin Pandey:** Okay.

**Geoff Horowitz:** How it exists right now is that all of these are
called AOI small black.

**Hemanth Sarabu:** H,

**Geoff Horowitz:** Okay.

**Hemanth Sarabu:** but they\'re but some of them are actually UXOs.

**Geoff Horowitz:** Some of them are UXOs and we know that from Bedrock.
Some of them are not UXOs,

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** but our labelers said these also look like AOI small
black. They look the same, so they put them all in the same category.
Satchin, is that correct?

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** Yeah.

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** I\'m just going to say something. These are just
ideas and thoughts. No real assertions. But um I think to the model I
agree with what you said Jeff that once we have mag maybe there\'s more
information but without mag these are just these are small black
features right that\'s all they are it\'s unclear if they\'re actually
UXOs I don\'t think you can tell that it\'s a UXO without actually
knowing this this is a potential minefield. Could be wrong about that,
but I\'m relatively confident.

### 00:11:19

**Geoff Horowitz:** Uh, I I\'m sorry.

**Hemanth Sarabu:** In which in which case I wonder if we should

**Geoff Horowitz:** I didn\'t mean to cut you off.

**Hemanth Sarabu:** actually call it AOI small black, which is how it
appears, and have a second label,

**Sachin Pandey:** It\'s

**Hemanth Sarabu:** like a tag that says like this is a UXO. I haven\'t
thought this through, and I\'m sure this will open up a can of worms. Um
but we someone has to make a decision at some point about this right

**Sachin Pandey:** bigger.

**Hemanth Sarabu:** like uh an MLE goes and says oh this AOI small black
in a different data set is not a UXO and a similar looking object in
this data set is a UXO so we will have to combine these classes to train
the model um is you know like an Emily

**Sachin Pandey:** Thank

**Hemanth Sarabu:** making like like a deliberate decision. I think
there\'s no free launch.

**Sachin Pandey:** you.

**Hemanth Sarabu:** We we either have to do that or we call these AOI
small black but but tag is saying by the way this is a true UXO.

### 00:12:16

**Geoff Horowitz:** Yeah, I I agree with what you\'re saying, Hamoth. I
think I think that\'s what I was I I think that\'s what we\'re getting
at right now, which is even if they\'re two separate classes, we we
should because they look the same, make the decision to combine them for
training.

**Hemanth Sarabu:** Yeah, but we want traceability at some point. Like
we want to be able to say these are actually UXOs versus these are

**Geoff Horowitz:** that and and

**Hemanth Sarabu:** not.

**Geoff Horowitz:** and that\'s exactly why I\'m recommending that we
create a second class right now.

**Hemanth Sarabu:** Mhm.

**Geoff Horowitz:** Uh now could we could we keep them in the same class
and like add a tag if it\'s possible? I think it functionally does the
same thing. Um Sachin Sachin I don\'t know if you have any insights
there but

**Sachin Pandey:** uh hard part will be that because uh like they only
shared one instance of each uh unique uh UXO and the same UXO is present
in multiple areas and even in like in this image you see like two ones
But only this is the original one which they have marked and this is
similar looking thing.

### 00:13:31

**Sachin Pandey:** And the reason why labeled it because like if you
don\'t the model get confusion even like it will confusion may not
predict this in the future.

**Hemanth Sarabu:** What? What is your point?

**Sachin Pandey:** So like even in the mind fields not all like these
are uh UXOS

**Hemanth Sarabu:** Oh god.

**Geoff Horowitz:** Wait, Sasha, I don\'t understand the I think this is
what we\'re getting at, right? Is that in case we want to change this
going forward, maybe we label them separately now or or somehow tag it
separately. However, because of the reason you\'re saying, right, that
they look so similar and we don\'t want the model to get confused, we we
do put them in the same class for training right now.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** So, so I didn\'t understand the distinction

**Sachin Pandey:** So

**Geoff Horowitz:** then.

**Sachin Pandey:** we can try it out like at least for a TX and DRN we
will mark it as uh UXO but for BW we will like put it as a small black
patch

**Geoff Horowitz:** Uhhuh. But but only the ones only the ones that are
UXOs.

### 00:14:53

**Sachin Pandey:** Hey.

**Geoff Horowitz:** Right? So if you go back to the example that you had
before, only one of those is a UXO. Right?

**Sachin Pandey:** Yes.

**Geoff Horowitz:** So only the one that\'s a UXO, we say that that\'s a
UXO.

**Sachin Pandey:** Yeah, we we can get it done

**Geoff Horowitz:** Yeah.

**Sachin Pandey:** automatically.

**Geoff Horowitz:** There\'s only there\'s only like what 10 or 15 of
these these UXOs total. So I mean I I can imagine this will take us all
of five minutes.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** Is that correct?

**Sachin Pandey:** Yes. It will not take much

**Geoff Horowitz:** Yeah.

**Sachin Pandey:** time.

**Geoff Horowitz:** But then just just to be clear Sachin but for for
training purposes we combine these

**Sachin Pandey:** Uh we can like get both of them trained with all of
them combined with the single class. And uh like separated based on the
classes like UXO plus a small and see like if we see like the objects
which are a small and getting moved to or getting predicted as a AX uh
UXO then like we will know like the model is not able to learn these
like features are not strong enough to distinguish uh them

### 00:16:17

**Geoff Horowitz:** Okay. So, so what I hear you saying is let\'s
separate them. Let\'s try to train a model and just see what we get and
then if we see that the model\'s not able to differentiate

**Sachin Pandey:** Yes.

**Geoff Horowitz:** then then we\'ll we\'ll combine them for training.
Is that right?

**Sachin Pandey:** Yeah. And we can train both in

**Geoff Horowitz:** Yeah,

**Sachin Pandey:** parallel.

**Geoff Horowitz:** that seems reasonable to me. I assume you don\'t see
any issues with

**Hemanth Sarabu:** Can you um can you summarize

**Geoff Horowitz:** that.

**Hemanth Sarabu:** me?

**Sachin Pandey:** So we will train two models. One where the UXO will
be marked based on the like the data we got

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** from the like client. In other one everything will be
in AI mode.

**Hemanth Sarabu:** Okay. So one as is and one based on our grouping.

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** Sure.

**Geoff Horowitz:** Uh, okay. I think that wraps up that discussion. Um,
there\'s one thing I wanted to talk about here. Um, this has come up a
few times.

### 00:17:36

**Geoff Horowitz:** Uh, so I want to make sure we\'re all on the same
page here. Um, for the first project we were very focused on recall. Um,
and that stemmed from the conversation that Heamant and I had with
Bridget where, you know it wasn\'t a huge data set. We she she really
wanted to kind of see what we could do. Um and so the focus was was on
was on recall there. Um like it didn\'t matter much if we had all these
false positives. What the the objective now has shifted a little bit,
right? The reason that we have all of these other data sets that don\'t
have a ton of objects. So we have, you know, the the POE data set that
has this dredging going on. We have the RO data set, right? Or RO data
rather. uh you know some of these different backgrounds is because
Bedrock doesn\'t want us looking at all these things and saying well
these are all false or rather these are all positives right when they
turn out to be false positives um so so for this round I mean yes we\'re
always focused on recall and that\'s that\'s a lot of the story but I
think that precision is also a big factor here Um, again, that\'s
that\'s why we\'re trying to train on these additional backgrounds to
say that these are not objects.

### 00:19:18

**Geoff Horowitz:** Is is that clear? Questions, comments, concerns?

**Sachin Pandey:** Uh I have one question.

**Geoff Horowitz:** Yeah.

**Sachin Pandey:** So like this is for the case where the model is
separate uh distinguishing between between the like the AI small black
versus the UXO. If not then like if you are only training on AI small
black then everything in the VW data set is false

**Geoff Horowitz:** No,

**Sachin Pandey:** positive.

**Geoff Horowitz:** no, that\'s that\'s not what I\'m getting at.

**Hemanth Sarabu:** Jeff, are you generally saying you\'re saying
generally we were more focused on recall previously and

**Geoff Horowitz:** Yes.

**Hemanth Sarabu:** now the the data sets have gotten harder. There\'s
more more uh there\'s more opportunity for false positives and so we
need to pay attention to precision also.

**Geoff Horowitz:** uh similar similar I think I I\'m I\'m not yes with
a nuance. The nuance is this has come up before where we\'ve said let\'s
focus on recall but I think that Bedrock isn\'t laser focused on recall
now they\'re focused more on maybe a balance between the two more on an
F1 score more on kind of general performance does that nuance make sense
do Do you agree with that?

### 00:20:50

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** I mean, you\'ve been on these calls with Bridget,
too.

**Hemanth Sarabu:** Uh, I think I actually don\'t think she said
explicitly. My my my interpretation is what what I just said which is
look we got we there\'s this role there\'s this uh there a bunch of
rocks and so um we can\'t highlight all of these as as targets but we I
don\'t think we actually I don\'t think this is even part of

**Geoff Horowitz:** Exactly.

**Hemanth Sarabu:** the I could be wrong. I don\'t think this is even
part of the um the buy off the success criteria um that we achieve
better recall and precision but I could be

**Geoff Horowitz:** Um I I you\'re you\'re right that we didn\'t say

**Hemanth Sarabu:** wrong.

**Geoff Horowitz:** explicitly that that was part of it. uh Hemoth, you
know, that was part of at least what I got out of the conversation where
she was saying that, you know, we\'re picking up all of these false
positives and I think we we happen we h we happen to get the right one
right there.

### 00:21:54

**Hemanth Sarabu:** Yeah. Yeah. Yeah. Yeah. But yeah. But I So again,

**Geoff Horowitz:** But

**Hemanth Sarabu:** maybe we\'re saying the same thing, but my
understanding is this is just too low. You know, this is uh this is like
the precision here is like I don\'t know

**Geoff Horowitz:** yes,

**Hemanth Sarabu:** 5%, 10% dep if you count pixels,

**Geoff Horowitz:** right.

**Hemanth Sarabu:** maybe even smaller.

**Geoff Horowitz:** Yeah.

**Hemanth Sarabu:** Um so I think that she\'s saying reasonable we got
to get reasonable and even previously we needed to be reasonable um if
our precision was like 50 60% in the number of objects I think they
would be okay with that and I feel like uh that number is still

**Geoff Horowitz:** Uh

**Hemanth Sarabu:** okay and just the background has gotten more
difficult um so that\'s my that\'s my interpretation but you and I can
discuss more so

**Geoff Horowitz:** I I I think Yeah, I think I agree with you. I think
I agree with you. I mean,

**Hemanth Sarabu:** M

**Geoff Horowitz:** you know, maybe we\'re coming about this from two
slightly different angles, but but I think the effect is exactly the
same.

### 00:22:54

**Hemanth Sarabu:** yeah such projects does it make sense to you guys
what we\'re trying to say

**Geoff Horowitz:** So,

**Hemanth Sarabu:** uh it\'s actually not not not that nuanced it\'s
just we can\'t have uh precision that is that looks like

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** this.

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** right.

**Pratyaksh Singh:** This was my understanding also like you know you
can\'t predict everything. If it looks like it if there is a probability
then it makes sense.

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** For example those small back black patches they

**Hemanth Sarabu:** now. Yeah.

**Pratyaksh Singh:** make

**Geoff Horowitz:** Okay. Um, the second thing that I wanted to talk
about briefly was

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** that the VW data set, you know, includes a lot of
these uh, do I not have a picture of these? I may not have a picture of
these, but you you guys know it. uh a lot of like these types of
objects. The objective here is the objective for for kind of this whole
project is to um is for bedrock to to to show off to the UK Royal Navy.

### 00:24:04

**Geoff Horowitz:** Um as a result, I don\'t think we expect the new
data sets that they\'re having to have a ton of these types of objects.
I\'m not trying to say we should exclude these. I think we should
include them. They\'re all part of the data set that we\'re learning on.
Um, but as we go through this, I want to kind of keep in the back of our
heads that what we expect a lot of the data sets that they\'re testing
on to be uh or rather a lot of the data sets that they\'re they\'re
going to use in something akin to production is going to have contacts
that are closer looking to this. Um, again, no action item there, but I
wanted to I wanted to bring that up that, you know, we want to think a
lot about the UXOs. Um, and maybe not overindex on the VW objects.

**Pratyaksh Singh:** Understood.

**Geoff Horowitz:** Okay, those were the two items that I have been
thinking about for a while and wanted to bring up to the group. All

### 00:25:20

**Hemanth Sarabu:** Guys, I\'m curious.

**Geoff Horowitz:** right.

**Hemanth Sarabu:** Has anyone thought about training a model like a VAE
type model on just what is not a target and um and then like an anomaly
detection model. Then have you have you tried any of that those ideas?

**Pratyaksh Singh:** No, not here.

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** I think I think we can we can look into this one
few other papers that I\'ve seen coming are from using generative models
as discriminative one where the idea is that they will train a
generative model and then

**Hemanth Sarabu:** H

**Pratyaksh Singh:** they will use it they\'ll fine tune it for semantic
segmentation these cases I don\'t think

**Hemanth Sarabu:** interesting.

**Pratyaksh Singh:** Google has been doing a lot lot of these

**Hemanth Sarabu:** Can you paste that paper

**Pratyaksh Singh:** great I think that fine tune nano banana

**Hemanth Sarabu:** somewhere?

**Pratyaksh Singh:** like output on object detection setation

**Hemanth Sarabu:** Interesting. Can you post a link to it?

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** Oh, it\'s not it\'s not uh urgent.

**Pratyaksh Singh:** Right. Image generator file generally is present.

### 00:27:23

**Pratyaksh Singh:** This is okay.

**Hemanth Sarabu:** Oh, yes. I I didn\'t know that one. They find you
banana.

**Pratyaksh Singh:** I\'m not sure. I just like read what it is trying
to do. I I mean like you know just I didn\'t get into the methodology
and just looked at that. That\'s it.

**Hemanth Sarabu:** Let\'s see.

**Pratyaksh Singh:** Do you want me to research?

**Hemanth Sarabu:** Uh, it\'s your call. It\'s your call. I you know
your um your priorities so I won\'t I won\'t ask you to do it ask you
good interesting interesting yes thank

**Pratyaksh Singh:** I\'ll share the link.

**Hemanth Sarabu:** you um I was talking to someone I was talking to
someone and they said Um I told them what we were doing with uh say
Bedrock or or Boommy and they said oh do you guys fine tune SAM and I
said no we tried SAM and it wasn\'t as good as our segmentation models
and they were very surprised. It it is true, right? We tried we tried
fine-tuning SAM and we didn\'t see good results out of it at least
better than whatever architecture we\'re using which is I guess vanilla
ResNet.

### 00:28:56

**Pratyaksh Singh:** for boomie I I am surprised that it doesn\'t work
that well right for

**Hemanth Sarabu:** But you you um you tried Sam,

**Pratyaksh Singh:** bedrock I tried Sam but

**Hemanth Sarabu:** didn\'t you?

**Pratyaksh Singh:** that was you know just Sam and I tried Sam and then
it was it was doing good like it wasn\'t underperforming. Sam was doing
good.

**Hemanth Sarabu:** It

**Pratyaksh Singh:** The uh Sam was doing good dude.

**Hemanth Sarabu:** wasn\'t

**Pratyaksh Singh:** I think uh Sam was doing good as far as I remember
like it was doing very good for buildings

**Hemanth Sarabu:** I see. Well, I guess I just spread some fake news
then.

**Pratyaksh Singh:** for

**Hemanth Sarabu:** Um.

**Geoff Horowitz:** Come on.

**Hemanth Sarabu:** Um.

**Geoff Horowitz:** I hope you did it on Twitter.

**Pratyaksh Singh:** as far as I remember it was it

**Hemanth Sarabu:** What was this?

**Geoff Horowitz:** I just said I Never mind.

**Pratyaksh Singh:** was Oh,

**Geoff Horowitz:** Go ahead.

**Pratyaksh Singh:** no. No.

**Geoff Horowitz:** I I said I hope you did it on

**Hemanth Sarabu:** No, no, it\'s not. I don\'t say anything publicly
for this

### 00:29:57

**Geoff Horowitz:** Twitter.

**Hemanth Sarabu:** reason. But we we I it doesn\'t make sense. If um if
Sam was if Sam made sense for us, we would have continued using Sam. But
we didn\'t. And you did a lot of work with them. Like you you were you
were training the second stage,

**Pratyaksh Singh:** Yes.

**Hemanth Sarabu:** the final stage, keeping the embeddings the same,
etc., etc. And I don\'t know if you tried you did some caching and tried
uh right like there was a bunch of work you guys

**Pratyaksh Singh:** Uh-huh.

**Hemanth Sarabu:** did.

**Pratyaksh Singh:** Yeah. So that\'s what I am saying that you know the
it was performing

**Hemanth Sarabu:** Nothing.

**Pratyaksh Singh:** it was performing good. That\'s why you remember
the orthogonalization thing that we wrote for going from to go from the
segmentation mask to to those building polygons, right?

**Hemanth Sarabu:** Right.

**Pratyaksh Singh:** For the small mistakes that it made that that came
after Sam because like Sam was doing as far as I remember Sam was doing
good like the only

**Hemanth Sarabu:** I think

### 00:31:14

**Pratyaksh Singh:** problem.

**Hemanth Sarabu:** here\'s

**Pratyaksh Singh:** Uhhuh. Right.

**Hemanth Sarabu:** I think here\'s what happened. I think while we\'re
doing that, Sid found a paper that that multi-stage paper. I forget the
name of it. Um, and then he implemented that. Actually, you know what?
Forget it. I\'m not even going to try to remember the trajectory, but

**Pratyaksh Singh:** So are you referring to that to that

**Hemanth Sarabu:** um

**Pratyaksh Singh:** paper where they they did what was that model? I\'m
also forgetting the name of the model. Yeah, they they they did data on
on buildings specifically. Are you referring to that paper?

**Hemanth Sarabu:** yeah, they did that and they also learned the they
also learned the polygon. But sorry, hey, we shouldn\'t. This is a
distraction. I don\'t I\'m sorry for taking us down this uh down this uh
we\'ll catch up later about this.

**Pratyaksh Singh:** Okay. All

**Hemanth Sarabu:** I I do I think what is more exciting is what uh you
and are working on.

### 00:32:19

**Pratyaksh Singh:** right.

**Hemanth Sarabu:** So let\'s uh let\'s talk about

**Geoff Horowitz:** Um I I shared in the chat if anybody wants to see it
what are

**Hemanth Sarabu:** that.

**Geoff Horowitz:** mostly the end baseline results. Uh you guys can
look through that if you want to. For the for the new trained results,
obviously we don\'t have the final ones yet because um Sachin is working
with the labelers to update those uh model

**Hemanth Sarabu:** This is in the bedrock how to running notes.

**Geoff Horowitz:** in bedrock to running notes. Yeah, I think I think
it opened the right page. Uh yeah, it did. Okay. So you guys you guys
can look through that.

**Hemanth Sarabu:** Confirmation.

**Geoff Horowitz:** But um but again the the objective here is really
just to get a well number number one to make sure that we can reproduce
the results that we had which we we basically can. We basically can
we\'re around the right area. There\'s some minor differences uh to get
actually let me just show this. probably easier.

### 00:33:29

**Geoff Horowitz:** Uh so number one was say

**Hemanth Sarabu:** So Sachin you put you put this together.

**Geoff Horowitz:** what?

**Hemanth Sarabu:** Suchin put this together this page.

**Geoff Horowitz:** Yeah.

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** I just fill in the

**Hemanth Sarabu:** Hey such an I was so minor thing actually not

**Sachin Pandey:** data

**Geoff Horowitz:** Uh

**Hemanth Sarabu:** minor pretty major just um this is a question right
uh include your answer you\'re able to

**Sachin Pandey:** and we

**Hemanth Sarabu:** see all I\'m saying is include your

**Geoff Horowitz:** uh.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Okay.

**Hemanth Sarabu:** answer here in one line confirm we\'re able to
recreate um say yes mostly and then you know like one line just one line
guiding the user guiding the leader.

**Geoff Horowitz:** This this isn\'t entirely on Sachin. We were working
on this together.

**Hemanth Sarabu:** Okay. Okay.

**Geoff Horowitz:** Um but yes, Sin, I do think that\'s a good outcome
here.

**Hemanth Sarabu:** Whoever.

**Sachin Pandey:** like conclusion on the top so we can get the most
information.

**Geoff Horowitz:** Uh

**Hemanth Sarabu:** Yes. The takeaway, right? The takeaway.

### 00:34:28

**Hemanth Sarabu:** The takeaway. So,

**Sachin Pandey:** Okay.

**Hemanth Sarabu:** this is think of think of reports in in um in
multiple levels, right? This is data. This is data. It\'s a raw. It\'s
numbers, right? It\'s data. When you want to dig in into the detail,
this is where it gets important. And then at the higher level, there\'s
this question, very simple question. Can we recreate? And the answer
should be something like yes, mostly except for a couple of things. Look
for this in the data. Or no, we\'re not able to recreate. We\'re very
far from it. Something is wrong. Right? Um and then also guide the
reader. Think of the reader like uh they\'re a baby. They\'re like um
someone in fifth grade, right? Keep it really simple. Um so that is my
that is my recommendation to you.

**Sachin Pandey:** Okay.

**Geoff Horowitz:** Okay. Um, second page. The second question.

### 00:35:35

**Geoff Horowitz:** This is something that we might want to kind of
consider, but um, these results aren\'t great. Uh there\'s or question
number two

**Hemanth Sarabu:** Second page.

**Geoff Horowitz:** rather.

**Hemanth Sarabu:** Got it.

**Geoff Horowitz:** The results aren\'t great. Um, this is kind of
expected because we didn\'t train on these, uh, you know, One question
here is what\'s our what\'s our learning? What does this teach us?
Right? Um that\'s that\'s an open question.

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** Um that open question. Sorry. Um and then the third
part is so so as you know as far as I\'m concerned the first two parts
are are pretty much answered um you know except for like some open
questions. Um the first part I think I think I\'m okay that we\'re
getting pretty much the right results uh or rather the same results and
we can identify that there\'s some slight differences that could be
attributing to those. And then the third part this is really our
baseline right this should be our baseline. Um and so you know
ultimately we want to say okay this is what we think we\'re doing now
with the existing data set and the existing model then you know what are
all the ways we want to improve it.

### 00:37:14

**Geoff Horowitz:** Um so that\'s that\'s where we are there. Um, in
terms of in terms of next steps, uh, in terms of next steps, so kind of
going back to our initial whatever we call this, you know, guidelines
here. Um, we finished this kind of data review process. We more or less
finished the the reabeling. Uh, we\'re obviously going back there. We
are trying to wrap up these baseline results. Um and then Sachin you had
already started to do this but again we you know we jumped back because
we want to do a a more um I don\'t know standardized approach but you
know the next steps are certainly to see where we can improve that
model. Um and then we already know as we\'ve been talking about that we
we need to add the synthetic data uh because we just don\'t have enough
data. Um, from the recording last time, Pratia, I will ask Bridget if
she has more UXO data. Um, but I\'m relatively sure that she doesn\'t
have more data from data sets that she can share.

### 00:38:49

**Geoff Horowitz:** I I\'m pretty sure that Bridget and I had talked
about that and and Hemon,

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** you might have been on there. I think that we had
talked about that. She said, \"Look, you know, 15 examples isn\'t that
much. Can we get more?\" She said, \"I can see if I can get the Go

**Hemanth Sarabu:** Do we do we even have 15?

**Geoff Horowitz:** ahead.\"

**Hemanth Sarabu:** What what is the total number we have of actual
different

**Geoff Horowitz:** I think it\'s 7 + 4 Sachin.

**Hemanth Sarabu:** examples?

**Geoff Horowitz:** Is that right? 7 + 4 It\'s

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** Yes.

**Pratyaksh Singh:** Oh, sorry.

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** 11.

**Pratyaksh Singh:** sort of button. But aren\'t they the same

**Sachin Pandey:** Uh they shared like in uniquely there were like
around 10 11

**Pratyaksh Singh:** object?

**Sachin Pandey:** objects but they appears in multiple XTF.

**Hemanth Sarabu:** Okay, so there are actually 10 11 different objects
and they repeat themselves across the

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** D.

**Pratyaksh Singh:** I only found like one one or two example of mine.

### 00:39:47

**Pratyaksh Singh:** Where are they?

**Sachin Pandey:** But if we are like talking about the long ones, those
are like not like they may be UXO but like we didn\'t get that
information from bedrock.

**Pratyaksh Singh:** So, I looked at AOI MS, the ones that are labeled,
AOI MS, and I found one distinct example of

**Sachin Pandey:** Yeah, I I labored it as mine because I think that was
because in the last

**Pratyaksh Singh:** it.

**Sachin Pandey:** iteration where Siddhhat labeled those, it was put
into others.

**Pratyaksh Singh:** Okay.

**Sachin Pandey:** So I just put it in like that UX are mainly

**Pratyaksh Singh:** And what does are the

**Sachin Pandey:** in ENTX and DRN data set and they are mainly like a
spot on the ground not.

**Geoff Horowitz:** And they\'re they\'re small black. They\'re labeled
as small black. Right. Sum,

**Sachin Pandey:** Yes.

**Geoff Horowitz:** we don\'t have we don\'t have AOI mines here.

**Sachin Pandey:** Yeah.

**Pratyaksh Singh:** Yeah.

**Sachin Pandey:** like these are like in I just like that class was not
getting used and like there\'s a high chance that object was a like mine
but it wasn\'t like we didn\'t uh if I\'m correct uh entx we didn\'t get
any uh like that object was not in the any annotation so instead of just
putting it in the other I

### 00:41:16

**Pratyaksh Singh:** Okay.

**Geoff Horowitz:** meaning Yeah.

**Sachin Pandey:** just reclassified

**Geoff Horowitz:** meaning it wasn\'t a mine. It was, you know, a
cabinet, right? Is that what you\'re trying to say?

**Sachin Pandey:** The reason why I marked it as mine because if if you
look at the open source data the similar looking objects were marked as
mine. That\'s why that\'s the reason behind why I marked as mine.

**Geoff Horowitz:** Okay. So, Sachin, this goes back to the conversation
that we were having earlier, which is like I I think even for us it\'s
useful to, you know, if all of the AOI small blocks were not were UXOs,
right? Then, you know, to say to say this is like UXO. It\'s a problem
that they\'re not they\'re not all UXOs. So, this is why, you know,
maybe splitting them up, at least for our purposes, might be useful. But
I I I think we\'re getting a little confused on what these objects are.

**Pratyaksh Singh:** Yes.

**Sachin Pandey:** Yeah.

**Pratyaksh Singh:** then please do that because for now

**Sachin Pandey:** Yes.

### 00:42:14

**Geoff Horowitz:** Um,

**Sachin Pandey:** For UX. So I will create one

**Pratyaksh Singh:** like because for now I just

**Sachin Pandey:** another.

**Pratyaksh Singh:** took that mines\'s example and then I used it to
generate synthetic example like I was trying to generate synthetic
example of that mind like shape because I thought that was the UXO. So
please pinpoint where the UXOs are. I will try to generate synthetic
examples like that like

**Sachin Pandey:** Okay. So most of the objects a y small black intx and
drn are

**Pratyaksh Singh:** this.

**Sachin Pandey:** uxos like most of them I will there are yeah I will I
will mark the ones which are not I will create a I will add another JSON
where you can just toggle it to see the UXO directly

**Pratyaksh Singh:** Okay.

**Hemanth Sarabu:** Hey guys,

**Pratyaksh Singh:** Okay. Whatever you

**Hemanth Sarabu:** I I I need to drop um I do need to

**Geoff Horowitz:** Oh,

**Pratyaksh Singh:** do.

**Hemanth Sarabu:** drop I have

**Geoff Horowitz:** do you do you need to drop right now or do you have
10 minutes?

**Hemanth Sarabu:** five

### 00:43:24

**Geoff Horowitz:** All right, go go go ahead. give your update at least
as fast as you can and then we can we can record

**Pratyaksh Singh:** Okay. So I think I shared in the Slack channel the

**Geoff Horowitz:** the

**Pratyaksh Singh:** things that I\'ve been that we have been wanting to
do. So I\'ll just go through them and so the first thing

**Hemanth Sarabu:** Mhm.

**Pratyaksh Singh:** was uh those objects copy and pasting object which
we discussed in the previous meeting was done. Second was generating
minds example. I was able to generate those mind examples to uh four or
the third one was generating role like data. So example for role that I
was also able to do. The last part where we we can go from one data set
to another. I wasn\'t able to do that. I will see if we can do that
using XTF but for now no success there. So that\'s a short u that\'s a
short like highlight. Next I can I can show you guys images of some of
the examples.

### 00:44:36

**Hemanth Sarabu:** So, so is it okay? So, you\'ve been working on
different Oh, this is cool. This is uh This is cool.

**Pratyaksh Singh:** And for for mines it is like so for mines What I
saw was that in one one of one of the object that we had labeled and in
all the open source data set mines were basically like cylindrical kind
of object and then they had shadow on top of them. So this is what I
tried to generate. I I was successful in it but uh like you know there
are few things

**Geoff Horowitz:** Just to be just to be clear, this is all using the
same um blended pan that you were discussing last

**Pratyaksh Singh:** No no no no these are different like uh these minds
and these roles they are uh they are

**Geoff Horowitz:** time.

**Pratyaksh Singh:** generated just as an augmentation on top of the
image. So there is no second image involved here. This is just like you
know it\'s nothing it\'s like cinosidal wave like similar to that
position emitting that it is similar it is cinosidal wave and then that
is added on top of the

### 00:45:48

**Geoff Horowitz:** Mhm.

**Pratyaksh Singh:** images on on top of the image and that is just uh
what do you say like the intensity is changed according to the intensity
of the cinosid that\'s it and this is why

**Geoff Horowitz:** Mhm.

**Pratyaksh Singh:** it creates this wave kind of pattern which I think
was visible in this role data set that we examples

**Hemanth Sarabu:** Yeah. Yeah. This looks very very very much like
that. Nice.

**Geoff Horowitz:** Yeah.

**Hemanth Sarabu:** Hey.

**Pratyaksh Singh:** of

**Hemanth Sarabu:** Uh, so did you when you say cinosidal, did you apply
that role to the raw data and create this XDF or did you uh is this
something in the just the image space you added something?

**Pratyaksh Singh:** it\'s in the image space not on that stage.

**Hemanth Sarabu:** I see. I see. I see.

**Pratyaksh Singh:** I haven\'t I haven\'t solved it.

**Hemanth Sarabu:** I see.

**Pratyaksh Singh:** It\'s okay. Do you want to do

**Hemanth Sarabu:** Okay. No, that\'s good. Um, honestly,

**Pratyaksh Singh:** that?

**Hemanth Sarabu:** where I was going to go with that is if you have a
way of going from top to bottom at the XTF, is there a way to like
actually correct for sonar roll um via the XTF compensate um and make it
look the same?

### 00:47:06

**Hemanth Sarabu:** But if you\'re doing this in the image space, you
can\'t actually do the inverse, right? So, it\'s um it\'s okay.

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** There are actually some interesting algorithms that
can take the second one and get the first one out. It is you remember
EMD,

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** right? We we played with it.

**Pratyaksh Singh:** You were discussing it on the call.

**Hemanth Sarabu:** Yeah. You So EMD works really well for like uh time
like a time 1D signing time series. There are two two dimensional v uh
variants. Uh they can work on images. Um, I\'m not saying you should try
it, but it was just I\'m just curious that that could help us like
actually isolate the

**Pratyaksh Singh:** What?

**Hemanth Sarabu:** these wave wave like components out.

**Pratyaksh Singh:** Got it. Yeah, I will I will try it out. Like uh
till now my experiments have had been on.

**Hemanth Sarabu:** Try that if it\'s fun. Yeah. Yeah.

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** Go on.

### 00:48:09

**Hemanth Sarabu:** Uh uh I\'m not saying XDF.

**Pratyaksh Singh:** So till now my experience had been no I I was I was
going to move to

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** XF but like I like you know throughout the life
cycle of this project I never worked with XF. So I\'ll have to spend
some time learning about it. That\'s why like I I delegated it

**Hemanth Sarabu:** It\'s look I you make you know

**Pratyaksh Singh:** to

**Hemanth Sarabu:** make the just make whatever you think is the best
call. I\'m not saying you should do one or the other. Um I think Jeff we
I think speed is more important. Speed and we don\'t want to be too
hacky and I don\'t think what you\'re doing is hacky. I think that\'s
pretty good. Um, I think whatever is fastest to get some results, to get
some improvements and deltas is most important.

**Geoff Horowitz:** Mhm.

**Hemanth Sarabu:** So, if your XDF corrections is going to take time,
let\'s just do what you have. That\'s that\'s that looks pretty
convincing,

**Pratyaksh Singh:** Yeah.

### 00:49:05

**Pratyaksh Singh:** No,

**Hemanth Sarabu:** right?

**Pratyaksh Singh:** with XTF like there are a lot more things that you
can do which is which is like a real use case which we discussed
previously that like what if velocity changes those things you can\'t do
in MS space what if the altitude of the sonar changes.

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** So those things you\'ll have to do in XDF space
only.

**Hemanth Sarabu:** Nice.

**Pratyaksh Singh:** So yeah I will play I I\'ll go into those space cuz
I think till now we have enough things to add as augmentation to the
data set and probably see some

**Hemanth Sarabu:** All right,

**Geoff Horowitz:** Nice.

**Hemanth Sarabu:** let\'s

**Pratyaksh Singh:** improvements.

**Hemanth Sarabu:** go.

**Geoff Horowitz:** Yeah. I I I guess we could do it all at once, but I
really want to make sure that we have these baselines.

**Pratyaksh Singh:** Uh yeah makes sense.

**Geoff Horowitz:** Um Yeah.

**Pratyaksh Singh:** I think it\'s it\'s not I think that this is one of
the thing I learn probably better to do one thing at a

**Geoff Horowitz:** Yeah. Well,

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** time.

### 00:49:57

**Geoff Horowitz:** yeah, there\'s a balance. How do you work fast and
do one thing at a time? I don\'t think you can but you know at least
being systematic about our

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** Makes sense.

**Hemanth Sarabu:** What is the iteration time?

**Geoff Horowitz:** approach.

**Hemanth Sarabu:** So let\'s say you have three different data
augmentation ideas and you\'re going to train three different models.
How long for each model to train and for us to determine whether
there\'s an improvement or not?

**Pratyaksh Singh:** Uh, do you have an answer for it for I think
usually it would be like two or

**Hemanth Sarabu:** That is amazing.

**Pratyaksh Singh:** three.

**Hemanth Sarabu:** That is amazing. All right. So you can actually test
all of these out in a day on because you have the augmentation pipelines
ready.

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** All right. Amazing. Not only just not only test all
of these out, you can also do combinations it seems.

**Pratyaksh Singh:** Yeah. Yeah. Uh that\'s why you know you when you
asked about I said right now we are logged on data like we don\'t have
enough data it takes you know 2 minutes 2 or 3 minutes to to do one eo
on one GPU right uh we have six in

### 00:51:08

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** parallel it\'s

**Hemanth Sarabu:** Yeah. Okay. Very cool. You know, Andre Karpathi, he
thinks at a very like abstract level, right? He would say, \"Oh, if you
don\'t have enough data, it\'s now you do compute scaling.\" Like, how
do you generate more data with compute?

**Geoff Horowitz:** Emma, this is what Gil said.

**Pratyaksh Singh:** How do you do more data than how do you generate
more data with compute?

**Hemanth Sarabu:** So there\'s a couple ways to think about it. One is
you be like, \"Andre Karpati, shut up. You\'re not making sense.\" And
the other way is um with coding agents and with like GPUs that we have,
can you actually generate 100 different candidates for similar looking
imagery and have a human go through that and say, \"Yeah, yeah, this
this is a good image that can go in the data set. It\'s synthetic.\" Um
and then or or not, right? So you still have to someone needs to inject
information someone needs to inject signal. If you take that if you
think the coding agents and the and your GPUs are good at generating a
lot of a lot of samples and let\'s say our labelers are looking at each
sample and saying yeah this should go in the data set because it looks
like it could be useful.

### 00:52:36

**Hemanth Sarabu:** That is a way to instead of going and collecting
data, you\'re using compute to generate many many possible samples and
filter through them using humans. So that is that is one way to make
that less abstract.

**Pratyaksh Singh:** Thank

**Hemanth Sarabu:** Um which which is actually what we are doing,

**Pratyaksh Singh:** you.

**Hemanth Sarabu:** right? uh you\'re you\'re actually trying to figure
out how to generate these augmentations and um you you know you\'re
looking at them testing if the model improves. So in some ways it is uh
it is a it is an extreme an extreme version of what you\'re doing. Not
so

**Pratyaksh Singh:** No, no, no. I agree with you.

**Hemanth Sarabu:** tall.

**Pratyaksh Singh:** I agree with you there. I agree with you. I\'m just
thinking about can we leverage generative AI today like these image
models to generate

**Hemanth Sarabu:** Yeah. Yeah.

**Pratyaksh Singh:** just novel novel with. Novel examples like these
are just augmentation on top of it,

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** right? We can we can do something like that or
there are a lot of open source data.

### 00:54:02

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** There is a lot of open source data. But the thing
is that uh the problem is that they are with a higher frequency imagery.
So the image is much higher resolution than what we usually have. Is
there go is there a way to get it to the resolution that we want

**Hemanth Sarabu:** But down sampling is pretty easy, right?

**Pratyaksh Singh:** looks they are like very different I didn\'t let me
show an example I I\'ll just share

**Hemanth Sarabu:** I I do have to run pro uh projection to I\'m going
to ask I\'m going to ask a direct question. Have we generated any new
data that uh that would be cool to show off right now and you show some

**Pratyaksh Singh:** Uh, not

**Hemanth Sarabu:** Okay,

**Pratyaksh Singh:** yet.

**Hemanth Sarabu:** cool. Anything?

**Ratul Shashank:** I have not addressified with N

**Hemanth Sarabu:** Okay, that\'s fine.

**Ratul Shashank:** data.

**Hemanth Sarabu:** I see. Okay, that\'s all right. In that case, uh
I\'m going to jump off now. Um, I\'ll talk to you on Monday.

### 00:55:23

**Geoff Horowitz:** Thanks. Uh, okay. Project. I want to make sure I got
this right. So, copy and paste objects. Uh, this this you this you said
is done, right? Yeah. Okay.

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** artificially generate mines. Uh this was one one
thing that you just showed,

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** right? the

**Pratyaksh Singh:** This was one thing that I showed and that one I
need to look at the UX only because

**Geoff Horowitz:** allong.

**Pratyaksh Singh:** currently I\'ve only generated for the elongated
miles.

**Geoff Horowitz:** So, and I\'m going to ask you one thing generated
for vines. These were in open source, right?

**Pratyaksh Singh:** Yeah, these are in open source and one

**Geoff Horowitz:** I don\'t think it\'s I think it\'s it\'s actually
good to show uh we can show it to Bridget

**Pratyaksh Singh:** intake.

**Geoff Horowitz:** but Oh, and you said one in uh Okay. Uh, no success
so far. What was you guys were discussing this at the end of the last
call I think artificially change velocity and amplitude.

### 00:57:01

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** Um anything to discuss

**Pratyaksh Singh:** Nothing.

**Geoff Horowitz:** there

**Ratul Shashank:** Yeah. So I I have like I have a few examples of uh
changing altitude and role and like a couple of uh metrics and I have
shared a presentation like uh cramming it what changes what major
changes like every every metric brings. To sum it all up, uh altitude is
a major altitude and speed. Uh it is it brings much higher changes than
any other. We don\'t get uh by changing role there is no uh visibly uh
there is no much there\'s no difference like in images there is no
difference.

**Geoff Horowitz:** virtual.

**Ratul Shashank:** uh uh

**Geoff Horowitz:** Did you say by changing the role there\'s no
differences in the

**Ratul Shashank:** uh like it is not very apparent in the image.

**Geoff Horowitz:** image?

**Ratul Shashank:** Yes. Uh I have shared a presentation and in that you
can see the

**Pratyaksh Singh:** Yeah, just it makes sense because we don\'t use the
rule to generate the

**Ratul Shashank:** role.

**Pratyaksh Singh:** image.

**Ratul Shashank:** Yeah.

### 00:58:31

**Pratyaksh Singh:** So we don\'t do ro correction.

**Ratul Shashank:** role affects as far as I have seen role does not
affect mosaics role affects waterfall as far as the images and the
examples that I have seen we don\'t get uh even in huge uh like if the
role is very extreme I think we can see a few waves but that is very
rare in mosaics we don\'t get much friends the role is high or not. So
that

**Geoff Horowitz:** Oh, we\'re not using Maybe I missed something here.

**Ratul Shashank:** is

**Geoff Horowitz:** We\'re not using the mosaics.

**Ratul Shashank:** we are using mosaics we are not using waterfall.

**Pratyaksh Singh:** Hey uh Jeff with mosaic I think he he means the
images the final

**Geoff Horowitz:** Yeah.

**Ratul Shashank:** Yeah,

**Pratyaksh Singh:** image at

**Ratul Shashank:** I mean the images like the what we are

**Pratyaksh Singh:** least

**Ratul Shashank:** using.

**Pratyaksh Singh:** for the MLS that we use for training data ratul is
solving them them as that\'s

**Geoff Horowitz:** Um,

**Ratul Shashank:** Yeah.

**Pratyaksh Singh:** it.

**Geoff Horowitz:** okay. So, so this this we\'re calling mosaic.

**Ratul Shashank:** Yeah, this is Uh, this is mosaic.

### 01:00:02

**Geoff Horowitz:** Um,

**Ratul Shashank:** It\'s a waterfall.

**Geoff Horowitz:** okay.

**Pratyaksh Singh:** So I think he wasn\'t there when we had image of

**Geoff Horowitz:** This is a water policy.

**Pratyaksh Singh:** Mojax.

**Geoff Horowitz:** Okay.

**Pratyaksh Singh:** the back side of the

**Geoff Horowitz:** What uh Rachel,

**Pratyaksh Singh:** screen.

**Geoff Horowitz:** what what\'s the difference between the mosaic and
the waterfall then? Why is this a mosa a mosaic and this is a

**Ratul Shashank:** uh like mosaic is

**Geoff Horowitz:** waterfall?

**Ratul Shashank:** a geo uh mosaic is a raster. we uh uh and waterfall
we are basically printing the data of

**Geoff Horowitz:** Uh-huh.

**Ratul Shashank:** ping uh as the pixels. So for mosaics we the a the
axis are the georreerence xy ning and east right but for the waterfall
we we don\'t use uh geo reference access we just uh on the yaxis it\'s
usually the range or the ping

**Geoff Horowitz:** Wait,

**Ratul Shashank:** samples and on the x-axis is the ping indexes.

**Geoff Horowitz:** got it. Okay.

**Ratul Shashank:** Yes.

**Geoff Horowitz:** Okay. All right. So, so is that the terminology
we\'re using?

### 01:01:33

**Geoff Horowitz:** I think we should use something other than mosaic
just because you guys know that\'s a different thing. Um, uh, Ro, just
to give you a sense, these these are what Bedrock calls mosaics, which
are like stitched together. Um, I don\'t know. Strips, whatever. Does
that make

**Ratul Shashank:** uh it does uh I mean I what my understanding was
like we

**Geoff Horowitz:** sense?

**Ratul Shashank:** can create mosaic of a bigger area. That\'s what I
thought like this particular example is a mosaic of just one XPF and the
example that you previously showed it is a mosaic of a bigger area.

**Geoff Horowitz:** Okay.

**Ratul Shashank:** So that was my

**Geoff Horowitz:** Okay.

**Ratul Shashank:** understanding.

**Geoff Horowitz:** Um. Uh. Okay. I don\'t think this is so urgent, but
I guess if everybody knows what we\'re talking about, that\'s not a big
deal. Um, virtual. I I lost the thread that we were talking about

**Ratul Shashank:** I mean uh just to summarize it uh we have tried uh

**Geoff Horowitz:** before.

**Ratul Shashank:** changing values of the explorf data and and the the
meaningful results that we have found are only are basically on the
altitude.

### 01:03:20

**Ratul Shashank:** If we change altitude, we get different results and
speed and yes I there is uh and I need to uh like

**Geoff Horowitz:** Oh, that\'s right.

**Ratul Shashank:** when I was investigating this I found that uh the
XTFs in ENTX and VW I don\'t know why but their sensor speed is showing
zero. I don\'t know why that is but for the all the files in NDX and DW
their sensor speed is showing zero and for DR and PWE have a consistent
sensor speed of two something m/s

**Geoff Horowitz:** Wait. Uh, let me take a step back. Project. I mean,
this this is an example of role affecting the mosaic. So, how are we
saying that the role doesn\'t affect the mosaic?

**Pratyaksh Singh:** It it affects uh let\'s see there are two things
right what we are doing is we are we have

**Geoff Horowitz:** Yeah.

**Pratyaksh Singh:** a PNG file and then we are renaming it as JPEG.

**Geoff Horowitz:** Uh-huh.

**Pratyaksh Singh:** We\'re changing it its extension JP easy. Right? So
the PNG file doesn\'t change.

**Geoff Horowitz:** Uh-huh.

### 01:04:52

**Pratyaksh Singh:** It\'s just it\'s it\'s the name that just changes.
Right?

**Geoff Horowitz:** Okay.

**Pratyaksh Singh:** So what we are currently doing is we have the XTF,
right? And in the XTF you update the value of the rule, right? just
updating the value of the rule won\'t affect won\'t affect the collected

**Geoff Horowitz:** Ah,

**Pratyaksh Singh:** data.

**Geoff Horowitz:** I understand what you\'re saying

**Pratyaksh Singh:** No. Now for things like altitude,

**Geoff Horowitz:** now.

**Pratyaksh Singh:** you actually consider it when you convert from XPF
to image. So that\'s why when you change the altitude or when you change
the velocity, then these things change. Does it make sense?

**Geoff Horowitz:** It it does. Let me let me repeat it back to you. So
what you\'re saying is that um if if the image was regenerated from the
XTF entirely, right, including the RO data, uh it it would I mean in
this hypothetical situation where where the you know we\'re there in
collection and we They the AUV roll more, right? That would end up
changing the image.

### 01:06:01

**Geoff Horowitz:** But because of the way that the X the XTF toPNG
conversion works,

**Pratyaksh Singh:** Yes.

**Geoff Horowitz:** RO isn\'t um RO isn\'t considered in that
conversion. And that\'s why in our pipeline,

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** it\'s not going to affect anything.

**Pratyaksh Singh:** Exactly.

**Geoff Horowitz:** Yes. Okay.

**Pratyaksh Singh:** So that is what has been for role uh for role

**Geoff Horowitz:** Yeah, I

**Pratyaksh Singh:** correctness right that is is there a way that we
can correct this role so that it looks

**Geoff Horowitz:** understood.

**Pratyaksh Singh:** much much similar to what we usually work

**Geoff Horowitz:** I follow you. Thanks for walking me through that.
Okay.

**Pratyaksh Singh:** Don\'t.

**Geoff Horowitz:** Um, so and then roll can be we we we have
successfully generated a roll. So that one\'s done too. Okay, I think I
just have one other um uh I\'m going to try to connect with Bridget next
week. Um, okay. Uh, I\'m going to try to connect with her next week and
I don\'t know, at least keep her updated.

### 01:07:53

**Geoff Horowitz:** Um, I will ask her if she has more UXO or mind data.
She she did mention that maybe she would, but um project I think it
would be good to show her some of the preliminary synthetic data that
we\'re that we\'re seeing. Um,

**Pratyaksh Singh:** Got

**Geoff Horowitz:** specifically specifically

**Pratyaksh Singh:** it.

**Geoff Horowitz:** um Let\'s add a new slide here. Um, synthetic data.
So specifically what I can imagine is something like um you know
something and doesn\'t well you know where we have like um where we have
just like you had here original

**Pratyaksh Singh:** You\'re sharing your screen.

**Geoff Horowitz:** image Sorry.

**Pratyaksh Singh:** I think I can only see your dog.

**Geoff Horowitz:** Sorry, can you see it now? You have original image,

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** you have um you know synthetic added to original
image. But then the only other thing that I can think of is adding
another panel here that shows um uh like real world example.

**Pratyaksh Singh:** All

**Geoff Horowitz:** And then what that what that would help us do is
just say say to her,

### 01:09:26

**Pratyaksh Singh:** right.

**Geoff Horowitz:** look, you know, you can you can really see that the
synthetic data in the real world example, they look really really
similar, you know. Um, and so that just helps tell the story a little
bit more. Um, and then I guess if we get to that point, you know, we we
could this is not critical. This this I would really like to show her
what I what we see here.

**Pratyaksh Singh:** Georgia.

**Geoff Horowitz:** But uh the other thing that we could show if we have
it is um I don\'t even really know how to describe this but I\'ll just
make a little box which is um model recognition of real world example
and then you know showing showing the model recognition of the synthetic
example too. I I don\'t I don\'t really know how that would look without
seeing it. But that\'s something else that you know we could show hey
look and the model sees this and it really identifies it in the same way
that it identifies the real world example. So that maybe have something
like that but not

### 01:10:39

**Pratyaksh Singh:** Okay. All right. Okay.

**Geoff Horowitz:** very

**Pratyaksh Singh:** Uh when do you need this?

**Geoff Horowitz:** this one I\'ll I\'ll update you. I haven\'t um I
haven\'t set a time with her.

**Pratyaksh Singh:** Okay.

**Geoff Horowitz:** She\'s at a conference this week,

**Pratyaksh Singh:** So, it\'s after Monday,

**Geoff Horowitz:** but uh Yes.

**Pratyaksh Singh:** right?

**Geoff Horowitz:** Yeah. Yeah. Definitely after Monday.

**Pratyaksh Singh:** All right.

**Geoff Horowitz:** Probably later next week is my guess.

**Pratyaksh Singh:** All right. Yeah, I\'ll be traveling this weekend.
So that\'s why I wanted to know otherwise I\'ll do it on Monday.

**Geoff Horowitz:** Okay. Where you off to?

**Pratyaksh Singh:** Uh I\'m off to Bangalore.

**Geoff Horowitz:** With your

**Pratyaksh Singh:** Yeah. With my friends.

**Geoff Horowitz:** friends.

**Pratyaksh Singh:** Actually there there is going to be some
construction at my home

**Geoff Horowitz:** Oh,

**Pratyaksh Singh:** and Yeah.

**Geoff Horowitz:** so you\'re getting out of

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** there.

**Pratyaksh Singh:** I\'m going to stay here for that.

**Geoff Horowitz:** That was the last thing that I had to say.

### 01:11:32

**Geoff Horowitz:** Uh, anything else that you guys want to bring

**Pratyaksh Singh:** Hey, one thing I want is something that Hmon
brought up,

**Geoff Horowitz:** up?

**Pratyaksh Singh:** right? That we are always going to be crying about
data and and it\'s not reasonable to to like to trust our client to
provide us that.

**Geoff Horowitz:** Mhm.

**Pratyaksh Singh:** So Ratul and Sajin if you have time can one of you
look at all the open-source data. I said and now we actually don\'t care
about the object that much. We care about distinct backgrounds, right?
We care about distinct backgrounds and then we can add the object
ourself. So look at like wide variety of opensource data set and for
each of those data like paste some examples from our data set and some
images from that data set and ask like chat GPT or whatever AI tool that
you\'re using that if you know this image can be converted into that
image that kind of thing or if you know if you can find some so my point
being is that we want to get a large data and we also want to get data
which match which is with the distribution that bedrock gave us.

### 01:12:45

**Pratyaksh Singh:** So and and let\'s let\'s try to see if we can find
images in the open source that that you know that has it and then I
think we can augment our training with it and then another thing is that
you know just download any generative AI models and like I think flux is
one option and then give it some example and then ask it to generate
more examples like it. Right? And then we can have the labelers you know
if it is generating because I tried it with Quen Quen wasn\'t able to
generate similar example it was just for this but if there are some
other AI models that can generate these examples let\'s generate a lot
of these examples and then just you know have it QCed by the labeler
with just a simple yes or no annotation if you know if this this looks

**Ratul Shashank:** I I I think I uh that process on my end is almost
90% complete because uh I have been using uh an uh we open source uh
model Z image turbo and all the images that I have shared with you they
are all generated Ed and it is doing.

### 01:14:00

**Pratyaksh Singh:** No.

**Ratul Shashank:** It is uh

**Pratyaksh Singh:** So, so what you are doing is something different
like you\'re conditioning and noising the image image and then you are
generating

**Ratul Shashank:** good.

**Pratyaksh Singh:** a different image from it. So it is much similar to
the image that we that we have in the training set right?

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** Do you get I want I want it to go wide.

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** I want generative model to go wide similar to what
we will see in the real world like I want it to generate novel images
not images that are already part of our data set right because our data
set already has a lot of

**Ratul Shashank:** Okay.

**Pratyaksh Singh:** duplication like you know for each of the for each
location

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** is captured by six or seven xt essentially we have
a lot less data than we know so I want the model to go file and I want
it to generate some novel images, right? So don\'t condition it on the
previous image like you know don\'t don\'t try to noise it and then ask
it to reconstruct like if you\'re noising it noise it heavily.

### 01:15:08

**Ratul Shashank:** Okay, I understand

**Pratyaksh Singh:** So you know I want those kind of things where you
know people give it an image and then they will ask

**Ratul Shashank:** that.

**Pratyaksh Singh:** it to write a description for that image and then
with that description you feed it to text to image model and you ask it
to generate a new image only right those kind of things and

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** don\'t do it for the complete image at once like
split the image into port and starboard and then ask it to generate
because when you give the complete image you

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** are like I think at least 30 to 40% of the image
are just you know those those gaps the water column right where the
model is wasting capacity so I would ask you to just you know just just
feed it the port or starboard image and then ask it to generate examples
like this like that does it make sense

**Ratul Shashank:** Okay. Yes.

**Sachin Pandey:** So it will be a mixture of uh both data like open
source and like better data also.

### 01:16:02

**Ratul Shashank:** I

**Sachin Pandey:** Oh,

**Pratyaksh Singh:** So uh for for the generative AI stuff I want it to
be like bedrock data, right? Yeah. I want it to be I don\'t want them to
give them open source data too

**Sachin Pandey:** generating

**Pratyaksh Singh:** because you know if it works it\'s good but if it
doesn\'t work you know they uh if you share that they would be expecting
us to be like you know uh they would be expecting us to perform good on
open source data too which I think which is just added complexity on the
process and added work from our end. So I want the open source data so
that I can augment it in training. So one of the thing that I\'ve been
thinking is that initially like I will train it with huge amount of data
and then I will just fine-tune it on a small small bedrock data only
right so similar to something like you

**Sachin Pandey:** like finding finding annotation.

**Pratyaksh Singh:** know now it doesn\'t matter like don\'t

**Sachin Pandey:** ation for images will be added.

### 01:17:08

**Pratyaksh Singh:** find annotation right don\'t find annotation just
find uh if the image

**Sachin Pandey:** Just the

**Pratyaksh Singh:** looks something like bedrock then it\'s good like I
would I would again like you know even if it doesn\'t look like

**Sachin Pandey:** image.

**Pratyaksh Singh:** bed roll just make a note of it at very high
resolution we might want to down sample it to lower resolution this and
that if there is any way we can convert it that is also fine if we
can\'t convert it that is also fine I still want to feed it to the
training and see what happens right does it make sense

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** so think of it like you know like similar to these
uh similar to like these

**Sachin Pandey:** Yes.

**Pratyaksh Singh:** LLMs any of these big models are trained that we we
are going to collect s\*\*\* ton of data. We are going to first
pre-train it. Once you pre-train it, then we will fine-tune it on the
high resolution bedrock data high or high quality of data that we have.
So if we have a lot of data, we can try things like this.

### 01:18:04

**Pratyaksh Singh:** Does it make sense? So we can like pre-train it
without any

**Ratul Shashank:** Yeah,

**Pratyaksh Singh:** annotation.

**Ratul Shashank:** I got it.

**Sachin Pandey:** And im image doesn\'t look to be like a similar set
of images like because most of the images in on the images from sidescar
will be like waterfall images with the distinct like yellow colors you
know

**Pratyaksh Singh:** It\'s fine. You can convert yellow to black, right?

**Sachin Pandey:** Like yellow is not the problem. The waterfall is the
problem.

**Pratyaksh Singh:** That is okay. So see our bottleneck is data, right?
Our bottleneck is data.

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** So and it\'s our choice that we are using geio
referenced image. We can shift to watershed image and then you know we
can shift to water side image. If more data is present in water set then
we can we can change our we can feed watershed to our model and see how
it performs right.

**Sachin Pandey:** Okay,

**Pratyaksh Singh:** So yeah, uh what I

**Sachin Pandey:** like first thing will be the like the the GitHub
which we have which already contains like a lot

### 01:19:08

**Pratyaksh Singh:** would

**Sachin Pandey:** of opensource data which is like curated

**Pratyaksh Singh:** h Yeah.

**Sachin Pandey:** Yeah.

**Pratyaksh Singh:** So go through that GitHub and then for each of the
each of the data set try to like download I think I will just suggest
this download all the data and then for each of the data for each of the
data set move them into like move them into two or three two or three
classes are high quality data. High quality data means that are they
very similar to the data that bedro gave us. Medium quality something
that we can convert to what bedro gave us. Low quality completely
different from bedro. Add add three or four images on a on the slide or
on the tool that you have so that it is easier for us to visualize also.
Right? And then once that once that repo is exhausted,

**Sachin Pandey:** Yeah.

**Pratyaksh Singh:** I will suggest you know uh Google it also because
there was this uh I found a website which has a lot of sonar data which
I I just found by googling it that opensource sonar data and there was
this paper where you can just download the zip and stuff.

### 01:20:21

**Pratyaksh Singh:** So those places also just find it you know if
we\'ll have data we can we can try a lot of things. So let\'s try to
have that data and then we can decide. Similar to like the way that we
have annotation. Similarly, we can try different mix of data and then we
will see what works, what

**Sachin Pandey:** Okay,

**Pratyaksh Singh:** doesn\'t.

**Sachin Pandey:** like I will set up a agent to just go search the
internet and curate I think then we will like going through the curation
cur data.

**Pratyaksh Singh:** Okay. Yeah. Yeah. Like uh so which bot agent are
you intercept? Which one?

**Sachin Pandey:** uh like agent is will be quen I need to find the
harness which can like do like do non-stop run without stopping

**Pratyaksh Singh:** So simple thing you can do Sachin is for starters
just use the uh you have the Google AI pro right and that GPT go just
use the D prearch agent right see what you get those

**Sachin Pandey:** Yeah, good point.

**Pratyaksh Singh:** also like usually I\'ll find that

### 01:21:21

**Sachin Pandey:** Not a deep research. Yeah, like agenda is a deep
research but yeah.

**Pratyaksh Singh:** in in in chat only in uh uh so in

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** chat GP uh in chat only for both Chad GP and Gemini
you can you can turn on the deep research mode right and at least for
finding data I have

**Sachin Pandey:** Yes.

**Pratyaksh Singh:** found them to be quite reliable that

**Sachin Pandey:** Yeah. Those are we we can do

**Pratyaksh Singh:** so yeah then I

**Sachin Pandey:** that.

**Pratyaksh Singh:** And then just please also categorize the data if
they are good, bad, what what is the quality of data.

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** All right.

**Sachin Pandey:** Uh I have like rough category for the mind data which
we have like it it was generally

**Pratyaksh Singh:** Uh-huh.

**Sachin Pandey:** between like same area but low resolution and high
resolution and you

**Pratyaksh Singh:** Uh-huh.

**Sachin Pandey:** know uh like

**Pratyaksh Singh:** And similarly have it for all the data set like
have an info that you can present to the meeting on

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** Monday in like 10 15 minutes like don\'t don\'t it
shouldn\'t be too

### 01:22:27

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** deep right it it shouldn\'t be this it shouldn\'t
be it should be like this that you know from the from the first five or
six line I can know you know how many which data are high quality which
data low quality what are the number of those images right what are the
number of those images which are high quality what are the number of
those images which are low quality and then if I want to individually
inspect those data then we can I can like go and inspect those
particular data does it make

**Sachin Pandey:** Okay. Yeah,

**Pratyaksh Singh:** sense

**Sachin Pandey:** I found a term for this like format. It\'s uh
leadership

**Pratyaksh Singh:** what is it You guys can

**Sachin Pandey:** brief.

**Pratyaksh Singh:** see

**Sachin Pandey:** Like just giving this to the agent will like put all
the information important info on the top like even one minute of read
can give the all the context.

**Pratyaksh Singh:** Yeah. Nice. Nice. You know, I think I think like
once uh I think like you know it would be norm very soon that once a
month the team sits down and discuss the AI agent and what prompt is
working for them, what prompt isn\'t and then we all can copy paste and
stuff.

### 01:23:53

**Sachin Pandey:** Yeah, I was just preparing a log for Uh Jeff, if you
want I can share it in the group too. It\'s basically like uh what was
it? Block just launched its um hardness and like I just tested it and it
was much better like it for the long running task it is doing better
than open code. I just connected all the local LLMs which are running on
Ninja and H100 and like it\'s it\'s

**Pratyaksh Singh:** Okay. Okay. Amazing.

**Sachin Pandey:** like working good.

**Pratyaksh Singh:** Amazing. I think there is one from uh Lang also
called deep pigs which I have heard is pretty good. So you might want to
try that out also be present.

**Sachin Pandey:** Yep.

**Pratyaksh Singh:** Anyways,

**Geoff Horowitz:** All right, guys. Uh, I guess we\'ll talk on Monday.
Anything else anybody needs to bring up, right? Let\'s talk on Monday.
Project safe travels.

**Pratyaksh Singh:** thanks. Thank you, Jeff.

**Geoff Horowitz:** Okay, bye guys. Rool, I\'ll see you in a second.

**Pratyaksh Singh:** Wait,

**Ratul Shashank:** Focus.

**Pratyaksh Singh:** it\'s flashed.

### Transcription ended after 01:26:31

*This editable transcript was computer generated and might contain
errors. People can also change the text after it was created.*
