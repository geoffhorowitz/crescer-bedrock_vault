Jun 19, 2026

## Iris Sync

Invited [[Sachin Pandey]{.underline}](mailto:sachin@crescer.ai)
[[Pratyaksh Singh]{.underline}](mailto:pratyaksh@crescer.ai) [[Niveta
Iyer]{.underline}](mailto:niveta@crescer.ai) [[Hemanth
Sarabu]{.underline}](mailto:hemanth@crescer.ai) [[Geoff
Horowitz]{.underline}](mailto:geoff@crescer.ai) [[Siddharth
Soni]{.underline}](mailto:siddharth@crescer.ai) [[Ratul
Shashank]{.underline}](mailto:ratul@crescer.ai)

Attachments [[Iris
Sync]{.underline}](https://calendar.google.com/calendar/event?eid=NnNzMHVxNzk3MmJqZGVwNXFoN2J1Mjd1OTdfMjAyNjA2MTlUMTYzMDAwWiBnZW9mZkBjcmVzY2VyLmFp)
[[EDA]{.underline}](https://drive.google.com/drive/folders/1oz5HWy8fQCbB8d5mHktRfRUo06hYlEei)

Meeting records
[[Transcript]{.underline}](https://docs.google.com/document/d/1QF-4ggG7f3I-0M8P-NqmBS67LIZ5Xp2aLq_scdTiRIw/edit?usp=drive_web&tab=t.j4xkei1z1obx)

### Summary

The meeting covered technical software workflows, competitive strategy
for Bedrock, and critical improvements to annotation classification
standards.\
\
**Bedrock Tools and Competition**\
The team reviewed Bedrock tool configurations while analyzing
competitive challenges from external firms in topography and bathymetry.
They successfully refined their understanding of tool limitations and
broader market positioning.\
\
**Data Quality and Validation**\
Discussions centered on addressing annotation errors and integrating new
validation strategies for scan data. The team decided to implement a
multi-class annotation system to improve model accuracy and reduce false
positives.\
\
**Documentation and Labeling Strategy**\
The team prioritized Bedrock development by consolidating technical
documentation and defining distinct classification rules for labelers.
These new guidelines will streamline future training and ensure
consistency across the annotation pipeline.

### Decisions

Aligned

-   **Multi-class training strategy adopted** The team aligned to train
    > the model to recognize seven to eight distinct classes instead of
    > limiting training to one or two, enabling the client to select
    > their preferred outputs.

-   **Labeling classification strategy defined** A structured
    > classification system for labelers is established to standardize
    > point cloud data for future model training.

-   **Bedrock project prioritization confirmed** Bedrock labeling is
    > established as the primary project focus, with priority over other
    > tasks effective the following week.

We\'ve **updated the Decisions section** using your feedback.

Let us know what you think:
[[Helpful]{.underline}](https://google.qualtrics.com/jfe/form/SV_5p6FWBVWvynleNU?isGoogler=no&isHelpful=yes)
or [[Not
Helpful]{.underline}](https://google.qualtrics.com/jfe/form/SV_5p6FWBVWvynleNU?isGoogler=no&isHelpful=no)

### Next steps

-   \[Geoff Horowitz\] Add to Sync: Include Ratul in the Boommy Sync
    > meeting series.

    > \[Geoff Horowitz\] Update Blog: Update the shared blog post with
    > the correct streamlet app link.

    > \[Sachin Pandey\] Verify Annotations: Cross check the total count
    > of unique annotations in the Navy data set.

    > \[Sachin Pandey\] Move Data: Transfer the relevant data folder to
    > the team drive for accessibility.

    > \[Ratul Shashank\] Analyze Datasets: Run additional datasets
    > through the visualization tool to provide a more comprehensive
    > report.

    > \[Sachin Pandey\] Share Images: Send annotated images on Slack to
    > clarify visualization concerns regarding the Navy data set.

    > \[The group\] Verify Targets: Validate the location of detected
    > objects in the dead zone using magnetometer data and point clouds.

    > \[Geoff Horowitz\] Contact Client: Query Bridget regarding
    > preferred target resolution, manual labeling methods, and usage of
    > magnetometer data.

    > \[Geoff Horowitz\] Confirm with Bridget: Ask Bridget for
    > clarification on background requirements and contact shape file
    > definitions for the model.

    > \[Sachin Pandey\] Create Labeler Guide: Design a documentation
    > piece for the ground queuing process to improve labeling
    > consistency.

    > \[Sachin Pandey\] Document Bedrock Specs: Compile all project
    > discussions, details, and open questions into a comprehensive file
    > for future reference.

    > \[Sachin Pandey\] Define Labeling Classes: Determine specific
    > categories for point cloud annotation to enable consistent
    > training for the model.

    > \[Sachin Pandey\] Inquire File Location: Message the IICA channel
    > to request the location of 7K files.

    > \[Geoff Horowitz\] Provide File Location: Post the path for 7K
    > data on the IICA channel for team accessibility.

    > \[Pratyaksh Singh, Ratul Shashank\] Develop Training Pipeline:
    > Collaborate on building the U-Net based training pipeline by
    > performing code reviews and joint development.

### Details

-   **Bedrock Tool Demonstration**: Geoff Horowitz and Sachin Pandey
    > coordinated on Bedrock tool settings, identifying that port 7001
    > is used for the power language and 7003 is used for Iris Insights
    > ([[00:02:11]{.underline}](#section)). They discussed the necessity
    > of distinguishing between demo data and the actual Tetra Tech data
    > within the app, and Sachin Pandey demonstrated the correct
    > procedure for interacting with the cross-section functionality
    > ([[00:05:42]{.underline}](#section-2)).

-   **Conference Update and Competitive Analysis**: Geoff Horowitz
    > provided an update on a recent conference, noting that they
    > successfully generated interest in their QA tools among academics,
    > as current automated classification workflows often ignore the QA
    > space ([[00:08:03]{.underline}](#section-3))
    > ([[00:13:17]{.underline}](#section-6)). They reported that while
    > attendees are frequently experimenting with machine learning and
    > Segment Anything (SAM) tools, these often prove ineffective when
    > used with point cloud data that lacks RGB color values
    > ([[00:14:33]{.underline}](#section-7)).

-   **Mach 9 Competitive Intelligence**: Geoff Horowitz discussed the
    > competitor Mach 9, noting that they are a YC company that expanded
    > from Department of Transportation work into aerial topography and
    > bathymetry ([[00:08:03]{.underline}](#section-3)). Although Mach 9
    > recently secured a contract with a government agency (the US Army
    > Corps of Engineers, now known as I-atlas) for work previously
    > targeted by the team, Geoff Horowitz indicated that they still
    > intend to pursue collaboration with this agency
    > ([[00:10:14]{.underline}](#section-4)).

-   **Mach 9 Interface Capabilities**: Geoff Horowitz noted that Mach 9
    > maintains a sophisticated graphical user interface (GUI) and
    > processes data at a minimum point density of 100 points per square
    > meter ([[00:18:02]{.underline}](#section-10)). Although Mach 9
    > primarily focuses on drone or mobile-based lidar, their expansion
    > into the bathymetry sector poses a competitive challenge that the
    > team did not previously anticipate
    > ([[00:19:16]{.underline}](#section-11)).

-   **Danish Royal Navy Dataset Analysis**: Sachin Pandey presented
    > findings from the Danish Royal Navy dataset, identifying
    > significant issues including duplicate annotations across files,
    > varying frequency types, and missing data
    > ([[00:20:26]{.underline}](#section-12)). Out of approximately 180
    > files, they found only seven unique annotations, several of which
    > were located within \"dead zones\" of the scan, raising questions
    > about the validity of those detections
    > ([[00:22:07]{.underline}](#section-13))
    > ([[00:26:19]{.underline}](#section-16)).

-   **Visualization and Scan Dead Zones**: The team discussed the
    > difficulty of visualizing side-scan sonar data, particularly in
    > dead zones where objects are not apparent in standard grayscale
    > TIFF images ([[00:26:19]{.underline}](#section-16))
    > ([[00:33:06]{.underline}](#section-20)). Ratul Shashank reported
    > success using open-source \"Open Side Scan\" software to visualize
    > XTF files, which helped identify objects that were missing from
    > the primary annotation pipeline
    > ([[00:27:46]{.underline}](#section-17))
    > ([[00:33:06]{.underline}](#section-20)).

-   **Magnetometer Data Integration**: Ratul Shashank and Sachin Pandey
    > explored the use of magnetometer (MAG) data to verify the
    > existence of objects in locations where visual inspection provided
    > no clear evidence ([[00:34:48]{.underline}](#section-21)). While
    > magnetic field fluctuations can indicate potential items, they
    > concluded that pinpointing the exact location of these objects
    > remains difficult and requires further analysis across larger
    > datasets ([[00:36:59]{.underline}](#section-22)).

-   **Object Validation Strategy**: To address the identified annotation
    > issues, the team agreed to validate object locations using .las
    > files and S7K data, as the current manual annotation process
    > relies primarily on XTF and MAG data
    > ([[00:39:59]{.underline}](#section-24)). Geoff Horowitz emphasized
    > the need to verify if the objects labeled in scan \"dead zones\"
    > are valid, noting that a physical object should ideally be visible
    > on both sides of a scan, rather than appearing only in the center
    > ([[00:41:23]{.underline}](#section-25)).

-   **Resolution and Processing Efficiency**: Sachin Pandey suggested
    > increasing the data processing resolution from the default 0.25
    > meters per pixel, noting that open-source data typically has
    > higher resolution. Pratyaksh Singh cautioned that while increasing
    > resolution improves texture visibility, it may introduce
    > corruption or noise, and they must verify the optimal operational
    > resolution with the client
    > ([[00:43:47]{.underline}](#section-27)).

-   **Client Coordination for Technical Requirements**: The team decided
    > to consolidate their technical questions for the client, Bridget,
    > regarding operational resolutions and the specific methodology for
    > using MAG data ([[00:43:47]{.underline}](#section-27))
    > ([[00:46:22]{.underline}](#section-29)). This approach aims to
    > ensure they receive consistent instructions on how the client
    > utilizes magnetic markers in conjunction with side-scan data
    > ([[00:46:22]{.underline}](#section-29))
    > ([[00:50:58]{.underline}](#section-33)).

-   **Port of Iceberg Background Artifacts**: Regarding the \"Port of
    > Iceberg\" dataset, Geoff Horowitz explained that the client
    > specifically wants them to recognize background artifacts caused
    > by submersible roll, which their previous model incorrectly
    > identified as contacts ([[00:52:05]{.underline}](#section-34)).
    > They agreed to focus on training the model to distinguish these
    > specific roll-based artifacts from actual contacts to avoid false
    > positives ([[00:54:49]{.underline}](#section-36)).

-   **Refining Annotation Classification**: Pratyaksh Singh and Geoff
    > Horowitz agreed to move away from binary (contact vs. non-contact)
    > classification ([[00:55:46]{.underline}](#section-37))
    > ([[01:00:22]{.underline}](#section-41)). Instead, they will
    > implement a more discreet approach using 7 to 8 distinct classes,
    > which will allow them to better categorize items like sand ripples
    > and specific anomaly types, thereby improving the overall
    > performance and specificity of their model
    > ([[00:59:21]{.underline}](#section-40)).

-   **Defining Labeler Classes for Model Training**: Pratyaksh Singh
    > proposes establishing specific classes for labelers to improve the
    > model training process, suggesting that they should identify and
    > classify distinct features, including contacts such as slide
    > discoloration. Pratyaksh Singh argues that this approach will help
    > the model handle distribution shifts by correctly categorizing
    > data points, and they obtain agreement from the team to provide
    > labelers with a set of classes to facilitate this
    > ([[01:01:19]{.underline}](#section-42)). Geoff Horowitz notes that
    > if this process slows down the labeling, they can involve
    > additional labelers, though Pratyaksh Singh anticipates that the
    > current team will maintain a similar pace
    > ([[01:02:26]{.underline}](#section-43)).

-   **Labeler Performance and Quality Concerns**: Sachin Pandey reports
    > that the labelers are processing between 100 and 200 files daily,
    > with recent output on photo map data described as nearly perfect.
    > However, Sachin Pandey identifies a recurring quality issue where
    > labelers are focusing on minor surface irregularities while
    > missing major mistakes, such as solar panels being incorrectly
    > classified as ground ([[01:02:26]{.underline}](#section-43)).

-   **Developing Guidance Documentation for Labelers**: To address the
    > issues with labeling accuracy, Pratyaksh Singh suggests creating a
    > detailed guidance document for the labelers, similar to a previous
    > document created by Sid, to clearly define classification
    > requirements. The team agrees that this documentation should
    > clarify how to identify specific features, such as solar panels,
    > potentially by instructing labelers to use cross-sections to
    > verify surface variations ([[01:03:38]{.underline}](#section-44)).
    > Pratyaksh Singh and Sachin Pandey decide to design this document,
    > specifically for ground quality control, over the weekend
    > ([[01:04:51]{.underline}](#section-45)).

-   **Compiling Comprehensive Documentation for Bedrock**: Pratyaksh
    > Singh requests that Sachin Pandey compile all details regarding
    > Bedrock into a single, comprehensive document to prevent the need
    > for redundant data reviews. This document is intended to include
    > all observations, questions for stakeholders like Bridget, and
    > granular details, with Pratyaksh Singh emphasizing that they
    > should not omit any information
    > ([[01:04:51]{.underline}](#section-45)). Sachin Pandey agrees to
    > organize this data, including test tasks derived from the
    > transcript, to ensure the information is fully documented in black
    > and white ([[01:05:54]{.underline}](#section-46)).

-   **Prioritization of Bedrock Labeling**: The team reaches a consensus
    > that Bedrock labeling will take priority starting the following
    > week. Pratyaksh Singh confirms that Sachin Pandey is focused
    > solely on Bedrock, and they plan to finalize the specific classes
    > for the labelers to enable the commencement of the model training
    > process ([[01:06:47]{.underline}](#section-47)).

-   **Team Status Updates and Pipeline Coordination**: Ratul Shashank
    > provides an update on their current workload, noting they are
    > reviewing annotations for Boommy and have completed the S7K to
    > LAST pipeline, which now requires data for validation. Regarding
    > file locations, Geoff Horowitz instructs Sachin Pandey to send a
    > message on the IICA channel so that the information is accessible
    > to everyone. Finally, Pratyaksh Singh and Ratul Shashank agree to
    > coordinate on the U-Net based training pipeline for Bedrock, which
    > will involve collaborative review and development
    > ([[01:07:56]{.underline}](#section-48)).

*You should review Gemini\'s notes to make sure they\'re accurate. [[Get
tips and learn how Gemini takes
notes]{.underline}](https://support.google.com/meet/answer/14754931)*

*How is the quality of **these specific notes?** [[Take a short
survey]{.underline}](https://google.qualtrics.com/jfe/form/SV_9vK3UZEaIQKKE7A?confid=LBdqE9QJkiDhFkhBrP3aDxIUOAIIigIgABgECA&detailid=standard&screenshot=false)
to let us know your feedback, including how helpful the notes were for
your needs.*

📖 Transcript

Jun 19, 2026

## Iris Sync - Transcript

### 00:02:11

**Sachin Pandey:** happen.

**Geoff Horowitz:** Hey guys.

**Pratyaksh Singh:** Hi everyone.

**Sachin Pandey:** I do

**Geoff Horowitz:** Okay. Uh Rul, I I should have added you to the
Boommy Sync, too, which I forgot to do.

**Ratul Shashank:** Hello everyone.

**Geoff Horowitz:** Uh but I will add you on that for Monday. One
second. Okay. Um, I\'ll give you guys a little bit of an update on the
conference. Uh, but I actually want to talk mostly about Bedrock. Um,
that said, I I need a second because Satcha, maybe you can help me with
this. Um, so Hammon is meeting with a company called Ulisses. Uh, are
you guys familiar with this? Ulyses. Uh, underwater.

**Pratyaksh Singh:** I can\'t see your screen.

**Geoff Horowitz:** They call themselves.

**Pratyaksh Singh:** Okay. Okay.

**Geoff Horowitz:** Say what?

**Pratyaksh Singh:** Nothing. Nothing. Uh, your screen was frozen. It\'s
working now.

**Geoff Horowitz:** Oh, okay. I I think it\'s this company, but I\'m not
positive. I think it\'s this company. Um, but anyway, so he\'s meeting
with them today and he asked if we have anything from Bedrock that we
can show them.

### 00:04:01

**Geoff Horowitz:** Sachin, I was thinking number one, we could show
them the um our streamlet app. Do we have a stream app up?

**Sachin Pandey:** Yes, it is. It will be on 7,000.

**Geoff Horowitz:** Bedrock. I have Why can\'t I just share my whole
screen? Uh, what did you I have 5006. That\'s not the right

**Sachin Pandey:** 7,02 these are okay I haven\'t updated it here I
updated

**Geoff Horowitz:** one.

**Sachin Pandey:** in the blog you shared table before

**Geoff Horowitz:** Ah. Ah. Okay. I\'ll update it here too.

**Sachin Pandey:** yesterday uh

**Geoff Horowitz:** What? I couldn\'t hear 7,000 and what?

**Sachin Pandey:** 72 two or one. I\'m not

**Geoff Horowitz:** R1. Well, we\'ll find out.

**Sachin Pandey:** sure.

**Geoff Horowitz:** Huh. Okay. Uh, okay. And so we have some defaults
here,

**Sachin Pandey:** This

**Geoff Horowitz:** so that\'s okay.

**Sachin Pandey:** 7,0001 will be the power language.

**Geoff Horowitz:** Oh, f\*\*\*. Oh, nice. Nice. Okay. All right. I
don\'t think he wants to show that, but

### 00:05:42

**Sachin Pandey:** like 7,0003

**Geoff Horowitz:** where does 7,0003

**Sachin Pandey:** I guess it will Power Linux 7,0001 is shadow
leveling.

**Geoff Horowitz:** Um, 2003. Oh. Oh, this is Iris Insights. Cool. Okay.
03. And this this was the labeling tool that you said was 7,0001, right?
Or was it the cross-section?

**Sachin Pandey:** Uh both are in the same like in the latest.

**Geoff Horowitz:** Same tool. No.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** Is this is 7001 the demo tool?

**Sachin Pandey:** Uh yes, like the same tool but you asked to replace
the data with the demo data.

**Geoff Horowitz:** Right. I just meant these these are actually for
tetra techch data not demo data. Right. So plus am I am I
misunderstanding what you\'re saying Sachin?

**Sachin Pandey:** uh lighter cross-section. I don\'t think those ports
are running anymore.

**Geoff Horowitz:** Yeah they\'re not this this

**Sachin Pandey:** Uh

**Geoff Horowitz:** tool here. So this both is dem replacement and
you\'re saying this is also uh I can do a cross-section here right

**Sachin Pandey:** Right click to

### 00:08:03

**Geoff Horowitz:** left click point.

**Sachin Pandey:** open.

**Geoff Horowitz:** Wait click click right. Oh I see. Push it first and
then Okay. Sweet. So same

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** tool. Great. Sweet. Thank you. Um, okay. I just need
one more minute to look for some images for Okay, I\'ll have to look
later. Um, so this conference, how did this conference go? This
conference went okay. The conference went okay. Um, you know, like we do
at most of these conferences, we drumed up some excitement. uh you know
there\'s some people that that are really interested that we\'re going
to follow up with. We did hear so Mach 9 was also at the conference. Um
which do you pretty much such do you guys remember Mach 9 at all? Um
they are a YC company and they they started with um like Department of
Transportation. Um they started with Department of Transportation doing
a lot of like road work like you know finding curbs um you know street
signs all that stuff.

### 00:10:14

**Geoff Horowitz:** My understanding is that with a lot of government
cuts in the US, they were struggling to to get revenue and so they
expanded into other areas um including Ariel Toppo, including now it
turns out uh Ba\'athy. Um they so I don\'t know if you guys remember but
like two years ago you know we were working with or we were trying to
work with Walbert and Jabax to to do some of their data. So it turns out
that they at some point over the last two years engaged with these guys
um with a like a a contract. So that was that was disheartening. Um but
at the same time we were talking to them and they said yeah let\'s you
know let\'s let\'s process some data. Let\'s you know do this together.
So um so it sounds like it\'s still not really sounds like we get
another opportunity there. Any questions for what I\'ve said so far?

**Pratyaksh Singh:** I didn\'t I didn\'t understand the thing with uh
Mark 9 working with pulp and then you know

**Geoff Horowitz:** So, so it\'s a little it\'s a little complicated.

### 00:11:39

**Geoff Horowitz:** It\'s not actually Walpert. So,

**Pratyaksh Singh:** you

**Geoff Horowitz:** Walpert got the contract from this government
agency, the US Army Corps of Engineers. Walpert got the contract to do
all of the Ba\'athy um detections around the entire coast of the US. And
so that\'s like a special group within Wilbert that

**Pratyaksh Singh:** Mhm.

**Geoff Horowitz:** works directly with this with this government
agency. Um so when we were saying so when we were saying we were working
working with Walbert

**Pratyaksh Singh:** Okay.

**Geoff Horowitz:** like project you remember this but like two years
ago when we were working with Chris Min and um and Nick Johnson um
they\'re they\'re actually this government agency. They\'re not really
Walpert.

**Pratyaksh Singh:** Okay.

**Geoff Horowitz:** Are you following me there? As opposed to when we
worked with Walpert like three months ago uh with that guy Michael Chris
Christy

**Pratyaksh Singh:** Mhm.

**Geoff Horowitz:** Christy Chrissy. He he is Walpert. He\'s Walpert
like traditional Walpert. Um so that\'s just clarifying the players a
little bit. So this government agency uh J they changed their name now
they\'re called I atlas it doesn\'t matter it\'s just a name right so
this government agency who we were trying to get the work for um it
turns out gave a contract to this company Mach 9 to do some of the work
that we wanted to do and we didn\'t know about

### 00:13:17

**Pratyaksh Singh:** Mhm.

**Geoff Horowitz:** that until just now. Okay. But we were talking to
them and we were saying, you know, what the hell? What\'s up?

**Pratyaksh Singh:** Okay.

**Geoff Horowitz:** And uh and that\'s when that\'s when the ILS guys
were like, look, let\'s let\'s, you know, let\'s let\'s try it. Let\'s
work together. We\'ve got more data. Let\'s do it. So, we\'ll see where
that goes. Um but everything else you know we got we got pretty good
feedback. Uh it was a very kind of academic focused conference not an
industry focused conference. We we got a lot of interest from academics
for using Iris. I did show off the um QA tools because that was that was
something that we we had talked about was you know lots of different
people are trying out various machine learning based classification
tools but nobody is really addressing anything in the QA space. So there
was some interest around there. That said, you know, exactly what I just
said there.

### 00:14:33

**Geoff Horowitz:** Everybody and their mother is is building, you know,
um some sort of automated classification tool. Um there\'s a lot of SAM
going on.

**Pratyaksh Singh:** Okay.

**Geoff Horowitz:** Um you know, segment anything. There\'s a lot of um
you know just cloud-based right cloud code based tools. Um that was
another insight that that we kind of saw there. Everybody\'s doing it.
Everybody\'s at least trying it internally. So you know I mean I think
we know that it\'s not that trivial, right? Um, it\'s easy to set up
something, but it\'s hard to get really good results. But, uh, you know,
is that going to take them some time to realize, right?

**Pratyaksh Singh:** like what is what\'s the feedback that you got from
people using these tool? So the one of the reason why segment anything
isn\'t scalable is because usually you don\'t get uh colors with the
with the point clouds right and that\'s where your image based tools
image based tool fail right because if you get colors then most of the
time segment anything and all these things would work but uh usually you
don\'t get color uh you don\'t get colors with the point the RGB values
And that is like one

### 00:16:05

**Geoff Horowitz:** Sorry.

**Pratyaksh Singh:** of I was saying like that that is one of the
failure cases that\'s

**Geoff Horowitz:** Go ahead.

**Pratyaksh Singh:** why we uh we don\'t use segment anything and these
things uh but what is the feedback that you got from them you know are
they excited towards it are they are they seeing success what is it

**Geoff Horowitz:** I I I think the general feedback is that they think
they\'re seeing success, right? These are not machine learning experts,
right? And so they they look at this stuff and they say, \"Oh, you know,
like whatever.\" They\'re not saying this explicitly,

**Pratyaksh Singh:** f\*\*\*.

**Geoff Horowitz:** but the the impression that I get is, oh, you know,
we spent we spent a month working with cloud code and, you know, we came
up with something and look, it seems to be working. Um, but but I think
I think your point, which which I agree with, is that, you know, I\'m
not sure that what they have actually adds value, right?

**Pratyaksh Singh:** Right.

**Geoff Horowitz:** And I think that they\'ll find that out pretty
quickly. Does that make any sense?

### 00:17:00

**Pratyaksh Singh:** H I think it does. But how are they using clot
code? Are they are they writing this terascript? Are they using clot
code to write terascripts for

**Geoff Horowitz:** I I didn\'t dig in.

**Pratyaksh Singh:** them?

**Geoff Horowitz:** I didn\'t dig in. Maybe Hamoth did.

**Pratyaksh Singh:** Okay.

**Geoff Horowitz:** Maybe Hamoth did.

**Pratyaksh Singh:** It will be interesting to know.

**Geoff Horowitz:** But I\'m here.

**Pratyaksh Singh:** It will it will be interesting to know because
natively cloud code doesn\'t work with point clouds,

**Geoff Horowitz:** Yeah,

**Pratyaksh Singh:** right? So it will be interesting to know what they

**Geoff Horowitz:** I I should have I should have specified, you know,

**Pratyaksh Singh:** doing.

**Geoff Horowitz:** they\'re using like cloud code to generate machine
learning tools, not using cloud code directly.

**Pratyaksh Singh:** They\'re using clot code to generate machine
learning tools uh to like to

**Geoff Horowitz:** Yeah. like to to Yeah.

**Pratyaksh Singh:** train.

**Geoff Horowitz:** to build a model for example.

**Pratyaksh Singh:** Oh, got it. Got it.

**Geoff Horowitz:** Yeah. Sorry. Sorry for the uh confusion there.

### 00:18:02

**Geoff Horowitz:** You say nice.

**Pratyaksh Singh:** Nice.

**Geoff Horowitz:** One one thing that really stood out to me here is um
you know Mach 9 has a good guey.

**Pratyaksh Singh:** What the website? Where is the GUI?

**Geoff Horowitz:** what bedrock

**Pratyaksh Singh:** No,

**Geoff Horowitz:** said.

**Pratyaksh Singh:** no. I\'m saying uh where is the GUI?

**Geoff Horowitz:** I mean what you can see here is their their
interface right it\'s how it\'s how the users are interfacing with their
data um

**Pratyaksh Singh:** Mhm.

**Geoff Horowitz:** so so that when they show off their demos it looks
like there\'s a lot to see even though you know we know that a lot of
it\'s just going on in the background right but I mean you know being
able to kind of interact with with the data in this way and They must
have some sort of SAM model going on. I don\'t know if you can see it in
this video here, but uh you know they were they were they had another
video that they were showing where they were kind of clicking segments
and um you know it was filling in uh like power lines and things like
that, right?

### 00:19:16

**Geoff Horowitz:** And their data looked clean. Meanwhile, they said
they said their minimum point density is three digits, right? So like
minimum 100 points per square per square

**Pratyaksh Singh:** Mhm. So yeah, like when I look at them,

**Geoff Horowitz:** meter

**Pratyaksh Singh:** it doesn\'t look like they they concern themselves
with aerial point close. So these whatever you see it looks like drone
or uh or you know uh those mobile based

**Geoff Horowitz:** that is that is where they were. That is where they
were.

**Pratyaksh Singh:** lighter

**Geoff Horowitz:** That\'s exactly where they were. and they\'re
expanding into these other spaces. So, you know, we saw them at drone at
Geo Week whatever two years ago, right? But we didn\'t really view them
as competitors because they weren\'t really in the same spaces as we

**Pratyaksh Singh:** All

**Geoff Horowitz:** were.

**Pratyaksh Singh:** right.

**Geoff Horowitz:** Turns out that they\'re expanding into not even
Topo, you know, which which we know there\'s some players in, but to
buttric, which, you know, kind of historically we thought we were the
only ones.

### 00:20:26

**Geoff Horowitz:** So, um, project, I\'m happy to talk more about this,
but I I do want to spend some time on bedrock. Um, so if you if you want
to ping me later, we can we can chat more.

**Pratyaksh Singh:** Yep.

**Geoff Horowitz:** Okay,

**Pratyaksh Singh:** Makes sense.

**Geoff Horowitz:** great. Sorry for taking up so much time on that, but
uh let\'s Yeah, let\'s do Bedrock. What do you guys have? What kind of
updates do you guys have? project. Do you want to start?

**Pratyaksh Singh:** I think Sachin has more information than me. They
should they should present it.

**Geoff Horowitz:** Okay.

**Sachin Pandey:** Okay. Uh I will share my screen. So mainly I was
looking into two data set. One was this Danish Royal Navy and other was
the port of something. So uh like first thing we noticed was like this
they have like uh there are only like seven annotations all over the
data set out of like around 180 files there is only seven annotations
and uh like mostly they are like classified as like mines.

### 00:22:07

**Sachin Pandey:** These are all the seven annotations they have and uh
out of seven three are like in the what this black region where we
can\'t see

**Geoff Horowitz:** So, Son, I just want to confirm. She said that there
were 10 in this data set,

**Sachin Pandey:** them.

**Geoff Horowitz:** but you only actually you you dug in and there were
actually only seven. Is that right?

**Sachin Pandey:** Uh give me a second. And I can open the sheet that
you shared. It was five. I guess in this data set it was mentioned five.

**Geoff Horowitz:** Oh, it was

**Sachin Pandey:** So out of seven like I thought two were uh

**Geoff Horowitz:** five.

**Sachin Pandey:** like royal. Yeah. 10 US.

**Geoff Horowitz:** It was 10.

**Sachin Pandey:** Yeah, but I like uh I confirmed it multiple times
like there were uh multiple instance like in total there were 14
annotation but same thing was repeated

**Geoff Horowitz:** There were What do you mean the same thing was
repeated?

**Sachin Pandey:** like same annotations were in uh different different
folder like file names were

### 00:23:29

**Geoff Horowitz:** So, same annotations were in different folders. Um,
so there\'s so there\'s XTFS that are repeated. Is that what you\'re
saying?

**Sachin Pandey:** I need to check like XTF are getting repeated but
it\'s in a different

**Geoff Horowitz:** Yes.

**Pratyaksh Singh:** Yes.

**Sachin Pandey:** way like uh for this reason the HTF is getting
repeated.

**Geoff Horowitz:** Okay.

**Sachin Pandey:** the same reason is scanned twice and this is with the
like low frequency and this is with the high frequency and these are
stored in a different folder like it has a lower pass folder where like
even on the same resolution like these both have the same resolution
like pixel per inch pixel per meter but both look like clearly different
because of the like because of the frequency for more detail like you
can check this table out. It is the difference between both the XTF
mainly like it it is

**Geoff Horowitz:** Mhm.

**Sachin Pandey:** missing a lot of data like what lot of these things
are just like not useful in the one which have the like low resolution
one. This is the low resolution one.

### 00:24:49

**Geoff Horowitz:** Sergeant, where is this file saved?

**Sachin Pandey:** Uh this talk uh I can

**Geoff Horowitz:** Uhhuh.

**Sachin Pandey:** share it with you.

**Geoff Horowitz:** Is it saved on a drive? Is it saved on our drive?

**Sachin Pandey:** Uh no I haven\'t shared it. Put it in a different I
have to move this folder to some drive.

**Geoff Horowitz:** Can you move it here, please? Or I can uh I can I
can I\'ll send this to you on Slack

**Sachin Pandey:** at this location like ADA.

**Geoff Horowitz:** also.

**Sachin Pandey:** It\'s there\'s already a another drive bedrock in and

**Geoff Horowitz:** Yeah, there\'s Yes.

**Sachin Pandey:** text.

**Geoff Horowitz:** Yes, that folder. Okay.

**Sachin Pandey:** So generally like it\'s different type of data like I
was thinking like the same XTF contains two different uh like both the
low frequency and high frequency data and uh but it was not the case. So
I will cross cross check this part again like uh what were the other
like seven annotations because like I only pulled the unique ones. So I
will just cross check this part like how many total annotations are
there but like out of like uh seven I found like three were like

### 00:26:19

**Geoff Horowitz:** All right.

**Sachin Pandey:** these uh like in the center region. Uh, correct me if
I\'m wrong, but this is the same image for this file.

**Ratul Shashank:** Yes. The visualization one,

**Sachin Pandey:** So,

**Ratul Shashank:** right?

**Sachin Pandey:** yeah.

**Ratul Shashank:** Yes. Yes.

**Sachin Pandey:** So uh so Jeff this yellow one is the like rul used
the opensource software to view the extent directly and we see like this
portion which is like completely

**Geoff Horowitz:** Mhm. Mhm.

**Sachin Pandey:** invisible in the dam black and white dem like this
part is like little bit visible in clearly visible in the other tool.

**Geoff Horowitz:** Is that just one side of the

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** scan?

**Sachin Pandey:** Uh like it is split between two sides.

**Geoff Horowitz:** Um, but there shouldn\'t be anything in the middle
of the scan cuz it\'s a dead zone.

**Sachin Pandey:** It is like what I think it will be like uh above the
surface like it is not in like expanding here. It is expanding upward.

**Geoff Horowitz:** I\'m having trouble visualizing that.

**Sachin Pandey:** Uh,

### 00:27:46

**Geoff Horowitz:** You you you know what I\'m saying about this should
be a dead zone,

**Sachin Pandey:** give me a second.

**Geoff Horowitz:** right?

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Yeah. Okay.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Rachel, which which software were you using?

**Ratul Shashank:** Uh actually I used just wait a minute I use open
site scan. It uh basically visualizes any XDF

**Geoff Horowitz:** Yeah.

**Ratul Shashank:** files.

**Geoff Horowitz:** Yeah. Yeah. We\'ve we\'ve tried that out and it was
it was pretty good. I\'m

**Sachin Pandey:** I\'m trying to find a visualization uh that I show
for this side scan which is like which make it easier to understand like
why the dead zone is there and how it looks.

**Geoff Horowitz:** Right. Um, I mean, look, what all this is getting to
though is go ahead

**Pratyaksh Singh:** Hey, hey guys. Sorry, but uh Sachin, there are a
lot more things that you want to discuss,

**Geoff Horowitz:** protect.

**Pratyaksh Singh:** right? Can you first summarize everything and then
we can we can you know we can dig into things more.

### 00:29:37

**Pratyaksh Singh:** I don\'t want to just get stuck on one thing.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** Good idea.

**Sachin Pandey:** So yeah like after this like uh like out of three

**Pratyaksh Singh:** All right.

**Sachin Pandey:** annotations were in the dead zone and the remainings
were like very hard to spot like if I if I like toggle off the
annotation like you won\'t be able to like even guess which location is
uh there. So like uh yeah so like there isn\'t any feature right where
uh any hint like where could be the like the region if I turn on
annotation like okay let\'s check for

**Geoff Horowitz:** Have we have we compared this?

**Sachin Pandey:** the

**Geoff Horowitz:** Let me double check containing targets.

**Sachin Pandey:** like these are very hard to spot

**Geoff Horowitz:** Do they do they give us This is all in our
generation pipeline, right? Like, are we confident that we\'re looking
at the right

**Sachin Pandey:** Yeah, we are using the annotation to save.

**Geoff Horowitz:** spot? Do we have the mag data session?

**Sachin Pandey:** Uh was looking into the mag data for this but we

### 00:31:25

**Geoff Horowitz:** Are we? Yeah. Please,

**Sachin Pandey:** didn\'t like uh these these are the reports for

**Geoff Horowitz:** please.

**Sachin Pandey:** the

**Geoff Horowitz:** Okay, we we can get back to this, but that that\'s
my question is I think I think we need to verify I think we need to
verify that these objects should be where we\'re where we\'re seeing
them somehow on Bedrock\'s data. Whether that\'s using a mag overlay,
looking at these um summary charts, like I think we need to
independently verify this. It seems weird to me that we\'re getting
objects in a dead zone.

**Sachin Pandey:** Yes,

**Geoff Horowitz:** That doesn\'t feel right.

**Sachin Pandey:** like uh for that like Runul was looking into it like
using the mag data

**Geoff Horowitz:** Yeah.

**Sachin Pandey:** to at least get some hint whether the object is there
or not. So we don\'t have a image for this file but we do have the lab
file for this but like similar to last time it was not uh giving us much
data like it was mostly uh like

**Geoff Horowitz:** Yeah,

**Ratul Shashank:** If I may uh sorry to you off such uh actually when

### 00:33:06

**Geoff Horowitz:** of

**Sachin Pandey:** Thank

**Geoff Horowitz:** course.

**Ratul Shashank:** I was looking into the data uh the problem with our
annotations is it\'s all in grayscale right so when

**Sachin Pandey:** you.

**Ratul Shashank:** we annotate it not much is seen to our eyes. But
when that same image when I load it up into that viewer that opens scan
software, we can see that there is an object uh which was not visible in
this uh uh annotations. So it\'s like there is a need zone when the data
was taken. Uh so what we tried to do we took the data of sides scan
sonar and the uh tiff folder. So we were basically trying to pinpoint
the object that was not that was not visible in the xdf file by that mag
data. So what Sachin found uh Sachin can you please uh show that file
again?

**Sachin Pandey:** This

**Ratul Shashank:** I know that uh

**Sachin Pandey:** This

**Ratul Shashank:** visualization

**Geoff Horowitz:** the viewer.

**Ratul Shashank:** that uh visualization uh if I can I share my screen
I would be I could explain it uh much

### 00:34:48

**Geoff Horowitz:** Of course,

**Sachin Pandey:** looks

**Ratul Shashank:** better. like this like this was the data that uh we
were that we were looking into particularly. Uh as we can see that the
annotated one it is showing something is in the middle of this black
zone and this picture is in grayscale. So we are losing much clarity in
the visual side. But when the same folder so in the same file is loaded
up. Wait this this one. Yeah. uh this port side scan is equivalent of
this upper strip and this starboard side scan is equivalent of this
lower strip. So we are losing the annotations because of the visual
problem. the object or anything is there but because of uh uh maybe
grayscale or anything it\'s not showing up. So we used magnetometer data
and the side scan sonar data. Just wait a minute I need to find that
file. Yeah. Yeah. Sorry. When we overlay both of those file like this
data is taken from the TIFF file that uh uh we put into our pipeline.

### 00:36:59

**Ratul Shashank:** This zone this zone is basically saying that the
magnetic field it approaches and it passed right through them. So there
is possibility of uh a substance which is lightly magnetic but not to a
great degree because if that would be the case we would have find higher
uh values like in the dark red zones. So at this point we are only able
to we are looking into it further how can we pinpoint it to a better
degree but this problem is the ner uh sorry to cut you off but this
problem is

**Geoff Horowitz:** So,

**Ratul Shashank:** in the ner region because we can\'t look into it
through the visualiz apart from the visualization and uh that pinpoint
that pointing out is the issue.

**Geoff Horowitz:** Where\'s the native region? Um,

**Pratyaksh Singh:** Do we have any examples when it is at the Enter.
That\'s

**Geoff Horowitz:** right.

**Ratul Shashank:** Uh I I need to run

**Pratyaksh Singh:** it.

**Ratul Shashank:** it with a few more data because I have only I I came
up with this uh just in the last minute.

### 00:38:31

**Ratul Shashank:** So I have not done it with a lot of data set because
I have also uh having a hard time finding out the XTF file and the exact
correlating OFG files for the same uh latl long geol location. So when I
will get back to you uh when I will have a proper proper view on this. I
was just sharing a preliminary report that we can have into finding this
uh bottleneck.

**Pratyaksh Singh:** All right. Uh, makes sense. Such an in the in the
black and white the grayscale image, you saying that the mines aren\'t
visible, right?

**Sachin Pandey:** Uh

**Pratyaksh Singh:** Okay. So we need to let\'s confirm it with the with
the open source tool

**Sachin Pandey:** yes.

**Pratyaksh Singh:** that with the tool that uh Ratul is using if it\'s
not visible you know just share images on slab right with annotation and
these things so that you know Jeff can talk with them or we can decide
on the next step

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** there and there

**Sachin Pandey:** Okay.

**Geoff Horowitz:** Um.

**Sachin Pandey:** Like there\'s also high chance like they are not like
only using the images.

### 00:39:59

**Sachin Pandey:** They have the like last files for the same data S7K
and like mag data for finding the uh magnetic regions and also some kind
of like sensor which is which can scan under the seabed to like 1 to two
2 m.

**Pratyaksh Singh:** Jeff, is that the case or do they only use Xer for

**Geoff Horowitz:** Um my understanding is that for the manual
annotation they only

**Pratyaksh Singh:** manualation?

**Geoff Horowitz:** use the XTFS and the MAG data. They don\'t use the
point cloud data. Um but I mean if we really are running into this I
think for our purposes it wouldn\'t be unreasonable to validate with the
point cloud data if if we can do it easily and suction you know we have
a way of maybe we might have a way of reading S7K Okay. Um, we obviously
have a way of viewing and interacting with the point clouds, so that
might be easy for

**Pratyaksh Singh:** Yeah, makes sense.

**Geoff Horowitz:** us.

**Pratyaksh Singh:** So we sin can we like load it on portry confirm
there also will it be

### 00:41:23

**Sachin Pandey:** Yeah.

**Pratyaksh Singh:** possible?

**Sachin Pandey:** I will check the files which already have the last
file available

**Geoff Horowitz:** Oh, they do have last file.

**Sachin Pandey:** and yeah I just found that I found one file which has

**Pratyaksh Singh:** Mhm.

**Geoff Horowitz:** Okay, great. Great.

**Sachin Pandey:** test

**Geoff Horowitz:** I was going to say if they just had S7K, it might be
a a process, but

**Sachin Pandey:** uh it is for the file that was just the one with the
dead zone.

**Geoff Horowitz:** so so look I mean you know if this is actually in
that dead zone, right, which is so so what is the dead zone? The dead
zone is a is water column, right? Um, but like first of all, we would
expect the base to be seen on both sides. I think that make sense. Yeah,
we would expect the base of it to be seen on both sides.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** I mean, the idea that this thing is just standing
straight vertically up is possible, but shocking to me. Also, I would
have expected to see it in multiple passes, maybe, right?

### 00:42:30

**Geoff Horowitz:** Um, I don\'t know. There\'s just something going on
here that doesn\'t feel doesn\'t feel like it\'s passing the smell test,
you know? But maybe it is. Maybe it is.

**Sachin Pandey:** Okay.

**Geoff Horowitz:** All right. So, so we talked about a few things.
Project, what what were you suggesting were the specific next steps?

**Pratyaksh Singh:** Uh I think I think there are few more things right

**Geoff Horowitz:** Oh, go ahead.

**Pratyaksh Singh:** session can we just quickly go through them so like
don\'t go deep

**Sachin Pandey:** Yeah. Yes.

**Pratyaksh Singh:** into them just you know just outline everything so
that at least we can decide the next steps.

**Sachin Pandey:** Yeah. Next will be the like resolution like earlier
we are Yeah.

**Pratyaksh Singh:** Can I share the screen?

**Sachin Pandey:** I am sharing. Next we\'ll build the resolution like
we we were using the default resolution was 0.25

**Pratyaksh Singh:** Okay.

**Sachin Pandey:** m per pixel and uh like we can clearly increase the
data because when comparing to the open source data that we downloaded
the resolution were much higher even in the images like these the output
resolution were much higher.

### 00:43:47

**Sachin Pandey:** So we can go like more higher and one thing we
noticed is one in one file uh while increasing the resolution it was
creating these gaps. So likely reason will be like for some reason these
pings were corrupted and because of the bigger grid size in higher res
uh like lower resolution it was filled up which is

**Geoff Horowitz:** Is this this is open source that you\'re

**Sachin Pandey:** good. No,

**Geoff Horowitz:** showing?

**Sachin Pandey:** this is the uh HTF conversion for the Navy data.

**Geoff Horowitz:** Oh for the existing data sets.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Okay.

**Pratyaksh Singh:** Uh so Jeff I think we need to know with them like
uh you know at what resolution do they operate because this is something

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** Ah.

**Sachin Pandey:** Like I found this in their PPT like they highlighted
mainly like high resolution SS 5

**Pratyaksh Singh:** Oh,

**Sachin Pandey:** cm. So we can get like at go to 0.05 and like by like
when I exported on max resolution it was something around 0.018 for a
file.

**Geoff Horowitz:** Well, it\'s not a big deal to ask.

### 00:44:59

**Sachin Pandey:** So

**Pratyaksh Singh:** I think I think we should because the reason is uh
Jeff with if you go high

**Geoff Horowitz:** Um,

**Pratyaksh Singh:** resolution so uh what I mean by high resol sorry
low resolution so let\'s say 0.2 or 0.25 what will happen is that it
will smooth out the image right so uh it\'s similar to saying to telling
me that is that you know as long as the resolution is below 0.25 25 our
model will work right but the capacity of our model will be uh will be
weak because you know it is it it is giving

**Geoff Horowitz:** Yeah.

**Pratyaksh Singh:** up on uh on you know on some some textures on you
know it is smoothing things out right now when you go to lower now when
you go to

**Geoff Horowitz:** Yeah.

**Pratyaksh Singh:** lower sorry when you go to higher resolution let\'s
say one pixel is like 5 cm or one pixel is 10 cm so what happens is that
your model won\'t work uh when your data is sparse right so for example
it\'s in these cases these can be

**Geoff Horowitz:** right?

**Pratyaksh Singh:** an anomaly cases where you know we get these
straight lines and all these things but uh the image will be much higher
resolution where we can see the texture a lot more so maybe we can do a
hyperparameter search to get the best model but I think you know
confirming with them at what

### 00:46:22

**Pratyaksh Singh:** resolution do they operate will be a better option

**Geoff Horowitz:** I I don\'t think it\'s a problem.

**Pratyaksh Singh:** maybe.

**Geoff Horowitz:** Uh but we should, you know, we should get all of our
questions together. I\'d rather ask them together than uh than one.

**Pratyaksh Singh:** Yeah. Yeah. Yeah.

**Geoff Horowitz:** But but yes,

**Pratyaksh Singh:** Makes sense.

**Geoff Horowitz:** I I agree with you, Patrick. Hey, you know, I I\'m I
mean I Sorry.

**Pratyaksh Singh:** That\'s it.

**Geoff Horowitz:** Go ahead.

**Pratyaksh Singh:** Uh uh Jeff,

**Sachin Pandey:** Yeah.

**Pratyaksh Singh:** do you have to

**Geoff Horowitz:** No, no, no, no, no, no.

**Pratyaksh Singh:** run?

**Geoff Horowitz:** I was going to say I can imagine, you know, they
have a target resolution, but um just because of, you know, they\'re
working in water, right?

**Sachin Pandey:** Okay.

**Geoff Horowitz:** So there\'s no consistency. So they\'re probably
working at a constant frequency, but the resolution might eb and flow.
That would be my guess. I don\'t know that for sure. Um,

**Pratyaksh Singh:** got it.

**Geoff Horowitz:** do you think that\'s going to affect anything?

### 00:47:18

**Pratyaksh Singh:** Uh,

**Geoff Horowitz:** You see, you see what I\'m saying? Like the
resolution will change if they\'re in shallower water or deeper water,

**Pratyaksh Singh:** I see what is in

**Geoff Horowitz:** you know?

**Pratyaksh Singh:** I I get it. I get it. And that\'s why, you know,
when we when we work on low resolution, it doesn\'t matter to us, but we
lose on texture.

**Geoff Horowitz:** Uhhuh.

**Pratyaksh Singh:** So, it might be better better to confirm with them
that you know uh

**Geoff Horowitz:** Uhhuh.

**Pratyaksh Singh:** what do you guys use for manual labeling,

**Geoff Horowitz:** Yeah.

**Pratyaksh Singh:** right?

**Geoff Horowitz:** Yes. Not a problem at all. Just

**Pratyaksh Singh:** And so I think just you know

**Geoff Horowitz:** Yeah.

**Pratyaksh Singh:** uh just because I think there are a lot more things
I I will suggest just

**Sachin Pandey:** Yeah, this is like almost

**Pratyaksh Singh:** uh go through those first and then we can dig
deeper uh dig deeper on individual things.

**Sachin Pandey:** all the things are uh done.

**Pratyaksh Singh:** Mhm.

**Sachin Pandey:** So like about this data set it also contains low
annotation unit uh I found like in the in the PDF they was present in
the folder they like they have marked some not marked like they have
highlighted the areas well what are the objects they find in the data
like wires or like some ship kind of structure.

### 00:48:39

**Sachin Pandey:** So uh we have to like allotate this data

**Pratyaksh Singh:** So Jeff are they what are the classes are they
interested in for this

**Sachin Pandey:** ourselves.

**Pratyaksh Singh:** milestone?

**Geoff Horowitz:** contact and non-cont

**Pratyaksh Singh:** What is the definition of contact?

**Geoff Horowitz:** um primarily it\'s minds primarily it\'s minds

**Pratyaksh Singh:** Uh-huh. Uh-huh.

**Geoff Horowitz:** but yeah I mean it\'s it it is following up even on
the the stuff that we did in the last in the last data set. It\'s
basically anything that\'s humanmade versus non-humanade.

**Pratyaksh Singh:** Okay. So pipeline and all these things they need to
be included as

**Geoff Horowitz:** Does that make sense? Yeah. I mean,

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** context.

**Geoff Horowitz:** so anything that we did in the last data set should
be contact and then in the new data set, as far as I know, it\'s only
UXOs that are added. That makes

**Pratyaksh Singh:** Sachin can you can you can you open your

**Geoff Horowitz:** sense.

**Pratyaksh Singh:** browser?

**Sachin Pandey:** Yeah.

**Pratyaksh Singh:** So,

**Sachin Pandey:** So uh just one more thing like even in the images
they shared in the

### 00:49:46

**Pratyaksh Singh:** uh,

**Sachin Pandey:** PPT like you see like this region mostly will be the
AXO and they

**Geoff Horowitz:** Mhm.

**Sachin Pandey:** only detected it with the MAC data like this
fluctuation because it is

**Geoff Horowitz:** This this is actually a concern.

**Sachin Pandey:** not rel showing anything in the FC. Uh, HDF.

**Geoff Horowitz:** and I\'ve discussed this with with Hemant at length
that I think we\'re going to need the MAG data in order to get good
detections. Um,

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** so that that won\'t surprise me,

**Sachin Pandey:** And

**Geoff Horowitz:** but let\'s let\'s go through the process. Let\'s
confirm

**Sachin Pandey:** yeah, other thing was like uh they have these reports
with some images attached. like these ones and uh you see

**Geoff Horowitz:** Mhm.

**Sachin Pandey:** these dots. This is like side scan image. This is the
this is not clear but this is the

**Geoff Horowitz:** I need to confirm, but I I think the dots are roll.

**Sachin Pandey:** elevation.

**Geoff Horowitz:** I think the dots are points that they\'ve rolled.
They\'re they\'re registering role, but I I don\'t know that for sure.

### 00:50:58

**Sachin Pandey:** Yeah, I I asked PBT he\'s telling like these are the
point of region where they find the magnetic fluctuations in the data
and they couldn\'t like point out the exact location.

**Geoff Horowitz:** Okay, that might be the case, too.

**Sachin Pandey:** So they have just marked it in the corner and it was
uh

**Geoff Horowitz:** Okay.

**Sachin Pandey:** uh it was like relatable to this line. This is also
the like the range of the magnetic field. So like in most of them it\'s
not obvious because almost the line is smooth but in some like you can
see a little bit fluctuation here but like we don\'t know like how much
fluctuation they are considering the like marker and like because it\'s
like fluctuation is continuing till here but they\'ve only marked like
these two reasons.

**Geoff Horowitz:** Uh we need to so this is we need to talk with
Bridget about how they are using the mag data. That\'s an open item
between us and Bridget,

**Sachin Pandey:** Okay.

**Geoff Horowitz:** us as a group. Um

**Sachin Pandey:** Yeah. Like we should also confirm whether it\'s uh
the mag like magnetic marker or

### 00:52:05

**Geoff Horowitz:** so

**Sachin Pandey:** something.

**Geoff Horowitz:** yeah yeah understood. Um okay what else we got?

**Sachin Pandey:** I think that\'s

**Pratyaksh Singh:** Uh so Jeff one more thing is that if you\'ll see
the background for port of

**Sachin Pandey:** all

**Pratyaksh Singh:** iceberg is that pronounced like that.

**Geoff Horowitz:** Sergeant, can you open it up?

**Sachin Pandey:** method.

**Pratyaksh Singh:** So yeah this one.

**Geoff Horowitz:** This is this is from so this specifically they

**Sachin Pandey:** This

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** gave us this data set for exactly this reason which
is this port they dredge the

**Sachin Pandey:** one.

**Geoff Horowitz:** port often and so this is the result of like I I
don\'t actually know exactly what kind of machinery they use but
whatever machinery they use leaves these like lines and bedrock wanted
to make sure that these types of backgrounds we do not identify as, you
know, positives, that they\'re not false positives. They want they want
us to learn that these should be

**Pratyaksh Singh:** Understood.

**Geoff Horowitz:** background.

**Pratyaksh Singh:** Understood. Uh so one more thing my question is
that till now they have shared us three kind of backgrounds right.

### 00:53:35

**Pratyaksh Singh:** One is something like this and then another one was
uh in the end can open the and and

**Geoff Horowitz:** Mhm.

**Pratyaksh Singh:** data.

**Geoff Horowitz:** into

**Sachin Pandey:** What is

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** Yeah.

**Pratyaksh Singh:** So one is this the BW1 which is kind of very smooth
right it is similar to

**Sachin Pandey:** this?

**Pratyaksh Singh:** what we saw what we were working with the previous
time and then another one is this and

**Geoff Horowitz:** Uh-huh.

**Pratyaksh Singh:** straighta right uh here it is much more noisier

**Geoff Horowitz:** This Yeah. So this this is according to Bridget
that\'s a function of roll

**Pratyaksh Singh:** right

**Geoff Horowitz:** the roll.

**Pratyaksh Singh:** that\'s a function

**Geoff Horowitz:** So the um the the what\'s it called?

**Pratyaksh Singh:** Oops.

**Geoff Horowitz:** The submersible was um in the water it was rolling
back and forth. Um you hear what I\'m saying? I\'m saying roll. Uh yeah.

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** So it was rolling back and forth. And so the result
was that you know it was creating these um I don\'t even have the right
word for it like these areas of compression and expansion um that was
generating these these artifacts that we see in the background and this
is a known issue.

### 00:54:49

**Geoff Horowitz:** So they said they said that when they tried to give
us to our last model um the last model identified a lot of these areas
of role as contacts. And so they wanted us same thing they wanted to
they wanted us to be able to learn that that\'s background

**Pratyaksh Singh:** Mhm.

**Sachin Pandey:** Perfect.

**Geoff Horowitz:** and not context.

**Pratyaksh Singh:** Understood. So, uh that makes sense. So what I want
to know is that are there any other kind of backgrounds or will this be
the reason that we would work on

**Geoff Horowitz:** these are the ones that they gave us.

**Sachin Pandey:** Quick

**Geoff Horowitz:** Uh she\'s familiar.

**Pratyaksh Singh:** okay?

**Geoff Horowitz:** She she knows that we\'re not going to be able to
generalize outside of the training set. So if there are other
backgrounds that she needs, she know she she knows we won\'t perform on
them.

**Pratyaksh Singh:** Mhm.

**Sachin Pandey:** one.

**Geoff Horowitz:** I\'m happy to ask if there are more backgrounds that
they expect and we can add it into the training data, but I also don\'t
I don\'t think we need to scope creep.

### 00:55:46

**Geoff Horowitz:** You know,

**Pratyaksh Singh:** Understood.

**Geoff Horowitz:** if these are the ones if these are the ones she
asked for,

**Pratyaksh Singh:** Makes sense.

**Geoff Horowitz:** then these are the ones we\'ll

**Pratyaksh Singh:** Understood. Makes sense. That makes sense. Uh,

**Geoff Horowitz:** do.

**Pratyaksh Singh:** another thing is that for contacts, right? Uh, for
contacts, Sachen, can you can you go to that previous one, the end state
only? Yeah. So, see, I still don\'t know like what the contact means and
how do they look. What I\'m basically seeing here is that uh just leave
it sin. I think I think this is good. So is it is this how the contact
look like where you know there is this dark background there is this
dark patch and there is light patches around it or you know is it
something similar to what we decided previously where there is if there
is any abnormality we are going to detect it. So that would be in the
lower region if you see the white kind of pixel that is kind of an
abnormality.

### 00:56:51

**Pratyaksh Singh:** Uh okay so in this image if you can just hold on in
this image the white pixel there is

**Geoff Horowitz:** Mhm.

**Pratyaksh Singh:** that contact or are are the contacts always when
you have kind of a dark pixel and then uh light pixel surrounding.

**Geoff Horowitz:** Um, we can confirm with Bridget,

**Pratyaksh Singh:** Thank

**Geoff Horowitz:** but in I I think the answer is is the latter.

**Pratyaksh Singh:** you.

**Geoff Horowitz:** Um, meaning the the data that she gave us has shape
files for or rather locations or whatever they are for the contacts. And
so she marked the the one on the bottom as a contact and the one on the
top not as a contact. Um, so therefore

**Pratyaksh Singh:** So then are we using are we using their shape files
or is this uh from our

**Geoff Horowitz:** I

**Pratyaksh Singh:** labelers labeled by our labelers?

**Sachin Pandey:** Uh this is by our

**Pratyaksh Singh:** Okay.

**Sachin Pandey:** class.

**Geoff Horowitz:** so we should confirm

**Pratyaksh Singh:** Uh can we do one thing? Yeah. Can we do one thing
session? Can we look at the way that they are annotating with their
shape files and then see what they are classifying as contacts?

### 00:58:02

**Pratyaksh Singh:** Right? What I can do is we can have maybe two
classes. one is you know uh when we get our labels to it one would
because if you\'ll

**Sachin Pandey:** Speed

**Pratyaksh Singh:** open the BW data set that we had previously right

**Geoff Horowitz:** We we did project. We did have those diffs from
them.

**Sachin Pandey:** up.

**Pratyaksh Singh:** uh-huh

**Geoff Horowitz:** You you you recall that. Um

**Pratyaksh Singh:** yeah these

**Geoff Horowitz:** yeah.

**Pratyaksh Singh:** are fine I I think in VW the final uh not only
faint fuel just scroll through it I think you will find it a lot because
we labeled a lot of them right so for example it\'s in this images we
labeled a lot of these a lot of these things right which we thought as
context basics Yeah, I I think you\'re right. We can confirm with the
diff. I think I uploaded the dip somewhere.

**Geoff Horowitz:** we can confirm with the diff. I I would I would
suggest

**Pratyaksh Singh:** Huh.

**Geoff Horowitz:** pract in, you know,

**Pratyaksh Singh:** Mhm.

### 00:59:21

**Geoff Horowitz:** not just use two, let\'s use 10 classes, right? like
let\'s be discreet in the labeling so that we can do it once and not
have to do it many

**Pratyaksh Singh:** Mhm. Mhm.

**Geoff Horowitz:** times.

**Pratyaksh Singh:** Understood.

**Geoff Horowitz:** Um then and then what you know it\'s it wouldn\'t be
unreasonable for forget unreasonable. I think Bedrock would actually
like it if we sent them our labels and said look these are the things
that we\'re going for. You know even if we broke it up these these are
the things that we\'re not sure about. We anticipate training on them
but you know we\'d like feedback on them. Um I mean we can split those
up by classes.

**Pratyaksh Singh:** Mhm. Uh-huh.

**Geoff Horowitz:** Um or or to say like like you mentioned, you know,
these are areas of just kind of light discoloration, which is a
different class than whatever it is, dark with with lighter color around
it. Um I mean, that\'s that\'s my recommendation is let\'s let\'s let
the labelers take their time.

**Pratyaksh Singh:** Mhm.

### 01:00:22

**Geoff Horowitz:** um be very kind of discreet um in in the classes
that we use.

**Pratyaksh Singh:** Mhm.

**Geoff Horowitz:** Um and then we can always get feedback from

**Pratyaksh Singh:** Got it. I think I think this is uh I think this
might be so what I\'m thinking is

**Geoff Horowitz:** Edrock.

**Pratyaksh Singh:** that how about we instead of training on this one
or two class, how about we train on train the model to predict let\'s
say seven or eight classes.

**Geoff Horowitz:** Yes,

**Pratyaksh Singh:** Seven or eight different classes,

**Geoff Horowitz:** I agree.

**Pratyaksh Singh:** right? And then they can basically choose whichever
they like.

**Geoff Horowitz:** I I completely agree.

**Pratyaksh Singh:** Our model will predict eight classes.

**Geoff Horowitz:** I completely agree with you.

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** I think that\'s a great approach.

**Pratyaksh Singh:** All right. Okay. Sachin,

**Geoff Horowitz:** I mean project we even we even started with that
right at the end of last the last one.

**Pratyaksh Singh:** do you have anything more to share? Yeah.

**Geoff Horowitz:** We were going to do like sand sand ripples as a
different as a different class, right?

### 01:01:19

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** Yeah. So, yeah,

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** I think that

**Pratyaksh Singh:** Yeah. I think we need to add a lot more.

**Geoff Horowitz:** aligns.

**Pratyaksh Singh:** Right. So for example what they have classified as
contacts we need to understand what they mean by that and then those
will be in one classes and then there will be some contacts which we

**Geoff Horowitz:** Mhm.

**Pratyaksh Singh:** think are correct right so for example let\'s say
the slide discoloration and all these things we can put those in one
another class and

**Geoff Horowitz:** Mhm.

**Pratyaksh Singh:** then similarly like different things we can put in
different classes and then And then once that is done what we can do is
we can basically train our model to do all these things. And my plan is
that even if uh the distribution shifts the model might predict one of
these uh random classes which can be like tape or all those things right
linear anything anything other than the class that is important. So I
think I think we are on the same page that you know let\'s give labeler
a bunch of classes that they have to label on and then we can decide
which one to

### 01:02:26

**Geoff Horowitz:** Yeah. Yeah.

**Pratyaksh Singh:** use.

**Geoff Horowitz:** Okay. Um and again, Pratak, you know, if if this if
this results in going slower, um we can always bring in the other two
labelers as well.

**Pratyaksh Singh:** I think it will take them sim similar time. It
should take them similar time.

**Geoff Horowitz:** Okay,

**Pratyaksh Singh:** We just have to monitor them. I think they work
pretty fast. They just don\'t tell us.

**Geoff Horowitz:** good.

**Pratyaksh Singh:** Maybe Yeah.

**Geoff Horowitz:** Okay.

**Pratyaksh Singh:** Uh I think

**Sachin Pandey:** like they are doing 100 image per person.

**Pratyaksh Singh:** Huh.

**Sachin Pandey:** uh like today like yesterday also they yesterday they
did around 130 files in total and today they did around 200 files in
total which is just a keyway for photo map data photo map brown which is
almost

**Pratyaksh Singh:** Uhhuh. Are they doing are they doing correctly?

**Sachin Pandey:** perfect.

**Pratyaksh Singh:** I I remember you mentioned some files where they
had missed the correct

**Sachin Pandey:** Yeah,

**Pratyaksh Singh:** one.

**Sachin Pandey:** like they are like pickpicking the small details and
missing the major mistakes.

### 01:03:38

**Pratyaksh Singh:** Uh

**Geoff Horowitz:** weird.

**Sachin Pandey:** So like I checked few of the file like mostly those
bigger mistakes were because of the solar panels and solar panel were
classified as ground

**Pratyaksh Singh:** Uh-huh.

**Sachin Pandey:** and like all the minor mistakes like they aren\'t
even a mistake.

**Pratyaksh Singh:** Uh-huh.

**Sachin Pandey:** Okay, just the surface is little rough. So mostly
those are the effects of the data.

**Pratyaksh Singh:** You need to make a doc similar to what uh Sid made,
right? where you know add add in a lot of things make things clear for
them

**Geoff Horowitz:** Yeah.

**Sachin Pandey:** Yeah, but like this this QI is mainly for like they
have to find the new issues in the data because we

**Pratyaksh Singh:** right

**Sachin Pandey:** haven\'t gone through the data once. If they have to
like uh look through the data and mark like all the issues and
categorize them

**Geoff Horowitz:** Heat.

**Sachin Pandey:** like based on their

**Pratyaksh Singh:** which I think they will strugg they struggle with
right I know I know like

**Sachin Pandey:** understanding

**Pratyaksh Singh:** you We like freedom but I I think they struggle
with it because maybe they haven\'t seen that much of point cloud data
to understand that this might be solar panel or or those things right

### 01:04:51

**Sachin Pandey:** like Even I don\'t understand like once I take the
cross-section it was like clearly

**Pratyaksh Singh:** so so just teach them that right you know take the
cross-section if cross-section it suddenly

**Sachin Pandey:** visible.

**Pratyaksh Singh:** increases if it doesn\'t make sense then those kind
of thing let\'s you know over the weekend Let\'s design a doc at least
for ground queuing because with tetra techch things are fresh and then
let\'s write down a doc so that one we can share with them or with other
labels too. All right.

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** uh for bedrock also such in you know whatever we
discussed if you had it in a doc somewhere or if you can just put it in
a detailed

**Geoff Horowitz:** Oops.

**Pratyaksh Singh:** talk along with the questions that we need to ask
them or things that we are confused with that would be

**Sachin Pandey:** Oops.

**Pratyaksh Singh:** awesome because I think that will also allow human
to catch up and then you know this easier thing if it\'s clean we can
refer back to it instead of going through the data again and again.

### 01:05:54

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** Does it make sense? I can I can help you with

**Sachin Pandey:** Yeah, I will. Yeah, I will organize the data and like
I will get the like mainly the test task from

**Pratyaksh Singh:** it.

**Sachin Pandey:** the transcript.

**Pratyaksh Singh:** Okay. And for this talk like dump everything. I
will say do not miss anything. Don\'t think anything is unimportant or
stuff. Just dump everything. And then if you want to have a highle
summary, add a summary. But I wanted to dump everything because you know
in future if we if let\'s say miss something I don\'t want us to go
through the data again. It will be just like we go through this EDA doc
and then we have things noted down here. Does it make sense?

**Sachin Pandey:** Yeah. Thank

**Pratyaksh Singh:** So note everything every detail right that you know
in uh black and white these

**Sachin Pandey:** you.

**Pratyaksh Singh:** things are not visible when we visualize in the
open source these things are visible.

### 01:06:47

**Pratyaksh Singh:** So what was the difference? What was chosen? What
are the open questions? Did we get answers to answer to them? Do we need
to ask it with Bridget and everything? Right. Just dump everything and
then I think we can we can form questions that we can share with
Bridget. Do you think that\'s a good idea,

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** Jeff?

**Geoff Horowitz:** Yes, I

**Pratyaksh Singh:** All right. And then such let\'s come up with
classes for uh

**Geoff Horowitz:** agree.

**Pratyaksh Singh:** for labelers so that we can give them to label this
point cloud and start with training the model

**Sachin Pandey:** Yeah. So yeah, for

**Pratyaksh Singh:** right yeah for bedrock uh because I think from next
week we

**Sachin Pandey:** better

**Pratyaksh Singh:** want uh bedrock labeling to take priority over

**Geoff Horowitz:** Yeah.

**Pratyaksh Singh:** Okay. Uh you now you\'re primarily working on
bedrock, right? Nothing from tetra tech or anything else.

**Sachin Pandey:** Yeah, only on

**Pratyaksh Singh:** All right. Yes.

**Sachin Pandey:** better.

### 01:07:56

**Pratyaksh Singh:** Uh ratul you are also working with Sachin on
bedrock only or anything else?

**Ratul Shashank:** Yes, at the moment I am also reviewing the
annotations done for Boommy and uh I was also working on the

**Pratyaksh Singh:** Mhm.

**Ratul Shashank:** S7K to last pipeline. It is finished. just need some
uh data to back for validation. Otherwise, only these two

**Pratyaksh Singh:** Mhm. Okay. Okay.

**Sachin Pandey:** uh like about the Jeff do you know where we are
putting the 7K files like I tried searching in the SFTV but I didn\'t
find

**Geoff Horowitz:** Yeah. Um,

**Sachin Pandey:** Okay.

**Geoff Horowitz:** Sashan, do me a favor. Send me a message. Um
actually just send me a message on the IICA channel um and I will find
I\'ll I\'ll respond so that everybody can see it.

**Sachin Pandey:** Okay.

**Geoff Horowitz:** Okay. Uh I I\'ll do that uh within the next hour or

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** so.

**Pratyaksh Singh:** All right. Uh, let me know. Go ahead,

**Ratul Shashank:** Yes,

**Pratyaksh Singh:** sir.

**Ratul Shashank:** X.

**Pratyaksh Singh:** Yeah, I was I was just saying ratul if we have some
time uh we can work on that training pipeline the unit based training
pipeline for a unit based training pipeline for uh for bedro you know uh
we can do it properly like you know raise VR review and work together.
Also, So, let me know if you\'re free for

**Ratul Shashank:** Yes.

**Pratyaksh Singh:** that.

**Ratul Shashank:** Then I will coordinate with you and uh we can do
that.

**Pratyaksh Singh:** Okay, makes sense. Sounds good.

**Ratul Shashank:** Okay.

**Pratyaksh Singh:** All

**Geoff Horowitz:** Okay, great. Thank you guys. Uh,

**Pratyaksh Singh:** right.

**Geoff Horowitz:** have a good weekend. Well, I\'m sure I\'ll talk to
you, but have a good weekend anyway. Uh, we\'ll talk on Monday, if not
before.

**Pratyaksh Singh:** All right.

**Sachin Pandey:** Okay,

**Geoff Horowitz:** Hi everyone.

**Pratyaksh Singh:** All

**Sachin Pandey:** come back.

**Pratyaksh Singh:** right.

### Transcription ended after 01:12:55

*This editable transcript was computer generated and might contain
errors. People can also change the text after it was created.*
