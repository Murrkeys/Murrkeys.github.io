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
