Jun 29, 2026

## Iris Sync

Invited [[Sachin Pandey]{.underline}](mailto:sachin@crescer.ai)
[[Pratyaksh Singh]{.underline}](mailto:pratyaksh@crescer.ai) [[Niveta
Iyer]{.underline}](mailto:niveta@crescer.ai) [[Hemanth
Sarabu]{.underline}](mailto:hemanth@crescer.ai) [[Geoff
Horowitz]{.underline}](mailto:geoff@crescer.ai) [[Siddharth
Soni]{.underline}](mailto:siddharth@crescer.ai) [[Ratul
Shashank]{.underline}](mailto:ratul@crescer.ai)

Attachments [[Iris
Sync]{.underline}](https://calendar.google.com/calendar/event?eid=NnNzMHVxNzk3MmJqZGVwNXFoN2J1Mjd1OTdfMjAyNjA2MjlUMTYzMDAwWiBnZW9mZkBjcmVzY2VyLmFp)

Meeting records
[[Transcript]{.underline}](https://docs.google.com/document/d/1OLB94qVIkpzWHTOVPTS7o4NxaSIJcPTLcdjFu7ojZlM/edit?usp=drive_web&tab=t.gfumccjmj8ki)

### Summary

Technical workflow review finalized the removal of water columns and
established documentation standards for data analysis.\
\
**Data Processing and Strategy**\
The team finished labeling and synthetic data generation, focusing on
robust augmentation. They debated using waterfall images versus
georeferenced ones for better model accuracy.\
\
**Water Column Processing Decision**\
Participants decided to remove the water column or nad zone from the
pipeline to improve efficiency. This change will be communicated to
relevant stakeholders for alignment.\
\
**Annotation Verification and Documentation**\
The team confirmed apparent contacts in the water column were likely
positional errors rather than genuine objects. They also planned a
session to standardize process documentation methods.

### Decisions

Aligned

-   **Water column imagery removal approved** The team will remove the
    > water column from processed imagery to optimize computational
    > efficiency, pending notification of the stakeholder.

We\'ve **updated the Decisions section** using your feedback.

Let us know what you think:
[[Helpful]{.underline}](https://google.qualtrics.com/jfe/form/SV_5p6FWBVWvynleNU?isGoogler=no&isHelpful=yes)
or [[Not
Helpful]{.underline}](https://google.qualtrics.com/jfe/form/SV_5p6FWBVWvynleNU?isGoogler=no&isHelpful=no)

### Next steps

-   \[Geoff Horowitz\] Coordinate Mag Data Meeting: Coordinate a time
    > with Hemanth Sarabu to discuss the mag data with Bridget.

    > \[Geoff Horowitz\] Notify Bridget: Inform Bridget that the team
    > will be removing the water column from the data analysis.

    > \[Sachin Pandey\] Verify Annotations: Verify if the Bridget
    > annotations match any objects present in the water column by
    > running the script.

    > \[Ratul Shashank\] Present Workflow: Present the personal workflow
    > and use of the obsidian tool for documentation.

    > \[Geoff Horowitz\] Schedule Workflow Meeting: Schedule a separate
    > meeting to discuss documentation workflows.

    > \[Sachin\] Verify Annotations: Re-examine and confirm the accuracy
    > of image metadata by checking problematic files, specifically
    > those similar to type 18.

### Details

-   **Opening and Administrative Coordination**: The meeting began with
    > the participants discussing their schedules, followed by Geoff
    > Horowitz providing an update on feedback received from Bridget
    > ([[00:02:23]{.underline}](#section)). Geoff Horowitz confirmed
    > receiving responses to open questions and requested to coordinate
    > a time with Hemanth Sarabu to discuss magnetometer data
    > ([[00:03:38]{.underline}](#section-1)). They agreed that if the
    > timing works, other team members will be included; otherwise, they
    > will record the session ([[00:05:07]{.underline}](#section-2)).

-   **Status of Labeling and Exploratory Data Analysis**: Pratyaksh
    > Singh provided an update on the labeling effort, stating that the
    > eXchangeable Teledyne Format (XTF) data for ENTX and DRN was
    > scheduled for completion either today or by tomorrow India time.
    > Regarding Exploratory Data Analysis (EDA), Pratyaksh Singh noted
    > that the team is largely finished with their current EDA tasks,
    > though Ratul Shashank is working on improvements to the XTF
    > scripts, which are not strictly required for the initial iteration
    > ([[00:06:52]{.underline}](#section-3)).

-   **Synthetic Data Generation and Model Training**: Pratyaksh Singh
    > reported that the synthetic data generation for the image side is
    > complete, and they are currently working on modifications to make
    > the process more robust for augmentation
    > ([[00:08:18]{.underline}](#section-4)). Pratyaksh Singh is
    > exploring how changes in intensity and noise generation from the
    > watershed (sonar scan) data might improve model robustness, with
    > plans to begin training once the data labeling is finalized
    > ([[00:09:35]{.underline}](#section-5)).

-   **Discussion on Georeferenced Imagery versus Waterfall Images**: A
    > technical discussion ensued regarding whether to use georeferenced
    > images or waterfall images for data processing . Pratyaksh Singh
    > proposed using waterfall images, noting that the georeferencing
    > process sometimes introduces visual artifacts or inconsistencies
    > compared to the raw waterfall data
    > ([[00:08:18]{.underline}](#section-4))
    > ([[00:16:48]{.underline}](#section-10)). Hemanth Sarabu expressed
    > concern that moving away from georeferenced imagery might
    > introduce distortions in how objects are represented due to the
    > Autonomous Underwater Vehicle (AUV) trajectory, whereas
    > georeferencing removes those variables
    > ([[00:11:59]{.underline}](#section-7))
    > ([[00:20:26]{.underline}](#section-13)).

-   **Decision on Water Column (Nad Zone) Removal**: Pratyaksh Singh
    > suggested removing the \"nad zone\" (the water column between the
    > submarine and the surface) from the data processing pipeline to
    > save compute resources and reduce complexity
    > ([[00:28:05]{.underline}](#section-19)). Hemanth Sarabu and Geoff
    > Horowitz agreed with this approach, noting that it should not
    > negatively affect accuracy, and Geoff Horowitz committed to
    > informing Bridget of this change to their analysis
    > ([[00:29:12]{.underline}](#section-20)).

-   **Verification of Annotations within the Water Column**: The team
    > discussed whether Bridget\'s annotations, which indicated contacts
    > within the water column, were accurate or the result of positional
    > errors ([[00:32:30]{.underline}](#section-23)). Sachin Pandey
    > noted that the file Bridget shared does not show contacts in that
    > area, and the team hypothesized that apparent contacts in the
    > water column were likely positional errors or overlaps from
    > multiple file scans ([[00:33:33]{.underline}](#section-24)).
    > Sachin Pandey committed to running the code to confirm whether the
    > nad zone contains meaningful data or if Bridget\'s annotations
    > were misplaced, with Geoff Horowitz assigning this task to Sachin
    > Pandey ([[00:34:39]{.underline}](#section-25)).

-   **Strategy for Presenting Synthetic Data to Bridget**: Geoff
    > Horowitz advised the team on the strategy for presenting synthetic
    > data to Bridget ([[00:35:48]{.underline}](#section-26)). The goal
    > is to provide a comprehensive overview that demonstrates the
    > synthetic data is representative of the real underlying data,
    > showing that the model\'s outputs (detections) on synthetic data
    > are comparable to those on real data, without revealing the
    > team\'s internal generation methodology
    > ([[00:37:25]{.underline}](#section-27)).

-   **Process Documentation and Workflow Sharing**: Geoff Horowitz
    > emphasized the importance of documenting processes more strictly,
    > citing Ratul Shashank\'s previous reports as a good example
    > ([[00:38:42]{.underline}](#section-28)). Ratul Shashank explained
    > their personal workflow, which involves using an Obsidian-based
    > tool to maintain a \"second brain\" for concepts and agent tasks
    > ([[00:40:06]{.underline}](#section-29)). The team agreed to
    > schedule a separate meeting on Friday or early next week for Ratul
    > Shashank to present their workflow, which others are welcome to
    > join ([[00:41:44]{.underline}](#section-30)).

-   **Review of Specific Annotations and Final Conclusions**: The
    > meeting concluded with a review of specific annotations in the EDA
    > document. Sachin Pandey clarified that some images showed
    > orientation changes or positional offsets, and they verified that
    > these were not genuine objects but rather errors. The team
    > confirmed the decision to cut out the water column and resolved
    > that Sachin Pandey would conduct a final verification of the
    > relevant annotations ([[00:44:13]{.underline}](#section-32))
    > ([[00:51:42]{.underline}](#section-37)).

-   **File and Annotation Type**: Sachin Pandey confirms that the files
    > under review are \"type 18,\" noting that they utilize the same
    > annotations and bounding boxes found in previous images
    > ([[00:57:07]{.underline}](#section-39)).

-   **Exploratory Data Analysis Data Pipeline**: Pratyaksh Singh and
    > Sachin Pandey review the status of the Exploratory Data Analysis
    > (EDA) pipeline, with Sachin Pandey confirming that the assessment
    > includes the number of points, the class map, the class
    > distribution, and the data collected .

-   **Bedrock Priority**: Pratyaksh Singh indicates that they are
    > assigning priority to the bedrock data, which Sachin Pandey
    > associates with the current annotations .

-   **Visual Data Characteristics**: Sachin Pandey characterizes the
    > visual elements of the dataset, identifying black circular shapes,
    > black lines, and black patches, and notes that the data merge
    > primarily involves these lines and patches .

-   **Object and Size Review**: Pratyaksh Singh and Sachin Pandey
    > discuss the necessity of checking objects and their appearance
    > sizes within the dataset . The conversation concludes with a
    > reference to continuing this communication via WhatsApp .

*You should review Gemini\'s notes to make sure they\'re accurate. [[Get
tips and learn how Gemini takes
notes]{.underline}](https://support.google.com/meet/answer/14754931)*

*How is the quality of **these specific notes?** [[Take a short
survey]{.underline}](https://google.qualtrics.com/jfe/form/SV_9vK3UZEaIQKKE7A?confid=H3BYsJg2qUJTW7exspPdDxIUOAIIigIgABgECA&detailid=standard&screenshot=false)
to let us know your feedback, including how helpful the notes were for
your needs.*

**📖 Transcript**

Jun 29, 2026

## Iris Sync - Transcript

### 00:02:23

**Hemanth Sarabu:** at all.

**Ratul Shashank:** Hello.

**Hemanth Sarabu:** Hey, how\'s it going?

**Ratul Shashank:** I\'m fine. What about you?

**Hemanth Sarabu:** Doing well. Doing well.

**Ratul Shashank:** How was your weekend?

**Hemanth Sarabu:** The weekend was pretty um pretty good. Pretty good.
How about yours?

**Ratul Shashank:** I can\'t say the same.

**Hemanth Sarabu:** Why? What happened?

**Ratul Shashank:** Um well most of my weekend was spent in trying to
fix my messed up sheep schedule.

**Hemanth Sarabu:** You\'re stupid.

**Ratul Shashank:** Nothing perfected.

**Hemanth Sarabu:** You okay? Wait,

**Ratul Shashank:** Uhhuh.

**Hemanth Sarabu:** this sounds exactly like such a

**Ratul Shashank:** That\'s why we are friends.

**Hemanth Sarabu:** Yeah.

**Ratul Shashank:** Hello guys.

**Geoff Horowitz:** You guys, what what were you doing that Sachin also
does?

**Ratul Shashank:** Uh we were just talking about how both of our sleep
schedules are messed up.

**Geoff Horowitz:** Introduce light.

**Ratul Shashank:** Uh how both of our sleep schedules is messed up.

**Geoff Horowitz:** Oh,

**Ratul Shashank:** Me and

**Geoff Horowitz:** oh, oh,

**Ratul Shashank:** Sachins.

**Hemanth Sarabu:** So, at some point, Roto is your sleep schedules are
not messed up.

### 00:03:38

**Geoff Horowitz:** yeah.

**Hemanth Sarabu:** They\'re just your sleep schedules.

**Ratul Shashank:** Yeah, I have made my peace with it.

**Hemanth Sarabu:** There you go.

**Ratul Shashank:** I mean, I can\'t sleep at night. I usually go go to
sleep around 6:00 in the morning.

**Hemanth Sarabu:** It\'s a good way to avoid traffic.

**Sachin Pandey:** All

**Ratul Shashank:** Yeah.

**Geoff Horowitz:** You know, Rachel, even I uh even I have a poor sleep
schedule. Sometimes I\'m up till 2 or 3, not quite 6:00 a.m., but uh

**Sachin Pandey:** right.

**Ratul Shashank:** I mean it it makes sense for you guys, right? You
guys have a lot to deal with.

**Geoff Horowitz:** Okay. Um, first things first, I sent everything to
Bridget. She she just like a few minutes ago, she said she responded to
some of the um our open questions. I haven\'t looked at them yet. I will
look at them later this afternoon uh and share them with everybody. But
she did ask if there\'d be a good time for us to connect uh on the mag
data this week.

### 00:05:07

**Geoff Horowitz:** Um so he I guess I guess it\'s primarily a question
for you.

**Hemanth Sarabu:** Yeah,

**Geoff Horowitz:** What does your schedule look like?

**Hemanth Sarabu:** I think we should do Okay, we can you and I can um
coordinate a time.

**Geoff Horowitz:** Yeah. And then I I guess guys,

**Hemanth Sarabu:** We can

**Geoff Horowitz:** if the if the timing works out, if it makes sense,
um I\'ll add you guys to the meeting. Otherwise, we\'ll we\'ll record
it. Um if it doesn\'t make sense, does that work?

**Hemanth Sarabu:** That\'s

**Geoff Horowitz:** Okay. Um, that was the primary stuff from Bridget\'s

**Hemanth Sarabu:** Move.

**Geoff Horowitz:** side actually. Okay. Okay. Um, that\'s what I had.
Where? So, somebody sent me uh Pratak, where are we on um initial
labeling? Um is there any more EDA that we feel like we need to do? Uh
at least where we are right now. That\'s question number two. And
question number three is where are we on the synthetic data?

**Pratyaksh Singh:** Hey, am I audible?

### 00:06:52

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** Yes.

**Pratyaksh Singh:** Uh, so for labeling effort, I think ants was left.
I think VW vineyard wine has been completed and then ants and DRN they
were left. I think they should have been completed today. Uh,

**Geoff Horowitz:** Sorry, Pax. Could you just say that?

**Pratyaksh Singh:** one was I think it should have been

**Geoff Horowitz:** Could you say that once

**Hemanth Sarabu:** Yeah, the your

**Geoff Horowitz:** more?

**Pratyaksh Singh:** complet.

**Hemanth Sarabu:** out

**Geoff Horowitz:** Okay, here. Let me open this up while we\'re

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** waiting.

**Pratyaksh Singh:** So what I was saying is that for the first question
there was there was some labeling left for uh ENTX and DRN data that
should have been done today if not it will be done tomorrow India time
and for for

**Geoff Horowitz:** Hey

**Pratyaksh Singh:** more EDA I think we are mostly done with EDF we are
mostly done with EDF there are few things that are uh we are trying out
I think Ratul is working on it. We\'re trying to improve the XTFS but uh
that won\'t be needed for the initial iteration.

### 00:08:18

**Pratyaksh Singh:** We also found out that uh the the script that they
gave us this was mostly this was that the script that okay that Bridget
gave us was just

**Geoff Horowitz:** Mhm.

**Pratyaksh Singh:** using was just using the water it wasn\'t geo
reference and I think this is how we should also proceed because we can
georreerence after our model makes prediction The advantage of having
something like this was that uh those weird examples that we were seeing
where there were these circular circular uh circular turns of the bridge
of the board those aren\'t there. So it simplifies things for us. I
think Sachin can share more example on this. Regarding synthetic data
generation I am working on it. I think for uh image for image side of
things that is done. Uh I can I I modified the previous one where you
know we are just copy pasting the annotation. I will see if uh once we
have the annotation I will see if that needs more work but I think
tomorrow it should be finished and I\'m working I am I\'m thinking of
generating the data or modifying things in the in the

### 00:09:35

**Geoff Horowitz:** Great.

**Pratyaksh Singh:** XP so that it works as an augmentation it is more
robust what I mean by that is uh even when we generate the image right
the image the images aren\'t pure image they are generated from the
waterershed right so uh I was I was you know exploring what if we change
the waterershed you know how the image will change if we change the
intensity of the values so that is something that I have to explore but
I think for for real

**Geoff Horowitz:** Right.

**Pratyaksh Singh:** phase

**Geoff Horowitz:** I just want to confirm when you when you\'re saying
watershed, you mean this image, right?

**Hemanth Sarabu:** He means a lot of

**Pratyaksh Singh:** so this is not yeah oh yeah that\'s called photo

**Geoff Horowitz:** So, what what do you mean?

**Hemanth Sarabu:** ball.

**Pratyaksh Singh:** of so okay so what I mean by

**Geoff Horowitz:** What do you mean when you say watershed?

**Pratyaksh Singh:** that is uh it doesn\'t give you image right the
solar the solar scan it doesn\'t give you image it gives you pings right
you convert those pings to

**Geoff Horowitz:** Right.

### 00:10:43

**Pratyaksh Singh:** image right so I was exploring

**Geoff Horowitz:** Right. Yes.

**Pratyaksh Singh:** uh artificially maybe artificially trying to
artificially generate those things add noise to them so that uh our
model is robust to this uh pings to image conversion too. So for example
adding noise in the pings will be different than I think may be
different than adding noise in the image too. But I think that this will
be iteration two. I think when the data once the data labeling is done
which should be done by tomorrow

**Geoff Horowitz:** got

**Pratyaksh Singh:** uh we I can I can start training the model.

**Geoff Horowitz:** it. Um, go ahead.

**Hemanth Sarabu:** But um you

**Geoff Horowitz:** Go ahead.

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** mentioned not using geo referenced um images.

**Pratyaksh Singh:** Seven.

**Hemanth Sarabu:** So I think I think we made a conscious choice to use
your referenced images the first time around.

**Pratyaksh Singh:** Yeah. Uh,

**Hemanth Sarabu:** Now I

**Pratyaksh Singh:** as far as I remember. Oh, sorry. I was just I was
just uh trying to put the reason we made those choice.

### 00:11:59

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** That was because they needed the output as shape
file. which was your reference. That\'s why I think I think we made this
choice.

**Hemanth Sarabu:** Um,

**Geoff Horowitz:** It is the case that Bridgette wanted contacts like
reference with session. What was it? Latl long. Was that it?

**Hemanth Sarabu:** Yeah, they have to be geio reference.

**Geoff Horowitz:** Yeah.

**Hemanth Sarabu:** That\'s for sure. My concern project is that things
may not appear like objects like objects that are in the in the 3D or 2D
world will get

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** morphed if the AU au returns,

**Pratyaksh Singh:** And the pink

**Hemanth Sarabu:** right? Um or if there is roll and things like that.
I think so. I I don\'t know. My my gut says we lose some things we take
for granted when we don\'t georreerence. Um including including
potentially how do we do we do you

**Pratyaksh Singh:** Hey. Uh, so let\'s let\'s agree on one thing. Do we
agree agree on one thing that if the board moves in a straight line then
it doesn\'t matter if we georreerence it or or if you know or or if you
don\'t.

### 00:14:00

**Pratyaksh Singh:** Do you agree with it?

**Hemanth Sarabu:** Um, but the so the vehicle doesn\'t always Okay. So
even if you move in a straight line, it does roll. It will uh pitch up
and down you know and then it\'ll

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** roll from side to side. It can do other motions. Now
it is possible that for a lot of the data sets there\'s that

**Pratyaksh Singh:** Hey

**Hemanth Sarabu:** motion is not prevalent but um

**Pratyaksh Singh:** Just wanted to point out that the current
implementation that we use we don\'t we don\'t consider these cases of
role and all these things. uh the only the way that I have seen in sets
code for geo referencing is they will use the position of of the boat
right the x and y position of the boat the direction in which the boat
is moving and then using that direction he will choose the perpendicular
that would be your that would be your sonar direction right and using
that he will he will get the he will get the value as far Uh this is
what I got from his code.

### 00:15:31

**Pratyaksh Singh:** Uh I didn\'t see any any mention of role or any
other any other features. Uh he used velocity also but uh not ro. I will
have to confirm with him but I think Sachin and they also went through
the so they can also comment there but I will I will confirm with

**Hemanth Sarabu:** Okay. So velocity is another thing but what what is
the look I\'m open to trying it

**Pratyaksh Singh:** it.

**Hemanth Sarabu:** out I just don\'t what is the reason for um
waterfall and also do you does it look different if you\'re um lower
higher you know

**Pratyaksh Singh:** Uh, what do you mean by lower or higher?

**Hemanth Sarabu:** So, um, if you\'re lower in the water, you\'re
versus higher in the water,

**Pratyaksh Singh:** Good.

**Hemanth Sarabu:** right?

**Pratyaksh Singh:** Yeah,

**Hemanth Sarabu:** What does that mean?

**Pratyaksh Singh:** the slant. Mhm.

**Hemanth Sarabu:** Hm.

**Pratyaksh Singh:** The slant. Yeah,

**Hemanth Sarabu:** H.

**Pratyaksh Singh:** I understood what you

**Hemanth Sarabu:** So my question is what what is the look like I said
I\'m not

**Pratyaksh Singh:** mean.

### 00:16:48

**Hemanth Sarabu:** uh saying we shouldn\'t do waterfall. I\'m trying to
understand why we want to switch from georreerenced imagery to uh

**Pratyaksh Singh:** the water.

**Hemanth Sarabu:** waterfall.

**Pratyaksh Singh:** Okay. So there are two reasons. So one of the
reason that we started exploring this was because uh yeah in different
softwares we were basically seeing different images right uh in in some
open source software uh the same XTF looked different than what we
generated from our so this thing was happening so there was uh one thing
that we wanted to standardize everything that we should standardize uh
you know for for our RO EDS which will standardize how to convert XT up
to images. Then Jeff mentioned that we should use the one you know that
Bridget shared one implementation and we should we should you know
probably use that because this is what that they might have been using.
So this directly using watershed that comes from the implementation that
they share. So this was the primary reason that we started exploring it.
And then another reason that I want to try it out in maybe iteration two
or iteration three of the model is because such and you have those
images where uh there is turn and

### 00:18:14

**Ratul Shashank:** I have shared them in the comments.

**Pratyaksh Singh:** then it looks much okay. Yeah.

**Sachin Pandey:** It\'s also updated in the ID

**Pratyaksh Singh:** So all right. So him can you if you look in the
chat right so the right image is the one that is your reference that is
generated by our model uh that is generated by our code and then the
left one is just the water shed generated by the code that bridged.

**Hemanth Sarabu:** One second. Wait,

**Pratyaksh Singh:** Now the left one

**Hemanth Sarabu:** wait, wait. Sorry. Hey, hold on. The you just sent
the image.

**Pratyaksh Singh:** is

**Hemanth Sarabu:** It\'s It says um I won\'t be able to view it. Is it
possible to put it on Slack?

**Pratyaksh Singh:** okay. I can share my screen also. Meanwhile,

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** translation. All right. So this one this is what
the georreerence measure images right. This is what is generated from
the code that we used for previous iteration of

**Hemanth Sarabu:** Wait,

### 00:19:26

**Pratyaksh Singh:** bedroom. And this is what the waterfall images. And
the point is that you know this image is much in distribution.

**Hemanth Sarabu:** I see I see uh one image.

**Pratyaksh Singh:** And do you see the next

**Geoff Horowitz:** How about they just

**Hemanth Sarabu:** Oh, yeah. Yeah, yeah, yeah.

**Pratyaksh Singh:** one?

**Hemanth Sarabu:** I see it. I see it. Uh-huh. Mhm.

**Geoff Horowitz:** share

**Pratyaksh Singh:** the the image that looks like a square box, right?

**Hemanth Sarabu:** Yeah. Yeah, that\'s

**Pratyaksh Singh:** Just yeah, that\'s your reference.

**Hemanth Sarabu:** your

**Pratyaksh Singh:** And the left one is just the water. No surprises
here, right? My point is that, you know, this looks much in distribution
with the data that we\'re working with. So I want to make

**Hemanth Sarabu:** What do you mean by that?

**Pratyaksh Singh:** prediction.

**Hemanth Sarabu:** What do you mean it\'s much more in distribution
with the data we\'re working at?

**Pratyaksh Singh:** So most of our most of our data looks like this.
Even when you geo reference they look they look like two parallel they
look like two parallel uh you know two parallel stream of images stream
of gray

### 00:20:26

**Hemanth Sarabu:** Yeah. Right.

**Pratyaksh Singh:** scale right so this is

**Hemanth Sarabu:** Okay. But my but tr truly it\'s

**Pratyaksh Singh:** what

**Hemanth Sarabu:** not they\'re not the same thing, right?
geometrically. If you have a rock at in that corner, it\'ll let\'s say
it\'s a rock in real life, it\'s circular. The moment you do this, it
becomes like this oblong shape, right? You\'ll you\'ll kind of you um
you you\'ll kind of what is the word I\'m looking for?

**Pratyaksh Singh:** Okay.

**Hemanth Sarabu:** You\'ll kind of twist it open. Um you\'ll elongate
it. So I I don\'t actually you know like I don\'t actually think uh so
it does a couple of things. One is we switch everything to this water.

**Pratyaksh Singh:** What?

**Hemanth Sarabu:** Um okay let let me take a step back. The reason uh I
can be convinced either way but I I\'m just looking for the reasons to
be convinced. Um the reason I like um georreerence is because you once
you put it in world coordinates um there is no more confusion about how
the object is supposed to look.

### 00:21:53

**Hemanth Sarabu:** It is not it is not that dependent on the trajectory
of the AUV. Whereas with the waterfall image, it is very dependent on
the trajectory of the AUV. So we have these multiple factors. Does that
make sense? So waterfall distributions, waterfall data depend on AUV
trajectory quite a bit. And of course the whatever is happening in the
seabed right whereas the J reference one removes that one variable
largely right like we should correct for

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** roll pitch velocity etc once you correct for it
those images are uh shouldn\'t be that are invariant to au trajectory so
that\'s why I think that is a simpler way to consume uh this data And
also you know like objects look like objects in in

**Pratyaksh Singh:** Thank you.

**Ratul Shashank:** Okay.

**Hemanth Sarabu:** in in real in kind of these real coordinates. Uh in
waterfall this is a new this is kind of a new system right a new uh
projection of uh the real world.

**Pratyaksh Singh:** All right. I agree with you here. I agree with you.

### 00:23:17

**Pratyaksh Singh:** But see, there is one thing that we there I I may
be wrong. I am just I\'m just thinking out loud. So there is one thing
that uh does it matter to the sonar sensor that you use right how the
object look in the real world or you know do we want to capture how does
the sonar behaves with the intensity

**Hemanth Sarabu:** So, let\'s let\'s take Um, let\'s say we\'re talking
about a circular or a square shaped object at

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** the on the seabed. Okay. Now,

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** you do a a waterfall. Depending on what trajectory
the AUV took,

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** that same object is going to look different in your
waterfall.

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** Right? Do you believe that?

**Pratyaksh Singh:** Uh yeah, let me draw it over here.

**Hemanth Sarabu:** Depending on how Yeah.

**Pratyaksh Singh:** So let\'s say this is the object, right?

**Hemanth Sarabu:** Yeah. Now,

**Pratyaksh Singh:** And then I think if I was saying that if you go
straight,

**Hemanth Sarabu:** if there isn\'t Mhm.

### 00:24:25

**Pratyaksh Singh:** it doesn\'t matter, right? If you just pass through
straight,

**Hemanth Sarabu:** Correct.

**Pratyaksh Singh:** it doesn\'t matter. Okay?

**Hemanth Sarabu:** Correct. If you pass this trade,

**Pratyaksh Singh:** So let\'s forget about this one now.

**Hemanth Sarabu:** it doesn\'t matter.

**Pratyaksh Singh:** But if it turn around this here, right? If it turns
something like this,

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** right?

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** Now what will happen is that it will hit it here.
High intensity. High intensity high intensity and your point is that
when you when we geo reference it okay I\'m stopping

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** should

**Hemanth Sarabu:** So when you when you do the waterfall, it looks like
a longer you just basically made it longer, right? You\'ve been taking
these section that are running along kind of the this outer

**Pratyaksh Singh:** and

**Hemanth Sarabu:** circumference uh the left uh left like far I don\'t
know what to call it.

**Pratyaksh Singh:** finish.

**Hemanth Sarabu:** um which won\'t won\'t happen if you do
georreerencing correctly. So the same object now looks different
depending on how the AUV traveled around it which

### 00:25:33

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** which means like you just have more variation in
your data for the same um object.

**Pratyaksh Singh:** Yeah, I agree with you. I agree with you. And yeah,
one more point that I forgot to mention is okay. So what we initially
thought of was to just you know these kind of terms we will just use no
prediction because there is no label there and our labelers aren\'t able
to find it in these kind of things. Right? And there is one more thing
that we wanted to try out which we discussed

**Hemanth Sarabu:** So, wait, wait, wait. Going back to that,

**Pratyaksh Singh:** yesterday.

**Hemanth Sarabu:** you\'re saying you\'re saying with all instances of
these short um short laps, short circuits short square circuits. The
labelers have not found any contacts. Okay,

**Pratyaksh Singh:** Yes.

**Hemanth Sarabu:** that\'s fine. We don\'t we don\'t uh we don\'t
actually consume um we don\'t actually consume anything like this,
right?

**Pratyaksh Singh:** uh there are very few examples of this and I

**Hemanth Sarabu:** Are we able to consume images like this?

### 00:27:08

**Pratyaksh Singh:** don\'t think so there are very because even in the
extended data that they gave us there are very few images like these
they in the in in the VW data

**Hemanth Sarabu:** Oh, okay.

**Pratyaksh Singh:** set there weren\'t any images like this as far as I
remember in the ants data set there are few images that\'s when we
encountered this this kind of thing and I think did an extensive review
on why things look like this and another reason that I wanted to go to
watershed was why do I keep calling it water I meant waterfall is that
when you georreerence the data with slant collection and all these
things what happens is that you have image like this right you\'ll have
one row right and then you will have another row Okay. Right.

**Hemanth Sarabu:** Another. Sorry. Sorry. Wait. You have one.

**Pratyaksh Singh:** And so you have this starboard kind.

**Hemanth Sarabu:** What?

**Pratyaksh Singh:** Uh I\'m just I\'m just trying

**Hemanth Sarabu:** Yeah. Yeah.

**Geoff Horowitz:** row. Row.

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** He said

### 00:28:05

**Pratyaksh Singh:** to and

**Hemanth Sarabu:** Yeah. Rope. Okay.

**Geoff Horowitz:** row

**Pratyaksh Singh:** you\'ll have this gap in between, right? This gap
is where your ship passes through, right? And when you georreerence it,
georreerence it,

**Hemanth Sarabu:** Right.

**Pratyaksh Singh:** you can have uh maybe other variation of it. the
ship going like this or in any in any direction right but you will have
these two rows kind of thing. Now the gap in between adds you know one
more place where the model fails uh I mean where the model might fail
and we need to augment for it is that this gap can be small or this gap
can be large also

**Hemanth Sarabu:** Right. That depends on height.

**Pratyaksh Singh:** right what that depends on it that is that depends
on height now what I was thinking is what if we remove this gap

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** and then stack them side by side and then you know
have this as an image and then remove the whole gap

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** completely.

**Hemanth Sarabu:** What is the reason for this?

### 00:29:12

**Pratyaksh Singh:** Uh the reason for this is just you know uh the gaps
usually don\'t have anything right you are wasting compute and you\'re
adding one more complexity with that that

**Hemanth Sarabu:** Right. Okay.

**Pratyaksh Singh:** is

**Hemanth Sarabu:** I mean I I agree with uh I agree with that. I mean
Yeah.

**Geoff Horowitz:** Yeah, pach there\'s even another benefit which is if
there is something you know if there is like a group of fish or
something in the water column that shows up right we don\'t want to we
don\'t want to detect that so removing this

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** We we I think I I I I don\'t I I\'m in support of
this, but Jeff, maybe we need to let Bridget know

**Geoff Horowitz:** that that we won\'t detect things in the water

**Hemanth Sarabu:** that.

**Geoff Horowitz:** column.

**Hemanth Sarabu:** Yeah, we\'re basically deleting the water column
from our uh

**Geoff Horowitz:** I\'ll make a note to to run it by her.

**Hemanth Sarabu:** analysis.

**Geoff Horowitz:** I also think it\'s worthwhile he I think this is
probably what you would say too. I think it\'s worthwhile to to just see
how how this affects performance, right?

### 00:30:15

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** Um and then make a

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** Wait,

**Hemanth Sarabu:** I it shouldn\'t affect accuracy as much as it does
compute stuff,

**Geoff Horowitz:** decision

**Pratyaksh Singh:** guys.

**Hemanth Sarabu:** right?

**Pratyaksh Singh:** Hey, I think I\'m sorry about this,

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** but you you I think we weren\'t detecting anything
in the water

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** column here, but we we might start detecting it
here. Is this what you guys were discussing or did you guys were
discussing something else?

**Geoff Horowitz:** Wait, we were not detecting there, but we might in
the second

**Hemanth Sarabu:** No, no, no, no, no. Wait,

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** no. Uh this is basically our Bridget. She wants to
know if we make changes

**Pratyaksh Singh:** Uh-huh.

**Hemanth Sarabu:** like this to how we analyze the data. Now, okay, the
the black area is is the area between the submarine and

**Pratyaksh Singh:** Uh-huh.

**Hemanth Sarabu:** the and the uh surface.

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** Now,

**Pratyaksh Singh:** Finished.

**Hemanth Sarabu:** it is actually possible that it is actually possible
that you will see things in the black area like uh Jeff said,

### 00:31:26

**Pratyaksh Singh:** Uh-huh.

**Hemanth Sarabu:** you could see uh a school of fish there, you know,

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** that is floating between the surface there. They\'re
in between the surface and the AOE. You could also have a mast,

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** a ship\'s mast that is pretty tall, right? That
could appear in that black area.

**Geoff Horowitz:** right?

**Hemanth Sarabu:** Now, we haven\'t we actually haven\'t seen that
happen yet. And typically, the mast could have because you do multiple
passes, the mast will appear outside of that uh dead

**Pratyaksh Singh:** Hey,

**Hemanth Sarabu:** zone.

**Pratyaksh Singh:** I I need to confirm this but I think it explicitly
makes these zero these ned zones.

**Hemanth Sarabu:** He\'s he\'s already not uh he\'s already not using
it is your point.

**Pratyaksh Singh:** Yeah, he makes yeah I mean I mean he explicitly
makes them zero.

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** Uh

**Pratyaksh Singh:** Even if like uh for example if you\'ll just look at
the example that we were seeing here you see these these here these kind
of water column uh so this

**Hemanth Sarabu:** Wait, wait, wait.

### 00:32:30

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** one so you wait you see this right you see this uh
this is filled

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** right the nad is on here this is filled right but
in his

**Hemanth Sarabu:** Yeah. Yeah.

**Pratyaksh Singh:** images will mostly remove all of these will
explicitly remove all of these at least this is what I got from reading
if it\'s too big I wasn\'t but this is like what

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** I got from so I think it it the other thing will
happen that if you go to

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** waterfall images then uh like you know you will see
it if they are present

**Hemanth Sarabu:** Um,

**Pratyaksh Singh:** if you don\'t remove the I mean you

**Hemanth Sarabu:** is that desirable or is that not

**Pratyaksh Singh:** guys want to detect things and water column,

**Hemanth Sarabu:** desirable?

**Pratyaksh Singh:** right? And I think there are there were some
annotations in the in between, right? Sachin, there were some
annotations that Bridget mentioned in in the water column which for us
looked

**Sachin Pandey:** Yes.

**Pratyaksh Singh:** empty, right?

### 00:33:33

**Geoff Horowitz:** But Sachin,

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** I thought we said that for those those areas that
there were predictions in the water column,

**Pratyaksh Singh:** So

**Geoff Horowitz:** it it was it was really a positional issue, right?

**Sachin Pandey:** Yes.

**Geoff Horowitz:** And that when we got a similar

**Sachin Pandey:** Like the same same area was scanned into multiple
XDF.

**Hemanth Sarabu:** Hey guys,

**Geoff Horowitz:** Exactly.

**Hemanth Sarabu:** I got a drop.

**Sachin Pandey:** So we were able to find

**Hemanth Sarabu:** I have a I have a call.

**Geoff Horowitz:** Okay. Yep.

**Sachin Pandey:** So same area was captured in other XTF and we were
able to like drop the annotation there and it was working.

**Geoff Horowitz:** Hi.

**Sachin Pandey:** But the file that bridget share in the JSON
annotation that that specific file doesn\'t show anything

**Geoff Horowitz:** Let\'s file the purchase.

**Pratyaksh Singh:** Can we look at the water waterfall image for that
and then see if there is something there?

**Sachin Pandey:** waterfall

**Pratyaksh Singh:** So similar to this image that you guys generated

**Sachin Pandey:** No, it it will not contain anything because that area
is not even captured.

### 00:34:39

**Pratyaksh Singh:** uh uh how how do you know that is it is it from the
images that we see from the code that we that we use XTF to image

**Sachin Pandey:** Yes.

**Pratyaksh Singh:** modified.

**Sachin Pandey:** Yes.

**Pratyaksh Singh:** So see that\'s my point like I think S said removed
those things. I\'m not sure,

**Sachin Pandey:** So he told me like this naida range variable is
ignored and he will calculate

**Pratyaksh Singh:** but

**Sachin Pandey:** it from the xtf directly. So if you even pass or not,
if you pass the variable or not, it will ignore it and recalculate it in
the

**Pratyaksh Singh:** it but it masks it out, right?

**Sachin Pandey:** code.

**Pratyaksh Singh:** My point is that if it gots the natty range, it
will mask it out. Even if there is something

**Geoff Horowitz:** So can can\'t we confirm that easily by

**Pratyaksh Singh:** there.

**Sachin Pandey:** Okay.

**Geoff Horowitz:** running code?

**Sachin Pandey:** Yeah,

**Pratyaksh Singh:** Yeah, thank

**Sachin Pandey:** I can just run it on the script and on the same file.

**Geoff Horowitz:** Yeah.

**Pratyaksh Singh:** you.

**Geoff Horowitz:** Okay. So, in summary, in summary, let\'s confirm
that Bridget\'s annotations do not match up to something in the water
column.

### 00:35:48

**Geoff Horowitz:** That\'s the action item. Is that correct?

**Pratyaksh Singh:** Yes.

**Geoff Horowitz:** Okay.

**Pratyaksh Singh:** Yes.

**Geoff Horowitz:** Okay. And Saxon, that\'s on you, right?

**Sachin Pandey:** Just I\'m just checking it

**Geoff Horowitz:** Okay.

**Sachin Pandey:** out.

**Geoff Horowitz:** Um, anything else timesensitive that you guys want
to discuss? I have one other item. I\'ll take that as a no. Okay. Um, so
Project, you mentioned the synthetic data. Um, I think you know this,
but I\'m gonna I\'m going to remind you anyway that we told Bridget so
we were we were trying to do a little dance with her, which is she
wanted insight into how we were generating the synthetic data. We
didn\'t want to share that. Um, but what we told her was that we would
give a a a significant overview of the data we generated and why we
think it\'s well representative of why why we think it well it it
represents well the underlying data. Does that make sense? Um and we
proposed a few things I think you know showing showing the inputs

### 00:37:25

**Pratyaksh Singh:** Mhm.

**Geoff Horowitz:** um you know and showing how they\'re they\'re
representative of of the inputs that we have. Uh similarly showing that
the outputs are equally detectable by the model for both synthetic and
um and real data. This is all just something to keep in mind as you go
through this.

**Pratyaksh Singh:** Uhhuh.

**Geoff Horowitz:** Um, what? Go

**Pratyaksh Singh:** So I was saying the summary is that you want to
share some data

**Geoff Horowitz:** ahead.

**Pratyaksh Singh:** where it looks pretty good, right?

**Geoff Horowitz:** The summary is that we need to The summary is that
we need to share data that looks like it\'s good. Yes. But a little bit
deeper. we need to kind of we need to kind of convince her, right? So,
it\'s not just sharing the data. It\'s really kind of making an
argument. It\'s forming an argument that the inputs are right and the
outputs are right.

**Pratyaksh Singh:** for synthetic data. The output means from the
model.

**Geoff Horowitz:** The output meaning the detection from the model that
what the model is learning on the synthetic data is um is pretty darn
close to what it would

### 00:38:42

**Pratyaksh Singh:** Uh-huh.

**Geoff Horowitz:** learn on real data,

**Pratyaksh Singh:** Got it. Okay. Understood.

**Geoff Horowitz:** which I I look I I think we\'re going to do this
anyway, right? I think that it\'s a um I mean,

**Pratyaksh Singh:** Mhm.

**Geoff Horowitz:** I think we\'re going to do it anyway, right? Uh,
okay.

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** The reason that I bring this up is I don\'t know if
you guys have seen Rut tools reports. Let me share one of them. So, this
is one that that he made for like some of the mind detection stuff. Um,
and Ratul, maybe you can speak a little bit more about this, but uh, I
actually thought that this report did a pretty good job of summarizing
kind of our workflow, not our workflow, that\'s not what I\'m trying to
say, of summarizing what we tried and then what worked and what didn\'t
work. Um,

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** Mhm.

**Geoff Horowitz:** and I think it helps us remember. So, like when we
get back to to this stuff at the end, uh, you know, it\'ll it\'ll help
us kind of remember what we did and how we got there.

### 00:40:06

**Pratyaksh Singh:** Mhm.

**Geoff Horowitz:** Um, I\'m not sure that this is critical, Pratio,
because I think ultimately we just want to look at the end results. But
I bring this up, I don\'t know, honestly. I think I\'m bringing this up
because I think it would be useful for me to to be a little more
stringent about documenting process. Um, and that\'s it.

**Pratyaksh Singh:** Mhm.

**Geoff Horowitz:** I was thinking that maybe maybe be good for for all
of us too. Rul at some point Rul you\'re using what are you using?
You\'re using some um like Carpathy style um obsidian tool,

**Ratul Shashank:** uh actually uh yeah similar

**Geoff Horowitz:** right?

**Ratul Shashank:** uh as I shared in the interview, I just basically
created a few context files for my agent and my agent understands that
concept uh that concept and acts as a second brain for me. So that is uh
uh similar to what Andrew Andre Karpathi mentioned in his tweet just uh
in my style.

**Geoff Horowitz:** So, so Rachel, I I asked you about this before, but
for me at least, I think it\'d be beneficial to at least hear a little
bit more about your workflow and,

### 00:41:44

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** you know, which repos you implemented, how you\'re
doing it. Um, I don\'t know, Projection Suction, I don\'t know if you
guys think similarly, but but I\'m interested in at least hearing it.
Um, so maybe you

**Ratul Shashank:** Uh I would love I would love to share that.

**Geoff Horowitz:** could

**Ratul Shashank:** Uh so do you want me to present now

**Geoff Horowitz:** No,

**Ratul Shashank:** or

**Geoff Horowitz:** no. Can we schedule some time either let let\'s let
you and I connect. Um, but maybe we can schedule some time either like
Friday or early next week at

**Ratul Shashank:** Definitely.

**Geoff Horowitz:** work. Um, okay.

**Ratul Shashank:** Yes.

**Geoff Horowitz:** I mean, yeah, I\'m interested Sachin. I mean, I\'m
not going to throw this down your throats, right? We all we all have our
own uh working style, but you know, I think if you guys are interested
in hearing um you should join, too. We\'ll try to do a separate meeting.
Um, and if you\'re not, that\'s that\'s all right,

**Pratyaksh Singh:** Yeah,

### 00:42:47

**Geoff Horowitz:** too.

**Pratyaksh Singh:** I think it would be good. It would be good to see

**Geoff Horowitz:** Okay. Um, Rachel, I just need to I need to sort out
this. I need to find a time that we\'re going to meet with Bridget. Um,
but once I get that set, uh, yeah, I think either either Friday or next
week would be best.

**Ratul Shashank:** Yeah, just let me know. I will I will present my
work. No problem.

**Geoff Horowitz:** Sounds good. All right, that\'s all I had.

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** Anything else anybody else wants to bring up in in
the

**Sachin Pandey:** Yeah, Jeff, I I\'ve shared the images that you
wanted.

**Geoff Horowitz:** Bedrock channel where

**Sachin Pandey:** Oh, in the meat. Uh, the link is for the the old
pipeline and the images from

**Geoff Horowitz:** Okay.

**Sachin Pandey:** the background script.

**Geoff Horowitz:** Oh. Oh, I forgot. I shared the um I I hope you guys
saw it. I shared the document with Bridget\'s responses. So Sachin does
this I think her annotation was like somewhere around here.

### 00:44:13

**Geoff Horowitz:** Is that right?

**Sachin Pandey:** Uh, it\'s hard to tell because orientation also
change in this one. If you open the EDA doc, uh,

**Ratul Shashank:** I mean that is a problem with geio referenced
mosaics right it highly depends on the script that is used so waterfall
it\'s objective it will not change its orientation but georreerence
mosaic uh it highly depends on the

**Sachin Pandey:** We change it. Yes. Yeah, it is.

**Geoff Horowitz:** I bet you this is the contact.

**Sachin Pandey:** It is inverted.

**Geoff Horowitz:** I bet you this is the contact.

**Sachin Pandey:** Uh, no, it is not marked in the original image as
well.

**Geoff Horowitz:** No.

**Sachin Pandey:** contacts are little off. So Jeff the image you send
uh asking why why it is off. I checked the multiple images for that uh
like for that annotation in like most of the

**Geoff Horowitz:** Yeah.

**Sachin Pandey:** files it was like almost on the boundaries for the
specific file it was like almost out of the boundary but generally it

**Geoff Horowitz:** Which which nothing sorry keep

**Sachin Pandey:** is generally it is uh

### 00:45:32

**Geoff Horowitz:** going.

**Sachin Pandey:** like under the like range. It might be some like
error while like could be in anything but most of the pipeline are
correct.

**Geoff Horowitz:** Which which image am I looking at? Sergeant. This

**Sachin Pandey:** No.

**Geoff Horowitz:** one.

**Sachin Pandey:** uh you shared me in the chat like I shared you the
annotations of the file like all the files which have this annotation in
them and you were saying like it is little bit off and it is not
covering the exact

**Geoff Horowitz:** it. Sorry. I I agree with you there.

**Sachin Pandey:** area.

**Geoff Horowitz:** Uh I I hear what you\'re saying there. Before we
started talking about that, you mentioned that I should look in the EDA
doc for

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** the

**Sachin Pandey:** Uh if you go to the end uh no uh so

**Geoff Horowitz:** this

**Sachin Pandey:** if you see these two images you see the orientation
is changed and so so

**Geoff Horowitz:** Where\'s the contact though?

**Sachin Pandey:** contact for that you have to open the link that I
have attached with the images the link contains the original like our
pipeline

### 00:46:49

**Geoff Horowitz:** Ah, got it.

**Sachin Pandey:** And the corner was in the middle. And you see the on
the right hand side on the lower row there is the both are inverted like

**Geoff Horowitz:** Yeah,

**Sachin Pandey:** this.

**Geoff Horowitz:** I see it. So maybe this could be But this also
doesn\'t resemble any of the other contacts we\'ve seen, right? Like
most of the contacts we\'ve seen look something like this, not I mean
I\'m trying to I\'m trying to visualize this like vertically.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Um, here. How do I guess like vertically it would
look something like like that I guess, right? Like if that were the
seabed.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** And I don\'t think we\'ve seen anything of that
nature here.

**Sachin Pandey:** Yeah. This is something like that in the open source
in not the open source

**Geoff Horowitz:** Yeah.

**Sachin Pandey:** tool but not in our

**Geoff Horowitz:** Yeah.

**Sachin Pandey:** platform.

**Geoff Horowitz:** And Sachin, you you um where is it? Is it in the EDA
doc? you looked at a few of these where you uh where you tracked, you
know, that image elsewhere.

### 00:49:05

**Geoff Horowitz:** You know what I\'m trying to

**Sachin Pandey:** Yes. Yes.

**Geoff Horowitz:** say?

**Sachin Pandey:** Uh, it\'s not in the ADA doc.

**Geoff Horowitz:** I still have it open.

**Sachin Pandey:** Uh,

**Geoff Horowitz:** I don\'t have it open. Um and my point is, what\'s
my point? My point is like I think when we track it, it does look, you
know, something more akin to this, right?

**Sachin Pandey:** Yes. Uh I\'m trying to find the image. I will just
share it once I find it in the chat from this specific

**Geoff Horowitz:** Okay. Well,

**Sachin Pandey:** annotation.

**Geoff Horowitz:** so so hold on. So what\'s the outcome here? The
outcome is we were asking about whether or not it\'s okay to get rid of
the water column, right? That\'s where this stemmed. That\'s where this
discussion stemmed. whether it\'s okay to like remove this part and put
the images side by side. And to me, it still seems like the answer is
yes. Did you guys come to a different conclusion?

### 00:50:30

**Pratyaksh Singh:** Uh, sorry. You said you make sense to keep the
water image.

**Geoff Horowitz:** I said what what we were asking was do we need to
keep this water column section right and looking looking at this looking
at this

**Pratyaksh Singh:** Mhm.

**Geoff Horowitz:** I think my answer is no.

**Sachin Pandey:** I want to add one thing. So just you might be right.

**Geoff Horowitz:** Sure.

**Sachin Pandey:** The thing you are seeing on the top is actually the
the point of contact and uh yes and the our

**Geoff Horowitz:** It might be that this is a contact.

**Sachin Pandey:** annotation for this specific file is way off than any
other

**Geoff Horowitz:** Uhhuh. Could be.

**Sachin Pandey:** files because in all other files I am seeing this as
a contact and

**Geoff Horowitz:** Could be.

**Sachin Pandey:** annotation is very close to this and I\'m not seeing
any other object like this.

**Geoff Horowitz:** Uhhuh.

**Sachin Pandey:** So like I checked mult in multiple images but this is
the only contact I am I shared it in the chat

**Geoff Horowitz:** It\'s just Yeah, it\'s surprising that it Okay.

### 00:51:42

**Geoff Horowitz:** It\'s surprising that it takes such a big footprint,
right? Like it could be that this protrudes,

**Sachin Pandey:** also

**Geoff Horowitz:** you know, vertically, too, but it would the
footprint wouldn\'t change. It would still be vertically as like a it
would still share the same footprint, right? I think so.

**Sachin Pandey:** Yes,

**Geoff Horowitz:** Yeah.

**Sachin Pandey:** like we found a similar encount uh similar mistake in
other file also. Rul pointed it out with for I guess it was 18 something
18 type 18. Yeah, type 18 also has the same issue for the image. The
image on the also has the annotation in the dark like black region.

**Geoff Horowitz:** Okay.

**Sachin Pandey:** But the other images which we found are directly
overlapping the a point of contact with the

**Geoff Horowitz:** Okay. Okay.

**Sachin Pandey:** annotation.

**Geoff Horowitz:** So, I guess there\'s two outcomes here. Number one
is I mean unless you guys disagree, I don\'t think it\'s an issue to to
cut out this water column. That\'s number one. And number two,

**Sachin Pandey:** Yes.

### 00:52:51

**Geoff Horowitz:** yeah. And number two, Sachin, it sounds like it
would be a good idea to go back and double check or I guess in this case
it\'s triple check uh some of those annotations.

**Sachin Pandey:** Okay.

**Geoff Horowitz:** Okay, guys. Uh, unless there\'s anything else chat
on Wednesday.

**Sachin Pandey:** Okay.

**Geoff Horowitz:** Thanks, guys.

**Sachin Pandey:** Okay, bye-bye.

**Pratyaksh Singh:** Why is this

**Sachin Pandey:** Uh Patics uh update

**Pratyaksh Singh:** happen?

**Sachin Pandey:** 26.04 for open to update.

**Pratyaksh Singh:** I you know you\'re talking to I don\'t use

**Sachin Pandey:** But this uh

**Pratyaksh Singh:** huh

**Sachin Pandey:** but base kernel update is same for everything right.

**Pratyaksh Singh:** Linux kernel update me Linux kernel update

**Sachin Pandey:** Linux

**Pratyaksh Singh:** Oh, my palace is

**Sachin Pandey:** maybe

**Pratyaksh Singh:** right.

**Sachin Pandey:** important update. databasian.

**Pratyaksh Singh:** All right. Uhhuh. question. Okay.

**Sachin Pandey:** said agent experiment

**Pratyaksh Singh:** I missed

**Sachin Pandey:** localatically.

**Pratyaksh Singh:** experiment experiment in the sense discuss But I

**Sachin Pandey:** Huh?

**Pratyaksh Singh:** think

**Sachin Pandey:** Annotation

**Pratyaksh Singh:** the program

**Sachin Pandey:** screen. screen.

### 00:57:07

**Sachin Pandey:** Same cheese. Dark

**Pratyaksh Singh:** This file nos

**Sachin Pandey:** type 18. Type 18. Same annotation. Exact. image.
Hello bounding boxes. Most of the files

**Pratyaksh Singh:** Show the photo.

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** Thank

**Sachin Pandey:** Thank you.

**Pratyaksh Singh:** you.

**Sachin Pandey:** EDA Data

**Pratyaksh Singh:** Uh data

**Sachin Pandey:** scound

**Pratyaksh Singh:** pipeline. Uh how much

**Sachin Pandey:** number of points class map class distribution data
collected

**Pratyaksh Singh:** I take bedrock priority

**Sachin Pandey:** annotations.

**Pratyaksh Singh:** It\'s another time.

**Sachin Pandey:** Black circular shape.

**Pratyaksh Singh:** Thank you.

**Sachin Pandey:** black lines mainly class

**Pratyaksh Singh:** Just a

**Sachin Pandey:** or data merge mainly lines.

**Pratyaksh Singh:** moment.

**Sachin Pandey:** Black patches mainly. Sorry, black patches.

**Pratyaksh Singh:** How about you? Um,

**Sachin Pandey:** I was

**Pratyaksh Singh:** I don\'t think

**Sachin Pandey:** looking

**Pratyaksh Singh:** one_1 check

**Sachin Pandey:** object

**Pratyaksh Singh:** button. Size size

**Sachin Pandey:** appear size

**Pratyaksh Singh:** come

**Sachin Pandey:** size.

**Pratyaksh Singh:** WhatsApp

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** Listen.

**Sachin Pandey:** Okay. What? Okay. Right.

### Transcription ended after 01:03:49

*This editable transcript was computer generated and might contain
errors. People can also change the text after it was created.*
