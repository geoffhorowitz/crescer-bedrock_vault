Jul 17, 2026

## Bedrock connect

Invited [[Sachin Pandey]{.underline}](mailto:sachin@crescer.ai) [[Geoff
Horowitz]{.underline}](mailto:geoff@crescer.ai)

Attachments [[Bedrock
connect]{.underline}](https://calendar.google.com/calendar/event?eid=N3M0bTBqdGZrMzVmam83OHN2cHI1MW85OGYgZ2VvZmZAY3Jlc2Nlci5haQ)

### Summary

Documentation review led to model performance analysis and strategy
adjustments for threshold evaluation and object classification.\
\
**Documentation and Data Issues**\
Communication gaps regarding data exclusions were addressed by
emphasizing the need for documented reasoning. Validation and test sets
now incorporate updated data to better reflect target accuracy.\
\
**Performance Metrics Strategy**\
Implementation of a 0.1 Intersection Over Union threshold allows for
better object detection visibility. Baselines will now include both 0.1
and 0.5 Intersection Over Union results for comparison.\
\
**Model Refinement Parameters**\
Binary classification remains the primary focus while excluding specific
annotations like sand ripples to improve accuracy. Labeling adjustments
for small black objects as Unexploded Ordnance are planned.

### Decisions

Needs Further Discussion

-   **UXO naming convention requires discussion** The proposal to label
    > small black artifacts as \'UXO\' in reporting is set for further
    > discussion due to inconsistencies in feature definitions across
    > different datasets.

Aligned

-   **Metrics evaluation strategy established** The team established a
    > strategy to utilize both 0.01 and 0.5 Intersection over Union
    > (IOU) thresholds when evaluating and reporting model performance.

-   **Reporting methodology for classes confirmed** The team confirmed
    > that model results should focus on Bedrock points of interest and
    > exclude specific classes, such as \'sand ripples\' and
    > \'incorrect\' annotations, as their inclusion did not improve
    > performance.

We\'ve **updated the Decisions section** using your feedback.

Let us know what you think:
[[Helpful]{.underline}](https://google.qualtrics.com/jfe/form/SV_5p6FWBVWvynleNU?isGoogler=no&isHelpful=yes)
or [[Not
Helpful]{.underline}](https://google.qualtrics.com/jfe/form/SV_5p6FWBVWvynleNU?isGoogler=no&isHelpful=no)

### Next steps

-   \[Sachin Pandey\] Update IOU Threshold: Add the 01 value into the
    > intersection over union threshold in the results table.

    > \[Sachin Pandey\] Confirm Annotations: Review the labels and
    > confirm or correct the accuracy of the documentation.

    > \[Sachin Pandey\] Reclassify Objects: Move the black structures
    > that look like black patches to the black patch category to
    > improve model classification.

### Details

-   **Missing Data and Documentation**: Geoff Horowitz and Sachin Pandey
    > discuss a communication issue where data was not included in a
    > previous message. Sachin Pandey explains that the data was
    > excluded because it was initially unlabeled, and they intended to
    > use it as a test set. Geoff Horowitz emphasizes that while it is
    > acceptable to exclude data for valid reasons, these decisions must
    > be documented to prevent information loss.

-   **Test Set and HTML Metrics**: Sachin Pandey notes that the
    > validation and test sets now incorporate the new data, though they
    > report that the model is performing poorly, potentially because
    > the data does not accurately represent the target. The pair
    > identifies where these metrics are located in the HTML file, and
    > Geoff Horowitz acknowledges that they should have provided a link.
    > They agree to maintain the current configuration while updating
    > data, labeling, and merging classes to observe performance
    > changes.

-   **IOU Thresholds and Ground Truth Counts**: Geoff Horowitz requests
    > that an 0.1 Intersection Over Union (IOU) threshold be added,
    > which Sachin Pandey confirms is straightforward to implement. They
    > address a discrepancy in the ground truth object count, noting
    > that the original target was 256, but the final count is 253.
    > Geoff Horowitz clarifies that these values were adjusted during
    > the transition between milestone 2 and milestone 3.

-   **Rationale for 0.1 IOU Threshold**: Geoff Horowitz explains the
    > logic behind using a 0.1 IOU threshold, which yielded a metric of
    > 0.866, rounded to 0.87. They argue that even a single pixel of
    > overlap suggests an object is present, which is a useful metric
    > for client interactions as it demonstrates the model\'s ability to
    > identify objects even when the entire structure is not captured.
    > Sachin Pandey agrees that utilizing both 0.1 and 0.5 IOU
    > thresholds is a beneficial internal evaluation method.

-   **Establishing Baseline Results**: Geoff Horowitz and Sachin Pandey
    > discuss the importance of creating baseline results once the model
    > is fully trained. They confirm that the report will include these
    > baselines at a 50% IOU threshold, and they plan to also include
    > results at the 0.1 IOU threshold for comparison.

-   **Model Assumptions and Exclusions**: Sachin Pandey outlines the
    > assumptions for the S1 model, which performed binary
    > classification and excluded specific classes, such as \"sand
    > ripples\" and annotations marked as \"incorrect,\" from the JSON
    > file. Sachin Pandey clarifies that while the images were included
    > in the training, the annotations for these excluded classes were
    > not. The pair discusses the \"incorrect\" label, with Sachin
    > Pandey explaining that these were specific annotations marked as
    > incorrect within the existing JSON file provided by Bedrock.

-   **Class Inclusion and Performance**: Geoff Horowitz and Sachin
    > Pandey confirm that the included classes comprise Bedrock Point of
    > Interest (POI), Faint POI, and Line Artifacts. Sachin Pandey
    > explains that excluding sand ripples and incorrect annotations did
    > not improve false positive results, leading to the decision to
    > retain the current baseline approach.

-   **Binary Classification and Background Features**: Sachin Pandey
    > explains that the model treats all classes as merged during binary
    > classification, focusing on detection rather than specific object
    > classification. Geoff Horowitz observes that the model performed
    > surprisingly well on data it was not explicitly trained on, such
    > as sand patches and black lines, suggesting that the model was
    > likely prioritizing background features.

-   **Training Parameters and Object Identification**: Sachin Pandey
    > confirms that only the learning rate was modified for the
    > training, with all other hyperparameters remaining consistent with
    > the previous model version. The pair discusses how to categorize
    > and report on various objects, including Area of Interest (AOI)
    > support, sand patches, and black patches. Sachin Pandey intends to
    > adjust the classification of black patches and AOI support in the
    > next training cycle to improve model accuracy. Geoff Horowitz
    > suggests labeling \"small black\" objects as Unexploded Ordnance
    > (UXO) in the report to improve clarity, though Sachin Pandey notes
    > that the features defining a UXO can vary across different
    > datasets.

*You should review Gemini\'s notes to make sure they\'re accurate. [[Get
tips and learn how Gemini takes
notes]{.underline}](https://support.google.com/meet/answer/14754931)*

*How is the quality of **these specific notes?** [[Take a short
survey]{.underline}](https://google.qualtrics.com/jfe/form/SV_9vK3UZEaIQKKE7A?confid=4JLifqwkqKpCouhMk6lnDxIXOAIIigIgABgBCA&detailid=standard&screenshot=false)
to let us know your feedback, including how helpful the notes were for
your needs.*
