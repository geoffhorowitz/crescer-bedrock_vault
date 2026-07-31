Jun 15, 2026

## Iris Sync

Invited [[Sachin Pandey]{.underline}](mailto:sachin@crescer.ai)
[[Pratyaksh Singh]{.underline}](mailto:pratyaksh@crescer.ai) [[Niveta
Iyer]{.underline}](mailto:niveta@crescer.ai) [[Hemanth
Sarabu]{.underline}](mailto:hemanth@crescer.ai) [[Geoff
Horowitz]{.underline}](mailto:geoff@crescer.ai) [[Siddharth
Soni]{.underline}](mailto:siddharth@crescer.ai)

Attachments [[Iris
Sync]{.underline}](https://calendar.google.com/calendar/event?eid=NnNzMHVxNzk3MmJqZGVwNXFoN2J1Mjd1OTdfMjAyNjA2MTVUMTYzMDAwWiBnZW9mZkBjcmVzY2VyLmFp)
[[Milestone 2 Presentation
\[presentation\]]{.underline}](https://docs.google.com/presentation/d/1VNj7VOYcbUpbjjINx6XYXp1F42sLuYk--5siks5oSSQ/edit?usp=drivesdk)
[[Bedrock SOW 2
Background]{.underline}](https://docs.google.com/presentation/d/1fwtCPUBYyHOogHWTAPvTH1JhRFpYK9E6ugt7S6ZVe6s/edit?usp=drivesdk)

Meeting records
[[Transcript]{.underline}](https://docs.google.com/document/d/1h4Q9neq-8yV7ugWItPg2GLmUM0PCwnC8hqLG6odny_s/edit?usp=drive_web&tab=t.ibvs10ti8sup)

### Summary

The team aligned on Bedrock project objectives and synthetic data
pipelines for model improvement and scheduling.\
\
**Demo and QA Status**\
The team finalized demo board files and set manual cleaning protocols
for data artifacts. Staffing adjustments were made to ensure project
continuity and support for ongoing tasks.\
\
**Bedrock Project Strategy**\
Leadership greenlit the Bedrock project with a 4 to 6 week deadline for
an initial product. The team prioritized exploratory data analysis and
synthetic data generation pipelines.\
\
**Pipeline and Planning**\
Members committed to parallel execution of tasks and documenting
priorities. The group decided to include open source data in exploratory
data analysis to streamline baseline development.

### Decisions

Aligned

-   **Ratul Shashank assigned to Bedrock project** Ratul Shashank is
    > assigned to prioritize Bedrock-related tasks to support the
    > team\'s capacity for the project.

-   **Manual smoothing process for data artifacts** The team will handle
    > problematic bathymetric surface areas via manual smoothing to
    > ensure consistency with prior project outcomes.

-   **Prioritization of Bedrock EDA** The project execution strategy is
    > set to prioritize Exploratory Data Analysis (EDA) on the Bedrock
    > dataset before initiating model training.

-   **Restart of EDA process** The team will perform a full restart of
    > the EDA process due to insufficient documentation of previous
    > efforts.

-   **Team workflow and workload allocation** The team workflow is
    > structured with Pratyaksh focusing on synthetic data and R&D,
    > while Sachin focuses on model training and EDA for the Bedrock
    > project.

-   **Expanded scope for EDA process** The team decided to include old
    > BRX data, new BRX data, and open-source data within the scope of
    > the Exploratory Data Analysis (EDA) process.

We\'ve **updated the Decisions section** using your feedback.

Let us know what you think:
[[Helpful]{.underline}](https://google.qualtrics.com/jfe/form/SV_5p6FWBVWvynleNU?isGoogler=no&isHelpful=yes)
or [[Not
Helpful]{.underline}](https://google.qualtrics.com/jfe/form/SV_5p6FWBVWvynleNU?isGoogler=no&isHelpful=no)

### Next steps

-   \[Geoff Horowitz\] Call Ben: Contact Ben to discuss block 1 and 2
    > feedback.

    > \[Geoff Horowitz\] Share Ben Feedback: Provide the team with any
    > immediate feedback received from the call with Ben.

    > \[Sachin Pandey\] Finish File QA: Complete the quality assurance
    > process for the remaining 13 to 14 files.

    > \[Geoff Horowitz\] Update Data Documentation: Collaborate with Sid
    > to update the open source data documentation.

    > \[The group\] Document EDA Plans: Maintain extensive documentation
    > for all project thought processes to facilitate parallel task
    > execution.

    > \[The group\] Perform Bedrock EDA: Execute the initial Exploratory
    > Data Analysis for the Bedrock project over the next 2 days.

    > \[Pratyaksh Singh, Sachin Pandey\] Update Project Slides: Review
    > the project slides and insert task durations. Update the
    > documentation to reflect necessary changes and missing plan
    > details.

    > \[Pratyaksh Singh, Sachin Pandey\] Share Priorities: Draft a Slack
    > message detailing individual work focus areas for the next 2 to 3
    > days.

    > \[Pratyaksh Singh\] Share Training Pipeline: Modify the auto
    > quality control training pipeline used for the Iris project.
    > Distribute the setup details after completion.

### Details

-   **Demo Board File Updates**: Pratyaksh Singh and Sachin Pandey
    > discussed the inclusion of specific files on the demo board, with
    > Pratyaksh requesting that Sachin move the files where the model
    > performed well into the example folders to complete the setup.
    > They also confirmed that the current examples were sourced from a
    > specific cluster and discussed the status of running tests on
    > class two and four ([[00:07:01]{.underline}](#section)).

-   **Project Resourcing and Ratul's Integration**: Geoff Horowitz
    > introduced Ratul Shashank to the team, explaining that Ratul would
    > assist the group to free up capacity for the Bedrock project.
    > Geoff stated that Ratul would work in whatever capacity the team
    > found most helpful, ensuring the team\'s current workflow remained
    > supported ([[00:09:07]{.underline}](#section-1)).

-   **Communication with Ben Regarding Block One and Three**: Geoff
    > noted that they had not yet received feedback from Ben regarding
    > block one and stated that they planned to wait until Ben finished
    > reviewing \"blocker\" before sending block three. Geoff committed
    > to calling Ben to request feedback and indicated they would share
    > any updates with the team, ideally scheduling a joint call for
    > further detail ([[00:10:28]{.underline}](#section-2)).

-   **Status of Block Three QA**: Sachin reported that approximately 13
    > to 14 files remained for block three. While the labelers had
    > addressed clear errors, they left behind areas that were confusing
    > or difficult to fix; Sachin planned to review these remaining
    > files and estimated completing the task within a few hours
    > ([[00:11:37]{.underline}](#section-3)).

-   **Handling Data Artifacts and Visual Cleaning**: Sachin shared
    > examples of problematic data where water surface movement caused
    > artifacts and noise ([[00:14:57]{.underline}](#section-5)). The
    > team discussed whether to leave these areas as they were or
    > manually clean them using cross-sections and point removal
    > ([[00:16:37]{.underline}](#section-6)). Geoff and the team agreed
    > that if no better solution existed, they should maintain
    > consistency with the approach used for block two, which involved
    > manually smoothing corners. Sachin estimated that this manual
    > cleaning process would take approximately 10 to 15 minutes per
    > tile, noting there were only two such tiles
    > ([[00:21:25]{.underline}](#section-8))
    > ([[00:25:07]{.underline}](#section-10)).

-   **Demo Data Preparation and Synthetic Data Validation**: Pratyaksh
    > clarified that the plan for automated QA involved conducting
    > synthetic data validation after the demo. For the upcoming
    > presentation, they planned to show tiles where the model performed
    > better, and Sachin was in the process of adding these files to
    > ensure readiness for the demo within a 24-hour window
    > ([[00:27:59]{.underline}](#section-12)).

-   **Project Bedrock Overview and Objectives**: Geoff provided context
    > on the Bedrock project, noting that they had received the go-ahead
    > to proceed with the work ([[00:31:37]{.underline}](#section-15)).
    > The primary goal is to produce a minimum viable product (MVP) in
    > four to six weeks, targeting completion around August 1st
    > ([[00:33:00]{.underline}](#section-16)). Hemanth Sarabu outlined
    > the high-level themes, which include retraining the model on a
    > new, under-represented class (explosives), developing a synthetic
    > data generation system, and addressing artifacts caused by the
    > rolling motion of the vessel
    > ([[00:35:08]{.underline}](#section-17)). Future milestones may
    > involve the use of magnetic (MAG) data if it is deemed necessary
    > for detection, with Bedrock agreeing to provide training on
    > interpreting and simulating MAG data
    > ([[00:38:00]{.underline}](#section-19)).

-   **Bedrock Project Management and Context Switching**: Hemanth and
    > Geoff invited the team to lead the planning for project execution
    > to avoid the inefficiencies of context switching
    > ([[00:40:45]{.underline}](#section-21)). Pratyaksh suggested
    > extensive documentation to facilitate picking up tasks after
    > switching between projects. The team agreed that they should
    > prioritize Exploratory Data Analysis (EDA) on the Bedrock data to
    > build familiarity before moving on to modeling, which would then
    > allow time to manage other projects in parallel
    > ([[00:43:27]{.underline}](#section-23)).

-   **Resource Allocation and Parent Model QC**: Pratyaksh explained
    > that while the data collection for the parent ground model was
    > complete, a final round of quality control (QC) by labelers was
    > required to ensure the digital elevation models (DEMs) met
    > expectations. Pratyaksh planned to spearhead the Iris point cloud
    > work while delegating image-based tasks to Sachin to help them
    > build relevant skills ([[00:46:16]{.underline}](#section-25)).

-   **Exploratory Data Analysis Strategy for Bedrock**: The team decided
    > to restart the EDA process for the Bedrock data, with Pratyaksh
    > estimating it would take one or two days to complete
    > ([[00:50:39]{.underline}](#section-28)). Hemanth and the team
    > agreed that initial data review should not exceed a few days
    > ([[00:52:14]{.underline}](#section-29)).

-   **Review of Previous Model Training Architecture**: In discussing
    > model training options, Pratyaksh recalled that for previous
    > iterations, they had trained models including ResNet 18, 34, and
    > 50, with ResNet 50 being the largest
    > ([[00:53:27]{.underline}](#section-30)).

-   **Data Volume and Labeling Logistics**: Geoff noted that there were
    > approximately 200 files in the new data set, excluding Vineyard
    > Winds and open-source data
    > ([[00:56:00]{.underline}](#section-32)). Pratyaksh and Hemanth
    > discussed the need to allocate labelers effectively, with
    > Pratyaksh expressing a preference for completing the QC work
    > quickly ([[00:58:06]{.underline}](#section-34)). It was noted that
    > other labelers were currently assigned to the Boommy project, but
    > their work would not be severely impacted by a slight delay,
    > allowing them to be pulled for Bedrock tasks if necessary
    > ([[00:59:43]{.underline}](#section-35)).

-   **Project Execution and Task Delegation**: Hemanth encouraged
    > Pratyaksh and Sachin to make \"game-time decisions\" regarding the
    > allocation of labelers ([[00:58:06]{.underline}](#section-34)).
    > The team agreed to attempt parallel execution of tasks, with
    > Pratyaksh suggesting that Sachin take ownership of specific EDA
    > tasks to build capacity while Pratyaksh focused on the
    > complexities of synthetic data generation and updating the
    > training pipeline ([[01:01:34]{.underline}](#section-36)).

-   **Synthetic Data Pipeline and Experimentation**: Hemanth Sarabu and
    > Pratyaksh Singh discussed the development of the synthetic data
    > generation and training pipeline
    > ([[01:05:34]{.underline}](#section-39)). Pratyaksh Singh suggested
    > setting up a training pipeline for Iris that could potentially be
    > used for Bedrock, though Hemanth Sarabu expressed uncertainty
    > regarding the transferability of this process
    > ([[01:07:10]{.underline}](#section-40)). To address this,
    > Pratyaksh Singh committed to creating a flexible pipeline that
    > allows for multiple experiments to run, facilitating the
    > comparison of results while modifying parameters like Iceberg
    > ([[01:08:21]{.underline}](#section-41)). Hemanth Sarabu suggested
    > a structure where Pratyaksh Singh focuses on synthetic data
    > research and development while simultaneously setting up initial
    > components so the rest of the team can continue the work
    > ([[01:09:44]{.underline}](#section-42)).

-   **Project Planning and Review**: Hemanth Sarabu emphasized that the
    > team must prioritize hitting the week six target
    > ([[01:05:34]{.underline}](#section-39)). Hemanth Sarabu requested
    > that the team review the project slides, add durations, and make
    > any necessary changes to the plan within the next hour to ensure
    > the information is accurate and fresh
    > ([[01:09:44]{.underline}](#section-42)). Hemanth Sarabu noted that
    > while the current plan is important, it is acceptable to change
    > details later as the project evolves
    > ([[01:11:04]{.underline}](#section-43)).

-   **Team Priorities and Slack Communication**: Hemanth Sarabu
    > requested that team members define their priorities for the next
    > couple of days. Pratyaksh Singh confirmed a focus on Bedrock and
    > synthetic data, while Sachin Pandey identified priorities
    > including Tetra Tech, S7K, and Bedrock. Hemanth Sarabu instructed
    > the team to write out their focuses in a Slack message so that
    > priorities could be adjusted if necessary
    > ([[01:11:04]{.underline}](#section-43)).

-   **Exploratory Data Analysis Scope**: Pratyaksh Singh recommended
    > that the team include open source data in the Exploratory Data
    > Analysis (EDA) process, a suggestion which Hemanth Sarabu
    > approved. Hemanth Sarabu confirmed that the Exploratory Data
    > Analysis will cover old BRX data, new BRX data, and open source
    > data, with an expected completion time of under one week
    > ([[01:12:39]{.underline}](#section-44)).

-   **Exploratory Data Analysis Process Refinement**: Following the main
    > discussion, Pratyaksh Singh and Sachin Pandey reviewed the details
    > for the Exploratory Data Analysis process for the XT project
    > ([[01:14:28]{.underline}](#section-45)). They outlined the
    > pipeline for quality control and confirmed the inclusion of open
    > source data. The discussion also addressed using COCO data for
    > quality control regarding foreground and background artifacts, as
    > well as the need to compile final results
    > ([[01:16:06]{.underline}](#section-46)).

-   **Task Timelines and Data Labeling**: Pratyaksh Singh and Sachin
    > Pandey discussed specific durations for upcoming tasks, including
    > data labeling and synthetic data generation. They estimated a
    > four-day timeframe for synthetic data generation and planned for
    > approximately half a day for other specific tasks to ensure the
    > baseline model is established efficiently
    > ([[01:22:34]{.underline}](#section-47)).

*You should review Gemini\'s notes to make sure they\'re accurate. [[Get
tips and learn how Gemini takes
notes]{.underline}](https://support.google.com/meet/answer/14754931)*

*How is the quality of **these specific notes?** [[Take a short
survey]{.underline}](https://google.qualtrics.com/jfe/form/SV_9vK3UZEaIQKKE7A?confid=1kEFVzEClsRREitR5yunDxIUOAIIigIgABgECA&detailid=standard&screenshot=false)
to let us know your feedback, including how helpful the notes were for
your needs.*

📖 Transcript

Jun 15, 2026

## Iris Sync - Transcript

### 00:07:01

**Pratyaksh Singh:** Hello.

**Sachin Pandey:** Did you complicate the demo board?

**Pratyaksh Singh:** Uh, demo work.

**Sachin Pandey:** Like we we wanted something for demo.

**Pratyaksh Singh:** Hey,

**Sachin Pandey:** Hello.

**Pratyaksh Singh:** hello S. I think we only had to add the uh add
those files. You already added them in the example, right? Hello Can you
just move

**Sachin Pandey:** Yeah, I haven\'t

**Pratyaksh Singh:** those TIFF files to the example files if possible
and I think everything will be set after that once you just move it.

**Sachin Pandey:** the files which I shared you like the names I

**Pratyaksh Singh:** Yeah, whichever files Yeah,

**Sachin Pandey:** shared.

**Pratyaksh Singh:** whichever files which is where the model is
performing good just add it to example files.

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** Did you get a chance to run on uh class two and
four too?

**Sachin Pandey:** examples are from

**Pratyaksh Singh:** These examples are from cluster. Great.

**Sachin Pandey:** I will try

**Geoff Horowitz:** Hey guys. Um, hey, really quickly. Um, so I I told
you we got some clarity on bedrock. Uh, we\'ll talk about that in this
meeting.

### 00:09:07

**Geoff Horowitz:** Um, as much as in a discussion as as anything else.
Um, but I\'m I basically I think Sid is going to need to focus on
Boommy. And so I\'m going to bring Ratul in to help you guys in whatever
you need in whatever capacity you need so that as a group we can free up
some time for Bedrock. Um, and we can discuss that more. I\'m going to
invite Rul to this call now just so that he can start getting exposure
to all the things we\'re working on. Is there anything that we want to
discuss before I bring him on? Questions, comments, concerns.

**Pratyaksh Singh:** So ratul primary working on beds.

**Geoff Horowitz:** Say say that once more. I couldn\'t hear.

**Pratyaksh Singh:** Raton will be primary working on bed. Right? Is
that correct?

**Geoff Horowitz:** I\'m I\'m gonna say that he\'ll he\'ll be working on
whatever you guys need him to work on. And if if this makes the most
sense for him to,

**Pratyaksh Singh:** Okay.

**Geoff Horowitz:** you know, primarily work on bedrock, which I I think
it does, I assume it does, then that\'s going to be the case.

### 00:10:28

**Geoff Horowitz:** But I I don\'t want to. Basically, what I\'m going
to say is that, you know, you guys you guys know you guys know what\'s
going on. You guys know what\'s going to be the most helpful. You have a
flow and so whatever is going to work best for you. He\'s just more
hands.

**Pratyaksh Singh:** important. Okay.

**Geoff Horowitz:** Okay.

**Pratyaksh Singh:** And also one more thing I wanted to ask was uh
feedback from Ben regarding block one and

**Geoff Horowitz:** I\'m going to call him today. I haven\'t gotten any
yet. Um I wanted to wait to send him block three,

**Pratyaksh Singh:** two.

**Geoff Horowitz:** but um I guess we\'ll discuss that today. But but
I\'m going to call him and I\'ll share it with you if I get some
immediate feedback. I\'d like to also get on a call with him together um
and go over it in more detail, but I think we need to wait until he\'s
done with

**Pratyaksh Singh:** Makes sense.

**Geoff Horowitz:** locker.

**Pratyaksh Singh:** That\'s it.

**Geoff Horowitz:** Um,

### 00:11:37

**Hemanth Sarabu:** Hey, you guys hear me?

**Geoff Horowitz:** yes.

**Hemanth Sarabu:** Okay. Did I miss

**Geoff Horowitz:** So, no, no, no, no. Um,

**Hemanth Sarabu:** one?

**Geoff Horowitz:** where are we on block three?

**Sachin Pandey:** There are few files remaining which I am doing a
final give all portry the count is 134 files. The lablers have already
done the cleaning but they left the part where they are confused or what
to fix. You just need to go through those areas and it will be done to
send.

**Geoff Horowitz:** such can couldn\'t really hear you. Could you say
that once

**Sachin Pandey:** Yeah. Uh I was saying like there are 13 to 14 files
remaining uh which I have to uh go through in

**Geoff Horowitz:** more?

**Sachin Pandey:** QA. They labor has already fixed the obvious mistakes
and they leave the part where it is confusing or hard to fix. So just
need to look through those and then it will be ready to

**Geoff Horowitz:** Okay. Okay.

**Sachin Pandey:** send.

**Geoff Horowitz:** Do you have a an estimated

### 00:13:19

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** ETA?

**Sachin Pandey:** uh like in I\'m trying to finish it in few hours like
as soon as possible so we can start working other

**Geoff Horowitz:** Okay. All

**Sachin Pandey:** things.

**Geoff Horowitz:** right. Okay. Great. Do you need anything else? Um,
do you need a a second review or anything like

**Sachin Pandey:** Yeah, there are few files which looks very bad and we
can\'t even fix it.

**Geoff Horowitz:** that?

**Sachin Pandey:** So for those I need like some thoughts like what we
can do about it.

**Geoff Horowitz:** Can you share one or two examples now?

**Sachin Pandey:** Oh, yeah.

**Hemanth Sarabu:** Jeff, do you have a When are you talking to Ben?

**Geoff Horowitz:** I just set a reminder to give him a call today. Why?
What\'s up?

**Hemanth Sarabu:** Just checking.

**Geoff Horowitz:** Yeah. Um hopefully I\'ll have some time later this

**Sachin Pandey:** profile like this.

**Geoff Horowitz:** afternoon what what are we looking

**Sachin Pandey:** So

**Geoff Horowitz:** at?

**Sachin Pandey:** okay may not be on.

**Geoff Horowitz:** Did you say give me a second?

### 00:14:57

**Sachin Pandey:** Yes.

**Geoff Horowitz:** Okay.

**Sachin Pandey:** These are the final images and like the surface is
like very weird because uh Like there are many the yellow annotations
you are seeing. We are this is pulling we are pulling surface from water
surface. So it will like pop out more and introduce a little bit of
noise. These are clean in the latest iteration. This is the max image
max and

**Geoff Horowitz:** Wait. So what what are each of the three panels?

**Sachin Pandey:** Uh this is before and this is after cleaning.

**Geoff Horowitz:** Reference classification

**Sachin Pandey:** This is after max and this is min.

**Geoff Horowitz:** men.

**Sachin Pandey:** This is before any cleaning.

**Geoff Horowitz:** Okay.

**Sachin Pandey:** We filled these areas but it doesn\'t look like good
like this is the best we can do. So we we leave it as it is.

**Geoff Horowitz:** Is this is this also a case of um like if you spot
checked one of the pow trees, right?

**Sachin Pandey:** small.

**Geoff Horowitz:** Does it look like this is the the reasonable is what
I\'m asking.

### 00:16:37

**Sachin Pandey:** Yeah, we can look like

**Geoff Horowitz:** Like does it look like this is the right
classification?

**Sachin Pandey:** this. uh like surface switch will be happening there.
We can\'t like get rid of it completely. But like maybe we can fix
little bit this area like this area was looking weird. So I applied the
minmax cleaning on it. So it get rid of a lot of noise points. So it is
uh it is showing some gap.

**Geoff Horowitz:** Hey, can\'t you just draw a cross-section using your

**Sachin Pandey:** I\'m drawing a procession. Yeah, it\'s

**Geoff Horowitz:** Yeah. Okay.

**Sachin Pandey:** loading.

**Hemanth Sarabu:** Is it running on Wall-E? Okay.

**Geoff Horowitz:** While this is loading, Son um never mind. I don\'t
want to get distracted.

**Sachin Pandey:** Do you want the cross-section?

**Geoff Horowitz:** Yeah, just for one of those areas. So, so in block
two session, we looked at this, right? You and Pra looked at this and
the outcome was there there\'s really no better surface, right? And
that\'s what I\'m trying to figure out.

### 00:18:18

**Geoff Horowitz:** Is that the case here,

**Sachin Pandey:** Yes.

**Geoff Horowitz:** too? Is it also the case where there\'s really no
better solution? um where it\'s also not obvious that we shouldn\'t have
a surface there.

**Sachin Pandey:** Generally in these areas there isn\'t any uh seaweed
below like even if you see the examples the other iterations like all
all of them are failing. This is with water where we are pulling the
most of the surface from. But like it is introducing the moving. This is
how the data look very like few down points. These are

**Geoff Horowitz:** Honestly, he this is just where we need sigh.

**Sachin Pandey:** the

**Hemanth Sarabu:** Um, but this is not this is not the cross-section
view,

**Geoff Horowitz:** Oh,

**Hemanth Sarabu:** right?

**Sachin Pandey:** We are looking at this.

**Hemanth Sarabu:** Yeah. We is there a way we can

**Geoff Horowitz:** heat.

**Sachin Pandey:** Select the upper

**Hemanth Sarabu:** um we almost

**Sachin Pandey:** surface.

**Hemanth Sarabu:** want it the way portry does it, right?

**Sachin Pandey:** So we we can fix this area by choosing the upper
surface like removing these isolated noise and pulling the water.

### 00:21:25

**Sachin Pandey:** But like I I mainly talking about these surface
switches. We got here another look.

**Hemanth Sarabu:** What are you What are you showing us?

**Sachin Pandey:** These are like two files which looks bad to me. I
like needed some right whether it\'s

**Geoff Horowitz:** I I mean, look, I I agree with you. It\'s not
amazing. Um, this looks similar to what we did on block two, right?

**Sachin Pandey:** Yes.

**Geoff Horowitz:** And so my recollection of the outcome from block two
was that we couldn\'t do any better and that we thought having the
surface was better than not having the surface. Are we all agreed there?

**Sachin Pandey:** Yes.

**Geoff Horowitz:** So at the very least I think it\'s better to be
consistent, right? If we if we can\'t do better, then I think it\'s
better to be consistent than

**Sachin Pandey:** So there is like no surface below it. That\'s why it
was empty.

**Geoff Horowitz:** inconsistent.

**Sachin Pandey:** And we are switching once we find the surface. So
this whole area doesn\'t have any surface below.

### 00:23:22

**Geoff Horowitz:** Ultimately, the question is, does it make more sense
to have a surface there or not have a surface there? We\'ve decided it
makes more sense to have a surface that\'s consistent with the training
data that they gave us. Is that right?

**Sachin Pandey:** like they wanted the surface. Uh I\'m not sure
whether it was in the training data.

**Geoff Horowitz:** They wanted a surface. You\'re not sure if it was in
the training data. Were there big gaps in the bathy surface and the
training

**Pratyaksh Singh:** No,

**Sachin Pandey:** So like this artifact we can remove it completely.

**Geoff Horowitz:** data?

**Pratyaksh Singh:** there

**Sachin Pandey:** It will look better if we remove this. There isn\'t
any

**Pratyaksh Singh:** there weren\'t any gaps in the in the BI surface
that they gave us. Sashin, can you color the uh ground white? Maybe is
not visible in the street.

**Geoff Horowitz:** Yeah, I agree. That does not look like ground,

**Sachin Pandey:** Thank you.

**Geoff Horowitz:** but I mean in that specific instance, we can see a
few points underneath.

### 00:25:07

**Geoff Horowitz:** Yeah. So that\'s that\'s why it seems so clear.

**Sachin Pandey:** adding it will look like spikes instead

**Geoff Horowitz:** Yeah, that\'s why it seems so clear to

**Sachin Pandey:** of even if you

**Geoff Horowitz:** me.

**Sachin Pandey:** turn all the points there is mix but then like we
will like continue with uh what we did with the block two. I will remove
the like these areas where it is not looking good and try to smooth out
these corners.

**Geoff Horowitz:** Okay, fine. How did we smooth out the corners?

**Sachin Pandey:** Uh just taking a cross-section and like removing
points and

**Geoff Horowitz:** Oh, we did it manually.

**Sachin Pandey:** drawing. Yeah. like also I can so generally like the
points we remove would be of like uh will be unclassified so I like
sometimes select those but in this one there isn\'t any like most of the
points we removed are below the surface yeah for this one we have to
pull some points from noise manually like mainly for these colets
Otherwise, it\'s looking

**Geoff Horowitz:** Okay. How much time do you think that\'s going to
add?

### 00:26:36

**Sachin Pandey:** uh 10 to 15 minutes. It didn\'t take much

**Geoff Horowitz:** Oh,

**Sachin Pandey:** time.

**Geoff Horowitz:** okay. Fine. Per tile. 10 to 15 minutes per tile.

**Sachin Pandey:** There\'s only like two tiles like this.

**Geoff Horowitz:** Fine.

**Sachin Pandey:** So, it won\'t take

**Geoff Horowitz:** Okay. Okay. Great. Yeah. And you\'re saying that\'s
what we did with block two also? Yeah. Okay.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** I do think I do think when in doubt we go with
consistency. So, unless there\'s an obvious reason not to um production
month, you guys agree?

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** Yeah. Okay. Sin, anything else you need guidance on
or feedback?

**Sachin Pandey:** No, no,

**Geoff Horowitz:** Okay.

**Sachin Pandey:** that\'s it.

**Geoff Horowitz:** Okay. Um, okay, great. Ratioak, I I do want to spend
some time on bedrock, but do you want to do you want to go over the uh I
think you were you were going to give us a like a a plan of action for
the automated QA stuff.

### 00:27:59

**Pratyaksh Singh:** I think we discussed it right that uh we we have
what we needed for a demo and then we are going to do it after the
synthetic data validation. This is what we discussed in the previous.

**Geoff Horowitz:** I I didn\'t mean automated QA. I meant synthetic
data generation. Sorry for the confusion.

**Pratyaksh Singh:** Okay. Yeah. Uh do you want to do it

**Geoff Horowitz:** Oh, but actually remind

**Pratyaksh Singh:** after bedrock because I think it will take some

**Geoff Horowitz:** him. Um,

**Pratyaksh Singh:** time.

**Geoff Horowitz:** so it all kind of goes together, but one second for
the automated QA. Uh, so for the demo, we\'re just going to show based
on the synthetic data.

**Pratyaksh Singh:** Uh no I will add uh I think Sachin has add some
tiles where the model performs better. We\'ll we\'ll add those tiles.

**Geoff Horowitz:** as as some of the default tiles or the Yeah.

**Pratyaksh Singh:** Yeah. Yeah.

**Geoff Horowitz:** Okay, good.

**Pratyaksh Singh:** Some of the options that you will have available
there on

**Geoff Horowitz:** Okay, great.

### 00:29:05

**Geoff Horowitz:** Um, can you guys can you guys add can you guys add
those?

**Pratyaksh Singh:** that

**Geoff Horowitz:** f\*\*\*. Son, do you already have those tiles?

**Sachin Pandey:** Uh, I haven\'t added it right now. I\'m doing it
right now.

**Geoff Horowitz:** Okay,

**Sachin Pandey:** I have the file name but I

**Geoff Horowitz:** thank you.

**Sachin Pandey:** haven\'t

**Pratyaksh Singh:** Where is the

**Geoff Horowitz:** You haven\'t actually just I don\'t know,

**Pratyaksh Singh:** demo?

**Geoff Horowitz:** but we\'re going tomorrow. We just want it to be
ready for for us to show people if they ask.

**Pratyaksh Singh:** Understood.

**Geoff Horowitz:** I think I think we\'ll we\'ll have 24 hours at least
if we need

**Pratyaksh Singh:** Okay.

**Geoff Horowitz:** it.

**Pratyaksh Singh:** All right.

**Geoff Horowitz:** Okay.

**Pratyaksh Singh:** All right.

**Geoff Horowitz:** Okay. Um, so where is that? Okay, let me share this.
Um, let me share this deck. Uh, how do I hire R tool?

**Ratul Shashank:** Hello everyone and thank you Jeff for having me on
board.

**Geoff Horowitz:** Welcome.

**Ratul Shashank:** Glad to be start working with you guys.

### 00:30:25

**Hemanth Sarabu:** Hey, welcome.

**Pratyaksh Singh:** Yeah. Welcome, Richard.

**Ratul Shashank:** Thank you.

**Geoff Horowitz:** Okay. So, I\'ll share my screen, too, but I just
sent the uh the deck that I\'m looking at. So, Ratul, um, just to get
you up to speed,

**Hemanth Sarabu:** Come

**Geoff Horowitz:** uh,

**Hemanth Sarabu:** on.

**Geoff Horowitz:** I had mentioned to you a side scan sonar project
that we\'re working on um, that we\'ll probably have you help out on.
Uh, also what we were talking about at the beginning is one of our core
products in the point cloud space. Um, and so it\'s it I I don\'t know.
But, you know, it\'s it\'s possible that at some point you could have
your hands there, too. So, I just wanted you to join this meeting so
that you could um you know, you could start seeing what we\'re doing,
how we\'re working. Um yeah, but there\'s no no specific action for you
right at this

**Ratul Shashank:** Yes,

**Geoff Horowitz:** moment.

**Ratul Shashank:** it\'s definitely I will understand and get myself up
to speed as soon as possible.

### 00:31:37

**Geoff Horowitz:** Great. Thanks. Okay. So guys, uh I\'d shared this
this deck with you in the past which is just um just a you know a
centering a centering document. Obviously you guys know much of this
already. Um talks a little bit about what we did and then what the plan
is for this current um statement of work. Uh so it goes over that a
little bit. Um it also goes through the milestones uh which are a little
bit out of date but not entirely. Um so I\'m happy to go through those
if if you guys want a refresher, but what I actually want to talk about
is some of the internal milestones. So the latest the latest um I don\'t
know what the word is latest uh you know progress I guess. Um we were
initially planning on starting this project at the beginning of May.
Bedrock asked us to hold off on it for a little while. So we did. We
just talked with Bedrock last week and they gave us the go-ahad to to
start on the project.

### 00:33:00

**Geoff Horowitz:** um initially uh and project I I\'d shared this I I
had shared the initial statement of work with you I think right um or
that was teladine maybe that I\'d shared whatever anyway uh so initially
we thought we thought of breaking this work up into what I\'ll call two
two different substantial phases. One was to get an MVP up and running
and then the second phase of that would be to iterate on it, improve it
um over a longer time period. that was that was set up to align with
Bedrock\'s um presentation schedule. They wanted to present middle of
July to their customer. We still need to connect with Bedrock to
understand what their timeline is, but in the meantime, we still want to
get something akin to an MVP up in call it six weeks, four to six weeks,
five to six weeks. I think I put here that would put us somewhere around
August 1st. um questions up to this point.

**Hemanth Sarabu:** So,

**Geoff Horowitz:** Okay.

**Hemanth Sarabu:** um, project and such, did you guys have a chance to
review these slides like the original version that Jeff shared a while
ago?

### 00:35:08

**Hemanth Sarabu:** Oh,

**Sachin Pandey:** No.

**Pratyaksh Singh:** Oh, I forgot.

**Hemanth Sarabu:** you\'re mute.

**Pratyaksh Singh:** Can you can you share the slide?

**Hemanth Sarabu:** Okay. So, it\'s fine. That\'s That\'s all right. So,
let\'s catch you up first. Um the first in the first project with
Bedrock we developed this pipeline to detect targets. Right. Okay. So in
the second project there will be a couple of uh a couple of additional
things we will be doing. There\'s a there\'s more than a couple but
these are the highle themes. Number one, they have examples of um
explosives, actual explosives on the ocean surface, on the seabedit
surface. Okay. And there not that many I think in the I think under 100.
I can\'t remember the exact number. I think definitely under 100
examples of this.

**Geoff Horowitz:** far under 100. I think they said like 10 or
something.

**Hemanth Sarabu:** Okay,

**Geoff Horowitz:** 15.

**Hemanth Sarabu:** amazing. We have a rich data set of size 15 um to
train a an updated model.

### 00:36:41

**Hemanth Sarabu:** Now, so that is number one. There\'s a couple of
other things um I won\'t get into that right now, but there\'s a couple
of other things. And we have been talking to bedrock about synthetic
data. So they said, \"Oh, why don\'t why don\'t we develop a synthetic
data generation system to help here.\" So that is a second thing we will
be developing. Okay. So I\'ll summarize what what I have so far. Uh
Jeff, I I would say maybe maybe don\'t switch the slides. We can go
through them again. One, we retrain on this new class or new set of
data. two, how do we get more out of that data using synthetic methods?
Okay. And there\'s a couple of other things, but before we we move on to
that, I ask Pratak Sachin, is it clear so far what we\'ll be doing?

**Pratyaksh Singh:** Yeah, it makes sense. So to summarize, it\'s one
more class of mine which is heavily under represented

**Hemanth Sarabu:** Correct.

**Pratyaksh Singh:** and the one parallel thing to do is synthetic data
generation for it.

### 00:38:00

**Hemanth Sarabu:** Correct. Now I\'ll add a couple of things. So the
the background might be different too, you know, like it\'s not just the
actual positive examples, not just the targets, but the backgrounds will
be different too. And uh they said that they had a lot of uh this their
vehicle was rolling meaning it was it was moving side to side rolling
side to side um the way you know like a a boat would rock right side to
side. So because of that the images captured had um had a bunch of
artifacts. So we\'ll have to deal with that as well. Okay. Now that\'s I
think that this primarily captures milestone 2. There are future
milestones that involve using the mag data. We think it\'s possible that
we may need mag data sooner to detect these um these explosives. because
they\'re obviously they\'re, you know, they will show up. They\'ll
they\'ll be a signature in the mag, right? They\'re they\'re heavy uh
metallic objects. Um but right now that\'s not what we are that\'s not
that\'s not really the goal.

### 00:39:26

**Hemanth Sarabu:** Okay. and Bedrock has agreed to teach us how to
interpret the mag data, the raw mag data, the labeled MAG data and also
with some like ways to simulate the outputs of the mag system. Now that
is not part of milestone 2, but if we decide we need mag data, it will
help a lot with uh detections, we will pull that forward. We\'ll pull
that into this milestone.

**Pratyaksh Singh:** Got it. And why is that not part of milestone too?

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** It will be easier with

**Hemanth Sarabu:** It It\'s a bit arbitrary.

**Pratyaksh Singh:** that.

**Hemanth Sarabu:** It\'s a bit arbitrary. Um we No. So, this is like um
if this was an internal project, we probably wouldn\'t set it up this
way. The reason it\'s set up this way is so that uh the milestones
roughly, you know, they\'re distributing the efforts a little, right?
And so only for contract purposes. It was it was set up this

**Geoff Horowitz:** project.

**Hemanth Sarabu:** way.

**Geoff Horowitz:** It also had a little bit to do with what their
client wanted.

### 00:40:45

**Geoff Horowitz:** Their client didn\'t their client didn\'t necess
their their client wanted results. Their client didn\'t necessarily care
about incorporating MAC data. Um, and so that this this milestone two
that you can see, that\'s what they really wanted to show their client
and everything else was uh uh you know, icing on the cake, if you will.
It was it was an added benefit. So, as Hammon said, kind of arbitrary.
Um, but you know, we were we were trying to say, okay, this is what we
absolutely want, and we\'re going to try to get this done as fast as
possible. Everything else we can take more time with if we need to.

**Pratyaksh Singh:** Roger.

**Hemanth Sarabu:** Okay. So, you know, Jeff and I actually um want to
try this out a little differently. Um since you guys have been working
on these projects for a while, you know, very similar projects, right?
There\'s an R&D component. There\'s a model evaluations, data labeling
piece, reviewing data sets piece. We wanted to have this conversation
with you where you decide how to plan execution instead of us doing it.

### 00:42:11

**Hemanth Sarabu:** So, I don\'t know if Jeff you have the deliverables
for milestone to written out. Okay.

**Geoff Horowitz:** I I do I broke these up roughly into synthetic data
and you know regular model training um ra so just to

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** add one more thing you know the reason that I said
that this kind of goes handinhand with the synthetic data that we\'re
doing for for Iris is that you know I think we can all project you would
agree with this too we can all agree that there\'s some there\'s some
cost to context switching right picking picking up picking up one
project, putting it down, picking up another one. Um, and there are some
things that we\'ll need to do in parallel. Um, such in the S7K thing
comes to mind, right? I\'m not I hope that won\'t take extraordinarily
long, but it is something that we\'re going to need to do in parallel.
So the part of the basis of this discussion is um what\'s a reasonable
timeline? How do we if these are maybe some of the milestones that we
want to hit?

### 00:43:27

**Geoff Horowitz:** How do we coordinate this in a way that um that uh
sorry I lost my train of thought. How do we coordinate this in a way
that um still gives us some time to to to not fully drop these other
things or at least get to a stopping point with the other things?
That\'s that\'s reasonable that we can um pick up again later. Any
thoughts?

**Pratyaksh Singh:** I think I agree with the cost of context switching.

**Geoff Horowitz:** Yeah.

**Pratyaksh Singh:** I think uh documenting extensively helps with that.
Right. So for each of the project whatever the thought is if we can just
document it then it\'s it\'s easier to pick it up from there and uh if
you want to do it parallelly uh both of these things parallelly I think
uh I think we should like uh I think we should you know first focus on
just doing a EDA or bedrock first so that we are comfortable with the
data. And then once we are comfortable with the data and we move to
modeling where we are training the model I think we will get get some
time to work on other things parallelly during that time.

### 00:44:56

**Pratyaksh Singh:** I think EDA is the one where um if you want to
focus on if if you\'re prioritizing bedrock we should focus on it
extensively.

**Hemanth Sarabu:** So what happens is by the way if you need some time
you can take it uh to decide agree that we should start with EDA and we
should do that properly. How do you want to manage the context switching
piece?

**Pratyaksh Singh:** How do I as I said right we\'ll have to document
each of these projects uh either in the

**Hemanth Sarabu:** Okay. So,

**Pratyaksh Singh:** running mode

**Hemanth Sarabu:** you\'re Okay. So,

**Pratyaksh Singh:** or

**Hemanth Sarabu:** you\'re saying that um so what are you juggling
right now?

**Pratyaksh Singh:** so currently I think it will be synthetic data
generation And so that data generation for Iris and I think it will be
bedrock and along with that uh training the ground model and QA and QC
for it those

**Geoff Horowitz:** ground model.

**Pratyaksh Singh:** things the parent ground models because I think we
have data

**Geoff Horowitz:** You mean the the parent model? Yes.

**Pratyaksh Singh:** for it.

### 00:46:16

**Pratyaksh Singh:** We have enough data for it and we can data for

**Geoff Horowitz:** Who who who is actually spearheading that?

**Pratyaksh Singh:** it.

**Geoff Horowitz:** Is that you? Is it Sachin? Are you both doing it
together so that you know Sachin builds up that skill? What is Who\'s
How are you guys splitting that

**Pratyaksh Singh:** Uh I think for uh at least for iris I think I

**Geoff Horowitz:** up?

**Pratyaksh Singh:** am going to do it because since you know point
clouds are are little bit more complex than images and stuff. So I would
want such to start with images then to go directly on point

**Geoff Horowitz:** Cut

**Pratyaksh Singh:** cloud but still for QC and Q and

**Geoff Horowitz:** it.

**Pratyaksh Singh:** data collection I think I\'m going to

**Geoff Horowitz:** Cut

**Pratyaksh Singh:** need

**Geoff Horowitz:** it.

**Hemanth Sarabu:** So

**Geoff Horowitz:** Data collection is done, isn\'t it? We already have
the data sets.

**Hemanth Sarabu:** s\*\*\*.

**Geoff Horowitz:** The labelers were working on that for a long time.

**Pratyaksh Singh:** Data collection is done for ground. I think we have
a lot of data for ground.

### 00:47:31

**Pratyaksh Singh:** I think we have a lot of data. We need to get it QC
by the labelers. Uh you know a final a final 10 QC before we feed it to
the model. And for more data collection, it\'s basically like you know
on open too. I think we have enough data to at least get the first run
on and then if needed we will get more we\'ll get more data but we need
a final round of QC where we confirm that you know that the dems are as
expected.

**Geoff Horowitz:** got it. Is that QC done by Satchin or is that QC
done by the labelers? And then a final message.

**Pratyaksh Singh:** labelers. Mostly mostly

**Geoff Horowitz:** Okay.

**Pratyaksh Singh:** labelers

**Hemanth Sarabu:** Um such an brother tell me um who would have to do
the EDA for bedrock brother politics. Do you have to be um heavily
involved, lightly involved, not involved?

**Pratyaksh Singh:** I think I\'ll have to be lightly involved because I
think Sachin knows a lot about EDA given the amount of data he has been
seeing.

### 00:49:01

**Pratyaksh Singh:** But uh I\'ll have to be lightly involved with EDA
for

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** better.

**Hemanth Sarabu:** Um, so okay, I\'ll I\'ll throw this idea there.
These are the milestones. Let\'s let\'s go through them. You guys ask us
questions. Um you know we have some dates assigned to them but uh you
know it doesn\'t matter um you know like what what is most important is
that we are ready with a you know we\'re ready with the milestone
deliverables by the end of say week six. Um let\'s go through these and
then we\'ll decide how to split up the how to split up work at the
project level and also at within a intra project level. Um does that
sound good?

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** Okay. So, sounds like Jeff split this up into
synthetic data related and not synthetic data related. Uh,

**Pratyaksh Singh:** Heat.

**Hemanth Sarabu:** standardized data review

**Geoff Horowitz:** Yeah, one and two really go together,

**Hemanth Sarabu:** processes

**Geoff Horowitz:** right? Standardize the processes and do do the EDA.

### 00:50:39

**Geoff Horowitz:** Um, my concern here, maybe this is even for for
Sachin. My concern here, Sachin, I know you did a little bit of EDA. I
know Sid did a little bit of EDA. I don\'t even know if we\'ve
documented that or can kind of pick up where we left off. My instinct
says more or less we\'re going to need to restart.

**Hemanth Sarabu:** I\' I\'d say let\'s restart.

**Geoff Horowitz:** Yeah.

**Hemanth Sarabu:** Yeah,

**Geoff Horowitz:** Guess

**Hemanth Sarabu:** let\'s restart. And

**Geoff Horowitz:** I\'ll put these together

**Hemanth Sarabu:** um

**Geoff Horowitz:** then. Do you have any thoughts about how long the
EDA process will

**Hemanth Sarabu:** heat

**Geoff Horowitz:** take?

**Pratyaksh Singh:** Uh I would like to like do iteratively where where
we take one or two days to do EDA and then come back and see if we need
more.

**Geoff Horowitz:** Yeah.

**Pratyaksh Singh:** But I think yeah to initially should be done in
like 2 days one or two

**Geoff Horowitz:** Um, my my my instinct is actually saying that we
should probably try to do this sooner rather than later.

### 00:52:14

**Geoff Horowitz:** Maybe tomorrow and the next day because the data
labeling, getting the the labelers to work on this is probably going to
take some time. Um, is this clear what I mean by data relabeling? Yeah.
Okay. I mean,

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** you guys remember this from the first set and
obviously with all our other projects.

**Hemanth Sarabu:** Why would initial data review take two weeks, guys?

**Pratyaksh Singh:** Two days,

**Geoff Horowitz:** That was just me.

**Pratyaksh Singh:** right?

**Geoff Horowitz:** That was just me.

**Hemanth Sarabu:** H Yeah,

**Pratyaksh Singh:** Two days. One or two days.

**Hemanth Sarabu:** it\'ll be it should be a couple days max initial
data

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** review.

**Geoff Horowitz:** Yeah.

**Pratyaksh Singh:** There\'s two. I think previously we trained ResNet
50 and that was good with them, right?

**Hemanth Sarabu:** Um.

**Geoff Horowitz:** We trained three models for them. I can pull it up.

**Hemanth Sarabu:** Mhm.

**Geoff Horowitz:** Uh, we trained three

**Hemanth Sarabu:** Yeah. All

**Geoff Horowitz:** models.

**Hemanth Sarabu:** three.

**Geoff Horowitz:** Uh, I don\'t have it up.

### 00:53:27

**Geoff Horowitz:** I can find it if we want, but we want to retrain all

**Pratyaksh Singh:** Yeah, I think the largest was reset 50.

**Geoff Horowitz:** three.

**Pratyaksh Singh:** No, I just wanted to see if uh what was the size of
the model to see what options we have.

**Geoff Horowitz:** Oh, you can\'t see us.

**Hemanth Sarabu:** Oh, go up. Go down. 11. Slide 11. Slide 11.

**Geoff Horowitz:** Oh, yeah. Oh, we changed the names. I forgot we
changed the names. We We trained three models.

**Hemanth Sarabu:** Um,

**Geoff Horowitz:** Uh, I\'d have to look back to see exactly what they

**Hemanth Sarabu:** okay.

**Geoff Horowitz:** were.

**Hemanth Sarabu:** I don\'t remember what these guys were. I think
there were Is there a ResNet 10 or 12 guys? Yeah, I have no way. I have
no recollection. We\'ll have to ask actually. Protect, you you train
these, right?

**Pratyaksh Singh:** I reset 50 was the largest that we did.

**Hemanth Sarabu:** Okay. I have no idea where this came from. I have no
idea.

### 00:54:48

**Hemanth Sarabu:** Well, um Jeff, we probably Yeah,

**Geoff Horowitz:** I guess we did a good job off skating, huh?

**Hemanth Sarabu:** there was some logic to this. I can\'t remember what
the logic was.

**Geoff Horowitz:** I I thought it was I thought you just like it was
like reset

**Pratyaksh Singh:** Yeah. 18 34 and 50.

**Geoff Horowitz:** 25

**Pratyaksh Singh:** We 18 34 and 50.

**Hemanth Sarabu:** What\'s that?

**Pratyaksh Singh:** 18 34 and 50.

**Hemanth Sarabu:** 18 34 and 50.

**Geoff Horowitz:** 18 24 and 50. Okay.

**Hemanth Sarabu:** 34.

**Geoff Horowitz:** 34. Yeah.

**Hemanth Sarabu:** Okay. All right. Um, that\'s Why is it lumen 25?

**Geoff Horowitz:** I think we just thought like I think we thought like
putting lumen 34 was gonna be

**Hemanth Sarabu:** Yeah,

**Geoff Horowitz:** weird.

**Hemanth Sarabu:** but at least the ratio you would have I don\'t know.
Okay, it\'s fine. Um, okay. Okay. Can we go back to the

**Geoff Horowitz:** Yeah.

**Hemanth Sarabu:** Okay. Uh, data re relabeling. I think we should that
should be I don\'t know about which weeks.

### 00:56:00

**Hemanth Sarabu:** Let\'s just let\'s for now let\'s maybe let\'s do
durations. But I think initial reabeling should take no longer than a
couple of days to given we don\'t have that much data.

**Geoff Horowitz:** I\'m not sure that that\'s true. Let me look this
up. I I made a uh a data sets folder.

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** Here you guys go. Let me just add the comment here.

**Pratyaksh Singh:** I think they can do in a couple of days. Check. The
reason previously took time was we asked them to re label it multiple
times.

**Geoff Horowitz:** We may also need to go through the first data set
again. Possible.

**Pratyaksh Singh:** I\'m also concerned about the artifacts that they
talked

**Geoff Horowitz:** Uh yeah, you\'re right.

**Pratyaksh Singh:** about.

**Geoff Horowitz:** There\'s like 200ish 200ish XTFS. Not a ton.

**Hemanth Sarabu:** That\'s not terrible.

**Geoff Horowitz:** Not a ton.

**Hemanth Sarabu:** Oh, yeah.

**Geoff Horowitz:** I I\'m that that that\'s for the new data that
excludes whatever we had for Vineyard Winds and the open source data

**Hemanth Sarabu:** Yeah,

### 00:57:10

**Geoff Horowitz:** um which s updated here if you guys

**Hemanth Sarabu:** we need to add in the open source data. That\'s
true.

**Geoff Horowitz:** look. Well,

**Hemanth Sarabu:** Hey, we don\'t we only see your

**Geoff Horowitz:** whatever. Yeah.

**Hemanth Sarabu:** slides.

**Geoff Horowitz:** This is what I was looking at. I made this. I think
you guys have seen this.

**Hemanth Sarabu:** Nice.

**Geoff Horowitz:** I posted this on the Slack channel, too. But I have
like descriptions for each of these new data sets that they gave us. Uh,

**Pratyaksh Singh:** Mhm.

**Geoff Horowitz:** you know, that goes through a little bit. It goes
through the folder structures. That\'s pretty much it. By all means, add
more if you guys want to. Um, but I did not do that for Vineyard Winds
or the open source data. I don\'t even know what open source data there
is. We we\'ll need to rope sit in to update

**Pratyaksh Singh:** Sure.

**Geoff Horowitz:** this anyway. What were you saying? You said this was
only a couple of

### 00:58:06

**Pratyaksh Singh:** Yeah. Like if it\'s 200 files,

**Geoff Horowitz:** days.

**Pratyaksh Singh:** it should be at the end.

**Geoff Horowitz:** Would you say how much you wanted a few? You want a

**Hemanth Sarabu:** I think durations.

**Geoff Horowitz:** duration?

**Hemanth Sarabu:** Let\'s do durations. We\'ll figure out which week
later on.

**Geoff Horowitz:** You guys think? Okay. Um, we can we can take all
four labelers if we need it. Um, my only recommendation is that if we do
that, we we probably Santo, right? we\'d put somebody in charge. Um, I
mean unless projects you you want to split it up so that you know some
people are still working on the ground data.

**Hemanth Sarabu:** Let\'s do this.

**Pratyaksh Singh:** I I think I would rather get it done first.

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** Get this one done first if it takes just a couple
of days.

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** Amen. What were you proposing?

**Hemanth Sarabu:** I I was proposing you and such and decide make like
a what\'s it called a game time decision about how you want to allocate
the labelers.

### 00:59:43

**Hemanth Sarabu:** We don\'t have to decide that now.

**Pratyaksh Singh:** Got

**Hemanth Sarabu:** So feel free to pull those guys uh into whatever you
need.

**Pratyaksh Singh:** it. Got it.

**Hemanth Sarabu:** And if you want then you

**Pratyaksh Singh:** And the other two labers are right

**Hemanth Sarabu:** know

**Pratyaksh Singh:** now working on uh boom, right?

**Hemanth Sarabu:** yeah I believe so. Um so establish baseline model
retraining workflows

**Geoff Horowitz:** Yeah, they\'re working on Boommy, but uh you know,
Hammond, when we talk to Sid, like he doesn\'t seem to be blocked by
that. So, if it\'s delayed a week or two, I I don\'t think it\'s going
to harm him too much.

**Hemanth Sarabu:** Yeah. Yeah. So I guess project we can pull them. Sid
is using IC for all the blocking blocking data labeling

**Geoff Horowitz:** Ready?

**Hemanth Sarabu:** work. Okay. So I guess Pratak I want to understand
do you want to pause parent model training and point cloud synthetic
data efforts finish this and pick those back up? Do you want to do two
things in parallel?

### 01:01:34

**Hemanth Sarabu:** three things in parallel. What? How do you want to
do it?

**Pratyaksh Singh:** Yeah,

**Hemanth Sarabu:** I guess it\'s

**Pratyaksh Singh:** let me try to do things in parallel if uh but you
know this will be like

**Hemanth Sarabu:** not

**Pratyaksh Singh:** the I just try to I I don\'t want to block

**Hemanth Sarabu:** makes sense.

**Pratyaksh Singh:** it.

**Hemanth Sarabu:** Okay. In that case, um I\'m going to throw I think I
would like you and Sachin to make this call, you know, like you make the
decision. But one idea is um things like number three what you can do is
project you could do primary like R&D IC work on synthetic data for
point clouds etc. Um and then you can if you feel comfortable uh with
the codebase and the data sets then Suchin can do number three. He can
do number three until you decide okay I need to like go and change the
change the training pipeline or I need to go and add synthetic.

**Pratyaksh Singh:** Got it.

**Hemanth Sarabu:** That\'s an idea. Now I don\'t know if that is what
you guys want to do, how you want to split up the

### 01:02:51

**Pratyaksh Singh:** No, I think I think it\'s a good idea.

**Hemanth Sarabu:** work.

**Pratyaksh Singh:** One of the reason is is I want to have like kind of
a standard thing at least for training your reset models uh sorry the
unit models right where you just change the data folder because I think
uh I think we are going to train them

**Hemanth Sarabu:** Right.

**Pratyaksh Singh:** a lot right so it will be easier to have control on
this where you know you

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** don\'t have to touch the code you just maybe change
one or two things in the config and just put the data and point to data
similar to what we have

**Hemanth Sarabu:** Yeah. I mean,

**Pratyaksh Singh:** for

**Hemanth Sarabu:** I don\'t um frankly I don\'t know if we\'re if
we\'re going to be able to get away with no code changes, at least
augmentations, at least synthetic data gener that stuff will change,

**Pratyaksh Singh:** yeah but I think you

**Hemanth Sarabu:** I believe.

**Geoff Horowitz:** Come on. Even even accounting for roll.

**Pratyaksh Singh:** know

**Geoff Horowitz:** I mean that\'s that\'s not accounted for in our
guys.

### 01:03:50

**Geoff Horowitz:** I\'m really sorry.

**Hemanth Sarabu:** Yeah,

**Geoff Horowitz:** I need to drop. Um, but uh,

**Hemanth Sarabu:** I\'ll catch you up.

**Geoff Horowitz:** thanks. Also, let\'s let\'s come up with a plan for
the next two days or 3 days he while we\'re out of town

**Hemanth Sarabu:** Um

**Geoff Horowitz:** or just make sure that we\'re not blocking our even
if that plan is working on the other stuff and pausing this whatever.
Okay, you guys will figure it out.

**Hemanth Sarabu:** yeah.

**Geoff Horowitz:** I gotta run.

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** Um, okay. Thanks, guys.

**Hemanth Sarabu:** Okay. Oh, I guess we needed that. Give me one sec.
Pull that up.

**Pratyaksh Singh:** It\'s in the chat.

**Hemanth Sarabu:** Okay, you guys able to see this? Okay. Okay. So, you
want to do that. You want to kind of like let Sachin own this stuff.

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** Such in. How does that sound to you?

**Sachin Pandey:** Uh yeah, I

**Hemanth Sarabu:** Okay. I mean, again,

**Sachin Pandey:** can

### 01:05:34

**Hemanth Sarabu:** just because we\'re deciding now doesn\'t mean
that\'s what you guys need to do. The most important thing is that we
hit this week six target. This is the most uh important thing. Oh,
there\'s all these new sounds. Google Meet is doing all these new
sounds. I have no idea what they mean. Um, okay. So um should we
allocate this a duration of one and a half weeks?

**Pratyaksh Singh:** uh baseline model retaining workflow searching to
execute. Yes, it\'s time. Yeah. Yeah. Let me let me finish setting this
up. Uh so anyone for synthetic data and all uh I wanted to share
something for what I did for bedrock maybe I\'ll sh it on slash I think
having

**Hemanth Sarabu:** Yeah, please please do for bedrock or

**Pratyaksh Singh:** a stand yeah huh what for

**Hemanth Sarabu:** pirus.

**Pratyaksh Singh:** Iris like you know the way that I trained the
synthetic uh so I for the auto

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** QC the way that I set up the training I want to I
want to share that other

### 01:07:10

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** thing I did something different and might help.

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** I will try to you know the I will try to modify
what I had for auto

**Hemanth Sarabu:** Right.

**Pratyaksh Singh:** QC training for Iris and have this uh training
pipeline set up. I will add some flexibility so that you can change one
of one or few things but I want to keep it standard so that like so that
you know uh I think I think you know we are going to train a lot of that
is

**Hemanth Sarabu:** Right.

**Pratyaksh Singh:** why

**Hemanth Sarabu:** But but that\'s not going to be useful for bedrock
command. Right.

**Pratyaksh Singh:** also we going to train unit

**Hemanth Sarabu:** So okay, I\'m talking about synthetic data stuff
that will be transferable between

**Pratyaksh Singh:** Mhm. So

**Hemanth Sarabu:** bedrock and uh

**Pratyaksh Singh:** the pipeline will be the pipeline can be
transferable, right?

**Hemanth Sarabu:** I I don\'t know.

**Pratyaksh Singh:** The process will be different.

**Hemanth Sarabu:** You tell me. Okay.

**Pratyaksh Singh:** Uh uh I will I I\'ll share that Let me share that
thing.

### 01:08:21

**Hemanth Sarabu:** Um Mhm.

**Pratyaksh Singh:** I had it written down. I just didn\'t know which
channel to share it in.

**Hemanth Sarabu:** Okay. I mean anywhere is okay.

**Pratyaksh Singh:** I\'ll share that.

**Hemanth Sarabu:** You can do it. Okay.

**Pratyaksh Singh:** Yeah,

**Hemanth Sarabu:** Good.

**Pratyaksh Singh:** I think I think it should be the the pipeline
should be

**Hemanth Sarabu:** Mhm. Go on. Come on. Okay.

**Pratyaksh Singh:** transferable.

**Hemanth Sarabu:** Okay. That\'ll be awesome. If it is, but I did not
expect it to be, but if it is, that\'ll be awesome. Um, so what is your
what is your saying you will think about this?

**Pratyaksh Singh:** Yeah, like you know at least set up the pipeline so
that we can run multiple experiment and then just compare the results
something like that. I\'ll create the pipeline such will basically
supervise change the iceberg parameters and everything.

**Hemanth Sarabu:** Okay. Okay. This is about synthetic data gen. Um I
also have to run.

**Pratyaksh Singh:** I will I will try to focus on this I think because
this will be

### 01:09:44

**Hemanth Sarabu:** Mhm.

**Pratyaksh Singh:** required at some some stage even in our previous
milestone.

**Hemanth Sarabu:** Yeah. Yes. So if you if you know like one structure
can be and this is obviously dependent on how things are going right.
One structure can be you do the synthetic data gen R&D primarily you
know um and then in the meantime you set set up initial stuff so that
the rest of the team can carry carry this forward right while you\'re
working on this guy.

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** And then you know uh when the time is right you add
that in add the data in and move

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** forward. Um can you do me one favor?

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** You guys review the these slides and add in
durations and add like you know make changes to this plan. If you think
anything doesn\'t make sense or we need to have something here that we
haven\'t documented, I would like you to add them.

**Pratyaksh Singh:** Okay.

**Hemanth Sarabu:** Can I request that you do that in the next hour
while everything is fresh in your heads in my head and

### 01:11:04

**Pratyaksh Singh:** All

**Hemanth Sarabu:** I can respond on Slack if needed. Yeah. Uh and look
um I don\'t I don\'t want you to take this exercise lightly.

**Pratyaksh Singh:** right.

**Hemanth Sarabu:** Um but you know if you need to change things that is
totally fine later on. Does that sound reasonable?

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** And do you guys have uh are you what is what are
your priorities for the next couple of days?

**Pratyaksh Singh:** I think for me it will be this and synthetic data.

**Hemanth Sarabu:** Sorry.

**Pratyaksh Singh:** It will bedrock and synthetic data.

**Hemanth Sarabu:** Okay. So, Bedrock, EDA, etc., etc. Okay. And that\'s

**Sachin Pandey:** Uh for me after tetra tech I have like S7K and then
better

**Pratyaksh Singh:** Yeah.

**Sachin Pandey:** both.

**Hemanth Sarabu:** for the next couple of days. Okay. All right.

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** Um just so just because uh I don\'t forget, do you
guys mind just typing out a Slack message about your focuses for the
next uh 2 to 3 days and then uh I will um yeah, if we need to change
priorities or something, I\'ll let you know, which is unlikely.

### 01:12:39

**Hemanth Sarabu:** Okay, maybe they might we might ask for support
while we\'re at the conference, but that\'s that\'s it. Okay. All right.
Anything else, guys? Anything else you want to bring up? No. Okay. All
right, let\'s speak to you

**Pratyaksh Singh:** Hey uh for EDA I think it will be good if we do for
open source

**Hemanth Sarabu:** guys.

**Pratyaksh Singh:** data too.

**Hemanth Sarabu:** Yes,

**Pratyaksh Singh:** Is that included in

**Hemanth Sarabu:** let\'s do it.

**Pratyaksh Singh:** there?

**Hemanth Sarabu:** Um, he uh Jeff added a link to the data sets folder,
but I will make I don\'t know if that contains it, but I will add that
right now. Standard data review process conduct. Uh, I\'m just going to
call this EDA. Yeah, which cover old BRX data, new BRX data and
opensource data. Okay. And of course, this might change the duration to
I still think under a week. Well, under a

**Pratyaksh Singh:** Yeah. Fold that.

**Hemanth Sarabu:** week.

**Pratyaksh Singh:** Okay. We\'ll we\'ll update it.

### 01:14:28

**Hemanth Sarabu:** Okay. Yeah. So, two requests. One is you guys
discuss and uh Okay. I have a request. Two requests. I\'m wondering if
this is just making these sounds based on something I\'m saying. Okay.
Um, so two requests. One is, you know, update this and let us know and
let us know about your priorities for the next couple days. Yeah. All
right.

**Sachin Pandey:** Okay.

**Hemanth Sarabu:** Thanks, guys. Okay. All right, guys. Bye-bye.

**Sachin Pandey:** Bye.

**Pratyaksh Singh:** uh do you want to discuss this machine?

**Sachin Pandey:** Yeah. Okay.

**Pratyaksh Singh:** Uh so data review process and conduct. Can you see
my screen?

**Sachin Pandey:** Yeah,

**Pratyaksh Singh:** Okay. Data review process and conduct TDA. This
will be I think so just

**Sachin Pandey:** this will be on both uh like mag data also,

**Pratyaksh Singh:** add no not mag data.

**Sachin Pandey:** right?

**Pratyaksh Singh:** Try also this element data. Let\'s write it for X2.

**Sachin Pandey:** Checking the pipeline for XTF to

### 01:16:06

**Pratyaksh Singh:** Yeah, wait. Uh only for XT add open source data and

**Sachin Pandey:** CNG.

**Pratyaksh Singh:** then open source data again. This will be there.
And then second thing will be let me just

**Sachin Pandey:** Now, RX data consider

**Pratyaksh Singh:** The data maybe for questionual

**Sachin Pandey:** What\'s up?

**Pratyaksh Singh:** Coco data for QC forground background or
foreground.

**Sachin Pandey:** Foreground main

**Pratyaksh Singh:** Huh?

**Sachin Pandey:** artifact. Okay.

**Pratyaksh Singh:** Changes in background between Open old or new
basically. Background

**Sachin Pandey:** screenshot this s.

**Pratyaksh Singh:** screen

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** final Result compilation. Finally compat.

**Sachin Pandey:** Oops.

**Pratyaksh Singh:** Open source data. So yeah, finally I Finally.

**Sachin Pandey:** last time. Same pipelines. We\'ll be taking

**Pratyaksh Singh:** Take

**Sachin Pandey:** over.

**Pratyaksh Singh:** confirm.

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** creative

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** Friday. Take

**Sachin Pandey:** Clean.

**Pratyaksh Singh:** a deadline.

**Sachin Pandey:** Hey

**Pratyaksh Singh:** Okay.

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** QC dat.

### 01:22:34

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** knowable

**Sachin Pandey:** continuation.

**Pratyaksh Singh:** sharable.

**Sachin Pandey:** Take

**Pratyaksh Singh:** fin

**Sachin Pandey:** During time may uh label

**Pratyaksh Singh:** I will

**Sachin Pandey:** Unless

**Pratyaksh Singh:** suggest Data.

**Sachin Pandey:** Okay. part.

**Pratyaksh Singh:** data QC.

**Sachin Pandey:** Yes.

**Pratyaksh Singh:** Go

**Sachin Pandey:** Min.

**Pratyaksh Singh:** minport

**Sachin Pandey:** So much stuff.

**Pratyaksh Singh:** Minry

**Sachin Pandey:** Okay, cool.

**Pratyaksh Singh:** fileand data

**Sachin Pandey:** I

**Pratyaksh Singh:** R9

**Sachin Pandey:** can\'t

**Pratyaksh Singh:** SSTP R9 R9 final data

**Sachin Pandey:** wait.

**Pratyaksh Singh:** Okay. Okay.

**Sachin Pandey:** Take

**Pratyaksh Singh:** Netherlands.

**Sachin Pandey:** okay groundwater

**Pratyaksh Singh:** Okay. Anyways, data relaying few

**Sachin Pandey:** Two question

**Pratyaksh Singh:** days.

**Sachin Pandey:** to Thank you.

**Pratyaksh Singh:** data labeling a few days. Yeah, I think I want to
get this started soon. Start establish baseline model. Baseline.
services.

**Sachin Pandey:** Take

**Pratyaksh Singh:** What is your approach for sensitive data?

**Sachin Pandey:** me.

**Pratyaksh Singh:** Gen 4 days. Smelling champions of location. Take

**Sachin Pandey:** Everything. Okay.

**Pratyaksh Singh:** Let\'s try to get this done in two days.

**Sachin Pandey:** Look.

**Pratyaksh Singh:** for maybe half a day. I think

**Sachin Pandey:** Awesome.

**Pratyaksh Singh:** Same thing for disparity and labeling.

**Sachin Pandey:** It

**Pratyaksh Singh:** Some say uh was

**Sachin Pandey:** display.

**Pratyaksh Singh:** a

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** QC.

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** Fin compare. Okay.

**Sachin Pandey:** AP

**Pratyaksh Singh:** There you go.

**Sachin Pandey:** Okay. Well, thanks

**Pratyaksh Singh:** Thank

**Sachin Pandey:** man.

**Pratyaksh Singh:** you. Find

**Sachin Pandey:** Okay. Yeah.

### Transcription ended after 01:33:00

*This editable transcript was computer generated and might contain
errors. People can also change the text after it was created.*
