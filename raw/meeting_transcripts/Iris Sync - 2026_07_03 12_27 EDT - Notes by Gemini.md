Jul 3, 2026

## Iris Sync

Invited [[Sachin Pandey]{.underline}](mailto:sachin@crescer.ai)
[[Pratyaksh Singh]{.underline}](mailto:pratyaksh@crescer.ai) [[Niveta
Iyer]{.underline}](mailto:niveta@crescer.ai) [[Hemanth
Sarabu]{.underline}](mailto:hemanth@crescer.ai) [[Geoff
Horowitz]{.underline}](mailto:geoff@crescer.ai) [[Siddharth
Soni]{.underline}](mailto:siddharth@crescer.ai) [[Ratul
Shashank]{.underline}](mailto:ratul@crescer.ai)

Attachments [[Iris
Sync]{.underline}](https://calendar.google.com/calendar/event?eid=NnNzMHVxNzk3MmJqZGVwNXFoN2J1Mjd1OTdfMjAyNjA3MDNUMTYzMDAwWiBnZW9mZkBjcmVzY2VyLmFp)

Meeting records
[[Transcript]{.underline}](https://docs.google.com/document/d/1GQUBZ_GNwJ7CvZQTg87iq0vmsOm9il7a-BHciDI00K0/edit?usp=drive_web&tab=t.58jlrfipuz8r)

### Summary

Technical teams reviewed data pipelines and model progress while
establishing infrastructure protocols and development strategies.\
\
**Data Pipeline and Strategy**\
The team reached consensus on using calibrated filtered data for
magnetic signal analysis with a 5 to 10 nanoTesla threshold. This
approach prioritizes reliability while establishing baselines for dipole
interference detection.\
\
**Model Development and Labeling**\
Exploratory data analysis is complete, establishing manual labeling as
the current bottleneck. Iteration 2 of the model will improve accuracy
by dropping non-essential classes.\
\
**Infrastructure and Workflow Design**\
Engineering workflows now emphasize intent-driven development via AI
agents to accelerate system design and UI testing. The team will adopt
Playwright to automate critical regression testing for stability.

### Decisions

Aligned

-   **Filtered magnetometer data prioritized** The team will utilize
    > filtered magnetometer data as the primary baseline for analysis,
    > reserving the investigation of raw data for future requirements.

-   **Agent-based experimentation pipeline strategy** The team will
    > adopt an agent-based approach for model experimentation, where
    > agents utilize seed papers to source, test, and integrate new
    > model improvements.

-   **Model training strategy refinement** The second iteration of the
    > model is set to drop non-essential classes during training to
    > improve overall accuracy.

-   **Team hackathon initiation** A team hackathon will be organized to
    > share knowledge on LLM usage and development workflows.

We\'ve **updated the Decisions section** using your feedback.

Let us know what you think:
[[Helpful]{.underline}](https://google.qualtrics.com/jfe/form/SV_5p6FWBVWvynleNU?isGoogler=no&isHelpful=yes)
or [[Not
Helpful]{.underline}](https://google.qualtrics.com/jfe/form/SV_5p6FWBVWvynleNU?isGoogler=no&isHelpful=no)

### Next steps

-   \[Ratul Shashank\] Analyze Filtered Data: Examine the filtered
    > magnetometer data provided in the OBF files to identify potential
    > signal patterns. Compare these results with the preliminary
    > findings on raw data to validate the effectiveness of the filtered
    > approach.

    > \[Ratul Shashank\] Review OBF Data: Review the OBF file format and
    > content to ensure correct interpretation of the filtered
    > magnetometer readings. Confirm if the current pipeline can utilize
    > this data for signal detection.

    > \[The group\] Finalize Data Labeling: Conduct a review of the
    > remaining 2 parts of the ENT data to fix classification mistakes.
    > Finalize the labeling process for the entire dataset.

    > \[The group\] Schedule Retreat: Schedule a follow up discussion to
    > determine the logistics and timing for the company retreat, taking
    > into account availability in October or November.

    > \[Sachin\] Generate Progress Report: Compile a summary of recent
    > accomplishments and future objectives. Focus on headlines and
    > results without excessive detail.

    > \[Ratul\] Schedule Workflow Meeting: Set a meeting for next
    > Wednesday or Friday to review the project workflow. Invite the
    > entire team and Sid.

    > \[Pratyaksh\] Update Diffusion Progress: Share findings regarding
    > the use of diffusion models for generating training data. Provide
    > these results on Monday.

    > \[Pratyaksh\] CC Hemanth: Copy Hemanth on the existing Slack
    > discussion regarding map data. Ensure he has context to assist
    > with inquiries.

    > \[Pratyaksh Singh\] Share Research: Share resources on RL and
    > post-training for LLMs in Slack for the team to review.

    > \[Sachin Pandey\] Investigate Playwright: Investigate Playwright
    > for website button click testing to improve automation speed and
    > reliability.

    > \[The group\] Organize Hackathon: Organize a hackathon for the
    > team to explore and learn how each person uses LLMs in their
    > workflow.

### Details

-   **Project Report and Status Check**: Ratul Shashank provided an
    > update to Geoff Horowitz regarding the RTL report, confirming that
    > the necessary data points were included alongside an overview of
    > current pipeline capabilities. Geoff stated they would review the
    > material later that day or over the weekend to provide feedback
    > ([[00:01:49]{.underline}](#section)).

-   **Pratyaksh's Health and Infrastructure**: Pratyaksh Singh discussed
    > their recent illness, attributing it to heat due to their air
    > conditioner breaking down seven or eight days prior. They
    > confirmed the unit had been sent to a service center for repairs
    > ([[00:02:58]{.underline}](#section-1)).

-   **Retreat and Office Location Planning**: Hemanth Sarabu, Geoff, and
    > Pratyaksh debated potential locations for a company retreat, with
    > Hemanth suggesting a \"slow\" part of South Goa to avoid the party
    > atmosphere of North Goa. The group discussed timing, noting that
    > September would be challenging due to holidays and weather,
    > leading them to consider October or November as better
    > alternatives ([[00:03:48]{.underline}](#section-2))
    > ([[00:06:07]{.underline}](#section-4)).

-   **Amritsar Discussion and AI Reliability**: The team engaged in a
    > tangent regarding Geoff\'s past visit to Amritsar, specifically
    > debating whether the city experienced snow. The discussion
    > concluded with a consensus regarding the unreliability of
    > AI-generated images and the impact of environmental factors like
    > pollution on perception ([[00:09:23]{.underline}](#section-7)).

-   **Magnetometer Data Pipeline Strategy**: Geoff, Ratul, and the team
    > discussed the ongoing work with Bedrock's magnetic (MAG) data.
    > They addressed whether they should use raw or filtered data, with
    > Ratul and Hemanth debating the effectiveness of filtering
    > techniques to remove vehicle noise and environmental interference
    > ([[00:12:06]{.underline}](#section-10))
    > ([[00:15:54]{.underline}](#section-13)).

-   **Definition of Despiking**: Hemanth, Ratul, and Geoff clarified the
    > \"despiking\" process, which they identified as the removal of
    > low-amplitude, high-frequency noise or vehicle-produced magnetic
    > effects from the signal to create a cleaner dataset
    > ([[00:14:46]{.underline}](#section-12)).

-   **Preliminary Analysis of Dipole Interference**: Ratul presented
    > preliminary findings from the DR dataset, showing blue markers
    > where amplitude spikes aligned with dipole interference. Hemanth
    > and Geoff advised caution, noting that while this serves as a
    > baseline, the group needs to confirm the reliability of this
    > method and understand why it might or might not work across
    > different regions ([[00:20:06]{.underline}](#section-16)).

-   **Threshold Consensus for Filtering**: The team discussed using a
    > threshold of 5 to 10 nanoTesla to identify potential targets.
    > Geoff instructed the team to start by working with the filtered
    > data provided by Bedrock---specifically the files Sachin Pandey
    > previously displayed---before considering raw data, as this
    > filtered information is already calibrated
    > ([[00:25:53]{.underline}](#section-20))
    > ([[00:35:54]{.underline}](#section-28)).

-   **Labeling and Training Progress**: Sachin provided an update on the
    > VW dataset labeling, noting they are finishing the labeling for
    > the first division while reviewing the other two. Sachin also
    > reported that the ML intern agent is running, and training models
    > have been logged for both raw and processed data
    > ([[00:40:20]{.underline}](#section-31)).

-   **LLM Architecture and Hosting**: Sachin and Hemanth discussed the
    > use of locally hosted LLMs like Quen and Gemma to optimize latency
    > and utilize larger context windows. They explored a strategy of
    > using paid models like Claude as orchestrators while utilizing
    > open-source models for lower-level tasks
    > ([[00:43:05]{.underline}](#section-33)).

-   **Experimental Model Pipeline**: Pratyaksh proposed a pipeline for
    > future experiments where an agent identifies seed papers,
    > retrieves code from GitHub, executes tests, and logs performance
    > on ClearML. The team agreed on the importance of implementing
    > clear evaluation metrics, such as boundary metrics for
    > segmentation, to track improvements
    > ([[00:49:30]{.underline}](#section-38)).

-   **Gamification of Labeling**: Hemanth shared an experience of using
    > Claude to build an app for travel planning and suggested
    > incorporating gamification---such as awarding gold stars or using
    > interactive interfaces---to increase labeler engagement and
    > performance ([[00:53:35]{.underline}](#section-42)).

-   **Security Audit and Closing**: Hemanth described using Claude to
    > perform a security audit on the \"Wall-E\" system, which involved
    > analyzing logs and open ports, with results indicating the system
    > is well-protected. Geoff concluded the meeting by designating the
    > ongoing review of labeler outputs as the primary bottleneck for
    > the first iteration of the model
    > ([[00:57:01]{.underline}](#section-46)).

-   **Training Bottlenecks and EDA Process**: Geoff Horowitz and Sachin
    > Pandey clarify the current project status, noting that the
    > exploratory data analysis process is mostly complete and the team
    > is currently focused on data labeling, which serves as the
    > bottleneck for moving to the next stage of training
    > ([[00:59:00]{.underline}](#section-48)).

-   **Baseline Model Performance**: The team confirms that the current
    > baseline model is functioning well for major classes, such as AI
    > support, noise lines, and sand patches, with predictions
    > demonstrating over 80 percent accuracy for classes that possess
    > clear features ([[01:00:18]{.underline}](#section-49)).

-   **Class Selection and Dropping Strategy**: Sachin Pandey explains
    > that the second iteration of the model involves dropping
    > unnecessary classes, such as white lines and chains, during
    > training to focus exclusively on essential patterns, which has
    > resulted in improved predictions for the classes the team intends
    > to prioritize ([[01:01:31]{.underline}](#section-50)).

-   **Progress Documentation**: Geoff Horowitz requests that Sachin
    > Pandey collaborate with Ratul Shashank to generate a report
    > summarizing the team\'s progress, current results, and next steps;
    > the report should be clear and informative without requiring an
    > excessive time investment to create
    > ([[01:02:27]{.underline}](#section-51))
    > ([[01:04:46]{.underline}](#section-53)).

-   **Workflow Sync Meeting**: Ratul Shashank is tasked with scheduling
    > a meeting for next Wednesday or Friday to provide an overview of
    > the current workflow to the team, with Geoff Horowitz noting that
    > the invitation should be open to all team members
    > ([[01:04:46]{.underline}](#section-53)).

-   **Synthetic Data Generation Strategy**: Pratyaksh Singh discusses
    > plans to use diffusion models for generating training data and
    > inquires whether the team needs to generate both foreground
    > objects and backgrounds or just the objects themselves; Geoff
    > Horowitz clarifies that previous discussions only focused on the
    > objects, but mentions the possibility of requesting more raw data
    > from Bridget if background data is insufficient
    > ([[01:05:53]{.underline}](#section-54)).

-   **Map Data Queries**: Pratyaksh Singh mentions having posted
    > questions regarding map data on Slack, which Geoff Horowitz agrees
    > to review over the weekend, requesting that Pratyaksh Singh also
    > copy Hemanth Sarabu on the communication to ensure comprehensive
    > context ([[01:07:11]{.underline}](#section-55)).

-   **Hardware Data Collection and Custom Application Demo**: Hemanth
    > Sarabu demonstrates a custom application designed to manage
    > hardware connections, collect motion capture data, run
    > optimization jobs, and visualize results using 3JS; the tool
    > allows for tracking lineage between different experiments and
    > datasets ([[01:09:57]{.underline}](#section-57)).

-   **Development Iteration and Speed**: Hemanth Sarabu reports that the
    > custom application took approximately five days to build,
    > accounting for both the physical hardware integration and the
    > algorithmic development; they emphasize that utilizing AI agents
    > allowed for this efficiency, despite the complexity of managing
    > multiple devices and database interactions
    > ([[01:16:57]{.underline}](#section-62)).

-   **System Design with AI Agents**: Hemanth Sarabu discusses how
    > working with LLMs like Claude has shifted their coding focus from
    > implementation details to high-level system design; they describe
    > an intention-driven workflow where they prompt the AI to act as a
    > senior engineer and UX designer to generate and iterate on system
    > options ([[01:19:33]{.underline}](#section-64)).

-   **Testing and Refactoring Strategies**: Hemanth Sarabu and Pratyaksh
    > Singh discuss the challenges of using AI agents for large-scale
    > app refactoring, noting that agents can struggle with code reuse
    > and breaking existing functionality; they emphasize the importance
    > of incorporating tests---including regression tests and Playwright
    > UI tests---early in the development process to ensure stability
    > ([[01:21:15]{.underline}](#section-65)).

-   **Code Optimization and Vectorization**: Hemanth Sarabu explains the
    > process of using iterative prompting to optimize code for
    > performance, where they first focus on correctness and
    > subsequently use AI agents to vectorize the code and improve
    > compute efficiency, achieving significant speed improvements
    > ([[01:25:48]{.underline}](#section-69)).

-   **LLM Evaluation and Future Hackathon**: Pratyaksh Singh and Hemanth
    > Sarabu discuss the potential of using LLMs as judges for code
    > optimization and system design; they conclude that the team should
    > organize a hackathon to share strategies and explore different AI
    > tools, particularly regarding post-training and RL-based
    > environments ([[01:28:31]{.underline}](#section-71)).

-   **Iterative Design Workflow**: Hemanth Sarabu describes an iterative
    > design process where they engage in extended, free-form
    > conversations with the AI over multiple days to build context, ask
    > the model to pose questions, and refine feature implementation
    > through a structured Q&A format
    > ([[01:32:01]{.underline}](#section-74)).

-   **Automated UI Testing with Playwright**: Hemanth Sarabu and Sachin
    > Pandey discuss using Playwright to automate UI testing, with
    > Hemanth Sarabu explaining that it runs a headless Chromium process
    > to interact with the DOM and simulate user actions, providing a
    > reliable way to catch UI bugs that backend-only tests might miss
    > ([[01:37:17]{.underline}](#section-78))
    > ([[01:43:12]{.underline}](#section-83)).

*You should review Gemini\'s notes to make sure they\'re accurate. [[Get
tips and learn how Gemini takes
notes]{.underline}](https://support.google.com/meet/answer/14754931)*

*How is the quality of **these specific notes?** [[Take a short
survey]{.underline}](https://google.qualtrics.com/jfe/form/SV_9vK3UZEaIQKKE7A?confid=QFC7BDzZWEkNH8IZiZebDxIUOAIIigIgABgECA&detailid=standard&screenshot=false)
to let us know your feedback, including how helpful the notes were for
your needs.*

**📖 Transcript**

Jul 3, 2026

## Iris Sync - Transcript

### 00:01:49

**Ratul Shashank:** Hey man.

**Hemanth Sarabu:** How\'s it going?

**Ratul Shashank:** Hi. What about you?

**Hemanth Sarabu:** Pretty good. Pretty

**Ratul Shashank:** Hello

**Geoff Horowitz:** Hey,

**Hemanth Sarabu:** good.

**Geoff Horowitz:** Rul.

**Ratul Shashank:** there.

**Geoff Horowitz:** Um, RTL, I saw here. I\'ll share I\'ll share it in
this chat so that everybody else can see it if you guys want to.

**Ratul Shashank:** Uh

**Geoff Horowitz:** But I saw your message. Uh, I haven\'t had a chance
to look at it yet, but I\'ll look at it uh, you know,

**Ratul Shashank:** uh-huh.

**Geoff Horowitz:** later today or this weekend and give you some
feedback.

**Ratul Shashank:** Yeah. Just just letting you know like uh uh in the
report I have given the data points that we need uh apart from the seven
files and uh and yeah it is the report also

**Geoff Horowitz:** Yeah.

**Ratul Shashank:** shows what the pipeline can pro produce right now.
It is not perfect but yeah I\'m working on it.

**Geoff Horowitz:** Cool. Thanks. Thank you. Um, okay. Hey guys. Hey
Brad.

### 00:02:58

**Geoff Horowitz:** You feeling better?

**Pratyaksh Singh:** Hey. Yeah. Uh, am I audible?

**Geoff Horowitz:** Yeah.

**Pratyaksh Singh:** Hey. Yes.

**Hemanth Sarabu:** What

**Pratyaksh Singh:** Yes.

**Geoff Horowitz:** Glad to

**Hemanth Sarabu:** happened?

**Pratyaksh Singh:** Uh, I think it\'s the heat,

**Geoff Horowitz:** hear

**Pratyaksh Singh:** man.

**Hemanth Sarabu:** Is the heat.

**Pratyaksh Singh:** I got sick.

**Hemanth Sarabu:** It heats.

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** Oh man,

**Pratyaksh Singh:** Eat.

**Hemanth Sarabu:** that\'s really bad.

**Pratyaksh Singh:** Heat.

**Hemanth Sarabu:** Yeah. Yeah. Yeah. He he always

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** protection. You need you need to move to a place
where you can get

**Hemanth Sarabu:** works.

**Geoff Horowitz:** AC.

**Pratyaksh Singh:** Uh, I So, okay. believe it. Uh it\'s a different
also like I have an AC but it broke down I

**Geoff Horowitz:** Yeah.

**Pratyaksh Singh:** think seven or eight days back. So I\'ve sent it to
service center to get it repaired. Let\'s see when I get it

**Geoff Horowitz:** Oh man.

**Hemanth Sarabu:** If you do an office very soon,

**Pratyaksh Singh:** back.

### 00:03:48

**Hemanth Sarabu:** soon very soon. Do an office. Pra actually agreed to
uh scout places.

**Geoff Horowitz:** Oh yeah. Project is it going to be in

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** Goa?

**Pratyaksh Singh:** Uh if I have to start it, yes, I think No, just
joking. Like I think I think we should probably take a safer option,
right? Because places like Goa,

**Geoff Horowitz:** Uh

**Pratyaksh Singh:** they have their own problem.

**Geoff Horowitz:** um well if if we get an office then uh I\'ll have to
make the trip over. So it should be somewhere that I uh I I enjoy

**Pratyaksh Singh:** I didn\'t

**Geoff Horowitz:** being.

**Hemanth Sarabu:** Well, you love Hyderabad, it seems, last

**Geoff Horowitz:** Yeah. But Hemoth,

**Pratyaksh Singh:** know

**Hemanth Sarabu:** time.

**Geoff Horowitz:** you keep telling me Hydrobot is so different in the
13 years since I was there.

**Hemanth Sarabu:** Yeah, it is. It is. I don\'t I don\'t think there
was much to there wasn\'t a terrible amount to like in Hyderabad 13
years ago. Um there is even less now I think but that\'s also because I
like nature quite a bit and Hyderabad is not around

### 00:05:00

**Pratyaksh Singh:** Yeah,

**Hemanth Sarabu:** nature

**Pratyaksh Singh:** I was going to say the same thing that is there
anything to like about biryani.

**Hemanth Sarabu:** biryani there\'s there\'s a there\'s a lot of

**Geoff Horowitz:** Do you have

**Pratyaksh Singh:** Yes, but I think I think it it has for

**Hemanth Sarabu:** um you have a lot of like uh nam architecture Nisam
culture,

**Pratyaksh Singh:** over

**Hemanth Sarabu:** museums. It\'s It\'s really about culture like you.
It\'s a very interesting It\'s a It has a very interesting history,

**Pratyaksh Singh:** a

**Hemanth Sarabu:** culture, um which obviously the city didn\'t do a
good job like um preserving the architecture etc. But uh that is that is
what you would you would go for. Now maybe jobs, right? Like honestly
jobs is probably

**Pratyaksh Singh:** So when I so when I went Hyderabad for for the G
what was that I forgot the name of it go J go J go J go J go J go J go J
go J go J go J go S smart yeah yeah go smart so

**Hemanth Sarabu:** you\'re

**Geoff Horowitz:** smart.

**Hemanth Sarabu:** smart.

### 00:06:07

**Pratyaksh Singh:** I was planning to go there.

**Geoff Horowitz:** Yeah.

**Pratyaksh Singh:** I talked to one or two of the locals that said that
you now it\'s just crowded as as hell

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** and then they have a lot of street shop around it.
So it\'s not worth it if you are in hurry. So I decided not to

**Hemanth Sarabu:** Yeah. Well, that\'s why I keep saying go off.

**Geoff Horowitz:** Yeah. How about let\'s do a company retreat. How
about that in Goa?

**Hemanth Sarabu:** Where? Okay, I\'m down. By the way, when I say Goa,

**Geoff Horowitz:** All right.

**Hemanth Sarabu:** I don\'t mean like the party Goa. There is a very
slow part of Goa with a lot of trees

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** Oh,

**Hemanth Sarabu:** and exactly.

**Pratyaksh Singh:** South Goa is beautiful. Like so this time when I so
previous year when I went to Goa

**Geoff Horowitz:** okay.

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** I I was in North Goa right that is like complete
party and all those things.

### 00:07:03

**Pratyaksh Singh:** Uh this year I think when I went to around New Year
I went to South and it is like so much it is so much better than North
is very beautiful.

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** It is very quiet and the beaches are very nice and
and

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** you know the sheer number of trees and everything
it\'s like it it feels very you

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** know calm and alive at the same time. It\'s
amazing.

**Hemanth Sarabu:** So we can do a retreat somewhere then.

**Geoff Horowitz:** I think that\'d be cool.

**Hemanth Sarabu:** You want to go in September,

**Geoff Horowitz:** In

**Hemanth Sarabu:** Jeff?

**Geoff Horowitz:** September,

**Hemanth Sarabu:** I need to visit my parents,

**Geoff Horowitz:** you you need you need to go in September

**Hemanth Sarabu:** so I\'ll probably go around that time.

**Geoff Horowitz:** though.

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** September is just going to be a little hard because
of the holidays, but I could do like October, November.

**Hemanth Sarabu:** That might be difficult, but I\'ll let you

**Geoff Horowitz:** All right. All right. Let\'s talk about it.

### 00:08:05

**Hemanth Sarabu:** know.

**Geoff Horowitz:** Um, is is going is going nice most of the year.

**Pratyaksh Singh:** I think September is September might be difficult.

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** Uh it\'s months doing the entire

**Hemanth Sarabu:** What? Oh,

**Pratyaksh Singh:** thing

**Geoff Horowitz:** Rainy

**Hemanth Sarabu:** I see. It\'s I mean it\'s fine.

**Geoff Horowitz:** season.

**Hemanth Sarabu:** Jet actually.

**Pratyaksh Singh:** and

**Hemanth Sarabu:** Maybe not. Maybe not. Maybe not.

**Geoff Horowitz:** Okay.

**Pratyaksh Singh:** I\'m not sure mans it is end of monsoon season

**Geoff Horowitz:** Uh,

**Pratyaksh Singh:** will it might be pleasant then

**Hemanth Sarabu:** Monster would be now, right? Because the best time
for go is actually winter at least.

**Pratyaksh Singh:** I think yeah so September

**Hemanth Sarabu:** Way

**Pratyaksh Singh:** is end of the months right so October November
December these

**Hemanth Sarabu:** back.

**Pratyaksh Singh:** are good times for This time also it\'s Yeah,

**Geoff Horowitz:** huh?

**Pratyaksh Singh:** I think I think monsoon is right now.

**Geoff Horowitz:** I I really do think we should find a time H. So we
should find we should find an opportunity to do

### 00:09:23

**Hemanth Sarabu:** We should. Yeah, I agree.

**Geoff Horowitz:** it.

**Hemanth Sarabu:** What about northeast?

**Pratyaksh Singh:** North is pretty good. Like if you love mountains,
it is

**Hemanth Sarabu:** Yeah, I mean Sachin went I guess Sachin didn\'t go
northeast.

**Pratyaksh Singh:** amazing.

**Hemanth Sarabu:** He went to the north, but that could be a cool place
to go. But Jeff hates the cold.

**Pratyaksh Singh:** It\'s

**Geoff Horowitz:** I I told you I did I did on Ritzer.

**Pratyaksh Singh:** not

**Geoff Horowitz:** It was like snowing the whole time.

**Hemanth Sarabu:** Amritsa.

**Pratyaksh Singh:** also in the old time.

**Geoff Horowitz:** Yeah,

**Hemanth Sarabu:** What?

**Geoff Horowitz:** I did Ritzer in uh It was like It was like January.
It was like January 1st or something.

**Hemanth Sarabu:** No way.

**Geoff Horowitz:** January.

**Hemanth Sarabu:** Not somewhere else.

**Geoff Horowitz:** What do you mean?

**Pratyaksh Singh:** Ombra doesn\'t snow.

**Geoff Horowitz:** No.

**Pratyaksh Singh:** It doesn\'t snow

**Hemanth Sarabu:** It doesn\'t sound

**Pratyaksh Singh:** in

**Geoff Horowitz:** I\'m telling you it was snowing there. I I I
remember.

**Pratyaksh Singh:** visiting Golden

**Geoff Horowitz:** Yeah. I visited the Golden Temple and and we went to
the border and uh did I ever tell you guys this

### 00:10:14

**Pratyaksh Singh:** Temple.

**Geoff Horowitz:** story? I\'ll I\'ll do it very quickly. We went to
the border um for the closing ceremony and on the India side it was like
it was insane. It was like a whole party. There were thousands and
thousands of people, right? And on the uh on the Pakistan side maybe
there was one

**Pratyaksh Singh:** Mhm.

**Geoff Horowitz:** person. It was like it was like a whole party on the
one side. The other side it was like they couldn\'t care less. Um

**Pratyaksh Singh:** They were working,

**Hemanth Sarabu:** It does not snow on umbrella,

**Pratyaksh Singh:** dude. They were working.

**Hemanth Sarabu:** dude.

**Pratyaksh Singh:** No, I I just saw something.

**Geoff Horowitz:** I

**Pratyaksh Singh:** It says first time in decades Amrits are witnesses
snowfall.

**Hemanth Sarabu:** Oh,

**Geoff Horowitz:** Okay. All

**Pratyaksh Singh:** So Thank

**Hemanth Sarabu:** Gemini is telling me that if you saw the city
covered in snow

**Geoff Horowitz:** right.

**Pratyaksh Singh:** you.

**Hemanth Sarabu:** or golden devil covered in heavy natural snowfall,
these are generally AI generated.

### 00:11:13

**Geoff Horowitz:** Okay. Okay.

**Hemanth Sarabu:** Yep.

**Geoff Horowitz:** It wasn\'t It wasn\'t like a It wasn\'t like snow
cover.

**Hemanth Sarabu:** You were you were experiencing AI generated in

**Geoff Horowitz:** It wasn\'t snow cover,

**Hemanth Sarabu:** person.

**Geoff Horowitz:** but it was like it was like first of all, it was
freezing. Second of all,

**Hemanth Sarabu:** Oh.

**Geoff Horowitz:** we were in a we were in a we were in a tuk tuk and
the guy was wearing like 18 different layers and I think there was like
there was like flakes of snow in the air.

**Hemanth Sarabu:** All auto

**Geoff Horowitz:** It was like it was like,

**Hemanth Sarabu:** pollution. That\'s

**Geoff Horowitz:** huh?

**Hemanth Sarabu:** pollution.

**Geoff Horowitz:** I\'ll have to find a picture for you.

**Pratyaksh Singh:** I don\'t think I start

**Geoff Horowitz:** All all you are convinced I\'m wrong. So uh so I
must be

**Hemanth Sarabu:** That is Pakist that\'s just Pakistan making you
think it\'s No,

**Geoff Horowitz:** right.

**Hemanth Sarabu:** it\'s not.

**Geoff Horowitz:** Nuclear

**Hemanth Sarabu:** Exactly.

**Geoff Horowitz:** winter.

**Hemanth Sarabu:** That\'s why you didn\'t see any of the soldiers
there.

### 00:12:06

**Geoff Horowitz:** Ah. All right. D. Um, where were we? Uh, so were you
guys able to look at the the conversation we had with Bedrock about the
mag data?

**Pratyaksh Singh:** Yeah. Yes.

**Geoff Horowitz:** Okay,

**Ratul Shashank:** Yeah.

**Geoff Horowitz:** Raul, are you still spearheading that or is Sashin,

**Ratul Shashank:** No, I am looking into it.

**Geoff Horowitz:** you\'re looking at it? Okay. Um,

**Ratul Shashank:** Yes.

**Geoff Horowitz:** we can still follow up with with open questions, but
I actually I do think that this is a pretty good place to start. I think
that he was able to tell us, you know, how to find signal there. My
biggest concern is essentially our ability to get the filter data or um
I don\'t you know some somehow generate our own corrections during
runtime but that\'s that\'s a problem that we can figure out with
bedrock too.

**Ratul Shashank:** Mhm.

**Pratyaksh Singh:** And the data that we received from bedrock for map
is it the corrected one

**Ratul Shashank:** No, it\'s wrong.

**Geoff Horowitz:** the it uh the the OB OBF

### 00:13:22

**Pratyaksh Singh:** or

**Geoff Horowitz:** files. OB Sachin, what\'s it called? OBF what is it?

**Ratul Shashank:** OG

**Geoff Horowitz:** Rol

**Ratul Shashank:** file the Mac data are in OFG

**Geoff Horowitz:** what?

**Ratul Shashank:** format.

**Geoff Horowitz:** OFG. Yeah, in the OFG files,

**Ratul Shashank:** Yeah.

**Geoff Horowitz:** at least the one that um I think Satchin shared on
Wednesday, it did have the filtered the filtered

**Hemanth Sarabu:** Yeah, they they have multiple Oh,

**Geoff Horowitz:** data.

**Hemanth Sarabu:** do you guys watch the videos already?

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** Yeah.

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** So you you know they talk about multiple levels of
filtering and I think a few of those lay few of those levels are there.
I think

**Ratul Shashank:** Uh, I had a question. Uh not not a question exactly
but uh like they were

**Hemanth Sarabu:** yeah

**Ratul Shashank:** talking about despiking. So uh uh is that regarding
the spiking the amplitudes or uh uh regarding uh or where the spikes are
generated in hits? Uh what is the spiking exactly?

**Geoff Horowitz:** I don\'t remember this.

### 00:14:46

**Geoff Horowitz:** He maybe you do. I don\'t remember the specific
context of what you\'re saying. If you like send over a, you know, a
time stamp, I\'m happy to look at it. But what you might be talking
about is when he was saying that like one of the later levels of
filtering, they might have multiple close together spikes and they kind
of combine them. Um

**Hemanth Sarabu:** Well, that\'s actually actually what what what are
you asking for?

**Geoff Horowitz:** what

**Hemanth Sarabu:** Do you do you know do you can you provide some more
context?

**Ratul Shashank:** uh like uh spikes can be interpreted differently,
right? Uh but I

**Hemanth Sarabu:** So you\'re you\'re you\'re talking specifically
about these jaggedy spikes, not these nice nice like peaks and valleys
that are relatively well smooth after the spiking. You\'re talking about
the former or the

**Ratul Shashank:** Uh uh I I I remember they talk about

**Hemanth Sarabu:** latter.

**Ratul Shashank:** despiking the data while

**Hemanth Sarabu:** Okay. So,

**Ratul Shashank:** processing

**Hemanth Sarabu:** so they do a few things.

**Ratul Shashank:** it.

### 00:15:54

**Hemanth Sarabu:** So number one is they comp they compens they
compensate or subtract the whatever they think the vehicle is producing
the mag effects that the vehicle is producing.

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** Okay. So that is the first thing they have to do and
we may or may not be able

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** to get a filter to do that which is what Jeff was
just saying and that\'s something we need to figure out with better.

**Geoff Horowitz:** Right.

**Hemanth Sarabu:** I believe immediately after they will try to remove

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** these relatively low amplitude meaning small heights
high frequency um spikes.

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** They\'re just they\'re just doing they\'re just
removing noise in some way. I don\'t know if it\'s right to call it
noise. It may not actually be noise. It may this might actually be
something else. But when he used the word despiking, it was in that
context. Um,

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** so it would be I I I remember this pretty clearly, I
think, but you know, you you can check out the part of the like Jeff
said, you can check out the part of the video where he brings that up.

### 00:17:07

**Hemanth Sarabu:** There\'s a clear difference before despike and after
despiking where there are these small small like uh pretty spiky uh
bumps, you know, like they\'re they\'re kind of um they\'re riding on on
the wave on the sign on the on

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** the 1D wave and they\'re he\'s talking about
removing that. So that\'s now that is most likely they\'re doing a
pretty simple like high frequency filter and maybe yeah that\'s what
they\'re doing and maybe they\'re maybe it\'s also amplitude capped
meaning they don\'t want to remove a big amplitude from that filter.

**Ratul Shashank:** Yeah,

**Hemanth Sarabu:** Does that make

**Ratul Shashank:** that\'s what I like.

**Hemanth Sarabu:** sense?

**Ratul Shashank:** I also thought that uh they are maybe normalizing
the amplitude. So rather than getting a huge gap between the low point
and the high points, they are removing the spikes.

**Hemanth Sarabu:** So that is a um Okay. So I think I think it would be
good to if

**Ratul Shashank:** Uh-huh.

**Hemanth Sarabu:** you\'re not familiar with the these kind of filters.
Um it would be good to read up on these uh you know like time series
filtering which we used to we did quite a bit for

### 00:18:22

**Pratyaksh Singh:** Hold

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** um I don\'t know if uh Pratak remembers but we did
we did this for Aura. Yeah.

**Pratyaksh Singh:** on.

**Hemanth Sarabu:** So we looked at these time series 1D filtering quite
a bit. So that that you should look at that. You know, there\'s some
pretty good videos, YouTube videos out there and then and then it\'ll um
you\'ll be you\'ll be able to kind of um um you\'ll be able to
understand what he\'s saying directly.

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** Yeah.

**Ratul Shashank:** Yeah.

**Hemanth Sarabu:** Yeah.

**Ratul Shashank:** So I uh as far as I understood I tried running uh
running a pipeline for uh the DRN data set. So let me just show my
screen. Uh my screen is visible right?

**Geoff Horowitz:** Yes.

**Ratul Shashank:** Uh so the report is not very uh it\'s not very clear
but uh this is just a preliminary uh testing like uh you can say I was
just uh understanding what uh we can do by studying the amplitudes and
the points where the amplitude shows spikes. So these blue circles these
are where the amplitude is showing spikes.

### 00:20:06

**Ratul Shashank:** Uh

**Hemanth Sarabu:** So, uh, wait, wait, wait.

**Ratul Shashank:** and no uh it

**Hemanth Sarabu:** Is this is that yours or um theirs?

**Ratul Shashank:** it is uh uh it is mine.

**Hemanth Sarabu:** It is yours. So, meaning you generated blue the blue
uh annotations.

**Ratul Shashank:** Okay.

**Hemanth Sarabu:** It\'s not from bedrock.

**Ratul Shashank:** Yeah, it is. Uh I generated that by running the OFG
file that they shared in DR data set. And to make sense of it, what I
did was uh like these

**Hemanth Sarabu:** So sorry I I\'m sorry if I missed this detail but
you\'re saying that the blue points

**Ratul Shashank:** are

**Hemanth Sarabu:** you extracted them they were they were populated in
the OG file or did you process the the data and apply a filter and look
for spikes and then draw these blue

**Ratul Shashank:** No uh these are just spikes uh in the data.

**Hemanth Sarabu:** points.

**Ratul Shashank:** So these are the spikes in the amplitude like these
are points where the amplitude was registered higher than the
surroundings.

**Geoff Horowitz:** in the filtered

**Ratul Shashank:** Uh it is not filtered actually just the raw OFMG

### 00:21:13

**Geoff Horowitz:** data.

**Ratul Shashank:** uh I have not filtered anything. So what I did to
make sense uh for me like these are the

**Hemanth Sarabu:** Okay.

**Ratul Shashank:** spikes and this particular uh this one it is showing
how the dipole is changing across the uh path. So if we can see there
are two uh rather high dipole interference in the entire path and these
two in dipole interference can be seen coinciding with the uh 0.8 8 mark
in these uh like these amplitudes are coinciding with this dipole
interference and this was the uh OFG file where they found a target soy
boy. So uh like this is just my preliminary attempt to understanding how
we can uh make use of Mac data but I think we can do this like this is
not I I\'m not uh passing the OFG file through any filter or uh uh I\'m
not desping I\'m just reading the amplitudes where it was registered and
correlating with correlating them with the position conditions where um
dipole interference was registered. So this point this is the highest
dipole in this entire path and this point was uh where they found the
target uh somewhere around this.

### 00:23:21

**Ratul Shashank:** So uh I don\'t mean to be presumptive but I think we
can uh follow follow along this uh this line of thought. I will look
into it if this is something useful or uh like because this is just one
track right if we for an entire

**Hemanth Sarabu:** So I True.

**Ratul Shashank:** uh

**Hemanth Sarabu:** So I think it\'s important to understand why this
works and when this might not work.

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** Does that make sense?

**Ratul Shashank:** Yeah. So that is why I also want to look at the
entire region like because this is just one track. uh I have not I have
not not run for the entire uh uh region

**Hemanth Sarabu:** Yeah.

**Ratul Shashank:** but my hypothesis is if I run for that entire region
there could be significantly more uh spike registered like this one
because each path will interfere interfere with each other it is my
hypothesis I uh I need to confirm that I\'m just showing you a

**Hemanth Sarabu:** Do you know? So I\'m looking at your title, right?
It says analytical signal plus peaks.

### 00:24:35

**Hemanth Sarabu:** Analytical signal meaning you you took the
derivative of the of the signal to that.

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** Is that right?

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** And then is that is that what is going on?

**Ratul Shashank:** Yeah.

**Hemanth Sarabu:** And then we found basically the zero values. Right.

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** We try to find the maximum maxima and minima.

**Ratul Shashank:** Yeah.

**Hemanth Sarabu:** Right.

**Ratul Shashank:** Local maxima and local

**Hemanth Sarabu:** Right.

**Ratul Shashank:** minima.

**Hemanth Sarabu:** Okay. Uh it\'s good. This could be a good baseline.
Could be a good baseline. Right. Um this could be a good baseline.

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** Now the reason we should be careful about this is
could the honestly I don\'t know why this wouldn\'t work somewhere else
like well for this to be true I mean for this to work everywhere I think
basically we need uh uh but I would be surprised if this is I\'d

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** be surprised if this is not filtered in any Right?
Because if uh if this looks imagine you have that uh spiky high
frequency stuff then if you have the

### 00:25:53

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** high high frequency stuff then you should see a lot
more of these peaks. Um now the the height of those peaks will be small
but you will see a lot of peaks.

**Ratul Shashank:** What are you doing?

**Hemanth Sarabu:** That\'s number one. number two.

**Ratul Shashank:** Uhhuh.

**Hemanth Sarabu:** So, so something else is going on here. Either the
signal is actually very clean or it has been filtered to remove the

**Ratul Shashank:** uh most of uh uh I did not mention that but these
peaks are where the

**Hemanth Sarabu:** peaks.

**Ratul Shashank:** magnetometer registered

**Hemanth Sarabu:** Sorry, these are

**Ratul Shashank:** uh readings compared comparable.

**Hemanth Sarabu:** what?

**Ratul Shashank:** Uh I was saying that these beaks are the
magnetometer where it registered uh readings compare more than 10
nanometer. Uh sorry more than 10 nanotesla. Sorry more than more than
five nanoes.

**Hemanth Sarabu:** Okay.

**Ratul Shashank:** Sorry that is wrong. More than five nanotesla. These
were the points. So I just put a threshold on the part anywhere they
show uh more than five nano Tesla.

### 00:27:00

**Hemanth Sarabu:** Yeah.

**Ratul Shashank:** uh and I me I remember I think they are using like
they the threshold that they are using also fall somewhere along like 5
nano Tesla to 10 Okay.

**Hemanth Sarabu:** Ah, I see. I I I don\'t recall that.

**Geoff Horowitz:** It was it was minimum. They they basically said
anything over 10 is they would mark as an object and anything between

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** five and 10 they tag as kind of like a likely object
deserving of of more

**Ratul Shashank:** Mhm.

**Geoff Horowitz:** attention.

**Ratul Shashank:** Targets like potential

**Hemanth Sarabu:** So maybe maybe maybe this uh maybe it is as simple
as finding

**Ratul Shashank:** targets.

**Geoff Horowitz:** Yeah.

**Hemanth Sarabu:** the peaks.

**Geoff Horowitz:** But no,

**Ratul Shashank:** Uh

**Geoff Horowitz:** I just uh again I the the sense that I got was after
correction a lot of these peaks get removed. Right.

**Hemanth Sarabu:** after correction. What do you mean?

**Geoff Horowitz:** Mhm.

**Hemanth Sarabu:** Who removes them?

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** Do you mean in his workflow or something like

**Geoff Horowitz:** Yeah. Yeah.

### 00:28:17

**Hemanth Sarabu:** this?

**Geoff Horowitz:** after after combining with like the after filtering,
right? After correcting for outside influences of the AUV or the
environment as a whole or, you know, whatever whatever the case may be,
um that many of these spikes get get removed right in the resulting
filtered data. Those those spikes don\'t exist.

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** So my yeah the I think there\'s pro like there\'s we
could make arguments about why this would work why this wouldn\'t work
like I think

**Geoff Horowitz:** Um,

**Hemanth Sarabu:** the arguments for okay let\'s do arguments against
this this simple algorithm would be that at the very least you need to
remove the effects of the vehicle because they

**Ratul Shashank:** Yeah. And the geology and the

**Hemanth Sarabu:** the sorry yeah actually I was thinking

**Ratul Shashank:** geology

**Hemanth Sarabu:** about that the question is does does the actual
geology can it actually influence this stuff that much and maybe the
answer is potentially um and the thing is but we there\'s no

**Ratul Shashank:** Uh,

**Hemanth Sarabu:** way I actually think there\'s no way you And if the
earth creates a

### 00:29:35

**Ratul Shashank:** I

**Hemanth Sarabu:** peak, then you can\'t remove it. You know what I
mean?

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** Like if the earth itself creates a peak, there\'s no
way for you to know. There\'s no like uh the way they filter out the
effects of the earth is by saying um look, my peaks and troughs need to
have a zero baseline like they should have a constant level. So I want
it to go up and then I want it to go down and then I want it to go back
up.

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** And uh I don\'t want my signal to slowly be going up
or slowly be going down you know I want it to sit on a flat line like
for example like a heartbeat right

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** the heartbeat it looks like it\'s on a flat line it
goes up and then comes back down and so on. So that is what they say.
They\'re they\'re saying like the mag effects of mag of the object look
like that

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** and if it is sloping up sloping down you know it\'s
on a curve that has got to be the earth.

### 00:30:36

**Hemanth Sarabu:** So then then the question becomes can the earth
actually create peaks

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** and and I think the answer is probably not and I
think if the earth creates peaks we wouldn\'t be able to tell but also
this is from one meeting with that guy right so he\'s seen a lot more
data so I have uh anyway that\'s that is why I don\'t think geology will
mess with this idea too much but I do noise.

**Geoff Horowitz:** Come on.

**Hemanth Sarabu:** Uh,

**Geoff Horowitz:** I thought Anna was saying that it\'s it\'s like you
run over Ferris rocks for example.

**Hemanth Sarabu:** but you can\'t tell. Like, I don\'t think you can
actually tell.

**Geoff Horowitz:** That\'s

**Hemanth Sarabu:** Um, like you can\'t actually tell the difference.
You know what I

**Pratyaksh Singh:** Uh-huh.

**Hemanth Sarabu:** mean?

**Pratyaksh Singh:** But the boat uh I think Shim also mentioned that
the boat might have moved and they also do record the bimetry too,
right?

**Ratul Shashank:** Yeah.

**Pratyaksh Singh:** So with that they can

**Geoff Horowitz:** Uh-huh.

**Hemanth Sarabu:** Yeah,

**Pratyaksh Singh:** tell

**Hemanth Sarabu:** but if it\'s subsurface, if it\'s sub bottom,

### 00:31:44

**Ratul Shashank:** Mhm.

**Hemanth Sarabu:** you couldn\'t. Anyway, but uh you guys are right.
Like we\'re still like um I guess I\'m uh I\'m getting ahead of myself.
We we\'re still very early in the this exploration.

**Geoff Horowitz:** Um, Hammond, do you do you need to run or do you
have more time?

**Hemanth Sarabu:** I got some more time.

**Geoff Horowitz:** Okay. I I this is a a good discussion, but also I I
want to keep Oh,

**Pratyaksh Singh:** Hey,

**Hemanth Sarabu:** Yes.

**Geoff Horowitz:** go ahead, Proctor.

**Pratyaksh Singh:** I just wanted to ask one question. Uh it looked
like you know they had the filtered data, they can subtract the baseline
from it and then they can detect the peaks also, right? So I don\'t
understand the need for deep learning it.

**Hemanth Sarabu:** All right. Yeah.

**Pratyaksh Singh:** Why not just use that

**Hemanth Sarabu:** No.

**Pratyaksh Singh:** pipeline?

**Hemanth Sarabu:** you can I don\'t think at any point um yeah we
don\'t we don\'t need to use deep learning now is Bridget going to like
that is she going to go like guys I told everyone we\'ll use AI you
can\'t put a uh a 20 40 year old filter there right um Uh maybe not.

### 00:33:01

**Hemanth Sarabu:** But we should okay let\'s say this. Let\'s figure
out a way to get really accurate results and then we\'ll figure out if
we need to add deep learning to it. But we should we should basically
take the approach that gives us the best

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** results.

**Pratyaksh Singh:** And also one

**Ratul Shashank:** Uh this is just a go.

**Pratyaksh Singh:** thing

**Geoff Horowitz:** We can also I mean there\'s also the case where we
just use it as an additional signal, right? the the the we get we get a
a classification from from the visual network and then you know this MAG
network even if it\'s just a time series analysis gives us an additional
signal and so it gives us more confidence or less confidence

**Pratyaksh Singh:** Yeah, this is what I wanted to talk about. It looks
like you know the map data isn\'t a available for every location. It\'s
just like you know one time series data for the whole board. So what I
got from it was that they will use a map to maybe pinpoint the areas
that they need to look at and in the XTF there will marks where there is
where there is you know an anomaly.

### 00:34:13

**Pratyaksh Singh:** Is that the case? Is that what you guys also got or
do you guys understand something else?

**Geoff Horowitz:** I I I do think that that\'s their part of their
pipeline. I think that\'s why the onboard reports show the waterfall
images and the MAG data.

**Ratul Shashank:** Mhm. I think like they uh the MAC data could be
useful in only in

**Geoff Horowitz:** Um,

**Ratul Shashank:** regions where the HTFS can\'t see very clearly like
in the NA region. Uh apart from that I think it would be very uh useful
but that is just my presumption.

**Pratyaksh Singh:** Uh I I think there is something else. I will wait a
minute. I just pointed out Uh, I I I\'ll share an image on

**Geoff Horowitz:** What you\'re pointing out that the peak

**Pratyaksh Singh:** Now I\'m pointing out that you know there is one
contact that is visible right and maybe that mag data is corresponding
to that contact. Do you get what I

**Geoff Horowitz:** He also said he also said yeah yeah he also said
that this mag data is

### 00:35:54

**Pratyaksh Singh:** mean?

**Geoff Horowitz:** unfiltered right so so again just kind of getting
back to the maybe one of the outcomes we we can use the unfiltered data
it\'s just going to give us a lot more false positives

**Ratul Shashank:** What are you

**Pratyaksh Singh:** by unfiltered.

**Ratul Shashank:** doing?

**Pratyaksh Singh:** What do you mean by unfiltered? The despite

**Geoff Horowitz:** By unfiltered, by unfiltered,

**Pratyaksh Singh:** ones

**Geoff Horowitz:** I mean before he applied the um like the calibration
corrections, before he applied um you know corrections for the movement
of the AUV.

**Pratyaksh Singh:** and got it. Got it. But yeah, anyways. Anyways, but
what I was saying is that you know if it\'s only a 1D time signal, I
don\'t know how much useful it can be for a 2D image, right? because you
can maybe get one direction from it but not the other one. You\'ll have
to rely on the exterior major. Not sure. Not sure though.

**Geoff Horowitz:** uh so so I\'m going to say like the action item here
is to I think we have more insights.

### 00:37:19

**Geoff Horowitz:** Let\'s let\'s see what signal we get from it. Let\'s
keep digging into it. Um, Rul, I personally I I do recommend that we
actually start out with the filtered data. Um, because we know that we
know that Bedrock gets a signal from the filtered data.

**Ratul Shashank:** and the filter data are the tip files they shared,
right?

**Geoff Horowitz:** No, it\'s Sachin. Do you still have the I was
looking for the image? I can\'t find it. I know you showed the image
last time um but I just don\'t see it.

**Sachin Pandey:** which

**Geoff Horowitz:** Suchin showed a um he opened up the OB of the OFB
file.

**Sachin Pandey:** are

**Geoff Horowitz:** Oh, here it is. No. um in the last meeting.

**Sachin Pandey:** like in last meeting.

**Geoff Horowitz:** Yeah.

**Sachin Pandey:** Yeah, I just rename in the OG to CSV and use this
extension to color it

**Geoff Horowitz:** Um yes. Yeah, that one. Do you do you still have
that

**Sachin Pandey:** out.

**Geoff Horowitz:** open? I\'m trying to see if I have it here.

### 00:38:46

**Sachin Pandey:** Yeah, I have it here.

**Geoff Horowitz:** Can you share your screen quickly? Okay. Uh I don\'t
know if you can make it a little bit bigger, but amplitude amplitude
filtered NT. Uh it\'s the next white one right there. amplitude filtered
NT at the top. That\'s their filtered data.

**Sachin Pandey:** Like they talked about multiple kind of filter like
do we know which kind of filter it is?

**Pratyaksh Singh:** I think I mentioned this is the final

**Geoff Horowitz:** So that\'s Yeah. Yeah.

**Sachin Pandey:** The final one,

**Geoff Horowitz:** That\'s after Go ahead.

**Sachin Pandey:** the one where they have converted the lows and highs
to only highs.

**Geoff Horowitz:** Uh I don\'t know if it\'s after that but I it is
after they apply these the calibrations and corrections. Um so that\'s
that\'s the one that they look at that amplitude filtered. That\'s the
one they look at to to generate a signal. They might do some more after
it but I think that\'s what we can work with. At least for now, rul um
let\'s start there.

### 00:40:20

**Geoff Horowitz:** Make sure we can get a signal from that and then you
know we can always work backward into the raw data if needed.

**Ratul Shashank:** Okay, I will uh I will uh I will get back to you on
this. I don\'t have much to say right now. Uh I I need to look at it. Uh
I will get

**Geoff Horowitz:** Okay.

**Ratul Shashank:** back.

**Geoff Horowitz:** Okay. Um so where are we on the rest of the
pipeline? Uh, has all of the data been um labeled correctly? What\'s
what\'s the status on the rest of

**Sachin Pandey:** So VW data is labeled in keyword.

**Geoff Horowitz:** it?

**Sachin Pandey:** Uh ent is I cued uh like the ent was divided in three
part. I just finished the keyword of one part and the other two are like
I asked them to review it again because there were some mistakes.

**Geoff Horowitz:** Hey

**Sachin Pandey:** These are just finishing up and after that I will
queue it and uh uh I also set up the ML in turn promoting base

**Geoff Horowitz:** Oh,

### 00:41:36

**Sachin Pandey:** and train models uh like on hold all the data

**Geoff Horowitz:** nice.

**Sachin Pandey:** set including the including raw and pro.

**Hemanth Sarabu:** What? You said you cleaned

**Sachin Pandey:** Yeah, like uh it generated some reports but uh

**Hemanth Sarabu:** already.

**Sachin Pandey:** we like it started the training. It\'s also getting
logged into the we can see here

**Hemanth Sarabu:** Okay. What is the result?

**Sachin Pandey:** not good for all the classes. Let me

**Hemanth Sarabu:** You guys using the Pro 6000 the black?

**Sachin Pandey:** ninja.

**Hemanth Sarabu:** Yeah.

**Sachin Pandey:** Yeah, all the agents are running here. Everything is

**Hemanth Sarabu:** All the agents you mean you mean like the ML
internon agent or there are more

**Sachin Pandey:** running.

**Hemanth Sarabu:** agents?

**Sachin Pandey:** So like I posted the two models Quen Quen and Gemma

**Hemanth Sarabu:** Oh,

**Sachin Pandey:** and

**Hemanth Sarabu:** for for coding.

**Geoff Horowitz:** Satchin set up his own LLM.

**Sachin Pandey:** yeah

**Hemanth Sarabu:** Nice. So such what is um what is what is the latency

**Geoff Horowitz:** Yeah.

**Hemanth Sarabu:** like

**Sachin Pandey:** it\'s fast like many like it\'s like time in in
thinking the output tokens are quite fast like it consumes half our
memory if One model is running and it it is automatically removed from
the memory after 5

### 00:43:05

**Hemanth Sarabu:** right interesting. Um so I was actually wondering

**Sachin Pandey:** minutes.

**Hemanth Sarabu:** Um I was I actually I guess I\'m surprised because
if you were using something like anti-gravity um your the serving the
server would be close to you.

**Sachin Pandey:** No like this is so this is the interface of ML intern
and the agent is using it\'s using three which is hosted on

**Hemanth Sarabu:** No, I mean for you if you were using a coding agent
instead of anti-gravity,

**Sachin Pandey:** no it\'s quite fast doesn\'t

**Hemanth Sarabu:** I would really interesting. You\'re right though.
Like I think thinking takes way longer.

**Sachin Pandey:** Yeah.

**Hemanth Sarabu:** Yeah. Yeah.

**Sachin Pandey:** And the benefit of local hosting is we get more
context window integr.

**Hemanth Sarabu:** So, are you seeing an improvement over um
anti-gravity

**Sachin Pandey:** No mainly these agents are running inside cloud port.

**Hemanth Sarabu:** quad? You mean the open quad code?

**Sachin Pandey:** No official one.

**Geoff Horowitz:** Oh, hold on. Suchin, you you had to clarify this for
me.

**Hemanth Sarabu:** I am

**Geoff Horowitz:** Can you clarify it for him, too?

### 00:44:32

**Geoff Horowitz:** It\'s not actually running

**Sachin Pandey:** It\'s not running cloud. It\'s using the cloud code
uh interface.

**Geoff Horowitz:** Claude.

**Hemanth Sarabu:** Right.

**Sachin Pandey:** So I I can just uh output this variable set this

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** variable to different model and just run.

**Hemanth Sarabu:** That\'s right. Clock code can be used with other

**Sachin Pandey:** It will it will use the local with API

**Hemanth Sarabu:** models,

**Geoff Horowitz:** Right.

**Sachin Pandey:** based billing but it doesn\'t get

**Hemanth Sarabu:** but AV uses billing that you shouldn\'t see any
charges, right?

**Sachin Pandey:** Yeah, it is true like if show special model and if I
do in without any the interface by default it is set to

**Hemanth Sarabu:** got it. But when I I\'m curious,

**Sachin Pandey:** G.

**Hemanth Sarabu:** is this better than do you feel like this is better
than the paid models?

**Sachin Pandey:** not better but it\'s good for some task where you
need a lot of context and search a lot of files like I discussed with to
like create a pipeline where the paid plot models can work as the
orchestrator and these models can work as a like workers which will like
pull the file search every file and just give the like reduce the
context in and out of the main

### 00:45:51

**Hemanth Sarabu:** H. So I heard people are using uh like Opus and
Mythos for planning orchestration at high level decision- making and
then they\'re using open source models for uh um for for like lower
level tasks which are easier to execute.

**Sachin Pandey:** Yeah, that\'s the plans similar to

**Hemanth Sarabu:** Interesting. Interesting. Okay. Yeah, please keep us
posted. I\'m very curious to see how uh

**Sachin Pandey:** Yeah,

**Hemanth Sarabu:** this

**Sachin Pandey:** like I tried open code as well but open codes
doesn\'t take the image as input but like cloud code can.

**Hemanth Sarabu:** Yeah,

**Sachin Pandey:** So

**Hemanth Sarabu:** is pretty nice. That rare

**Sachin Pandey:** images

**Geoff Horowitz:** Wait, did Sachin I don\'t know if I missed this.

**Hemanth Sarabu:** hits.

**Geoff Horowitz:** You said you got some preliminary results from um
MLG.

**Sachin Pandey:** let me I struggle a lot with organiz Okay.

**Geoff Horowitz:** What OS are you running these days? Such these why
he keeps

**Hemanth Sarabu:** these

**Geoff Horowitz:** changing.

**Hemanth Sarabu:** days.

**Sachin Pandey:** Uh can you repeat the question?

**Geoff Horowitz:** What OS are you running now?

### 00:47:21

**Sachin Pandey:** I updated 2.26.

**Geoff Horowitz:** Are you doing

**Sachin Pandey:** It\'s a lot better. Yeah.

**Geoff Horowitz:** what?

**Sachin Pandey:** Like it fixed the major issue which I was facing like
on boot up the screen doesn\'t load up. If I boot in like dual GP mode
both integrated and dedicated so it\'s

**Geoff Horowitz:** Uh, got

**Sachin Pandey:** finally fixed so like I don\'t have to like find a
work around

**Geoff Horowitz:** it.

**Sachin Pandey:** it my own

**Hemanth Sarabu:** Are you talking about Ninja or uh your own machine?
What about projection tool?

**Sachin Pandey:** machine

**Hemanth Sarabu:** What are you guys using? Oh, they\'re project. Oh,
they\'re here.

**Geoff Horowitz:** They\'re

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** here.

**Pratyaksh Singh:** Oh, I\'m using. It\'s

**Sachin Pandey:** This is a rough overview for the

**Pratyaksh Singh:** like

**Sachin Pandey:** models.

**Geoff Horowitz:** Sergeant, walk walk me through this page. There\'s
there\'s a lot going on.

**Hemanth Sarabu:** Nice.

**Geoff Horowitz:** Tell show me where to focus.

**Sachin Pandey:** These are the metrics overall metrics

**Geoff Horowitz:** Oh,

**Sachin Pandey:** and like because the data

### 00:48:22

**Geoff Horowitz:** cool.

**Sachin Pandey:** set was not finalized. So I just like pass run it
just for testing. So like main classes like ai big AI big will be

**Geoff Horowitz:** Is it a similar approach where each iteration gets
pushed to GitHub like a GitHub repo?

**Ratul Shashank:** No,

**Sachin Pandey:** this one.

**Ratul Shashank:** I think that was auto

**Geoff Horowitz:** Yeah, it was auto research.

**Ratul Shashank:** reset.

**Geoff Horowitz:** Is this a similar approach where you know each
iteration gets pushed or is this a different approach?

**Sachin Pandey:** in like ML in no it just like train the model and
model are

**Geoff Horowitz:** ML intern. Yeah.

**Sachin Pandey:** shaped group log

**Geoff Horowitz:** Oh, okay.

**Hemanth Sarabu:** Guys, I need to drop. This is actually very
interesting. But you know what this reminds me of? Kyak, you were pretty
you were a proponent of this back from pretty early boommy days where
you were like, I want to run experiments. I want to add these thin
layers for each experiment and then just run it. Sounds like this could
work really well with that where you come up with a bunch of ideas.

### 00:49:30

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** And an agent can actually add those layers and you
basically visualize

**Pratyaksh Singh:** Mhm. Yeah. Yeah.

**Hemanth Sarabu:** results.

**Pratyaksh Singh:** I\'m I think I am planning to do something like
this that you know. So my plan is that you know I don\'t want to just
have it you know run wild like I\'m still skeptical of those things
right. So what I want to do is

**Hemanth Sarabu:** I think I think blind running you should be
skeptical. But I think there is something here where there\'s something.

**Pratyaksh Singh:** Yeah. Mhm.

**Hemanth Sarabu:** Okay, go

**Pratyaksh Singh:** Yeah. So what I was saying is that you know uh I I
have the pipeline set like you know the

**Hemanth Sarabu:** on.

**Pratyaksh Singh:** whole pipeline is I decide the whole pipeline the
model can change annotation uh sorry augmentations model it can\'t touch
the data set and these things right so those things are standard it can
change the augmentation pre-processing post-processing and and the model

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** right and then and my plan was that have an agent
you give it a

### 00:50:31

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** seed paper right Let\'s say for example for I was
planning it for Iris right so I give it a seed paper like PTV3 and it
finds all the paper who site PTV3 right those paper will basically be
the improvement on PTV3 right and from there it filter out those papers
for which uh you know which which shows which promise better performance
than

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** PTV right it it gets their code from GitHub it
extracts the model out it runs the test to make sure that you know the
single page code that it wrote for model that works and then

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** it it feeds into it. uh it you know it feeds that
model into our pipeline and then it runs a hyperparameter search on it
and it it just it just you know the experiments are logged on clear ML
and

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** then it just shows us on weekly basis if if the
model improved or improved or if it didn\'t for that also I think we\'ll
need to set up very good evaluation right to know

### 00:51:35

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** that where the performance increase but this is
this is the plan I

**Geoff Horowitz:** Mhm.

**Hemanth Sarabu:** I mean the good thing is that at least we have uh
yes when you say good evals luckily for segmentation and object

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** detection the metrics are not bad they\'re not bad
metrics right

**Pratyaksh Singh:** Mhm. Yeah. But I think we\'ll need to find better
metrics in the sense let\'s say for I site where the

**Hemanth Sarabu:** um

**Pratyaksh Singh:** mistakes are do the mistakes happen at the boundary
right let\'s say do the mistake happens where tree and and a building
need are the mistakes there or is it is it you know classifying some
unclassified which looks like building into building

**Hemanth Sarabu:** Yeah. Yeah.

**Pratyaksh Singh:** right so

**Hemanth Sarabu:** I think I think iris card as all because I find
clubs

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** but images uh yes will also have those issues but it
won\'t be as difficult right to have um yeah I agree with you.

**Pratyaksh Singh:** Mhm. Yeah.

**Hemanth Sarabu:** We\'ll still we\'ll have to

### 00:52:32

**Pratyaksh Singh:** With images. I was saying with images you can use
uh it is easy to get these metrics also especially the boundary

**Hemanth Sarabu:** gone.

**Pratyaksh Singh:** metrics. You can just quium blur the mass and then
you can just get the boundary. You can extract the boundary and see your
accuracy at the boundary.

**Hemanth Sarabu:** Yeah. Yeah. Yeah.

**Pratyaksh Singh:** Anyways, did you try fable

**Hemanth Sarabu:** No,

**Pratyaksh Singh:** or

**Hemanth Sarabu:** I don\'t know why it\'s not. I don\'t have access to
it. They think I\'m a threat,

**Geoff Horowitz:** What do you mean

**Pratyaksh Singh:** Oh, no. I think they they

**Hemanth Sarabu:** maybe.

**Geoff Horowitz:** think?

**Pratyaksh Singh:** can I think they canled it for non-Americans,
right?

**Hemanth Sarabu:** How do they know that?

**Geoff Horowitz:** Oh, is that

**Hemanth Sarabu:** That\'s my point.

**Pratyaksh Singh:** But it\'s back now,

**Hemanth Sarabu:** It is. It is back. It is back.

**Pratyaksh Singh:** right?

**Hemanth Sarabu:** But I I\'ve been trying to use it and I have I It
won\'t let me. It\'ll take me to this dump page.

### 00:53:35

**Hemanth Sarabu:** And so right now I\'m like, \"Okay, I will I will
wait a little long. I mean, not wait. I I\'m too busy to look into it. I
do want to use it. I do want to use it.\" So recently,

**Geoff Horowitz:** Um,

**Hemanth Sarabu:** if you guys don\'t know, I\'ve uh with some friends
of ours, we\'re planning like a small like weekend near SF, but my
friends are coming from somewhere else and they have babies. Okay. So,
I\'m like,

**Pratyaksh Singh:** green.

**Hemanth Sarabu:** I don\'t want to look up places that have baby
things to do. And then also Airbnbs. What need What do we need to book?
So, I actually had Claude uh I actually had Claude create an app. It\'s
like a Tinder style app where it\'ll show me all these potential things
to do and also Airbnbs and stuff and then I go left, right, left, right
whether I like it or not. And then it\'s Yeah.

**Geoff Horowitz:** Dude,

**Pratyaksh Singh:** Uh,

**Geoff Horowitz:** come on. That that should be a business.

### 00:54:28

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** You should just do it.

**Hemanth Sarabu:** What do you mean to be a business?

**Geoff Horowitz:** Nope.

**Hemanth Sarabu:** If I can make that in 5 minutes,

**Pratyaksh Singh:** Hey.

**Hemanth Sarabu:** anyone can make that in five

**Geoff Horowitz:** But remember remember what what this guy said.

**Hemanth Sarabu:** minutes.

**Geoff Horowitz:** No moat. Okay. It\'s about execution.

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** Yeah,

**Pratyaksh Singh:** Hey, one thing like I also was thinking is that uh
so for I decide for

**Hemanth Sarabu:** that\'s

**Pratyaksh Singh:** QC these buildings and all they are difficult for
us right when the building entries made these things are difficult.

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** So one thing I thought was that you know you can
have something like Instagram or maybe Tinder where you just extract
that out and then it rotates and shows a video of everything if it\'s
correct your left side or right five something like that but

**Hemanth Sarabu:** Yeah, that would be great. Then our labelers can be
can be like, you know, Prate,

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** take it take it even more to the extreme.

### 00:55:17

**Hemanth Sarabu:** You know, these Chinese apps that go that give you
like gold stars, exploring gold stars, exploding hearts every time you
do something.

**Pratyaksh Singh:** Uhhuh.

**Hemanth Sarabu:** coupons like tu. We can add like a bunch of
gamification stuff

**Pratyaksh Singh:** Uhhuh. Ah.

**Hemanth Sarabu:** too.

**Pratyaksh Singh:** So yeah, this is one of the good thing, right? With
with at least with AI, you can you can get to at least a working pro
product really fast.

**Hemanth Sarabu:** That\'s

**Pratyaksh Singh:** That\'s why we have been able to even for labeling
that\'s why we have been able to build

**Hemanth Sarabu:** true.

**Pratyaksh Singh:** tools so fast

**Hemanth Sarabu:** Yeah. Yeah. Yes. I do want to show you guys the
stuff that I built for one robot. My my front end skills are negative
one. Okay, that my front end skills are negative one.

**Pratyaksh Singh:** Uh-huh.

**Hemanth Sarabu:** But now like now that Claude is so good at front
end, I\'m building so so many visualizations like it\'s on steroids.

**Pratyaksh Singh:** Uhhuh.

**Hemanth Sarabu:** Um and it\'s very helpful for debugging.

### 00:56:12

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** Um I want to show you some point Nita asked me. So I
showed Nita. I was very impressed with the front ends or or basically
the apps. And she was asking me, \"Hey, what do you use for what do you
use for your front end?\" I\'m like, \"I don\'t know. It\'s Claude.\" I
feel she\'s like, \"Yeah, but what library? I don\'t want uh I don\'t
want to use like a bad library. What do you use for I like I have no
idea.

**Geoff Horowitz:** It it probably it\'s it probably uses real or

**Hemanth Sarabu:** Just cl

**Pratyaksh Singh:** Yeah, we don\'t care. We don\'t care if it\'s a
security

**Geoff Horowitz:** some

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** threat.

**Hemanth Sarabu:** No. Uh nothing is hosted.

**Geoff Horowitz:** Yeah.

**Pratyaksh Singh:** Yeah,

**Hemanth Sarabu:** So I I am very serious about security but if nothing
is hosted.

**Pratyaksh Singh:** exactly. No.

**Hemanth Sarabu:** Yes.

**Pratyaksh Singh:** So like as long as it\'s on my computer, I don\'t
care about any security threat, right?

**Hemanth Sarabu:** Yeah.

### 00:57:01

**Pratyaksh Singh:** Then it\'s

**Hemanth Sarabu:** Yes. I did I did have claude after there was a few
security issues

**Pratyaksh Singh:** local.

**Hemanth Sarabu:** recently. Um and something Wally also behaved a
little weird and I think Sachin I asked Sachin for help for with
something. I also ran claude. I said, \"Hey, can you do a full audit on
Wall-E for security?\" And it did. It did like it was pretty cool to
watch it like work through all the logs, all the login attempts, go
through all the configs, uh look at the open ports, right? That was
actually very cool to watch. Um the good news is we\'re actually pretty
well protected. Um but uh yeah, all is fine, but it\'s very cool to see
that.

**Geoff Horowitz:** I\'m I\'m actually shocked because we did it so we
did it so kind of peacemeal and like whatever you know we just did
whatever we needed to to work in many

**Hemanth Sarabu:** No, no, no. Well,

**Geoff Horowitz:** cases.

**Hemanth Sarabu:** I think security we were pretty conscious from the
beginning.

### 00:57:55

**Geoff Horowitz:** Uh, were we

**Hemanth Sarabu:** Yeah, we\'re pretty conscious about Yeah, because
for the longest time it was we did not expose the Wall-E to the

**Geoff Horowitz:** okay?

**Hemanth Sarabu:** broader internet and when we decided to do it, I
think we were pretty careful. We\'ll see. I hope I hope uh I haven\'t
jinxed Wall-E now.

**Geoff Horowitz:** Um, okay. I I don\'t want to keep everybody too much
longer.

**Pratyaksh Singh:** You\'re going to show your apps.

**Hemanth Sarabu:** What was that?

**Pratyaksh Singh:** We\'re going to show your apps,

**Hemanth Sarabu:** Oh, do you you guys want to see it now?

**Pratyaksh Singh:** right?

**Hemanth Sarabu:** I can show it.

**Geoff Horowitz:** Yeah, Hemoth I I just want to wrap up this
discussion quickly.

**Hemanth Sarabu:** Yeah. Yeah.

**Geoff Horowitz:** Is that all right?

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** So Sachin uh so we\'re running the ML intern
simultaneously you\'re looking you\'re reviewing the labelers um
outputs. Is that right? Okay.

**Sachin Pandey:** Yes.

**Geoff Horowitz:** And then that\'s the bottleneck uh sachin and pratio
that\'s the bottleneck for training a first iteration of the model.

### 00:59:00

**Geoff Horowitz:** Um and then it am I right till there that\'s the
bottleneck for training the first iteration of the model just to

**Sachin Pandey:** the model that we can ship

**Geoff Horowitz:** to start seeing some of the results on the new data
seeing how we\'re performing.

**Sachin Pandey:** new data like NTF

**Geoff Horowitz:** Yeah. Hold on.

**Sachin Pandey:** and

**Geoff Horowitz:** Let me let me let me be more clear. Maybe I\'m
getting confused. All right. So, can you guys see my screen? Yeah. Okay.
So,

**Sachin Pandey:** yes.

**Geoff Horowitz:** we finished we finished this EDA process more or
less. I mean, we\'re we\'re still looking at the MAG stuff, but that\'s
different. We\'re we\'re in step number two right now, data reabeling,
right? And that\'s our bottleneck for step number three here.

**Sachin Pandey:** Yes.

**Pratyaksh Singh:** Oh, I think I think we should we are getting the
baseline model in the center right we

**Geoff Horowitz:** So

**Pratyaksh Singh:** can train a model uh I mean depends

**Geoff Horowitz:** okay have have we start I mean but for the ML intern
have we started training with our existing architecture and existing
models.

### 01:00:18

**Sachin Pandey:** Yeah, like the code code is the one that Kate shared
and he using the same code to just

**Pratyaksh Singh:** Okay.

**Sachin Pandey:** like fill in the data and finding the hyperparameters
and tuning it.

**Geoff Horowitz:** Okay,

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** great. So, we do have a

**Hemanth Sarabu:** You do have a baseline.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** baseline.

**Hemanth Sarabu:** Do we do we know do we know the u how how well or
poorly the baseline

**Sachin Pandey:** like it\'s working good for the major major classes
that\'s what I was

**Hemanth Sarabu:** does

**Sachin Pandey:** so if you see like which are above 80 like big AI AI
support repulse and noise lines I can show you some examples like the
classes which have like clear feature which are very easy to identify
have good uh good predictions AI ai will something like this. The center
one is the AUI big and these are like the supports for the like
windmill. So they are AI supports and like these are the noise strips
and these are like sand patch and these are some black

### 01:01:31

**Hemanth Sarabu:** Wait, wait. What is What is the headline?

**Sachin Pandey:** line majorly like for major classes it\'s working
good

**Hemanth Sarabu:** What is the headline?

**Sachin Pandey:** getting a good accuracy and these are some examples
of the prediction test set. So like I uh train a second iteration where
I remove the like the ones which we don\'t actually need like we try to
segment everything into different class. So because when we need it we
can just merge multiple classes into single one to train a different
model but we can\'t separate it. We ask our labels to separate
everything something like these.

**Hemanth Sarabu:** No, that\'s a good

**Geoff Horowitz:** Yeah, which is a good

**Sachin Pandey:** So like something like these we don\'t actually need.

**Geoff Horowitz:** idea.

**Hemanth Sarabu:** Yeah.

**Sachin Pandey:** We can just drop them. So that\'s what the second
iteration of model is doing

**Geoff Horowitz:** Okay.

**Sachin Pandey:** there.

**Geoff Horowitz:** Drop him during inance or during training.

**Sachin Pandey:** Yeah. They are running the like they training.

**Geoff Horowitz:** I didn\'t understand.

**Sachin Pandey:** So

**Geoff Horowitz:** You\'re going to

### 01:02:27

**Pratyaksh Singh:** We want to drop them during training,

**Sachin Pandey:** there\'s

**Pratyaksh Singh:** right? We want to drop them during training these

**Geoff Horowitz:** drop

**Sachin Pandey:** Yeah. Uh,

**Pratyaksh Singh:** classes.

**Sachin Pandey:** I already dropped them like uh it\'s not working. So
in notion I have like makes a note of like which are the classes I\'m
dropping mainly the like these white lines uh and chain like subject uh
like the ones which we don\'t

**Geoff Horowitz:** Such an S would you do me a favor?

**Sachin Pandey:** need.

**Geoff Horowitz:** Would you do me a favor? Can you work with Ratul to
generate a a a report? not like not too in-depth like Ratul does his
reports right where it\'s not like ultra ultra in-depth right it\'s not
100 pages but you know it it really kind of gives you the headlines says
a little bit about what we did what the current action uh the current
results are and maybe some of the next

**Sachin Pandey:** I can share this one.

**Geoff Horowitz:** steps

**Sachin Pandey:** This is the report which I used to generate this
website.

### 01:03:35

**Sachin Pandey:** It has like rough idea of all the classes, the points
and strong predictions,

**Geoff Horowitz:** Okay.

**Sachin Pandey:** weak predictions, where are the paths to of the
models and everything. Generally like these models we have removed it
because we generally like don\'t need it. We are only interested in the
main things mainly the like uh two three things are will be this uh
black patch which are like mines then for BW data set we are interested
in these things and the supports mainly like three or four classes which
we are interested in and we are doing like sand triple and sand patches
also like four five classes which we are like which we want to focus and
other things are just we can like we can just drop

**Geoff Horowitz:** Okay. Um

**Sachin Pandey:** So if you only focus on those patterns the
predictions are looking good

**Geoff Horowitz:** Okay. I I I hear you.

**Sachin Pandey:** right

**Geoff Horowitz:** I just what what I what I want what I think is
important is that we document we kind of document our progress, right?

### 01:04:46

**Geoff Horowitz:** I don\'t want it to take a ton of your time which is
why I think Ratul has a good pipeline down u but somehow like kind of
document where we are and where we want to where we want to go next so
that we can

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** look back at it you know see our progress over time
is that clear Sachin yeah um again I want to emphasize like it
shouldn\'t take a ton of your time but also it should

**Sachin Pandey:** Yes.

**Geoff Horowitz:** be clear and you know something that we can all kind
of understand as we look at

**Sachin Pandey:** Yeah. I will I will I will take that. You have to set
up it.

**Geoff Horowitz:** Speaking of which, Routool, I neglected to touch
base with you and I\'m sorry, but can can you can you set a meeting time
uh either next Wednesday or next Friday um to

**Ratul Shashank:** regarding the workflow.

**Geoff Horowitz:** Sorry.

**Ratul Shashank:** Regarding the workflow that I

**Geoff Horowitz:** Yeah. Yeah.

**Ratul Shashank:** use uh definitely

**Geoff Horowitz:** Yes. either

**Ratul Shashank:** uh next week uh when exactly next week can you be
more specific?

### 01:05:53

**Geoff Horowitz:** next Wednesday or next Friday. Do it uh do it after
this after this sync.

**Ratul Shashank:** Mhm. Okay. Okay. I will.

**Geoff Horowitz:** Okay?

**Ratul Shashank:** Okay.

**Geoff Horowitz:** And just, you know, in invite all of us, invite Sid.
And uh I mean nobody has to show up, but you know it\'s open to I I\'m
certainly interested and anybody else who\'s interested um can come.

**Ratul Shashank:** Okay, I will invite the entire team and we can
discuss

**Geoff Horowitz:** Yeah.

**Ratul Shashank:** that.

**Geoff Horowitz:** Okay. Uh any other any other high um high priority
things that we need to discuss or make decisions on before uh I guess he
if you have the time to to show us anything else you guys can think

**Pratyaksh Singh:** I think here. So for synthetic data generation I I
think we also need to generate the backgrounds right not just the
foreground object you also have to generate the background. What I mean
by background is the actual XTS. Is that true or do we only need to
generate the generate the

### 01:07:11

**Geoff Horowitz:** Bedrock only we we had only discussed the objects
themselves.

**Pratyaksh Singh:** object?

**Geoff Horowitz:** We only discussed the objects themselves. I would
say that if we think we don\'t have sufficient background, then let\'s
work to generate those two. I did ask Bridget for more role data.

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** Uh yeah,

**Pratyaksh Singh:** Yeah, that\'s

**Geoff Horowitz:** so she said she said she would look for that.

**Pratyaksh Singh:** needed.

**Geoff Horowitz:** Um but other than that, that\'s the only that\'s the
only additional data that I\'ve asked her for.

**Pratyaksh Singh:** Okay. So, I am uh I was planning to use diffusion
models to generate the training data, generate generate data.

**Geoff Horowitz:** Cool.

**Pratyaksh Singh:** I will let you know on Monday how that works out.

**Geoff Horowitz:** Sweet. Sweet. I\'m really excited to see

**Pratyaksh Singh:** Okay.

**Geoff Horowitz:** it.

**Pratyaksh Singh:** And uh and I po I posted some question regarding
the map data on Slack.

**Geoff Horowitz:** I I saw them. I\'ll look at them this weekend.

**Pratyaksh Singh:** All right. Thank you.

**Geoff Horowitz:** Is that okay?

### 01:08:10

**Geoff Horowitz:** Um,

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** will you will you also just CC Hemoth? Um, just so
that he can he can add some uh some context there too if I miss
anything. Thanks.

**Hemanth Sarabu:** Hey,

**Geoff Horowitz:** Okay. Uh, I think we discussed everything.

**Hemanth Sarabu:** f\*\*\*.

**Geoff Horowitz:** the TLDDR is um uh Sachin\'s going to try to
generate a a report of this. We\'re going to keep keep going on that. We
talked a little bit. Um Ratul is going to uh give us an overview of his
process next week. Also, um we discussed synthetic data briefly.

**Hemanth Sarabu:** That\'s

**Geoff Horowitz:** Pratak is working on a diffusion model and he\'s
going to give us an update on Monday. Yeah.

**Hemanth Sarabu:** nice.

**Geoff Horowitz:** Other than that, Hamoth, if you have the time, it\'s
all all you.

**Hemanth Sarabu:** Uh yeah. Yeah. Can you guys see the screen?

**Geoff Horowitz:** Yeah.

**Hemanth Sarabu:** Okay. I mean, I think there\'s a lot of context to
provide um about what these are supposed to do, but um so let me see if
I can do a good job explaining.

### 01:09:57

**Hemanth Sarabu:** So these two uh are used. So this one I\'ll start
with this one. there are some devices hardware that needs to be
connected and then it will actually show the position of that hardware
in some 3D space and um so that\'s not that\'s why it\'s not visible
right now but this is an app to collect some data and then run a like a
solver an optimization job and then visualize the results. So what I can
show you and you can use this to actually kick off the the data
collection process and I can show you take you through uh one I guess
one uh one journey. So this has already been solved. Uh we\'re actually
you\'re if you\'re wondering what are we looking at what we\'re looking
at? So, we\'re actually collecting this data with some with some
hardware. Okay, there are some very precise motion capture devices and
um measurement devices that we\'re using to collect data. Now, you know,
if you guys know me, you know I want to visualize everything. So when I
capture this data, I have multiple sources coming together to measure
the same thing.

### 01:11:28

**Hemanth Sarabu:** And so I\'m I\'m trying to measure uh positions and
orientations. And this will actually tell me, you know, what sort of
what sort of error I\'m getting between the different sources. And it
tells me what, you know, what is the confidence, etc. And you know of
course I can actually visualize uh I can this is using three 3JS which
we\'ve used of course at crer 2 this this is used to visualize the
different positions that were collected during that session and this is
not the only thing that is cool okay and then I can run a bunch of
checks I can run a bunch of checks Now it doesn\'t matter what it comes
up with. I can visualize specific examples and in these specific
examples I can actually visualize the errors. That\'s actually difficult
to see here but you can visualize the errors. And what I think is pretty
cool is I can go back here and decide that hey I actually don\'t like
this this config. I\'m going to find all the images with very high
error. Sort it.

### 01:12:49

**Hemanth Sarabu:** Remove the top five or 10 whatever. And then I\'ll
go here. Give it a new name. Okay. And then I can select some of the
parameters and then I can actually rerun this. Oh, and there\'s a bug.
There\'s a bug of O of course. I think I deleted a bunch of stuff.
That\'s why there\'s a bug. But once I do this, what it\'ll actually do
is, and I\'ll show you examples that I\'ve done this with before. Once I
do that, it\'ll actually track the lineage like which experiment is the
parent of which experiment, which data set and so on. So this is one of
the things that I built with um with cloud and then there are very
similar very similar like tools that look like that. Basically this is
another one that is very similar. I use it to run multiple solutions and
I can inspect it. I can inspect it and I can actually play the video.
Sometimes it works well, sometimes it doesn\'t work well.

### 01:14:05

**Hemanth Sarabu:** I can play the video. That is me. And I can view the
time series as well. I can run some other like postprocessing steps. I
can also I actually recently integrated some other thing. Was it an
inspect diagnostics? Okay. Where it was? Oh, maybe it was in your job.
Had to be in your job. Ah, trajectory. Yes. So I can actually compute
other things for velocity and stuff which I think is pretty cool. This
is all custom. And when I run any of these, it takes a it takes a while.
It can take seconds. It can take minutes depending on how large the data
set is. So there\'s a job tracker as well, which is pretty cool. And I
can kill the jobs here. Yeah, this is this is another thing that I
built. There\'s a bunch of diagnostics too which I don\'t use anymore.
And I can review like all the metadata that was going into these sol.

### 01:15:28

**Hemanth Sarabu:** I can compare different like algorithms here. I
don\'t have ways to compare different sessions but I can compare
different algorithms here. Um yeah this is another thing that we built.
And then there\'s this guy which you guys saw the cube that I added,
right? So this is the tool to m like create new cubes, maintain them,
etc. Let\'s see. Yeah, so you can actually create a new a new cube here.
You can create a new cube by scanning it. Uh if you want to print out
all the faces, that\'s here. You can add notes and then it actually
solves for the geometry. So I have that uh I have all that information.
Oh no, I think this is too old or or there\'s a bug cube file that\'s
new. Okay. So it\'ll actually solve for the geometry the ideal versus
what actually is what actually is going on. Um and then different errors
I think. Yeah. So this is what I got.

**Geoff Horowitz:** He do you uh do you have Claude like do um like
version control and everything automatically?

### 01:16:57

**Geoff Horowitz:** Do you not care about version control? What\'s
What\'s your Oh,

**Hemanth Sarabu:** No, it\'s doing it\'s committing to GitHub pretty
pretty frequently. Yes. Yes.

**Geoff Horowitz:** yeah.

**Hemanth Sarabu:** There is version control. Even the Yeah, everything
everything is version

**Geoff Horowitz:** Got

**Hemanth Sarabu:** control.

**Geoff Horowitz:** it.

**Pratyaksh Singh:** And like did it take zero short sorted or did it
take

**Hemanth Sarabu:** No, no, no, no. It was not shot.

**Pratyaksh Singh:** multiple?

**Hemanth Sarabu:** It was very iterative. Like um it\'s very iterative.

**Pratyaksh Singh:** How long did it take you to get this?

**Hemanth Sarabu:** Um the let\'s see. So there\'s So this is the How
long did it take me to build this? This is probably a couple of days,
maybe two and a half days. This is a couple of days. But remember like
um there\'s there\'s like actual physical hardware I\'m messing with and
then there\'s also math that I\'m doing algorithms uh checking things.
So I would say between these two it was like 5 days.

### 01:18:27

**Hemanth Sarabu:** This stuff is very easy stuff. This stuff is
relatively easy. This stuff is actually Yeah, this is relatively easy.
So, this this this takes time. I mean, I say time, but I would have
never been able to build this in

**Pratyaksh Singh:** Like imagine paying someone to build this, right?
It would have cost you that.

**Hemanth Sarabu:** Yes.

**Pratyaksh Singh:** And it\'s it\'s not like it\'s it\'s not a simple

**Hemanth Sarabu:** No,

**Pratyaksh Singh:** app.

**Hemanth Sarabu:** it is not. Uh very a lot of moving pieces. A lot of
moving pieces. A lot of database stuff.

**Pratyaksh Singh:** Hold

**Hemanth Sarabu:** Um I mean this app actually manages multiple uh
devices, meaning it actually connects to it connects to like a motion
capture system. It connects to cameras.

**Pratyaksh Singh:** on.

**Hemanth Sarabu:** Um and uh you know like it is a this is a pretty
complex app. I\'m not saying that\'s a good thing, but it is what it it
evolved to become. But um yeah, but the maybe

**Pratyaksh Singh:** Yeah, I was saying yeah,

### 01:19:33

**Hemanth Sarabu:** maybe

**Pratyaksh Singh:** it does a lot like you know you have you have a
place to track everything basically like whatever you need and you can
add things to you need it

**Hemanth Sarabu:** Yeah. Yeah. Yeah. My uh my uh pro my thinking went
like

**Pratyaksh Singh:** later.

**Hemanth Sarabu:** If I\'m doing coding work, my the amount of time I
spend thinking about uh functions and even algorithms has reduced and
now it has become system design.

**Pratyaksh Singh:** E

**Hemanth Sarabu:** System design but also this is cloud is pretty good
at system design.

**Pratyaksh Singh:** drink.

**Hemanth Sarabu:** So it has actually evolved even more to a very high
level system design like how what do we actually what is if this was a
product what should it look like what are what is the life cycle of the
product what am I going to do with this data you know it\'s all more in
intention driven like it\'s it\'s all intention related not
implementation related um but I do like two things implementation like I
will like

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** um I will ask cloud when I ask it I want something
and then I will say something like you\'re a senior UX person you\'re
also a senior engineer and then I have a few things that I care about
and I will say uh argue create so you know create options based on these
principles and let\'s talk through them and it\'ll actually you know
create these it\'ll have like four or five questions.

### 01:21:15

**Hemanth Sarabu:** It\'ll create these options. If they\'re good, I\'ll
select. Otherwise,

**Pratyaksh Singh:** in.

**Hemanth Sarabu:** I\'ll say I don\'t like these for whatever reason.
It\'s pretty

**Pratyaksh Singh:** Yeah,

**Hemanth Sarabu:** iterative.

**Pratyaksh Singh:** I think I think this is what I have also
experienced that uh it is quite good at writing code but structures and
then

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** you know uh you know class designs and all these
things is where it struggles with or at least the model that I use
struggle with like you know it won\'t it won\'t reuse your code or those
kind of

**Hemanth Sarabu:** I think. Yes. Yes. Yeah.

**Pratyaksh Singh:** things.

**Hemanth Sarabu:** I\'m trying to do a pretty major refactor and
everything

**Pratyaksh Singh:** Yeah,

**Hemanth Sarabu:** broke.

**Pratyaksh Singh:** you can\'t do it. You can\'t like uh one of the
thing like when I work with like big apps, right? What will happen is
that something will work and then it will ask it to refactor. It will
break down and then another thing that\'s a problem is that it assumes a
lot of thing and then it it like it reinvents a lot of thing and then
another thing one thing that I

### 01:22:25

**Hemanth Sarabu:** Yes. Yeah. 100%.

**Pratyaksh Singh:** also

**Hemanth Sarabu:** Yeah. I think it is a whole skill to learn how to
use these

**Pratyaksh Singh:** uh

**Hemanth Sarabu:** agents but also the agents are itself they\'re
getting better, right? So I what is the I don\'t know what is the time
value of

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** uh knowing it I don\'t know but I think we should
you know we should be on the cutting edge in any case we should be on
the cutting

**Pratyaksh Singh:** Yeah. So see if you don\'t uh I don\'t know like
you know if you

**Hemanth Sarabu:** edge

**Pratyaksh Singh:** don\'t look at the code everything looks good but
if you when you start to look at the code it\'s it\'s sometimes it\'s
sometime a

**Hemanth Sarabu:** I don\'t try this is this Tens of this is tens of
thousands of

**Pratyaksh Singh:** mess.

**Hemanth Sarabu:** lines. I can\'t look, you know,

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** like producing tens of thousands of lines in 4 days.
I don\'t I actually don\'t care about the code anymore.

### 01:23:20

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** What I what I do Yeah.

**Pratyaksh Singh:** Exactly.

**Hemanth Sarabu:** Yeah. So, it\'s more about tests. I actually start
with a lot of tests and I will say things like um I\'ll actually part of

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** my prompt will be you need to make this app agent
friendly. So, everything needs to be logged. all the traces should be
logged. Um,

**Pratyaksh Singh:** Hey.

**Hemanth Sarabu:** and then every change will come with tests and
it\'ll also back test. It\'ll do run regression tests to see if anything
broke. I also incorporate playright tests. Playright so that you can it
can actually test the UI by clicking instead of just doing like backend
calls, right? Um, so that helps quite a bit I believe.

**Pratyaksh Singh:** Okay,

**Hemanth Sarabu:** Um, the thing is I\'m pretty sure the issues that
you and I are talking about around reusing the same code and stuff, I\'m
pretty sure there\'s a way to like uh using skills. I\'m pretty sure
there\'s a way

**Pratyaksh Singh:** so there is There is one still which is what I
called ponytail

### 01:24:17

**Hemanth Sarabu:** to

**Pratyaksh Singh:** I think is it name I don\'t know wait let me find

**Hemanth Sarabu:** don\'t need it.

**Pratyaksh Singh:** it uh ponytails

**Hemanth Sarabu:** Oh, okay. That\'s funny.

**Pratyaksh Singh:** did it find it yeah this one yeah

**Hemanth Sarabu:** I found it.

**Pratyaksh Singh:** this is I think for that you know write less

**Hemanth Sarabu:** What? Uh,

**Pratyaksh Singh:** food.

**Hemanth Sarabu:** I\'ll check this

**Pratyaksh Singh:** I I haven\'t used it. Uh I mean still my so my
preferred way of working is that if

**Hemanth Sarabu:** out.

**Pratyaksh Singh:** I like if I need to build something for
visualization or for internal work or something that I don\'t care about
how the code is like something that I\'m going to use and then throw
away I will use agents to build that thing

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** I will I will use it for the visualization and
stuff but for things that I care about uh like I will I prefer a
conversational reason like I will

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** use chat GPT or I will use slot on the web UI and
then I will I will copy paste code instead of like having the agent type
to hold it because you know if it writes a lot of code uh it it seems
similar to what you know what you told me previously like when you
commit a lot of

### 01:25:48

**Pratyaksh Singh:** changes I become lazy to to check everything out
right

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** so it\'s similar like if I if I have things broken
down into part it is easier for me to check things out

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** and at least for point cloud it writes very slow
code like it\'s unoptimized like the algorithm that it uses it\'s it\'s
not optimal so in those cases

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** it\'s easier to find it and that\'s why like when
they fast for cloud code I was like it\'s fine I

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** mean I like the way it is working that but at least
for like web development or for these kind of things it is pretty good
so for 43 right so for example

**Hemanth Sarabu:** Hey, it\'s actually uh I don\'t know about portry.
I\'m not sure about pottery but um it is okay. So the for the stuff I do
it will create these loops which take seconds tens of seconds to return.
Um and so what I do is I will say okay let you know we\'ll run with it
first to that uh correctness and then we focus on correctness and then
once it\'s correct I\'ll say uh is this code vectorized is it optimized
for compute and then it will say no no no no there\'s like 10x 30x 20x

### 01:27:06

**Pratyaksh Singh:** Thank

**Hemanth Sarabu:** whatever the options to to improve it and then what
what we\'ll do then is actually write regress regression tests, input
output tests or for the existing data and then I will spin up another
agent that

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** says okay your only goal is to optimize this code uh
maintain correctness and this is the past data so you should be able to
get like bit identical results almost um and then it\'ll do it and
it\'ll do really well it will do like it will do really well um like
I\'ve had things that tens of seconds to under two seconds under one
second right Um yeah.

**Pratyaksh Singh:** Yeah. So,

**Hemanth Sarabu:** So

**Pratyaksh Singh:** vectorization converting to vectorized code,

**Hemanth Sarabu:** it

**Pratyaksh Singh:** I think it does it does pretty well. into bits for
it does pretty well. But if you want to if you wanted to completely
switch

**Hemanth Sarabu:** not just that like not just that there\'s people
that have said that it will

**Pratyaksh Singh:** to

**Hemanth Sarabu:** do this C C++ magic um where you know people have
not like really been able to optimize the code for whatever reason right
and then it\'ll it\'ll find it\'ll find a way to optimize so I actually
do the reason I\'m I\'m saying that cloud code can optimize code is
because it is very easy to build RL environments for code optimization
right so they have to be

### 01:28:31

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** pretty good at that um unlike say good point clouds
there\'s very

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** hard very hard to build those environments so they
they\'re not trained on that

**Pratyaksh Singh:** Yeah. Similarly, I think uh the one thing that you
say about system design, right? I think I think the only way to confirm
it is uh is with an LLM as a

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** judge, right?

**Hemanth Sarabu:** Yeah. Have you tried that? I haven\'t actually tried
it,

**Pratyaksh Singh:** So

**Hemanth Sarabu:** but I know that people are using similar ideas.

**Pratyaksh Singh:** what for for code optimization or

**Hemanth Sarabu:** So,

**Pratyaksh Singh:** LME?

**Hemanth Sarabu:** they\'ll have multiple agents with different
personas talk to each

**Pratyaksh Singh:** Huh.

**Hemanth Sarabu:** other. I haven\'t I haven\'t tried that.

**Pratyaksh Singh:** Mhm. No, I also haven\'t but I have like read about
it and and like you know in lot of these we should do a hacker.

**Hemanth Sarabu:** We should do a sorry what we

**Pratyaksh Singh:** Yeah, we should we should.

**Hemanth Sarabu:** just like try all these apps.

### 01:29:32

**Hemanth Sarabu:** But what were you

**Pratyaksh Singh:** Yeah, I was like you know the reason that these
coding agents are actually getting better is because

**Hemanth Sarabu:** saying?

**Pratyaksh Singh:** uh you know we are doing a lot of post training on
that along with pre and with LLM as a judge and then at least and even
for like your coding for your coding task there is a verifiable
environment right and then talking about optimization I think there are
some environments where you you have the LLM right kernel code to speed
up your so instead of like PyTorch and thing it will write

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** write on write on code to speed your inference and
you have verifiable reward for it right so it

**Hemanth Sarabu:** Yeah. Yeah.

**Pratyaksh Singh:** does critical I think I think it was Google which
reduced the time complexity of matrix

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** multiplication using using something like that

**Hemanth Sarabu:** Yes. Yes. Yes.

**Pratyaksh Singh:** but but for system design I think they will have to
use if you want to know about post training There is one Nathan Lambert
he has created for

### 01:30:37

**Hemanth Sarabu:** Yes. Yeah.

**Pratyaksh Singh:** RL and he also has YouTube video so you can just
watch it

**Hemanth Sarabu:** Yeah. Can you can you share what you think is good
in Slack for us all so all of us can see

**Pratyaksh Singh:** on

**Hemanth Sarabu:** it?

**Pratyaksh Singh:** okay I can I think at least for post training which
I think should be important for us because pre-training I don\'t think
we\'re going to we don\'t have the compute

**Hemanth Sarabu:** It doesn\'t matter because uh

**Pratyaksh Singh:** yeah we don\'t have the money to do it right but
for post

**Hemanth Sarabu:** yeah

**Pratyaksh Singh:** training I think I think this is this is a very
good report and

**Hemanth Sarabu:** agreed.

**Pratyaksh Singh:** then this is all about RL and then I will also
share one for

**Hemanth Sarabu:** Okay. Yes. Yes. These

**Pratyaksh Singh:** you

**Hemanth Sarabu:** two. Okay. Any questions or thoughts?

**Sachin Pandey:** Uh I have one question like when you prompt for like
how do you like what you ask do you ask for a function or like in your
application did you ask for each and every function or just like you
generalize it that well that cloud just filled in the gaps.

### 01:32:01

**Hemanth Sarabu:** Sorry. Can you say that again?

**Sachin Pandey:** So like you in your application like the website it
has a lot of function right you asked for each of them separately like
you like you make the dog

**Hemanth Sarabu:** Yeah.

**Sachin Pandey:** which like something this functions supposed to do
this this this and then it built it or like there were like some
functions which you didn\'t ask but Lord built it anyway and it was
helpful.

**Hemanth Sarabu:** Um I did not so this was not built in one shot
actually.

**Sachin Pandey:** Hey

**Hemanth Sarabu:** This was built iteratively throughout one one one or
two days. Each of these the for

**Sachin Pandey:** like function by function or complete

**Hemanth Sarabu:** example you see you see this this was like a few
hours this came on its own this auto recover this came in one shot but
the thing is I will tell it what I\'m trying to do and I will so I
don\'t so sometimes I will design I will write a doc when I already have
a lot of opinions about how a thing should be done or there\'s a lot of
context a lot of data lot of information right if it\'s already there if
it\'s not there I will actually talk I\'ll just talk to claude or chat
GBD for a while and usually I\'m talking about this some ideas I\'ll
talk over many days like whenever I have time some ideas I\'ll talk like
I\'ll sit down and talk with it for 30 minutes an

### 01:33:32

**Hemanth Sarabu:** hour um and then we\'ll come up with a uh you know
like at the end when it comes to actually what feature should be here
that is a Q&A claude will ask a question it\'ll have three to four
options and it will go through that one by one and that\'s how the
design gets uh made and then does that make sense so a lot of it is free
form like my conversation with it a lot of it is free form when it comes
to actually what featur should go on here like this idea and that idea
and this idea that they need to be here that will be that will come out
of Q&A by the time I\'ve had a long conversation it already has a good
idea of what I want and um yeah I will actually the the line I will say
is okay we\'re going to design this system ask me questions about it uh
check my thinking give me arguments tell me give me your opinion about
what\'s best for these considerations questions and let\'s go through
them and then have you guys have you guys seen Claude like uh do Q&A
with you?

### 01:34:46

**Sachin Pandey:** Yeah, like it suggest some options and we just have
to select

**Hemanth Sarabu:** Exactly. Yeah. So that is actually really good.

**Sachin Pandey:** it.

**Hemanth Sarabu:** I think that is really good. Um yeah. So that\'s
that\'s what I would I would do. And sometimes you can reject it too
because as you\'re working through it you realize this is not what I
want

**Sachin Pandey:** Should

**Hemanth Sarabu:** and then you you can like I guess start over. Um

**Sachin Pandey:** I do the conversation in the same uh same context
window with same

**Hemanth Sarabu:** yeah, it\'s all uh it\'s all in one session.

**Sachin Pandey:** session?

**Hemanth Sarabu:** It\'s all in one session. But uh yeah, one thing
I\'ve also found is not in full. Uh yeah, I agree. I agree. Uh it\'s all
in the same session. Typically I have a I have a session that has been
running for over a month and you know like claude will just keep
compacting it and compacting it and compacting it. And also by the way
after you finish like a project let\'s say there\'s a project and
you\'re happy with it at the end you can actually ask it to write write
down what is my style like what do I care about and it\'ll do a pretty
good job and you

### 01:36:01

**Hemanth Sarabu:** can make that a skill or whatever you want. By the
way,

**Sachin Pandey:** Yeah.

**Hemanth Sarabu:** if you\'re this this app looked pretty bad
initially. Like if you take a look at this app, right? It doesn\'t look
great, right? This this actually took pretty long for other reasons,

**Sachin Pandey:** Yeah.

**Hemanth Sarabu:** but this doesn\'t look great, right? So, what I will
do is this this app used to look pretty, you know, boring like this guy.
And uh what I will do is I will say uh you\'re a senior UX designer plus
engineer. Uh you care about the user\'s experience. You care about
clarity and and simplicity without giving control. Something like that.
Um, I would say review review this page aggressively and implement uh
implement improvements and nine out of 10 times it gives you a great
result. And so the the UX like the u UX I think this is pretty good
honestly. Um UX is is pretty good. I mean okay by the way this page has
not gone through that.

### 01:37:17

**Hemanth Sarabu:** This page has not gone through that. Uh, this page
has also not meaning I did it once and then I added a bunch of features.
I haven\'t done it again, which is why there\'s like it\'s a little
it\'s a little bad, but this one uh is pretty good, at least for my my
application. And so it does a really good job of uh reviewing the user
experience and making changes. The latest one is actually this guy. So
this is actually terrible. Used to be terrible to use, but now it became
very simple. It\'s very responsive. This was terrible before. And I
actually complained and said, \"You\'re a UX engineer. What What are
your solutions?\" Came up with good options.

**Sachin Pandey:** like giving personal value is important.

**Hemanth Sarabu:** Uh yeah. Yeah.

**Sachin Pandey:** And other thing was like you told you told about test
like the actual like clicking button.

**Hemanth Sarabu:** Yes.

**Sachin Pandey:** Can you elaborate elaborate it a little

**Hemanth Sarabu:** Yeah. Yeah. I\'m not an expert on it,

### 01:38:25

**Sachin Pandey:** more?

**Hemanth Sarabu:** but there\'s this thing called So, there was a time
when I was I was starting to build this stuff and a lot of the you know,
you click a button and it doesn\'t work. It\'s not responding, whatever,
right? But all the math and algorithms were working on the back end. So,
it was a UI problem.

**Sachin Pandey:** Look.

**Hemanth Sarabu:** So I said uh I found out that it was testing only
the back end. It wasn\'t actually spinning up a browser. But I believe
Playright which is by Windows or Microsoft um it\'s a web automation
platform. I don\'t know if this was always agents but it is agents. Now,
this guy will allow Claude to test the UI. In fact, it\'ll also take
pictures and check if everything is okay or not. Now, that\'s that is
about all I know. This is all I know. All I know is that it can use
playrate. It has the ability to view uh browser and it has the ability
to click through the browser via playright.

### 01:39:42

**Hemanth Sarabu:** And of course, if your app is local, you know,
there\'s no nothing. There\'s no Cloudflare or someone else like
blocking you from Yeah.

**Sachin Pandey:** I will I check it out because for generally I use
anti-gravity for testing out website like button clicks because it can
navigate the chrome browser easily.

**Hemanth Sarabu:** Look at that. It\'s actually Microsoft. They built
something useful.

**Sachin Pandey:** Is it only supported on

**Hemanth Sarabu:** No, no, no, no, no, no. I think this is uh

**Sachin Pandey:** Windows?

**Hemanth Sarabu:** multiple.

**Pratyaksh Singh:** What is

**Geoff Horowitz:** He I can\'t really tell if you hate Microsoft or
Google

**Pratyaksh Singh:** it?

**Geoff Horowitz:** more.

**Hemanth Sarabu:** I don\'t hate Google as much as Microsoft. I don\'t
hate Google.

**Geoff Horowitz:** You do. You do hate Google. You hate you.

**Hemanth Sarabu:** I don\'t

**Geoff Horowitz:** You hate Drive. You hate I mean you use it. I guess
you\'re right.

**Hemanth Sarabu:** Yes,

**Geoff Horowitz:** You you must hate Microsoft more because you use
Google products,

**Hemanth Sarabu:** I do.

**Geoff Horowitz:** but you you complain all the time about how Google,

### 01:40:42

**Hemanth Sarabu:** Drive.

**Geoff Horowitz:** you know, it\'s clunky and it, you know, they should
add this feature and that feature.

**Hemanth Sarabu:** It does feel like uh Windows drive is terrible.
Drive is the worst worst. That\'s it. I mean, okay, one drive is worse.
Sorry, but drive is pretty bad. Okay. Uh yeah, this is this is how I do
it. But Zach, I actually don\'t know what it does. All I know is that it
works. And when the UI breaks, I\'ll just be like, \"Hey, this is not
doing this.\" And then it will add a test for it.

**Sachin Pandey:** Yeah, I will check it out like if it is like uh using
something like the key for ID for the button to test it out then it will
be faster rather than the like looking at the image and then
anti-gravity just take the screenshot and then figure it out what to do
next and click the button. So that is like very slow

**Hemanth Sarabu:** I mean I think there\'s value that like I think some
things you have to do that

### 01:41:47

**Sachin Pandey:** to Yeah.

**Hemanth Sarabu:** right

**Sachin Pandey:** So, but like it it it can be speed up a

**Hemanth Sarabu:** um you know I I\'m wondering cloud code. Uh so it\'s
not as if cloud code can actually will actually run your um instance
outside of your machine, right? It\'s going to run it on your machine.
So it\'s not as if it\'s uh taking advantage of uh anobics compute. So
it\'s still on your compute. So is this is it slow on W as well? It does
take time. It does take time, right? Like it takes time for it to like
spin up the browser or whatever the headless browser. I I actually have
no idea how the infrastructure is different for headless.

**Sachin Pandey:** A browser works on local system like it access like I
give it a URL like use volley as a URL and it port like run a local
locally everything runs locally.

**Hemanth Sarabu:** Do you actually see the browser come

**Sachin Pandey:** Yes,

**Hemanth Sarabu:** up?

**Sachin Pandey:** in Chrome like it can uh interact and we can just
like step in to do something if

### 01:43:12

**Hemanth Sarabu:** I wonder if playright actually is a full I don\'t
know if clock is let

**Sachin Pandey:** needed.

**Hemanth Sarabu:** me let me ask why it\'s right here. Right. When this
display rate is sporally also thinking about getting a car and I
actually talked to Chad GBD about what car I want.

**Pratyaksh Singh:** Master stand.

**Hemanth Sarabu:** What\'s that?

**Pratyaksh Singh:** Why do you need

**Hemanth Sarabu:** No way.

**Pratyaksh Singh:** to

**Hemanth Sarabu:** No way. So it says yes playright. Chromium launch
spins up a real headless Chromium process on on the instance. It renders
the page.

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** Execute JavaScript and I evaluate the query the DOM
via CDP. Okay. So it\'s still getting the DOM. So no visible window
since it\'s headless but it\'s a full browser process with real

**Pratyaksh Singh:** Here

**Hemanth Sarabu:** V8 real layout real event loop. If I want a visible
window I\'d pass headless false that would require a display. So it has
been running headless.

**Pratyaksh Singh:** it is. I think before these LMS it was used

### 01:44:39

**Hemanth Sarabu:** Yeah. Yes.

**Pratyaksh Singh:** for for UI automation.

**Hemanth Sarabu:** Exactly. It\'s been around for a while.

**Pratyaksh Singh:** The good thing about playright is that you can
basically uh spin it up, use your mouse to click around things. It will
record those slicks as DOM interaction and then you can play them again
and again to

**Hemanth Sarabu:** M.

**Pratyaksh Singh:** test things out. So that was like the intended use
case for playback and then turns out that you know it sits very well
very nicely with LLM. So you know you can use the do you can use the DOM
elements to interact with it. You can take screenshots and all this. It
it was pretty awesome like even before much better

**Hemanth Sarabu:** Yeah. Yeah. Yeah.

**Pratyaksh Singh:** than

**Hemanth Sarabu:** I I I heard of this before. It only makes sense that
uh it only makes sense that um they move to agents now. Okay. All right.
I I do got to go. Hey, but any other ideas or

**Sachin Pandey:** Thank you.

**Hemanth Sarabu:** anything? No. Okay. All right, guys. I got to go. We
should do a hackathon and learn about how we all use Lols.

**Sachin Pandey:** All

**Geoff Horowitz:** Bye guys.

**Hemanth Sarabu:** Bye-bye.

**Sachin Pandey:** right.

### Transcription ended after 01:47:37

*This editable transcript was computer generated and might contain
errors. People can also change the text after it was created.*
