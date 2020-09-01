---
layout: post
title: COVID Testing and Baye's Theorem
categories: [Healthcare, Statistics]
---

A recent [announcement](https://abbott.mediaroom.com/2020-08-26-Abbotts-Fast-5-15-Minute-Easy-to-Use-COVID-19-Antigen-Test-Receives-FDA-Emergency-Use-Authorization-Mobile-App-Displays-Test-Results-to-Help-Our-Return-to-Daily-Life-Ramping-Production-to-50-Million-Tests-a-Month) from Abbott introduces a cheap ($5) and fast (15 minutes) COVID-19 antigen test.  This test is a vast improvement over the current tests that require days and sometimes weeks to return results. With current production ramping up to 50 million tests a month, this new test will help lead to a return to normalcy in the United States.

From the above announcment, a clinical study concluded that the test demonstrates sensitivity of 97.1% and specificity of 98.5%.  In this post, I am going to explain what exactly sensitivity and specificity mean, and how this example can explain the Baye's Theorem. 

## Baye's Theorem

To explain specificity and sensitivity, I can make the following statement : From the COVID-19 test above, if a patient receives a positive test, then that patient has a 97.1% probability of actually being positive. Similarily, if the patient receives a negative test, then that patient has a 98.5% chance of actually being negative. 

Baye's Theorem goes a step further by incorporting our prior knowledge about COVID-19 prevalence in the United States. Currently, approximately 1% of the United States population is infected with COVID-19 (estimated from [link](https://www.worldometers.info/coronavirus/country/us/))

$$$
P(A | B) = (P(B | A)P(A)) / P(B)
$$$

## Conclusion

