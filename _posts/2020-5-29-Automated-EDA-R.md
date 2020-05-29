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

Below, I will share some of the code I've written so far : 

## Load Dataset, Manual Adjustments

To begin, I loaded in three example datasets. I then chose which dataset to use, took a look at the columns, and made a few adjustments depending on how I wanted to analyze this data. Note : I am using the [Hmisc](https://cran.r-project.org/web/packages/Hmisc/index.html) and [Tidyverse](https://www.tidyverse.org/packages/#installation-and-use) packages.  

~~~~

library("tidyverse")
library("Hmisc")

heart <- read.csv("heart.csv", header=TRUE)
cars <- read.csv("USA_cars_datasets.csv", header=TRUE)
suicide <- read.csv("master.csv", header=TRUE)

data <- cars

dim(data)
str(data)

#Prepare dataset to allow for automated analysis
#Goal is for this cell to be the only required manual work

#Drop columns not needed in analysis
data_new <- subset(data, select = -c(model,vin,lot,condition))

#Set correct data type for columns

data_new$year <- as.factor(data_new$year)
data_new$mileage <- as.integer(data_new$mileage)

#Set index column if it exists
data_new <- data_new %>% remove_rownames() %>% column_to_rownames(var = "X")

#Print out new summary
str(data_new)
~~~~

FYI, I'm still new to using Markdown, so I won't be sharing the output. I'm hoping to set up RMarkdown and Jupyter notebooks to use in my blog soon!

## Univariate Analysis
Next, I will share some examples of the univariate analysis I performed.  This analysis is different depending on the data type of the field (integer or categorical in this case). 

First, I wrote a function that calculates the summary statistics (mean,median,percentiles,etc) for the numeric columns and the frequency tables for the categorical columns. The results are stored in a list so I can access them in my later report : 

~~~~
#Function for univariate descriptive statistics for each column

num_descrip_stat <- function(x) {
    
    if (class(x) == 'integer'){
        y <- summary(x)}
    
    if (class(x) == 'factor'){
        a <- table(x)
        b <- as.data.frame(a)
        c <- round(100*prop.table(a),digits=2)
        b$Percentage <- c
        y<-b}
    
    return(y)
}

#Create list with univariate descriptive statistics for each column

output_list <- lapply(data_new, num_descrip_stat)

~~~~




