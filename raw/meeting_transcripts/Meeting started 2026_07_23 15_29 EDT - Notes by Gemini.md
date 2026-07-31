Jul 23, 2026

## **Meeting Jul 23, 2026 at 15:29 EDT**

### **Summary**

Technical review session covering model performance discrepancies, infrastructure updates, and dashboard documentation improvements for better usability.

**Addressing Model Metric Errors**  
Discrepancies in object detection accuracy stemmed from flawed pixel-level calculations regarding large object classification. The primary decision was to recalibrate these metrics to ensure accurate object-level performance tracking.

**Streamlit Infrastructure Enhancements**  
Updates are underway to integrate version 3 models into the application for performance demonstrations. Focus remains on verifying pixel-level accuracy across multiple model versions.

**Standardizing Dashboard and Training**  
Training methodology discussions highlighted the need for isolating variable impacts on model performance. Dashboard documentation will adopt a streamlined format emphasizing high-level results over technical clutter.

### **Decisions**

## Aligned

* **V3 model selection for presentation** The V3 model is selected for use in the upcoming presentation to Bridget, as it is identified as the best-performing model for both UXO and general classes.

* **Strategy for isolating training variables** Future model training will isolate specific changes, such as image transformations versus data augmentation, to systematically evaluate the performance gains of each factor.

* **Documentation format for model reports** Model reporting will adopt a high-level format featuring a summary headline and a link to full technical details, replacing the practice of including exhaustive details directly in the documents.

We've **updated the Decisions section** using your feedback.

Let us know what you think: [Helpful](https://google.qualtrics.com/jfe/form/SV_5bXzKQfylMIhSXc?isHelpful=True&entryPoint=decisions&isGoogler=False) or [Not Helpful](https://google.qualtrics.com/jfe/form/SV_5bXzKQfylMIhSXc?isHelpful=False&entryPoint=decisions&isGoogler=False)

### **Next steps**

- [ ] \[Sachin\] Fix prediction bug: Resolve the object prediction calculation error and update the associated metrics.

- [ ] \[Sachin\] Add V3 model: Incorporate the V3 model into the Streamlit application.

- [ ] \[Sachin\] Summarize V2 model: Provide a concise summary of changes and results for the V2 model within the documentation.

- [ ] \[Sachin\] Share documentation link: Upload the detailed documentation to the repository and share the link for future reference.

### **Details**

* **Object Detection Calculation Discrepancies**: Sachin Pandey reported a bug in the model's performance metrics, where pixel-level accuracy for large objects, such as "AI big," shows high overlap (approximately 80%) but fails to classify the entire object as a single unit. Because the model fails to predict the remaining pixels as part of the object, it generates multiple incorrect annotations in separate locations, leading to poor object-level metrics. Sachin Pandey confirmed they would resolve this calculation error and update the matrices accordingly.

* **Streamlit Model Updates**: Geoff Horowitz requested the addition of the V3 model to the Streamlit app (instance 8505\) for upcoming demonstrations. Sachin Pandey confirmed that the V3 model is the top performer for UXO (Unexploded Ordnance) tasks and performs as well as previous versions on other classes. Sachin Pandey agreed to update the app with the V3 model and verify pixel-level metrics for both the V1 and V3 versions.

* **Training Methodology and Augmentation**: The team discussed the role of "cut and paste" synthetic data in the training pipeline. Sachin Pandey clarified that while cut and paste augmentation was already present in the baseline configuration, the frequency was increased to improve model performance. Geoff Horowitz expressed confusion regarding the specific contributions of another team member, Proty, and whether their procedural generation work differed from the existing pipeline. To ensure clarity, Sachin Pandey suggested isolating variables in future training runs—specifically separating image transformations, such as brightness and gamma adjustments, from augmentation strategies—to accurately measure the impact of each change on model gains.

* **Standardizing Dashboard Documentation**: Geoff Horowitz reviewed the documentation layout on the dashboard and requested a more concise format. Geoff Horowitz advised that the interface should feature high-level summaries of model changes and results, with links to detailed external reports or HTML files for those who need to review full technical specifications. Sachin Pandey agreed to organize the documentation for the V2 and V3 models to follow this structure, keeping the main interface clear while maintaining access to detailed data.

* **Tool Usability and Interface Navigation**: Geoff Horowitz and Sachin Pandey reviewed the usability of the application and confirmed it was functioning as expected. Sachin Pandey provided instructions on navigation controls, explaining that users can zoom by holding Ctrl while scrolling and move the view horizontally by holding Shift while scrolling. Following this discussion, Sachin Pandey committed to updating the model and metrics on the platform prior to an upcoming meeting scheduled for one hour later.

*You should review Gemini's notes to make sure they're accurate. [Get tips and learn how Gemini takes notes](https://support.google.com/meet/answer/14754931)*

*How is the quality of **these specific notes?** [Take a short survey](https://google.qualtrics.com/jfe/form/SV_5bXzKQfylMIhSXc?confid=NEKh2090hpZX2uoNIOLIDxIXOBEBMgUIigIgABgBCA&detailid=standard&screenshot=false&entryPoint=footerMain&isGoogler=False) to let us know your feedback, including how helpful the notes were for your needs.*