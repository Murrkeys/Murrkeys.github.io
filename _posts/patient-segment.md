---
layout: post
title: Data Science Ideas in Healthcare - Patient Segmentation
categories: [Personal,Healthcare]
---

### Introduction

The healthcare landscape is continuing to transform from volume to value-based care models in order to lower costs and provide higher quality care for individuals and populations.  Population segmentation holds enormous potential to aid organizations as they transition to patient-centered care models.  Population segmentation aims to address the key issue facing health systems today: how to give the right care, to the right person, at the right time.  However, population segmentation remains a relatively novel approach, and there is a tremendous opportunity to expand on current tools and offerings. 


### What is Population Segmentation?

To achieve true patient-centered care, an integrated care model is needed.  Integrated care aims to coordinate a patient's care across all the different settings and providers a patient might access.  For this to work, the patient's specific needs and characteristics needs to be taken into account.  A popular term many use to describe this idea is precision medicine.  Precision medicine aims to tailor care for the individual based on personal information such as demographics, environment, and genomics.  While precision medicine shows promise for a myriad of future health applications, it is still infeasible today to develop care models and interventions for each individual.  Therefore, population segmentation is a technique that can identify groups of patients with largely similar characteritics that can be used for care delivery.  

At it's core, population segmentation is the process of identifying distinct sub-populations with similar characteristics.  The identification and definition of the sub-populations depends on the question at hand, as well as what data is being used.  For example, a segmentation analysis answering "How do we better attract and retain consumers?" will be very different from one answering "What interventions can we introduce for high utilizers?".  In both cases, the process to create segments is the same, but the data needed is very different.  The former will require customized survery data, along with demographic data, to understand patient's attitudes and preferences towards healthcare.  The latter will require clinic, ED, and hospital utilization and treatment data, along with demographic data, to understand patient's historical usage and morbidity patterns.  

In general, the resulting segments can be used in a variety of ways.  The most obvious application is tailoring services, programs, and interventions to those who need them most.  By doing this, outcomes are improved and costs are controlled for the entire population.  The outcomes and benefits are varied and can impact multiple areas, such as disease incidence, cost-effectiveness, worsening health states, and quality of life indicators.  The population segments also offer an opportunity for further analytical insights.  The segments can be extremely useful in predictive applications, where certain segments are associated with relevant clinical outcomes.   Also, the segments can be used as a stratification method in a variety of analysis workflows.  Within the segments themselves, insights can be generated for factors affecting how and why certain sub-populations fall into a segment.  Overall, population segmentation can be valuable as a standalone tool, but also offers plenty of value for further analysis. 

If you are interested in learning about some real-world examples of patient segmentation, the following links can be used.  The ["Better Health for London"](https://www.healthylondon.org/resource/better-health-london-report/) is a report developed by the London Health Commission that applies patient segmentation to understand the needs-based care for everyone.  The relevant section of the report is Section 3.1 : Making Care More Personal.  The ["Bridges to Health"](https://outcomesbasedhealthcare.com/bridges-to-health-segmentation-model/) is a framework developed to pursue the health of each population segment, where different segments require different strategies.  Finally, Kaiser Permanente developed a [Senior Segmentation Algorithm](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4116260/) for use in risk stratification and tailored interventions for older patients.   

### How to Implement?

The implementation of population segmentation depends entirely on the data available.  If the data needed to represent a problem is not available, then population segmentation methods will be useless.  In many instances, custom primary data sources, such as surveys, will be needed to properly create segments.  Once the data is available, many times unsupervised machine learning approaches are used to create the sub-populations.  Clustering algorithms, such as k-means, are popular for their simplicity and usefulness. Other clustering algorithms, such as DBSCAN and Hierarchical Clustering, can be applied depending on the problem at hand.

The operationalization will depend entirely on what the segments will be used for. Automated dashboards and reports can be created that visualize the segments and monitor key clinical indicators within them.  Segments can also be used in process improvment projects, to tailor interventions to the correct group.  Another interesting use is monitoring transitions between segments, creating a process to identify and notify providers when patients move into a new segment.  Overall, the segments are merely another useful feature that data analysts and scientists can use for their workflows. 

### Conclusions

Population segmentation provide a range of benefits to both policy makers and care providers.  Integrative care models are here to stay, and population segmentation is a powerful tool needed to support these models now and in the future.  As this movement towards true patient-centered care grows, data-driven approaches are needed to ensure that the right patient is receiving the right care at the right time.  Population segmentation obviously holds enormous potential, and I would love to work on these problems in the future.  As always, please reach out to connect if this interests you! 


