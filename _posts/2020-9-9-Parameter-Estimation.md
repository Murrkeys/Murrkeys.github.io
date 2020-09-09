---
layout: post
title: Parameter Estimation
categories: [Healthcare, Statistics, R]
---

When the COVID pandemic took off in early March 2020, my department at UC San Diego Health was tasked with modeling out potential scenarios for the capacity impact on our hospital system.  Lacking the epidemiology expertise needed to create a sophisticated infection model, I decided to use the [CHIME](https://penn-chime.phl.io/) tool developed by the Penn Medicine Predictive Health team. The interactive tool models out potential scenarios based on a variety of input parameters specific to your health system and area. 

As you may know, ICU capacity was one of the most significant constraints facing health systems in response to COVID-19.  Therefore, the *Average ICU Length of Stay*, was an extremely important input parameter that we needed to get right in order to provide accurate projections.  This blog post will summarize the steps needed to estimate this parameter, both early on with limited data and a few months later when more COVID patients had been cared for.    

## The Data

The dataset contains ICU status (Ecmo, Vent, Non-vent), discharge grouping, and the total ICU length of stay.  The Group Two column splits the data into two groups that I will use for the estimation. The first group contains patients seen early (March/April) in the COVID pandemic.  The summary statistics for each column can be seen below :  

<img src="/images/PE_6.PNG"/>

I also wanted to see the difference in LOS between the two groups : 

<img src="/images/PE_7.PNG"/>

The first grouping only contains 29 observations, while the second grouping contains 123.  The mean and standard deviation for the second grouping is higher, both likely due to high outliers present in the second group.  

Below, the histograms for LOS for the first group and overall data can be observed : 

<img src="/images/PE_2.PNG"/>

<img src="/images/PE_1.PNG"/>

Neither of these distributions look remotely close to normal, especially the first group.  As a result, simply taking the mean was not going to be a great estimate.  To 

## Bootstrap Method




## Conclusion


