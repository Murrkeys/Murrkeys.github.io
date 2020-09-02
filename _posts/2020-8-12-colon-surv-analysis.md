---
layout: post
title: Colon Cancer Survival Analysis
categories: [R,Code]
---
In this post, I will be conducting analysis on colon cancer survival.  The dataset include information from a clinical trial on the effectiveness of two different types of chemotherapy (levamisole and levamisole+5-fluorouracil) compared to controls (i.e. no chemotherapy treatment) on survival from stage B/C colon cancer.  

I will highlight the process and some key findings from the overall analysis.  The complete code and analysis can be found on my [Github](https://github.com/Murrkeys/colon_cancer_survival_model). 

## Initial Survival Curves

The documentation for the dataset can be found [here](https://stat.ethz.ch/R-manual/R-patched/library/survival/html/colon.html).  This analysis will study the effects of the chemotherapy treatments as well as other clinical variables concerning the colon cancer diagnosis. The survival object for this analysis is *Time* and *Status*.   Time represents the days until death or censoring. Status represents whether the individual died or whether the individual was censored.  In this context, censored means the patient was still alive when the study observation took place.    

First, let's take a look at the overall survival curve by fitting a Kaplan-Meier survival curve : 

<img src="/images/SA_1.PNG">  

Let's also stratify the survival curve by the treatment (rx) and more than 4 positive lymph nodes (node4) : 

<img src="/images/SA_2.PNG">

<img src="/images/SA_3.PNG"> 




## Fitting a Linear Model



<img src="/images/LM_4.PNG">  
 

## Conclusion


