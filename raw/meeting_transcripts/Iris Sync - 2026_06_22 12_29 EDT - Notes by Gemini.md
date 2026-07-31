Jun 22, 2026

## Iris Sync

Invited [[Sachin Pandey]{.underline}](mailto:sachin@crescer.ai)
[[Pratyaksh Singh]{.underline}](mailto:pratyaksh@crescer.ai) [[Niveta
Iyer]{.underline}](mailto:niveta@crescer.ai) [[Hemanth
Sarabu]{.underline}](mailto:hemanth@crescer.ai) [[Geoff
Horowitz]{.underline}](mailto:geoff@crescer.ai) [[Siddharth
Soni]{.underline}](mailto:siddharth@crescer.ai) [[Ratul
Shashank]{.underline}](mailto:ratul@crescer.ai)

Attachments [[Iris
Sync]{.underline}](https://calendar.google.com/calendar/event?eid=NnNzMHVxNzk3MmJqZGVwNXFoN2J1Mjd1OTdfMjAyNjA2MjJUMTYzMDAwWiBnZW9mZkBjcmVzY2VyLmFp)

Meeting records
[[Transcript]{.underline}](https://docs.google.com/document/d/1YdgiDAmz7-xuNGR9Ize2i4n6ojfdleETewgp0HLX5lQ/edit?usp=drive_web&tab=t.6wmwx3nu3l0i)

### Summary

The meeting addressed pipeline orientation issues and data resolution
debates with project configuration updates.\
\
**Pipeline and Project Scope**\
The team decided Bedrock and Iris are distinct entities, removing the
need for separate meetings. Discussions focused on resolving S7K
pipeline orientation and altitude exaggeration issues.\
\
**Data Resolution and Artifacts**\
Participants debated increasing resolution to 10 centimeters per pixel
to clarify small features. Analysts proposed visualizing eXtended Triton
Format data as waterfall images to isolate processing errors.\
\
**Annotation and Configuration**\
Discussions addressed manual labeling protocols and standardizing
criteria for shadow region identification. The team verified frame
definitions and segment sizes for the current project workflow.

### Decisions

Aligned

-   **Bedrock data resolution standard** The team established a standard
    > to process Bedrock data at 10cm x 10cm pixel resolution to improve
    > image quality and feature visibility, replacing the previous 25cm
    > standard.

We\'ve **updated the Decisions section** using your feedback.

Let us know what you think:
[[Helpful]{.underline}](https://google.qualtrics.com/jfe/form/SV_5p6FWBVWvynleNU?isGoogler=no&isHelpful=yes)
or [[Not
Helpful]{.underline}](https://google.qualtrics.com/jfe/form/SV_5p6FWBVWvynleNU?isGoogler=no&isHelpful=no)

### Next steps

-   \[Ratul Shashank\] Fix Pipeline: Resolve point cloud orientation and
    > altitude exaggeration issues in the S7K data pipeline.

    > \[Ratul Shashank\] Test Inversion: Attempt inverting latitude and
    > longitude parameters to correct current point cloud orientation
    > errors.

    > \[Geoff Horowitz\] Clarify Resolution: Contact the project team to
    > confirm the expected data resolution requirements.

    > \[Sachin Pandey\] Analyze Files: Review associated CSV and SEG
    > format files to verify data quality and identify potential
    > anomalies.

    > \[Geoff Horowitz\] Verify Background Data: Consult the provider to
    > determine if current background data visual artifacts are
    > expected.

    > \[Pratyaksh Singh\] Schedule meeting: Schedule a meeting for
    > tomorrow to discuss the dataset and annotation tasks.

    > \[Geoff Horowitz\] Send link: Send out a link for the follow up
    > meeting later.

    > \[Geoff Horowitz\] Ping Pratyaksh Singh: Ping Pratyaksh Singh
    > later today to review additional items.

### Details

-   **Personal Check-in**: The team opened the meeting with a brief
    > check-in regarding their weekends and discussed personal
    > anecdotes, including Sachin Pandey's update on their bird, noting
    > that the bird is unable to fly due to a past injury involving a
    > fan and now exercises by running around the house
    > ([[00:01:31]{.underline}](#section)).

-   **Project Clarification**: Geoff Horowitz confirmed that Bedrock and
    > Iris are distinct entities. The team agreed that there is no need
    > for separate meetings for Bedrock at this time, as the same group
    > is currently working on the project
    > ([[00:03:29]{.underline}](#section-1)).

-   **S7K Pipeline - Point Cloud Directionality**: Ratul Shashank
    > reported an issue with the S7K pipeline where generated point
    > clouds are oriented in a different direction than the reference
    > files. While the reference file points might be oriented at an
    > angle, the generated ones are pointing in a different, consistent
    > direction ([[00:04:51]{.underline}](#section-2)). Geoff Horowitz
    > suggested this might be a plotting issue on a vertical axis rather
    > than rotation around a central axis. Sachin Pandey noted that
    > inverting the latitude and longitude (X and Y) coordinates might
    > resolve this, which Ratul plans to investigate
    > ([[00:06:24]{.underline}](#section-3)).

-   **S7K Pipeline - Altitude Exaggeration**: Ratul Shashank described a
    > secondary problem where the pipeline exaggerates altitude,
    > specifically in areas classified as noise in the reference data
    > ([[00:04:51]{.underline}](#section-2)). Ratul is working to
    > minimize this exaggeration ([[00:06:24]{.underline}](#section-3)).

-   **Coordination and Communication**: Geoff Horowitz encouraged the
    > team to use the Slack channel to share images, thoughts, and
    > progress updates to help coordinate their work on the pipeline
    > ([[00:07:58]{.underline}](#section-4)).

-   **Bedrock Data Resolution**: Sachin Pandey presented questions
    > regarding the Bedrock dataset, specifically concerning resolution
    > ([[00:07:58]{.underline}](#section-4)). The team previously used a
    > 25 cm per pixel resolution but determined it resulted in
    > low-quality images. Sachin proposed switching to 10 cm per pixel
    > to improve clarity, noting that they have achieved better results
    > at that scale ([[00:11:00]{.underline}](#section-6)). The team
    > discussed whether to confirm this shift to 10 cm or 5 cm per pixel
    > with the stakeholders, as higher resolution is needed to identify
    > small features like anchor chains
    > ([[00:12:31]{.underline}](#section-7))
    > ([[00:14:39]{.underline}](#section-9)).

-   **Production Pipeline Responsibility**: The team discussed who is
    > responsible for processing XTF files into PNG images for
    > production ([[00:17:12]{.underline}](#section-11)). Hemanth Sarabu
    > noted that the team likely wants to retain visibility into or own
    > the code that handles this XTF to PNG conversion, rather than
    > relying on a third party ([[00:18:43]{.underline}](#section-12)).

-   **Availability of High-Resolution Data**: Sachin Pandey explained
    > that for some datasets, such as those from ENTX and DRN, there are
    > both low-pass and high-resolution XTF files available
    > ([[00:19:47]{.underline}](#section-13))
    > ([[00:22:46]{.underline}](#section-15)). While artifacts are more
    > visible in the high-resolution versions, the team prefers working
    > with the highest resolution data possible and can downsample it
    > later if necessary ([[00:21:24]{.underline}](#section-14)).

-   **Data Artifacts and Gaps**: When processing data at a higher
    > resolution (0.1 meters), the team observed gaps and lines in the
    > imagery ([[00:24:39]{.underline}](#section-16)). The team debated
    > whether these are genuine data gaps or artifacts caused by
    > rasterization, averaging effects, or processing settings. Hemanth
    > Sarabu suggested cross-checking these observations to ensure the
    > processing pipeline is not introducing errors
    > ([[00:27:34]{.underline}](#section-18)).

-   **Comparison of Datasets and Pipeline Performance**: The team
    > compared the performance of the pipeline on different datasets,
    > specifically Vineyard Winds (VW) and ENTX
    > ([[00:30:40]{.underline}](#section-20))
    > ([[00:34:54]{.underline}](#section-22)). Sachin Pandey clarified
    > that the pipeline's performance issues on ENTX might stem from the
    > previous version of the script using a fixed altitude, whereas the
    > updated script dynamically adjusts based on sensor data
    > ([[00:40:25]{.underline}](#section-24)). Geoff Horowitz requested
    > confirmation on whether the resolution is consistent across these
    > datasets, noting that ENTX images appear to be of lower quality
    > ([[00:30:40]{.underline}](#section-20))
    > ([[00:34:54]{.underline}](#section-22)).

-   **Proposed Cross-Check Method**: To investigate whether the image
    > quality issues are due to faulty data or the processing pipeline,
    > Ratul Shashank proposed creating waterfall images for the XTF
    > files ([[00:42:18]{.underline}](#section-25))
    > ([[00:47:14]{.underline}](#section-28)). By visualizing the pings
    > consecutively, the team hopes to determine if the data itself is
    > valid or if the pipeline is incorrectly projecting the data,
    > resulting in the lines and distortions observed
    > ([[00:42:18]{.underline}](#section-25))
    > ([[00:48:41]{.underline}](#section-29)).

-   **Next Steps for Communication**: The team plans to reach out to
    > stakeholders to clarify the expected resolution and to ask if the
    > background artifacts they are seeing are standard for the provided
    > data or indicative of a processing error
    > ([[00:50:38]{.underline}](#section-30))
    > ([[00:56:34]{.underline}](#section-33)). Geoff Horowitz intends to
    > follow up with Bridget to address these questions and ensure they
    > are aligned on expectations for production
    > ([[00:14:39]{.underline}](#section-9))
    > ([[00:50:38]{.underline}](#section-30)).

-   **File Access and Meeting Scheduling**: Pratyaksh Singh and Sachin
    > Pandey discussed issues regarding opening files, with Sachin
    > Pandey identifying a previously failing file that could now be
    > accessed. Due to a time constraint, Geoff Horowitz requested to
    > drop the call and scheduled a follow-up meeting for the next day,
    > committing to send a link later and providing a follow-up status
    > check to the team later that day
    > ([[00:59:19]{.underline}](#section-35)).

-   **Image Quality and Resolution Analysis**: Pratyaksh Singh and
    > Sachin Pandey reviewed file resolution and visual artifacts,
    > noting that changing the resolution did not visually alter the
    > image but improved the clarity of vertical lines. They discussed
    > the impact of resolution on data, specifically noting that
    > low-resolution settings might obscure details compared to
    > high-definition imagery ([[01:01:14]{.underline}](#section-36)).
    > The conversation included technical comparisons of frequency,
    > specifically relating to clean acoustic shadows for long-range
    > detection, and the conversion of images to Portable Network
    > Graphics format ([[01:05:19]{.underline}](#section-37)).

-   **Annotation Protocols and Data Set Definitions**: The participants
    > discussed foreground and background modeling, questioning how to
    > provide annotations for specific data sets and identifying which
    > classes items belong to ([[01:05:19]{.underline}](#section-37)).
    > Sachin Pandey inquired about specific tools or methods for manual
    > annotation, highlighting the time-intensive nature of the process.
    > Discussions also covered data set identification, including
    > distinctions between TX and VW models, and how to handle zoom
    > artifacts ([[01:12:22]{.underline}](#section-38)).

-   **Project Artifacts and Labeling Criteria**: Regarding manual
    > labeling, the team discussed the difficulties of identifying
    > shadow regions and determining whether specific elements, such as
    > black portions of an image, should be considered for annotation.
    > There was a discussion on standardizing the annotation of script
    > lengths and addressing image artifacts, such as combined multiple
    > lines ([[01:20:12]{.underline}](#section-39)). The participants
    > also touched on Project Alexa, reviewing annotation counting
    > methods and the need to maintain consistent labeling across the
    > project ([[01:29:08]{.underline}](#section-40)).

-   **Project Configuration and Export Settings**: The team focused on
    > configuring project attributes, including defining the number of
    > frames and segment sizes for Project B7. Pratyaksh Singh clarified
    > the procedure for job submission, noting requirements for sorting
    > orders and frame definitions in the interface. They concluded by
    > verifying the workflow for saving and refreshing tasks to ensure
    > project data was correctly updated
    > ([[01:35:55]{.underline}](#section-41)).

*You should review Gemini\'s notes to make sure they\'re accurate. [[Get
tips and learn how Gemini takes
notes]{.underline}](https://support.google.com/meet/answer/14754931)*

*How is the quality of **these specific notes?** [[Take a short
survey]{.underline}](https://google.qualtrics.com/jfe/form/SV_9vK3UZEaIQKKE7A?confid=vAekXe58y6fzhzK9a7_2DxIUOAIIigIgABgECA&detailid=standard&screenshot=false)
to let us know your feedback, including how helpful the notes were for
your needs.*

📖 Transcript

Jun 22, 2026

## Iris Sync - Transcript

### 00:01:31

**Sachin Pandey:** Happy days.

**Pratyaksh Singh:** Hello. Am I audible?

**Sachin Pandey:** Yes. Yes.

**Pratyaksh Singh:** How was it?

**Sachin Pandey:** That was good.

**Pratyaksh Singh:** It was

**Sachin Pandey:** It the pain will start from tomorrow.

**Pratyaksh Singh:** the start.

**Geoff Horowitz:** Hey guys,

**Sachin Pandey:** blue.

**Geoff Horowitz:** how\'s your weekend? What\' you say, Sash?

**Sachin Pandey:** It was good.

**Geoff Horowitz:** Oh, nice. Um, Sachin, what uh do you ever like do
you ever take your bird for exercise or something?

**Sachin Pandey:** No, like he doesn\'t fly.

**Geoff Horowitz:** He doesn\'t

**Sachin Pandey:** So he Yeah, he like half of the wing like he half of
the wings got cut

**Geoff Horowitz:** fly.

**Sachin Pandey:** off in the with the from the fan when he was flying.
So he can\'t fly anymore.

**Geoff Horowitz:** Oh my gosh.

**Sachin Pandey:** So, like he runs around the house.

**Geoff Horowitz:** Oh my gosh. Wow. Well, I guess he gets exercise by
running around the house.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** Okay. All right. Um, okay. I don\'t think there\'s
anything Iris we need to talk about.

### 00:03:29

**Geoff Horowitz:** Is that Is that correct?

**Sachin Pandey:** Badrock is different from iris.

**Geoff Horowitz:** Such for some reason I\'m struggling to hear you.

**Sachin Pandey:** Uh I was asking like bedrock is uh will be separate
from iris.

**Geoff Horowitz:** Bedrock will be separate from Iris. What do you
mean?

**Sachin Pandey:** Uh like Yes.

**Geoff Horowitz:** Like are we going to have a separate Bedrock
meeting? Uh I think right now I\'m just going to overload them.

**Sachin Pandey:** Okay.

**Geoff Horowitz:** Um because I don\'t I mean at least it\'s the same
group. So, um, but if it\'s easier for you guys, I can set up a separate
meeting.

**Sachin Pandey:** Uh I don\'t think we need it because we are like all
of us are only working on petrol right now.

**Geoff Horowitz:** Yeah. Um,

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** actually there is Sergeant. What\'s the status of
the S7K stuff?

**Sachin Pandey:** RT can believe that he was working on it.

**Geoff Horowitz:** Okay.

**Ratul Shashank:** Uh is my audio audible now? Yes.

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** Yeah.

**Ratul Shashank:** Uh regarding S7K to last file,

### 00:04:51

**Hemanth Sarabu:** Anybody?

**Ratul Shashank:** we are talking about that, right?

**Geoff Horowitz:** Mhm.

**Ratul Shashank:** uh I have created a pipeline although there is one
problem which uh I I am not able to find out why it\'s happening I am uh
coordinating with such in regarding this the point clouds are directing
in a different direction which was uh in reference file which are in one
direction but in the file that it\'s generating the point clouds are in
a separate direction.

**Geoff Horowitz:** like a Z direction.

**Ratul Shashank:** Uh like uh like like u uh for

**Geoff Horowitz:** What do you mean a separate

**Ratul Shashank:** example in our the generation that our pipeline gave
us all the points are let\'s suppose pointing in north direction but in
the reference file they could be pointing in something like in northeast
direction at an angle. Uh and there is another problem which is uh
regarding the uh in some features the altitude our pipeline is
exaggerating the altitude uh like it\'s not to a great degree. Uh and
the altitude problem is only highlighted in the region where uh the
reference says it\'s not it\'s it\'s been classified as noise.

### 00:06:24

**Ratul Shashank:** So these are the two problems that I\'m having at
this point regarding the pipeline. I am looking into it and uh I will
try to

**Geoff Horowitz:** Okay.

**Ratul Shashank:** minimize these as much as

**Geoff Horowitz:** Okay. Yeah. I just Okay.

**Ratul Shashank:** possible.

**Geoff Horowitz:** It looks it looks to me just from the pictures that
Sashin sent that these a lot of these points are being plotted on a
vertical axis instead of you know the line being um rotated around some
central axis. You you might be looking into that already.

**Ratul Shashank:** Actually Sachin mentioned something regarding
inversion of XY points like uh lat long so I

**Geoff Horowitz:** Uh that could be too.

**Sachin Pandey:** Let go.

**Ratul Shashank:** have not tried that but when he mentioned then
because uh

**Geoff Horowitz:** Yeah.

**Ratul Shashank:** on the parameters it\'s looking like the features
are protruding much uh more than it should be. So if it\'s if there is a
problem regard with the inversion then I guess that could solve most uh
that problem because everything else is uh predicting is uh accurate all
the xy points the uh perimeter and the area all of that it\'s uh giving
an accurate uh generation

### 00:07:58

**Geoff Horowitz:** Mhm. Okay. All right. Keep keep us updated.

**Ratul Shashank:** I will try that

**Geoff Horowitz:** Feel free to use the feel free feel free to use the
Slack channel too to share images

**Ratul Shashank:** in

**Geoff Horowitz:** and thoughts and things like that of help if it\'s
helpful. Cool. Okay. Um,

**Ratul Shashank:** definitely.

**Geoff Horowitz:** unless Rachel there\'s something you need from us,
uh, let\'s move on to bedrock.

**Ratul Shashank:** Uh No, at not at this moment, but I will ask for it.

**Geoff Horowitz:** Okay, great. Then let\'s move on to bedrock. Um,

**Sachin Pandey:** Yeah, for bedrock I have created a like list of
questions which we need answer from.

**Geoff Horowitz:** Right.

**Sachin Pandey:** Uh it is in the you want me to like show it or just
share those slides.

**Geoff Horowitz:** Uh you can show it and show the slides.

**Sachin Pandey:** Yeah, the first was like uh the resolution because
like in one PDF they have mentioned like they are capturing up to like 5
cm cm. So like we just want to confirm.

### 00:09:30

**Geoff Horowitz:** Son,

**Sachin Pandey:** No,

**Geoff Horowitz:** where is this document

**Sachin Pandey:** but uh it\'s not in the folder.

**Geoff Horowitz:** saved?

**Sachin Pandey:** Give me a second. I\'ll just remove it.

**Geoff Horowitz:** Sachin, you must know I\'m going to ask at this
point,

**Sachin Pandey:** Use that.

**Geoff Horowitz:** right?

**Sachin Pandey:** Once all the main changes are done, then like I
generally move it to the

**Geoff Horowitz:** You move it.

**Sachin Pandey:** So uh this was mentioned in the the port of is B uh
survey. This was the exact PDF. So they have mentioned like they were
using like they can get around high resolution SSS. So we are not using
like 5 cm. Earlier we were using uh 0.25 m but we have switched it to
0.1 m. like uh at almost double the double the distance for one pixel.
So we can like increase it more because like uh for one image I tested
we were getting the highest resolution of 0.018. So we can like get more
resolution out of the image. But it was not usable because the the file
size were reaching like 80 to 90 MBs for each XTF.

### 00:11:00

**Geoff Horowitz:** So, okay.

**Sachin Pandey:** Next one was two.

**Geoff Horowitz:** You\'re I What what is the clarification we need
from them? That\'s what I\'m missing.

**Sachin Pandey:** So like we were using the low resolution data because
we thought like if bedrop shares the like if we train on the high
resolution and model sees the low resolution it will be not be working
well. But like we can get the high resolution if they like if they
generally use get the if the XTFs are in this much

**Geoff Horowitz:** Okay.

**Sachin Pandey:** resolution.

**Geoff Horowitz:** You\'re you\'re saying so you\'re saying what I\'m
hearing you say is from the specification document they\'re saying that
they have this high resolution data but what they shared with us is
lower

**Sachin Pandey:** No, they they all they they share the same data,

**Geoff Horowitz:** resolution.

**Sachin Pandey:** but we were using we were like we didn\'t uh we
weren\'t extracting the high resolution images from the XTF like the the
it was 0.25 m per pixel.

**Pratyaksh Singh:** Hey Jeff, uh the shares is the of files. What we
did was you know we took a random assumption that we are going to
operate on 25 cm + 25 cm as one pixel.

### 00:12:31

**Sachin Pandey:** Thank

**Pratyaksh Singh:** But uh in our current analysis we found out that

**Geoff Horowitz:** Mhm.

**Sachin Pandey:** you.

**Pratyaksh Singh:** that results in very low quality image
comparatively low quality image. So we are deciding to go to a lower
dimension maybe 10

**Geoff Horowitz:** Right.

**Pratyaksh Singh:** cm + 10 cm as one pixel right. So we need
clarification from them that should we operate on 10 cm cross 10 cm
pixel or should we stay with something like 25 cm + 25 cm. The reason
being is that uh I think we discussed the reason yesterday right?

**Geoff Horowitz:** Fine.

**Pratyaksh Singh:** Do you need the reason for it or is it fine?

**Geoff Horowitz:** No, no, no. I I understand the reason. What What did
we do for vineyard winds? What did we do for the last data set?

**Pratyaksh Singh:** It was 25 cm.

**Geoff Horowitz:** It was 25 centimeters. And do we know does anybody
know if we had higher

**Pratyaksh Singh:** Yeah,

**Geoff Horowitz:** resolutions for that data set?

**Pratyaksh Singh:** I think we do. Right.

### 00:13:34

**Pratyaksh Singh:** Session for VW. We have higher resolution too.

**Sachin Pandey:** Yes.

**Pratyaksh Singh:** Yeah,

**Sachin Pandey:** Uh second

**Pratyaksh Singh:** we do.

**Sachin Pandey:** got

**Geoff Horowitz:** And we we prefer to do higher resolution.

**Pratyaksh Singh:** Jeff.

**Geoff Horowitz:** We prefer to do higher resolution because Yeah.

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** Yeah. Because we\'re not we\'re not catching these
things at the lower

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** resolutions.

**Pratyaksh Singh:** Uh I think uh the choice was arbitrary

**Sachin Pandey:** These are the high res.

**Pratyaksh Singh:** mostly. This this is what we got from uh this is
what we got from Sid. From Sid we got that you know he chose a
resolution which didn\'t leave a lot of

**Sachin Pandey:** Can

**Pratyaksh Singh:** gaps and and you know 25 was an

**Sachin Pandey:** you

**Pratyaksh Singh:** arbitrary number. So we want to you know we want to
know from them what number do they operate on because at

**Sachin Pandey:** please

**Pratyaksh Singh:** lower resolution there are some additional
artifacts that come in which which is avoided in the higher resolution.

**Geoff Horowitz:** Okay.

### 00:14:39

**Geoff Horowitz:** All right. I understand. Thanks for the
clarifications.

**Sachin Pandey:** So like these details are clearly visible in the
higher resolution which were like almost lost in the lower resolution.
And when we zoom into annotate it\'s like hard to identify the things
like this is a good balance between the size and the resolution.

**Geoff Horowitz:** What resolution is

**Sachin Pandey:** It\'s uh 10 cm per meter.

**Geoff Horowitz:** this? So,

**Sachin Pandey:** Cool.

**Geoff Horowitz:** so it I and this is what I\'ll say to Bridget, you
know, ideally we want to work at at the highest resolution possible. Is
that right? I mean, if we can do 5 centimeters across 5 centimeters,
that\'s fine with us, right? But all all of their data needs to be at
that resolution including whatever they\'re going to be running on

**Sachin Pandey:** Yes.

**Geoff Horowitz:** board real time.

**Hemanth Sarabu:** Jeff, can you catch me up real quick?

**Geoff Horowitz:** Yeah. Uh we\'re going through the questions for
bedrock. Um we\'re on the first question which is a question of data
quality essentially.

### 00:15:45

**Geoff Horowitz:** So the they gave us higher resolution data 5cm um
resolution uh in in this current data set when we process the data at a
lower resolution 25 cm we don\'t actually see the detail of these
contacts that\'s a problem for us so we want clarification from Bridget
on what what kind of resolution they expect on board right in
production.

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** If we can get the higher resolution,

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** everybody\'s happy with that. If it\'s going to be
lower resolution real, you know, in production, then um it\'s going to
be a longer discussion. We\'re going to have to figure out what to do.

**Hemanth Sarabu:** So you\'re saying the features are not visible at a
lower

**Geoff Horowitz:** Some are not visible, some are significantly less
visible.

**Hemanth Sarabu:** resolution.

**Geoff Horowitz:** Right section.

**Sachin Pandey:** Yes, like this area is uh same between this is the
low resolution file and this is higher res resolution.

**Hemanth Sarabu:** Uh ah okay. What are we looking at? What are those?

**Sachin Pandey:** These are chains.

**Hemanth Sarabu:** The dragon.

### 00:17:12

**Sachin Pandey:** I think it\'s metallic chain because I saw the
similar annotation in

**Hemanth Sarabu:** Oh, I

**Sachin Pandey:** which

**Hemanth Sarabu:** see.

**Sachin Pandey:** it was in the port data set. They mark these object
as like chain or like anchor chains. All

**Hemanth Sarabu:** Ah okay. So it is these are anchor uh anchor chains
being dragged. Can you zoom in a little more?

**Sachin Pandey:** right.

**Hemanth Sarabu:** This is full res or high res.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** He I I don\'t remember. Did we specify if they\'re
going to send us XT apps or if they\'re going to send us images?

**Hemanth Sarabu:** um in the S like the goal is for this to go XDF to
something

**Geoff Horowitz:** Uhhuh.

**Hemanth Sarabu:** else. Um now why did they send us JPEGs?

**Geoff Horowitz:** No, no, no, no. In production, do you do you
remember if the pipeline was going to

**Hemanth Sarabu:** Actually not JPEGs I think PNGs in production.

**Geoff Horowitz:** be

**Hemanth Sarabu:** Yeah. Yeah. Yeah.

**Geoff Horowitz:** PNG,

**Hemanth Sarabu:** So either they were going to process XDF to PNG or
we are going to process XDF to PNG.

### 00:18:43

**Geoff Horowitz:** right? I don\'t remember if it decided which one.

**Hemanth Sarabu:** that I I don\'t either, but uh it\'s we probably
want to own

**Geoff Horowitz:** Okay.

**Hemanth Sarabu:** the XDF to PNG as in like at least we want
visibility into that code,

**Geoff Horowitz:** Yeah,

**Hemanth Sarabu:** which is how it was originally,

**Sachin Pandey:** Are

**Hemanth Sarabu:** right?

**Geoff Horowitz:** correct.

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** Actually, I think they pushed back on us.
Originally, we did we just did PNG and then they\'re like, \"Hey, we
want you to process the XTFs.\" And we\'re like, \"Yeah, no problem. I
think that\'s what happened because the first version of the Streamlit
app was only PNG.

**Hemanth Sarabu:** Um,

**Geoff Horowitz:** Maybe we caught that. I don\'t remember

**Hemanth Sarabu:** we just made it.

**Geoff Horowitz:** clearly.

**Hemanth Sarabu:** We just made it for a demo.

**Geoff Horowitz:** Uh okay. Uh unless there was anything else you talk
about at this point, then let\'s move on.

**Sachin Pandey:** Okay. So uh next question is like in their data set
like this is the same file same

### 00:19:47

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** location but the difference is like uh like the
quality like these are both are the same resolution image but the like
it was recorded differently like the difference is from the XDF file
itself. This was located in like low low pass folder where like they
maybe they have like reduced the height or use a different kind of
frequency for it to generate the like more details. So we want to just
confirm whether we want to use it or not because the annotations were
only

**Geoff Horowitz:** Were

**Sachin Pandey:** uh done on the lower resolution one

**Geoff Horowitz:** they both XTFs or was one an image?

**Sachin Pandey:** table both yeah the only difference is underscore

**Geoff Horowitz:** Both XTFs. Okay. So the question is really say once

**Sachin Pandey:** one the like almost name is also same just the higher

**Geoff Horowitz:** more.

**Sachin Pandey:** resolution has underscore one at the

**Geoff Horowitz:** So the the question is will the lowass XTFS be
available? Um because if they\'re available then it\'s really our
choice.

**Sachin Pandey:** But like artifacts will be much visible in this one
than this And there\'s a high chance model will confuse this as also
artifact.

### 00:21:24

**Sachin Pandey:** But these are just the elevation changes which is
clearly visible in the high resolution and

**Geoff Horowitz:** I mean, look, I I go back to the same question that
I just asked.

**Sachin Pandey:** the

**Geoff Horowitz:** Do Do we prefer the highest res possible?

**Pratyaksh Singh:** to be honest it doesn\'t matter to us but you know
in high things are more clear yes we do

**Geoff Horowitz:** I I agree with you pra I mean it\'s better that I
think it\'s better that we see all this if we really need to we can down
sample on our end. Um I think we we prefer to work with the most
high-res data possible.

**Sachin Pandey:** Yes, because all the uh open source data is generally
in this pro this resolution.

**Geoff Horowitz:** Did we have these lowass XTFs for all of the data
sets or only a few of them

**Sachin Pandey:** uh like not all there around 68 files. Yeah, around
68 files.

**Geoff Horowitz:** only 68 what I mean I know we had them for just for
the sake of this discussion section let\'s talk in data sets right so I
know we had them for at least one of the data sets.

### 00:22:46

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** I can\'t remember if it was ANTX or Danish Royal
Navy, but I remember we had them for at least one of them. Do we have
them for all of

**Sachin Pandey:** Uh it is for it\'s some not all of them have it but

**Geoff Horowitz:** them?

**Sachin Pandey:** ent have it and yeah DRN also have it

**Geoff Horowitz:** What did you say? Entx and what?

**Sachin Pandey:** entrance.

**Geoff Horowitz:** Okay. DRN. Yeah. So then um if so do we have low
pass for um Esper and

**Sachin Pandey:** f\*\*\*.

**Geoff Horowitz:** Vineyard Winds? That\'s the question. Okay.

**Sachin Pandey:** Uh VW also have it but they have a different format
like these two files have the same name. This has some extra.

**Geoff Horowitz:** They have a different naming format but but the data
they do have high

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** resolution XCF data.

**Sachin Pandey:** Yes, for the same resolution. Sorry, same for the
same

**Geoff Horowitz:** Okay.

**Sachin Pandey:** location.

**Geoff Horowitz:** Vineyard wins ant. Okay. Fine.

### 00:24:39

**Geoff Horowitz:** Okay. Uh, we\'ll ask that next

**Sachin Pandey:** Yeah. uh when we increase the uh resolution the

**Geoff Horowitz:** questions.

**Sachin Pandey:** the gaps in the data is more clearly visible like
these are the pings which may got corrupted. So this is also visible in
the low resolution but it is filled because of the like the grid size
when we lower the grid side these become empty.

**Geoff Horowitz:** Mhm.

**Sachin Pandey:** So I sorry

**Geoff Horowitz:** this. But this is it.

**Sachin Pandey:** just

**Hemanth Sarabu:** Hey,

**Geoff Horowitz:** Uh

**Hemanth Sarabu:** where This is coming from

**Sachin Pandey:** uh this one when we

**Hemanth Sarabu:** Oh, I see. I see. So, you\'re you\'re you\'re
upsampling the the lowres

**Sachin Pandey:** testing

**Hemanth Sarabu:** images.

**Sachin Pandey:** Yeah. These are just like same XTF. We are just
changing the resolution size. The more we increase the more like these
gaps are there. It is similar to

**Hemanth Sarabu:** But how is the how\'s the resolution being

**Sachin Pandey:** like how is the resolution being

**Hemanth Sarabu:** increased?

### 00:25:51

**Geoff Horowitz:** Sergeant,

**Pratyaksh Singh:** The XPF is recorded at very high

**Sachin Pandey:** increased.

**Pratyaksh Singh:** resolution.

**Geoff Horowitz:** which which data set is this particular image from?

**Sachin Pandey:** This is for uh the RN data set.

**Geoff Horowitz:** DRN.

**Sachin Pandey:** The one with the like this part was marked as the
annotation. This is

**Geoff Horowitz:** Um,

**Sachin Pandey:** playing

**Geoff Horowitz:** is DRN also does DRN also have these high 5cm high
resolution images?

**Sachin Pandey:** low pass images.

**Geoff Horowitz:** Sure.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Okay.

**Sachin Pandey:** This like this is the location. This is also the

**Geoff Horowitz:** Okay. So, is what you\'re showing us here,

**Sachin Pandey:** same.

**Geoff Horowitz:** this was collected at something above 5 mm, 5cm
resolution, rather.

**Sachin Pandey:** I don\'t get your question. If you are asking like
this artifact was present in the different like this image, it was not
because both of XDFs are different and they are captured at different
time. So this is only happening with the one which is lower resolution.
The lower path doesn\'t have this thing.

### 00:27:34

**Hemanth Sarabu:** I don\'t understand. Are there actually data gaps
there?

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** Okay, then it\'s My question is if there\'s a data
cap then then that\'s okay.

**Sachin Pandey:** Beautiful

**Hemanth Sarabu:** Is it an error in processing then that\'s not

**Geoff Horowitz:** How such an I I guess wasn\'t confused.

**Hemanth Sarabu:** okay.

**Geoff Horowitz:** How do you know that it\'s a data gap?

**Sachin Pandey:** because it\'s uh following the like lines and
increasing the

**Geoff Horowitz:** But there\'s so like there\'s some

**Sachin Pandey:** resolution like creating these lines

**Geoff Horowitz:** places in the in the uh 0.15 meter where it does
fill in those lines. So you\'re just

**Hemanth Sarabu:** I I think it\'s like some averaging

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** like rasterizing effect Jeff like if you zoom into
the top there is there is a it is

**Geoff Horowitz:** Uh,

**Hemanth Sarabu:** lighter.

**Geoff Horowitz:** I I do see that too. I do

**Hemanth Sarabu:** So but I still want to make sure that we are not
messing up anything.

**Geoff Horowitz:** see

**Hemanth Sarabu:** Hey, so this may be a stupid question, but Sen, the
low res images that we\'ve had previously, can we make them high res?

### 00:29:04

**Hemanth Sarabu:** Is this that or is this something else?

**Sachin Pandey:** like uh how are you we are generating the same
location but with the different resolution we are making those high res
we

**Hemanth Sarabu:** Okay. by processing the XTF

**Sachin Pandey:** can\'t yes we are using the same pipeline just
changing

**Hemanth Sarabu:** differently.

**Sachin Pandey:** the resolution earlier it Just default to 0.25. Now
we are using the

**Hemanth Sarabu:** Okay. Okay.

**Sachin Pandey:** 0.1.

**Hemanth Sarabu:** So, Jeff, what is the resolution that we\'re going
to talk to Bedrock about? because they probably they don\'t own the PNG
resolution. Sounds like we own it. We control it.

**Sachin Pandey:** Like we can ask them which resolution they generate
the tips because tips are also the images.

**Hemanth Sarabu:** Mhm. But Sachin, your original point about low res,
we cannot see the features and previously we were doing this lower res.
Is that an issue? Is that an is that a an issue we can solve on our own
or is that an issue that we need them to help us with?

### 00:30:40

**Sachin Pandey:** So, uh we just want to confirm the resolution because
like when we were working with uh this data set VW originally and these
were good like in the same like 0.25 these were like all the features
were available or visible but when we switched to NTX uh entx it were
like looking very bad and like these are not looking good for the same

**Hemanth Sarabu:** very bad and uh okay

**Sachin Pandey:** regime

**Hemanth Sarabu:** NTX what at what resolution will it look good or do
we not uh uh Jeff

**Sachin Pandey:** I can open the same image with the like higher
resolution which we generated.

**Hemanth Sarabu:** Sorry.

**Sachin Pandey:** I can open the same image like this same image with
the 0.1

**Hemanth Sarabu:** Let\'s take a look at

**Sachin Pandey:** resolution.

**Hemanth Sarabu:** that.

**Sachin Pandey:** This is the At least it\'s look cleaner than the one
we This

**Hemanth Sarabu:** Yeah, I I doubt there\'s actually a bug somewhere
there.

**Sachin Pandey:** bug in the in the pool.

**Hemanth Sarabu:** Yeah, it looks extremely blurry.

**Sachin Pandey:** I like these things.

**Hemanth Sarabu:** Not here.

**Sachin Pandey:** in this

### 00:32:56

**Hemanth Sarabu:** Previously.

**Sachin Pandey:** one.

**Hemanth Sarabu:** Previous one. This looks really bad,

**Sachin Pandey:** Yes,

**Hemanth Sarabu:** right?

**Sachin Pandey:** that\'s why we wanted to check like we also have the
some images from the open source tools and they also render it in high
resolution

**Pratyaksh Singh:** We have that view for XTF the open

**Sachin Pandey:** here for X.

**Pratyaksh Singh:** source and we put those images there

**Sachin Pandey:** Yeah, like this is for the

**Pratyaksh Singh:** and see how it is.

**Sachin Pandey:** same

**Pratyaksh Singh:** Yeah,

**Sachin Pandey:** file.

**Pratyaksh Singh:** for the same file the one where I mentioned that
there might be bug here.

**Sachin Pandey:** Yeah, do you have these files downloaded?

**Ratul Shashank:** I will just give me a moment. I will please fail to
fuse

**Sachin Pandey:** Yeah, I can give

**Ratul Shashank:** once.

**Sachin Pandey:** you So uh like answer your question like earlier we
were not facing problem because like in this data was looking good and
we were okay with it. But when we like switched to the another data set
like this one, it was like not looking good.

### 00:34:54

**Sachin Pandey:** That\'s why we tested out to like how much higher
resolution can we get.

**Hemanth Sarabu:** Are you guys convinced that this is the same
resolution as the other one?

**Sachin Pandey:** This pipeline hasn\'t

**Hemanth Sarabu:** That\'s not what I\'m asking.

**Sachin Pandey:** changed.

**Hemanth Sarabu:** You you convinced at the same resolution?

**Geoff Horowitz:** that Vineyard Winds and ENTX are the same

**Hemanth Sarabu:** Yeah, this image and the the vineyard winds image we

**Geoff Horowitz:** resolution.

**Hemanth Sarabu:** saw

**Sachin Pandey:** All right, it should be

**Hemanth Sarabu:** You see I\'m looking at what project shared or added
me to.

**Ratul Shashank:** I\'ve shared the image for that particular file.
It\'s uh it\'s very bad actually. It\'s not possible to look anything in
that.

**Hemanth Sarabu:** What?

**Ratul Shashank:** I have

**Hemanth Sarabu:** That\'s all there.

**Ratul Shashank:** shared

**Hemanth Sarabu:** See

**Ratul Shashank:** and I have shared it\'s very bad actually.

**Sachin Pandey:** So I generated the image again and it\'s almost the
same dimensions only one pixel change.

**Hemanth Sarabu:** No, no, no. My my question is not um was I\'m trying
to ask is do does it look like the same resolution like are there any is
there anything else we can use um to basically so what I\'m looking for
sanity check if that is actually the same resolution like what else is
going on.

### 00:38:39

**Hemanth Sarabu:** Why would that look that bad? So is saying the
ground level ping is still the same even though it\'s higher, right? Can
we do some simple geometry like compute the the width of the track, the
width of the swath? Does that match the width of the old swath? Is the
number of pings the same? Is it the same in meters? Um, why would why
would generating a higher res image look better if it\'s the same thing,
right? Do you get what I mean?

**Sachin Pandey:** Where you

**Hemanth Sarabu:** I don\'t think you should trust the processing
pipeline like 100%.

**Sachin Pandey:** at?

**Hemanth Sarabu:** Maybe 90%. The sense already for new is through.

**Sachin Pandey:** What the

**Hemanth Sarabu:** Oh.

**Sachin Pandey:** f\*\*\*?

**Hemanth Sarabu:** Um, Sachin, did you is that part of uh, is that part
of the message or did you add that in as a comment? The one that
mentions Sachin.

**Pratyaksh Singh:** That is part of the message I

**Sachin Pandey:** Yeah,

**Hemanth Sarabu:** Uh,

**Sachin Pandey:** this was for the like uh if you

### 00:40:25

**Hemanth Sarabu:** yeah,

**Pratyaksh Singh:** think.

**Hemanth Sarabu:** it is.

**Sachin Pandey:** use uh the old uh tool, the demo tool, so it will not
work for the uh entx data set because it is using the older code which
was like using the fixed altitude and assuming it was uh 10 which we
change it to fix the issue like in this code if we upload the the file
from data it will not will not look the same

**Hemanth Sarabu:** Why is that?

**Sachin Pandey:** because like the pro processing pipeline was assuming
that the distance between the sensor and the rece was 10 m which like
changed and it was not earlier it was not dynamically changed but in the
uh improved script it is like dynamic it is reading from the sensor and
adjusting

**Hemanth Sarabu:** Yeah. Okay.

**Sachin Pandey:** itself.

**Hemanth Sarabu:** So, I actually You\'re saying that VW vineyard winds
was 10 m height, right? antx is 3 m

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** high. I don\'t know why then for the same ground
resolution we would see such worse images. The only thing I can think of
is roll kicks had roll issues.

### 00:42:18

**Geoff Horowitz:** I don\'t remember if it was ANTX off the top of my
head. There was at least one data set that had B shoes, if not

**Hemanth Sarabu:** Um okay. So project such are you guys satisfied with
uh with this that the resolutions are the same but they look different.
So different.

**Ratul Shashank:** Uh can I add

**Hemanth Sarabu:** You guys can win.

**Ratul Shashank:** something?

**Geoff Horowitz:** Yeah, go ahead.

**Hemanth Sarabu:** Yeah.

**Ratul Shashank:** Uh we can cross check this problem by creating a
waterfall image for that XDF. Like if that image that waterfall image
that we generate if that is clear then we won\'t have we won\'t
theoretically we shouldn\'t have this problem for the rest.

**Hemanth Sarabu:** What will that tell us?

**Ratul Shashank:** Uh so if we if we are uh if we could create a
waterfall image for any exterior so that would basically give us uh
representation uh visualization of that entire uh HTF based on uh based
on that we can identify if these uh the columns that The previous
annotations showed it problem. It is is that the problem for the ping uh
is or the data is not very correct.

### 00:44:21

**Ratul Shashank:** So we can cross check that adding a second layer to
protein link.

**Hemanth Sarabu:** project. What are your thoughts?

**Pratyaksh Singh:** I didn\'t understand what I went through.

**Hemanth Sarabu:** Okay, I let\'s get back to that in a second.

**Ratul Shashank:** Yes.

**Hemanth Sarabu:** But same question.

**Ratul Shashank:** bit.

**Hemanth Sarabu:** Sachin Raj, are you guys convinced that this is a
resolution issue? Like the resolutions are the same but they look worse.
One looks way worse

**Pratyaksh Singh:** I don\'t think it\'s a resolution issue.

**Hemanth Sarabu:** h

**Pratyaksh Singh:** There are these are two different issues maybe
right. The resolution is something is for something else where we we are
saying that you know

**Hemanth Sarabu:** Those

**Pratyaksh Singh:** elevations and other artifacts are not visible in
higher in sorry lower resolution and if you go to higher resolution
those things are more clear right uh

**Hemanth Sarabu:** things are more clear.

**Pratyaksh Singh:** particularly

**Hemanth Sarabu:** Um. Mhm. Go on. Continue.

**Pratyaksh Singh:** and particularly referring to this file I think
this is just a that file and even if you increase the resolution of that
it\'s not going to change right

### 00:46:02

**Hemanth Sarabu:** I don\'t know that.

**Pratyaksh Singh:** because

**Hemanth Sarabu:** I I don\'t know. You You tell me.

**Pratyaksh Singh:** so that\'s what I said uh that\'s what I told uh
rat to do to use that this opensource app there is one app for at CF
viewers

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** right yeah so you know because that Well, that will
basically uh that will basically like you know take out all the all of
pre-processing pipeline a bug in our repro pipeline but there also it
doesn\'t look

**Hemanth Sarabu:** So Rul for uh to somewhat address what you were
saying that app does

**Ratul Shashank:** No.

**Hemanth Sarabu:** waterfall.

**Ratul Shashank:** Uh can I share my screen? I would be much able to
understand uh explain this.

**Hemanth Sarabu:** Sure.

**Sachin Pandey:** want this

**Hemanth Sarabu:** Wait,

**Sachin Pandey:** image.

**Hemanth Sarabu:** I thought the app does it. What? What is

**Sachin Pandey:** This is

**Ratul Shashank:** Now this is this is a PNG.

**Hemanth Sarabu:** this?

**Sachin Pandey:** the

**Ratul Shashank:** No session that is different. Uh I will I will share
my screen and I will explain what I was talking about.

### 00:47:14

**Hemanth Sarabu:** Okay.

**Ratul Shashank:** So is my screen visible? Yes. So this is basically
what a waterfall image is.

**Hemanth Sarabu:** Mhm.

**Ratul Shashank:** Waterfall image basically it prints the pinks the
echoes consecutively. So we can visualize what is in the XTF much
clearer. The problem with

**Hemanth Sarabu:** Wait, how how is it different from what Sachin was
showing or what is in the viewer

**Ratul Shashank:** that uh the problem with viewer app is some data I I
don\'t know why

**Hemanth Sarabu:** app?

**Ratul Shashank:** but the some data it just shows like a square or
just a blob. Uh I\'m not able to figure out why the app does that but
the

**Hemanth Sarabu:** Okay, wait wait wait wait one sec. I think that is
very important that the app is doing that.

**Ratul Shashank:** my

**Hemanth Sarabu:** So the app is supposed to show you a waterfall if I
remember the code correctly.

**Ratul Shashank:** uh app is basically for the visualization. This is a
waterfall. Uh, I will I will

**Hemanth Sarabu:** A waterfall is just uh it will just project the

### 00:48:41

**Ratul Shashank:** Yes.

**Hemanth Sarabu:** points naively and color it which is also what
Suchin was showing. Yeah,

**Ratul Shashank:** Yeah.

**Hemanth Sarabu:** this is the same thing.

**Ratul Shashank:** Yeah. This is for a different file, but I guess this
is also I guess this is also a waterfall

**Hemanth Sarabu:** Okay.

**Ratul Shashank:** image.

**Hemanth Sarabu:** Right. So I think the fact that that file looks
weird is it a clue?

**Ratul Shashank:** Uh,

**Hemanth Sarabu:** Like I don\'t think ignore it.

**Ratul Shashank:** actually just give me a second.

**Hemanth Sarabu:** Mhm.

**Ratul Shashank:** Yes. So what my reasoning behind that was uh let me
first clear my screen. this water this particular waterfall I don\'t
know my computer is I guess my laptop is uh not able to

**Hemanth Sarabu:** Okay. Okay. Look,

**Ratul Shashank:** handle

**Hemanth Sarabu:** uh, I actually have to run. I have an appointment at
11. Um,

**Geoff Horowitz:** Set.

**Ratul Shashank:** I will uh I don\'t think computer is very uh it\'s
it\'s not it\'s acting up. I will share the photos in just that thread
uh and

### 00:50:38

**Hemanth Sarabu:** okay.

**Ratul Shashank:** we\'ll be able to annotate next clearly there.

**Pratyaksh Singh:** Chef, I remember uh someone shared you a screenshot
right where they were showing that you know the uh the model is not
working on this new and

**Geoff Horowitz:** Yeah,

**Pratyaksh Singh:** data

**Geoff Horowitz:** it\'s in the um I I can tell you which folder it\'s
in. I\'m not I\'m not at my computer right now. Uh it\'s in the it\'s in
that kind of active active Bedrock SA 2 UKHO folder. It\'s in the uh
that like overview PDF uh PowerPoint rather.

**Pratyaksh Singh:** Okay. Uh,

**Geoff Horowitz:** I can send it to

**Pratyaksh Singh:** one more thing is that did they mention that you
know the XTM doesn\'t look like what it\'s supposed to supposed to

**Geoff Horowitz:** you.

**Pratyaksh Singh:** be?

**Geoff Horowitz:** They didn\'t mention that in particular. They
mentioned that the contacts like the contacts looked

**Pratyaksh Singh:** So they\'re basically like do you think they are
agreeing that you know the background is like that only the

**Geoff Horowitz:** different.

**Pratyaksh Singh:** same way that we are seeing or uh or do we need to
ask them about it?

### 00:52:00

**Geoff Horowitz:** Do we need to ask them if the back is this? Are you
talking about the next slide in Sachin\'s questions?

**Pratyaksh Singh:** I\'m talking about what we were discussing about
the ants data that why why why is it look so

**Geoff Horowitz:** which

**Pratyaksh Singh:** bad

**Geoff Horowitz:** they didn\'t bring up that issue in particular when
they were talking about background images. the issues that they brought
up were were issues where you could actually see the background um and
that we were picking up contacts that didn\'t actually exist, right? So,
false positives because of um you know divots, lines, features in the
background. That\'s what they were concerned about with background
image.

**Pratyaksh Singh:** Uh so I don\'t know how to confirm if you know if
it\'s a problem with our code or or if it\'s actually you know the
background is like that only. Does anyone have any idea how can they
confirm that?

**Ratul Shashank:** uh I am sharing my screen my open so I can explain
much clear now can I

**Pratyaksh Singh:** Okay.

**Ratul Shashank:** Uh what I was saying is when I was creating the
waterfall image for one particular HDF when the pipeline was not fine-
tuned it basically showed many horizontal lines like this which was also
consistent when our pipeline uh when the image that such showed earlier
which high-res image showed many vertical lines.

### 00:54:15

**Ratul Shashank:** So after I improved the pipeline

**Pratyaksh Singh:** What do you mean by improve the five like

**Ratul Shashank:** basically for for this particular waterfall image
these horizontal lines were created by pins and for to improve these I
improve I reduce the gamma level exposure and I uh improve uh I uh
increase the rest for this particular it was on 25 0.25 25 m per pixel.
And this one, just wait a minute. And this is after I tried a bunch of
stuff. And this is with lower gamma. and uh 0.1 m/s. So if after
improving uh or after trying a bunch of things if the water water uh
fall image improves then I think theoretically the problem is not with
data. But even if we try if we uh try a bunch of things and it still
gives discontinued data like this one then I guess the data that we have
got it itself it\'s faulty theoretically that should be the Yes. At this
point I don\'t have any other ways to cross check that but I think that
would help.

### 00:56:34

**Pratyaksh Singh:** Okay. Uh can we go to uh the next issues? Let\'s
discuss it at the end. There were other issues in the slide, right?

**Ratul Shashank:** Okay.

**Sachin Pandey:** Yes. So uh about your question like how we can verify
whether the file is correct or not? Uh I only found two other files with
the same name like one are CSV and other is SEG by format files. We can
like try looking at those to figure out or like find some relation
between the files because they they have the same name.

**Pratyaksh Singh:** Okay. Can you please try to do

**Geoff Horowitz:** Look, we

**Pratyaksh Singh:** that?

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** I\'m also I\'m also I couldn\'t I can ask them what
the resolution of the data is. You know, it\'s not a problem. Um we are
here for local.

**Pratyaksh Singh:** I think uh Jeff it\'s not it\'s not about
resolution as Aan

**Geoff Horowitz:** Yes. Yes. I agree.

**Pratyaksh Singh:** mentioned it\'s uh it\'s more about

**Geoff Horowitz:** Yeah.

**Pratyaksh Singh:** if the data is the data like this only or are we
messing something up in our pre-processing scripts right so we need to
ask them like is this the expected background because it looks much
different from all the other data that they gave us.

### 00:57:59

**Pratyaksh Singh:** Or are we messing something up or should it look
something

**Sachin Pandey:** This

**Pratyaksh Singh:** different?

**Geoff Horowitz:** But we\'re we\'re also this only this doesn\'t
happen. You\'re as such is saying this only happens when we um when we
try to render this at a higher resolution.

**Pratyaksh Singh:** It will happen everywhere.

**Geoff Horowitz:** And that\'s what I\'m saying is is welcome.

**Pratyaksh Singh:** It should happen at every resolution. So, correct
me if I\'m wrong, but it should happen at every resolution. Things
should improve.

**Sachin Pandey:** like uh these images are like a little bit clear in
these

**Pratyaksh Singh:** Yeah.

**Sachin Pandey:** ones.

**Geoff Horowitz:** We\'re we\'re seeing we\'re seeing on the on the
0.25 resolution that it doesn\'t show up. It\'s on the slide.

**Sachin Pandey:** Just a show.

**Pratyaksh Singh:** Can you open the same file for uh 1 cm? Sorry, 10

**Geoff Horowitz:** here first. We always step out of the

**Pratyaksh Singh:** cm.

**Sachin Pandey:** I will just open the one this one. The one we were
viewing earlier.

**Pratyaksh Singh:** Don\'t open fail to fuse.

### 00:59:19

**Pratyaksh Singh:** Don\'t open fail to fuse. can open anything

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** else. Can open the same file for 2 pipe

**Sachin Pandey:** Okay. So this uh this is wrong as actually I was
looking for the

**Pratyaksh Singh:** also.

**Sachin Pandey:** the image you were mentioning earlier the file which
were failing to load I just find it so we can change it.

**Pratyaksh Singh:** Can you open something else?

**Sachin Pandey:** Okay, it is I\'ll open this one.

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** Guys, I\'m I\'m gonna need to drop in a second.

**Pratyaksh Singh:** Let me schedule a meeting for tomorrow also.

**Geoff Horowitz:** Um,

**Pratyaksh Singh:** I think we need to discuss on

**Geoff Horowitz:** okay. Yeah,

**Pratyaksh Singh:** this

**Geoff Horowitz:** that works. Um, I\'ll send out a link later. I uh
I\'ll send it later. It\'s not I\'m also gonna try to um I\'ll ping you
later today and if you\'re still awake uh you and I can go through some
of the other ones um just on more up to speed when we talk tomorrow.

### 01:01:14

**Sachin Pandey:** Okay.

**Geoff Horowitz:** Does that work?

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Okay. Okay. Uh all right. I\'ll talk to you guys
later.

**Sachin Pandey:** Okay. So, this is the file.

**Pratyaksh Singh:** It looks the same, right? Changing the resolution
doesn\'t change anything.

**Sachin Pandey:** Yeah.

**Pratyaksh Singh:** The file was looking

**Sachin Pandey:** Changing the doesn\'t change the look,

**Pratyaksh Singh:** good.

**Sachin Pandey:** but it just make it much cleaner.

**Pratyaksh Singh:** lines.

**Ratul Shashank:** video lines. Technically,

**Sachin Pandey:** Yes.

**Pratyaksh Singh:** Vertical lines.

**Ratul Shashank:** low resolution.

**Pratyaksh Singh:** Okay.

**Ratul Shashank:** Huh? Low resolution. location. Focus.

**Pratyaksh Singh:** Oh,

**Ratul Shashank:** Fine.

**Pratyaksh Singh:** I

**Sachin Pandey:** download issue issue

**Pratyaksh Singh:** is

**Sachin Pandey:** issue issue discuss for him.

**Pratyaksh Singh:** and file discuss.

**Sachin Pandey:** Yeah.

**Pratyaksh Singh:** Okay.

**Sachin Pandey:** Okay. It should be low resolution level. It\'s a
similar example.

**Pratyaksh Singh:** Don\'t resolution

**Sachin Pandey:** Same.

**Pratyaksh Singh:** resolution.

**Sachin Pandey:** Sorry. We dr_1 high resolution low passersore Okay.

### 01:05:19

**Sachin Pandey:** You

**Pratyaksh Singh:** It\'s same

**Sachin Pandey:** put

**Pratyaksh Singh:** resolution. Uh, same

**Sachin Pandey:** Same.

**Pratyaksh Singh:** answer.

**Sachin Pandey:** Indoor frequency difference.

**Pratyaksh Singh:** Frequency is a cash

**Sachin Pandey:** You can see clarity

**Pratyaksh Singh:** driver.

**Sachin Pandey:** change.

**Pratyaksh Singh:** 25m high definition.

**Sachin Pandey:** Same energy example frequency lacking High frequency
parity shape imagery and clean acoustic shadows for detection long
range. So yellow Long range, lower frequency, high frequency. detap.

**Pratyaksh Singh:** Okay, images to PNG conversion.

**Sachin Pandey:** Oh

**Pratyaksh Singh:** Okay.

**Sachin Pandey:** modified high resolution vision

**Pratyaksh Singh:** Institution.

**Sachin Pandey:** seconds. Heat. Next issue. Types of background.
Hopefully background model.

**Pratyaksh Singh:** Foreground

**Sachin Pandey:** mention

**Pratyaksh Singh:** annotations.

**Sachin Pandey:** can we provide annotation for this data set which
class they will belong to examples that\'s

**Pratyaksh Singh:** annotation.

**Sachin Pandey:** all

**Pratyaksh Singh:** Annotation

**Sachin Pandey:** Same example.

**Pratyaksh Singh:** Let\'s do contact.

**Sachin Pandey:** shadows already. So you see is slightly people. Hey
Click only few script.

### 01:12:22

**Sachin Pandey:** What do you see? data set discuss data

**Pratyaksh Singh:** Are you

**Sachin Pandey:** set

**Pratyaksh Singh:** sure?

**Sachin Pandey:** TX or VW, but

**Pratyaksh Singh:** Thank you.

**Sachin Pandey:** most You

**Pratyaksh Singh:** Or 25 cm.

**Sachin Pandey:** create

**Pratyaksh Singh:** 10 cm.

**Sachin Pandey:** zoom artifact. Uh, artifact

**Pratyaksh Singh:** That\'s

**Sachin Pandey:** data set example background. identify.

**Pratyaksh Singh:** Okay. Enough.

**Sachin Pandey:** Okay. Uh what specific tools or method are used to
manually on your endotages. So highlight

**Pratyaksh Singh:** How much

**Sachin Pandey:** M.

**Pratyaksh Singh:** Minds particularly mindset.

**Sachin Pandey:** Fine. File open source.

**Pratyaksh Singh:** It\'s time. Time is

**Sachin Pandey:** Okay. Relax. Halfway hard rock.

**Pratyaksh Singh:** Uh the garden

**Sachin Pandey:** towards

**Pratyaksh Singh:** cm 10 cm.

**Sachin Pandey:** T322. Okay, but It is same high resolution. We

**Pratyaksh Singh:** Huh?

**Sachin Pandey:** had main

**Pratyaksh Singh:** Yeah.

**Sachin Pandey:** object.

**Pratyaksh Singh:** zoom resolution. First normally begin.

**Sachin Pandey:** Just scing shortly. I\'m basic.

### 01:20:12

**Ratul Shashank:** Sorry guys. Shadow region come.

**Pratyaksh Singh:** We can such a

**Ratul Shashank:** Okay.

**Pratyaksh Singh:** Sorry.

**Sachin Pandey:** It\'s not perfect. Is it?

**Pratyaksh Singh:** Hey. Yes. See, manual

**Sachin Pandey:** lab.

**Pratyaksh Singh:** lab diffult manual.

**Sachin Pandey:** Uh media high

**Pratyaksh Singh:** Yeah,

**Sachin Pandey:** resolution.

**Pratyaksh Singh:** mention your mind. cancel. Okay.

**Sachin Pandey:** Can I exit radio light? It also can both of them are
counted or only the black will be considered contract. Uh uh let\'s make
it clear.

**Pratyaksh Singh:** It\'s still code generate.

**Sachin Pandey:** annotation length of the

**Pratyaksh Singh:** I

**Sachin Pandey:** strips.

**Pratyaksh Singh:** should

**Sachin Pandey:** length of the script. Length.

**Pratyaksh Singh:** be

**Sachin Pandey:** Uh-huh.

**Pratyaksh Singh:** okay.

**Sachin Pandey:** Yeah.

**Pratyaksh Singh:** I think Thank you so

**Sachin Pandey:** Oops.

**Pratyaksh Singh:** much.

**Sachin Pandey:** Top structure large areas large areas concept.

**Pratyaksh Singh:** image

**Sachin Pandey:** Blue

**Pratyaksh Singh:** Blue

**Sachin Pandey:** question.

**Pratyaksh Singh:** table question.

**Sachin Pandey:** Yeah, I\'m sorry. Join images. Join multiple lines.

### 01:29:08

**Sachin Pandey:** Some join

**Pratyaksh Singh:** That\'s

**Sachin Pandey:** artifacts.

**Pratyaksh Singh:** it.

**Sachin Pandey:** What are these?

**Pratyaksh Singh:** Double background. Context

**Sachin Pandey:** That\'s partic.

**Pratyaksh Singh:** 7

**Sachin Pandey:** Sky resolution.

**Pratyaksh Singh:** label. Ver.

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** Yeah.

**Sachin Pandey:** SIP

**Pratyaksh Singh:** Let\'s

**Sachin Pandey:** resolution update.

**Pratyaksh Singh:** pipeline.

**Sachin Pandey:** take screenshot

**Pratyaksh Singh:** Okay.

**Sachin Pandey:** screen Fire shot

**Pratyaksh Singh:** Oh,

**Sachin Pandey:** system

**Pratyaksh Singh:** that\'s

**Sachin Pandey:** comments. Annotations Project Alexa

**Pratyaksh Singh:** a little bit.

**Sachin Pandey:** Check.

**Pratyaksh Singh:** I think user special.

**Sachin Pandey:** Oh yeah.

**Pratyaksh Singh:** But I just remember

**Sachin Pandey:** Yeah. 1 2 3 4 Okay.

**Pratyaksh Singh:** is of

**Sachin Pandey:** Example 1 2 3

**Pratyaksh Singh:** course

**Sachin Pandey:** counting. Okay. Document. Okay. Uh

**Pratyaksh Singh:** Oh, now there

**Sachin Pandey:** Generally,

**Pratyaksh Singh:** 1 2 3 4

**Sachin Pandey:** support a And this had to be changed to film. Zen
press

**Pratyaksh Singh:** minutes

**Sachin Pandey:** remove.

**Pratyaksh Singh:** left. Anyway, short You learn so scared at

### 01:35:55

**Sachin Pandey:** Stop.

**Pratyaksh Singh:** them.

**Sachin Pandey:** Radio checkbook attribute.

**Pratyaksh Singh:** got

**Sachin Pandey:** Hello.

**Pratyaksh Singh:** left.

**Sachin Pandey:** Hello. S4.

**Pratyaksh Singh:** Continue the click. Continue the work. Okay. Okay.
Okay.

**Sachin Pandey:** Add attribute. Small white color. windows. Okay. What
do you see? question. Thank you. Thank you. Ready? My is Hi there. Okay.
Yeah. Project.

**Pratyaksh Singh:** Uh-huh. You can distribute

**Sachin Pandey:** You\'re coming there. Keep

**Pratyaksh Singh:** Multitask.

**Sachin Pandey:** coming.

**Pratyaksh Singh:** Advanc configuration. Advanc size.

**Sachin Pandey:** here.

**Pratyaksh Singh:** What? Define a number of frames to be

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** in Google image size. as a job

**Sachin Pandey:** That\'s it.

**Pratyaksh Singh:** sorting order.

**Sachin Pandey:** Stop. Ignore.

**Pratyaksh Singh:** I

**Sachin Pandey:** Jason, I

**Pratyaksh Singh:** got

**Sachin Pandey:** don\'t

**Pratyaksh Singh:** confirming our export ministry.

**Sachin Pandey:** Thank you. I don\'t know. It\'s okay. Table. Hello.

**Pratyaksh Singh:** Oh, size

**Sachin Pandey:** The info is

**Pratyaksh Singh:** actions. Edit for action. Google.

**Sachin Pandey:** video.

**Pratyaksh Singh:** Okay.

**Sachin Pandey:** Sorry.

**Pratyaksh Singh:** link.

**Sachin Pandey:** I

**Pratyaksh Singh:** Okay.

**Sachin Pandey:** think it\'s It\'s action.

**Pratyaksh Singh:** GW annotation pass.

**Sachin Pandey:** Hello. Okay.

**Pratyaksh Singh:** for delete. Save.

**Sachin Pandey:** Which project?

**Pratyaksh Singh:** Right.

**Sachin Pandey:** Okay. What you

**Pratyaksh Singh:** Everyone capital B7 small.

**Sachin Pandey:** looking

**Pratyaksh Singh:** Segment size. Oh,

**Sachin Pandey:** Yes. Okay.

**Pratyaksh Singh:** Define number of frames 100%.

**Sachin Pandey:** 3:40.

**Pratyaksh Singh:** Submit and continue. Trash me.

**Sachin Pandey:** If I don\'t

**Pratyaksh Singh:** this

**Sachin Pandey:** Perfect. I need

**Pratyaksh Singh:** again.

**Sachin Pandey:** to

**Pratyaksh Singh:** again. Refresh

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** again.

**Sachin Pandey:** Okay. Thank you.

### Transcription ended after 01:57:40

*This editable transcript was computer generated and might contain
errors. People can also change the text after it was created.*
