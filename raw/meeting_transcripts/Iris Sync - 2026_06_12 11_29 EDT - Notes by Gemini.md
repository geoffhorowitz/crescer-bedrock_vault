Jun 12, 2026

## Iris Sync

Invited [[Sachin Pandey]{.underline}](mailto:sachin@crescer.ai)
[[Pratyaksh Singh]{.underline}](mailto:pratyaksh@crescer.ai) [[Niveta
Iyer]{.underline}](mailto:niveta@crescer.ai) [[Hemanth
Sarabu]{.underline}](mailto:hemanth@crescer.ai) [[Geoff
Horowitz]{.underline}](mailto:geoff@crescer.ai) [[Siddharth
Soni]{.underline}](mailto:siddharth@crescer.ai)

Attachments [[Iris
Sync]{.underline}](https://calendar.google.com/calendar/event?eid=NnNzMHVxNzk3MmJqZGVwNXFoN2J1Mjd1OTdfMjAyNjA2MTJUMTYzMDAwWiBnZW9mZkBjcmVzY2VyLmFp)

Meeting records
[[Transcript]{.underline}](https://docs.google.com/document/d/1WcxBUWW_DACKDQDBlFIWzbOfGAskXcMMZy7_lMVpeAg/edit?usp=drive_web&tab=t.5yh6va5qdk2s)

### Summary

Team reviewed technical project status and established a generative
modeling strategy for improving synthetic data quality.\
\
**Project and Model Status**\
The team is cleaning digital elevation models for Block 3 while
addressing simulation to real performance gaps. Balancing research
projects and ongoing model development remains a priority for
operations.\
\
**Synthetic Data Strategy**\
A decision was made to utilize procedural generation and advanced
generative model techniques to enhance synthetic data. This approach
will improve control over point clouds for future demos.\
\
**Infrastructure and Regulation**\
Broad discussions addressed data center infrastructure challenges and
shifting regulatory landscapes for social media platforms. The
conversation examined impacts on development and government surveillance
policies.

### Decisions

Aligned

-   **Prioritize demo preparation** The team has prioritized the
    > immediate goal of preparing for the upcoming demo by committing to
    > produce four or five tiles where the model performs correctly.

-   **Adopt 3D synthetic data generation** The synthetic data generation
    > strategy is set to focus on procedural 3D scene and mesh
    > generation to emulate sensors for point cloud production, rather
    > than generating point clouds directly.

We\'ve **updated the Decisions section** using your feedback.

Let us know what you think:
[[Helpful]{.underline}](https://google.qualtrics.com/jfe/form/SV_5p6FWBVWvynleNU?isGoogler=no&isHelpful=yes)
or [[Not
Helpful]{.underline}](https://google.qualtrics.com/jfe/form/SV_5p6FWBVWvynleNU?isGoogler=no&isHelpful=no)

### Next steps

-   \[Sachin Pandey\] Clean port files: Fix remaining errors in the port
    > data. Complete this task by tomorrow.

    > \[Sachin Pandey\] Assist Rahul: Provide help for Rahul regarding
    > onboarding and orientation on Monday.

    > \[Hemanth Sarabu\] Update Tailscale access: Grant Rahul access to
    > the Tailscale network.

    > \[Pratyaksh Singh\] Provide demo tiles: Upload 4 or 5 tiles to the
    > application for the upcoming demo. Show successful model
    > performance in these examples.

    > \[Pratyaksh Singh\] Create synthetic scenes: Generate realistic
    > environments using Open Street Map shapes and procedural methods
    > for 3D object placement. Use these to create difficult training
    > data sets.

    > \[Pratyaksh Singh\] Collect training data: Aggregate data from
    > diverse locations using Open Topo. Use this to minimize the
    > simulation to reality gap.

    > \[Sachin Pandey\] Research generative models: Study control
    > networks and low rank adaptation approaches. Test these concepts
    > using Ninja.

    > \[Hemanth Sarabu\] Install GPU: Mount the 3090 Ti graphics card.
    > Take the Ninja system offline to perform this hardware update.

### Details

-   **Social and Connectivity Discussion**: The meeting began with a
    > brief social check-in, during which the team discussed internet
    > connectivity in India, noting that while connectivity is generally
    > reliable, power and electricity issues can persist in certain
    > areas ([[00:01:14]{.underline}](#section)).

-   **Block 3 and Project Review**: Sachin provided an update on the
    > status of Block 3, stating that the team is currently cleaning the
    > digital elevation models and addressing mistakes in the port, with
    > an aim to finish the process and proceed to a final review by the
    > following Monday ([[00:04:26]{.underline}](#section-2)).

-   **Team Expansion and Administrative Updates**: Geoff announced that
    > Rul will join the team on Monday to work with Sid and requested
    > that the team assist Rul with onboarding and ensuring they have
    > access to necessary tools, including Slack and Tailscale
    > ([[00:05:57]{.underline}](#section-3)).

-   **Bedrock Project Status**: Geoff shared an update regarding the
    > Bedrock project, noting that they expect to receive a go-ahead
    > imminently, which will necessitate balancing this work with
    > ongoing research and development projects, such as parent models
    > ([[00:07:04]{.underline}](#section-4)).

-   **Model Performance and Technical Challenges**: Pratyaksh reported
    > on the user interface for the labeling tool, explaining that while
    > the model performs well on synthetic data, there is a noticeable
    > sim-to-real gap, specifically with underperformance related to
    > surface switches in real-world data
    > ([[00:08:50]{.underline}](#section-5)).

-   **Technical Troubleshooting and Visual Analysis**: The team engaged
    > in a technical discussion regarding the model\'s performance on
    > spikes and divots, with Sachin and Pratyaksh screen-sharing
    > examples to analyze mask predictions and interpolation issues,
    > resulting in a plan to identify four or five high-quality tiles
    > for an upcoming demo ([[00:11:30]{.underline}](#section-7))
    > ([[00:13:58]{.underline}](#section-9)).

-   **Synthetic Data Generation Strategy**: Pratyaksh outlined a
    > strategy for improving data quality by utilizing OpenTopography
    > for ground data and implementing procedural generation methods to
    > create 3D structures such as buildings and trees, which can then
    > be integrated into realistic scenes using simulation tools
    > ([[00:24:11]{.underline}](#section-16))
    > ([[00:28:07]{.underline}](#section-20)).

-   **Generative Model Concepts and Control**: Hemanth introduced the
    > concept of using ControlNets and Low-Rank Adaptation (LoRA) to
    > exert greater control over generative models, suggesting that
    > while the implementation for point clouds may require further
    > study, these concepts could be useful for generating synthetic
    > data for the Bedrock project
    > ([[00:28:59]{.underline}](#section-21))
    > ([[00:34:27]{.underline}](#section-26)).

-   **Data Collection and Task Distribution**: Pratyaksh emphasized the
    > necessity of collecting diverse datasets from sources like ISC,
    > Walpert, Tet, and Photomap to minimize the sim-to-real gap, while
    > Sachin committed to spending time exploring the proposed
    > generative model techniques
    > ([[00:37:52]{.underline}](#section-29))
    > ([[00:41:27]{.underline}](#section-32)).

-   **Hardware and GPU Resources**: Hemanth and Geoff discussed the
    > current state of the team\'s GPU resources, noting that the team
    > is not currently starved for memory, though they acknowledged that
    > the price for purchasing additional units has increased since
    > their last acquisition ([[00:42:25]{.underline}](#section-33)).

-   **Infrastructure and Political Context**: The team engaged in a
    > broad conversation covering the challenges of data center
    > infrastructure, the impact of corruption on economic and business
    > development in India, and broader observations regarding political
    > trends, leadership, and democratic struggles in both India and the
    > United States ([[00:44:35]{.underline}](#section-35))
    > ([[00:47:41]{.underline}](#section-38)).

-   **Voting Preferences and Political Strategy**: Pratyaksh Singh
    > states that they vote for the BJP despite holding anti-Modi views
    > ([[00:58:52]{.underline}](#section-49)). They express frustration
    > with Congress, specifically criticizing the party\'s strategy of
    > increasing reservation quotas from 50% to 60% or 70%, which
    > Pratyaksh Singh believes is ineffective and ultimately harms the
    > party's electoral prospects
    > ([[00:59:58]{.underline}](#section-50)).

-   **Political Recruitment and Party Strength**: Sachin Pandey and
    > Pratyaksh Singh discuss the differences in party development,
    > noting that the BJP actively recruits leaders from other parties,
    > whereas they claim that Congress lacks prominent leadership
    > throughout India ([[01:00:53]{.underline}](#section-51)).

-   **Political Themes in Cinema**: Hemanth Sarabu, Pratyaksh Singh, and
    > Sachin Pandey discuss the presence of political propaganda in
    > movies. Pratyaksh Singh suggests that while some directors are
    > skilled storytellers, they often create content sponsored by the
    > BJP ([[01:00:53]{.underline}](#section-51)). Hemanth Sarabu cites
    > films such as \"The Kashmir Files,\" noting that these movies
    > frequently blame Congress for past issues, such as the special
    > status of Kashmir, while ignoring other contexts like network
    > shutdowns ([[01:02:07]{.underline}](#section-52)).

-   **Media Influence and Historical Narratives**: Hemanth Sarabu and
    > Pratyaksh Singh discuss how films and public discourse focus on
    > criticizing past leaders like Jawaharlal Nehru. Pratyaksh Singh
    > claims that most news channels in India have been purchased by
    > Adani, creating a landscape of state-aligned media
    > ([[01:03:20]{.underline}](#section-53)).

-   **Digital Surveillance and Platform Regulation**: Pratyaksh Singh
    > explains that the government has increased regulatory pressure on
    > social media companies like Meta. They note that the timeframe for
    > companies to respond to government requests for video removals has
    > been reduced to one hour to mitigate the risk of legal challenges
    > ([[01:04:22]{.underline}](#section-54)). Pratyaksh Singh further
    > asserts that the government intends to expand surveillance,
    > including the potential monitoring of messages on platforms like
    > WhatsApp ([[01:05:15]{.underline}](#section-55)).

-   **The Women\'s Reservation Bill and Privacy Legislation**: Pratyaksh
    > Singh describes a legislative controversy involving the Women\'s
    > Reservation Bill, which aimed to provide 40% representation for
    > women in Parliament. They explain that this bill was bundled with
    > privacy legislation that would enable the government to access
    > WhatsApp chats for tax and surveillance purposes. Pratyaksh Singh
    > notes that while Congress blocked the bill due to these privacy
    > concerns, the party faced significant public backlash for opposing
    > the reservation component ([[01:06:10]{.underline}](#section-56)).

-   **Future of BJP Leadership and Yogi Adityanath**: Pratyaksh Singh
    > and Hemanth Sarabu discuss the political future of the BJP, with
    > Pratyaksh Singh expressing doubt that the party will lose power
    > after Prime Minister Modi departs
    > ([[01:06:10]{.underline}](#section-56)). Sachin Pandey proposes
    > that Yogi Adityanath could be a successor. Pratyaksh Singh
    > characterizes Yogi Adityanath as a rigid, dictator-like figure who
    > is honest regarding corruption but is currently facing internal
    > party politics intended to curb their influence
    > ([[01:07:15]{.underline}](#section-57)).

-   **Critique of Rahul Gandhi**: Hemanth Sarabu discusses the
    > perception of Rahul Gandhi, critiquing the persistent framing of
    > Rahul Gandhi as a representative of \"young leadership\" despite
    > this image being maintained for decades
    > ([[01:08:20]{.underline}](#section-58)).

-   **Technical Closing**: The meeting concludes with Sachin Pandey and
    > Pratyaksh Singh briefly discussing technical aspects regarding
    > WhatsApp spikes and data file management
    > ([[01:08:20]{.underline}](#section-58)).

*You should review Gemini\'s notes to make sure they\'re accurate. [[Get
tips and learn how Gemini takes
notes]{.underline}](https://support.google.com/meet/answer/14754931)*

*How is the quality of **these specific notes?** [[Take a short
survey]{.underline}](https://google.qualtrics.com/jfe/form/SV_9vK3UZEaIQKKE7A?confid=dHnTnZaaMVTCMohFtMkoDxIUOAIIigIgABgBCA&detailid=standard&screenshot=false)
to let us know your feedback, including how helpful the notes were for
your needs.*

📖 Transcript

Jun 12, 2026

## Iris Sync - Transcript

### 00:01:14

**Hemanth Sarabu:** Hey,

**Sachin Pandey:** Hi.

**Hemanth Sarabu:** how\'s it

**Sachin Pandey:** Hi.

**Hemanth Sarabu:** going?

**Sachin Pandey:** It\'s going. What about

**Hemanth Sarabu:** Good, good, good.

**Sachin Pandey:** me?

**Geoff Horowitz:** Hey

**Hemanth Sarabu:** Yep. Are you on Twitter?

**Sachin Pandey:** No.

**Hemanth Sarabu:** Jeff, what about you?

**Geoff Horowitz:** I think I have one, but you know me. I haven\'t
looked at it in 15 years.

**Sachin Pandey:** Okay.

**Geoff Horowitz:** Come on. Don\'t you know nobody\'s on Twitter except
for um uh you know,

**Hemanth Sarabu:** Yeah,

**Geoff Horowitz:** Silicon Valley bros?

**Hemanth Sarabu:** that\'s true.

**Geoff Horowitz:** Uh on Alex said to me the other Alex said to me
yesterday she said she said Jeff I really want to watch Silicon Valley.
I said no you don\'t.

**Hemanth Sarabu:** Yeah, she does. It\'s a lot of fun. Very funny

**Geoff Horowitz:** Yeah.

**Hemanth Sarabu:** show.

**Geoff Horowitz:** So what I was thinking about was you know the it was
that show is what 15 years old something like that.

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** Um and I don\'t think much has changed.

### 00:03:08

**Hemanth Sarabu:** No. Yeah. Everything they say they say on there is

**Geoff Horowitz:** Yeah.

**Hemanth Sarabu:** true.

**Geoff Horowitz:** Yeah. Yeah.

**Hemanth Sarabu:** I\'ve lived it. that lived it.

**Geoff Horowitz:** Um we are we waiting are we waiting for we waiting
for project?

**Hemanth Sarabu:** Where?

**Geoff Horowitz:** When is India going to come into the 21st century?

**Hemanth Sarabu:** Jeff, I can drive 40 minutes from where I am and
have no signal in San

**Geoff Horowitz:** Right. But but Sid is basically in the middle of San

**Hemanth Sarabu:** Francisco. Oh,

**Geoff Horowitz:** Francisco.

**Hemanth Sarabu:** what what is he saying? He has pretty good internet
connectivity. What? He\'s having power

**Geoff Horowitz:** No,

**Hemanth Sarabu:** issues.

**Geoff Horowitz:** the the the hotel that he\'s at are the internet
service

**Hemanth Sarabu:** That that is that is not that is not common.

**Geoff Horowitz:** pro.

**Hemanth Sarabu:** That is not common. In fact, you know, like I\'ve
had issues with that too multiple times uh in the last 12

**Geoff Horowitz:** Okay.

**Hemanth Sarabu:** months. Yeah.

### 00:04:26

**Hemanth Sarabu:** Uh there\'s a few things that India has India really
has down. Um I don\'t think electricity is one of them but I think
connectivity is pretty good.

**Geoff Horowitz:** There he is. Okay. Hey brother.

**Pratyaksh Singh:** All right, Jeff.

**Hemanth Sarabu:** What do what do your friends call you? What\'s your
nickname?

**Geoff Horowitz:** Um

**Pratyaksh Singh:** Uh, nothing.

**Hemanth Sarabu:** full name protect.

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** I don\'t believe

**Pratyaksh Singh:** Yeah,

**Hemanth Sarabu:** it.

**Pratyaksh Singh:** it is true.

**Hemanth Sarabu:** Okay, I\'m just joking.

**Geoff Horowitz:** um all right. I Let\'s Let\'s jump in. Such an where
are we on block three?

**Sachin Pandey:** Uh they are cleaning the dam and tomorrow we will uh
clean the remaining mistakes in port.

**Geoff Horowitz:** Okay. Haven\'t they been cleaning the dem for a

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** while?

**Sachin Pandey:** Like there are around 440 files. Uh they\'re working
on it for around two days.

**Geoff Horowitz:** Oh. Oh, right. Right. This is the second round of
reviews.

**Sachin Pandey:** At least this time the mistakes are less.

### 00:05:57

**Sachin Pandey:** They are taking time but the mistakes has

**Geoff Horowitz:** Good. Okay.

**Sachin Pandey:** reduced.

**Geoff Horowitz:** Oh, good. I\'m all right with that then. Um, so then
tomorrow they\'re going to clean and poetry. You expect that to take
what? Two working days.

**Sachin Pandey:** No, I will try to finish it by tomorrow.

**Geoff Horowitz:** Oh, you\'re going to do it.

**Sachin Pandey:** I I No,

**Geoff Horowitz:** They\'re not doing it.

**Sachin Pandey:** I will also help out with

**Geoff Horowitz:** Okay. Okay.

**Sachin Pandey:** them.

**Geoff Horowitz:** Um and then what does that mean? A final review on
Monday.

**Sachin Pandey:** Yeah. Saturday, Sunday and Monday.

**Geoff Horowitz:** Sunday and Monday. Okay. Okay. Cool. Anything you
need?

**Sachin Pandey:** Come

**Geoff Horowitz:** All right. Okay. Um,

**Sachin Pandey:** on.

**Geoff Horowitz:** great. I mentioned to you Sachin Rul is starting
Monday. Um, he\'s going to be working with Sid, but uh, you know, if he
needs anything, just give him a hand, please.

### 00:07:04

**Sachin Pandey:** Okay.

**Geoff Horowitz:** Thanks. I mean, obviously not like work-wise. if he
needs help getting situated um at all, you know, help him out. Thank
you.

**Sachin Pandey:** Yeah.

**Geoff Horowitz:** Uh he do we need to add him to tail scale?

**Hemanth Sarabu:** Yo, did we give him a We did.

**Geoff Horowitz:** We gave him an email.

**Hemanth Sarabu:** Okay.

**Sachin Pandey:** Heat.

**Geoff Horowitz:** I\'ve added him to Slack. Um I think tail scale is
the the other thing.

**Hemanth Sarabu:** Mhm. We haven\'t heard back from Bedrock yet, right?

**Geoff Horowitz:** No, not today. I mean, you know, it sounds like
it\'s imminent, but actually,

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** I guess that\'s maybe somewhat pertinent. Project
Dr. Sachin, um, we had a call with Bedrock yesterday, with the CEO of
Bedrock yesterday. Uh nothing notable really came out of the
conversation according to him. He just wanted to meet us and get a sense
of who we are, what we\'re offering.

**Hemanth Sarabu:** Can you see?

**Geoff Horowitz:** Yeah, a relatively new CEO. Um but he did say that
they think the um the the projects that they were that were working on
for that uh UKHO project UKRN project is going to be imminent and so
sorry let me rephrase that.

### 00:08:50

**Geoff Horowitz:** they think that they\'re going to get the go-ahad on
that project imminently. Um, which, you know, for us means that we can
kind of pick up and start working on it again when we get some time.
Product, we\'ll have to we\'ll have to um we\'ll have to find a way to
kind of balance this with the ongoing R&D projects like the parent
model, things like that. Um but certainly the yeah certainly the

**Pratyaksh Singh:** Makes sense.

**Geoff Horowitz:** um uh synthetic data generation I I would assume
would have overlap. Um but I guess we can start talking about that now.
Um yeah, do you want to do you want to take over? Anything you wanted to
add to that?

**Hemanth Sarabu:** No.

**Geoff Horowitz:** Do you want to take over?

**Hemanth Sarabu:** Me or

**Geoff Horowitz:** Uh, I\'m sorry. I\'m sorry. I\'m sorry. Project, do
you want to take

**Hemanth Sarabu:** production?

**Pratyaksh Singh:** uh yeah I mean I shared the update uh I shared

**Geoff Horowitz:** over?

**Pratyaksh Singh:** the UI that you know that I build to expose the
labeling tool right the thing is that you know with synthetic data

### 00:10:05

**Geoff Horowitz:** Yeah.

**Pratyaksh Singh:** it works pretty help right but uh with real data it
is underperforming especially for the surface switches

**Hemanth Sarabu:** Sorry,

**Pratyaksh Singh:** right

**Hemanth Sarabu:** can you sorry uh you\'re saying with synthetic data
the model is doing well

**Pratyaksh Singh:** yeah

**Hemanth Sarabu:** and with Oh, you mean like testing on synthetic data
is doing

**Pratyaksh Singh:** but yeah testing on synthetic

**Hemanth Sarabu:** well.

**Pratyaksh Singh:** data is

**Hemanth Sarabu:** Okay. So, we have a sim to real gap.

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** So for example, this is one of the test style in
basic liquids, you know, all of the mistakes that we added, right? But
uh we are trying to you know uh look at basically looking at all the
tires and seeing if there are some places where you know the model is
performing. But we me and Sachin we were able to find Sachin mostly has
been looking through it looking through the tiles and uh we have we have
been able to find like two or three files where the model does pretty
good right but uh you know most of the tiles most of the mistakes are
for uh most of the DMs have this uh surface switch issues so there uh
it\'s underperforming and we

### 00:11:30

**Hemanth Sarabu:** What?

**Pratyaksh Singh:** are trying to get you uh uh recall it

**Hemanth Sarabu:** Recall issue. Precision issue.

**Pratyaksh Singh:** is like you know it is not it is not marking the
mistakes basically.

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** Uh there is one more thing that we are trying to
try out is uh yeah so that\'s

**Hemanth Sarabu:** Do you do you have an idea as to why it is uh

**Pratyaksh Singh:** uh-huh I

**Hemanth Sarabu:** struggling?

**Pratyaksh Singh:** think you know uh in the real images uh the
mistakes are mostly with surface switch right in the real de most of the
mistakes are for surface there it

**Hemanth Sarabu:** Mhm.

**Pratyaksh Singh:** is underperforming whereas I think wherever there
is spikes and all the model is kind of doing a decent job right but

**Hemanth Sarabu:** Can you show

**Pratyaksh Singh:** uh I\'ll share one

**Hemanth Sarabu:** them?

**Geoff Horowitz:** project.

**Pratyaksh Singh:** example on this on slap

**Geoff Horowitz:** I was going to say if you can share a tile with me,

**Pratyaksh Singh:** yeah

**Geoff Horowitz:** I can show it here. That\'d be helpful.

**Hemanth Sarabu:** We\'re moving.

### 00:12:55

**Sachin Pandey:** I can also share it in

**Pratyaksh Singh:** It\'s brief. Yeah. Sachin,

**Sachin Pandey:** chat.

**Pratyaksh Singh:** can you can you share your screen? Maybe show some
go through some of examples if you have downloaded locally.

**Sachin Pandey:** Yeah.

**Pratyaksh Singh:** So I think you know the thing is that we generated
for few of the cases you know but uh in real there are few more cases
which are we can share images and

**Geoff Horowitz:** I think it\'s I think it\'s new since they
integrated uh chat into

**Pratyaksh Singh:** now

**Geoff Horowitz:** meeting notes or meeting chat.

**Sachin Pandey:** these areas. So it is getting

**Hemanth Sarabu:** I don\'t know.

**Sachin Pandey:** marked.

**Hemanth Sarabu:** What are we uh Can you What is going on with audio?
Oh,

**Sachin Pandey:** Is it my audience?

**Hemanth Sarabu:** um I\'m hearing an echo,

**Geoff Horowitz:** What are you hearing your love?

**Hemanth Sarabu:** but I think it\'s fine.

**Geoff Horowitz:** I think it\'s just you.

**Hemanth Sarabu:** Oh,

**Sachin Pandey:** Oh,

**Hemanth Sarabu:** okay.

**Geoff Horowitz:** Oh. Oh. Oh. Now I hear

### 00:13:58

**Sachin Pandey:** like the Sorry. Is it happening from my side?

**Hemanth Sarabu:** I think so, but it\'s not happening anymore.

**Geoff Horowitz:** Yeah.

**Hemanth Sarabu:** Okay. Not happening.

**Sachin Pandey:** Okay.

**Hemanth Sarabu:** Zach, can you um can you walk us through the through
the file?

**Sachin Pandey:** Yeah. So this is like one of the file where the there
are three spikes in the data which

**Geoff Horowitz:** Help.

**Sachin Pandey:** is uh getting marked like these red dots like this
also but this is not actually a mistake because these three are getting
marked

**Hemanth Sarabu:** Mhm. What do we have a sense of our precision recall
for these spikes and divots?

**Sachin Pandey:** Uh no like in this example

**Pratyaksh Singh:** Oh,

**Hemanth Sarabu:** What about qualitatively?

**Sachin Pandey:** also. Uh no idea like this is a new file which I just
predicted. Uh like it generally has the points which we remove so we
added it back to add more noise in the data. So model can identify it on
earlier pence like

**Hemanth Sarabu:** Mhm.

**Sachin Pandey:** it was not much like model was not able to identify
anything like there was some lines for surface switch.

### 00:15:36

**Sachin Pandey:** This is the mask like it can give you better idea
without going inside the disc like there are some like surface switches
which are getting marked most of like these boundaries are

**Hemanth Sarabu:** Uh

**Sachin Pandey:** mistakes which don\'t actually have anything in it.
So let\'s suppose we have this example

**Hemanth Sarabu:** uh.

**Geoff Horowitz:** Sachin, I don\'t understand what I\'m seeing right
now.

**Hemanth Sarabu:** We just see

**Geoff Horowitz:** Can you decent mask?

**Sachin Pandey:** these are the mask which model predicted on the dam.
So like from the shape you can see like these are mainly for uh

**Geoff Horowitz:** Okay.

**Sachin Pandey:** lines like I\'m opening the them for this mask. It
was for this

**Geoff Horowitz:** What is Just center me here. What\'s the dark gray?
What\'s the red?

**Sachin Pandey:** uh red is the part that model marked dark gray.

**Geoff Horowitz:** That is the part

**Sachin Pandey:** I\'m also not sure what what about dark this is
different

**Hemanth Sarabu:** Oh,

**Geoff Horowitz:** that

**Hemanth Sarabu:** what is going on with

**Sachin Pandey:** than the like we use

### 00:16:56

**Hemanth Sarabu:** Wait, what? What is this then?

**Pratyaksh Singh:** So it basically interpolates it uh you know for
window size it

**Hemanth Sarabu:** What the?

**Pratyaksh Singh:** interpolates

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** that

**Hemanth Sarabu:** So, it\'s very sparse and so there\'s a lot of like
stitching going on. Okay.

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** And what what are we looking at? Is that is that a
um it feels like there is a mistake in the dem generated itself. No.
Maybe.

**Pratyaksh Singh:** Uh it\'s our time.

**Hemanth Sarabu:** Maybe.

**Pratyaksh Singh:** So this kind of artifact comes from them.

**Hemanth Sarabu:** Okay. So, what are we what are we learning from
this? Is that a true positive, false positive?

**Pratyaksh Singh:** for this I don\'t really know but you know uh the
main goal is to look at all the predictions and see where the model is
underperforming and where it is performing good and get you guys first
of all like get you guys four or five tiles which you can show in the
demo where the model performs and

**Hemanth Sarabu:** Sounds good.

### 00:18:21

**Hemanth Sarabu:** Sounds

**Sachin Pandey:** I think this dam is not matching like this is the dam
from the prediction we

**Hemanth Sarabu:** good.

**Pratyaksh Singh:** then

**Sachin Pandey:** give it. It\'s the same file. This is only the
surface. But here it\'s very

**Pratyaksh Singh:** I can\'t see your screen

**Sachin Pandey:** bigger.

**Pratyaksh Singh:** such

**Geoff Horowitz:** Uh,

**Hemanth Sarabu:** Oh, we we see

**Geoff Horowitz:** I see

**Hemanth Sarabu:** it.

**Geoff Horowitz:** it.

**Pratyaksh Singh:** okay think there is some so what you\'re saying is
that okay so you see those individual things there Right. I run an
interpolation with window size of I think three.

**Sachin Pandey:** Yeah.

**Pratyaksh Singh:** Yeah, window size of three to fill the gaps. And
the things that you see the kind of artifacts those are because you know
it tried to fill the gap and that\'s why it is

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** coming.

**Sachin Pandey:** Like actually this sur doesn\'t even exist.

**Pratyaksh Singh:** It won\'t come. I think you know uh I can take a
look at the tip for which I ran a prediction right but it won\'t
interpolate that far to generate a whole new surface maybe you are
looking at a different t than the one that was used for prediction
because for prediction we are using the tiff from one drive right

### 00:19:42

**Sachin Pandey:** Yeah.

**Pratyaksh Singh:** so I can confirm with the tiff but uh you know it
interpolates a bit for I think three three or four meter to fill the
gaps where there is no

**Sachin Pandey:** Hey.

**Pratyaksh Singh:** data.

**Hemanth Sarabu:** Um, got it. Patak,

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** what what what makes it difficult for us to compute
metrics against the corrections we made for uh surfaces um bricks or
surface bricks um spikes and divots.

**Pratyaksh Singh:** uh I think because most of our mistakes are
actually for surface bricks mostly and for surface bricks you know I
told you previously

**Sachin Pandey:** Are you

**Pratyaksh Singh:** only the uh it won\'t perform well for the surface
bricks because we

**Sachin Pandey:** ready?

**Pratyaksh Singh:** couldn\'t augment it that well right for styles and
divots I don\'t think I don\'t think we do have a lot of we have a lot
of things. The reason being is that mostly the model is good for spikes
and divots and for the other mistake like where you know it classifies
building I think I think we can do we can get numbers for spikes and
divots for some uh for some cases because we remove them with CC right
most of the time most of the time like these isolated mistakes they get
removed by CCA so we can you know uh one rough metrics we can get by
adding those back predicting on you know what was

### 00:21:46

**Pratyaksh Singh:** removed from CCO2 and see if the model performs I
think is where the model is getting most of the

**Hemanth Sarabu:** Hm.

**Pratyaksh Singh:** mistakes when we add those styles where there are
spikes and all I will I will

**Hemanth Sarabu:** Go.

**Pratyaksh Singh:** get you uh I think mostly as we discussed it on
call uh this is mostly for a demo right the first session. So I will try
to first get you like four or five tiles on the on the app which you can
use for the demo and then uh you know try to dig

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** deeper into this into the

**Geoff Horowitz:** projects that you\'re you\'re exactly right.

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** That\'s um good. Uh what\'s the word I\'m thinking
of? Like um it\'s good to kind of stay focused on on whatever our media
goal is, which is that demo. Um so I I Yeah, I think that\'s great. Also
I guess internally we\'re we\'re also I mean this is something that we
want to do right longer term. So I think it\'s also good to be able to
discuss what our future

### 00:22:57

**Pratyaksh Singh:** Mhm.

**Geoff Horowitz:** approaches and options should be.

**Hemanth Sarabu:** But but also I think project is working on a bunch
of things, right?

**Geoff Horowitz:** That\'s true.

**Hemanth Sarabu:** So I get that we don\'t want to like keep going
deeper

**Geoff Horowitz:** Quickly

**Hemanth Sarabu:** into Yeah.

**Pratyaksh Singh:** uh I think one positive thing is that you know the
model detecting spikes and divids is like we can maybe artificially
generate these mistakes right so uh I\'ll try to you know in my in my
free time I will keep this in mind and I\'ll try to see if it is
possible to possible to generate these things because

**Hemanth Sarabu:** I mean I guess this is a little bit related to what
what are you looking at for

**Pratyaksh Singh:** uh

**Hemanth Sarabu:** synthetic? data right now.

**Pratyaksh Singh:** so I am looking at uh uh do you guys want to do you
want me to give you a brief or do you guys want to do it on uh Sunday or
Monday because I think me and Sachin we have it planned of discussing it

**Hemanth Sarabu:** Um,

**Pratyaksh Singh:** on

### 00:24:11

**Hemanth Sarabu:** it\'s just like a one one or two line one or two

**Pratyaksh Singh:** okay so the idea is that uh you know for ground we
usually have a lot of data right so we don\'t actually need to generate
a lot of data for ground because uh in Nova and open tofo there are a
lot of files with just ground classifier Right. So we can just download
them from there and then if we learn how like uh you know so for ground
is my least of my concern and then apart from that it is mostly about
generating other top features which being your buildings and then uh
mostly walls around building where we make mistake steel uh sorry hedges
besides building then you will have wires and towers which are which are
close to vegetation Right. So things like that. So my idea is something
like this where you first create a scene like realistic realistic
looking scene for which you can download things from uh open street map.
So for example you have building footprint, road footprint and uh
bridges there as well as water body.

### 00:25:26

**Hemanth Sarabu:** Mhm.

**Pratyaksh Singh:** You can download those shapes from there and then
having that as a base map you can basically create a whole

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** scene where you have boundaries around around
buildings. You have uh you have trees and all these things around
building.

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** Once you do this I have I have seen that you know
there are some procedural generation method where

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** you can where algorithmically you can generate uh
3D structures. So I found one implementation for trees. There are some
for buildings also. I\'ll see if that works for us.

**Hemanth Sarabu:** Nice.

**Pratyaksh Singh:** Otherwise like this.

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** Mhm. I just want to add one more thing is that you
know the simplest thing that we can do is uh we already have some

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** data right. So for example let\'s say for building
when building is closed by vegetation we make mistake right but

**Hemanth Sarabu:** Yeah.

**Sachin Pandey:** What\'s

**Pratyaksh Singh:** we already have data for building.

### 00:26:14

**Sachin Pandey:** that?

**Pratyaksh Singh:** So what we can do is we can isolate each of those
buildings and then put those on the scene after making some

**Hemanth Sarabu:** Mhm.

**Pratyaksh Singh:** modification to them. Right?

**Geoff Horowitz:** See?

**Pratyaksh Singh:** Same thing we can do for all the classes and then
we can kind of have a pipeline which can generate difficult data set uh
and you know we generate a lot of those difficult data set. So currently
I\'m working on you know figuring those scene out so that the scene rule
scene looks realistic and after that it will be placing object all over
the

**Sachin Pandey:** Awesome.

**Pratyaksh Singh:** scenes.

**Hemanth Sarabu:** Nice. Okay. So, in short, you\'re saying that tell
me if this is correct or or if I\'m missing any important detail.
You\'re you\'re going to get ground from open top and uh you have

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** ways to procedurally generate trees and buildings
and maybe also cut copy paste buildings that we already have good
buildings and then you\'re going to you\'re going to like contaminate it
from

**Pratyaksh Singh:** Yeah.

### 00:27:15

**Hemanth Sarabu:** there.

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** Is that

**Pratyaksh Singh:** Like once you create Yeah.

**Hemanth Sarabu:** right?

**Pratyaksh Singh:** So the idea is that instead of creating point cloud
you create a 3D scene. So you create mesh kind of like you create a 3D
object, right?

**Hemanth Sarabu:** I

**Pratyaksh Singh:** And then there are tools like ASM which you can use
in Nvidia is to

**Hemanth Sarabu:** see.

**Pratyaksh Singh:** kind of emulate an airplane going above you know an
aircraft with sensor going above above it.

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** So you can generate very realistic examples and I
think once you have the 3D data you can you can get to point clouds
easily

**Hemanth Sarabu:** All right.

**Pratyaksh Singh:** because Yeah.

**Hemanth Sarabu:** Do you Okay.

**Sachin Pandey:** Next.

**Hemanth Sarabu:** You have the machine for XM now, right?

**Pratyaksh Singh:** Yeah. Yeah.

**Hemanth Sarabu:** Okay. Because it needs a

**Pratyaksh Singh:** Yes.

**Hemanth Sarabu:** lot.

**Pratyaksh Singh:** Yes. There are other uh other one I think there\'s
Helios+

**Hemanth Sarabu:** I I don\'t know what that is. Is that a simulator?

### 00:28:07

**Pratyaksh Singh:** which yeah uh it is a simulator. Uh maybe I forgot
names of it. I have it written down. Everything I have written down. So
there are these air simulators which you know which you can use to fly
aircraft, fly drones and all the all these things. So my thought process
was that generate the scene then generate 3D object and then you can get
to data from

**Sachin Pandey:** You\'re good.

**Hemanth Sarabu:** Okay, cool. Sounds good.

**Geoff Horowitz:** like that protect if you need it.

**Pratyaksh Singh:** there.

**Hemanth Sarabu:** Um,

**Geoff Horowitz:** You can also, you know, you can you can take over
Pandora uh Pandora. Um you can take

**Hemanth Sarabu:** but there\'s whole ninja. Yeah, ninja is like free.

**Geoff Horowitz:** over Ninja for this if you need

**Hemanth Sarabu:** with a yeah big

**Pratyaksh Singh:** Mhm. Yeah.

**Geoff Horowitz:** it.

**Pratyaksh Singh:** Yeah. Yeah. Yeah. I will I will. I think you know
the things that I\'m currently working on right now,

**Hemanth Sarabu:** GPU.

### 00:28:59

**Pratyaksh Singh:** they don\'t require a lot of compute because it\'s
a scene generation. But as as I go to next steps,

**Geoff Horowitz:** No.

**Pratyaksh Singh:** I think we have the compute to to you know reach
this goal.

**Hemanth Sarabu:** Okay. Okay. One idea. Uh what idea?

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** H maybe. Okay. Hey, uh, did you ever look into
control nets and Lauras?

**Pratyaksh Singh:** controlled net. I think I just uh read a summary of
it not completely. Let me just turn on the

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** notep.

**Hemanth Sarabu:** Um I don\'t think this will be I mean it might be
more difficult in the point cloud space but I will I\'ll quickly share
this is not really unique to control nets or but um they\'re just ways
to uh control uh generative models. Okay. Um so let me

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** um here\'s one example, right?

**Pratyaksh Singh:** Okay.

**Hemanth Sarabu:** I\'m I\'m thinking of a good example. Okay. So,
let\'s say you have a you must have

### 00:30:14

**Geoff Horowitz:** Project Project,

**Hemanth Sarabu:** come.

**Geoff Horowitz:** you can see him on screen, right?

**Pratyaksh Singh:** Yeah, I can. I

**Geoff Horowitz:** Okay.

**Hemanth Sarabu:** Okay. So, by the way, this is how all the models
today do it.

**Pratyaksh Singh:** can.

**Hemanth Sarabu:** Um anything related to editing. Okay. So you can
basically um um let\'s say you want you have a way to procedurally not
procedure let\'s say you want to put a a picture of a cat. Okay, that\'s
a cat. Uh you want to put a picture of a cat in a scene, right? You want
to put that in the scene. So the one way that people would train this
today is u they would take a data set with a lot of cats in it, right?

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** And then they\'ll probably take a segmentation mask
or a bounding box or even key points of the cat. They will extract it.
This could be bounding box uh segmentation even key points. So key
points could be something like here are the eyes, here are the ears,
here\'s the mouth, right?

### 00:31:21

**Hemanth Sarabu:** And then you put that into a vector. Uh we\'ll call
that pose, right? Post vector. And then of course you can also have like
a description description like it\'s a black cat with uh I don\'t know
green eyes, whatever. And what they do is um you know this is kind of
your background image background or context. this is your background
image and this is your object that you want to put in in the image. So
what they end up doing is they will give a they\'ll train a generative
model that whose responsibility is to uh given this given this
background without anything here right nothing is there here you just
put the you just put a the bounding box here this or segmentation and
pole or something like that some combination of this and you say that
you\'re supposed to predict this guy you\'re supposed to this guy so it
learns this process so what does that look like Actually, it\'ll be this
uh this image with the background and then it you don\'t actually show
it um the cat and then you say and it is conditioned on uh these are
called control variables.

### 00:32:34

**Hemanth Sarabu:** Okay, your control control variables or condition
variables and then you\'re supposed to generate that that uh cat image.
Okay, does this make sense?

**Pratyaksh Singh:** You basically like you know uh with these pose or
with the with the key point and everything you basically give it kind of
a sketch of what to create right and then it

**Hemanth Sarabu:** Correct. It is a way to control it.

**Pratyaksh Singh:** generates with that

**Hemanth Sarabu:** Exactly. Exactly.

**Geoff Horowitz:** Come on. You said you said this was control

**Pratyaksh Singh:** strip.

**Geoff Horowitz:** net.

**Hemanth Sarabu:** Um control net is a way to implement a controllable
uh diffusion or a generative model.

**Geoff Horowitz:** Okay,

**Hemanth Sarabu:** Yeah. But you can apply this idea with you know
whatever architecture you want.

**Geoff Horowitz:** this is Yeah,

**Hemanth Sarabu:** This is a very general idea.

**Geoff Horowitz:** this is the

**Hemanth Sarabu:** Yeah. Okay.

**Geoff Horowitz:** approach.

**Hemanth Sarabu:** So I think this is a powerful approach especially if
you have a lot of data because you know there\'s a huge data sets with
cats in it.

### 00:33:35

**Hemanth Sarabu:** Right. And there are segmentation models bounding
box models. You can use a VLM to get the descriptions.

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** Maybe post is a little difficult. Okay. So maybe
you\'ll label or maybe you won\'t. But if you do this, once you train
this model, you have a way to generate cats in any scenes, right?

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** And this is how like if I go to Gemini and say,
\"Hey, this is a picture of me. Put me in a uh put me in a video or
whatever.\" This is roughly what it\'s doing at a high level. Of course,
they\'re doing much fancier stuff.

**Geoff Horowitz:** Is it is it going through kind of every image in the
in the training set?

**Hemanth Sarabu:** So

**Geoff Horowitz:** This process is is with every image in the training

**Hemanth Sarabu:** yeah, this is during train time,

**Geoff Horowitz:** set.

**Hemanth Sarabu:** right? Train time and lunch time. You\'re doing
something like this.

**Geoff Horowitz:** And so then the loss the loss is generally like a a
pixel wise loss.

### 00:34:27

**Geoff Horowitz:** They\'re looking at each

**Hemanth Sarabu:** be a combination but it\'ll be a combination but you
know like a diffusion model will use

**Geoff Horowitz:** pix. Oh yeah. Yeah.

**Hemanth Sarabu:** um yeah like some some kind of reconstruction loss
so definitely there\'s pixel wise

**Geoff Horowitz:** You said that. Yeah.

**Hemanth Sarabu:** loss does that make

**Geoff Horowitz:** It does.

**Hemanth Sarabu:** sense

**Pratyaksh Singh:** Yeah. Um I will open to control that.

**Geoff Horowitz:** Yes.

**Pratyaksh Singh:** I think a little bit.

**Hemanth Sarabu:** well I\'m not I\'m not saying you should look into
it but I\'m saying this is a powerful idea I don\'t actually know how
you would use it. But the thing is we have all these dems,

**Pratyaksh Singh:** Um

**Hemanth Sarabu:** right? We have all these dems from everywhere. So de
are images. So if we wanted to generate dems in a controllable fashion,
like let\'s say the thing is um let\'s say you have I don\'t know like
let\'s say you have a dam and there\'s a hill in this area, right? In
this area uh maybe we can actually

### 00:35:22

**Geoff Horowitz:** Maybe we can.

**Geoff Horowitz:** Excellent.

**Geoff Horowitz:** Yes.

**Hemanth Sarabu:** Yeah, maybe we can like try to remove that and then
basically get some control on, hey, I want I want you to put a hill
here. I want you to put a building here. I want you to put trees here.

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** Um, but the thing is de actually are not supposed to
have those things, right? Like actual clean dems won\'t have trees or
buildings. Um, so anyway,

**Pratyaksh Singh:** Thank

**Hemanth Sarabu:** that\'s thought. um like I don\'t actually know how
we would use this idea but that\'s an idea for you. There\'s also point
cloud generative models. So you can do this you can do this kind of
stuff with point clouds.

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** that it will be more, you know, maybe it\'s worth
looking into, but you know, that\'s that\'s a

**Pratyaksh Singh:** Yeah, there are some.

**Hemanth Sarabu:** thought.

**Pratyaksh Singh:** So I actually came across some papers which were
using diffusion models to generate 3D to generate these three examples
with within a web with with a lot of like they were using agent
engineering and everything but I think

### 00:36:29

**Hemanth Sarabu:** Nice.

**Pratyaksh Singh:** mostly for 3D it it is like you know they will use
diffusion models to generate a lot of images and then we\'ll use goshian
splatting on it to get to the 3D scene

**Hemanth Sarabu:** Yeah. Yeah. That that\'s actually pretty great to me
that we can do that today.

**Pratyaksh Singh:** What? I didn\'t hear

**Hemanth Sarabu:** Oh, I\'m saying it\'s crazy that we can do that
today.

**Pratyaksh Singh:** you

**Hemanth Sarabu:** You generate a video and then do a gausian splat and
then reconstruct. That\'s crazy. But yeah, that\'s why video is making
Yeah.

**Pratyaksh Singh:** generator.

**Hemanth Sarabu:** Yeah. People are generating videos and then they do
gion splats on those videos and

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** then that\'s crazy.

**Pratyaksh Singh:** Uh oh. Yeah.

**Hemanth Sarabu:** I just think that that is pretty crazy that you can
do that.

**Pratyaksh Singh:** Yes.

**Geoff Horowitz:** protection. Um,

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** we\'re also going to pull Rul into the bedrock
stuff. So, if at any point you need an extra set of hands, uh, I mean,
negotiate with Sid a little bit, but you can pull him into

### 00:37:52

**Pratyaksh Singh:** Correct.

**Hemanth Sarabu:** Suchin is helping supporting this effort. Uh
currently

**Pratyaksh Singh:** Yeah. Uh I mean we discussed it that you know uh we
will so whatever comes up

**Hemanth Sarabu:** Pratak.

**Pratyaksh Singh:** uh like you know we will it will like you know we
will give one or two hours at least every day to this effort and uh I
think uh

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** one more thing uh along with this synthetic data
generation I want to do is like uh collect a lot of data from different
location so that you know that sim to real gap that doesn\'t that is at
least you know as small as possible so that we know you know what

**Hemanth Sarabu:** Right.

**Pratyaksh Singh:** are the different ways that data exist and then so
use open topo to collect like data from each of the sensor from every
location so that we basically know like if we have at least five square
kilometer we at least know that you know there are some uh there are
different ways that the point clouds can

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** appear and we will have to have to have that as
well as I think you know we we

### 00:38:55

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** should also speed up uh the effort of generating uh
getting this real data cleaning cleaning it up with the labels.

**Hemanth Sarabu:** Understood.

**Pratyaksh Singh:** So uh yeah I think we will do it

**Hemanth Sarabu:** We have a lot of data.

**Pratyaksh Singh:** together what are you

**Hemanth Sarabu:** Sorry.

**Pratyaksh Singh:** saying?

**Hemanth Sarabu:** We have a lot of data open source and otherwise. We
have you know like some data from ISC.

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** We have data from Walpert. A lot of data from
Walpart from New Zealand. Uh we have data from Tet.

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** We have data from photo map.

**Pratyaksh Singh:** photo map also. Yeah,

**Hemanth Sarabu:** Right.

**Pratyaksh Singh:** Netherlands has a lot of Netherlands has a lot of
data

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** too.

**Hemanth Sarabu:** So we should have a decent decent amount.

**Pratyaksh Singh:** Yeah. Yeah. So like QCing it uh or at least
selecting those areas which are useful uh I think will be an important
effort along with the synthetic data generation.

**Hemanth Sarabu:** I agree.

### 00:39:59

**Hemanth Sarabu:** Um, one thing I would ask maybe you got your playful
Sachin, you can look into these loras L a/control lands. Uh, I will type
it out here. Control S or um UI. I\'m just going to leave this. Okay,
these are just keywords. Okay. The the concept that we want to maybe
learn a little bit is you see all these uh

**Sachin Pandey:** Okay.

**Hemanth Sarabu:** people generating uh images right on Twitter, on
Instagram, whatever,

**Sachin Pandey:** Yes.

**Hemanth Sarabu:** whatever images and videos they want. So you can
actually train these generative models, these like stable diffusion type
models with not a lot of data,

**Sachin Pandey:** Yep.

**Hemanth Sarabu:** like a few hundred samples. So that\'s why people
are training these cool like very uh artistic images to to do very niche
things. Obviously a lot of women a lot of anime women right um the so it
would be good to get familiar with this.

**Sachin Pandey:** Good.

**Hemanth Sarabu:** So if you have if you could spend a little bit of
time just playing with these there are tools out there that will already
let you do a lot of this very quickly.

### 00:41:27

**Hemanth Sarabu:** um you don\'t have to write any code. You don\'t you
know like there\'s there\'s UIs for it where you upload data sets.
They\'ll tell you how to control. Um so I would I would read up a little
bit and the thing is you don\'t even have to do it on the data we\'re
talking about. There\'s examples data sets that you can play with and
you can train these models and you can use Ninja for it. Does that make
sense?

**Sachin Pandey:** Yeah. Yes.

**Hemanth Sarabu:** Now you might be wondering how does this fit into
everything else that we do. Um it might be useful for bedrock when we
start generating synthetic data could be useful not necessarily the same
tooling but the concepts like understanding what breaks what works what
doesn\'t those concepts we can use even if we don\'t write any code now
we\'ll end up writing code then

**Sachin Pandey:** Yeah, I I will uh make a note of it and explore these

**Hemanth Sarabu:** okay yeah and feel free to use ninja Um you

### 00:42:25

**Sachin Pandey:** things.

**Hemanth Sarabu:** can if you guys are obviously if you\'re doing
multiple things you can split up the GPU. It has make

**Geoff Horowitz:** He did you leave the old GPU in there?

**Sachin Pandey:** Okay.

**Hemanth Sarabu:** no work with both the GPUs.

**Geoff Horowitz:** I

**Hemanth Sarabu:** Yeah. So either I\'ll have to spend some time
figuring out why. And it\'s also it\'s an old GPU like it\'s a 3090 Ti.
It\'s very old. So I just have it lying lying here at home. If I can,
I\'ll put it back. But it will be um I will have to take Ninja down for
that. But I don\'t think we\'re starved on G V RAM.

**Geoff Horowitz:** I I agree with you. Also, Hem, we talked about
getting another another one of the same GPUs if we need it.

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** So,

**Hemanth Sarabu:** Yeah. The price did go up.

**Geoff Horowitz:** Oh, we should have bought two.

**Hemanth Sarabu:** Price went up quite what?

**Geoff Horowitz:** We should have bought two.

### 00:43:36

**Hemanth Sarabu:** No, I can get another if you want. The price went up
in the last few months. It went up a couple

**Geoff Horowitz:** Hello.

**Hemanth Sarabu:** hundred.

**Geoff Horowitz:** Since we bought this, it went up. I mean, including

**Hemanth Sarabu:** Yeah. I don\'t know if it\'s gone up since.

**Geoff Horowitz:** buying.

**Hemanth Sarabu:** They had a bunch of deals back then. Not only was it
a couple hundred dollars cheaper, it was \$200 cheaper if I bought two.
They were doing like a bulk discount. Uh which meant it was like \$200
cheaper per GPU.

**Geoff Horowitz:** Okay.

**Hemanth Sarabu:** Sorry, \$300 cheaper per GPU. Now it\'s not. Now
it\'s um \$300 more expensive on that. So if we want more GPUs, now may
be the time to buy it. Jeff, should we start building data centers? So,
we could do this,

**Geoff Horowitz:** Maybe.

**Hemanth Sarabu:** right? We have uh we have uh the GIS expertise. We
can deal with point clouds. Uh we you have you know sensors, I know
sensors, you know, LAR.

### 00:44:35

**Hemanth Sarabu:** Um we do survey. Bring in your dad for construction.
We build data centers.

**Geoff Horowitz:** We we could do it but but honestly Ham it it might
be even cheaper to build in India than it would be to build here.

**Hemanth Sarabu:** Um it would be cheaper in India but latency will be
a

**Geoff Horowitz:** though.

**Pratyaksh Singh:** Yeah,

**Hemanth Sarabu:** problem.

**Pratyaksh Singh:** there is no regulation in India too.

**Hemanth Sarabu:** Pradesh that is uh I don\'t know like in India there
is there are gundas there are gundas gundas there

**Pratyaksh Singh:** There

**Hemanth Sarabu:** there are gangs

**Geoff Horowitz:** Oh.

**Pratyaksh Singh:** Yeah,

**Hemanth Sarabu:** yeah you

**Pratyaksh Singh:** you can pay them instead of the government.

**Hemanth Sarabu:** you have to pay them and in places like Hyderabad uh
I\'m sure this is everywhere else too apparently someone was telling me
about who manages waste in Hyderabad AD and he was like you can\'t you
just can\'t start a waste management company in Hyderabad because those
guys will f\*\*\* you up.

**Pratyaksh Singh:** Yeah. Yeah, that is true. But you know, they
aren\'t smart enough for data centers,

### 00:45:41

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** right?

**Geoff Horowitz:** yet.

**Hemanth Sarabu:** No, that No, no, no, no. These guys are very No.

**Pratyaksh Singh:** Yes.

**Hemanth Sarabu:** These guys are very sophisticated people. So when I
say sophisticated um they understand,

**Pratyaksh Singh:** Uhhuh.

**Hemanth Sarabu:** okay, the people that are going to get into data
centers are not tech people. They\'re not like us. There\'ll be people
that have a lot of land. They have connections with the government. They
have connections with contractors, water supply, right? These guys are
the same people,

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** you know. Um, this is Adani. Adani is not
technically forward. Look what look what they\'re running,

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** right? Um,

**Geoff Horowitz:** So,

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** so I just I just read and this is off topic,

**Hemanth Sarabu:** anyway.

**Geoff Horowitz:** but whatever. I think you\'ll you guys will all
think of this as interesting.

**Hemanth Sarabu:** Okay.

**Geoff Horowitz:** I there\'s you know there\'s a lot of push back in
the states about um about data centers going up everywhere, right?

### 00:46:29

**Geoff Horowitz:** Including Michigan, right? Everywhere. And I just
read an article where I think I think it was I think it was open AI,

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** but I\'m not positive about that. Uh pointed to
Chinese interference in um in promoting uh conflict specifically around

**Hemanth Sarabu:** Yeah. Yes. Yes.

**Geoff Horowitz:** data centers.

**Hemanth Sarabu:** Yeah. Yeah. Yeah. It\'s hilarious.

**Geoff Horowitz:** Uh I\'m glad you find it funny.

**Hemanth Sarabu:** project. Jeff is very sensitive to um uh anyone
messing

**Geoff Horowitz:** Uh

**Hemanth Sarabu:** with the US. What\'s the word? I\'m looking for the
I guess the US national security, which is which is obviously fair, but

**Geoff Horowitz:** he just thinks it\'s part for the

**Pratyaksh Singh:** Uhhuh.

**Geoff Horowitz:** course.

**Hemanth Sarabu:** I just think it\'s part of the game.

**Pratyaksh Singh:** I think so too.

**Hemanth Sarabu:** How many how many how many nations has the US not

**Pratyaksh Singh:** I think so too.

**Hemanth Sarabu:** toppled?

**Geoff Horowitz:** Uh, I don\'t know the answer to that.

**Hemanth Sarabu:** A handful actually I don\'t I don\'t know but it\'s
definitely more than a handful but it has it

### 00:47:41

**Geoff Horowitz:** Um,

**Hemanth Sarabu:** has affected uh

**Geoff Horowitz:** look,

**Hemanth Sarabu:** control.

**Geoff Horowitz:** I come on. you you guys you guys don\'t think that
this is well I I can\'t say this is a blanket statement but I think you
guys don\'t think that this is very offended when I hear about um um
like like all the all the what\'s the word the um you know you have to
pay to get anything done in India like corruption I get very offended by
that I get very offended for all of my Indian

**Hemanth Sarabu:** Wait, what?

**Geoff Horowitz:** brethren uh that there\'s So much corruption in
Indian government.

**Hemanth Sarabu:** Oh, yeah. It is very bad. Um, isn\'t it?

**Geoff Horowitz:** I know.

**Hemanth Sarabu:** It\'s terrible.

**Geoff Horowitz:** I

**Pratyaksh Singh:** I agree with you.

**Geoff Horowitz:** know.

**Pratyaksh Singh:** I agree with you. But you know uh for people you
know who wants to get things done uh this corruption is maybe good for
them. Right? For example, let\'s

**Geoff Horowitz:** Uh so there\'s actually been there\'s there\'s been
studies a lot of like uh you know economists have done

### 00:48:44

**Pratyaksh Singh:** say

**Geoff Horowitz:** studies that basically show that that yes for you
know for for the individual purchaser right the the individual who\'s
who\'s like giving this bribe to get their thing done

**Pratyaksh Singh:** Mhm.

**Geoff Horowitz:** it\'s better but glo like from a global perspective
it\'s bad for for for um citizens,

**Hemanth Sarabu:** They call me.

**Geoff Horowitz:** it\'s bad for, you know,

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** consumers. You get worse products, right? Because
they\'re not choosing based on I I I\'m just giving an example of like a
a purchase order, right? They\'re not choosing based on what\'s the best
product or the lowest cost. They\'re choosing based on who gave them the
biggest bribe.

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** Yeah,

**Geoff Horowitz:** So

**Pratyaksh Singh:** that is true.

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** I I agree with you.

**Geoff Horowitz:** um

**Pratyaksh Singh:** But I think like you know India has bigger problems
than corruption.

**Hemanth Sarabu:** Really?

**Geoff Horowitz:** is bigger problems than

**Pratyaksh Singh:** Yeah.

**Geoff Horowitz:** corruption.

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** I want which one is it? What is a bigger problem?

### 00:49:42

**Pratyaksh Singh:** Huh.

**Hemanth Sarabu:** corruption in

**Geoff Horowitz:** What is it?

**Hemanth Sarabu:** India.

**Pratyaksh Singh:** What is bigger problem than corruption? I need
discrimination as well,

**Hemanth Sarabu:** this like uh I yeah

**Pratyaksh Singh:** right?

**Hemanth Sarabu:** um I feel like corruption it\'s all

**Pratyaksh Singh:** Uh

**Hemanth Sarabu:** the all the issues that you would you would you
would mention I think it affects

**Geoff Horowitz:** I I I was just going to say I bet you corruption I I
can\'t tell you how exactly,

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** everything

**Geoff Horowitz:** but I bet you corruption plays an effect into that,
right? Into reform or into into lots of things.

**Hemanth Sarabu:** yeah but what what form of discrimination Are you
are you referring

**Pratyaksh Singh:** H.

**Geoff Horowitz:** Um,

**Pratyaksh Singh:** So I mean like you know I think you know all of
these are interconnected if you think about it

**Hemanth Sarabu:** to?

**Pratyaksh Singh:** like corruption discrimination discrimination like
you know based on cast religion or even like you know the most of it
like you know based on based on the economic class you are right because
in India I think it it\'s so bad

### 00:50:46

**Hemanth Sarabu:** Yeah.

**Geoff Horowitz:** yeah.

**Pratyaksh Singh:** that the worst thing is that you know in India are
these economic backward people are they they feel like you know they
don\'t deserve things which is which is much more which is much more
worse than anything like you know if you if you do something good for
them still they are like you know they will be like you know I we don\'t
deserve it and all this they they don\'t think they have rights and all
yeah it\'s it\'s it\'s really f\*\*\*\*\*

**Hemanth Sarabu:** Really?

**Pratyaksh Singh:** up like you know how do you think you know these
politicians win these elections and everything it\'s it\'s so
f\*\*\*\*\* up like uh you know they will do one thing and they will be
like you know they don\'t they won\'t think so for example let\'s say uh
if if they build a bridge right or if they build anything right it\'s
like you know it here here in India it feels like you know it\'s the
politicians gift to you that they did some f\*\*\*\*\*\*

**Hemanth Sarabu:** Yeah. Yeah. Yeah. Yeah.

### 00:51:48

**Pratyaksh Singh:** work so and people like you know it\'s it\'s so
mess up like if I will talk to my

**Geoff Horowitz:** Yeah.

**Pratyaksh Singh:** grandfather And so they will be like you know it\'s
it\'s a big thing that they are

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** doing this and this and like then why the f\*\*\*
were they elected to go there like you know we are paying for it but
still that mentality right because a large section of people in India
don\'t pay any taxes right so I don\'t think they understand the meaning
that you know it\'s your money that is basically going into things
because these uh nondirect taxes Right.

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** So for example uh not income taxes but these uh GST
and all these things. I don\'t think people count this as something that
government does because you basically assume that you know it\'s the
large company that is increasing the price right most of the people will
think that

**Hemanth Sarabu:** Mhm.

**Pratyaksh Singh:** and one more worst thing that uh has happened since
Narendra Modi is prime minister is that you know if you if you raise
your voice against it then you know you are either an antiational or a
Muslim or anything so it\'s it\'s like people aren\'t when raising voice
and it\'s like with especially with

### 00:53:00

**Hemanth Sarabu:** So you\'re you\'re anti Modi.

**Pratyaksh Singh:** Huh.

**Hemanth Sarabu:** Are you anti-Modi?

**Geoff Horowitz:** Oh,

**Pratyaksh Singh:** So see,

**Geoff Horowitz:** Hemoth, you found you found good company

**Hemanth Sarabu:** Wait, wait, wait, wait. He didn\'t answer the

**Pratyaksh Singh:** so so yeah.

**Geoff Horowitz:** finally.

**Hemanth Sarabu:** question.

**Pratyaksh Singh:** So I initially, initially I was like very pro modu
and like my family is mostly a BJP

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** supporter. My father holds some position in BJP.
But with these things happening especially with uh especially with like
you know especially

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** with all the contracts that Anani is getting and uh
you know all these all these protest that they don\'t give a f\*\*\*
about uh I\'m like just fed up with this and the worst part is you know

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** uh with Modi it is like kind of a fan culture right
so for example let\'s say MS Dhoni and all right even if they get out on
zero you know people are going to support them.

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** Similarly with Narendra Modi also like if it
doesn\'t do s\*\*\*

### 00:53:53

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** they are going to support them regardless right so
which is I think very f\*\*\*\*\* up thing uh to have with a politician
right you know you should appreciate the work not the

**Geoff Horowitz:** That\'s that\'s that\'s globally that\'s everywhere
you know

**Hemanth Sarabu:** Yeah,

**Geoff Horowitz:** unfortunately. I I totally agree with you project
but that don\'t even

**Hemanth Sarabu:** Jeff is a big Trump fan, by the way.

**Geoff Horowitz:** joke. Don\'t even

**Pratyaksh Singh:** Huh?

**Geoff Horowitz:** joke.

**Hemanth Sarabu:** Jeff is a big Trump fan.

**Pratyaksh Singh:** What?

**Hemanth Sarabu:** Yeah,

**Pratyaksh Singh:** Oh, wow.

**Hemanth Sarabu:** he won\'t tell us.

**Pratyaksh Singh:** Jeff,

**Geoff Horowitz:** Don\'t even joke.

**Pratyaksh Singh:** make America great again.

**Geoff Horowitz:** No. You You think I\'m Na? You know,

**Hemanth Sarabu:** project for context. Na joke saying just for just to
just to piss off Jeff

**Geoff Horowitz:** you would say she joked.

**Pratyaksh Singh:** Huh?

**Hemanth Sarabu:** see what did she

**Geoff Horowitz:** She sounded very serious to me.

**Hemanth Sarabu:** say?

**Geoff Horowitz:** She said she basically said she basically said that
that everybody\'s the same and Trump is just as bad as everybody else,
which is like categorically untrue.

### 00:55:01

**Hemanth Sarabu:** Oh, is that what she

**Geoff Horowitz:** Yeah.

**Pratyaksh Singh:** Oh yeah,

**Hemanth Sarabu:** said?

**Pratyaksh Singh:** that is the thing that people say about Modi too
like you know if I if I ask him if you know if I\'ll ask them that you
know uh if I\'ll show them that you know these are things that Modi does
wrong then the answer is like you know if if not Modi then who else and
if you say Rahul Gandhi they will just laugh

**Geoff Horowitz:** Uh,

**Pratyaksh Singh:** right it\'s Uh

**Hemanth Sarabu:** But I think there\'s something to be said about uh
look,

**Pratyaksh Singh:** if

**Geoff Horowitz:** truck.

**Hemanth Sarabu:** I I get how Modi got to power. Um, I get how he got
to power and I think he\'s not leaving power until until

**Pratyaksh Singh:** Uhhuh.

**Hemanth Sarabu:** Congress has a a a um what\'s the word I\'m looking
for? Um, what\'s the word I\'m looking for? I don\'t know. Basically, a
really strong opponent, right? Uh, Modi, what\'s the word I\'m looking
for? Um,

**Geoff Horowitz:** Uh, dictator.

### 00:55:59

**Hemanth Sarabu:** not a dictator. He\'s he\'s also a dictator,

**Geoff Horowitz:** I\'m kidding.

**Pratyaksh Singh:** He is very so to be honest he\'s very

**Hemanth Sarabu:** but what\'s the word?

**Pratyaksh Singh:** charismatic.

**Hemanth Sarabu:** He\'s he\'s charismatic.

**Pratyaksh Singh:** He is

**Geoff Horowitz:** you you know you know you know what project I was
actually in India when

**Hemanth Sarabu:** Yes.

**Geoff Horowitz:** Modi first came to national power um and and and I
actually I he hates me for this I actually really liked him at the time
because of exactly that you know he ran

**Pratyaksh Singh:** What?

**Geoff Horowitz:** he ran on this platform of uh of anti-corruption
right I mean obviously

**Pratyaksh Singh:** Mhm. Yeah.

**Geoff Horowitz:** I haven\'t stayed in touch since So,

**Hemanth Sarabu:** The word I\'m looking for is formidable. Modi is
formidable and uh and the left does not have a formidable

**Geoff Horowitz:** uh,

**Pratyaksh Singh:** Yeah. And like

**Hemanth Sarabu:** leader which is true even in the states. Well, what
do you have?

**Pratyaksh Singh:** and

**Hemanth Sarabu:** What do you get?

**Geoff Horowitz:** yeah,

**Hemanth Sarabu:** You have you have the left lukewarm about uh the
people in middle are lukewarm.

### 00:56:50

**Pratyaksh Singh:** life.

**Hemanth Sarabu:** Um, and the and the the the guys on the right have a
potentially formidable formidably possibly formidable person and also
charismatic. It\'s going to swing right and then what\'s happening? I
don\'t know. Modi is going to be dictator for life now. Um, I don\'t
think he\'s even let the left cultivate a formidable

**Pratyaksh Singh:** Monis.

**Hemanth Sarabu:** leader.

**Pratyaksh Singh:** Yeah. Yeah. It\'s it\'s it\'s like it\'s so bad
that you know what happens in Indian politics is that uh they will just
uh have an CBI probe on the opposition leaders until they join their
party. So they are like just systematically killing the opposition like
every every big every opposition party they will do the same thing like
for Bengal just to remove ma banana

**Hemanth Sarabu:** No.

**Pratyaksh Singh:** they did s where they removed a lot of ws right

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** and like these guys they are like very smart I mean
BJP guys are like very smarter and huh

**Hemanth Sarabu:** You know the only hope for India is the south only
hope for India

### 00:57:58

**Pratyaksh Singh:** Huh?

**Hemanth Sarabu:** is the south.

**Pratyaksh Singh:** Only hope for India is it is the south.

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** I I mean I mean I I promise you like in in the next
three elections I think BJP will be there too in the next April

**Hemanth Sarabu:** Well, it is a stronghold. That\'s what I mean. It is
a stronghold,

**Pratyaksh Singh:** election.

**Hemanth Sarabu:** right? It is a it is a nonBJP stronghold right now.

**Pratyaksh Singh:** Yeah. Yeah.

**Hemanth Sarabu:** Um,

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** as if we get if the South kind of keeps it. Yeah.

**Geoff Horowitz:** He you would be a

**Hemanth Sarabu:** Look, while I\'m thinking through this,

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** I\'m thinking I\'m thinking like in my head,

**Geoff Horowitz:** southerner.

**Hemanth Sarabu:** I\'m thinking maybe the South has to keep that
stronghold as an anti-NOR thing, right? Like whatever whatever goes, you
know, whatever goes BJP out. Um, that\'s I guess that\'s polit

**Pratyaksh Singh:** Mhm.

**Geoff Horowitz:** How about how about Indian India is a young
democracy.

**Hemanth Sarabu:** Yeah.

### 00:58:52

**Geoff Horowitz:** Let me tell you a little bit a little bit something
from from American history about about about

**Hemanth Sarabu:** Oh,

**Geoff Horowitz:** the south competing against the north. Uh,

**Hemanth Sarabu:** is that it? Just Just don\'t don\'t mess with the
north.

**Geoff Horowitz:** you\'re you\'re gonna have you\'re gonna have civil
war. I\'m kidding.

**Pratyaksh Singh:** I I don\'t think Jeff we are going to have civil
war because you know most of the north Indians work for south

**Hemanth Sarabu:** Um,

**Geoff Horowitz:** I\'m kidding. I\'m kidding.

**Pratyaksh Singh:** Indians. So,

**Geoff Horowitz:** Oh boy. All right, guys.

**Hemanth Sarabu:** so Sachin where do you uh what is your position and
all this.

**Geoff Horowitz:** I I don\'t have

**Hemanth Sarabu:** Imagine a sentence like I\'m a movie fan.

**Sachin Pandey:** No,

**Geoff Horowitz:** to

**Sachin Pandey:** I agree with

**Pratyaksh Singh:** so to to be honest,

**Sachin Pandey:** Patics.

**Pratyaksh Singh:** okay,

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** I I\'ll tell you one thing that u I am anti Modi
Modi but all the elections that I\'ve gone to I have voted BJP and I I
I\'ll tell

### 00:59:58

**Hemanth Sarabu:** f\*\*\*

**Sachin Pandey:** It

**Pratyaksh Singh:** you the reason I\'ll tell you the reason. So they
do BJP does cost politics and I don\'t know whatever what the f\*\*\*

**Hemanth Sarabu:** yeah.

**Sachin Pandey:** seems

**Pratyaksh Singh:** is wrong with uh Rahul Gandhi or Congress they will
do the same thing like uh you know BJP will support Hindus they will
support Muslims and then they will so you you will think of giving them
vote and then they will come in and in one of the rally they will say
that you know we are going to increase the reservation from 50% to 60 or
70%. And it\'s like, brother, why are you just why are you killing your
own votes, right? So that\'s why like, you know,

**Hemanth Sarabu:** I mean,

**Pratyaksh Singh:** that\'s why I don\'t vote for

**Hemanth Sarabu:** he\'s uh he\'s he\'s I mean,

**Pratyaksh Singh:** Congress.

**Hemanth Sarabu:** he\'s probably he\'s doing that because he thinks
he\'s going to get more votes from whoever he\'s reserving the the you
know, he\'s making the reservations for.

**Pratyaksh Singh:** Yeah. But it has been like 14 years, right?

### 01:00:53

**Pratyaksh Singh:** 14 15 years now. And they aren\'t winning anywhere.
So why not change your strategy,

**Hemanth Sarabu:** True. It\'s true. That\'s true.

**Pratyaksh Singh:** right?

**Hemanth Sarabu:** That\'s true.

**Sachin Pandey:** By the way, BJPing pulling leaders from all other
party other than

**Hemanth Sarabu:** Mhm.

**Sachin Pandey:** Congress.

**Pratyaksh Singh:** Congress don\'t have any leaders to they have like
what all over India I don\'t think they have any any leaders.

**Hemanth Sarabu:** Yeah, you guys have watched these uh Adita movies.

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** Um the man those that guy loves

**Pratyaksh Singh:** Yeah. Yeah.

**Hemanth Sarabu:** Modi.

**Sachin Pandey:** Yeah.

**Hemanth Sarabu:** He hates Congress. You can tell.

**Pratyaksh Singh:** Uh

**Hemanth Sarabu:** You can tell in every movie that he he\'ll drop a
few like

**Pratyaksh Singh:** yeah.

**Hemanth Sarabu:** hints.

**Pratyaksh Singh:** Uh-huh. Yeah.

**Hemanth Sarabu:** every movie. I

**Pratyaksh Singh:** I feel like BJP is BJP is paying him to make those
movie.

**Hemanth Sarabu:** like

**Pratyaksh Singh:** It feels like you know he\'s being getting
sponsored from BJP because it\'s it\'s like you know it it\'s kind of
propaganda but if you remove that I think you know if you remove the
propaganda part I think I think he\'s a great director though right you
know his movies and all

### 01:02:07

**Hemanth Sarabu:** I agree. I agree.

**Pratyaksh Singh:** storytelling

**Hemanth Sarabu:** I agree. But the problem is that he will he will do
that. I Yeah,

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** we recently watched article um 15 16 the Kashmir
one. In that one they were blaming Congress for the special status which
which I which is true.

**Pratyaksh Singh:** Uh-huh.

**Hemanth Sarabu:** Nu did that but they bring it up so many times.
It\'s like it\'s you know they bring it up so many times and it\'s
clearly it\'s clearly a proBJP. let\'s whitewash the the whole Kashmir
operation kind of thing.

**Pratyaksh Singh:** Um. Yeah.

**Hemanth Sarabu:** They they don\'t go over any of the other stuff like
they shut down the the network.

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** That was all chaos all around the world actually.
People were like what is going on in Kashmir? Um and then same thing
with um uh the new what is

**Pratyaksh Singh:** Mhm.

**Hemanth Sarabu:** their durand the first movie he said you

**Pratyaksh Singh:** Do

**Hemanth Sarabu:** know the guy says the b guy he says oh let\'s keep
you know he said everything is happening in Bihar or something like that
and then he\'s like uh oh let\'s store all this all this information so
that when a future government that cares about the nation comes up you
know I was like what

### 01:03:20

**Hemanth Sarabu:** why did he say And then I I I Googled it and I
realized that it was Congress in power back then and

**Pratyaksh Singh:** Uh uh

**Hemanth Sarabu:** he was basically Congress doesn\'t care and uh he\'s
basically saying oh let\'s wait for

**Pratyaksh Singh:** yeah

**Hemanth Sarabu:** Modi and I thought my god yeah

**Pratyaksh Singh:** it is. So if you so I think tell move it is fine
but but right now even

**Hemanth Sarabu:** that\'s

**Pratyaksh Singh:** if you open the news you will see something similar
right

**Hemanth Sarabu:** uh people people like s\*\*\*\*\*\*\*

**Pratyaksh Singh:** so yeah like BJP is on

**Hemanth Sarabu:** on Congress

**Pratyaksh Singh:** power and then they will talk about that Javal Neu
didn\'t do this like what the f\*\*\*

**Hemanth Sarabu:** for

**Pratyaksh Singh:** you know it\'s they will talk about Jawahal Neu
didn\'t do this you know was Gandhi important for indep independence and
and you know how good the Modi government is.

**Hemanth Sarabu:** heat.

**Pratyaksh Singh:** They they have bought like BJP through Adani they
have bought all these uh all these news channels right most of the news
channels they are they have been bought by Adani yeah like

### 01:04:22

**Hemanth Sarabu:** Oh, really? I don\'t know. No

**Pratyaksh Singh:** most of these news channels they have been bought
by Adan so it\'s it\'s pure

**Hemanth Sarabu:** idea.

**Pratyaksh Singh:** propaganda only like you know these people on
YouTube and Instagram uh you know they they do these things and and
it\'s hard for them hard for BJP to control it because it\'s
decentralized but uh but you know

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** one one smart thing that they did was uh uh they
they raised to meta that you know there are some pe some things that are
international and stuff that you know which hurt the

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** sovereignity of our country so we will raise the
request we will raise you know request for videos and

**Hemanth Sarabu:** Oh.

**Pratyaksh Singh:** all these things and then you have to reply reply
it in 3 hours and we reduced it to 1 hour

**Hemanth Sarabu:** Oh,

**Pratyaksh Singh:** now so what happens is that for any video If uh if
you know

**Hemanth Sarabu:** they

**Pratyaksh Singh:** if uh so it\'s like you know if there is uh if
there is a problem for any

### 01:05:15

**Hemanth Sarabu:** don\'t

**Pratyaksh Singh:** request uh meta just you know removes that video
without without even checking it just to avoid these code cases and all.

**Hemanth Sarabu:** down.

**Pratyaksh Singh:** So you know they\'re trying to they\'re trying to
remove this thing also. Uh they already have I think they already did it
for WhatsApp that they will basically check all your messages and all.
So it\'s f\*\*\*\*\*

**Hemanth Sarabu:** Really?

**Pratyaksh Singh:** up. Yeah. Yeah it is. It is uh they were just saw
that you know we we want to do it for taxes.

**Hemanth Sarabu:** I didn\'t know that.

**Pratyaksh Singh:** Huh?

**Hemanth Sarabu:** VPN is gone.

**Pratyaksh Singh:** No VPN isn\'t gone.

**Hemanth Sarabu:** VPN. Oh,

**Pratyaksh Singh:** You can use VPN. I think you can use VPN.

**Hemanth Sarabu:** really?

**Pratyaksh Singh:** It\'s like you know the government can read your
messages. It\'s something like this. Uh I mean they can request your
message or something like this. uh and the way that they pass uh from
any of your social

**Hemanth Sarabu:** from.

### 01:06:10

**Pratyaksh Singh:** media.

**Hemanth Sarabu:** Oh s\*\*\*.

**Pratyaksh Singh:** Yeah,

**Hemanth Sarabu:** Okay.

**Pratyaksh Singh:** I think especially it was for WhatsApp and the way
that they passed this bill was very smart like you know they p they
passed it with a bill which mentioned that you know we will give around
40% of representation to women\'s in parliament right and with that bill
they put this also the privacy bill that you know we will use uh your
WhatsApp messages chats and all these things for income tax and for
surveillance basically. So Congress blocked it and then Congress got a
backlash all over the India because they blocked the bill which
mentioned 40% reservation for women.

**Hemanth Sarabu:** That\'s so dumb. Honestly, that is so dumb.

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** Damn. Okay,

**Pratyaksh Singh:** Yeah.

**Hemanth Sarabu:** I got to drop to Yeah. Tell me.

**Pratyaksh Singh:** I mean yeah so you know you were saying that you
know

**Hemanth Sarabu:** Tell me. Tell me.

**Pratyaksh Singh:** I don\'t think Mi is going anywhere until she dies.
I will be like I will be surprised if after Modi PJP goes

### 01:07:15

**Hemanth Sarabu:** Yeah.

**Pratyaksh Singh:** out of power even after Modi.

**Hemanth Sarabu:** Yeah. I I I I believe that.

**Pratyaksh Singh:** So

**Hemanth Sarabu:** I believe that.

**Pratyaksh Singh:** yeah he\'s I

**Sachin Pandey:** I think Yogi can replace Moody.

**Hemanth Sarabu:** Who?

**Pratyaksh Singh:** think he\'s currently kind of better than Modi.

**Hemanth Sarabu:** Who?

**Pratyaksh Singh:** Uh chief minister of Uttar Pradesh Yogi Aditinat.

**Sachin Pandey:** Yogi.

**Pratyaksh Singh:** He\'s dumb. He\'s stupid but you know but he\'s
he\'s honest at least like you know he won\'t he won\'t bend to

**Hemanth Sarabu:** Oh, this guy. Oh,

**Pratyaksh Singh:** the will uh yeah yeah

**Hemanth Sarabu:** isn\'t he he\'s weird, right? He\'s a weirdo.

**Pratyaksh Singh:** yeah so see uh

**Hemanth Sarabu:** Okay, you guys are joking.

**Pratyaksh Singh:** I mean all of the BJP members are weirdo only but
this guy is at least honest like you know the corruption thing he
doesn\'t tolerate that right but he is he

**Hemanth Sarabu:** Oh, okay.

**Pratyaksh Singh:** he\'s dictated He\'s as close to a dictator as you
get, right? But it doesn\'t tolerate corruption.

**Hemanth Sarabu:** I\'d be very concerned for the monk.

### 01:08:20

**Pratyaksh Singh:** Oh yeah. Yeah.

**Hemanth Sarabu:** Very

**Pratyaksh Singh:** I I don\'t think I don\'t think he\'s Yeah.

**Hemanth Sarabu:** concerned.

**Pratyaksh Singh:** I don\'t think he\'s is he\'s is going to become a
PM. Uh even in BJP there is a lot of politics. They\'re trying to push
him out because he\'s getting too powerful.

**Hemanth Sarabu:** Oh okay. You guys uh you know even like five six
years ago when Rahul Gandhi is uh over 40 years old he used to do like
oh young young leadership stuff. Do you guys know that joke? But when I
was a kid, he was actually young, you know, he was like 20, 30. And even
now,

**Pratyaksh Singh:** Uh

**Hemanth Sarabu:** he does like young leadership stuff. And people are
like, \"This guy\'s not young anymore.\" Yeah.

**Pratyaksh Singh:** uh.

**Hemanth Sarabu:** Okay. I I I do get it. But this was um uh

**Pratyaksh Singh:** Okay.

**Hemanth Sarabu:** Yeah. You guys uh what what do you guys uh actually
I\'ll ask next time. We\'ll I\'ll ask next next time. Not important.
Okay. Shut up.

**Pratyaksh Singh:** or Oh,

**Hemanth Sarabu:** Good casting of credits. Bye-bye.

**Pratyaksh Singh:** bye.

**Sachin Pandey:** that may WhatsApp spikes. Watch your

**Pratyaksh Singh:** data/ app/ example files

**Sachin Pandey:** spike

**Pratyaksh Singh:** Spike

**Sachin Pandey:** dismissive spike.

**Pratyaksh Singh:** model.

**Sachin Pandey:** mainly to spikes,

**Pratyaksh Singh:** Ah,

**Sachin Pandey:** but

**Pratyaksh Singh:** spikeid

**Sachin Pandey:** taking.

**Pratyaksh Singh:** dat. Tless apps as example files.

**Sachin Pandey:** Okay.

**Pratyaksh Singh:** Okay.

**Sachin Pandey:** Okay.

### Transcription ended after 01:11:25

*This editable transcript was computer generated and might contain
errors. People can also change the text after it was created.*
