Jul 17, 2026

## Aux Discussion Mag Data

Invited [[Ratul Shashank]{.underline}](mailto:ratul@crescer.ai) [[Geoff
Horowitz]{.underline}](mailto:geoff@crescer.ai)

Attachments [[Aux Discussion Mag
Data]{.underline}](https://calendar.google.com/calendar/event?eid=MzVoM2twaTdjbTZndjRmZTNtMXFjN3U4MHIgcmF0dWxAY3Jlc2Nlci5haQ)

Meeting records
[[Transcript]{.underline}](https://docs.google.com/document/d/1hTy2Q9TEweZIHmNKTjp8TFEivNLBL19qfL0noimpaYI/edit?usp=drive_web&tab=t.gn7fgjrkmdav)

### Summary

Discussion focused on refining magnetic data pipelines and resolving
sensor data discrepancies for integration into detection models.\
\
**Magnetic Data Pipeline Integration**\
Transitioning to 2D grid processing reduced duplicate detections.
Adopting the current pipeline for integration remains the priority
despite notable amplitude variations.\
\
**Model Detection Refinement Strategy**\
Magnetic data will enhance confidence levels in detection models by
providing a secondary validation channel. Initial testing will focus on
simplified normalized threshold algorithms.\
\
**Vertical Accuracy and Provenance**\
Vertical data errors decreased significantly using corrected sound
velocity assumptions. Maintaining raw data workflows ensures necessary
audit logs for system provenance.

### Decisions

Needs Further Discussion

-   **Sound velocity methodology validation** The proposal to utilize
    > sensor speed rather than a constant 1500 m/s for sound velocity
    > requires further discussion to validate accuracy across different
    > water layers.

Aligned

-   **Magnetic data pipeline usage strategy** The magnetic data pipeline
    > is approved for use with either raw or filtered data, with ongoing
    > validation against known results until proven otherwise.

-   **Iterative validation strategy** The model validation approach is
    > set to iteratively increase complexity, starting with a simple
    > algorithmic threshold applied to existing annotated data.

-   **Extra LAS dimensions exclusion** Extra dimensions within LAS
    > files, such as beam ping and beam angle, are approved to be
    > ignored during data processing.

-   **Reference SHZ file selection** The SHZ file sourced from the
    > \'two_pressor\' folder is approved for use as the reference data.

We\'ve **updated the Decisions section** using your feedback.

Let us know what you think:
[[Helpful]{.underline}](https://google.qualtrics.com/jfe/form/SV_5p6FWBVWvynleNU?isGoogler=no&isHelpful=yes)
or [[Not
Helpful]{.underline}](https://google.qualtrics.com/jfe/form/SV_5p6FWBVWvynleNU?isGoogler=no&isHelpful=no)

### Next steps

-   \[Ratul Shashank\] Investigate Calibration: Determine why filtered
    > results are reproducible without utilizing offline calibration
    > data.

    > \[Ratul Shashank\] Analyze Annotations: Evaluate magnetic readings
    > at existing site coordinates to quantify model performance.

    > \[Ratul Shashank\] Document Benefits: Record potential performance
    > improvements gained from multi-pass sensor data for future project
    > discussions.

    > \[Ratul Shashank\] Test Algorithm: Test the new algorithm on the
    > annotated bedrock data to evaluate results.

    > \[Ratul Shashank\] Confirm LAS Dimensions: Confirm with Sachin if
    > extra dimensions in LAS files can be safely ignored.

    > \[Ratul Shashank\] Locate Matching Data: Search for other data
    > files that match the Rory McKenzie survey data.

    > \[Ratul Shashank\] Document Data Sources: Maintain documentation
    > for the source of every used data file.

    > \[Ratul Shashank\] Resolve Z Discrepancies: Investigate the root
    > cause of Z depth coordinate discrepancies in the survey data.

### Details

-   **Magnetic Data Processing Methodology**: Ratul Shashank explained
    > that while the team can locate targets, the measurement of
    > magnetic field strength is a bottleneck. Previously, they analyzed
    > one OFG file at a time, which led to approximately 800 detections,
    > many of which were duplicates. Bedrock uses a 2D detection system
    > involving a grid of 5m by 5m cells and an Inverse Distance
    > Weighting interpolation method. By adopting this 2D grid approach
    > instead of a 1D profile, Ratul Shashank reported that the number
    > of detected peaks dropped to approximately 500, as the method
    > effectively handles multiple passes over the same area.

-   **AUV Survey Passes and Calibration**: Geoff Horowitz and Ratul
    > Shashank discussed the movement of the AUV during survey passes.
    > Ratul Shashank clarified that the AUV traverses the same surface
    > in multiple iterations, often referred to as calibration runs.
    > Geoff Horowitz illustrated that these passes do not necessarily
    > follow the exact same path but instead cover the area using
    > different lines. The primary objective of these multiple passes is
    > to improve results by reducing uncertainty, as measuring the same
    > location multiple times helps achieve more accurate readings.

-   **Magnetic Field Compensation**: The discussion shifted to how the
    > vehicle compensates for magnetic fields. Ratul Shashank suggested
    > that multiple passes help remove the vehicle\'s magnetic field,
    > noting the presence of a raw column in the OFG files used for
    > compensation. Geoff Horowitz clarified that the AUV typically
    > undergoes a calibration step in a flat, object-free seabed area
    > before the survey to account for global effects and the AUV\'s
    > motor interference. Ratul Shashank agreed that filtering
    > techniques, such as low-pass filters, are applied during the
    > processing stage.

-   **Amplitude Discrepancies**: Ratul Shashank identified a significant
    > discrepancy where the magnetic peaks found by their pipeline are 2
    > to 2.5 times greater than those registered by Bedrock. Despite
    > this amplitude difference, the location and other data
    > characteristics remain consistent. Geoff Horowitz expressed
    > surprise that Ratul Shashank could reproduce the filtered output
    > using raw data without the specific offline calibrations usually
    > required. They agreed to proceed by using the pipeline as is,
    > while keeping the amplitude difference in mind for future
    > validation.

-   **Pipeline Integration Strategy**: Geoff Horowitz described the goal
    > of fusing magnetic data into the \"Lumen\" model to enhance
    > detection quality. Currently, the model uses side-scan sonar (XTF
    > files) and achieves high recall but mediocre precision. By adding
    > magnetic data as an additional channel, they aim to improve
    > confidence levels and reduce false positives. It was clarified
    > that magnetic data acts as a decision factor rather than a binary
    > filter, as it might fail to detect non-ferrous objects.

-   **Utility of Magnetic Data in Object Detection**: Geoff Horowitz and
    > Ratul Shashank discussed when magnetic data is most effective.
    > While side-scan sonar is the primary tool, magnetic data can help
    > identify objects that are buried just beneath the seabed surface
    > where side-scan might struggle. Geoff Horowitz noted that while
    > Bedrock has shared other data, such as Multi-Beam Echo Sounders,
    > they are currently unable to integrate this into the pipeline
    > because the model is not optimized for edge compute.

-   **Next Steps for Magnetic Data Pipeline**: The team discussed future
    > steps for the magnetic data pipeline. Ratul Shashank suggested
    > focusing on narrowing the detection diameter to mitigate the risk
    > of multiple objects hindering each other\'s magnetic fields. Geoff
    > Horowitz directed that they should proceed by testing the current
    > pipeline against all existing annotated training data to see where
    > it generates detections. They will use this process to evaluate
    > true positives and false positives rather than just relying on
    > amplitude accuracy for now.

-   **Analyzing Model Performance**: Ratul Shashank proposed segregating
    > performance data by class or altitude to pinpoint where the model
    > produces poor results. Geoff Horowitz advised against
    > over-complicating the initial approach, warning that segregating
    > by altitude might lead to look-ahead bias or unnecessary
    > complexity. Instead, they agreed that the team should start with
    > simple algorithms, like a normalized threshold, and iteratively
    > increase complexity rather than pulling too many levers at once.

-   **S7K Data Challenges and Axis Systems**: Ratul Shashank raised
    > concerns regarding the S7K data, specifically regarding depth
    > readings that appeared to be above sea level. Geoff Horowitz
    > clarified that this is likely due to the coordinate system
    > conventions in multi-beam point cloud data, where Z is
    > downward-facing and positive, meaning depth increases as the value
    > becomes more positive. Ratul Shashank noted that they also
    > observed discrepancies in data availability, such as beam and ping
    > information, which are missing from the LAS files provided.

-   **Extra Dimensions in LAS Files**: Ratul Shashank expresses
    > confusion regarding the presence of beam ping and beam angle data
    > in their latest LAS file outputs. Geoff Horowitz clarifies that
    > while standard LAS data typically would not include these specific
    > dimensions, their presence is acceptable provided the XYZ
    > coordinates remain intact ([[00:56:37]{.underline}](#section-44)).
    > Geoff Horowitz advises that they can likely ignore these extra
    > dimensions but encourages Ratul Shashank to verify this
    > requirement with Sachin to be certain
    > ([[00:57:56]{.underline}](#section-45)).

-   **Vertical Data Accuracy**: Ratul Shashank points out a discrepancy
    > in the Z-axis (vertical) data produced by their system compared to
    > the reference LAS file, noting that this is a primary issue they
    > need to investigate. Geoff Horowitz confirms the data originated
    > from the same multi-beam sensor and that the team did not perform
    > multiple surveys ([[00:59:11]{.underline}](#section-46)).

-   **Data Processing and Provenance Requirements**: Geoff Horowitz
    > explains that while it is theoretically possible to map ping,
    > beam, and XYZ data back from LAS to S7K or GSF, the IIC software
    > does not support this, and it is not a viable workflow
    > ([[01:00:18]{.underline}](#section-47)). Furthermore, using GSF
    > conversion results in the loss of \"provenance,\" defined as the
    > audit log of all changes made to the data. Because IIC requires
    > this full audit log for final delivery, the team must continue
    > working directly with the S7K data
    > ([[01:01:46]{.underline}](#section-48)).

-   **Sound Velocity Adjustments**: Ratul Shashank discusses the impact
    > of sound velocity assumptions on vertical accuracy, noting that
    > using the sensor speed recorded in the S7K datagram---rather than
    > the default 1500 meters per second---reduced the vertical error
    > gap to under 6 centimeters
    > ([[01:03:07]{.underline}](#section-49)). Geoff Horowitz queries
    > the nature of \"sensor speed,\" and Ratul Shashank clarifies that
    > it represents a crude but effective approximation of the speed of
    > sound through the water column for that specific surface survey
    > ([[01:04:13]{.underline}](#section-50)).

-   **Selection of Reference Data Files**: Ratul Shashank reports
    > finding an \"S rose\" file within the \"two_cursor\" folder that
    > more closely matches the output they are producing compared to the
    > file in the \"preser\" folder
    > ([[01:07:42]{.underline}](#section-52)). Geoff Horowitz authorizes
    > the use of the \"two_cursor\" file for current work, provided that
    > Ratul Shashank verifies it matches the requirements and continues
    > to document the source of all used data. Ratul Shashank plans to
    > finalize these tasks and will reach out to Geoff Horowitz if
    > further collaboration is needed over the weekend
    > ([[01:09:00]{.underline}](#section-53)).

*You should review Gemini\'s notes to make sure they\'re accurate. [[Get
tips and learn how Gemini takes
notes]{.underline}](https://support.google.com/meet/answer/14754931)*

*How is the quality of **these specific notes?** [[Take a short
survey]{.underline}](https://google.qualtrics.com/jfe/form/SV_9vK3UZEaIQKKE7A?confid=R4Oyj1g73eVr2ZaeEkOjDxISOAIIigIgABgECA&detailid=standard&screenshot=false)
to let us know your feedback, including how helpful the notes were for
your needs.*

**📖 Transcript**

Jul 17, 2026

## Aux Discussion Mag Data - Transcript

### 00:00:00

**Ratul Shashank:** mentioned that they are using uh trans uh they are
using like to give you a context what I was doing previously I was just
looking at one OFG G files in in one go, right?

### 00:00:16

**Ratul Shashank:** So when if I run for every single OG files one time,
it would that is giving the absolute number of 800 something pics in the
in the report that I mentioned. Uh what bedrock is doing, they are not
looking at one line at a time. they are they they are using a grid
system and I remember uh they call it IDW. So basically they are not
using a 1D detection they are using a 2D

**Geoff Horowitz:** Careful.

**Ratul Shashank:** detection system and that is dropping many uh like
they are not just in in they are not just doing one path one at a time
right they are traveling the same path in different iterations. So, so
that is why it is bring uh it is uh like duplicating.

**Geoff Horowitz:** Mhm.

**Ratul Shashank:** If we are uh going one file at a time, it will
duplicate the fix. I think I have it was IDW. Yeah, like they they they
are using this inverse distance waiting and they are creating a cell of
5 m by 5 m and they are like in short they are not using just 1D they
are using a 2D map and when I did that the number dropped from 500 uh
from 800 to something about 500 Uh, fix

### 00:02:16

**Geoff Horowitz:** Yeah, Rachel, let me make sure I understand. So,

**Ratul Shashank:** and

**Geoff Horowitz:** so we were looking at these, we were looking at
these kind of 1D profiles that Francisco was showing us in the call,
right? And what you\'re telling me is look, they they have all these 1D
profiles, but they\'re not just looking at a 1D profile in order to
determine whether or not this mag reading is a is a relevant object.

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** Am I am I right so far?

**Ratul Shashank:** Yeah. So,

**Geoff Horowitz:** Okay.

**Ratul Shashank:** uh like for

**Geoff Horowitz:** In Hold on,

**Ratul Shashank:** an

**Geoff Horowitz:** hold on. I I just want to let me let me talk this
out and make sure I understand it. Okay.

**Ratul Shashank:** Uh-huh.

**Geoff Horowitz:** Instead, they\'re going over the same area multiple
times, and they\'re using those multiple passes to

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** generate a a surface, a 2D surface by interpolating
between between each of the passes using uh the IDW method.

**Ratul Shashank:** uh just just to uh clarify on one on one point like
they

### 00:03:35

**Geoff Horowitz:** Yeah, correct

**Ratul Shashank:** are they are creating a 2D space for an entire surf

**Geoff Horowitz:** me.

**Ratul Shashank:** entire survey.

**Geoff Horowitz:** Can you can you draw using like a you know Scala
draw or paint or

**Ratul Shashank:** So uh I have

**Geoff Horowitz:** whatever?

**Ratul Shashank:** I have downloaded Z file so it should be even
easier. So this uh the this is what I mean by uh a grid. So this is not
just one path. This is different files combined.

**Geoff Horowitz:** How how many do you

**Ratul Shashank:** Uh this one is like they they have segregated for uh
like the

**Geoff Horowitz:** know?

**Ratul Shashank:** targets. So in this one

**Geoff Horowitz:** I mean for me it\'s three.

**Ratul Shashank:** uh

**Geoff Horowitz:** It\'s three files. Five.

**Ratul Shashank:** uh it it depends on the target.

**Geoff Horowitz:** Yeah.

**Ratul Shashank:** So for this one, let me this one would be around
five files.

**Geoff Horowitz:** Okay. All right. So,

**Ratul Shashank:** This this one.

**Geoff Horowitz:** it\'s on it\'s on the order of a

**Ratul Shashank:** Yeah.

### 00:04:57

**Geoff Horowitz:** few

**Ratul Shashank:** So if they they have classified so they are not just
using one of files if they are you if they are surveying an entire area.
So that was what I was doing wrong the previous time because uh as I
remember in the report I mentioned something around 800 picss right so
in in that number many are duplicated so let me open next calendar

**Geoff Horowitz:** And just to just to be explicit here, um they\'re
not actually getting that whole surface though. They\'re getting
individual lines and then they\'re they\'re they\'re doing um they\'re
doing interpolation using IDW, right? the inverse distance.

**Ratul Shashank:** Hey yeah I mean that is our understanding.

**Geoff Horowitz:** Correct.

**Ratul Shashank:** So like this is what they are doing.

**Geoff Horowitz:** Okay.

**Ratul Shashank:** This square is a surface and they uh and

**Geoff Horowitz:** Mhm.

**Ratul Shashank:** they are covering one surface in multiple
iterations. So they would go in one pass and on the same surface they
would go uh second time or third time like I think they call it a
calibration run or something.

### 00:06:25

**Ratul Shashank:** uh uh I I I don\'t remember very well but the point
is they they are eliminating uh if you remember Francisco said like
there are two types of norms in this industry. One is if one is an AUB
has three magnetometers and another one is only one magnetometer but
different passes. Uh I I think uh I think Haven asked if uh bedrock uses
neither and they mentioned that they used one magnetometer over multiple
passes. So this is what this is this is what it is.

**Geoff Horowitz:** right?

**Ratul Shashank:** So if pass one If if this path one gives one OFG
then this same path this same location will create a different OFG.
Right?

**Geoff Horowitz:** understood.

**Ratul Shashank:** So if we if we run the pipeline on the on two
different OFG

**Geoff Horowitz:** Yeah.

**Ratul Shashank:** files, we would get the same findings and it

**Geoff Horowitz:** Uh I mean the same or

**Ratul Shashank:** would I mean yeah I mean since

**Geoff Horowitz:** similar

**Ratul Shashank:** it\'s MA data so the amplitude would be similar
right like even if it if it\'s going from here to here it would peak out
around here like if there is uh

### 00:08:07

**Geoff Horowitz:** ritual. Can you can you share this?

**Ratul Shashank:** object

**Geoff Horowitz:** Can you share this uh do you know how to do that?
Can you share this excel draw with me?

**Ratul Shashank:** uh chance like uh like uh PNB right?

**Geoff Horowitz:** No, no, no, no. Uh, is this on the website or is
this this is in VS Code?

**Ratul Shashank:** No, it\'s it\'s it\'s in it\'s locally.

**Geoff Horowitz:** Ah, okay. All right, that\'s why.

**Ratul Shashank:** I can share this uh like they are using the uh they
are using I think

**Geoff Horowitz:** Uh

**Ratul Shashank:** JS files to create these

**Geoff Horowitz:** here, let me just do me a favor and just

**Ratul Shashank:** right

**Geoff Horowitz:** um just uh join me here. All right, just join me
here. Um, so, uh,

**Ratul Shashank:** Yeah.

**Geoff Horowitz:** oh, you want me to share? I can share my screen just
so you can see where I\'m at. So, you know, what you\'re saying is what
you\'re saying is that they, you know, they go over this multiple times.

### 00:09:29

**Geoff Horowitz:** What I\'m trying to say is like this is um, you
know, this is this is some there\'s some like real area here, right? So
this, you know, Y and X.

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** Um, and so, you know, at one pass they may be going
over here. At another pass they may be going,

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** you know, down here, right?

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** And maybe they even have a third pass where they\'re
going, I don\'t know, you know, right here or something, right? I\'m
making up.

**Ratul Shashank:** Yeah.

**Geoff Horowitz:** And so because the, you know, if our object is
really kind of over here, right? So,

**Ratul Shashank:** Uh-huh.

**Geoff Horowitz:** let me change colors. Um, if our object is really
over here, then the reading from this pass, you know, may be
significantly stronger than the reading from this pass, which may be
significantly stronger than the reading from this pass. Um, and that\'s
that\'s the distinction that I I want to make sure that we\'re on the
same page about is

**Ratul Shashank:** Thanks.

### 00:10:32

**Geoff Horowitz:** that they might not be exactly the same, right? They
might be off uh because of just distance to the object itself. Is that
is that accurate or is that

**Ratul Shashank:** W

**Geoff Horowitz:** inaccurate?

**Ratul Shashank:** Uh what uh I what I believe is uh

**Geoff Horowitz:** Uhhuh.

**Ratul Shashank:** we uh like we are looking it on a 2D space right uh
in 3D when when

**Geoff Horowitz:** Mhm.

**Ratul Shashank:** multiple persons If we if we go from A to B then we
would traverse back from on the same part B to A. So that is what my
understanding is. So it would cover the

**Geoff Horowitz:** So you\'re you\'re saying and you can you can draw
on here.

**Ratul Shashank:** same.

**Geoff Horowitz:** You\'re saying you\'re saying that your
understanding is if they went this way on the first pass,

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** right?

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** Then on the second pass they would be going I can
draw this. On the second pass, they would not go here. They would not go
here. This is incorrect.

### 00:11:52

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** Your understanding is that they would go here
approximately by line of s\*\*\*.

**Ratul Shashank:** Yeah. Yeah. I mean because if if if we uh like if

**Geoff Horowitz:** Um,

**Ratul Shashank:** we consider this this would cons would read this
area this part would read this area right but this path would read this
area.

**Geoff Horowitz:** yes, we agree.

**Ratul Shashank:** So that is why multiple passes just mean going from
here and then back and then backs and by doing that they are I think
removing the uh geological magnetic field or vehicles no they are they
are removing the vehicle magnetic field because I found in the OG file
there is a uh column raw uh raw comore for something which is uh which
which was compensating the vehicle\'s magnetic field uh and subtracting
that from the overall. So by doing this multiple path back and forth
they are removing the vehicles analytic field and yeah that is the best
understanding that I have and one missing point is if they are
subtracting the overall magnetic field of overall geological magnetic
field because as far as I have able to understand there is uh like uh in
this survey what they basically do is they

### 00:13:51

**Geoff Horowitz:** Hold on, Rachel. Hold on. I I think you\'re saying
something that I\'m not sure I agree with.

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** I can\'t tell you if I\'m right or if you\'re right,
but I I don\'t agree with it. So,

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** I think that what you\'re saying to me is that Let
me just uh let me try to draw this out a little bit. I think that what
you\'re saying to me is that you know I\'m a if this is distance right
and this is this is nanotesla

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** right here right that you\'re saying you know they
have

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** some kind of combined measurement here you know
whatever whatever that combined measurement is right and I think that
what you\'re saying actually let

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** me like where they they actually see an object even
right and that combined measurement is made up of you know like an
actual right object portion there\'s the you

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** know there\'s the ship itself the AUV itself that\'s
giving some you know MAD readings because of just the ship right um
there

### 00:15:01

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** is the kind of MAG readings from the Earth, you
know, which may I I don\'t know, you know, have some some component
there. And so there\'s all these components.

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** And I think that what you\'re saying to me is that
by going over this multiple times, that\'s how they\'re removing uh you
know, maybe the portion of the ship and the portion of the the part of
Earth. And I don\'t agree with that inherently. Uh,

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** I think that they do do that when they\'re doing
calibration.

**Ratul Shashank:** Yeah.

**Geoff Horowitz:** So when they\'re Yeah,

**Ratul Shashank:** So, go on.

**Geoff Horowitz:** go ahead.

**Ratul Shashank:** Go

**Geoff Horowitz:** No, no, that\'s So when they\'re before they before
they start with an area,

**Ratul Shashank:** on.

**Geoff Horowitz:** they go and look for for a space of seabed that\'s
very flat, right?

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** That\'s very flat that they know doesn\'t have any
objects in it. um and they just have the AUV kind of roam around that
area, right? Uh,

### 00:16:07

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** and so that to do that, that\'s how they get this
kind of global um you know the the global effect that\'s how they get
some of the effects from the AU from the motors from the motors of the
AUV. They also have a component that they test um like out of the water,

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** right? They test the the uh mag readings for like
the sensors themselves, things like that. Um so I think that\'s where
that happens. they do multiple passes to get to get more accurate
results. Right? If you measure something once, it may be an aberant
measure. If you measure something two or three times, then you can get
uh less uncertainty in your in your measurements. Does that make sense
what I\'m saying or no?

**Ratul Shashank:** I mean yes it makes sense. uh like I I agree with
you on this part that they are they are using multiple buses to remove
this uh ve uh vehicles uh magnetic field. I don\'t agree that they are
removing the uh geological because that is where they are using the uh
like what Francis was said about lowass filters or medians right so they
are doing in they are doing that after uh like they are doing it in the
processing stage and that is what I was doing when I shared that

### 00:17:45

**Geoff Horowitz:** Okay.

**Ratul Shashank:** uh the I I shar shared four images with you, right?
Um that is what I was doing in the in the in the

**Geoff Horowitz:** Uhhuh.

**Ratul Shashank:** ambient uh magnetic

**Geoff Horowitz:** Yeah. The end. That\'s right. Okay.

**Ratul Shashank:** field.

**Geoff Horowitz:** Uh, you you might be right there. Maybe I\'m
misremembering that, but but I want to I want to emphasize something.
When they do the multiple passes,

**Ratul Shashank:** Uh-huh.

**Geoff Horowitz:** I do not think that they\'re necessarily accounting
for the effects of the AUV there.

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** They\'re doing that during a calibration step
beforehand.

**Ratul Shashank:** Yeah, they could be because in the in the OFMG files
there were two separate uh columns. One was raw from XYZ tmi uh and
another was raw\_ raw XYZ XYZ TMI. So what my understanding is the raw
raw uh

**Geoff Horowitz:** Sure.

**Ratul Shashank:** let me show my screen I will I will uh it would be
much more clear if I yeah so I I have I have g I have collected all the
data on the files and like stored them.

### 00:19:18

**Ratul Shashank:** So the all like there are two variants that I that I
shared right one was the process that was variant A and the variant B
was raw. So in the raw data there are two columns. One was raw row XYZ
tmi which is before compensation and another one count contains form
which could be after compensation. These are separate columns. So and uh
I this is the

**Geoff Horowitz:** Okay.

**Ratul Shashank:** difference like in this one this spread and this
spread is significantly I mean the difference is about this much nanote
as well. So this is what I believe that they are uh compensating for the
magnetic

**Geoff Horowitz:** Mhm.

**Ratul Shashank:** field. Uh so the point is I think uh the only uh the
only question that is left is is regarding the amplitude right the uh
like uh the peak that I am uh that I am seeing is somewhere around two 2
to 2.5x greater than the peak that bedrock uh registers. The location is
same everything is same just the amplitudes peak.

### 00:21:04

**Ratul Shashank:** So that could be that could be in the in the uh find
in

**Geoff Horowitz:** Okay.

**Ratul Shashank:** in finding the ambient uh like the ambient of
atmosphere that could be something that I\'m doing for like in the grid.
I mean that is the open question at this point and I uh

**Geoff Horowitz:** So does it

**Ratul Shashank:** if that was my question for you like uh what are

**Geoff Horowitz:** matter?

**Ratul Shashank:** we expecting with the mad data that was

**Geoff Horowitz:** I don\'t think I don\'t think we have expectations.

**Ratul Shashank:** I

**Geoff Horowitz:** I mean that\'s the short version. I think you know
according to according to bedrock the the data we should be using

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** is that um what was the name it was amplitude
filtered that\'s

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** like the final data fully filtered but I think what
you told me and correct me if

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** I\'m wrong what you told me is that when we look at
that amplitude filtered NT data like

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** we\'re not actually getting good results Is that
correct?

### 00:22:12

**Ratul Shashank:** No. No. Uh, two. To be more specific, we are getting
the same results.

**Geoff Horowitz:** Uh-huh.

**Ratul Shashank:** Then like amplitude filter is the despike and every
and like every

**Geoff Horowitz:** Uh-huh.

**Ratul Shashank:** filter that they are using. And if I use that in the
pipeline and find the uh

**Geoff Horowitz:** Uh-huh.

**Ratul Shashank:** like like the result that it is producing, it is
similar to what I was doing with the raw data and applying the spy
filter and like

**Geoff Horowitz:** I see.

**Ratul Shashank:** the the the data is similar and both of them like
they are both producing the similar uh differences like this is the mag
for the processed amplitude filter. filtered one and this is without
that.

**Geoff Horowitz:** Uh-huh.

**Ratul Shashank:** So both of them like you can see the correlation is
not very different and like even in here they are the amplitude that we
get in their t file is about 2x. This is also about 2x. So this is just
the case for amplitude. Everything else is the exact

**Geoff Horowitz:** Understood.

### 00:23:17

**Ratul Shashank:** same.

**Geoff Horowitz:** I I want to just put a pin in the amplitude for for
one second. I want to put a pin in there.

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** Um so so if what you\'re saying is true, I think
that\'s great, right? I think that\'s great that that we could basically
use their raw data and recreate the filtered output. Uh that surprises
me.

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** The reason it surprises me is because I would have
expected that they\'re applying, you know, all these coefficients that
they\'re applying to get the filter data. Uh, I thought you you would
need these kind of offline calibrations that they\'re doing.

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** Does that make sense? Um, and so so that\'s why it
surprises me that we can recreate them even without those offline

**Ratul Shashank:** Yeah.

**Geoff Horowitz:** calibrations. If we can, awesome. I think that\'s
great. But it does surprise me. So I\'m I\'m viewing it a little bit
skeptically, but I I believe you, you know, I believe that that you\'ve
run this.

### 00:24:24

**Geoff Horowitz:** And so so so I I kind of like I accept it with this
kind of question mark in my head,

**Ratul Shashank:** Yeah, I I like I had that same skepticism.

**Geoff Horowitz:** right?

**Ratul Shashank:** So I think I have also stored uh like I can go ahead
and find out. I have also stored that what are we doing? Uh let if you
have time then I can just have a quick look.

**Geoff Horowitz:** Um I I I would like if you don\'t mind doing that
later, I\'d appreciate that.

**Ratul Shashank:** Yeah, no problem.

**Geoff Horowitz:** Um just

**Ratul Shashank:** I I I think I have stored it.

**Geoff Horowitz:** because

**Ratul Shashank:** Uh it\'s just I need to find it because there are
too many uh files there.

**Geoff Horowitz:** Sure thing.

**Ratul Shashank:** So uh I don\'t it\'s not a problem for me.

**Geoff Horowitz:** No, no worries. So, So that\'s an open question, but
I think I think if we assume for the time being that we can use either
pipeline, um then I think that\'s great, right? And just keep this
question in the back of our head that you know maybe we want to keep
validate as long as we\'re

### 00:25:21

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** using, you know, your pipeline or we\'re using the
other pipeline, right? The the filtered end uh filtered data. Let\'s
just keep validating and you know assume that it works until we find
until we find some place that it doesn\'t work right.

**Ratul Shashank:** Yeah. So, uh, so that\'s not a problem. So what I am
getting out of this is like the uh like

**Geoff Horowitz:** Yeah.

**Ratul Shashank:** I can you just clear one question like in our entire
uh

**Geoff Horowitz:** Yeah. Of course.

**Ratul Shashank:** process like what does bedrock expect out of mag
data from us like what where does it stand in the entire

**Geoff Horowitz:** Ah,

**Ratul Shashank:** process?

**Geoff Horowitz:** okay. Um, so I don\'t think I have an expectation,
but let me let me try to draw this out for you. If you go back to the uh
Excal or I can share my screen, whatever, it doesn\'t matter.

**Ratul Shashank:** Yeah, I I will stop.

**Geoff Horowitz:** Um, oh,

**Ratul Shashank:** Sure.

**Geoff Horowitz:** okay. I mean I\'ll I\'ll draw it in in Excal anyway
so you\'ll have access to it.

### 00:26:32

**Ratul Shashank:** Okay. No

**Geoff Horowitz:** So right now our pipeline is

**Ratul Shashank:** problem.

**Geoff Horowitz:** um our pipeline is show you and let\'s start here.
So our pipeline is um this is side scan sonar you know XTFs right or let
me let me actually just we\'re using the XTFs but for the sake of
clarity I\'m going to call this images okay so these right now these go
into our

**Ratul Shashank:** Are you home?

**Geoff Horowitz:** model um which we call we call this lumen

**Ratul Shashank:** Hello.

**Geoff Horowitz:** doesn\'t matter just our model right and then we
output um we output uh let\'s see if I can remember this um target
detections uh locations right so this is latl

**Ratul Shashank:** Okay.

**Geoff Horowitz:** long and um confidences Uh so this is this is kind
of the pipeline from the from the last deliverable. Okay. Um what they
are proposing and they said this

**Ratul Shashank:** What?

**Geoff Horowitz:** to us is that hey we also have the snag data. We
also actually let me let me take one step back for for a second.

### 00:28:14

**Geoff Horowitz:** So for these detections, okay, um we are we\'re you
know getting pretty high recall um mediocre uh precision and mediocre
accuracy accuracy. Okay, meaning And you you saw this in the last
meeting. We\'re pretty good at detecting things that we\'ve trained on,
but we have all of these false positives going on. Um, we also have some
some false negatives. I mean, not a ton, but we have some false
negatives. And so,

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** so Bedrock said to us, hey, you know, this is good.
We can clearly see the the the potential here, right? But we want to
kind of improve overall performance. So as humans when we do this we do
look at the sidescan data but we also look at this mag data right and as
humans we say okay well the mag data maybe this points to an object and
the sides scale oh yeah we can we can see it there and when we put these
together we have pretty high confidence that there\'s a target there.

### 00:29:32

**Geoff Horowitz:** So what they said to us is hey can you take this mag
data can you fuse

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** it into your model right so then this becomes lumen
uh with mag fusion and then once you do that can we end up getting can
we end up getting um like I\'m going to call this you know higher
quality detections Right? Higher quality detections because we have more
information meaning you know better precision fewer false positives

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** etc. Does that add clarity?

**Ratul Shashank:** Uh I have a question regarding that. So like mag
data is basically like a filter.

**Geoff Horowitz:** Yes. Yeah. It\'s

**Ratul Shashank:** So we so like if instead of looking at the looking
around entire survey we would use map data find like what is the area
giving signals and then we just use in that particular is that I

**Geoff Horowitz:** So, so,

**Ratul Shashank:** mean

**Geoff Horowitz:** so I mean the problem would be that MAG MAG doesn\'t
necessarily have very strong correlation because because of all the
issues that you know you\'ve already seen.

### 00:31:02

**Geoff Horowitz:** if your if your object is not very ferrris, if your
AUV,

**Ratul Shashank:** Yeah.

**Geoff Horowitz:** you know, kind of misses it, you\'re far away,
you\'re too high, you\'re, you know, all these things. So, If you only
look at the mag data, then you could miss a ton of objects. A ton of
objects,

**Ratul Shashank:** Yeah,

**Geoff Horowitz:** right?

**Ratul Shashank:** that was that was exactly the question in my head
because it

**Geoff Horowitz:** Yeah.

**Ratul Shashank:** is not going to find any nonparis objects or

**Geoff Horowitz:** Ex.

**Ratul Shashank:** like many things.

**Geoff Horowitz:** Exactly. Exactly. So that\'s that\'s the that\'s the
concern. That\'s why what we\'ve talked about is adding it as a uh you
know a channel to the model meaning the model can assess this data and
say hey does this give me higher confidence or lower confidence right
but that it doesn\'t necessarily by itself or you know maybe it could
right maybe we can\'t see anything in the sides scan but the mag data is
such a strong signature that we can say hey there is a target here right
but it\'s still

### 00:32:05

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** going to be kind of a decision factor. It\'s not a
It\'s not necessarily a a binary filter.

**Ratul Shashank:** I mean I mean correct me if I\'m wrong but uh like I
have two questions in my

**Geoff Horowitz:** Yeah,

**Ratul Shashank:** head at this point.

**Geoff Horowitz:** of course. Go

**Ratul Shashank:** Isn\'t that like if we if any uh if mag data

**Geoff Horowitz:** ahead.

**Ratul Shashank:** is producing significant results then isn\'t that
would also be very apparent in the xdfs like that at that point it would
be kind of redundant

**Geoff Horowitz:** Not necessarily.

**Ratul Shashank:** because

**Geoff Horowitz:** Imagine if the imagine if the object is like just
under the surface of the

**Ratul Shashank:** ah yes yes Yes.

**Geoff Horowitz:** of the uh you know just under the seabed surface,
right?

**Ratul Shashank:** Yes.

**Geoff Horowitz:** Like I I mean close enough, you know, close enough
that we can get a mag reading. So not like you know 5 meters or 10
meters or 20 meters below but you know just buried maybe because of the
you know how the water is moving like it just buries it a little bit.

### 00:33:11

**Geoff Horowitz:** Uh yeah so those are those are places where the mag
could help a

**Ratul Shashank:** Yeah. I and exactly I the second question that I had
was regarding this

**Geoff Horowitz:** lot.

**Ratul Shashank:** like they the bedrock they also shared different uh
like other datas as well like they have also shared MBEs and SP files.
Uh are we going to use those as well

**Geoff Horowitz:** Yes. So,

**Ratul Shashank:** or

**Geoff Horowitz:** so we we did talk about it with them. The problem
right now is that their goal is to run all of this on board the AUP,
right? and our existing Iris model you know which which

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** um which we would use to process the multi-beam data
for example right uh it\'s not set up to work on edge

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** compute um you know we use even for our clients,

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** right? If we run it for them or when we run it
ourselves, we use pretty high performing compute. Um, I mean, you know
this, we use black wells, we use 4090s.

### 00:34:24

**Geoff Horowitz:** Um, and so, so because of that, we have not
integrated point cloud analysis into this whole pipeline.

**Ratul Shashank:** Makes sense.

**Geoff Horowitz:** Yeah.

**Ratul Shashank:** Uh I understand I understand so so regarding the MAC
data like what I am getting out of this is we don\'t care about uh like
how like the aptitude part we can just skip it if if we are find if we
are able to like cut the slice of where we are finding any anomaly we
that is fine in either way,

**Geoff Horowitz:** Exactly.

**Ratul Shashank:** right?

**Geoff Horowitz:** That\'s exactly what I\'m getting at is like I hear
I hear you saying that, you know, we\'re not getting 10 nanopes, right?
We\'re getting 25,

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** we\'re getting 50. Um, but from my perspective,

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** and I think this is true until we can prove it
wrong, and we may prove it wrong, but this is true until we can prove it
wrong. As far as I\'m concerned, you know, if we see a clear signal, it
doesn\'t really matter what the exact value is.

### 00:35:42

**Geoff Horowitz:** It matters what the relative values are, right?

**Ratul Shashank:** Makes

**Geoff Horowitz:** Um, so that\'s that\'s my instinct and and I want to
emphasize this again.

**Ratul Shashank:** sense.

**Geoff Horowitz:** My instinct may be wrong, right? Maybe we\'re going
to look at this and it\'s going to be proven wrong, but we don\'t have
the information to sort it out yet. And so why not assume that it\'s
right until we prove it wrong.

**Ratul Shashank:** Makes sense. Makes sense. Makes sense.

**Geoff Horowitz:** Okay. So, so there is that one thing that you wanted
to look into which is that um you know the the h like how are we
reproducing it if we don\'t have these what we assume are are offline
calibrations but you know we can look into that in terms of next

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** steps I think that we should well let me ask you
what do you think the next steps are

**Ratul Shashank:** for uh in just Mac data or overall

**Geoff Horowitz:** it in this mag data for to use this mag

**Ratul Shashank:** uh I mean the biggest bottleneck is just

### 00:36:44

**Geoff Horowitz:** data.

**Ratul Shashank:** accuracy right I mean what I have found the uh like
the the pipeline that I have created it is fine ing the targets

**Geoff Horowitz:** Mhm.

**Ratul Shashank:** in in a radius of around 5 to 10 m which is

**Geoff Horowitz:** Uh-huh.

**Ratul Shashank:** uh even though it is short but uh in in in hindsight
It it could be like it could be like if there are two UFOs or two
targets in at around the same location, it could hinder each other\'s
magnetic field. So the next part could be uh narrowing it down and I

**Geoff Horowitz:** Mhm.

**Ratul Shashank:** have like uh using the grid that I that I told you
about. It is solving a lot in that area but obviously using that grid

**Geoff Horowitz:** Okay.

**Ratul Shashank:** means you would have you need to have the entire uh
surveys OMG and not just one line.

**Geoff Horowitz:** Yeah. Which may be an issue. Which may be an

**Ratul Shashank:** So I mean if if you are using it on the go then it
would not

**Geoff Horowitz:** issue.

### 00:38:00

**Ratul Shashank:** make any sense.

**Geoff Horowitz:** Mhm.

**Ratul Shashank:** So one would be that uh to reducing the overall

**Geoff Horowitz:** Yeah.

**Ratul Shashank:** uh detection diameters and I think uh it is just my
preliminary belief like if we if I can narrow that circle down then I
would eventually also figure out why I\'m getting this amplitude
problem. I think it is like it is just my belief that they would go hand
in

**Geoff Horowitz:** Uh-huh. Okay. Okay. Uh, that\'s reasonable.

**Ratul Shashank:** hand.

**Geoff Horowitz:** Um, I think that I think that in for the time being
we should assume that we won\'t have the multiple passes that we\'ll
only have the one pass. However, we should keep this documented
somewhere that hey,

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** if we had multiple pass data, you know, we we
actually think that we could get even better results, right? And we can
bring that up as a like a next step with with Bedrock.

**Ratul Shashank:** Yeah,

**Geoff Horowitz:** Um so yes

**Ratul Shashank:** I am I am documenting every single step like you you
know my pipeline.

### 00:39:11

**Ratul Shashank:** I have

**Geoff Horowitz:** I I do know you are. Yeah.

**Ratul Shashank:** I

**Geoff Horowitz:** Uh okay. The second thing is so so I I what you said
sounds reasonable to me.

**Ratul Shashank:** uh

**Geoff Horowitz:** Uh to me a next step would actually be going through
the data going through the data we have um sending in our pipeline.

**Ratul Shashank:** Which data exactly?

**Geoff Horowitz:** So all of our training data or I mean e even all of
our annotated data now

**Ratul Shashank:** Oh, okay.

**Geoff Horowitz:** that I think about it, right? Uh we could we could
go through all that data and we could say essentially for for each of
these annotations, right? What does our mag data look like? Okay. and
then and then to to write some it could just be a simple algorithm,

**Ratul Shashank:** Oh,

**Geoff Horowitz:** right? It could be a simple like um it could be a
threshold. It could be a like a normalized threshold, right? So that we
don\'t really care about um uh you know these these relativistic
differences.

### 00:40:17

**Geoff Horowitz:** I mean it could be something very simple but to look
at this and say hey if we ran this kind of simple

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** algorithm where are all the places that we would
that we would show um that we would we would show detections right and
you know because we have the ground truth from

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** the sidescan data how many essentially create these
same let me show you uh uh here it is. You know, essentially create
these same tables, right, that say that say, you know, what would be our
true positives, what would be our false positives, right? And kind of
dig into those results a little bit. Um to me that seems like a
reasonable next step is to say, okay, let\'s we think we have an
understanding of the data. We think there\'s a signal here. How does
this look when we apply this to our data set? Does that make sense?

**Ratul Shashank:** uh so uh what I am understanding Yes, you want to
segregate these metrics like individual uh metrics

### 00:41:23

**Geoff Horowitz:** Uhhuh.

**Ratul Shashank:** of the classes and then figuring out what each class
produced in the individual data be it mag or uh

**Geoff Horowitz:** Uh-huh.

**Ratul Shashank:** xtfs and and we can have a high level data of which
class

**Geoff Horowitz:** Yeah.

**Ratul Shashank:** produced what kind of results right is that am I
understanding correctly

**Geoff Horowitz:** Yeah. Yeah, I think so. Um, so let\'s see how it
producing each of these results. Yeah. Uh, I mean, go

**Ratul Shashank:** I mean I mean I talked something similar with Sachin
and

**Geoff Horowitz:** ahead.

**Ratul Shashank:** when when we were talking when uh like when he was
showing how the recall was performing I we talked something I mean not
exactly

**Geoff Horowitz:** Mhm.

**Ratul Shashank:** this but I told him wouldn\'t it be beneficial to us
if we just uh like if we do two things. One if uh like if we are getting
mixed results then we can just

**Geoff Horowitz:** Mhm.

**Ratul Shashank:** segregate each uh classes and then find the values
for each class. Uh so we would we can like uh we can segregate which
class is performing bad.

### 00:42:45

**Ratul Shashank:** And the second thing that we discussed was uh like
these also depend on factors like altitude or uh speed.

**Geoff Horowitz:** Mhm.

**Ratul Shashank:** So like altitude is a major factor because because
the same

**Geoff Horowitz:** Yeah.

**Ratul Shashank:** uh area if on a higher altitude would look much
smaller compared to a lower altitude.

**Geoff Horowitz:** Uh-huh.

**Ratul Shashank:** So if we separate, if we separate lower altitude
data and higher altitude data and then compare them with the overall
overall results that the model produces. Then we would have uh we would
have the data where it is producing bad results. So, we can pinpoint on
those

**Geoff Horowitz:** I I have a I have a small issue with that,

**Ratul Shashank:** because

**Geoff Horowitz:** Ritual, which is as I understand what you\'re

**Ratul Shashank:** Uh-huh.

**Geoff Horowitz:** saying, it it almost feels like something like look
ahead bias, right? So I\'ll tell you why. I\'ll tell you why. Let\'s say
that we find that in high altitude areas, you know, we have some issues
and you know the well the the the range of the mag data and the high
altitude areas is different than the range of the altitude and low al
the range of the magnitude and low altitude

### 00:44:08

**Ratul Shashank:** Sorry.

**Geoff Horowitz:** data. That\'s not something that we actually have
control over,

**Ratul Shashank:** Hello.

**Geoff Horowitz:** right? Like the AUV is going to travel at whatever
altitude the AUV is traveling at, right? And even a raw altitude value
isn\'t altitude above ground it is yeah above

**Ratul Shashank:** Yeah, I mean above the sea

**Geoff Horowitz:** seed. Um so like it it\'s

**Ratul Shashank:** bed.

**Geoff Horowitz:** one thing to say it\'s one thing to to have the
altitude as an input into our like simple algorithm. It\'s a different
thing to actually segregate by altitude in my head. Does that make
sense?

**Ratul Shashank:** Yes. Yes, it makes sense. It makes

**Geoff Horowitz:** Um, yeah. So, like using altitude to say, oh,

**Ratul Shashank:** sense.

**Geoff Horowitz:** maybe we have less confidence because we\'re higher
or um, you know, or this this threshold, you know, should be attenuated
because because we\'re at some alt I, you know, or as a function of
altitude. Like that all kind of makes sense to me as part of the
algorithm.

### 00:45:15

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** But I worry about I worry about like segregating the
data based on

**Ratul Shashank:** Yeah,

**Geoff Horowitz:** that.

**Ratul Shashank:** I mean what I like what I wanted to achieve by
segregation is like we would get the data of how it\'s performing then
for the final run we would just want to minimize that gap right

**Geoff Horowitz:** Mhm.

**Ratul Shashank:** so we can do that with like we would have only few
options like either tweaking the model or either improving the quality
of data or like or like changing the activation function.

**Geoff Horowitz:** Mhm.

**Ratul Shashank:** I mean like that was in my head what we can do to
minim like minimizing that gap is what I

**Geoff Horowitz:** I see. I see. Well, look,

**Ratul Shashank:** intended

**Geoff Horowitz:** I I\'ll also say to to me like that doesn\'t need
that doesn\'t need labelers. That doesn\'t need anything. We can
actually just go through. We have the location of all of these
annotations, right?

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** Because it\'s all georreerenced and we have the
altitude at that location.

### 00:46:21

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** So it\'s very easy to write a script that just
segregates these, right? Like it takes no time to do it.

**Ratul Shashank:** Yeah. Yeah. I mean we don\'t need to train

**Geoff Horowitz:** So So I don\'t I mean

**Ratul Shashank:** separately.

**Geoff Horowitz:** this I think there\'s no harm in trying it. Um but
but I I\'m also and this goes back to like us being um uh what\'s the
word? Um I can\'t think of the word I\'m thinking of but you know like
systematic in how we do this is I worry I worry about trying to pull too
many levers at one time, right? Um so like I think that we should do I
believe in starting with kind of the

**Ratul Shashank:** Oh,

**Geoff Horowitz:** the lowhanging fruit. The lowhanging fruit here is
let\'s just see how we do you know if

**Ratul Shashank:** you

**Geoff Horowitz:** we write some simple algorithm and then the
systematic way is to I think is to um iteratively increase complexity.

**Ratul Shashank:** No,

**Geoff Horowitz:** Would you agree with that?

### 00:47:34

**Ratul Shashank:** I I I understand that. I understand that. Uh and and
and when you mentioned that I am also I mean like what I mentioned what
like what I proposed it would be kind of redundant. So yeah it makes
sense for you sir.

**Geoff Horowitz:** Okay. Um Okay. So,

**Ratul Shashank:** Uh

**Geoff Horowitz:** so let\'s re I I\'m going to need to go in a few
minutes. Um

**Ratul Shashank:** yeah, and before you before uh before you go like I
would also want to discuss about

**Geoff Horowitz:** I

**Ratul Shashank:** the uh S7K data uh

**Geoff Horowitz:** That\'s right. That\'s right. Uh,

**Ratul Shashank:** just

**Geoff Horowitz:** is it going to be a deep conversation because we may
have to delay it?

**Ratul Shashank:** uh like I need two things from you.

**Geoff Horowitz:** Yeah. What\'s

**Ratul Shashank:** Uh what\'s uh one is like the the uh what you

**Geoff Horowitz:** up?

**Ratul Shashank:** shared uh

**Geoff Horowitz:** Wait, sorry, Rachel. Rachel, let me just wrap up the
last conversation. So,

**Ratul Shashank:** the

### 00:48:36

**Geoff Horowitz:** so I I\'m I\'m all for you trying whatever kind of
next steps you deem appropriate and interesting, right? I don\'t I I
think you found this out, right? Our style is not to micromanage. Uh but
I do think that you should as part of whatever you do do this next step
of um of you know actually kind of testing it out on our data and seeing
what results we get.

**Ratul Shashank:** Yeah, I understand.

**Geoff Horowitz:** Okay, cool.

**Ratul Shashank:** I I regarding it. I just to uh clarity just to Be
clear regarding data. You are talking about the model,

**Geoff Horowitz:** The data I\'m talking about is the model.

**Ratul Shashank:** right?

**Geoff Horowitz:** The data I\'m talking about is our our annotated
bedrock data.

**Ratul Shashank:** Yeah. Yeah. I I understand.

**Geoff Horowitz:** Yes. Okay.

**Ratul Shashank:** Uh and uh what I wanted to ask about

**Geoff Horowitz:** And and Rachel,

**Ratul Shashank:** the seven frame

**Geoff Horowitz:** if you ever you I think you know this by now. If you
ever have any questions or you start digging into it and then something
doesn\'t make sense or, you know, you thought it made sense and it
doesn\'t, just reach out.

### 00:49:50

**Geoff Horowitz:** You can always reach out. I I have no qualms about
uh I I prefer that everybody clarify before, you know, wasting a bunch
of time doing something.

**Ratul Shashank:** Yeah, I mean that was my point like because I I was
uh I was kind

**Geoff Horowitz:** So,

**Ratul Shashank:** of confused where I where the direction was going
with the nar data. So I thought it would be best to clarify with you.

**Geoff Horowitz:** absolutely.

**Ratul Shashank:** So I that was uh even with the S7K pipeline

**Geoff Horowitz:** Okay. So, so let\'s shift to that.

**Ratul Shashank:** uh yeah I mean that regarding the S7K

**Geoff Horowitz:** Uh

**Ratul Shashank:** uh what data what uh what you shared the last file
that you shared I have found like the the point cloud this the
differences regarding in the point cloud I have shared in the report
right. uh because in long story short I think this uh what you shared
what the data of SHC rose it is a different it is a different sensor
like

**Geoff Horowitz:** Mhm.

**Ratul Shashank:** we it was created by maybe a LAR sensor or I don\'t
know because uh the sole reason for that is the depth that uh the that
particular file is showing is well above the sea level, right?

### 00:51:25

**Geoff Horowitz:** is well above the sea level.

**Ratul Shashank:** And yeah, I mean in the report

**Geoff Horowitz:** Uh, Repul this might be this this might just be
because you

**Ratul Shashank:** we

**Geoff Horowitz:** um you I don\'t think you\'ve worked with a lot of
the uh the multi-beam data yet. Um so the the Z data is actually

**Ratul Shashank:** How

**Geoff Horowitz:** inverted. Um meaning Yes.

**Ratul Shashank:** many negative 0 to negative

**Geoff Horowitz:** Uh, no. No.

**Ratul Shashank:** Hey.

**Geoff Horowitz:** I I\'m I\'m a little rusty here, but uh just because
I haven\'t thought about it in like a few months, and that\'s, you know,
an eternity. Um, but hold Hold on, let me let me just validate here. Um,
in multi-beam point cloud data, what is the uh what\'s the word? I\'m
thinking of the um origin direction. Yeah, there you go. Okay. Um, here
I\'ll just share this with you. So, so yeah, I can this. So, okay. So,
the directionality is the positive x direction is is is easting, right?

### 00:52:58

**Geoff Horowitz:** They call it the positive y direction is northing.

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** So, these are both so this is actually this is more
it\'s along the track, right?

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** Um and then positive x is uh to the right of the to
the right. If if the ship is going forward, positive X is to the right.
And then Z is downward facing.

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** So it starts at the ship and then it goes down.

**Ratul Shashank:** Yeah. So ship would be zero and down would be
negative, right?

**Geoff Horowitz:** So down. No. So down would be positive. The further
down it goes, the more positive it gets.

**Ratul Shashank:** Uh-huh.

**Geoff Horowitz:** Did you follow that?

**Ratul Shashank:** Oh. Oh, I I see the depth depth would

**Geoff Horowitz:** Let me see if I Let me see if I can get an image
because I even I had to look this up.

**Ratul Shashank:** increase.

**Geoff Horowitz:** Uh let me see if I can find an image that actually
shows this. Um not it.

### 00:54:05

**Geoff Horowitz:** This is also not it. Uh, I don\'t have a good image,
but basically here I can I can draw it out for you. It\'s not that hard.
Uh, where\'s my where\'s my uh skele um, so basically like you have this
problem. So you have a ship, right, that\'s going along the path and
this is your ship, right? It\'s a bad ship. Should make it look like a I
should make it look like a good ship. Um, there\'s my ship. So then you
have the sensor on the bottom here, right?

**Ratul Shashank:** Hello

**Geoff Horowitz:** And so directionality directionally forward.

**Ratul Shashank:** everyone.

**Geoff Horowitz:** This is Y. This is your Y axis. This is positive Y.
This is positive Z direction.

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** And then uh I think it\'s if I can do this right,

**Ratul Shashank:** Anyway,

**Geoff Horowitz:** then that would make this your positive x direction.
I might have gotten that backwards, but I think that\'s

**Ratul Shashank:** I mean X and Y would be I mean the main problem is

### 00:55:24

**Geoff Horowitz:** Right.

**Ratul Shashank:** Z.

**Geoff Horowitz:** So, but does this So, so okay, I I don\'t know if
you knew that. I don\'t know if that\'s important, but if you invert
your Z to make downward positive, does that change anything?

**Ratul Shashank:** Uh I mean I think we are talking about two different
things. I mean like I I get your point but what I want to share

**Geoff Horowitz:** Okay. Okay. Fine.

**Ratul Shashank:** like

**Geoff Horowitz:** Sure.

**Ratul Shashank:** this is the uh detail that I have logged for both
right so classification scheme does not matter the main the two and four
are more important points like we are producing extra data of beam,

**Geoff Horowitz:** Okay,

**Ratul Shashank:** ping. These are not available in the last file

**Geoff Horowitz:** correct. Because last doesn\'t store that
information.

**Ratul Shashank:** and

**Geoff Horowitz:** Last only stores XYZ. So we wouldn\'t expect to find
it in the last data.

**Ratul Shashank:** understood.

**Geoff Horowitz:** Does that make

**Ratul Shashank:** And this I mean I mean it makes sense but uh it is
also

### 00:56:37

**Geoff Horowitz:** sense?

**Ratul Shashank:** like it is confusing me because the this comparison
is on the last fight on the two last fights. So according to this agent
we are also producing these

**Geoff Horowitz:** Okay, I see. Yes, I agree with you.

**Ratul Shashank:** data.

**Geoff Horowitz:** That doesn\'t make sense why our last file is
producing beam ping, beam angle, things like that. I mean, it it if
they\'re just extra dimensions, then we may just be copying them over.
So, they don\'t it doesn\'t harm us as long as we have XYZ,

**Ratul Shashank:** Mhm. Mhm.

**Geoff Horowitz:** right? Um,

**Ratul Shashank:** Uh,

**Geoff Horowitz:** but normally Go ahead.

**Ratul Shashank:** I understand.

**Geoff Horowitz:** Okay.

**Ratul Shashank:** I I I was just saying that I

**Geoff Horowitz:** Yeah. Okay.

**Ratul Shashank:** understand

**Geoff Horowitz:** So normally normally last data would not have like
beam ping beam angle.

**Ratul Shashank:** and what does IIC require like what is their uh uh
requirement?

**Geoff Horowitz:** It it doesn\'t it doesn\'t matter because we\'re not
using this pipeline. We would never give them the last data.

### 00:57:56

**Geoff Horowitz:** We would have the last data.

**Ratul Shashank:** Okay. Okay.

**Geoff Horowitz:** the the requirement is just whatever Iris needs.

**Ratul Shashank:** Understand.

**Geoff Horowitz:** And you know, I\'m pretty sure this is something
that you can definitely confirm with Sachin, but I\'m pretty sure that
we can like, you know, we can ignore Um. We can ignore extra dimensions
from our last.

**Ratul Shashank:** So, so I can ignore extra dimensions.

**Geoff Horowitz:** Yes.

**Ratul Shashank:** Uh

**Geoff Horowitz:** Yeah. I I would confirm that with Sachin,

**Ratul Shashank:** ah okay.

**Geoff Horowitz:** but I\'m I\'m 98%

**Ratul Shashank:** Okay. I I I think Sachin like I was talking about
this.

**Geoff Horowitz:** sure.

**Ratul Shashank:** He mentioned that he would get back to me because he
is also he he mentioned that he is he he kind of forgot a few things

**Geoff Horowitz:** Yeah, Rachel.

**Ratul Shashank:** but

**Geoff Horowitz:** Rachel, this is our problem. We forget all these
things, you know, if we haven\'t worked on them in two weeks.

**Ratul Shashank:** I mean I uh and regarding the uh agent uh I think I
can als I can give you a briefing about not briefing Sorry, like just a
preliminary architecture because I have a few data uh not

### 00:59:11

**Geoff Horowitz:** I would love that.

**Ratul Shashank:** data but uh and a few

**Geoff Horowitz:** Wait, wait, Rachel.

**Ratul Shashank:** ideas.

**Geoff Horowitz:** I I would I would love that, but I don\'t have time
to talk about it right now.

**Ratul Shashank:** Yeah,

**Geoff Horowitz:** Yeah.

**Ratul Shashank:** I I just to just to clear this uh like the main
problem is this.

**Geoff Horowitz:** Ah, the Z.

**Ratul Shashank:** This is the log log.

**Geoff Horowitz:** Okay.

**Ratul Shashank:** This is what the agent find out.

**Geoff Horowitz:** Okay.

**Ratul Shashank:** V uh the this is the range that our last files is
producing and this is the range that uh the last file S

**Geoff Horowitz:** Uh-huh.

**Ratul Shashank:** rose is showing and this is the major uh reason uh
that it uh that I think it could be possibly not MBS uh I mean obviously
MBS would be I The last f would not be created from MBS but uh different
sensor. This is the uh main point.

**Geoff Horowitz:** I I know I know the data was from the same mult I
mean this is all the same multi-beam sensor.

### 01:00:18

**Geoff Horowitz:** They didn\'t do this multiple times.

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** So the the last data was exported from the same S7K
file.

**Ratul Shashank:** So,

**Geoff Horowitz:** um and they exported it to lass and gave it to us.

**Ratul Shashank:** uh-huh.

**Geoff Horowitz:** The problem the problem with that is that they
can\'t reimpport it from lass. That\'s is what

**Ratul Shashank:** Is that possible to like to go back

**Geoff Horowitz:** possible.

**Ratul Shashank:** from last two GSF or S7K? I mean there are multiple
corrections on the

**Geoff Horowitz:** Um, so it hypothetically if you were somehow able to
map

**Ratul Shashank:** path.

**Geoff Horowitz:** each ping and this is what we did with GSF, right?
If you were able to map the ping um the beam and the ping to an XYZ
point, And each XYZ point was unique. Then yes, you can you can reverse
the mapping because you know because each beam and ping rather each ping
of each beam is unique or should be unique.

**Ratul Shashank:** Mhm. I am

**Geoff Horowitz:** Um the the ping is unique. Whether or not multiple
pings end up pointing to the same XYZ location, that\'s possible.

### 01:01:46

**Ratul Shashank:** Yes, I it is a time series kind of a time

**Geoff Horowitz:** Yeah. Yeah. So, so,

**Ratul Shashank:** series.

**Geoff Horowitz:** so like theoretically there is a way to go from the
S7K data directly to LAS and then back again, but IIC software doesn\'t
support that. And really it\'s it\'s very theoretical, right? Like
there\'s no there\'s no reason it should work.

**Ratul Shashank:** Oh

**Geoff Horowitz:** Um so that\'s that\'s the problem and that\'s why we
went with this

**Ratul Shashank:** no.

**Geoff Horowitz:** GSF route which kind of worked but it loses um do
you know what providence is?

**Ratul Shashank:** I don\'t know.

**Geoff Horowitz:** Providence is basically like think of it like an
audit log, right?

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** an audit log of every single thing that\'s ever
happened, right? Um, and so by exporting then reimpporting using GSF,
the that audit log is lost and uh and that\'s a problem for IIC\'s like
final delivery. They need this full audit log for final delivery. And so
this is Yeah.

**Ratul Shashank:** I understand.

**Geoff Horowitz:** So this is why we\'ve kind of ended up where we are
where we\'re trying to go with the S7K data

### 01:03:07

**Ratul Shashank:** Okay. So,

**Geoff Horowitz:** directly.

**Ratul Shashank:** so TLDDR this is something that I need to work on,
right? Like why is this uh not showing uh like why is this not

**Geoff Horowitz:** Yeah. Yeah.

**Ratul Shashank:** accurate?

**Geoff Horowitz:** It it could that could be just because of the some
of the assumptions we\'re making. It\'s possible, but I think we need to
validate

**Ratul Shashank:** Uh yeah.

**Geoff Horowitz:** that.

**Ratul Shashank:** So in this for this uh Rory Mckenzie we are not
using anyone like this is running on zero ancillary just 7K and no extra
I

**Geoff Horowitz:** Oh,

**Ratul Shashank:** mean the they have not provided provided us with any
extra data.

**Geoff Horowitz:** okay. So, so then, so then yeah, I would assume,
well, they haven\'t provided us with any extra data, but there are still
assumptions, right? We\'re making assumptions on like speed of water,
speed of sound through water. We\'re making I mean, there\'s plenty of
assumptions we\'re making, right?

**Ratul Shashank:** uh so the speed of sound uh ac across water we are
using the sensor speed.

### 01:04:13

**Ratul Shashank:** So as previously mentioned in the report that the by
default we would use 1500 m/s but I have found if we could use the
sensor speed uh for the speed of sound we could

**Geoff Horowitz:** Mhm.

**Ratul Shashank:** like uh like when I mentioned like if we are uh 7 m
uh I think 7 8 cm closer to the reference right but if we use the sensor
speed we close that gap much under 6 cm.

**Geoff Horowitz:** What is What is sensor speed?

**Ratul Shashank:** So that is sensor speed is just a datagramgram

**Geoff Horowitz:** What is that?

**Ratul Shashank:** in the S7K like the

**Geoff Horowitz:** What does it represent?

**Ratul Shashank:** entire uh the speed

**Geoff Horowitz:** What does sensor speed

**Ratul Shashank:** that the sensor is registering for

**Geoff Horowitz:** represent?

**Ratul Shashank:** uh it is a very crude representation of sound
velocity profile because sound velocity profile would be like it would
uh affect it would be affected by the layers of water right earlier we
would we just we we just adopted the value of 1500 m/s as I mentioned in
the comment that you uh that you uh flagged uh but if we can use this
rather than a constant value then it would be it it is it is much closer
Like it is just what the speed water uh in the ray is travel inside
water.

### 01:06:25

**Geoff Horowitz:** What what what what Google is telling me is that and
I think this is what you just said, right? Is that you can use that for
the surface water layer, but for deeper layers of water that won\'t
work.

**Ratul Shashank:** Yeah, this is this is a surface uh I also confirmed
this this Rory McKenzie S7K it is a surface uh survey

**Geoff Horowitz:** Ow. How did you confirm that?

**Ratul Shashank:** uh this is also a data in uh in the uh a datagram
also hold this data. So I I I can ask this but this Rory McKenzie file
it contains a data graph. uh for the altitude and depth. Just let me
confirm

**Geoff Horowitz:** Okay,

**Ratul Shashank:** this.

**Geoff Horowitz:** Rachel, I\'m really sorry. I do have to run.

**Ratul Shashank:** Oh. Oh.

**Geoff Horowitz:** I\'m already No.

**Ratul Shashank:** Uh I will I just confirm everything and just let you
know. So uh uh TLDDR I just want to I just need to work on the Z, right?

**Geoff Horowitz:** Yeah. Yeah.

### 01:07:42

**Geoff Horowitz:** Yeah. Yeah. I think so. I mean, I\'m trying to think
through with you like why there might be differences, but I guess I
guess that\'s just the big thing that we need to dig into is why are we
seeing differences between um the results that we\'re getting and the uh
the reference last file.

**Ratul Shashank:** Okay, I I I will I will just write a message
regarding the second part that I wanted to discuss like uh in short this
SHC I I

**Geoff Horowitz:** Great.

**Ratul Shashank:** this S rose file I found it also in the two\_ cursor
data sorry two\_ folder this uh I I will I will explain in the

**Geoff Horowitz:** Let me check.

**Ratul Shashank:** chat much uh uh so it would be you can look at look
at it the what I wanted to tell you that is the last file that I\'m
creating is much closer to the to\_ presser folder then from preser
folder uh last file

**Geoff Horowitz:** Uh, do you remember where SHZ row? Oh, okay. Uh,
yes. As far as I\'m concerned, you can use the one in the two pressor

### 01:09:00

**Ratul Shashank:** Okay.

**Geoff Horowitz:** file.

**Ratul Shashank:** So, this is much closer to what I am producing even
the

**Geoff Horowitz:** Honestly, Rul,

**Ratul Shashank:** bumps and

**Geoff Horowitz:** honestly, Rul, I\'m I\'m concerned that I\'m
concerned that we gave them something that didn\'t match what they gave
us. Does that make any

**Ratul Shashank:** I mean,

**Geoff Horowitz:** sense?

**Ratul Shashank:** uh, I I can\'t comment on that, honestly.

**Geoff Horowitz:** Okay. Anyway, but yes, as far as I\'m concerned, you
can use the the one that they sent us. I would just um I would I would
double check to make sure that it does indeed match. It sounds like
you\'re doing

**Ratul Shashank:** Okay,

**Geoff Horowitz:** that.

**Ratul Shashank:** I will I will just look if there are any other data
files that match with the royal

**Geoff Horowitz:** Cool.

**Ratul Shashank:** and I will I will update you on

**Geoff Horowitz:** Okay. And also as as I know you do anyway,

**Ratul Shashank:** this.

**Geoff Horowitz:** just make sure to document, you know, exactly where
you got the data from.

**Ratul Shashank:** Uh I mean that is kind of my ammo at this point,
right?

**Geoff Horowitz:** Exactly. Exactly. Uh, all right. Cool. Thank you,

**Ratul Shashank:** Okay.

**Geoff Horowitz:** Rul. I uh send me a message if you need something
else. I\'m I mean I don\'t need you to work this weekend, but you know
I\'m happy to get on a call this weekend if you want to or we can
reconnect next

**Ratul Shashank:** Okay,

**Geoff Horowitz:** week.

**Ratul Shashank:** I I will uh like there are a few things that I need
to wrap up. I will if I need it, I will drop in any message.

**Geoff Horowitz:** Cool. Thank you, Rachel. Appreciate it.

**Ratul Shashank:** Okay, Jeff.

**Geoff Horowitz:** All right.

**Ratul Shashank:** Thank you.

**Geoff Horowitz:** Byebye.

**Ratul Shashank:** Bye-bye.

### Transcription ended after 01:10:44

*This editable transcript was computer generated and might contain
errors. People can also change the text after it was created.*
