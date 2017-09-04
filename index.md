---
title       : What drives Infosys stock performance?
subtitle    : An initial exploration
author      : Krupakar Singampally
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Introduction

1. Infosys Limited is a multinational IT consulting firm based in India
2. In 2017, it exceeded annual revenue of $ 10 Billion and has over 200,000 employees
3. Infoys has been listed on the NASDAQ since 1999
4. This project sets up a very initial exploration of the question: What drives Infosys stock performance?

--- .class #id 

## How has the stock performed over the years?

Infosys is listed as 'INFY' on the NASDAQ since 1999. This analysis looks at stock performance between 2009 and 2017. The following summary features can be noted of the stock performance:





```
## [1] "INFY"
```

```
##      Index              INFY.Close   
##  Min.   :2007-01-03   Min.   : 5.28  
##  1st Qu.:2009-09-02   1st Qu.:11.53  
##  Median :2012-05-02   Median :13.80  
##  Mean   :2012-05-03   Mean   :13.57  
##  3rd Qu.:2015-01-04   3rd Qu.:15.76  
##  Max.   :2017-09-01   Max.   :20.00
```


Thus, The closing stock price of the stock has varied from $ 5.28 to $ 20.

The stock price information is obtained from Google. 

--- .class #id 

## How does the Shiny app help?

The project sets up a Shiny app that allows the user to see how stock price trends  relate to the following performance parameters:

- Quarterly revenue
- Quarterly operating margin
- Annual revenue
- % increase in Q-o-Q revenue
- Key events such as management changes



--- .class #id 

## Key elements of the Shiny app 

- Stock price time series data is obtained from Google using the 'zoo' package
- Quarterly end points of the closing stock price are selected into a new dataframe
- Revenue and margin information is obtained from the Infosys website. They are pre-procossed into a csv file
- Management changes by date have been collected into a csv file and ingested
- The GoogleViz package is used to generate combo plots that juxtapose stock price with revenue 
- The UI allows the user to select each combo graph to examine trends one by one
- The Application can be accessed here: <a href="https://svkrup.shinyapps.io/InfShiny/" target="_blank">Infosys Performance</a> 

--- .class #id 

## Initial observations 

- Revenue has increased continuously for all quarters and years from 2009, but the stock price has moved up and down over the years. Hence, absolute revenue may not be a primary feature  
- This is the same for annual revenue. Annual revenue is computed as a sum of quarterly revenue from April to March, and the March end stock price is used for comparison
- Operating margin has seen quite a bit of fluctuation across the years. But stock price is not exactly in tune with the trends of OM
- The % Q-o-Q revenue growth seems to be much more correlated to stock price movements. QoQR is the % growth in current quarter revenue from the same quarter in the previous year
- Key leadership changes seem to preceed a stock price trend. The movement can be negative or positive 

**Conclusion:** Key performance indicators certainly seem to have a predictable impact on the stock price. Other factors will also need to be examined before model creation. 
