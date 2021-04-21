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

<img src="/images/delay_pic.png" alt="Discharge Delay Workflow"/>

This flow chart visualizes the workflow for a new nurse manager process.  As you can see, the activities are organized in order and by whom is responsible. Additional information is avaiable, such as which technology is needed and decision points.  You can imagine adding analysis to this flow chart to include how long different activities take and opportunities to remove or optimize certain ones.  In this example, the process work flow was created by shadowing nurse managers, a time intensive activity.  

Process mining moves beyong this traditional method by utilizing event logs.  What are event logs? Simply put, an event log is a data source that includes each specific event and a timestamp of when the event occured.  Using this event data, process mining can be used to more accurately represent what is actually happening.  With an accurate representation, new insights into problems and eventual solutions can be attained. 

There are three main types of process mining.  Discovery refers to process mining techniques that use event logs to construct entirely brand new process models. Conformance refers to comparing event logs against a model that already exists. This can be used to ensure business rules are being followed, or to analyze deviations away from what the expected process.  Finally, performance refers to using event logs to optimize the efficiency of a model that already exists.  Performance data can be analyzed to find improvement opportunities and model potential solutions.  All of these types are useful, and healthcare especially can benefit from these techniques as I will explain below. 

### Process Mining in Healthcare

### How to Automate?

### Conclusions


