---
title       : M/M/C Queueing Model Calculator
subtitle    : 
author      : Thomas Roh
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Service Engineering

* Does your staff ever feel overwhelmed throughout the course of the day?

* Do you want to reduce customer waiting time?

* Do you need to hire more staff or reduce it?

Service engineering is a great way to answer many of these questions with
a data-driven approach. Through the use of queuing models, managers can better
align their staff to customer demand. This can allow your company to work optimally.

--- 

## M/M/C Queue

An M/M/C queue refers to service lines that have arrival and service rates that are
exponentially distributed and the C refers to the number of servers. The queueing model takes
into account the variability of people arriving at random times of the day and also the 
randomness of the length of time it takes to serve the customers. The information that can be gleamed from this model is:

* Average Number of Customers in the System
* Average Number of Customers Waiting in Line
* Average Time the Customer spends in the System
* Average Customer Waiting Time
* Average Server Utilization

---

## How does it work?

The only information that you need to provide is the average arrival rate and service rate and the
number of servers. The following code then returns the outputs:

```
library(queueing)
inputs <- NewInput.MMC(15,5,4)
model <- QueueingModel(inputs)
paste('The Average Number of Customers in the System',L(model))
paste('The Average Number of Customers Waiting in Line',Lq(model))
paste('The Average Time the Customer spends in the System',W(model))
paste('The Average Customer Waiting Time',Wq(model))
paste('The Average Server Utilization',RO(model))
```

---

## The Results


```
[1] "The Average Number of Customers in the System 4.52830188679245"
```

```
[1] "The Average Number of Customers Waiting in Line 1.52830188679245"
```

```
[1] "The Average Time the Customer spends in the System 0.30188679245283"
```

```
[1] "The Average Customer Waiting Time 0.10188679245283"
```

```
[1] "The Average Server Utilization 0.75"
```

--- 

## The Application

Now lets do it with multiple servers.

<img src="assets/fig/unnamed-chunk-2.png" title="plot of chunk unnamed-chunk-2" alt="plot of chunk unnamed-chunk-2" style="display: block; margin: auto;" />


