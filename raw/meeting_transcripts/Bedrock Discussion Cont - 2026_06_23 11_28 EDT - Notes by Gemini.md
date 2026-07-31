Jun 23, 2026

## Bedrock Discussion Cont

Invited [[Sachin Pandey]{.underline}](mailto:sachin@crescer.ai)
[[Pratyaksh Singh]{.underline}](mailto:pratyaksh@crescer.ai) [[Ratul
Shashank]{.underline}](mailto:ratul@crescer.ai) [[Hemanth
Sarabu]{.underline}](mailto:hemanth@crescer.ai) [[Geoff
Horowitz]{.underline}](mailto:geoff@crescer.ai)

Attachments [[Bedrock Discussion
Cont]{.underline}](https://calendar.google.com/calendar/event?eid=Nm43YzFqMnJmbHAyYXAyazZiY2VtOWx1N2ogZ2VvZmZAY3Jlc2Nlci5haQ)
[[s7k
conversion]{.underline}](https://drive.google.com/drive/folders/1M0YUQjPGEfWsEAFYi7gJS0XfIr5eJOzV)

### Summary

The team reviewed technical data requirements and pipeline artifacts
while debating annotation strategies and setting higher research
standards.\
\
**Improving Data Pipeline Processes**\
Investigations into pipeline artifacts and resolution settings revealed
inconsistencies in data representation. The team identified that
external sensor data is currently missing from the extraction process.\
\
**Refining Annotation and Training**\
Discrepancies in port data and background images highlighted a need for
synthetic data generation. The inclusion of magnetic data was deemed
necessary for effective object identification.\
\
**Establishing Research Standards**\
The team formally adopted a mandate to replace informal technical
approaches with rigorous, theory-based documentation and citation
practices.

### Decisions

Aligned

-   **Root cause analysis strategy** The team will prioritize
    > identifying whether data gaps are caused by existing data or the
    > pipeline tool before applying remediation or filtering techniques.

-   **Training set exclusion strategy** The team will exclude specific
    > out-of-distribution background images, such as square or
    > semicircular patterns, from model predictions to prevent false
    > positives.

-   **Synthetic data generation strategy** The team will generate
    > synthetic contact data on new background sets and present them to
    > the client to validate the feasibility of including these datasets
    > for training.

-   **MAG data required for mine identification** The team aligned that
    > mine identification features not visible without MAG data are out
    > of scope for the current milestone, and that using MAG data is
    > necessary to achieve reasonable results.

We\'ve **updated the Decisions section** using your feedback.

Let us know what you think:
[[Helpful]{.underline}](https://google.qualtrics.com/jfe/form/SV_5p6FWBVWvynleNU?isGoogler=no&isHelpful=yes)
or [[Not
Helpful]{.underline}](https://google.qualtrics.com/jfe/form/SV_5p6FWBVWvynleNU?isGoogler=no&isHelpful=no)

### Next steps

-   \[Ratul Shashank\] Collate S7K Requirements: Collate all necessary
    > data requirements for the S7K pipeline into a document.
    > Distinguish between data extracted from the S7K files and
    > information needed from external sources.

    > \[Geoff Horowitz\] Query IIC Data: Ask Jose whether the IIC
    > organization possesses the necessary S7K pipeline data internally.

    > \[Ratul Shashank\] Update PowerPoint: Add images demonstrating the
    > swath bands and potential data gaps to a separate slide in the
    > reference document.

    > \[Ratul Shashank\] Research Tool: Investigate how the Open Sight
    > Scan tool converts XTF files to images and determine if it uses
    > any data imputation techniques.

    > \[Ratul Shashank\] Create Research Report: Develop a detailed
    > report covering research findings on Open Sight Scan. Include
    > specific details on how pixel resolution is calculated.

    > \[Pratyaksh Singh\] Provide Report Guide: Share a guide with the
    > team on how to structure the detailed report and what specific
    > information to include.

    > \[Geoff Horowitz\] Update Bedrock: Inform Bedrock that specific
    > types of unusual background images will be excluded from training
    > data.

    > \[Geoff Horowitz\] Discuss Detections: Confer with Bridget
    > regarding the approach for handling detections on unusual
    > background images during production.

    > \[Geoff Horowitz\] Consult Bridget: Consult with Bridget regarding
    > the missing or required role data for the current project.

    > \[Geoff\] Contact Bridget: Confirm the generation process for the
    > reported dots and inquire about obtaining the underlying data from
    > Bridget.

    > \[Ratul\] Analyze MAG Data: Examine the magnetic data for visual
    > insights and potential overlaps with project features. Conduct an
    > analysis to determine if this data can assist in identifying
    > contacts.

    > \[The group\] Schedule Bridget Meeting: Coordinate a meeting time
    > with Bridget to perform a comprehensive overview of the magnetic
    > data.

    > \[Sachin\] Align Lat Long: Test the alignment of contacts using
    > latitude and longitude coordinates with the XTF files. Provide a
    > status update regarding this alignment process within a few hours.

    > \[Ratul\] Upload Report: Upload the completed report regarding the
    > XTF data analysis to the drive for team accessibility.

    > \[Ratul\] Review Mine Detection: Review findings related to
    > magnetic data mine identification during the scheduled follow up
    > meeting.

    > \[Pratyaksh\] Report Discussion Outcome: Send a message to Geoff
    > summarizing the outcome of the discussion regarding project tasks.

### Details

-   **S7K Pipeline Data Requirements**: Ratul Shashank explains that
    > accurate conversion from S7K format requires external data,
    > including tide information, lever arm data (sensor location), and
    > water density, which are not currently C-data centric. The current
    > manual process for gathering tide data is inefficient and slow.
    > Geoff Horowitz notes that the client, IIC, may not have this
    > information, as it is likely embedded in their CARIS software, and
    > suggests that Ratul compile a document detailing the specific data
    > needed versus what is currently extractable. Ratul will compile
    > this information for review, and Geoff will reach out to Jose to
    > inquire about the data availability.

-   **Access to Project Documentation**: Ratul Shashank reports
    > difficulty accessing Google Docs and Drive using their company
    > email, preventing them from sharing documents during the meeting.
    > Geoff Horowitz clarifies that they will assist in troubleshooting
    > the access issues to ensure Ratul can manage file sharing and
    > uploads for the project.

-   **Investigation of Data Gaps**: The team discusses \"gaps\" observed
    > in the data and whether these are artifacts of the pipeline or
    > actual data voids. Sachin Pandey and Ratul are utilizing Open
    > Sight Scan to visualize these gaps and compare ping data,
    > specifically examining pitch and roll variables. Pratyaksh Singh
    > emphasizes that the immediate goal is to verify if the data
    > actually exists at those points before attempting to implement
    > filtering remedies, such as time-varied gain or automatic gain
    > control.

-   **Open Sight Scan Implementation**: To understand the data gaps, the
    > team plans to investigate how the Open Sight Scan tool loads XTF
    > files and renders them as images. Ratul will specifically analyze
    > the code to determine if the tool uses imputation techniques to
    > fill gaps or if the gaps are inherent to the data. Sachin will
    > also attempt to cross-check ping gaps by drawing annotations at
    > specific indices to verify the findings against the visual output.

-   **Resolution and Image Quality Analysis**: Sachin Pandey reports
    > that after using an updated script, the \"underscore 1\"
    > (high-resolution) images show fewer details, such as lower
    > standard deviations and unique altitudes, compared to the original
    > images. Pratyaksh Singh requests a detailed report explaining the
    > impact of specific resolution settings---such as 2 cm per
    > pixel---on the resulting image size, noting that increasing pixel
    > size should technically reduce image dimensions, which is not
    > currently observed. Ratul will compile this report to clarify the
    > relationship between resolution settings and data representation.

-   **Background Training Exclusion**: The team discusses excluding
    > specific, irregularly shaped (square or semicircular) background
    > images from the training set, as these are viewed as
    > out-of-distribution compared to standard two-strip data. Geoff
    > Horowitz will inform Bedrock that they intend to exclude these,
    > though Pratyaksh suggests they might experiment with including
    > them to see if it improves performance. Geoff confirms that if
    > these images appear in production, they can be treated as negative
    > examples or potentially ignored.

-   **Port Data Annotation Concerns**: Pratyaksh Singh expresses concern
    > that the provided port (POA) data lacks contact annotations, which
    > may cause the model to learn to associate that background type
    > with \"no prediction\". Geoff Horowitz acknowledges this and
    > suggests they may need to generate synthetic data or discuss the
    > matter further with Bedrock. Geoff plans to propose to Bedrock
    > that they use synthetic data to show what contacts would look like
    > on that background, allowing the client to decide on the training
    > approach.

-   **Magnetic (MAG) Data Investigation**: The team discusses the use of
    > MAG data for identifying ferris objects, with Ratul noting that
    > MAG data is particularly useful for identifying dipole patterns.
    > While Bridget is scheduled to provide a full overview of the MAG
    > data later, the team intends to conduct an independent
    > investigation in the interim to see if they can identify obvious
    > overlaps or insights on their own.

-   **ENT Target Location Issues**: Regarding ENT target locations,
    > Sachin reports that the provided data does not contain names or
    > relationships to existing IDs. To resolve this, Sachin proposes
    > using latitudinal and longitudinal coordinates to plot XTF
    > boundaries and drop annotation points to determine the correct
    > associations.

-   **XTF and Magnetic Data Alignment**: Geoff Horowitz requests that
    > Sachin Pandey align contacts derived from latitude and longitude
    > data with XTF files that contain geo-referenced magnetic data.
    > Sachin Pandey commits to testing the pre-processing script to see
    > how the data is extracted and providing a report on the alignment
    > status within one hour.

-   **DRN Dataset Annotation Issues**: Ratul Shashank reports difficulty
    > uploading a report on DRN dataset annotations to the shared drive
    > due to access restrictions. Ratul Shashank states an intent to
    > share the report in the drive for future reference and offers to
    > present the findings via screen share during the meeting.

-   **Annotation of Mines in Data**: Pratyaksh Singh and Sachin Pandey
    > discuss the difficulty of spotting mines in the annotation
    > session, noting that mines appear very small and are not visible
    > in all files. Pratyaksh Singh questions whether this is within the
    > scope of the current milestone, specifically regarding the usage
    > of XTF data.

-   **Requirement for Magnetic Data in Mine Identification**: Geoff
    > Horowitz, Pratyaksh Singh, and Ratul Shashank debate whether
    > magnetic data is necessary for identifying mines. Geoff Horowitz
    > suggests that if mines are not visible without magnetic data, the
    > team must incorporate it to achieve reasonable results, despite
    > potential difficulties with geographic interference. The team
    > agrees to review this approach further the following day.

-   **Research Methodology and Documentation Standards**: Pratyaksh
    > Singh advises the team on maintaining a professional research
    > standard when working on machine learning and transformation
    > pipelines. Pratyaksh Singh emphasizes the importance of
    > understanding underlying theory, thoroughly documenting processes,
    > grounding research in cited articles, and avoiding the practice of
    > \"hacking things together.\" Ratul Shashank and Sachin Pandey
    > agree to improve their documentation and communication practices
    > to build a stronger case for their research.

-   **Technical Problem Solving and Metrics**: The team discusses
    > specific machine learning problem-solving techniques, including
    > hypothesis testing and the use of distance metrics. Pratyaksh
    > Singh mentions using specific values, such as 0.25, 0.2, 0.05, and
    > 0.18, in their evaluation process to test for accuracy. They agree
    > to continue refining their approach to data management and problem
    > solving.

*You should review Gemini\'s notes to make sure they\'re accurate. [[Get
tips and learn how Gemini takes
notes]{.underline}](https://support.google.com/meet/answer/14754931)*

*How is the quality of **these specific notes?** [[Take a short
survey]{.underline}](https://google.qualtrics.com/jfe/form/SV_9vK3UZEaIQKKE7A?confid=M3SiOuywMuTwY_d9CJXVDxIWOAIIigIgABgBCA&detailid=standard&screenshot=false)
to let us know your feedback, including how helpful the notes were for
your needs.*
