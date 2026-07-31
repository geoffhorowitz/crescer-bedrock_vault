Jun 24, 2026

## Iris Sync

Invited [[Sachin Pandey]{.underline}](mailto:sachin@crescer.ai)
[[Pratyaksh Singh]{.underline}](mailto:pratyaksh@crescer.ai) [[Niveta
Iyer]{.underline}](mailto:niveta@crescer.ai) [[Hemanth
Sarabu]{.underline}](mailto:hemanth@crescer.ai) [[Geoff
Horowitz]{.underline}](mailto:geoff@crescer.ai) [[Siddharth
Soni]{.underline}](mailto:siddharth@crescer.ai) [[Ratul
Shashank]{.underline}](mailto:ratul@crescer.ai)

Attachments [[Iris
Sync]{.underline}](https://calendar.google.com/calendar/event?eid=NnNzMHVxNzk3MmJqZGVwNXFoN2J1Mjd1OTdfMjAyNjA2MjRUMTYzMDAwWiBnZW9mZkBjcmVzY2VyLmFp)

Meeting records
[[Transcript]{.underline}](https://docs.google.com/document/d/11ptxH7K2hWJAlnUGOJMYJQaKuZq2t4SjvaCBnnfT_rE/edit?usp=drive_web&tab=t.2f4a6cnq58hb)

### Summary

Meeting focused on project prioritization, data artifact
troubleshooting, and refining technical workflows for image processing.\
\
**Prioritization and Data Gaps**\
Bedrock-related tasks were prioritized over other projects. Technical
analysis confirmed that observed data gaps resulted from
hardware-related ping loss rather than software processing errors.\
\
**Technical Analysis Strategies**\
The team committed to geo-referenced raster processing over alternative
methods to maintain data integrity. They decided to standardize image
enhancement settings, including AGC and TV adjustments, to improve
clarity.\
\
**Documentation and Future Analysis**\
The team resolved to utilize AI models to document codebase
functionality and enhance image processing algorithms. They plan to
investigate persistent discrepancies in waterfall intensity and depth
reporting.

### Decisions

Aligned

-   **Bedrock project priority over S7K** The team established that the
    > Bedrock project takes priority over the S7K project.

-   **Waterfall enhancement setting** The waterfall enhancement
    > configuration is set to default off.

We\'ve **updated the Decisions section** using your feedback.

Let us know what you think:
[[Helpful]{.underline}](https://google.qualtrics.com/jfe/form/SV_5p6FWBVWvynleNU?isGoogler=no&isHelpful=yes)
or [[Not
Helpful]{.underline}](https://google.qualtrics.com/jfe/form/SV_5p6FWBVWvynleNU?isGoogler=no&isHelpful=no)

### Next steps

-   \[Ratul Shashank\] Conduct Experiments: Perform additional
    > experiments regarding the S7K data.

    > \[Sachin Pandey\] Locate Script: Find the notebook or script used
    > to generate the analysis report.

    > \[Ratul Shashank\] Coordinate Data Search: Work with Sachin to
    > identify the specific data set showing the anomaly.

    > \[Geoff Horowitz\] Inquire Data Availability: Ask Bridget about
    > the availability of high resolution low pass data.

    > \[Sachin Pandey, Ratul Shashank\] Comment Open Items: Provide
    > updates and comments on the project open items.

    > \[Ratul Shashank\] Report Data Loss: Create a report estimating
    > the impact of missing pings on data quality.

    > \[Ratul Shashank\] Verify Data Gaps: Check the low pass XTF files
    > for the presence of data gaps.

    > \[Ratul Shashank\] Review Reports: Read the reports folder
    > documents to better understand data resolution.

    > \[The group\] Clarify Data Gaps: Determine if identified data gaps
    > are actual collection errors or related to other factors.

    > \[The group\] Check Low Pass Gaps: Verify if identified data gaps
    > are present within the low pass filter results.

    > \[Sachin Pandey\] Analyze Code: Examine code functions to define
    > their purpose, required input data, and expected output.

    > \[Sachin Pandey\] Verify Context File: Evaluate whether the
    > current context file effectively maps out the full scope of the
    > code operations.

    > \[The group\] Upgrade Construct Guide: Incorporate the computer
    > vision image processing algorithm into the existing main construct
    > guide.

### Details

-   **Project Prioritization**: Geoff Horowitz instructed Ratul Shashank
    > to prioritize Bedrock-related work over the S7K tasks. Ratul
    > Shashank confirmed this priority, noting that their current focus
    > is on mapping data and identifying features that are not readily
    > apparent within the region ([[00:00:23]{.underline}](#section)).

-   **Analysis of Threshold Data**: The team discussed a prior analysis
    > by Sachin Pandey regarding threshold values, with uncertainty
    > regarding whether the plotted units of 5,000 were in nanoteslas or
    > microteslas ([[00:03:24]{.underline}](#section-1)). Ratul Shashank
    > pointed out a potential unit mismatch, noting that their own
    > analysis yielded a value of -500 nanoteslas
    > ([[00:05:14]{.underline}](#section-2)). The team agreed to
    > coordinate to verify the original data set and the corresponding
    > notebook to resolve the discrepancy
    > ([[00:06:29]{.underline}](#section-3)). Geoff Horowitz emphasized
    > the necessity of using Bedrock\'s actual output as a baseline for
    > analysis, considering variables such as sensor distance, object
    > size, and material ([[00:05:14]{.underline}](#section-2)).

-   **Data Labeling Status**: Geoff Horowitz inquired about the status
    > of data labeling for Iris and Bedrock. Sachin Pandey reported that
    > while they are currently processing old datasets for quality
    > assurance, they do not have sufficient features available for the
    > remaining two datasets to assign to the two available labelers
    > ([[00:08:07]{.underline}](#section-4)).

-   **Investigation of Data Gaps**: Ratul Shashank investigated the
    > \"black strip\" artifacts found in files processed by Sachin
    > Pandey and confirmed that the gaps exist within the raw XTF files
    > due to missing pings, rather than an error in the processing
    > software ([[00:09:41]{.underline}](#section-5)). Ratul Shashank
    > observed that timestamps and pings in specific sections failed to
    > correlate, likely due to a hardware glitch
    > ([[00:11:23]{.underline}](#section-6)). Hemanth Sarabu noted that
    > a 500 to 700 millisecond gap is estimated to represent only a few
    > centimeters on the ground, suggesting that the data loss is not
    > critical ([[00:15:13]{.underline}](#section-8)).

-   **Open-Source Tool Processing**: The team discussed how open-source
    > tools handle data compared to their own methods. They noted that
    > unlike their geo-referenced raster approach, open-source tools
    > typically stack pings on the y-axis, which hides data gaps
    > ([[00:18:28]{.underline}](#section-10)). The team concluded that
    > they prefer maintaining geo-referenced data over adopting the
    > stacking method used by open-source tools
    > ([[00:21:44]{.underline}](#section-12)).

-   **Defining Data Resolution and Quality**: The team reviewed the
    > terminology and quality of the datasets, specifically
    > distinguishing between \"base\" XTF files and those labeled \"low
    > pass,\" which appeared to contain cleaner imagery
    > ([[00:23:26]{.underline}](#section-13))
    > ([[00:26:25]{.underline}](#section-15)). Sachin Pandey and Ratul
    > Shashank reviewed reports and visual slides to clarify these
    > distinctions ([[00:24:44]{.underline}](#section-14)). Although the
    > team noted that \"low pass\" images provided clearer results,
    > ambiguity remained regarding the precise definition of the term
    > and its relationship to sensor altitude or frequency
    > ([[00:23:26]{.underline}](#section-13)).

-   **Technical Troubleshooting and Next Steps**: Following the
    > departure of Geoff Horowitz, Sachin Pandey and Ratul Shashank
    > continued to discuss technical parameters, including image
    > enhancement levels of 0.1 and 0.25, sensor frequencies, and
    > specific file naming conventions
    > ([[00:27:54]{.underline}](#section-16)). They reviewed various
    > files and scripts to determine how to address resolution and noise
    > issues ([[00:41:16]{.underline}](#section-19)). The team
    > prioritized utilizing higher-resolution, high-frequency images and
    > agreed to document their findings in the report to ensure clarity
    > moving forward ([[00:46:07]{.underline}](#section-20)).

-   **Slide and Image Enhancement Troubleshooting**: Sachin Pandey and
    > Ratul Shashank discussed issues with slide presentations,
    > specifically referencing slides two, six, eight, and nine. To
    > address resolution and clarity concerns, they explored \"enhanced
    > waterfall\" and \"enhanced data clean\" settings, implementing
    > specific adjustments such as an \"Output minus 0.5\" setting and
    > \"AGC plus TV enhancement\" to reduce noise
    > ([[00:57:44]{.underline}](#section-22)). The team decided to
    > compare the enhanced image against the original pass and generate
    > a PDF report to finalize the process
    > ([[01:04:45]{.underline}](#section-23)).

-   **Data Collection Gap Investigation**: The team debated whether the
    > gaps observed in their data are actual collection failures or
    > issues stemming from resolution. Ratul Shashank argued that the
    > gaps are real and can be identified by examining how pings are
    > staged. Sachin Pandey and Ratul Shashank agreed that this remains
    > an open question, and they need to clarify exactly what
    > information to request to determine if these are indeed gaps in
    > data collection ([[01:10:33]{.underline}](#section-24)).

-   **Low Pass Filter Verification and File Processing**: The team
    > focused on whether data gaps appear in the low pass and reviewed
    > file management, specifically mentioning \"extended XTF\" and
    > \"UTM\" data ([[01:15:22]{.underline}](#section-25)). Ratul
    > Shashank provided a definition of a low pass filter, describing it
    > as an algorithm or device that allows signals with frequencies
    > below a specific cutoff threshold to pass while reducing higher
    > frequencies ([[01:20:57]{.underline}](#section-26)). They
    > confirmed that sensor data should be located in the DRN folder and
    > agreed to continue checking both low pass and high pass data
    > ([[01:15:22]{.underline}](#section-25)).

-   **Code Analysis and Context Documentation**: Ratul Shashank and
    > Sachin Pandey discussed using Gemini 3.5 models to conduct a
    > detailed analysis of their codebase
    > ([[01:20:57]{.underline}](#section-26)). The primary task is to
    > understand the purpose of each function, identify what data each
    > function expects and produces, and determine if the current
    > context file is sufficient to map out the operation of the code
    > ([[01:27:23]{.underline}](#section-27)). They agreed to
    > potentially upgrade the main guide to include computer vision
    > image processing algorithms to bridge the gap in their current
    > documentation ([[01:32:38]{.underline}](#section-28)).

-   **Waterfall Intensity and Depth Report Analysis**: The team reviewed
    > \"284\" altitude and direction data, checking for consistency in
    > \"CrossPass\" and high pass results. They observed that despite
    > using almost identical file names, there were discrepancies in
    > \"waterfall intensity\" and \"Zange depth report\" data. The
    > discussion concluded with the item remaining an open task to
    > investigate why specific data points are not visible and how the
    > system is processing Mac data in these reports
    > ([[01:36:49]{.underline}](#section-29)).

*You should review Gemini\'s notes to make sure they\'re accurate. [[Get
tips and learn how Gemini takes
notes]{.underline}](https://support.google.com/meet/answer/14754931)*

*How is the quality of **these specific notes?** [[Take a short
survey]{.underline}](https://google.qualtrics.com/jfe/form/SV_9vK3UZEaIQKKE7A?confid=Gf9d39vbM9mwe6VrQbISDxIUOAIIigIgABgECA&detailid=standard&screenshot=false)
to let us know your feedback, including how helpful the notes were for
your needs.*

📖 Transcript

Jun 24, 2026

## Iris Sync - Transcript

### 00:00:23

**Sachin Pandey:** Thank you. I think

**Ratul Shashank:** It\'s

**Geoff Horowitz:** Okay. Um, needed a few minutes. Uh, I guess let\'s
start. I have a hard stop in 30 minutes. Um, but let\'s start talking
about the S7K stuff and then we\'ll stop. Um, we\'ll stop after a few
minutes. Um,

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** Rul, you sent me a document. Oh, that\'s right,
Rachel. You were you you gave me an update yesterday. Uh, I\'m I\'m fine
with your plan. Do you you still you you still need some time there,
right?

**Ratul Shashank:** regarding the S7K stuff.

**Geoff Horowitz:** Yeah.

**Ratul Shashank:** Yeah, I need to I need I need to try some more

**Geoff Horowitz:** Okay.

**Ratul Shashank:** experiments.

**Geoff Horowitz:** All right. No problem. Um, I will say I think I
mentioned this to you already, but in terms of the priority stack,
Bedrock should take priority over the S7K stuff.

**Ratul Shashank:** Yeah.

**Geoff Horowitz:** Okay, good. All right.

**Ratul Shashank:** And sorry to cut you off but uh I would just sten
that and for bedrock I have been uh primarily working on the map data
and uh to be more specific finding a way to detect stuff in the region
that is not very apparent.

### 00:03:24

**Ratul Shashank:** So that is uh of my top priority.

**Geoff Horowitz:** So, Rul, I was looking through your that that other
report you shared. Um, I made a comment. I don\'t know if I don\'t know
if you were able to see it or not, but regarding the

**Ratul Shashank:** regarding threshold one

**Geoff Horowitz:** threshold,

**Ratul Shashank:** right.

**Geoff Horowitz:** so so this was an analysis that uh Sachin did a
while ago. Um and what we can see here is yes you know maybe this

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** is such what these units are are nanoteslas or these
units are microteslas

**Sachin Pandey:** They were in the New

**Geoff Horowitz:** nanoteslas 5,000 nanoteslas

**Sachin Pandey:** Testament.

**Geoff Horowitz:** Does that seems What was

**Ratul Shashank:** What was this data set?

**Geoff Horowitz:** it?

**Sachin Pandey:** This was the

**Ratul Shashank:** Such

**Geoff Horowitz:** Uh, sorry guys. Turn it on the

**Sachin Pandey:** VW need to catch but it was It is plotting the raw
data. The data itself

**Ratul Shashank:** Jack,

**Sachin Pandey:** was

**Ratul Shashank:** please.

**Geoff Horowitz:** Okay, I\'m back. Sorry about that.

### 00:05:14

**Geoff Horowitz:** Um, yeah, my did I cut into something?

**Sachin Pandey:** no need.

**Geoff Horowitz:** So, so the point here was um I you know I think that
we actually need to look at the underlying data or a tool and and see
you know what are these when they when bedrock sees a contact what sort
of values are they getting right and those

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** might be really low they might be really high I
don\'t know and I think we need to use that as a baseline because um
because there\'s so many variables here, right? It depends it depends on
the distance of the of the mag sensor to the to the object. It depends
on the size of the object. Those are the ones that come to me. But, you
know, probably the material of the object. Lots of different

**Ratul Shashank:** just to cross check but I think this value is in
microtesla because I was

**Geoff Horowitz:** things.

**Ratul Shashank:** looking at what I analyzed on and I have a similar
kind of annotation and uh it revealed to be 500 nanotesla.

### 00:06:29

**Ratul Shashank:** So I uh I\'m not sure but I think there is a unit
mismatch.

**Geoff Horowitz:** Sash, do you still have the notebook or the script
that you use to generate this?

**Sachin Pandey:** I need to check.

**Geoff Horowitz:** It is a good point, Sen. We should always have
units. We should always have um what\'s it called? like um access units
for for exactly this reason, right? This is what we keep talking about.
It\'s like we we come back to it a few months later and we have little
recollection about what exactly we did.

**Ratul Shashank:** I have shared a photo in the chat and the structure
is very similar. uh and in my analysis is it gained out around if that
exact region it gained out to be of - 500 nanotes it could be a
different region uh we I will coordinate to search in and find the exact
data set but there is a possibility

**Geoff Horowitz:** Okay. Okay. Um, I mean there\'s no I I think that\'s
a good idea. Also, the outcome here is that we need we need to get some
sort of baseline from what Bedrock

### 00:08:07

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** does. Okay. Um, so do you guys want to do you guys
want to go through Oh, Sashin, one other thing. Do we have any more data
that needs to be labeled either for Iris or for Bedrock?

**Sachin Pandey:** I go for I wish uh this is about uh the quality for
leave from Santos.

**Geoff Horowitz:** I\'m struggling to hear what you\'re saying.

**Sachin Pandey:** Uh this is about the Santos like he\'s taking a leave

**Geoff Horowitz:** Sentosh

**Sachin Pandey:** tomorrow.

**Geoff Horowitz:** is taking a leave. This is actually about the other
two labelers. Um, you know, we\'ve got two more.

**Sachin Pandey:** Okay.

**Geoff Horowitz:** I don\'t think they have anything to do.

**Sachin Pandey:** Okay. So, uh like we are currently like giving the
old data set for keyway. They are marking them in in Iris and in bedrock
they like today they are finished with BW and we have entx which they
can label but for other two data other two data set we don\'t have any
features which we can like ask them to label Thank you.

### 00:09:41

**Geoff Horowitz:** Okay. Uh let\'s get back to this discussion then. Um
yeah, let\'s get back to this. Okay. Uh so what are the updates from
yesterday\'s discussion that you guys have been working on?

**Ratul Shashank:** Yes. So the strip uh the black strip that was coming
in the file that Sachin was preparing it is confirmed that the gap was
uh it that the gap exist in the XTF file itself. So basically uh I ran a
time series where I check every ping uh and the time stamp uh connected
to that pin. Uh and in some areas there appears to be the pings pings
are not correlating with the time stamps and those areas. Uh they are
exactly where Tachin encountered those black lines. So it is a problem
with the data set or a section of the data set. Not all RN.

**Geoff Horowitz:** You said there\'s you said there\'s missing time
stamps or you said that the time stamps don\'t align with the

**Ratul Shashank:** No,

**Geoff Horowitz:** pings

**Ratul Shashank:** there are missing things uh in of in that particular
instance.

### 00:11:23

**Geoff Horowitz:** existing timestamps missing pings.

**Ratul Shashank:** Yes.

**Geoff Horowitz:** See

**Ratul Shashank:** So that that would be uh I cross check if this is
possible. So uh it appears out that it is possible like in in that
instance the sensor glitched out or for any n any number of elements
maybe the hardware is not of much of better quality but it is common for
XTF files to be moving uh things in some instances but improved. I will
also share a photo which is which which will help understand better this
problem.

**Geoff Horowitz:** So, you both seem pretty convinced that the um that
the data is what what am I looking at here?

**Ratul Shashank:** Uh so it\'s the vertical lines are basically uh the
difference in time between each subsequent ping. So the horizontal lines
is are the ping numbers uh and the vertical lines are the difference in
that time delta between subsequent pings. So I I just cross check if
this uh if the data the data of ping that we have it correlates with the
uh the time stamp that each ping has and it appears that in some time
stamps the ping uh the difference between the time stamps that the ping
registered is much larger.

### 00:13:54

**Ratul Shashank:** So I I basically just uh the legend says five times
median right so it\'s just taking the median of each time interval at
the ping registers subsequent ping registers and if any place is five
times more than the median then that position will not show us any data.

**Geoff Horowitz:** This doesn\'t actually line up though, does it?
Meaning, what do I mean by that? It doesn\'t line up. I mean, let\'s
let\'s just say for the sake of argument that, you know, this missing
gap aligns to this one. I don\'t know, this missing gap aligns to one of
these two. We would expect to see a third a third gap here.

**Ratul Shashank:** No, actually I I think we are looking at a different
water file. like this is the exact uh water polyus for the data set that
I calculated this thing uh analysis

**Geoff Horowitz:** I\'m not following you.

**Ratul Shashank:** so data set right we are looking at the

**Geoff Horowitz:** We\'re looking at a different Oh,

**Ratul Shashank:** different image I have shared a photo in

### 00:15:13

**Geoff Horowitz:** a different image.

**Ratul Shashank:** the chat of the exact uh XF file That has done both

**Geoff Horowitz:** Ah, okay. I

**Ratul Shashank:** analysis.

**Geoff Horowitz:** see. Okay, fine. So, so you both seem pretty
convinced that that the data is actually missing here um in certain

**Ratul Shashank:** in certain areas,

**Geoff Horowitz:** areas.

**Ratul Shashank:** Hey.

**Hemanth Sarabu:** How many I I think that that\'s fine. I I think
it\'s I\'m convinced that this is there\'s no data

**Geoff Horowitz:** Yeah, a data gap.

**Hemanth Sarabu:** here.

**Geoff Horowitz:** Yeah,

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** I agree.

**Ratul Shashank:** Okay.

**Hemanth Sarabu:** And it\'s also not like we\'re losing a lot, right,
because of

**Geoff Horowitz:** Um

**Ratul Shashank:** Uh so if we were to uh put an assumption uh

**Hemanth Sarabu:** it.

**Ratul Shashank:** so basically a 700 millisecond of data would be
around a few cm on ground but I will I will get a proper uh report on
how much we would lose per uh missing pin but that is a rough estimate.
like a few 500 700 milliseconds would amount about a few centimeters on
ground.

### 00:17:00

**Geoff Horowitz:** Um, Rul, I I have two follow-up questions here.
Sorry, Hammond, were you saying something?

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** I have two follow-up questions here. Let me add a
comment.

**Hemanth Sarabu:** Oh,

**Geoff Horowitz:** Uh, I\'m putting it here, but I think you\'ll
understand what the comment is. So two followups. Uh number one is uh
okay so fine we\'re convinced the data is missing in the underlying XTF.
So question one is um can we confirm that we\'re not seeing these data
gaps in the low pass XTFS? I expect that to be true, but it\'s a it\'s a
dummy check, right? And then number two is

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** um uh I lost my train of thought. Give me just one
second. Okay. So number two is then you know in open sides scan we\'re
not seeing those gaps at what we think is much lower resolution, right?

**Ratul Shashank:** Yes.

**Geoff Horowitz:** So

**Ratul Shashank:** So uh uh to clarify on that uh the open side scan
and the other tool uh that Pratyak shared uh these are uh they are not
geo referencing in the ex in the prop in the pure

### 00:18:28

**Geoff Horowitz:** Mhm.

**Ratul Shashank:** sense. So they are what they are doing is they are
stacking up pins on the y-axis rather than the yaxis in terms of uh the
meters they are just stacking up pings. So if subsequent ping like for
example if ping number 20 uh if the difference between ping number 20
and ping number 21 is large. So in their data in their uh visualization
it won\'t appear as gaps because they are stacking up pings. But what
Sachin did I\'ll cross check that uh he created a raster for the htf im
the htf file. So he what he created was he uh georreerenced that image.

**Geoff Horowitz:** Wait, wait,

**Ratul Shashank:** So it is not

**Geoff Horowitz:** one, one second, RTL. So, so what it sounds to me
like what you\'re saying is that these open source tools,

**Hemanth Sarabu:** Let\'s

**Geoff Horowitz:** they\'ll just compress it if there\'s missing data.
Is that right? Like they\'ll just skip the game.

**Ratul Shashank:** Uh yes.

**Geoff Horowitz:** Okay.

**Hemanth Sarabu:** start

**Geoff Horowitz:** Yeah. They\'ll stack it,

### 00:19:47

**Ratul Shashank:** So so there they they uh open side scans main
objective

**Hemanth Sarabu:** it.

**Geoff Horowitz:** right?

**Ratul Shashank:** is uh it\'s a tool for finding any objects on the C
bit using SSS. That is why they can get away with that. And the other
tool it is used for labeling the HDF files. So that is why they can also
get away with that. They don\'t need uh a ge uh geograph geologically
correct raster. So that is why they are just stacking up things on the
y-axis and we don\'t see anything.

**Geoff Horowitz:** Uh,

**Pratyaksh Singh:** Uh,

**Geoff Horowitz:** Okay.

**Pratyaksh Singh:** a very stupid question, but like what does stacking
the

**Ratul Shashank:** So uh like what they do is they like what

**Pratyaksh Singh:** things

**Ratul Shashank:** we are doing in our raster is we first find what
each ping uh what is the location that each ping corresponds to in terms
of coordinates. So for example if ring number uh 20 is at x= to let\'s
suppose 20° and y is is equals to let\'s suppose - 40°. So if we
rasterize that in terms of degrees latl long degrees so we are we have
to put yaxis is equals to the coordinates but if we stack pings so we
are not putting yaxis as longitude we are just putting yaxis as the ping
number so that is what it would mean like we are stacking up

### 00:21:44

**Ratul Shashank:** pings because they would get a waterfall image
either way. They don\'t need a geo a geologically correct image. So that
is if if that makes sense that is what stacking up means.

**Pratyaksh Singh:** Understood.

**Geoff Horowitz:** Um, okay. Anything else? So, so I think the point is
that\'s how the open- source tools work. I don\'t think that\'s what we
want to do. Um, I think we want to keep our data georreerenced. So the
the I\'m going to say our optimal solution is to use

**Ratul Shashank:** Uh-huh.

**Geoff Horowitz:** the um the higher resolution lowass data if that\'s
available and I\'ll I\'ll ask Bridget about that. If that\'s not
available then internally we can make a decision about whether we want
to use the lower resolution data or if we want to use the higher
resolution data and you know basically make our models um uh what\'s the
word I\'m thinking of um you know like cognizant of of these of
potential gaps in the data. I mean, we can we can make that decision

### 00:23:26

**Ratul Shashank:** Just a follow-up question on that.

**Geoff Horowitz:** later.

**Ratul Shashank:** Uh how do we know the data is high res or low res?
Like do we have different frequency for different data

**Geoff Horowitz:** Such I think Son plotted it

**Ratul Shashank:** sets?

**Geoff Horowitz:** correct.

**Sachin Pandey:** No like the our default pipeline when we like process
both the HTF one gets like very like clean looking data and other is
very like looks to low resolution even with like even when both of them
are at the same resolution. Uh you can see some samples of these in the
ED talk like even in that was the one. Yeah,

**Geoff Horowitz:** This one red,

**Sachin Pandey:** that will be the low pass image.

**Geoff Horowitz:** there was a separate folder of XTFs that they called
lowass that when we plotted

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** The XTFs had higher resolution images.

**Ratul Shashank:** Is low pass low in altitude? Uh what does low pass
stand for?

**Geoff Horowitz:** What?

**Ratul Shashank:** Is it like less

**Geoff Horowitz:** I I don\'t know. Um

**Sachin Pandey:** We need to because if it it was low altitude then the
like then the

### 00:24:44

**Ratul Shashank:** altitude?

**Sachin Pandey:** length will not match or the angle will not

**Geoff Horowitz:** Rul,

**Sachin Pandey:** match.

**Geoff Horowitz:** you might be able to Um, in the data sets for each
of these,

**Sachin Pandey:** Okay. Yeah.

**Geoff Horowitz:** I think they all have a report. Hold on. They all
have a PDF somewhere. Um, that talks through the data available. I think
it might be in this reports folder for this one. Um, you can read
through these reports and they might give additional definitions.

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** Sin, do you remember? I think it\'s I think it\'s
this reports folder.

**Sachin Pandey:** Yes, report folders have some PDFs.

**Geoff Horowitz:** Okay.

**Sachin Pandey:** We need the slides.

**Geoff Horowitz:** Yeah. Um, I\'m not sure if it answers those
questions, Rul, but it might. So it\' be worthwhile to

**Ratul Shashank:** is because I was I the reason that I asked though
that question is because

**Geoff Horowitz:** read.

**Ratul Shashank:** resolution can be calculated in two ways. Uh one
would be how open side scan is doing like stacking up things and another
would be the actual geo reference way like what uh like if we create a
meter by meter box what is the number of pixel on that meter by meter
box that we are getting.

### 00:26:25

**Ratul Shashank:** So that would be that but that would affect the
entire image and the concept of resolution. So we should look into

**Sachin Pandey:** So in that term both of them have a same resolution.

**Ratul Shashank:** that.

**Sachin Pandey:** The only difference is with the view. So like the
normal base XTF doesn\'t look like clean enough. And that like you you
wrote some pre-processing pipeline for these right and those like after
running these base XTF it it was looking more like a low pass XTF there
was some I

**Hemanth Sarabu:** Guys, what\'s the lass low pass X here?

**Sachin Pandey:** uh it is like a lass was just the folder name where
the XF was present and the these are like generally looking looks very
clean like without any noise or anything.

**Hemanth Sarabu:** Nice.

**Sachin Pandey:** So Jeff if you open the slide two the slide two. Yeah
the last image is the slide

**Geoff Horowitz:** No, this is Oh,

**Sachin Pandey:** two. Yeah. The last image is the processed one.

**Geoff Horowitz:** sorry.

**Sachin Pandey:** Middle one is the low pass.

### 00:27:54

**Geoff Horowitz:** This is base

**Sachin Pandey:** This is base

**Geoff Horowitz:** image.

**Sachin Pandey:** ext.

**Geoff Horowitz:** And this is lowass image. And this you said is base
image after processing.

**Sachin Pandey:** Yes.

**Ratul Shashank:** What are we processing?

**Geoff Horowitz:** Wait guys, I I need to run in a minute. Um I mean
keep keep talking as long as um you guys have something you need to go
through. Sachin and Ratul can you please go through today and comment on
these these open items. Um just giving an update about where we are uh

**Hemanth Sarabu:** All

**Geoff Horowitz:** or if these are done. Can you guys do that later?

**Ratul Shashank:** Yeah,

**Geoff Horowitz:** Thank you. Okay, I got to draw. Thanks,

**Ratul Shashank:** sure.

**Geoff Horowitz:** S.

**Hemanth Sarabu:** right. Meet you guys.

**Sachin Pandey:** Okay. So, uh, you remember you shared some, uh,
images with the like 0.1 enhanced images and 0.25 25 enhanced images.
These are the enhanced images and they look very similar to the low pass

**Ratul Shashank:** Hello.

**Sachin Pandey:** images.

### 00:29:28

**Ratul Shashank:** After processing

**Sachin Pandey:** Uh, why didn\'t Amen.

**Ratul Shashank:** the laptop Help.

**Sachin Pandey:** You miss

**Ratul Shashank:** WhatsApp computer. Now screen low pass isue issue.
for

**Sachin Pandey:** Where they cut?

**Ratul Shashank:** the

**Sachin Pandey:** Ed basic

**Ratul Shashank:** Uh-huh. Uh-huh.

**Sachin Pandey:** images

**Ratul Shashank:** A file

**Sachin Pandey:** location\_

**Ratul Shashank:** name. 8

**Sachin Pandey:** modified script.

**Ratul Shashank:** minutes last

**Sachin Pandey:** Uh

**Ratul Shashank:** But

**Sachin Pandey:** weak default pipeline define

**Ratul Shashank:** I\'m pipeline.

**Sachin Pandey:** modif

**Ratul Shashank:** or

**Sachin Pandey:** Okay.

**Ratul Shashank:** image\_

**Sachin Pandey:** High resolution cleaner.

**Ratul Shashank:** download image.

**Sachin Pandey:** How they

**Ratul Shashank:** chance

**Sachin Pandey:** deter

**Ratul Shashank:** frequency comea.

**Sachin Pandey:** recording system almost

**Ratul Shashank:** Oh,

**Sachin Pandey:** same property. or sensor name

**Ratul Shashank:** never process.

**Sachin Pandey:** 349 3437 36 34 937 E file CF normal 450. I think she
she

**Ratul Shashank:** You can see zero.

**Sachin Pandey:** sonar frequency. High

**Ratul Shashank:** HR

**Sachin Pandey:** frequency.

**Ratul Shashank:** frequency. Sorry. Wait a minute.

### 00:35:55

**Sachin Pandey:** Okay. Same. Same pipeline.

**Ratul Shashank:** 450 Hz or 450

**Sachin Pandey:** Stone I

**Ratul Shashank:** MHz

**Sachin Pandey:** know.

**Ratul Shashank:** 450 MHz datarf.

**Sachin Pandey:** So now Print the cover. Print whatever.

**Ratul Shashank:** Frequency high frequency horizontal distance.

**Sachin Pandey:** horizontal

**Ratul Shashank:** Most probably horizontal distance or altitude.

**Sachin Pandey:** distance

**Ratul Shashank:** Most probably second_1_1

**Sachin Pandey:** P and rectangle

**Ratul Shashank:** is many

**Sachin Pandey:** and path will improve.

**Ratul Shashank:** SL angle angle matter but range

**Sachin Pandey:** Tangle.

**Ratul Shashank:** or primary altitude. You don\'t know

**Sachin Pandey:** SL range

**Ratul Shashank:** slant

**Sachin Pandey:** charisma

**Ratul Shashank:** altitude. Uh uh normal

**Sachin Pandey:** Hold on.

**Ratul Shashank:** jub_1itude.

**Sachin Pandey:** That\'s the cute

**Ratul Shashank:** Yeah. FG altitude.

**Sachin Pandey:** Sensor primary 800 sensor primary sensor.

**Ratul Shashank:** relevant. Uh

**Sachin Pandey:** Baby.

**Ratul Shashank:** problem lowass image, high pass image resolution.
Resolution we need clarity

**Sachin Pandey:** I one Tedd passing

**Ratul Shashank:** backing heading. color.

**Sachin Pandey:** altitude

**Ratul Shashank:** Heading

### 00:41:16

**Sachin Pandey:** spikes. logic comparison

**Ratul Shashank:** Red. Red.

**Sachin Pandey:** report.

**Ratul Shashank:** smooth or file fluctuations pink

**Sachin Pandey:** Altitude mean across all things.

**Ratul Shashank:** X or Yaxis.

**Sachin Pandey:** Intensity. Intensity.

**Ratul Shashank:** They

**Sachin Pandey:** Density.

**Ratul Shashank:** mhm

**Sachin Pandey:** view.

**Ratul Shashank:** navigation UTM

**Sachin Pandey:** One more hotel. Same here. Navigation.

**Ratul Shashank:** minute. Take

**Sachin Pandey:** We want to check.

**Ratul Shashank:** sense.

**Sachin Pandey:** key. No sona data in one. The backa data in_1tf is
purely receiving received noise and baseline uh thermal noise. It
contains zero batch scatter signal. The water column in the bottom
returns are completely absent resulting in a flat text and very image.
Besides details,

**Ratul Shashank:** Samsung

**Sachin Pandey:** backup data set folder.

**Ratul Shashank:** Red. Huh?

**Sachin Pandey:** All XFore.

**Ratul Shashank:** Hello. or

**Sachin Pandey:** It\'s amazing.

**Ratul Shashank:** maybe

**Sachin Pandey:** Five cycles.

**Ratul Shashank:** You take the Exact location.

**Sachin Pandey:** Proceed extended duration spread file 2 has 7.3x the
contrast of the file one.

### 00:46:07

**Sachin Pandey:** Auto correlation unique 65 199

**Ratul Shashank:** Back data column wise

**Sachin Pandey:** Just process open.

**Ratul Shashank:** Back scatter. Back scatter.

**Sachin Pandey:** section. Okay.

**Ratul Shashank:** Back scatter. Back scatter. Water analysis.

**Sachin Pandey:** Uh

**Ratul Shashank:** So may be

**Sachin Pandey:** session

**Ratul Shashank:** lord open slash

**Sachin Pandey:** cloud cloud

**Ratul Shashank:** SL

**Sachin Pandey:** Perfect.

**Ratul Shashank:** resume.

**Sachin Pandey:** Resume session. SC

**Ratul Shashank:** Low pass, high pass

**Sachin Pandey:** here we put for up

**Ratul Shashank:** problem. Brain

**Sachin Pandey:** there.

**Ratul Shashank:** capture. Low pass, high pass.

**Sachin Pandey:** high resolution. Use the high resolution, low images.
High frequency images.

**Ratul Shashank:** line repeat.

**Sachin Pandey:** So thinking low frequency images, high frequency
images,

**Ratul Shashank:** Uh-huh.

**Sachin Pandey:** high frequency

**Ratul Shashank:** Uh-huh.

**Sachin Pandey:** Tonight. We generate

**Ratul Shashank:** Chatp

**Sachin Pandey:** chat minute.

**Ratul Shashank:** port.

**Sachin Pandey:** Let\'s

**Ratul Shashank:** Questions for bedrop issues. Questions for bedrock
may

**Sachin Pandey:** talk solution here.

**Ratul Shashank:** image resolution cause lines to appear. Third,
let\'s suppose we believe background to include last meeting.

### 00:52:26

**Ratul Shashank:** Can you provide annotations? Graph report.

**Sachin Pandey:** Okay. So I need to

**Ratul Shashank:** Huh.

**Sachin Pandey:** write a random number Just

**Ratul Shashank:** file.

**Sachin Pandey:** recover.

**Ratul Shashank:** File You can suck. Hey, sorry. AKR. No. or first
slide down.

**Sachin Pandey:** 29

**Ratul Shashank:** issues. B 012

**Sachin Pandey:** 2025

**Ratul Shashank:** A

**Sachin Pandey:** 1 slightly

**Ratul Shashank:** 012 A X 011 A or 012 A

**Sachin Pandey:** top

**Ratul Shashank:** 012 or last 14 16

**Sachin Pandey:** 14 16 2 purchase a key purchase

**Ratul Shashank:** 20.

**Sachin Pandey:** plus a thist Just paste that.

**Ratul Shashank:** Yeah, I think I Download particular

**Sachin Pandey:** particular image.

**Ratul Shashank:** particular image

**Sachin Pandey:** You only report

**Ratul Shashank:** report location. Okay.

**Sachin Pandey:** Onboarding on on board port.

**Ratul Shashank:** Onboard reports.

**Sachin Pandey:** Yes.

**Ratul Shashank:** cont.

**Sachin Pandey:** Okay, let\'s make

**Ratul Shashank:** resolution issue. Technically palace be important

**Sachin Pandey:** a resolution.

**Ratul Shashank:** as second

**Sachin Pandey:** Low pass or high pass?

### 00:57:44

**Sachin Pandey:** Normal pass.

**Ratul Shashank:** data issue. Sixth last meeting. Sixth

**Sachin Pandey:** Six.

**Ratul Shashank:** slide. Eight slide.

**Sachin Pandey:** This is wondering

**Ratul Shashank:** Important.

**Sachin Pandey:** if See what 10 slide com

**Ratul Shashank:** Second slide. Important.

**Sachin Pandey:** Second slide.

**Ratul Shashank:** It\'s come.

**Sachin Pandey:** What

**Ratul Shashank:** Yes.

**Sachin Pandey:** better?

**Ratul Shashank:** Ninth side.

**Sachin Pandey:** How to

**Ratul Shashank:** Yeah.

**Sachin Pandey:** get later?

**Ratul Shashank:** Crossification. Second

**Sachin Pandey:** It\'s got chocolate resolution there

**Ratul Shashank:** or specific

**Sachin Pandey:** and

**Ratul Shashank:** mag. That is

**Sachin Pandey:** Default off.

**Ratul Shashank:** working.

**Sachin Pandey:** Default off.

**Ratul Shashank:** Yeah.

**Sachin Pandey:** Enhance waterfall.

**Ratul Shashank:** Sper add argument color cheese or as it is shown.

**Sachin Pandey:** Flag pass.

**Ratul Shashank:** Enhance. Enhanced. Enhanced. Basically, enhance.
Enhance data clean.

**Sachin Pandey:** Internet check.

**Ratul Shashank:** PH enhance resolution.

**Sachin Pandey:** What are you doing?

**Ratul Shashank:** Max quality, minity relevant.

**Sachin Pandey:** Output minus 0.5. Okay. Okay, generate your image
again

### 01:04:45

**Ratul Shashank:** Mhm.

**Sachin Pandey:** expected. Boom.

**Ratul Shashank:** Mhm.

**Sachin Pandey:** High flag. This is the store tool.

**Ratul Shashank:** Get

**Sachin Pandey:** Good.

**Ratul Shashank:** a huh? Huh?

**Sachin Pandey:** Enhanced image. original

**Ratul Shashank:** Ni.

**Sachin Pandey:** pass.

**Ratul Shashank:** Mhm. noise.

**Sachin Pandey:** Shift W pass

**Ratul Shashank:** argument.

**Sachin Pandey:** extra.

**Ratul Shashank:** Eargument Yeah. Help. Apply AGC plus TV.
enhancement.

**Sachin Pandey:** D noise

**Ratul Shashank:** Surf

**Sachin Pandey:** clean.

**Ratul Shashank:** noise. uh short, but AGC

**Sachin Pandey:** Waterfall. Okay.

**Ratul Shashank:** Waterfall image. Waterfall

**Sachin Pandey:** There you

**Ratul Shashank:** image.

**Sachin Pandey:** go.

**Ratul Shashank:** coordinates generate contess. Slide

**Sachin Pandey:** Okay.

**Ratul Shashank:** two.

**Sachin Pandey:** Huh. You replicate me.

**Ratul Shashank:** But huh process. Bar.

**Sachin Pandey:** behind report. generate PDF.

**Ratul Shashank:** display. shock

**Sachin Pandey:** Okay.

**Ratul Shashank:** value.

**Sachin Pandey:** Why don\'t I take

**Ratul Shashank:** General meeting

**Sachin Pandey:** any meeting?

### 01:10:33

**Ratul Shashank:** for

**Sachin Pandey:** Hold stretch cut.

**Ratul Shashank:** Yeah. Yes. Clarity.

**Sachin Pandey:** Deployment.

**Ratul Shashank:** Metro.

**Sachin Pandey:** So, let\'s get

**Ratul Shashank:** Process.

**Sachin Pandey:** here.

**Ratul Shashank:** After processing. comments update

**Sachin Pandey:** Okay. Oh, we thought

**Ratul Shashank:** by cross

**Sachin Pandey:** already.

**Ratul Shashank:** Third ugly slide answer. But

**Sachin Pandey:** Is this still an open question? Need to clarify
exactly what uh what to ask. Current question is are these actually care

**Ratul Shashank:** maker. Third, is this still an open question? Need
to clarify exactly what we want to ask. Current question is are these
actual gaps in data collection or something else? Slide resolution
resolution. resolution issue.

**Sachin Pandey:** Some most of the data

**Ratul Shashank:** Some data as

**Sachin Pandey:** here.

**Ratul Shashank:** in

**Sachin Pandey:** Okay.

**Ratul Shashank:** comments. May

**Sachin Pandey:** Okay. Sorry. This may be confirmed with the report
files or even with the open mag spiking.

**Ratul Shashank:** The gaps. eggs are real and can be find if we just
uh look at how pings are staged.

### 01:15:22

**Ratul Shashank:** Fourth, can we confirm that we are not seeing these
data gaps in the low pass?

**Sachin Pandey:** Okay. Uh, same file here.

**Ratul Shashank:** How about

**Sachin Pandey:** and file name

**Ratul Shashank:** you?

**Sachin Pandey:** duplicate. Okay. Oh yeah.

**Ratul Shashank:** personally send. Yeah. What\'s

**Sachin Pandey:** XDF processing

**Ratul Shashank:** wrong

**Sachin Pandey:** this order tab.

**Ratul Shashank:** with RAM

**Sachin Pandey:** I see a

**Ratul Shashank:** intensive?

**Sachin Pandey:** C%

**Ratul Shashank:** laptop.

**Sachin Pandey:** Minw

**Ratul Shashank:** Yeah,

**Sachin Pandey:** extended htf. Yes.

**Ratul Shashank:** type one.

**Sachin Pandey:** used in code used to determine

**Ratul Shashank:** UTM on there. Be

**Sachin Pandey:** one field XTF mean

**Ratul Shashank:** there.

**Sachin Pandey:** XFatch. for any

**Ratul Shashank:** report.

**Sachin Pandey:** two.

**Ratul Shashank:** Report

**Sachin Pandey:** location. Item system.

**Ratul Shashank:** system.

**Sachin Pandey:** PDF. team. Don\'t worry.

**Ratul Shashank:** Many low pass

**Sachin Pandey:** That\'s empty.

**Ratul Shashank:** resolution or low

**Sachin Pandey:** DRN folder. Main

**Ratul Shashank:** Yeah.

### 01:20:57

**Sachin Pandey:** folder.

**Ratul Shashank:** Mhm.

**Sachin Pandey:** Subnot

**Ratul Shashank:** man. Copy.

**Sachin Pandey:** sensor data. I hope it\'s here.

**Ratul Shashank:** sensor data.

**Sachin Pandey:** It\'s

**Ratul Shashank:** Sorry.

**Sachin Pandey:** Okay.

**Ratul Shashank:** Uh

**Sachin Pandey:** Low pass. High pass. High pass.

**Ratul Shashank:** the process imaginer Yeah.

**Sachin Pandey:** So processed image low pass. Uhhuh.

**Ratul Shashank:** Low pass filter. Low pass filter is a circuit device
or algorithm that allows signal with frequency below us. below a
specific cutff threshold to pass through while blocking or reducing
higher frequencies. Higher frequency lower frequency lower frequency Low
pass frequency. frequency. So

**Sachin Pandey:** See?

**Ratul Shashank:** obviously distance Sorry. Low pass. Low pass. High

**Sachin Pandey:** You\'re

**Ratul Shashank:** pass.

**Sachin Pandey:** Take Skyore A to Z.

**Ratul Shashank:** Definitely. Okay.

**Sachin Pandey:** Dubai repeat

**Ratul Shashank:** XT

**Sachin Pandey:** IP and file.

**Ratul Shashank:** book summary. Yeah.

**Sachin Pandey:** IP code output Gemini Gemini 3.5

### 01:27:23

**Ratul Shashank:** Gemini 3.5

**Sachin Pandey:** low

**Ratul Shashank:** low 3.5

**Sachin Pandey:** 3.5 flash low medium

**Ratul Shashank:** low now low

**Sachin Pandey:** I

**Ratul Shashank:** medium

**Sachin Pandey:** contact

**Ratul Shashank:** 3.1 Pro latest

**Sachin Pandey:** 3.5 passion.

**Ratul Shashank:** 3.5

**Sachin Pandey:** Oh my point in college same level.

**Ratul Shashank:** 999 model. Data chunking data chunking chunk. Fore

**Sachin Pandey:** You see the

**Ratul Shashank:** speech.

**Sachin Pandey:** dollar Cont.

**Ratul Shashank:** Flash.

**Sachin Pandey:** We will take ice cream. Okay.

**Ratul Shashank:** XTF

**Sachin Pandey:** The guide

**Ratul Shashank:** text file. File

**Sachin Pandey:** I think much

**Ratul Shashank:** code.

**Sachin Pandey:** area. Not sure.

**Ratul Shashank:** system data.

**Sachin Pandey:** Take advantage.

**Ratul Shashank:** I want you to understand both commas. uh how the
context is being used in the code. And what are uh uh water and water
and water? Full stop answer. Understand what is the purpose of each
functions in the

**Sachin Pandey:** Okay.

**Ratul Shashank:** code. And does our context file explain or is
sufficient to map out the functionality.

### 01:32:38

**Ratul Shashank:** Sorry, map out the operation of the function. class.
He give me a detailed analysis of the code and what it\'s doing. Comma
data what data it expects. Sorry. What data each function expects and
what they produce. And tell and finally tell me if this uh context file
is enough. Okay,

**Sachin Pandey:** Let your

**Ratul Shashank:** is enough to cover the full scope of

**Sachin Pandey:** table.

**Ratul Shashank:** code. bus prompting.

**Sachin Pandey:** 16 this organization filter applied by pass contains
data convention the file for the

**Ratul Shashank:** Frequency filter.

**Sachin Pandey:** strip time First time

**Ratul Shashank:** Yeah.

**Sachin Pandey:** clearly I have analyzed upgrade.

**Ratul Shashank:** Bridge the gap

**Sachin Pandey:** Would you like to upgrade the main construct guide to
include the computer vision image

**Ratul Shashank:** question.

**Sachin Pandey:** processing algorithm and we are not hold like to run
check on these scripts depending Whatever

**Ratul Shashank:** XT guide

**Sachin Pandey:** original XTF to

**Ratul Shashank:** the gaps.aps.

**Sachin Pandey:** PNG.

**Ratul Shashank:** or you currently have this

### 01:36:49

**Sachin Pandey:** already.

**Ratul Shashank:** Start Low pass, high pass.

**Sachin Pandey:** It\'s good. 284

**Ratul Shashank:** Low pass. High pass.

**Sachin Pandey:** actually low pass. Go enough today. Let\'s

**Ratul Shashank:** Altitude.

**Sachin Pandey:** see.

**Ratul Shashank:** Altitude direction. check.

**Sachin Pandey:** process with any

**Ratul Shashank:** CrossFass.

**Sachin Pandey:** specific Motion

**Ratul Shashank:** High pass.

**Sachin Pandey:** by 28 28

**Ratul Shashank:** Nice. See

**Sachin Pandey:** Z.

**Ratul Shashank:** that?

**Sachin Pandey:** Data is not there.

**Ratul Shashank:** window.

**Sachin Pandey:** Okay. Analyze file.

**Ratul Shashank:** data. Highgine

**Sachin Pandey:** Show Yeah.

**Ratul Shashank:** data.

**Sachin Pandey:** Skilled different development.

**Ratul Shashank:** Shall maybe

**Sachin Pandey:** Okay.

**Ratul Shashank:** answer

**Sachin Pandey:** Okay.

**Ratul Shashank:** questions. questions.

**Sachin Pandey:** Take it. Low pass. High pass.

**Ratul Shashank:** Yeah.

**Sachin Pandey:** How did identify these did they don\'t appear
visible? So is BRX using MAC data like

**Ratul Shashank:** Johch.

**Sachin Pandey:** report

**Ratul Shashank:** Waterfall images or TV

**Sachin Pandey:** What\'s

**Ratul Shashank:** strip.

**Sachin Pandey:** going like

**Ratul Shashank:** illuminated beach

**Sachin Pandey:** me. You all

**Ratul Shashank:** center. So binary data waterfall waterfall Mac data
cont.

**Sachin Pandey:** See everything.

**Ratul Shashank:** possibilities options.

**Sachin Pandey:** holding

**Ratul Shashank:** Same file

**Sachin Pandey:** almost same file\_

**Ratul Shashank:** almost but port. Same

**Sachin Pandey:** The file

**Ratul Shashank:** data.

**Sachin Pandey:** name.

**Ratul Shashank:** range. Waterfall intensity. Zange depth report.
report.

**Sachin Pandey:** Take

**Ratul Shashank:** WhatsApp

**Sachin Pandey:** two.

**Ratul Shashank:** Tell three.

**Sachin Pandey:** Okay. Open question. Open task.

### Transcription ended after 01:46:54

*This editable transcript was computer generated and might contain
errors. People can also change the text after it was created.*
