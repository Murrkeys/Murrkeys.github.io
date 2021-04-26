---
layout: post
title: Data Science Ideas in Healthcare - Automated Process Mining
categories: [Personal,Healthcare]
---

### Introduction

The old business adage does, "You can't manage what you can't measure".  And when you are managing business processes, the first step to managing and hopefully improving a process is modeling the process.  During my time at UC San Diego Health, I was fortunate enough to receive my Black Belt certificate in Lean Six Sigma and be involved (both supporting and leading) in multiple process improvement projects across the organiziation.  Each of the projects were different in many ways, however almost every project began with a value stream mapping of the process in question.  Whether it was admitting patients for chemotherapy treatment or environmental services cleaning rooms, the process had to be modeled and analyzed before any solutions could be found.  

If you have ever been involved in similar projects, you probably know how difficult and time consuming this step can be.  It usually involves multiple meetings with the stakeholders to identify the process. Once the process is defined, thorough data analysis still has to be completed to quantify the different steps in the process.  And if the data doesn't exist?  Be ready to shadow the staff, sometimes with your iPhone stopwatch running!  After all this is complete, many times the process model still doesn't adequalety represent what is actually happening.  It's not an entirely data-driven process, and the subjective nature of the exercise can lead to mistakes.  

I am of the opinion that for the majority of cases, this exercise should be entirely data-driven and automated. This idea is known as [process mining](https://en.wikipedia.org/wiki/Process_mining).  In this post, I'm going to explain why I think healthcare can benefit enormously from process mining techniques.    

### What is Process Mining?

Process modeling aims to improve processes by optimizing the efficiency of connected activities in the provision of a product or service. There are a multitude of techniques, some common ones include flow charts, control flow diagrams, and gantt charts. Traditionally, the process would be visualized similar to below :

<img src="/images/delay_pic.PNG" alt="Discharge Delay Workflow"/>

This flow chart visualizes the workflow for a new nurse manager process.  As you can see, the activities are organized in order and by whom is responsible. Additional information is avaiable, such as which technology is needed and decision points.  You can imagine adding analysis to this flow chart to include how long different activities take and opportunities to remove or optimize certain ones.  In this example, the process work flow was created by shadowing nurse managers, a time intensive activity.  

Process mining moves beyong this traditional method by utilizing event logs.  What are event logs? Simply put, an event log is a data source that includes each specific event and a timestamp of when the event occured.  Using this event data, process mining can be used to more accurately represent what is actually happening.  With an accurate representation, new insights into problems and eventual solutions can be attained. 

There are three main types of process mining.  Discovery refers to process mining techniques that use event logs to construct entirely brand new process models. Conformance refers to comparing event logs against a model that already exists. This can be used to ensure business rules are being followed, or to analyze deviations away from what the expected process.  Finally, performance refers to using event logs to optimize the efficiency of a model that already exists.  Performance data can be analyzed to find improvement opportunities and model potential solutions.  All of these types are useful, and healthcare especially can benefit from these techniques as I will explain below. 

### Process Mining in Healthcare

Electronic Health Records (EHRs) offer a promising opportunity for process mining.  In an EHR, almost every event and action conducted is stored with both the event and time stamp.  Within the EHR there are many different types of data that is being stored.  Continous vital signs, patient movement, radiology utilization, and mediciation administration are a few different types of data that are included.  Obviously, there is a treasure trove of information here that is not being used to it's full capability today. Using the three types of process mining, I will illustrate a few specific examples of process mining applications in healthcare.  

The discovery process has a wide variety of use cases, however care pathways are the first (and probably most important!) one that come to mind.  Care pathways are the standard processes that patient's following for a specific diagnosis or procedure. For example, patients undergoing a knee replacement follow very similar trajectories post procedure until discharge from the hospital.  Discovery process mining can be used to define the most commonly followed paths for different groups of patients, and also find subsets of variations of these paths.  This is important information that can help standardize treatment plans and develop best practices. 

The conformance process naturally builds off of the discovery process to ensure processes follow the standard treatment plan or best practice defined above.  Another example is using the conformance process to make sure both external and internal guidelines are met.  For example, many times strict timelines are needed for mediciation administration.  Failure to comply with the timeline can lead to adverse events and poor quality outcomes.  Process mining can be used to ensure the process is followed correctly, and also root cause analyze any deviations from what is expected. 

Lastly, the performance process can be used to analyze processes, identify issues, and create potential solutions.  In many hospitals, the emergency department exceeds capacity limits almost on a daily basis.  A combination of patient's waiting for inpatient beds and inefficent treatment of ED patients leads to capacity issues, which results in negative consequences.  Performance process mining can be used to model out different pathways through the ED for different groups of patients.  Potential bottlenecks can be identified, and alternative strategies can be studied.  In this case, it could be identified that X-ray turnaround time was a bottleneck for a high percentage of patients or patients presenting with chest pain were spending a far longer time in the ED before discharging.  Whatever the problem might be, it would be difficult to identify without process mining tools. 

These are just a few examples of process mining applications in healthcare. Delivering healthcare is one giant process comprised of many small processes.  And process mining can help discover and improve on these processes, leading to more efficient delivery and better outcomes for all. 

### How to Automate?

When I think about automating process mining, I am thinking about a few different things.  As a discovery and performance process, I imagine a platform where analysts can upload their process log files and receive detailed analysis outlining their process.  The discovery function lies in defining the different variations the process takes, while the performance function lies in identifying possible issues and differences between the variations.  Software already exists that accomplishes this, here are a few tools I have used and recommend : [ProM](https://www.promtools.org/doku.php) and [Fluxicon](https://fluxicon.com/).  The real challenge is collecting and organizing the data log files that will be used.  Without the proper data to represent the process, any further analysis will be useless.  The data source needed in this case would be very complex. I imagine an overall data source with event logs for EVERY event that takes place in a health setting.  This would have to be a continous process, as different categories of events would be added over time.  Once this was in place, analysts and end users could filter down to specific areas and then use the platform to run their process mining analysis.  For example, a business analyst might filter down to a patient population consisting of only heart transplant patients.  The data behind the scenes would be the same for other patient populations, but in this case would only analyze the care pathways for heart transplant patients.  

As a conformance process, I imagine a platform that continously checks process log files to ensure deviations are not occuring.  Following the conformance and performance processes, this process is the ongoing analysis conducted to ensure conformance is met.  As an automated task, this is actually very simple.  With a well-defined process and resulting data source, processes can be monitored continously in a batch fashion or even real-time.  In a batch fashion, all events could be analyzed retroactively and any deviations could be identified for follow-up.  In real-time, a process could be identified as soon as a deviation occurs.  Alert systems or notifications to process stakeholders could be implemented for timely intervention.  The infrastucture to support either of these ideas are different, but both very much possible.  

This is no trivial task, and would require time and effort.  But, the idea is certainly possible and would be a very interesting, and important project to work on! 

### Conclusions

In this post, I took a deep look at what process mining is and how it can be applied in a health setting. I illustrated a few use cases and also outlined how process mining could be automated and implemented in a healthcare setting.  As data collection continues to grow, there will continue to be a huge opportunity to leverage process log files and apply data science techniques in healtcare. I hope this post was a useful introduction to these ideas, and sparked your interest!  Please feel free to reach out and connect. 


