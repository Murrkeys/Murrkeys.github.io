---
layout: post
title: COVID Stock Analyis
categories: [Python,Code]
---

As everyone knows, COVID-19 has thrown a wrench in our everyday lives and the economic market. However, with downside of the stock market, 
there is an opporunity for investors to buy stocks at a discounted price.  In this blog post, I will take a look at some quick analysis I conducted in Python to identify possible invesment opportunities.  

## Using Stock Data

This being my first time using Python to analyze stock data, I spent a huge chunk of my time figuring out the best way to do so. Luckily for you, I have summarized my method using the [yFinance](https://pypi.org/project/yfinance/)package.  You can find detailed infomration and summary at the link. For this post, I will just share a handy little function I wrote to make downloading lists of stock data fast and easy.  The function below can take in a single ticker or list of tickers, the start and end date, and returns the closing price for each ticker by day: 

```python
def get_stock_data(stock,start_date,end_date):
    
    data = yf.download(stock, start=start_date, end=end_date,threads=True)
    closing_data = data['Close']
    return closing_data
```
With this function defined, downloading historical stock data into a Pandas dataframe is easy:

```python
stock = pandas.dataframe(get_stock_data(ticker_list),"2019-01-01","2020-05-19"))
```
In my case, I performed some research to manually build a list of "blue chip" companies.  I am seeking to find companies with a strong reputation that I can hopefully buy into while shares are at a discount. 

## Analysis

With a dataframe of historical daily stock prices ready, the fun part begins.  

My process and logic is outlined below : 
<ul>
    <li>Calculate baseline and post COVID average stock price values</li>
    <li>Find companies with the largest decrease of stock price due to COVID impact.</li>
    <li>Of these companies, find the companies where the stock prices have not rebounded yet.</li>
    <li>From this list, perform due diligence and decide whether an investment is a good idea.</li>
</ul>
    
