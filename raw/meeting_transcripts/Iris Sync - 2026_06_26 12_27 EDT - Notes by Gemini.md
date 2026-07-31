Jun 26, 2026

## Iris Sync

Invited [[Sachin Pandey]{.underline}](mailto:sachin@crescer.ai)
[[Pratyaksh Singh]{.underline}](mailto:pratyaksh@crescer.ai) [[Niveta
Iyer]{.underline}](mailto:niveta@crescer.ai) [[Hemanth
Sarabu]{.underline}](mailto:hemanth@crescer.ai) [[Geoff
Horowitz]{.underline}](mailto:geoff@crescer.ai) [[Siddharth
Soni]{.underline}](mailto:siddharth@crescer.ai) [[Ratul
Shashank]{.underline}](mailto:ratul@crescer.ai)

Attachments [[Iris
Sync]{.underline}](https://calendar.google.com/calendar/event?eid=NnNzMHVxNzk3MmJqZGVwNXFoN2J1Mjd1OTdfMjAyNjA2MjZUMTYzMDAwWiBnZW9mZkBjcmVzY2VyLmFp)

Meeting records
[[Transcript]{.underline}](https://docs.google.com/document/d/1G4XSk1LvSU7oJ2x6jYsI1KiVbUkLB6O5JL3mu4RGI1c/edit?usp=drive_web&tab=t.1udnb5p9nvu5)

### Summary

Team discussions focused on data management strategies and image
processing workflows with established plans for initial iterations.\
\
**Data Management and Processing**\
The team confirmed dataset collection status and discussed technical
requirements for TIFF resolution and intensity normalization. They
concluded that existing conversion pipelines will serve as the baseline
for initial development phases.\
\
**Addressing Dataset and Annotation Issues**\
Discrepancies in contact counts and identification of dead zones
prompted a review of annotation data. The team identified the need to
cross reference files and verify visual contact data before client
consultation.\
\
**Client Consultation Strategy**\
The team established a list of open issues to discuss with the client,
including expanded dataset needs and magnetic data methodology. A final
decision was made to verify data validity before external communication.

### Decisions

Aligned

-   **Bedrock data processing pipeline inquiry** The team will contact
    > Bedrock to inquire about their specific data processing pipeline
    > and software to gain necessary context.

-   **Existing XTF pipeline usage confirmed** The team will proceed with
    > the current XTF-to-PNG conversion pipeline for the initial project
    > iteration before attempting alternative enhancement methods.

-   **Separate port and starboard data processing** The team decided to
    > process port and starboard sonar data separately to prevent model
    > confusion resulting from gaps in the combined data.

We\'ve **updated the Decisions section** using your feedback.

Let us know what you think:
[[Helpful]{.underline}](https://google.qualtrics.com/jfe/form/SV_5p6FWBVWvynleNU?isGoogler=no&isHelpful=yes)
or [[Not
Helpful]{.underline}](https://google.qualtrics.com/jfe/form/SV_5p6FWBVWvynleNU?isGoogler=no&isHelpful=no)

### Next steps

-   \[Geoff Horowitz\] Share contact update: Post the message from the
    > contact on Slack to the team.

    > \[Geoff Horowitz\] Inquire collection resolution: Clarify with the
    > contact if the project expects the same collection resolution for
    > current files.

    > \[Geoff Horowitz\] Research processing pipeline: Inquire with the
    > contact about the specific software or pipeline used for data
    > processing.

    > \[Ratul Shashank\] Recreate processing pipeline: Investigate if
    > the internal engineering team can replicate the external data
    > processing methodology.

    > \[Geoff Horowitz\] Clarify Input Format: Confirm with Bridget
    > whether the team should use raw images or if there is a way to
    > receive images directly as inputs instead of XTFS.

    > \[Ratul Shashank, Pratyaksh Singh\] Validate Ants Data: Check the
    > ants data for visible mines using the open source tool without
    > enhancement.

    > \[Ratul Shashank\] Document Image Enhancement: Create a
    > documentation file detailing the algorithms tested for XTF image
    > enhancement and share it with the group.

    > \[Ratul Shashank\] Test Enhancement Algorithms: Test image
    > enhancement algorithms on at least 10 images from all datasets,
    > including POE, DRN, and VW, to ensure predictable results.

    > \[Geoff Horowitz\] Verify Roll Input: Confirm with Bridget whether
    > roll data is available as a separate input for the datasets.

    > \[Geoff Horowitz\] Clarify Blue Triangles: Ask Bridget
    > specifically about the blue triangle plots found in the reports to
    > understand their meaning.

    > \[Geoff Horowitz\] Coordinate Mag Data Meeting: Coordinate a
    > meeting with Bridget to discuss the magnetic data usage and
    > determine how it can be incorporated to identify contacts.

    > \[Sachin Pandey\] Capture Mosaic Screenshot: Provide a screenshot
    > of the mosaic screen showing the specific contacts in the Danish
    > Royal Navy dataset.

    > \[Geoff Horowitz\] Reconcile Contact Counts: Verify the
    > discrepancy between the 10 contacts reported by Bridget and the 7
    > contacts found by the team in the Danish Royal Navy dataset.

    > \[Sachin Pandey\] Investigate Missing Targets: Download the found
    > targets for mission planning from the website to investigate why
    > the report indicates 10 contacts.

    > \[Sachin Pandey\] Investigate unknown contacts: Confirm the
    > remaining three contacts in the targets as found folder by
    > investigating why they are not visible.

    > \[Sachin Pandey\] Verify DRN contacts: Confirm that all seven
    > contacts in the Danish Royal Navy data set are visible in at least
    > one XTF file.

    > \[Sachin Pandey\] Verify ENTX targets: Confirm that all six
    > targets in the ENTX data set are visible.

    > \[Geoff Horowitz\] Share draft for Bridget: Share the drafted
    > message for Bridget with the team for review before sending it.

    > \[Sachin Pandey, Ratul Shashank\] Review Bridget message: Review
    > the draft message for Bridget once shared and provide
    > confirmation.

### Details

-   **Communication Update from Bridget**: Geoff reported receiving a
    > message from a contact regarding \"title\" (tide) related issues.
    > The contact is investigating, and Geoff confirmed the team is open
    > to a follow-up chat once more information is available .

-   **Dataset Collection Status**: Sachin provided an update on data
    > collection, noting that most available data has been gathered.
    > They observed that several URLs redirected to the same S3 folders,
    > but data for New Zealand, the US, and Canada was successfully
    > retrieved ([[00:07:08]{.underline}](#section-2)).

-   **Future Data Management**: The team discussed plans to obtain
    > bounding boxes for all collected data. This will allow them to
    > categorize data by area and time, enabling more efficient analysis
    > and potential manual verification of specific data segments .

-   **TIFF File Resolution**: The team assessed the resolution of TIFF
    > files. Ratul confirmed that a resolution of 0.25 is sufficient to
    > identify contacts, and higher resolutions are not necessary for
    > their objectives .

-   **Identification of Processed Data**: Ratul clarified that files
    > ending in underscore one (\_1) are pre-processed by Bedrock for
    > visual appeal rather than being raw data. These files are found in
    > a folder labeled \"processed sensor data\" .

-   **Utility of Bedrock's Processing Pipeline**: There was a discussion
    > regarding whether to request details of Bedrock's processing
    > pipeline. The team concluded that while they might not be able to
    > replicate the exact process or use the processed data directly for
    > machine learning segmentation, gaining context on Bedrock's
    > methodology would be beneficial .

-   **Intensity Normalization and Segmentation Concerns**: Pratyaksh
    > expressed concern about how intensity values, which can range up
    > to 16,000, are normalized and packed for segmentation. They
    > emphasized that the method used to transform these values---such
    > as log transformation or min-max scaling---could impact the
    > machine learning model\'s performance .

-   **Historical Project Context**: Geoff clarified that during the
    > Vineyard Winds project, the team worked exclusively with raw data,
    > as processed mosaics were not part of the onboard pipeline and
    > were generated independently
    > ([[00:27:46]{.underline}](#section-16)).

-   **Visual Appeal vs. Data Integrity**: The team compared raw and
    > processed images. Ratul noted that processed images appear clearer
    > to the human eye due to contrast enhancement but likely lose
    > details necessary for machine learning segmentation. Pratyaksh and
    > Ratul debated whether the processing performed by Bedrock involves
    > slant height correction .

-   **Image Gap Analysis**: The team debated the cause of gaps visible
    > in the images. Pratyaksh suggested the gaps might result from
    > slant height correction, while Ratul noted the gaps could also
    > represent the \"nadir zone,\" which is the area directly beneath
    > the vehicle that is often poorly illuminated .

-   **Bedrock's Labeling Sources**: Pratyaksh asked if Bedrock uses
    > processed images for manual labeling. Geoff explained that Bedrock
    > likely uses a combination of data sources, including magnetic data
    > and multi-beam point clouds, rather than relying solely on
    > processed imagery .

-   **Strategy for Initial Iterations**: The team reached a consensus to
    > proceed with the existing XTF to PNG conversion pipeline for
    > initial iterations, as it is a proven method. They agreed to avoid
    > over-engineering with new enhancements or custom slant height
    > corrections until they have established baseline results .

-   **Port and Starboard Data Processing**: Pratyaksh Singh and Ratul
    > Shashank discussed separating port and starboard data for model
    > training to eliminate the confusing gap created by combined
    > datasets. While they agreed this is a viable strategy for the
    > future, Pratyaksh Singh noted they must proceed with caution
    > regarding the specific geo-referencing requirements of the data
    > ([[01:00:48]{.underline}](#section-38)).

-   **Image Quality and Pre-processing**: Pratyaksh Singh instructed the
    > team to first test the \"ants\" dataset without enhancement using
    > the existing open-source tools. Ratul Shashank proposed an
    > approach that normalizes images by increasing the pixel intensity
    > in shadow regions. Pratyaksh Singh requested that Ratul Shashank
    > test various algorithms across at least eight to ten images from
    > all provided datasets---specifically POE, DRN, and VW---to ensure
    > consistent enhancement. Furthermore, Pratyaksh Singh emphasized
    > the necessity of documenting these algorithm trials in a shared
    > document so other team members can evaluate the results
    > ([[01:02:06]{.underline}](#section-39)).

-   **XTF to Image Conversion**: Pratyaksh Singh and Geoff Horowitz
    > discussed the potential to request raw images from the client
    > instead of XTF files to reduce the internal processing workload,
    > with Geoff Horowitz agreeing to confirm this with the client. The
    > team identified an issue with the provided XTF-to-PNG conversion
    > script, noting that it relies on a specific sensor processing
    > module that they do not possess. Geoff Horowitz observed that it
    > would be difficult to ask the client for the missing script
    > components now that the initial phase of work has already been
    > completed ([[01:05:49]{.underline}](#section-42)).

-   **AUV Roll Data Analysis**: The group discussed the impact of AUV
    > roll on sidescan data, noting that it creates ripple-like
    > features. Ratul Shashank reported that the \"mag-cal-1\" folder
    > within the DRN dataset contains significant roll, likely because
    > the AUV was calibrating its sensors. Pratyaksh Singh suggested
    > that they might need to generate synthetic data if the current
    > examples are insufficient, though Geoff Horowitz noted they would
    > first verify with the client if more examples of roll data are
    > available ([[01:09:31]{.underline}](#section-45))
    > ([[01:13:24]{.underline}](#section-48)).

-   **Definition of Project Issues for Client Consultation**: Geoff
    > Horowitz summarized the primary issues they intend to present to
    > the client, Bridget. These include the need to train on expanded
    > datasets, incorporate new contact types such as mines and
    > UXOs---which were missing from the Vineyard Wind (VW)
    > data---addressing seabed dredge bottom identification, and
    > developing methods to recognize AUV roll as non-contact data. They
    > also discussed using synthetic data to address the limited size of
    > the current dataset ([[01:20:01]{.underline}](#section-53)).

-   **Elevation Maps and Sensor Data Requests**: Sachin Pandey inquired
    > about obtaining an elevation map script, suggesting it would
    > assist with tilt-related issues. Geoff Horowitz expressed
    > hesitation, fearing that requesting further scripts might force
    > them to justify their technical needs to the client. The team
    > debated whether they could utilize alternative altitude data to
    > avoid requesting more intellectual property from the client, with
    > Geoff Horowitz deciding to reconsider the request later
    > ([[01:21:15]{.underline}](#section-54)).

-   **Magnetic (Mag) Data Methodology**: The team discussed the
    > challenge of interpreting magnetic data, specifically the lack of
    > clear correlations between spikes in mag data and actual contacts.
    > Ratul Shashank highlighted that in previous datasets, the values
    > in regions of interest were inconsistent, making it difficult to
    > differentiate contacts from background noise. Geoff Horowitz
    > concluded that a meeting with the client is necessary to
    > understand their methodology for identifying contacts via mag
    > data, as the team aims to perform the analysis independently while
    > retaining their own intellectual property
    > ([[01:24:05]{.underline}](#section-56)).

-   **Discrepancy in Contact Counts**: Sachin Pandey reported challenges
    > mapping reported contacts to XTF images for the Danish Royal Navy
    > (DRN) and ENTX datasets. While the client claimed there were 10
    > contacts in the DRN data, Sachin Pandey was only able to identify
    > seven unique contacts after reviewing JSON files and visual
    > annotations. The team discovered that many files contained
    > duplicate or slightly offset annotations, leading to confusion.
    > Geoff Horowitz instructed Sachin Pandey to provide a screenshot of
    > the mosaic screen to verify the contact counts before
    > communicating this discrepancy to the client
    > ([[01:31:26]{.underline}](#section-61)).

-   **Dead Zones and Annotation Visibility**: The participants addressed
    > \"dead zones\" where potential objects are obscured by black
    > regions or the water column. Ratul Shashank confirmed that visual
    > identification is impossible in these areas. Sachin Pandey
    > suggested that these annotations might be correctly placed but are
    > simply associated with the wrong file, and that other files likely
    > contain the same annotations in visible regions. They agreed to
    > cross-reference the annotations with other available XTF files to
    > ensure positive identification of the contacts
    > ([[01:47:04]{.underline}](#section-71)).

-   **Finalization of Open Assignments**: Geoff Horowitz finalized the
    > list of open items for the team to complete before contacting the
    > client. Sachin Pandey is tasked with investigating three
    > \"unknown\" targets from the \"targets as found\" folder to
    > determine their validity. Additionally, Sachin Pandey must confirm
    > that all seven contacts in the DRN dataset and six contacts in the
    > ENTX dataset are visually identifiable in at least one XTF image.
    > Geoff Horowitz planned to share the drafted list of questions with
    > the team for review that evening
    > ([[01:50:47]{.underline}](#section-74)).

*You should review Gemini\'s notes to make sure they\'re accurate. [[Get
tips and learn how Gemini takes
notes]{.underline}](https://support.google.com/meet/answer/14754931)*

*How is the quality of **these specific notes?** [[Take a short
survey]{.underline}](https://google.qualtrics.com/jfe/form/SV_9vK3UZEaIQKKE7A?confid=OZb5ZlrXT2yk4J2tFi3MDxIUOAIIigIgABgECA&detailid=standard&screenshot=false)
to let us know your feedback, including how helpful the notes were for
your needs.*

**📖 Transcript**

Jun 26, 2026

## Iris Sync - Transcript

### 00:02:22

**Ratul Shashank:** Hello section.

**Sachin Pandey:** There we go. Nothing.

**Ratul Shashank:** I look like that.

**Geoff Horowitz:** Hey guys.

**Ratul Shashank:** Hey there.

**Geoff Horowitz:** Okay. Um Oh,

**Pratyaksh Singh:** All

**Geoff Horowitz:** I got a message from then. Uh there\'s nothing
notable. Uh I just touch I know sometimes you\'re interested and uh what
I talk to him about. So I\'ll share this with you guys.

**Pratyaksh Singh:** right.

**Geoff Horowitz:** I\'ll send it to you on Slack. Uh no no he just

**Pratyaksh Singh:** Is that something like is you happy with the
prediction

**Geoff Horowitz:** said actually here I\'ll just read it to you. He
said first he said to me can we have a chat about the outputs?

**Pratyaksh Singh:** Hard

**Geoff Horowitz:** I said, \"Sorry, this is delayed.\" He said, \"We
we\'ve been slammed with other things.\" And so, I thought he just
wanted to kind of do this overall update. And then before I responded to
him, he said, \"Actually, I think what I\'m seeing is title related.\"
Um, like, you know,

### 00:05:42

**Pratyaksh Singh:** title list.

**Geoff Horowitz:** tides, tides, like title.

**Pratyaksh Singh:** Okay. All

**Geoff Horowitz:** Yeah. Title meaning tides. And so, I just said to
him, I\'m I\'m happy to chat if you still want to.

**Pratyaksh Singh:** right.

**Geoff Horowitz:** Um, I asked him, you know, if he does, when does he
want to chat? And he said, \"Let me do a bit more investigating. I think
what I\'m seeing is explainable. It just looks odd.\" So, I didn\'t dig
in because I didn\'t want to know right now. Um, but yeah, that\'s
that\'s what happened. I said, \"No, no problem. Let me know if you want
to chat.\"

**Pratyaksh Singh:** Makes

**Geoff Horowitz:** Um, okay.

**Pratyaksh Singh:** sense.

**Geoff Horowitz:** All right. Uh, is there anything I related that we
need to discuss?

**Pratyaksh Singh:** We can discuss on the data set collection thing
that session is working out and

**Geoff Horowitz:** Okay.

**Pratyaksh Singh:** plan behind it but nothing apart from

**Geoff Horowitz:** Okay.

**Pratyaksh Singh:** that.

**Geoff Horowitz:** Uh Sachin if if you think there\'s something more to
share than what project shared on the chat yesterday um or if you need
some feedback let\'s go ahead otherwise I think we can go on to bedrock

### 00:07:08

**Sachin Pandey:** mainly with data sub collection we collected all the
data we could and like if you you try to search more like there\'s
multiple files were redirect to the same S3 folders so like the you see
this the fly the

**Geoff Horowitz:** Do I see the slide?

**Sachin Pandey:** first link first one this data set is not corrected I
site just the

**Geoff Horowitz:** Oh, fly.

**Sachin Pandey:** open source data set and they have just redirected
the URL. So like I stumbled upon the same URL for most of the data set.
So other than that we have a separate URL for New Zealand and uh from US
and Canada. These are mainly the bigger ones.

**Geoff Horowitz:** Okay.

**Hemanth Sarabu:** This is good.

**Geoff Horowitz:** Is there anything you Is there anything you need? Is
there a decision that we need to make here or we\'re just going to keep
going with it?

**Sachin Pandey:** So uh let\'s talk future plan with the data

**Hemanth Sarabu:** What is this for? Oh, never mind. Never mind.

**Sachin Pandey:** set.

**Hemanth Sarabu:** Never mind.

### 00:08:21

**Geoff Horowitz:** Okay.

**Hemanth Sarabu:** I\'ll ask Geminis.

**Geoff Horowitz:** He the the short version is what you\'re what
you\'re seeing is the the data set collection effort for the parent
model. If you look at the Iris channel project shared a link to this
document.

**Hemanth Sarabu:** Ah,

**Geoff Horowitz:** Okay. Right. Sorry S.

**Hemanth Sarabu:** okay.

**Geoff Horowitz:** What were you saying?

**Sachin Pandey:** Yeah, there are some data set which don\'t have
direct SD access. We will be ignoring those for now unless we really
need it because it will take time to like select the area and download
the data set. But it\'s it\'s just there if you want it and other is
like a future plan NP to uh get the bounding boxes of the whole data set
for all the data present and based on

**Geoff Horowitz:** Okay.

**Hemanth Sarabu:** What?

**Sachin Pandey:** that we can like categorize it which area we want and
which time we want and

**Geoff Horowitz:** Okay.

**Sachin Pandey:** to dig deep into it like we can ask laborers to go
check each data for the

**Geoff Horowitz:** Okay.

### 00:09:22

**Sachin Pandey:** classification and other things.

**Geoff Horowitz:** All right. Okay. Um, yeah, I guess we\'ll we\'ll
talk about it more further down the road. Um, okay, let\'s talk bedrock.
So, first and foremost, I want to keep going through I want to I need to
send bridge at these questions today. So, I want to make sure that all
these are addressed and answered. Um, Sachin Rul, I saw that you
addressed some of these questions uh during the day today, but I
haven\'t had a minute to look at them yet.

**Hemanth Sarabu:** Yes.

**Geoff Horowitz:** Um, so if it\'s okay with you, let\'s just go
through them anyway. Okay.

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** Um, based on the naming of the TIFF files, they\'re
using 5 centimeters. So, we think that they\'re all using 5 centimeters.
Fine. I will I\'ll ask her if we expect the same collection resolution.
Um, yeah, I\'m gonna ask her that anyway. Okay, we didn\'t have any
questions. These are not relevant for us. The gap is not a problem.

### 00:11:03

**Geoff Horowitz:** Okay, great. And even if this exact method is used
such and used the gap is only going to be apparent if we increase the
resolution. Um do we need higher resolution in order to identify the
contacts?

**Ratul Shashank:** I don\'t think so. As far as I uh 0.25 R should be
enough.

**Geoff Horowitz:** Yeah. So I mean even if we look at this contact I
don\'t know how well you guys can see it but at this point too I think
this is the contact right here and I

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** mean I certainly this is is higher resolution you
know over there um but I think this contact is still visible so I agree
with that. Okay, fine. I will bring it up. Two seconds. Rachel, can you
give me a brief summary of what you were saying here?

**Ratul Shashank:** Uh so basically all the and all or the files that
end with underscore one uh those files are those files are processed
files. Uh bedrock used some uh method for processing.

### 00:12:45

**Ratul Shashank:** Uh I how I came up with the conclusion is I looked
up in the data set zip of DRN itself and they have a separate folder uh
with name processed sensor data and uh these uh and the name lowass and
high pass. This is basically the altitude like we are using two AUVs.

**Geoff Horowitz:** Mhm.

**Ratul Shashank:** AOV 011 is uh capturing on lower

**Geoff Horowitz:** Yeah.

**Ratul Shashank:** altitude uh and that is called low pass and AOV012
is capturing on higher altitude and that is called high pass. So what
they are categorizing as low pass and high pass in the process sensor
report is basically they use some processing pipeline uh we don\'t know
what they used uh to just make the the image appear

**Hemanth Sarabu:** Thanks.

**Ratul Shashank:** uh better visually

**Geoff Horowitz:** Wait, but these are two different things, Rul,
right? So, so one you\'re saying you\'re saying they either sent the
they sent this submersible, you know, further down or somehow uh, you
know, somehow got the sensor lower,

**Ratul Shashank:** No, no, no. Uh uh to clarify on that uh we

### 00:14:05

**Geoff Horowitz:** right?

**Ratul Shashank:** have the raw data uh they in the survey report they
extracted the raw data uh using two two AUVs the 011 all the AOV that is
with name AOV-011 are operating on lower altitude and

**Geoff Horowitz:** Uh-huh.

**Ratul Shashank:** all the AOVs that are on 012 are operating on higher
amplitude and they are processing those images with a pipeline that they
are using and that is what they are calling and that is what they have
classified as underscore one images. So that is not raw data that is
processed data on their end.

**Geoff Horowitz:** I see what you\'re saying.

**Ratul Shashank:** uh and uh and as far as I have uh as as far as I
have found

**Geoff Horowitz:** Okay.

**Ratul Shashank:** uh the only reason for that processing is visual
appeal.

**Geoff Horowitz:** is

**Ratul Shashank:** So for us visual appeal so that uh the data is more

**Geoff Horowitz:** what

**Ratul Shashank:** uh apparent to eyes that

**Hemanth Sarabu:** Which one?

**Ratul Shashank:** is all the all

**Geoff Horowitz:** the low low pass.

**Hemanth Sarabu:** Altitude. Okay.

**Geoff Horowitz:** Yeah.

### 00:15:28

**Ratul Shashank:** the underscore one files all all the_1 files are
processed data be it lowass or high pass every file that is that ends
with_1 are processed datas that is The processing is done by TRN or
Bedrock themselves. These are not raw data. So these would be of no use
to us.

**Geoff Horowitz:** I thought there I thought there was a specific
folder called low pass.

**Ratul Shashank:** Any file that ends uh

**Geoff Horowitz:** Is there not my

**Ratul Shashank:** yes that specific folder is inside a folder process
sensor data.

**Geoff Horowitz:** remembering

**Ratul Shashank:** So every data inside that folder be it low pass or
high pass these are all processed data. So these would be not relevant
for us.

**Pratyaksh Singh:** What do they mean process data and why won\'t it

**Ratul Shashank:** Uh because uh just can you just go up a slide? Uh
this is the image that was waterfall image that was made on the process
data. Uh we can see that these uh this image is much clearer. So they
used a processing uh pipeline.

### 00:16:55

**Ratul Shashank:** We don\'t know yet. We don\'t know what processing
they used. But this is not raw data.

**Geoff Horowitz:** Do you remember off the top of your head? I I
actually think I think our is right. I think Bridget said to us we
should only look at the raw data,

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** the process data they do offline.

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** Yeah.

**Hemanth Sarabu:** Yes.

**Geoff Horowitz:** Okay. That\'s my recollection.

**Hemanth Sarabu:** Correct.

**Ratul Shashank:** and and and I have also prepared a short def on this
end like uh uh I uh the entire purpose of me was to find if what this
underscore one images is. So uh I when I checked uh basically when I
asked AI to check what what the uh how we can classify this as process
and how we can classify this as row. So AI AI checked for the
normalization and

**Geoff Horowitz:** Mhm.

**Ratul Shashank:** uh and other stuffs. Uh so based on those uh
assumptions and also how the folder has staged because it is literally
uh in a folder called process sensor report.

### 00:18:24

**Ratul Shashank:** So that is why this is very possible that these data
are pre-processed by some

**Geoff Horowitz:** Understood.

**Ratul Shashank:** software

**Geoff Horowitz:** Um, so in summary, we actually don\'t have any
questions about about this resolution, right? I mean, we\'re just going
to take the raw we expect to have access to the raw data there.

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** There are not multiple versions of the raw data and
so so so we we really don\'t have an an open question here.

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** Is that correct?

**Ratul Shashank:** Yes.

**Geoff Horowitz:** Okay. Okay. Fine.

**Ratul Shashank:** uh there we can ask one questions one question which
I don\'t know if this is relevant for us we can ask bedrock what
pipeline did they use or what software they used for processing data if
that is relevant for us and if we should do that I don\'t know but

**Hemanth Sarabu:** I think We I think they write their own software for
this and they Jeff did they ever share that with us?

**Geoff Horowitz:** Yeah.

**Ratul Shashank:** Yeah.

**Hemanth Sarabu:** I feel like can\'t remember if they did but rul I
think when we are we are able to recreate any of

### 00:19:53

**Geoff Horowitz:** Okay.

**Hemanth Sarabu:** their process stuff.

**Ratul Shashank:** Uh I\'ll actually we can only speculate. So based

**Hemanth Sarabu:** No I Are we are able to recreate their stuff their
uh like their processed

**Ratul Shashank:** Yeah,

**Hemanth Sarabu:** files

**Ratul Shashank:** that we can only we don\'t not to a great degree
unless we know what methods they use. We can only speculate like if they

**Hemanth Sarabu:** right I\'m not saying do the do

**Ratul Shashank:** use

**Hemanth Sarabu:** the outputs of our processing our processing look
worse than their processed data There.

**Ratul Shashank:** the enhancement the enhancement that we I am
searching that we were using earlier that did not uh uh actually I need
to check if we can I I don\'t have data to answer your question. At this
point,

**Hemanth Sarabu:** Okay.

**Ratul Shashank:** I will check if we can uh recreate this uh

**Hemanth Sarabu:** Okay. So,

**Ratul Shashank:** pipeline.

**Hemanth Sarabu:** we should um we can I think we looked into asking
them for the processing pipeline. I think they may have shared
something. I cannot remember.

### 00:21:25

**Hemanth Sarabu:** Jeff, do you

**Geoff Horowitz:** Yeah,

**Hemanth Sarabu:** remember?

**Geoff Horowitz:** they they only share for the XTF pipeline like how
they generate images from their

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** XTFs.

**Hemanth Sarabu:** And that\'s all that\'s all there is.

**Geoff Horowitz:** Uh yeah, but that\'s What\' you say

**Pratyaksh Singh:** Where is that?

**Geoff Horowitz:** project?

**Pratyaksh Singh:** Uh where is that resource for generating images
from

**Geoff Horowitz:** I think we\'re using it already. Suchin,

**Pratyaksh Singh:** X?

**Hemanth Sarabu:** I think we incorporated it.

**Geoff Horowitz:** I think you I think you incorporate or maybe Sid did
this, but let me let me look.

**Hemanth Sarabu:** I think incorporated.

**Geoff Horowitz:** Um, this was a while

**Pratyaksh Singh:** All right. All right.

**Geoff Horowitz:** ago.

**Hemanth Sarabu:** So yeah. So here\'s what I\'m saying. Do we know
what our problem is? If our if we know what our problem is and if we
look if we say the way their processed outputs are better than our
processed outputs, then we can go and ask them what specifically is
different.

**Ratul Shashank:** As far as we know at this stage, um the processing
that they did was entirely for visual appeal so that the features could
be more apparent to eyes.

### 00:22:40

**Ratul Shashank:** But the uh the pipeline that they used it destroyed
many uh details and normalized uh to a huge extent. So as far as
computer and ML segmentation is concerned I don\'t think we should do
that.

**Hemanth Sarabu:** Okay. Um so it is important to remember that they
are probably also maybe not. Okay. Um so R you\'re saying that it
doesn\'t sound like we need to know what they\'re doing. We can do
whatever we want for for segmentation.

**Ratul Shashank:** Yes.

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** I pinged you guys on

**Pratyaksh Singh:** Uh I\'ll I\'ll I\'ll think I think it\'s it might

**Geoff Horowitz:** the

**Pratyaksh Singh:** because I\'m concerned about the ranges because the
XTF string values they range between like uh they can go as high as
16,000 plus values from 0 to 16,000 plus

**Ratul Shashank:** Here

**Pratyaksh Singh:** values the raw intensity and we are currently using
log values to transform it to the range for images.

**Ratul Shashank:** we

**Pratyaksh Singh:** So you

**Ratul Shashank:** go.

**Pratyaksh Singh:** know I I think it might matter because uh from what
I have gotten from breeding is that usually these contacts come in high
high intensity region.

### 00:24:27

**Pratyaksh Singh:** Okay. One of the sign is that they will have high
intensity the black color that we see. So I think it it might matter
because we are going to pack it between 0 and 256 for our segmentation
pipeline. So how we pack it might matter how we normalize the values it
might matter or we can try running the segmentation model on

**Hemanth Sarabu:** I

**Pratyaksh Singh:** the raw values which I don\'t know will work

**Hemanth Sarabu:** see.

**Pratyaksh Singh:** on

**Ratul Shashank:** I think then it\'s best that we know what they are
using and then we can check with both so that we would have the data if
the processing that they are using creates better results because
obviously the processing that they use uh that pipeline has reduced
shadows on top and and the middle end. So I don\'t know if that will
help in segmentation but it\'s best to know just for sake of collecting
data.

**Hemanth Sarabu:** Okay, I got a drop.

**Geoff Horowitz:** All right,

**Hemanth Sarabu:** Amen.

**Geoff Horowitz:** I am up. So, what\'s what was the conclusion we came
to?

### 00:26:00

**Ratul Shashank:** I think we should ask them.

**Geoff Horowitz:** Because

**Ratul Shashank:** It\'s best to know before.

**Geoff Horowitz:** we should ask them how they\'re generating the
process

**Ratul Shashank:** Yes.

**Geoff Horowitz:** data.

**Ratul Shashank:** like there is an entire folder that is that is
called process sensor uh report and uh I think it could be we can we can
get context if that process would be helpful for our pipeline I I
personally I don\'t know because I don\'t uh I don\'t know much on that
but it\'s best to have context

**Geoff Horowitz:** Um, it\'s Best to have

**Pratyaksh Singh:** I\'m also actually confused by the raw versus
process

**Geoff Horowitz:** context

**Pratyaksh Singh:** data because till now I I have been working with
XTFS. I don\'t know if it\'s raw or or the process from so I am kind of
confused like what

**Geoff Horowitz:** for for vineyard for vineyard wins.

**Pratyaksh Singh:** is

**Geoff Horowitz:** We only worked with raw because because that\'s
that\'s what Bridget wanted us to

**Pratyaksh Singh:** Mhm.

**Geoff Horowitz:** do. Um, so the processed suction,

**Pratyaksh Singh:** Okay.

**Geoff Horowitz:** do you remember this for processed?

### 00:27:46

**Geoff Horowitz:** I think for vineyard winds processed was the
mosaics.

**Sachin Pandey:** I don\'t I I don\'t remember

**Geoff Horowitz:** I can\'t hear you.

**Sachin Pandey:** this.

**Pratyaksh Singh:** I remember the mosak and it was that you know
things were more clear in the moss but we didn\'t have to uh sorry but
we we weren\'t allowed to work on it work with it

**Geoff Horowitz:** Right, right, right. Because they because that\'s
not part of their onboard pipeline. the mosaics were were generated
independently. Um, look, Rachel, I\'m I\'m I\'m happy to kind of ask for
for uh you know what they\'re doing in post-processing. I\'m happy to
ask and get some insight. Um there are what\'s the concern? The concern
is multiffold. Number one, for a variety of reasons. Um I don\'t think
that Bridget will share the actual code that they use to process the
data. That\'s number one. Uh number two, she has said explicitly she\'s
just kind of sharing the the the process data because it\'s already all
together. It\'s easy to share, but she only wants us to focus on the raw
data.

### 00:29:25

**Geoff Horowitz:** That\'s number two.

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** Um

**Ratul Shashank:** Uh I mean as much as I have seen uh there\'s also a
folder regarding Danish Royal Navy. Even in that folder it\'s like an
inference of what the data contains. Even there the entry there is
process sensor data it says contains processed version of the sensor
data and they have segregated in terms of what they found in their
survey. So I think uh we can

**Geoff Horowitz:** What what\'s wait what\'s what\'s the point?

**Ratul Shashank:** we

**Geoff Horowitz:** What\'s the point there? So they they talk about
what they\'ve done in the survey and

**Ratul Shashank:** uh so what I was saying that I think if they share
like best then

**Geoff Horowitz:** therefore

**Ratul Shashank:** best case scenario but even if they don\'t share we
can\'t use that process data for our ML segmentation we can\'t feed that
to any ML model. So it\'s uh maybe it can be used for

**Geoff Horowitz:** Correct.

**Ratul Shashank:** data preparation. I don\'t know because we don\'t
have context yet. But as far as our current uh sanding is concerned, I
don\'t think we would have any problem if we know or we don\'t what
pipeline they are using because as much as I have uh I have asked AI to
figure out how much they are if this is really any sort any sort of
processing done or uh it\'s just any it\'s just an error on our And so
it\'s um

### 00:31:26

**Ratul Shashank:** maybe we should uh I don\'t think we would have any
problem if I were to conclude I don\'t think we would have any problem
if you don\'t know the processing pipeline because we

**Pratyaksh Singh:** Can we do we have an example of side by side

**Ratul Shashank:** Uh-huh.

**Pratyaksh Singh:** what the image look like after our processing and
what the profess image look like? Is there any is there anywhere on the
slide where that image is there?

**Ratul Shashank:** Uh yes. Uh just let me Jeff can you go to slide
number five and six. Uh this is the what the processed image looks like.

**Geoff Horowitz:** Wait. So,

**Pratyaksh Singh:** This is what the process

**Ratul Shashank:** And

**Geoff Horowitz:** so this is processed that five is processed and six
is raw

**Pratyaksh Singh:** is.

**Ratul Shashank:** yeah.

**Geoff Horowitz:** for the same image.

**Ratul Shashank:** Yes. uh uh I don\'t know if if it is very apparent
in the slide but I will share the PNG the PNG that I generated but

**Pratyaksh Singh:** Uh

**Ratul Shashank:** we are not losing any context in the raw data
itself.

### 00:32:47

**Pratyaksh Singh:** oh. I I think I know what this one. I think I know
this.

**Geoff Horowitz:** I mean, it looks like just intensity normalization,

**Ratul Shashank:** uh and there is yes and as far as

**Geoff Horowitz:** doesn\'t it?

**Ratul Shashank:** we know this processing was only done for human
visual so that a human can understand what is happening. If we feed that
data to a pipeline, it won\'t uh find anything because of

**Geoff Horowitz:** I I I need one minute.

**Ratul Shashank:** normalization.

**Geoff Horowitz:** Keep talking, but I need one minute. Alberta.

**Pratyaksh Singh:** Don\'t you think like six looks better than five
for humans? You spot the difference satin.

**Ratul Shashank:** Uh it\'s just

**Pratyaksh Singh:** Can we do one thing? Yeah. Go ahead.

**Ratul Shashank:** I they\'re saying that it\'s just a difference of
contrast. I think that they are producing better contrasting image in
the pipeline. But apart from that there is no uh nothing that we can
extract of value from the processing.

**Pratyaksh Singh:** Okay. How many process file have do they have?

### 00:34:08

**Pratyaksh Singh:** Have they given us?

**Ratul Shashank:** Uh it\'s a statement.

**Pratyaksh Singh:** I think we are just sming it out.

**Ratul Shashank:** I

**Pratyaksh Singh:** This is it. The restization. Do you have just raw
watered for this image?

**Ratul Shashank:** uh robot

**Pratyaksh Singh:** The waterershed image. Water shed image for this
file. BRX av00011 SS the

**Ratul Shashank:** uh I have not generated I I I have not generated for
that one.

**Pratyaksh Singh:** file.

**Ratul Shashank:** But just let me see

**Sachin Pandey:** Correct me if I am wrong but this image also has
extra processing where we are removing the empty region.

**Ratul Shashank:** process

**Sachin Pandey:** Yeah,

**Ratul Shashank:** number.

**Sachin Pandey:** the current one. This is not the actual raw_1 file,
right?

**Ratul Shashank:** Now this is the actual_1

**Pratyaksh Singh:** Wait.

**Ratul Shashank:** waterfall

**Sachin Pandey:** So if we take the original HTF file and pass it to
HTF2 image, this will this is what we

**Ratul Shashank:** I have not tried that but

**Sachin Pandey:** get.

**Pratyaksh Singh:** So this this is what like slide five or slide

**Ratul Shashank:** yes slide

### 00:35:24

**Pratyaksh Singh:** six.

**Ratul Shashank:** five is the process one anything underscore one is
the process data and slide six is raw

**Pratyaksh Singh:** Ah undersc_1 is process I think we have images
there right sa labeling where is it 8505

**Sachin Pandey:** Yes, Let\'s

**Pratyaksh Singh:** so we should have image for that

**Sachin Pandey:** continue.

**Pratyaksh Singh:** also the underscore one is for Which file is this?
Is it in DRF?

**Ratul Shashank:** Yes.

**Pratyaksh Singh:** Okay, here you go. Which file is it? BRX A01.

**Ratul Shashank:** Uh,

**Pratyaksh Singh:** What is your final name? Can you please spell it
out? I\'ll try

**Ratul Shashank:** and this S BRX AOV 01

**Pratyaksh Singh:** it.

**Ratul Shashank:** 011 S SS 20 25 10 28 T 13

**Pratyaksh Singh:** Uh uh 813.

**Ratul Shashank:** 24

**Pratyaksh Singh:** Sorry. Sorry. T13, right?

**Ratul Shashank:** G T3

**Pratyaksh Singh:** Tight. Finding P3.

**Ratul Shashank:** One

**Pratyaksh Singh:** Wow. I can\'t find T3. 11 12 13 after that what is
it?

**Ratul Shashank:** 24 58

**Pratyaksh Singh:** P3 24 58

**Ratul Shashank:** 58 Yes.

### 00:37:16

**Pratyaksh Singh:** right?

**Ratul Shashank:** and zed.

**Pratyaksh Singh:** Okay. Nice. Uh, thank

**Ratul Shashank:** Yes.

**Pratyaksh Singh:** my screen visible. So this is XF to PNG conversion
from our pipeline right for this file prx aub001 set.png PNG and this is
with underscore one. Let\'s see if it this is with the underscore one,
right?

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** So if they process the XTF, right? Even if they
process the XTF or XTF to PNG pipeline. Yeah, that\'s right.

**Ratul Shashank:** I\'m sorry but your voice was breaking.

**Pratyaksh Singh:** But this is the kind of image that

**Ratul Shashank:** Can

**Pratyaksh Singh:** this

**Geoff Horowitz:** projects. You broke up a little bit.

**Ratul Shashank:** you

**Pratyaksh Singh:** Mhm. I was saying that even if we have the XTF, the
row XT, right? Even if we have to draw XTF uh the underscore one this is
the PNG for that XF with our uh XTF to PNG converter right and I think
that you find

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** in the file this is their converter right and

### 00:38:59

**Ratul Shashank:** I\'m sorry I\'m not able to understand your voice.
There is static in your voice.

**Pratyaksh Singh:** Uh any chance it\'s better now?

**Ratul Shashank:** Mhm. Much

**Pratyaksh Singh:** Okay.

**Ratul Shashank:** better.

**Pratyaksh Singh:** Okay. So what I was saying is that let\'s say we
have the postprocess XTF right sorry uh we have the postprocess XTF and
then on their

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** post process XTF we ran our image to PNG converter
okay uh so XTF to PNG converter sorry and this is the image that we get
right and this is the image that

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** you guys got from their XTF files, right?

**Ratul Shashank:** the process.

**Pratyaksh Singh:** Is this from some map

**Ratul Shashank:** No,

**Pratyaksh Singh:** or uh

**Ratul Shashank:** no, this is not from some app.

**Pratyaksh Singh:** where did you get this image

**Ratul Shashank:** This was just uh just like what

**Pratyaksh Singh:** from?

**Ratul Shashank:** we found uh by we we we recreated this pipeline the
HDF to PNG by studying how other images other software does just from
code.

**Pratyaksh Singh:** just from

### 00:40:31

**Ratul Shashank:** This is just from output of a code that we recreated
from DAS

**Pratyaksh Singh:** what

**Ratul Shashank:** engineering the opensource software and how everyone
how open source software does

**Sachin Pandey:** So Pat uh the gap is in the middle gap is missing
because this

**Pratyaksh Singh:** Pencil soft.

**Sachin Pandey:** is not uh accurately representing the latl long. This
is just uh aligning the ping values for areas where it didn\'t find the
ping. It is just merging

**Pratyaksh Singh:** Yeah. No. No.

**Sachin Pandey:** it.

**Pratyaksh Singh:** And it\'s not it\'s not doing slant height
correction. The gap comes because of slant height correction. I was
looking at the code today also. I was trying to understand what our XTF
to PNG conversion does. Right. And we do slant height conversion which
is which is something like I have to explain it. It\'s like your LAR is
your LAR is somewhere around here. Right. Right. Your LAR is above the
above the board and then whenever you record the signal you actually
record this this value.

### 00:41:54

**Pratyaksh Singh:** Right. And but instead we are more concerned about
this value the the horizontal the horizontal right.

**Ratul Shashank:** Yes.

**Pratyaksh Singh:** This is what what they call as slant height
correction.

**Ratul Shashank:** Yes.

**Pratyaksh Singh:** And when you do slant height correction a lot of
values I think goes to negative or zero which is represented in this
kind of pixel. So I think this is slant height correction. uh I think
this is slant height correction so it\'s not merging it and that\'s why
you see the value here is kind of skewed at that reason and another

**Ratul Shashank:** Mhm. The middle one.

**Pratyaksh Singh:** thing why huh the middle one yeah and

**Ratul Shashank:** The middle one. The middle region.

**Pratyaksh Singh:** another thing why this looks uh little

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** better might be because it doesn\'t do uh the
rasterization with resolution that our code

**Ratul Shashank:** Yeah.

**Pratyaksh Singh:** does.

**Ratul Shashank:** This is uh uh this is just basic waterfall image. So
that we are just stacking pins along with sample sizes.

**Pratyaksh Singh:** Mhm.

### 00:43:04

**Ratul Shashank:** This is just for a visualization like what is

**Pratyaksh Singh:** So, uh,

**Ratul Shashank:** happening.

**Pratyaksh Singh:** one more thing I would want to say is that we
can\'t, uh, this is really needed. This is very weird.

**Ratul Shashank:** What is

**Pratyaksh Singh:** They aren\'t doing slant correction

**Ratul Shashank:** this?

**Pratyaksh Singh:** which can you can you do you know what happens what
what\'s happening in the code that you guys made

**Ratul Shashank:** uh in this first particular instance the waterfall
that it\'s just generating is just these are the stacked up things like
it\'s just uh uh on the x-axis it\'s number of pins so on the y-axis is
the number of pings and on the x-axis it\'s just the number of samples
these are not the

**Pratyaksh Singh:** Mhm.

**Ratul Shashank:** actual uh if you are asking if it is the actual
waterfall image I wouldn\'t classify it as that. It\'s just for the sake
of visualization like I wanted to see that waterfall image with ro and
pitch. Uh that was my agenda into this PNG is not a

**Pratyaksh Singh:** Mhm.

### 00:44:35

**Ratul Shashank:** a waterfall image that we should uh consider as you
know very correct is just for understanding purpose. And there is no
rasterization done in this.

**Pratyaksh Singh:** What about SL SL at correction? Is that done here
or not? Because I\'m confused because this gap here is

**Ratul Shashank:** The middle one, right?

**Pratyaksh Singh:** confusing me.

**Ratul Shashank:** This middle one uh it is taking it is considering
the slant height

**Pratyaksh Singh:** Yeah.

**Ratul Shashank:** correction. Uh this middle gap is only appearing
because uh like it produces image for port and it produces image for
starboard. If we print that on top of each other then like they would be

**Pratyaksh Singh:** Port and starboard is so port is here right?

**Ratul Shashank:** stacking.

**Pratyaksh Singh:** Port is on top starboard is at the bottom.

**Ratul Shashank:** Yeah. So the gap

**Pratyaksh Singh:** Yeah. Even if I stack it it is it is divided by
zero

**Ratul Shashank:** is like

**Pratyaksh Singh:** right?

**Ratul Shashank:** the the gap is only apparent because we are
reversing the port to have just a understanding.

### 00:46:04

**Pratyaksh Singh:** We are reversing the port to have understanding. I
I don\'t understand what that means.

**Ratul Shashank:** uh like as I was saying this image is just for
understanding what changes the overall waterfall would have uh
corresponding to role and pitch. That was my entire uh agenda behind
this entire PNG.

**Pratyaksh Singh:** I I get what you\'re saying but the image looks
different from what we have right the image is kind of different from
what we have. So what we have here what our pipeline generates the when
our pipeline generates the image this is the image that we get and when
you use the opensource tool this is the image that you get right which
is different which is

**Ratul Shashank:** Uh yes

**Pratyaksh Singh:** different right I want to know what the difference
That\'s

**Ratul Shashank:** and then I think I uh I I will share what this code
is Because we our main concern is that line in along the zero axis right
or

**Pratyaksh Singh:** No, no, it\'s not our main. Uh see a lot of a lot
of things goes on a lot of thing goes on and from what I understood by
reading sets code is that you have two side one is your port and then
another one is your starboard right and then

### 00:47:55

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** you stack these images to create kind of an image
both for port and both, right? And these are and then what he does is is
he will he will slant correct these things and then his image will look
something like this with the gap in between and and once this is done
after slant height correction it will convert to uh you will then
rasterize this image.

**Ratul Shashank:** That\'s

**Pratyaksh Singh:** So these will be your uh yeah these are just your
raw values right.

**Ratul Shashank:** is

**Pratyaksh Singh:** So the resolution that he uses is he will do
something like this like he will take this huge chunk and for all for
all the point inside it it will uh he will compute the pixel values. He
will compute the pixel values for yeah for x and y to

**Ratul Shashank:** X and Y.

**Pratyaksh Singh:** create the image. And another thing that goes on is
that these this log transformation and minmax scaling because the beam
range here the beam ranges from 0 to 2\^ 16 I think to no the beam the
ping values range

### 00:49:07

**Ratul Shashank:** 255.

**Pratyaksh Singh:** from 0 to 2\^ 16

**Ratul Shashank:** Oh yeah, that is send values are only from 0 to

**Pratyaksh Singh:** right uh yeah I think

**Ratul Shashank:** 355.

**Pratyaksh Singh:** it is not even 16 it is 2\^ 32 something like And
then he takes a log of these ping values to have to get them to

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** a manual. Then he will convert it to the power. So
and any processing pipeline will have to do this so that they will they
can you know because you can\'t visualize the color range 2 to the power
32 or 6 32 right. This is where things differ, right? These conversion
differ. So I think I think we should be mindful of these things.

**Ratul Shashank:** uh I don\'t think then the image that was generated
it\'s slant height it\'s undergoing slant height correctly I guess just
taking But

**Pratyaksh Singh:** So this is why I\'m confused, right? If it\'s not
going slight correction then why is this gap here? Are there no values
here?

**Ratul Shashank:** uh

### 00:50:27

**Pratyaksh Singh:** If there are no values here then imputing it here.
And because when we do slant height correction we get an empty space
here right? Give me an empty space. See we get an empty space here.
Thank

**Ratul Shashank:** Isn\'t that just Isn\'t that gap just a native zone?
Because of the shadow,

**Pratyaksh Singh:** you.

**Ratul Shashank:** it\'s creating a shadow zone. If that gap is a
native zone, right? If we don\'t correct that native zone, the shadows
will be will appear in the image. No needle n a di.

**Pratyaksh Singh:** What does that

**Ratul Shashank:** So needle zone is basically just the area that is
present

**Pratyaksh Singh:** mean?

**Ratul Shashank:** perpendicular beneath the perpendicular beneath the
vehicle. So when the sensor the sensor they are uh throwing the beams at
an angle right or perpendicular surface. So when they throw the beam at
an angle they the area

**Pratyaksh Singh:** Mhm.

**Ratul Shashank:** that is just beneath the vehicle it does not get
illuminated very well. So,

**Pratyaksh Singh:** I think it corrects for that.

### 00:52:01

**Pratyaksh Singh:** He has weights zero for areas that are in this of

**Ratul Shashank:** so

**Pratyaksh Singh:** NATO.

**Ratul Shashank:** yes and the image is not doing

**Pratyaksh Singh:** I saw it I think in a script somewhere near.

**Ratul Shashank:** that.

**Pratyaksh Singh:** Yeah, this n range 10 m I

**Ratul Shashank:** Yes, range is 10. Yes, it\'s about 10 m.

**Pratyaksh Singh:** think

**Ratul Shashank:** So that is the image is not uh correcting the needed
zone. That is what I uh it is just showing a basic waterfall image and
even the bright line that is going along that is the path the AOV is
following.

**Pratyaksh Singh:** And this one looks better because you know these
contacts are maybe more visual.

**Ratul Shashank:** Yeah, this is the process.

**Pratyaksh Singh:** Is this a contact? Is this the contact?

**Ratul Shashank:** Uh,

**Pratyaksh Singh:** Is this a contact?

**Ratul Shashank:** which one are you pointing at?

**Pratyaksh Singh:** Oh yeah,

**Ratul Shashank:** Something.

**Pratyaksh Singh:** sorry. I will just draw a shape. I was pointing it
this

**Ratul Shashank:** Oh, yes. Yeah, this is uh uh I there is

### 00:53:11

**Pratyaksh Singh:** way.

**Ratul Shashank:** something there.

**Pratyaksh Singh:** Can we use this tool? The tool that you are using
right now. So I think can we use these to look at hands image too entx
image which are kind of weird and uh and also the mines image where they
have marked the mind to see if you know the mines are visible in this
image is Jeff on the meeting Jeff do they use this uh do

**Geoff Horowitz:** Yeah, I\'m still on.

**Pratyaksh Singh:** they use this pre-processed image for their manual
labeling or do they use the raw

**Geoff Horowitz:** Do they use the processed

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** image?

**Pratyaksh Singh:** Do they use the process image for the manual
labeling or do they use the raw one?

**Geoff Horowitz:** I don\'t think she mentioned one way or the other,
but I would assume that they use the processed image.

**Pratyaksh Singh:** See guys, uh we need to decide on one thing.

**Geoff Horowitz:** But Protex just just to be clear protection they
don\'t they also don\'t

**Pratyaksh Singh:** Uh-huh.

**Geoff Horowitz:** they also don\'t just use the images right they also
use the mag data they may also use the side

### 00:54:39

**Pratyaksh Singh:** Did you

**Geoff Horowitz:** scan I\'m sorry I\'m sorry they might they may also
use the um the uh the um the point cloud data they may also use the
point the multi-beam point cloud data right So they they they probably
use more things than just the images was my

**Pratyaksh Singh:** Got it.

**Geoff Horowitz:** point.

**Pratyaksh Singh:** See uh I think we are stuck in this thing here,
right? We want to go from XTF to image and we aren\'t able to uh to find
one pipeline and stick with it at least for XTF to XTF to the XTF to
image conversion. Let\'s have as less pro processing there as possible.
I don\'t like the restization one and that\'s why like one of the thing
in today that I wanted to discuss was these things one thing was that uh
these gaps that you guys see right uh so I

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** looked at sid code and gio references these things
but I don\'t think I don\'t know if that is required for our case
because what we can do is we can get the model prediction and Then you
know we can use rest of his pipeline to convert the prediction to to
convert the prediction to to the geo reference that we

### 00:56:19

**Ratul Shashank:** Uh that is also uh I had a similar question that I
asked

**Pratyaksh Singh:** have.

**Ratul Shashank:** Sachin like what are we using? What uh what type of
annotations are we using like JSON or we are just using PNGs to annotate
including them? Because if we are just using the PNGs uh or rasterized
images, I think any waterfall image uh with no

**Pratyaksh Singh:** Yeah.

**Ratul Shashank:** processing just uh plain printing of the pixel it

**Pratyaksh Singh:** Mhm.

**Ratul Shashank:** would be it it would just it would produce the same
results. But I wanted to ask you guys

**Pratyaksh Singh:** I agree with you there. I agree with you there. I
don\'t want to do a very large processing there the rasterization and
all these things. I want to keep it simple where you just interpolate
whatever gaps that you the data that is present instead of rasterizing
to remove the gap. And then another thing that I wanted to remove was
these gap between the image because I think we

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** are waste model compute and creating problem for
ourself with these gaps because for some images these gaps are pretty
big while for some images these gaps are pretty small.

### 00:57:49

**Pratyaksh Singh:** So I I don\'t know if we should do this or not
because Jeff uh we need to share the results to them in the geo
reference format, right?

**Geoff Horowitz:** Correct.

**Pratyaksh Singh:** So we\'ll have to confirm it. I think uh let\'s get
initial iteration on the raw images initial iteration on the raw images
with the pipeline we already have that we know works and then we can try
these things out where we remove you know we just work with the raw
motor image or

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** we modify the XTFs to enhance the quality so the
kinding steps that they

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** You can use something similar as as other
iterations for this. breathing.

**Ratul Shashank:** Sorry, your voice has a lot of static

**Pratyaksh Singh:** I was saying that I was saying that the previous
pipeline that we had, right? Hello.

**Ratul Shashank:** the XT up to PNG one.

**Pratyaksh Singh:** Yeah. the XT up to PNG one the previous pipeline
that we had we know it is working because we gave them we gave them the
final results and they were good with it is that correct

### 00:59:21

**Geoff Horowitz:** Uh-huh.

**Pratyaksh Singh:** Jeff so and I think the labels are

**Geoff Horowitz:** Yes.

**Pratyaksh Singh:** labeling using those images only so for the first
iteration let\'s just go ahead with that and then we can try out these
things for enhancing the XTFS or remove the off net correction or or
these slant height corrections that we are using and then we can see if
we can convert those final prediction back to the georreerence format

**Ratul Shashank:** Yeah. Yes.

**Pratyaksh Singh:** that they needed.

**Ratul Shashank:** And and regarding the major region like we as much
as we what we can do we can\'t do much in that area because there is
simply no data in there. So it\'s no use uh trying to solve that
problem. So we uh what we can

**Pratyaksh Singh:** Mhm.

**Ratul Shashank:** do uh I I will I will coordinate with this with you
uh in future like I have an idea like if if I don\'t know if this works
or not like I will give you a rough idea uh if we take just board and
starboard separately and uh feed our pipeline not on

### 01:00:48

**Pratyaksh Singh:** Mhm.

**Ratul Shashank:** the entire uh not on the entire range but uh port
separately and

**Pratyaksh Singh:** Mhm.

**Ratul Shashank:** starboard separately. So I don\'t know but I think
we can I think it would be of use but that\'s for future.

**Pratyaksh Singh:** Yeah. I agree with I want to do that. Uh so the
back region that I was asking to remove because the gap that it\'s that
it creates right if you\'ll have port and starboard separate you can
stack them side by

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** side as one combined in and then you can train your
model with it and you can forget the model confusing gap in between.

**Ratul Shashank:** Exactly.

**Pratyaksh Singh:** So that\'s a good idea but uh but I think the
problem might come with geo referencing things. So we should have that
in mind and we should process according to that only we should proceed
according according to

**Ratul Shashank:** Yes,

**Pratyaksh Singh:** that.

**Ratul Shashank:** definitely.

**Pratyaksh Singh:** Anyways, can you guys just do one thing? If images
look better in the tool that you have downloaded, can you check for our
worst data which is the ants one?

### 01:02:06

**Pratyaksh Singh:** How does ants look? And if we are able to find
mines in the images with the tool that you guys with the open source
tool that you guys were

**Ratul Shashank:** Uh and just for clarification without any
enhancement,

**Pratyaksh Singh:** using

**Ratul Shashank:** right?

**Pratyaksh Singh:** without any enhancement. Yeah. first without any
enhancement then you can try you know just ask GPT for uh for lowass
filter on XTFS XTF pings it will give you an script run that script and
I think you will get what they were

**Ratul Shashank:** Uh I tried one uh approach like what it did it

**Pratyaksh Singh:** using

**Ratul Shashank:** just illuminates the shadows uh like it increases
the pixel of the shadow region and uh so it

**Pratyaksh Singh:** What? What do you mean by shadow

**Ratul Shashank:** a shadow region like any area which is less in pixel

**Pratyaksh Singh:** region?

**Ratul Shashank:** let\'s which is darker on the entire image. So what
it does is just bas it creates a normalized image. So it is very uh it
is apparent to eyes.

**Pratyaksh Singh:** Huh?

### 01:03:19

**Ratul Shashank:** I don\'t know if it is good for feeding any ML
algorithm but I will uh I what I will do is I will create a folder for
such

**Pratyaksh Singh:** Uh

**Ratul Shashank:** images. uh and we can just check if it it is of any
use. If it\'s not then we can just grab their

**Pratyaksh Singh:** got it. I will suggest try out uh different
algorithm create a dock with things and one thing that I will also

**Ratul Shashank:** ID.

**Pratyaksh Singh:** suggest is that whatever algorithm that you try it
on at least eight or nine images right at least 10 images and from all
the data sets right it shouldn\'t be on just one images from one data
set try it for all the data set that they gave us like POE DRN and VW
everything try it on you know two three images from each of the data
set. So you know that you know it enhances predictably in all the cases
does it make

**Ratul Shashank:** Yes,

**Pratyaksh Singh:** sense and uh if you are

**Ratul Shashank:** it does. You would have context.

### 01:04:24

**Pratyaksh Singh:** yeah and if you are going to try pre-processing
things I will suggest you know maintain a doc what algorithm you tried
out maintain a doc and share it in the group so that if anyone else also
wants to try something they can they can you know see your result and
decide like which algorithms.

**Ratul Shashank:** Yes, I will I will do that. It\'s even better if I
will uh if anyone can explore that.

**Pratyaksh Singh:** Okay. Yeah. But first first of all I will suggest
you know just just confirm that if ants data and mines are more visible
in the in the non-rasterized image or in the tool that you guys are
using the open source tool that you guys are using.

**Ratul Shashank:** Yes, I will I will confirm

**Pratyaksh Singh:** Okay,

**Ratul Shashank:** that.

**Pratyaksh Singh:** Japan. There is no chance that they will give us uh
images instead of XDFs, right? I think it would be stupid to ask now
also, right?

**Geoff Horowitz:** Um, you mean as inputs?

**Pratyaksh Singh:** As inputs. Yes, because a lot of work is going on
there only.

### 01:05:49

**Geoff Horowitz:** I can confirm with them. Um,

**Pratyaksh Singh:** Mhm.

**Geoff Horowitz:** hold on. Let me think about this. Give me just one
second. I will confirm with them. I think I think they they did not want
to feed in images. They wanted to feed in XDFs. But I I will confirm
with them.

**Pratyaksh Singh:** All right.

**Geoff Horowitz:** Um

**Pratyaksh Singh:** Okay. If it\'s like it\'s XTF, it\'s fine. I wanted
images because uh you know it looks like a lot of our work is going here
only converting XTFs to images.

**Geoff Horowitz:** I understand. Um,

**Pratyaksh Singh:** I didn\'t know it was that big of a problem because
previously said just it just converted it

**Geoff Horowitz:** he just did it,

**Pratyaksh Singh:** and yeah I just I just trained the model

**Geoff Horowitz:** right? But but I guess I also don\'t and maybe sorry
if I missed this during the

**Pratyaksh Singh:** on

**Geoff Horowitz:** conversation. They gave us their XTF to PNG
conversion script.

**Pratyaksh Singh:** Uhhuh.

**Geoff Horowitz:** Why why are we having trouble just using it

### 01:07:16

**Pratyaksh Singh:** I don\'t know.

**Geoff Horowitz:** directly?

**Pratyaksh Singh:** I don\'t know. I I\'ll have to ask that how much is
incorporated there because I don\'t think it\'s completely their script
because they aren\'t using pixf. We are using pix. I don\'t think they
are using py xtf. Oh,

**Geoff Horowitz:** Okay.

**Pratyaksh Singh:** they didn\'t give us the complete script.

**Geoff Horowitz:** I I uh I you know added you got they did not give us
the complete script. Is that what you said?

**Pratyaksh Singh:** H because they are using a sensor processing module
that we don\'t have. It would be stupid if sensor processing is let me
see if it\'s a pi module. Yeah, we should explore it. I think Jeff. Uh,
yeah, you are correct. You are correct there if they gave us their
script, we should we should stick with

**Geoff Horowitz:** I mean,

**Pratyaksh Singh:** it.

**Geoff Horowitz:** you know, if we did this in in the first phase, I\'d
be fine going back to them and being like, \"Hey, you know, you gave us
this script and it had this other this other library that we didn\'t
have access to.\" I\'d feel pretty stupid doing

### 01:08:34

**Geoff Horowitz:** that now, you know.

**Pratyaksh Singh:** Yeah. Yeah.

**Geoff Horowitz:** Um,

**Pratyaksh Singh:** I I agree with you.

**Geoff Horowitz:** so

**Pratyaksh Singh:** I I I understand what you\'re saying.

**Geoff Horowitz:** okay. Um, oh,

**Pratyaksh Singh:** I I think AI

**Geoff Horowitz:** sorry. Go ahead. Part two.

**Pratyaksh Singh:** can fill the missing gaps. Fill the gaps.

**Geoff Horowitz:** Figure this out. Yeah, it also I\'m just looking at
it briefly.

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** It looks like a lot of these might just be kind of
generic imports. suppose um validating a

**Pratyaksh Singh:** Uh-huh. Yeah. So this no no so sensor processing I
think it is their internal

**Geoff Horowitz:** list.

**Pratyaksh Singh:** module from sensor processing.com.pose pose and
port

**Geoff Horowitz:** Uhhuh.

**Pratyaksh Singh:** pose right

**Geoff Horowitz:** Yeah. Yeah, that\'s what I\'m looking at,

**Pratyaksh Singh:** that yeah and that I don\'t think they gave us also

**Geoff Horowitz:** too.

**Pratyaksh Singh:** meter per second to knots these we

**Geoff Horowitz:** Why didn\'t S tell me that I didn\'t have this

**Pratyaksh Singh:** can

### 01:09:31

**Geoff Horowitz:** s\*\*\*. Okay, whatever. It\'s not a big deal.

**Pratyaksh Singh:** send

**Geoff Horowitz:** Um, okay. I want to finish going through these to
make sure that I have all the appropriate questions. This I don\'t have
questions about anymore. Um, Rul, I noticed that you this questions I
noticed that you mentioned you found the role data. Is that

**Ratul Shashank:** It\'s it\'s I think it\'s in slide 13.

**Geoff Horowitz:** right

**Ratul Shashank:** This slide is talking about the MAG data.

**Geoff Horowitz:** or yeah if you see the RO data which is simple
extraction from the ping headers. So we we have the AUV

**Ratul Shashank:** Uh so what I did was I just

**Geoff Horowitz:** roll.

**Ratul Shashank:** used I just extracted the role value from the ping
headers and when I and I plotted them on a graph. Uh I tried to
correlate them with what is showing in this

**Geoff Horowitz:** Oh, but there was no correlation is what you\'re

**Ratul Shashank:** image. Uh I think Sorry,

**Geoff Horowitz:** saying.

**Pratyaksh Singh:** Yeah, I Hey,

### 01:11:01

**Ratul Shashank:** sorry. Go ahead.

**Pratyaksh Singh:** sorry. Sorry to cut off. I didn\'t I was just
saying

**Ratul Shashank:** Uh I was saying that I think

**Pratyaksh Singh:** that.

**Ratul Shashank:** they

**Geoff Horowitz:** Rel, finish your thought and then project will go
next.

**Pratyaksh Singh:** Yeah.

**Ratul Shashank:** Yeah, I was saying that I think they are using some
threshold for the role values that

**Geoff Horowitz:** I\'ll I\'ll I\'ll ask her. I\'ll tell her that we
prefer that it\'s a a separate input.

**Ratul Shashank:** Mhm. Uh and regarding the blue triangle uh that they
have

**Geoff Horowitz:** Um

**Ratul Shashank:** plot uh we have I have not found any

**Geoff Horowitz:** Mhm.

**Ratul Shashank:** inference like what they are doing.

**Geoff Horowitz:** I I\'m I\'m I\'m going to ask her about that
separately. I\'m just going to ask her.

**Ratul Shashank:** Yes.

**Geoff Horowitz:** She did mention to us that on the bottom these red
dots were areas of role. I\'m assuming actually that it\'s the same on
top, but that it\'s, you know, just port versus starboard. That\'s
that\'s my assumption, but I I\'m going to ask her explicitly.

### 01:12:03

**Ratul Shashank:** Yes.

**Geoff Horowitz:** Um,

**Ratul Shashank:** So they had uh uh they had an HTML report as well in
their f in the data sets in their reports. uh so I tried to look as much
as I could like feeding the HTML file and the images to AI and asked it
to correlate as much as it could. So if you can see in the slide 14 a
even AI can\'t find a solid inference like what they actually mean but
for the red dots it is saying that it\'s some sort of error so I think
that could be wrong but for blue it\'s we don\'t know

**Geoff Horowitz:** Okay.

**Ratul Shashank:** that.

**Geoff Horowitz:** Well, I\'ll I\'ll ask her anyway. So,

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** um, projects, what were we saying? Project.

**Pratyaksh Singh:** Hey uh yeah I looked at you know I looked at what
role

**Geoff Horowitz:** Yeah.

**Pratyaksh Singh:** is right it\'s just that you know uh from what I
found out it doesn\'t have any that much effect on on the image that you

**Geoff Horowitz:** Well,

**Pratyaksh Singh:** get

### 01:13:24

**Geoff Horowitz:** it it does. Um,

**Pratyaksh Singh:** uh

**Geoff Horowitz:** I\'ll show you.

**Ratul Shashank:** Well,

**Geoff Horowitz:** I mean,

**Ratul Shashank:** if Oh,

**Geoff Horowitz:** this this was just according to Bridget. Um,

**Ratul Shashank:** boy.

**Geoff Horowitz:** oh, can you can you guys hear me?

**Pratyaksh Singh:** Okay.

**Ratul Shashank:** Yes.

**Geoff Horowitz:** Uh that see each of these each of these are kind of
areas of role or significant role and they\'re generating these um these
ripple features in the data in the sides scan data

**Pratyaksh Singh:** Damn.

**Ratul Shashank:** Your role affects the pin values, right?

**Geoff Horowitz:** because and I mean actually it makes sense right
because uh I see oh you know because like if the how do I draw this I
don\'t know a good way to draw this but like um uh what\'s a good way to
draw this like maybe like this right and so you know oh sorry right so
if if your AUV is looking this way right then then you you know you have
a a solid um kind of cone of of view, right? Field of view.

### 01:14:41

**Geoff Horowitz:** But if you\'re if you\'re rotated, right,

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** then your field of view is going to is going to
rotate as well. So I can imagine that it ends up kind of, you know,
creating this zigzag effect, right? So I mean, at least to me it makes
sense.

**Ratul Shashank:** Yes.

**Geoff Horowitz:** I I I\'m I guess I\'m interested in how you how you
came up with

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** that. There\'s not a

**Pratyaksh Singh:** I mean I looked at three

**Geoff Horowitz:** significant.

**Pratyaksh Singh:** four XTF to image conversion and none of them
consider consider role you know none of none of people do rule

**Geoff Horowitz:** Huh?

**Pratyaksh Singh:** correction because I think you can correct for it
right if you know how much your board had or your sensor has rotated
Maybe you can correct for it. I\'m not sure. But you know, nowhere
nowhere it

**Geoff Horowitz:** But you can\'t you can\'t like fill in the missing
area, right?

**Pratyaksh Singh:** is.

**Geoff Horowitz:** like like I think maybe what you\'re saying is like
okay well you could better align these you know instead of kind of
zigzagging like this you could better align these but then you would
have gaps on the other side of the data um project I\'m not sure this is
true I\'m just this kind of makes sense in my head right you would have
gaps on on the uncorrected

### 01:16:04

**Pratyaksh Singh:** I get the same

**Geoff Horowitz:** side um and I think I think Bridget\'s I think
Bridget\'s point is not that like because if they could correct it then
this wouldn\'t even be an issue but rather

**Pratyaksh Singh:** and

**Geoff Horowitz:** that our model doesn\'t look at this and say and say
oh these are these are contacts because you know they don\'t look like
seabed so rather that that we we\'re able to train on these points maybe
with additional input about about the AUV role and say oh yeah we can
this is not a contact we know that this is CBED does that make any sense

**Pratyaksh Singh:** That makes sense. Dish uh let\'s share us some data
for the role

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** I believe the

**Pratyaksh Singh:** also

**Geoff Horowitz:** uh uh this is mag I I I think she said one of the
data sets has a lot of role in it but if that\'s not true then we should
Ask her for

**Ratul Shashank:** as as much as I have looked any folder that contains

**Geoff Horowitz:** it.

**Ratul Shashank:** uh mag-cal-1 any data set that is in that folder has
uh a significant role and disturbance.

### 01:17:30

**Ratul Shashank:** So what what AI what AI found that it is that

**Geoff Horowitz:** Okay.

**Ratul Shashank:** path the AOV is basically correcting its course. So
it is uh

**Geoff Horowitz:** Hold on.

**Ratul Shashank:** uh

**Geoff Horowitz:** Rul, which which data set was that a part of? DRN.

**Ratul Shashank:** DRN.

**Geoff Horowitz:** Okay, this one. All right, fine. So So basically
what you\'re saying is the DRN data set has a lot of role.

**Ratul Shashank:** No in the in the DRN data set the the folder is
divided into two types. One is lawn one and the other type is mag cal 1.
So the mag cal one folder which is basically I think it is three or four
xtfs. Those files have significant role compared to the lawn one lawn
one xtfs. So the logic behind that was the mag cal uh the what the data
generated during the mag cal session was the AOV was calibrating its
sensor for next path. I think that is why because of all those movements
it is creating decent amount of roll.

### 01:18:54

**Geoff Horowitz:** Okay. But but right so so this data set has examples
of ro is that right?

**Ratul Shashank:** Yes.

**Geoff Horowitz:** Okay.

**Ratul Shashank:** Yes.

**Geoff Horowitz:** All right. in the raw folder or

**Pratyaksh Singh:** Four files.

**Ratul Shashank:** Yes.

**Pratyaksh Singh:** They said four files,

**Ratul Shashank:** Yes. Just just a few more.

**Geoff Horowitz:** files.

**Pratyaksh Singh:** right?

**Ratul Shashank:** Not more.

**Geoff Horowitz:** Okay, fine. I will ask I\'ll ask Bridget

**Pratyaksh Singh:** Uh

**Geoff Horowitz:** um

**Pratyaksh Singh:** Hey Jeff, is there any place where all the issues
that they want us to solve written

**Geoff Horowitz:** is there a place with all the issues?

**Pratyaksh Singh:** down?

**Geoff Horowitz:** Um these are these are the ones that she brought up.

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** Uh these are Oh, hold on. These are the ones that
she brought up. You you know which document this is? You need me to send
the link this background document. Can I share? Send the link. Anyway,
so these are the issues that she brought up is um basically training on
more data, right?

### 01:20:01

**Geoff Horowitz:** To incorporate the new data sets, incorporate the
new contact types. Uh so these are mines. These are UXOs which were not
in the vineyard winds data set. Um seabed so getting better at seabed
dredge bottoms um was the big one that she pointed out. Um being able to
identify role as as not a contact.

**Pratyaksh Singh:** Okay.

**Geoff Horowitz:** And so those those are the main issues.

**Pratyaksh Singh:** On

**Geoff Horowitz:** And then we also talked about we also she she knows
that there\'s limited amount of data.

**Pratyaksh Singh:** it.

**Geoff Horowitz:** So we talked about using synthetic data and we
talked about the mag integration.

**Pratyaksh Singh:** Got it. Okay. I think uh role will have to generate
synthetically if there if she gave us only four files for bridg in

**Geoff Horowitz:** I I have to imagine I will ask her more.

**Pratyaksh Singh:** water.

**Geoff Horowitz:** I will ask her about the role because I have to
imagine that they have more examples of role even if it\'s from a
different data set. Yeah.

**Pratyaksh Singh:** That\'s it.

### 01:21:15

**Geoff Horowitz:** But I I\'ll ask her about

**Pratyaksh Singh:** All

**Geoff Horowitz:** that.

**Pratyaksh Singh:** right.

**Geoff Horowitz:** Did you have other things you wanted to say about
that?

**Pratyaksh Singh:** No, that\'s

**Geoff Horowitz:** All right.

**Pratyaksh Singh:** it.

**Geoff Horowitz:** Um, wait. So, Sachin, I mean, do we if we don\'t
need the elevation map, I\'d rather not ask her for it. But if you think
we need it, then I\'ll ask her.

**Sachin Pandey:** Oh, like the script for getting elevation

**Geoff Horowitz:** Yeah. Yes.

**Sachin Pandey:** or

**Geoff Horowitz:** The script for getting elevation.

**Sachin Pandey:** getting elevation if they\'re doing it from S7K then
it will be helpful with other client as well because we are struggling
with the like the tilt in the

**Geoff Horowitz:** I I I understand.

**Sachin Pandey:** out

**Geoff Horowitz:** I think that\'s exactly why if I ask for it and
Bridget says, \"Why do you need it?\" then suddenly I have to defend it.
Does this make sense?

**Sachin Pandey:** Yes,

**Geoff Horowitz:** So,

**Sachin Pandey:** Zul was using some altitude. Can we just give some
example for those?

### 01:22:45

**Sachin Pandey:** Do you you have some like images where the altitude
was reflecting

**Geoff Horowitz:** So,

**Sachin Pandey:** something?

**Ratul Shashank:** like the ones I shared with you uh on the

**Sachin Pandey:** You

**Ratul Shashank:** start that uh that is in uh that was not exactly
MBEs.

**Sachin Pandey:** guys

**Ratul Shashank:** So I but because map data was not making any sense.
So I just tried looking at the rate altitude changes. So that was not
MBES.

**Sachin Pandey:** like we just need some excuse to get the elevation
data.

**Ratul Shashank:** I will share a few photos.

**Pratyaksh Singh:** I mean are we going to incorporate it that\'s out
of scope for this right?

**Geoff Horowitz:** All right, Son, I\'ll I\'ll think about it. I\'ll
think if I can come up with a way to to ask her, but it\'s not it\'s not
critical for Bedrock. Is that right?

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Okay,

**Sachin Pandey:** Uh yeah, there\'s one more thing.

**Geoff Horowitz:** don\'t forget Sachin.

**Sachin Pandey:** I I

**Geoff Horowitz:** They they they might be using like,

**Sachin Pandey:** was

**Geoff Horowitz:** you know, Caris or QPS or one of these other guys.

### 01:24:05

**Sachin Pandey:** Yeah, there is a chance because some of the MG MBS
files have the last file as

**Geoff Horowitz:** Yeah. Yeah. Yeah.

**Sachin Pandey:** well.

**Geoff Horowitz:** Which is Yeah. because we we know these onboard
reports get processed after they get processed offline. They do not get
processed on the on the AUV. So, okay.

**Sachin Pandey:** Okay.

**Geoff Horowitz:** Um and then for the mag data, I will try to set up
some time to go over this with her. He here\'s here\'s what\'s going on,
guys,

**Sachin Pandey:** Thanks.

**Geoff Horowitz:** with the mag data. What\'s going on with the mag
data is we don\'t want to give up IP, right? We want to keep the IP. And
so the more that they share with us,

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** the less IP we get to keep. Does this make any
sense?

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** Um, so that\'s why we\'re to specifically for the
MAG data, we\'re trying to see what of this we can do ourselves. If we
can\'t do it ourselves, you know, we we\'d rather be able to do it than
than keep the IP for it.

### 01:25:21

**Geoff Horowitz:** Um, that\'s that\'s where this discussion is coming
from. So okay that said I guess Rul we we we really don\'t see any clear
connection there\'s no contacts here right there\'s no contact so like
do we have an example of contacts with the mag data

**Ratul Shashank:** Uh as far as I have used we can\'t unless the point
of contact is really big like with the VW data sets map data is pretty
much use useless because we the background noise itself uh it\'s much
it\'s not we can\'t segregate that

**Geoff Horowitz:** Mhm.

**Ratul Shashank:** so that is why I I asked you if they are using some
sort of threshold or if for to make sense of for the mag data

**Geoff Horowitz:** Understood. So, so we need to we we\'re going to
need to meet with her if she wants us to incorporate the mag data.
We\'re going to need to meet with her to understand how they\'re using
the mag data to identify contacts.

**Ratul Shashank:** And if I if I were to share what I found and I think
that they are doing uh if you look at the values for the map data like
these are astronomical 3

### 01:26:46

**Geoff Horowitz:** Mhm.

**Ratul Shashank:** uh 30,000 nanotes uh what we found what was uh in
was very the region of interest were barely around 500 and even 500
Teslas were uh a lot. So I think they are just segreg uh they are not
segregating using the MAC data just looking at how the amplitude changes
along that log. I think I I I don\'t know for sure because these data
the these numbers don\'t make any

**Geoff Horowitz:** Mhm.

**Ratul Shashank:** sense.

**Geoff Horowitz:** Uh, I hear you. I don\'t I don\'t know one way or
the other. It sounds like we\'ll need to meet with her to go over this.

**Ratul Shashank:** Mhm. And I wanted to ask one question like if uh we
were if I were to ask only spec uh for specific to presser what is our
expectations with mag data like what do we uh need to incorporate?

**Geoff Horowitz:** What do we need to incorporate?

**Ratul Shashank:** Mhm. Like we uh like with the XTFs we know that we
we for visual uh appeal we know that XTF is used but for the for map
data what are we looking for?

### 01:28:30

**Geoff Horowitz:** We we don\'t know we I mean that that was the
question you know if there was a clear correlation

**Ratul Shashank:** Uh

**Geoff Horowitz:** with you know a a spike right a spike in the mag
data and that

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** correlated to a context and we knew what we were
looking for. This is this is am I understanding your question Rel? Yeah.
So, so I\'m saying we we need to we\'re going to need to meet with
Bridget and see how they

**Ratul Shashank:** Yes.

**Geoff Horowitz:** um how they analyze their data then.

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** Okay. Fine. All right. Is that all the open
questions?

**Ratul Shashank:** Well, I think we

**Sachin Pandey:** Uh I have one if you see the image I

**Geoff Horowitz:** Yeah. What\'s

**Ratul Shashank:** have

**Geoff Horowitz:** up?

**Sachin Pandey:** shared the lines are the the OP obj path the actual
value of the MAC data and all the background is the tips and I\'m not
sure like if they don\'t have the data for

**Geoff Horowitz:** Yeah.

**Sachin Pandey:** it how are they generating these backgrounds And the
difference is very small like uh like 0.25 nanotesla like plus and minus
minus will be the red region and plus will be the blue

### 01:30:00

**Geoff Horowitz:** and and that\'s a contact,

**Sachin Pandey:** region.

**Geoff Horowitz:** right?

**Sachin Pandey:** Contact is like not even on the line on the mag data
line. It is a little bit off. If you zoom

**Geoff Horowitz:** I mean, look, to me, to me,

**Sachin Pandey:** in

**Geoff Horowitz:** there\'s a clear, you know,

**Sachin Pandey:** but yeah but we don\'t know

**Geoff Horowitz:** there\'s a clear dipole here, right?

**Sachin Pandey:** how they are getting these scripts. If you see just
the OBJ file the OBJ lines you can\'t tell anything.

**Geoff Horowitz:** These lines, you\'re saying these lines are all that
we have.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** You don\'t know how they\'re generating the stuff in
between.

**Sachin Pandey:** Yes. Yes.

**Geoff Horowitz:** Okay. I mean, I don\'t I don\'t have a good answer.
Um, yeah. I mean, I I don\'t have a good answer.

**Sachin Pandey:** Do you also need the file name for this? Yes,
exactly.

**Geoff Horowitz:** I I I can\'t ask her in email how she\'s generating.
I I it\'s we we would need to meet with her about the mag data.

### 01:31:26

**Sachin Pandey:** Yeah, like uh when we will be meeting for about mag
data then we can use it because if if

**Geoff Horowitz:** Yeah.

**Sachin Pandey:** the mag data is not even overlapping with the the AOI
and how they are like identifying it.

**Geoff Horowitz:** I bet you we\'re processing something incorrectly.

**Sachin Pandey:** No. Uh I\'m just looking at their website.

**Geoff Horowitz:** That\'s my second

**Sachin Pandey:** I\'m not like checking our pipeline. Yeah,

**Geoff Horowitz:** mosaic.

**Sachin Pandey:** just looking at the website uh and seeing the data.

**Geoff Horowitz:** I don\'t I don\'t know. Okay. Any other

**Sachin Pandey:** like there were four more three more contacts you
want me to uh look into it I can just get some slides for those as well.

**Geoff Horowitz:** Sa did we did we um were we able to map all 15
contacts onto the XDFs now?

**Sachin Pandey:** Uh for this file we found actually I like there were
in the save file there were only four contacts. I found a lot more in
the PDF because it was just a coordinate. So I used the latl longlong to
like plot the points and uh using the bounding box of the all xtf figure
out which points lies in which.

### 01:33:05

**Sachin Pandey:** So out of like around 10 only six have the one which
are ly lying in inside any of the xdf and yeah these are like spread
between quarter of 35s.

**Geoff Horowitz:** Hold on. The Danish Royal Navy had, according to
Bridget, had had 10 contacts,

**Sachin Pandey:** like

**Geoff Horowitz:** right? And you\'re saying of those 10 contacts, you
were only able to find six.

**Sachin Pandey:** yes.

**Geoff Horowitz:** So you\'re

**Sachin Pandey:** Yeah, we have the coordinates but they were not
overlapping with any of the

**Geoff Horowitz:** saying

**Sachin Pandey:** XTFs.

**Geoff Horowitz:** how is that possible?

**Sachin Pandey:** Like even on the website I saw only six. Four were of
blue color and two were of different color. I can just cross check it.

**Geoff Horowitz:** Can you can you give me a screenshot of Mosaic,
please?

**Sachin Pandey:** Yeah. You want all the right?

**Geoff Horowitz:** Say what?

**Sachin Pandey:** Uh they have annotations annotations of the area in
NTX data

**Geoff Horowitz:** No,

**Sachin Pandey:** set.

**Geoff Horowitz:** I I want a screenshot of the mosaic of the mosaic
screen that shows that shows the six contacts instead of 10. Is that
clear or no?

### 01:34:51

**Geoff Horowitz:** Are you you\'re already in Mosaic?

**Sachin Pandey:** in their website. Yeah. Uh sorry, I only see four
here. I can just share the images. Actually the the save file here it
also contain only four points.

**Geoff Horowitz:** I thought you said

**Sachin Pandey:** I can just share it.

**Geoff Horowitz:** six.

**Sachin Pandey:** See like I found the other two in in the PDF. It was
not present in the in the save file that pasted. I remember I saw more

**Geoff Horowitz:** Such a

**Sachin Pandey:** Uh it\'s uh sending I\'ve shared

**Geoff Horowitz:** this is this is mosaic right?

**Sachin Pandey:** it.

**Geoff Horowitz:** This is mosaic. Can you see my screen?

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Okay. So I see 1 2 3 4 5 6 7.

**Sachin Pandey:** This is

**Geoff Horowitz:** Are you trying? Uhhuh.

**Sachin Pandey:** intense.

**Geoff Horowitz:** This is ENT. Yes. Okay. Uh I\'m I\'m sorry. I\'m
sorry. No. No. This is Danish Royal Navy. Sorry. Okay.

### 01:36:28

**Geoff Horowitz:** Danish Royal Navy.

**Sachin Pandey:** Oh yeah.

**Geoff Horowitz:** So these these are all the contacts and they look to
me like they\'re they do overlay some some areas I

**Sachin Pandey:** Anybody?

**Geoff Horowitz:** assume. I mean I can I can find this directly. uh
reported targets. Okay, so they found all the

**Sachin Pandey:** Uh there were two targets. Yeah.

**Geoff Horowitz:** targets.

**Sachin Pandey:** The iteration one and itation three.

**Geoff Horowitz:** What is this area? I mean, I would assume that all
these areas we have XDFs for, right?

**Sachin Pandey:** Yes.

**Geoff Horowitz:** So does are you saying that maybe we\'re only
looking at this one where you found the four.

**Sachin Pandey:** Uh no uh I was in the ENT data set. No army they have
the annotations like they share the annotation

**Geoff Horowitz:** Okay. But fine,

**Sachin Pandey:** directly in

**Geoff Horowitz:** but entx, she said there\'s only five.

**Sachin Pandey:** ENTx.

**Geoff Horowitz:** So now you found six. I I\'m just confused. Suchin I
I don\'t want to I don\'t want to

### 01:38:27

**Sachin Pandey:** Yeah, I have the like I have the

**Geoff Horowitz:** go.

**Sachin Pandey:** annotation drawn on the

**Geoff Horowitz:** One, two, three, four,

**Sachin Pandey:** image.

**Geoff Horowitz:** five. Target locations. Yes, I see four here. One,
two, three, four. So, the point is she gave us four, not five.

**Sachin Pandey:** Yes. And in the PDF we have 10.

**Geoff Horowitz:** Okay.

**Sachin Pandey:** I use a

**Geoff Horowitz:** What about these? There\'s five here

**Sachin Pandey:** PDF.

**Geoff Horowitz:** though that is okay. So in this in this report
you\'re saying you found six contacts.

**Sachin Pandey:** Yes, I can give you the names of the context and the
annotation is drawn on the image.

**Geoff Horowitz:** Well, I guess I don\'t really care if we found more
than five, so I\'m okay with that. I\'m concerned about Danish Royal
Navy because she said there were 10, but we only found four. A seven
rather six. How many?

**Sachin Pandey:** I guess seven and excluding the which were in the

**Geoff Horowitz:** Seven, right?

**Sachin Pandey:** black we have minus4.

### 01:40:15

**Geoff Horowitz:** But we\'re able to identify all seven

**Sachin Pandey:** Yes.

**Geoff Horowitz:** contacts in DRN Bridget mentioned seven con sorry 10
contacts.

**Sachin Pandey:** We can do one more thing like uh for the like they
only give us the one name like one annotation. Suppose it is in the
black region and they mark they selected the file which has the the
annotation in the black region. But there are other files which are uh
have the black region visible but they didn\'t selected those file.

**Geoff Horowitz:** Are you are you saying this?

**Sachin Pandey:** So we can like do something.

**Geoff Horowitz:** I\'m not Sachin.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** I\'m not following what you\'re saying.

**Sachin Pandey:** Suppose so if you open that image there will be

**Geoff Horowitz:** I\'m not following what you\'re saying. Okay.

**Sachin Pandey:** also another uh x tape. There will be also another x
which is on the

**Geoff Horowitz:** If I open

**Sachin Pandey:** side.

**Geoff Horowitz:** Okay,

**Sachin Pandey:** Hello.

**Geoff Horowitz:** Sergeant, I I\'m just not following you. Okay,
let\'s start over.

**Sachin Pandey:** I can

### 01:41:25

**Geoff Horowitz:** Let\'s start over. Sergeant ENTX,

**Sachin Pandey:** uh

**Geoff Horowitz:** how many contacts are there?

**Sachin Pandey:** can

**Geoff Horowitz:** There are 10. Huh? ENTX.

**Sachin Pandey:** right

**Geoff Horowitz:** How many contacts are there?

**Sachin Pandey:** give me some some time. I I\'m opening my

**Geoff Horowitz:** Oh, f\*\*\*. Sachin, I\'m confusing myself now
because we\'re going back and forth. I didn\'t mean Entx, I meant Danish
Royal Navy. I\'m sorry for confusing you.

**Sachin Pandey:** uh we found all the seven because they have
annotation for all of

**Geoff Horowitz:** Okay. So,

**Sachin Pandey:** it.

**Geoff Horowitz:** in Danish Royal Navy, we found seven contacts,
right?

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Fine. She said to us there are 10 contacts.

**Sachin Pandey:** in Danish

**Geoff Horowitz:** Yes.

**Sachin Pandey:** world.

**Geoff Horowitz:** That\'s what she said in her notes. Do you know Do
you know what I\'m talking

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** about?

**Sachin Pandey:** In the this slide. Yeah. The sheet.

**Geoff Horowitz:** So, I\'m going to ask her. I\'m going to say, \"Hey,
you know, you said there were 10 here, but we only found seven.\" Okay,

### 01:42:51

**Geoff Horowitz:** I\'m going to ask her that, but I want to make sure
that we actually only found seven. We We have no idea where the other
three are. not zero. We don\'t even see them in the data set. Is that

**Sachin Pandey:** Yes,

**Geoff Horowitz:** correct?

**Sachin Pandey:** like all the annotations were present in the folder
like both the JSON files and the one we are seeing on the website is the
one we have.

**Geoff Horowitz:** What do you mean all of the annotations were
present?

**Sachin Pandey:** So about the like last time

**Geoff Horowitz:** We do you mean that there were 10 annotations
present?

**Sachin Pandey:** remember I told you like there were 14 annotations
and they were repeated right and there were only seven unique ones.

**Geoff Horowitz:** Okay.

**Sachin Pandey:** Even if you zoom into that image if you you will see
like the red ones are the one one like other one

**Geoff Horowitz:** Fine. Right.

**Sachin Pandey:** and the next to it will be a black one black pointer.

**Geoff Horowitz:** Okay. So, so let me repeat this back to you.

### 01:43:44

**Geoff Horowitz:** We found 14 shape files or annotation JSON files.

**Sachin Pandey:** JSON files. Yes.

**Geoff Horowitz:** We found 14 JSON files. Seven were unique.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Seven were essentially duplicated. Is that

**Sachin Pandey:** Yes.

**Geoff Horowitz:** correct?

**Sachin Pandey:** Roughly like not exactly there were little change but
only like very minor after.

**Geoff Horowitz:** Right. A little bit off. Yeah, I understand that.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** Um I understand that. That\'s that seems to be the
difference between where the targets were supposed to be, right?

**Sachin Pandey:** Yes.

**Geoff Horowitz:** The reported targets and where they actually found
them.

**Sachin Pandey:** And

**Geoff Horowitz:** But now, why does she have 10 here?

**Sachin Pandey:** Yes.

**Geoff Horowitz:** See? See? 1 2 3 4 5 6 7 8 9 10. What is this as
found targets for mission planning?

**Sachin Pandey:** Oops.

**Geoff Horowitz:** Do you know?

**Sachin Pandey:** I can look at it. I can download it from the website
and make a look at

**Geoff Horowitz:** Yeah, I\'m guessing that that\'s how she said 10.

### 01:44:46

**Sachin Pandey:** it.

**Geoff Horowitz:** But let\'s confirm that these other three are not
actually

**Sachin Pandey:** Yes. Can you double click on it?

**Geoff Horowitz:** targets.

**Sachin Pandey:** I think it will change to the API. Maybe not.

**Geoff Horowitz:** Okay. Oh, here it

**Sachin Pandey:** Okay, I can take a look at other three the remaining
three.

**Geoff Horowitz:** fine. Sachin is confirming this. Okay, bye. Okay, I
think that\'s all of our questions.

**Sachin Pandey:** Okay.

**Geoff Horowitz:** Do you want me to share it with you guys before I
send it to Bridget so that we can confirm that I\'m asking all the right
questions? Okay.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** Okay. I\'ll do that tonight then. So, just take a
look tomorrow. Uh tomorrow your time. Whenever you guys get up, take a
look and confirm for

**Sachin Pandey:** Oops.

**Geoff Horowitz:** me. Uh oh. Ratul, what were you saying here? There
is there is an object directly

**Ratul Shashank:** So uh

**Geoff Horowitz:** below.

**Ratul Shashank:** that is the classic uh n region problem like in some
annotations there is it\'s mark that uh an object is there but because
it\'s in the uh black region we can\'t confirm that visually.

### 01:47:04

**Ratul Shashank:** So we would need any other data

**Geoff Horowitz:** Ratul, when when we mapped annotations

**Ratul Shashank:** set.

**Geoff Horowitz:** from Bedrock onto our XTF images, did any of them
end up in this um this dead zone? this um like you know you know uh
water column

**Ratul Shashank:** Uh I I don\'t have any data on that

**Geoff Horowitz:** where did this image come from?

**Ratul Shashank:** from 8 8505 BI annotations exchange shared it with
me and

**Geoff Horowitz:** So,

**Ratul Shashank:** I take I took a look from there.

**Geoff Horowitz:** is this still a problem or did we fix this

**Ratul Shashank:** Uh I

**Geoff Horowitz:** annotation?

**Ratul Shashank:** mean it\'s not a problem because this even if
something is there down there we would not be able to see anything. I
mean if because this is just Yeah.

**Geoff Horowitz:** Right. But but I would I I understand what you\'re
saying, Rachel. I understand what you\'re saying. I\'m just I\'m trying
to get to the heart of of the question. Okay.

**Ratul Shashank:** Uh-huh.

**Geoff Horowitz:** If if Bedrock mapped this, if Bedrock gave us this
annotation,

### 01:48:29

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** I\'m not 100% but I\'m 90% sure that they probably
saw this in the side scan, too. Not 100%. Maybe, as you say, it\'s right
under the the sensor, you know, and they got this from whatever
multi-beam or something, but I would be surprised if that were the case.

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** Okay. So, so my question is, yeah, Sachin, what\'s

**Ratul Shashank:** Mhm.

**Sachin Pandey:** I think annotation is correct.

**Geoff Horowitz:** up?

**Sachin Pandey:** They just selected the wrong file. If you look to the
other file which will be like the next to it in the like original space
that region will be in the white zone where we can see the area they are
like passing.

**Geoff Horowitz:** Okay. So in DRN, so so SA let me just repeat this
then.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** Let me repeat this back to you. In Danish Royal Navy
data set, we have visual confirmation of all seven contacts, even if in
certain XTFs it ends up showing up in the in the middle. Is that right?

### 01:49:42

**Sachin Pandey:** We haven\'t confirmed it.

**Geoff Horowitz:** or am I misunderstanding what you\'re saying?

**Sachin Pandey:** No, you are right. But we haven\'t confirmed it. Like
we haven\'t plotted the missing like these spaces on any other XTFs.

**Geoff Horowitz:** Okay.

**Sachin Pandey:** Like if you plot the same annotation on multiple XTF
based on latl long then we can get the one where it is on the side and
which is visible not in the

**Geoff Horowitz:** Understood. Understood.

**Sachin Pandey:** dirt.

**Geoff Horowitz:** Fine. I don\'t care about these then because we\'ll
take them out of the training set, right? But but I do want to confirm
the positive examples that four that for all seven contacts there exists
at least one XTF that we can see it in the side scan. Is that true?

**Sachin Pandey:** You are asking for the four or

**Geoff Horowitz:** Uh,

**Sachin Pandey:** all

**Geoff Horowitz:** hold on. DRN DRN has let me let me double check so I
don\'t confuse us.

**Sachin Pandey:** seven?

**Geoff Horowitz:** DRN has seven seven contacts that we can find.

**Sachin Pandey:** Yeah.

### 01:50:47

**Geoff Horowitz:** My question is for all seven,

**Sachin Pandey:** Yes,

**Geoff Horowitz:** do we know that there exists at least one XTF that
we can see that contact?

**Sachin Pandey:** for three we need to confirm. For four we have
already like visible.

**Geoff Horowitz:** Okay.

**Sachin Pandey:** It is already there.

**Geoff Horowitz:** Okay. Can you please confirm those last three?

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Okay.

**Sachin Pandey:** Just tagging in the in the I will check it.

**Geoff Horowitz:** Fine. I will tag you right now. So at Sachin, so
there\'s two immediate open items that I need to know before I can
finish this for Bridget. So, one is um what is going on with the three
I\'m going to call these unknown contacts in the uh targets as found
folder in the targets as found folder. Right? And so these are as found
targets for mission planning. As found targets for mission, you know
what I\'m talking about there, section, you understand what my question
is there.

**Sachin Pandey:** I understand the task but not the statement.

### 01:52:20

**Geoff Horowitz:** You can rewrite this if you want. My question is it
seems like we can\'t find these three targets,

**Sachin Pandey:** Okay.

**Geoff Horowitz:** right? So, so the question is where are they? Right?
Do do they not exist? What what are these three things?

**Sachin Pandey:** Yeah. Okay.

**Geoff Horowitz:** Does that make sense?

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Okay. Um all right. Fine. Okay. And then number two
is confirm that we can see all seven targets targets in DRN data set. Oh
s\*\*\*, you know confirm that we can see all six targets in the ENTX
data set. Okay. So Sachin are these two items are clear. Okay. All
right. Once we get these questions answered,

**Sachin Pandey:** Yes.

**Geoff Horowitz:** I think I have enough to finish my questions to
Bridget. Okay guys, thanks for staying on. Anything else before we go?
Anything else you guys want to bring up? Okay. All right, guys. Thanks a
lot. I\'ll talk to you. Uh, Sachin, be sure to look at this and get back
to me. Um, other than that, I will get a message together for Bridget
today and I\'ll send it to you guys to look over. All right. Thanks,
everybody.

**Sachin Pandey:** Okay.

**Ratul Shashank:** Thank

**Geoff Horowitz:** Have a good weekend. Bye.

**Sachin Pandey:** Right.

**Ratul Shashank:** you.

**Sachin Pandey:** Hello. Okay.

### Transcription ended after 01:55:53

*This editable transcript was computer generated and might contain
errors. People can also change the text after it was created.*
