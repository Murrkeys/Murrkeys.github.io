---
layout: post
title: Techniques for Data Management and Reproducibility
categories: [Statistics]
---

Have you ever recevied an email like this : *"Hi this is so and so.  Would you mind re-doing that analysis from two years ago by updating it for the past year?"*.  If you're anything like me, this would lead to a frantic scramble in old folders to find an Excel file that you may, or more probable, may not remember exactly where the data came from.  As a healthcare data analyst who performs plenty of ad-hoc analysis, this is a common experience. 

Well, how to solve this issue?  Enter the unsung hero : Data Management Techniques for Reproducible Research!  Lost in the flashiness of statistics and machine learning algorithms, lies the most important part of any research project involving data that no one cares to talk about. The techniques needed to properly manage the data, and allow for the research to be reproducible. Since my data analyst position is not a research role, I was not familiar with this process.  In this blog post, I will explain the high level techniques associated with sound data management.  A process I am incorporating into my work flows, and you should too! 

## Data Management Techniques

A proper data management plan will have all the required information needed by yourself or others to locate, understand, and interpret the research in the future. While the format and content may differ, a data management plan should include all of the following : 

* What data will be created?
* Who owns the data and who will have access to it?
* What formats will the data have?
* Details about the ethics committee approvals.
* Who will have access to your data and how will you protect for unnecessary access if data is sensitive/confidential in nature?
* Data organistion: File naming conventions, folder structure.
* Data storage: Where will the data be stored? Will it be backed up?
* Data sharing: Will you share your data with others? How will you do this?

A detailed checklist can be found [here](https://www.dcc.ac.uk/DMPs/checklist).  

In addition to a document answering the above questions, a metadata document and thorough data dictionaries need to be included.  The metadata document is a condensed version of the data management plan and can be referenced by people exploring the dataset and/or research for the first time. 

Data dictionaries need to be included for any dataset used in the analysis/research.  The data dictionary includes both the original and created variables.  The data dictionary should include the following information about each field : 

* Variable Name
* Description 
* Format
* Allowable Entries

Below is a screenshot showing a simple example of a few fields : 

<img src="/images/DM_2.PNG"/>

Where,  
* P(A) is the probability of event A.
* P(B) is the probability of event B.
* P(A/B) is the probability of observing event A if B is true.
* P(B/A) is the probability of observing event B if A is true.

## Reproducibile Research

## Conclusion
 
