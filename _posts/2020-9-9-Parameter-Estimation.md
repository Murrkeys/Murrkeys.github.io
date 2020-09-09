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

Neither of these distributions look remotely close to normal, especially the first group.  As a result, simply taking the mean was not going to be a great estimate.  In order to more accurately estimate the mean, I decided to use the bootstrapping method. 

## Bootstrap Method

The [Bootstrap Method](https://en.wikipedia.org/wiki/Bootstrapping_(statistics)) is a resampling technique used to estimate statistics on a population by sampling a dataset with replacement.  To do this, the process is as follows : repeatedly take a small sample, calculate the statistic of interest, and take the average of the calculated statistic at the end.  Below is the R code needed to perform this manually for the first grouping : 

~~~~
first_subset <- los %>% filter(Group_Two == "First")

#manual calculation

# Create placeholders for mean,lower, and upper bounds for each sample
samp_lb <- rep(0, 1000)
samp_ub <- rep(0, 1000)
samp_mean <- rep(0, 1000)



# Draw 1000 samples & calculate 95% CIs for mean

for (i in 1:1000) {
 samp <- sample(first_subset$LOS, 10,replace=TRUE)
 se <- sd(samp)/sqrt(10)
 samp_lb[i] <- mean(samp) - 1.96*se
 samp_ub[i] <- mean(samp) + 1.96*se
 samp_mean[i] <- mean(samp)
}

mean(samp_mean)
mean(samp_lb)
mean(samp_ub)
~~~~

For the first grouping, the estimated mean was 10.37 and the 95% confidence interval was (5.8,14.9).  This is a pretty wide interval for the mean, and the COVID model outcomes vary significantly between lower and upper bound values.  

I also used the *boot* package available in R to calculate the estimated mean.  In order to use the boot function, you must define a function for the desired statistics you want to estimate (in this case just the mean).  The code for the first grouping is below : 

~~~~
#create function for mean

boot_fun <- function(data,index) {
  dt <- data[index,]
  mean(dt[,3])
}

#boot function with 1000 samples
myboot<- boot(first_subset, boot_fun, R=1000)

#display the output
myboot

#calculate the 95% CI
boot.ci(myboot, index=1)
~~~~

For the first grouping, the estimated mean was 10.27 and the 95% confidence interval was (7.5,12.9).  The difference between the manual calculation and the boot function arises from the sample size used. In the manual calculation, I only used a sample size of 10 which is small. The interval in this example was tighter and makes me feel a little more confident about using the estimated mean in the model. 

I also estimated the means and 95% confidence intervals using the entire dataset. For the bootstrap package, this returned an estimated mean of 10.6 and a 95% confidence interval of (9.2,12.1).  With more data, the interval shrunk further around the mean of 10.6.  The output distributions for the first grouping and entire dataset are shown below : 

<img src="/images/PE_3.PNG"/>

<img src="/images/PE_4.PNG"/>

It is important to realize that both distributions now appear normally distributed and we can use this distribution to make inferences about the estimated statistics similar to above.  Obviously, it always helps to have more data (information!) about the parameter of interest as seen above in the shrinking of possible values.   


## Conclusion

With all of the above work, we ended up using multiple values of *Average ICU Length of Stay* to model out potential scenarios.  The mean of 10 was used as the most likely scenario, but extreme scenarios on both the optimistic and pessimistic sides were shared as well.  It was very important to prepare for the worst, but hope for the best. Bootstrapping is a powerful tool to know and I hope this example helped shed some light on real world applications!   


