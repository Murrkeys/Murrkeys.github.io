---
layout: post
title: Australia Hospital Dashboards using R Shiny
categories: [R,Code,Healthcare]
---

I have extensive experience in the development of healthcare dashboards. My position at UC San Diego Health began with tedious, manual updates of enormous, complex Excel dashboards.  Luckily, the bulk of my dashboarding is done in Tableau now.  Tableau offers an easy way to create attractive, automated dashboards that decision makers love to use.  While Tableau is amazing at certain things, it still leaves a lot to be desired. Namely, it doesn't offer great functionality to incorporate custom, statistical analysis into user facing dashboards.  Therefore, I was really excited to learn more about R Shiny during my courses this past term.  This blog post will summarize my final term project and give a basic explanation of how R Shiny apps work.  The entire script for this project can be found on my [Github](https://github.com/Murrkeys/australia_hospital_shiny).

## The Basics

Shiny is an R package that is used to create interactive web applications straight from the R statistical software. A Shiny app is contained in a single script called *app.r*.  The script has three main components : 1) A user interface object (UI) 2) A server function 3) a call to the shinyapp function. 

For this dashboard, I will be using a dataset that contains length of stay summary information for Australian hospitals.  I will be building a dashboard that contains the following : 
* Plot with Average Length of Stay (ALOS) on Y-axis and Time Period on X-axis
* Point for each hospital, with number of overnight stays controlling the size and color of each point
* A reference line in each time period for peer ALOS comparison
* Filterable by Peer Group (Hospital Type) and Category (diagnosis/procedure).

## UI Code




## Server Code

## Screenshots of App

## Conclusions
