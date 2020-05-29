---
layout: post
title: Automated Exploratory Data Analysis in R
categories: [R,Code]
---

One of my classes this past term focused heavily on using R for statistical computing.  Many times during the course, I found myself performing similar exploratory data analysis (EDA) processes when beginning an analysis project. So, I began to work on a R script to automate the EDA process.  My final goal being to load a dataset, make a few manual adjustments, and then generate a clean looking report with my entire EDA findings.  

Safe to say, this is tougher than it sounds. I'll share some code below for the project progress so far.  I've been able to perfom a majority of the univariate analysis, but I am having heaps of trouble automating the bivariate analysis. Before I share the code, I'm going to quickly summarize what I mean when I say "Exploratory Data Analysis". 

Anytime you begin working with a new dataset, you typically begin by performing EDA to understand key characteristics about the data.  These characteristics include things such as : 
<ul>
    <li>Do any columns have missing values?</li>
    <li>Are my columns normally distributed?</li>
    <li>Do any correlations exist between columns?</li>
    <li>What is the frequency of the categorical variables</li>
</ul>
There are many questions I seek to answer when first analyzing a dataset. And while the process is not always the same, a majority of the questions are answered in every single EDA.  There are two main forms of EDA, univariate and bivariate analysis.  Univariate analysis is concerned with the characteristics of a single field, things like summary statistics and the shape of the data.  Bivariate analysis is concerned with how variables related to each other, things such as correlation and grouped summary statistics. 



