---
title: "Comparing travel behavior during 2019 and 2020 in the New York City Taxi and Limousine Commission trip records"
date: 2021-07-28
last_modified_at: 2021-08-11
permalink: /projects/nyctlceda
tags: [data wrangling, data science, exploratory data analysis, big data]
header:
  image: "images/nyctlceda_banner.png"
  caption: "Photo credit: [**Mikayel Bartikyan** from Getty Images on Canva](https://www.shutterstock.com/image-photo/nyc-cabstaxinew-york-america-times-square-686662231)"
excerpt: "An exploratory data analysis on pandemic and pre-pandemic NYC TLC data using Dask."
category: "projects"
mathjax: "true"
show_date: "true"
---

[![](https://img.shields.io/badge/Jupyter-View_Notebook-F37626?logo=jupyter)](https://github.com/nkespiritu/bdcc-mp2/blob/e299508dccd35b420be67d2f4fedf38419ef2e3a/T3_LT6A_BDCC_MP2.ipynb)       [![](https://img.shields.io/badge/Github-View_HTML-181717?logo=github)](https://github.com/nkespiritu/bdcc-mp2/blob/e299508dccd35b420be67d2f4fedf38419ef2e3a/T3_LT6A_BDCC_MP2.html)

*This mini project was written alongside my Term 3 learning team partner, [Jasper Pangan](https://www.linkedin.com/in/jasperkristianpangan/). This was submitted for our Big Data and Cloud Computing class held from September 2020 to January 2021. In this mini project, we were tasked to do an exploratory data analysis on 15 GB worth of data (size is prior to pre-processing). We were required to use Dask, a Python library specifically for wrangling big data.*

## Objective

Government response has worked double time to balance safety of the people as well as health of the economy. However, the impact of the pandemic still stands to this day: unemployment has surged, businesses and restaurants have shut down, and lives have been lost.

In this paper, we zoom in to see how the pandemic has affected transactions made with New York taxi drivers and compare this to their figures before the pandemic. **With New York City being the epicenter of the COVID-19 pandemic, how has travel behavior changed through the course of 2020 compared to pre-pandemic times?**

## About the data

Data of trips taken by taxis and vehicles in New York City were retrieved from the NYC Taxi and Limousine Commission (TLC) Trip Record Data found in the Registry of Open Data on Amazon Web Services (AWS) S3 bucket.

As of writing this, data available was only from January 1, 2019 to June 30, 2020. This corresponds to  9.36  GB worth of data. After preprocessing, this corresponds to  80,810,133  transactions in 2019 and  15,859,906  transactions in 2020.

## Methodology

<img src="{{ site.url }}{{ site.baseurl }}/images/workflow.png" alt="Methodology">

1. **Establishment of Dask Cluster**: We first set up our Dask scheduler and workers through Amazon Web Services’ Elastic Compute Cloud (AWS EC2) web service, as we will be dealing with \\(9.36\\) GB of data thus the need for distributed computing. To run the succeeding codes, we have assigned Jojie, the Asian Institute of Management's supercomputer, as our client.
2. **Data Extraction**: After establishing the connections of our client, scheduler, and workers, we extracted NYC TLC data from the AWS Registry of Open Data [6]. The extracted data covers the period of January 2019 to June 2020 (the most recent data as of this study). To focus our efforts, the scope was trimmed down to Yellow Taxis which refers to the official taxicabs in New York City.
3. **Data Processing**: We then cleaned the data by applying the following: 1) extracting year, month, day, and hour of transaction based on tpep_pickup_datetime; 2) adding a trip count; and 3) removing invalid trips (i.e., trips with invalid zones, no fare, no distance traveled, and no passengers).
4. **Exploratory Data Analysis (EDA) and Descriptive Analytics**: In our EDA, we answered the following questions and researched on supporting facts and evidence in current events:
    1. How has the pandemic affected the daily number of taxi transactions?
    2. Comparing 2019 and 2020 travel patterns, where were people coming from and heading to?
    3. In analyzing 2020 travel patterns, were people traveling to and/or from known COVID-19 hotspots?
    4. In taxi trips, were people practicing social distancing by limiting the number of people within taxi trips?
    5. How did payment behavior change due to the pandemic?
    6. Since New York has implemented a phased reopening, how did this affect mobility of New Yorkers?

## Insights

<img src="{{ site.url }}{{ site.baseurl }}/images/nyctlceda_viz.png" alt="Viz">

1. Consistent with Gov. Andrew Cuomo's stay-at-home orders issued on March 22, demand for taxis plummeted. However, travel ban for taxis were never issued. Instead, the quick drop in transactions is a demand-driven impact of the stay-at-home orders to the general New York population, as shown in the above graph. Nonetheless, it was too late, as New York quickly became the epicenter of the COVID-19 pandemic during early 2020.
2. We found little change in routes and in travel times of New Yorkers, but instead we found that New Yorkers strictly complied with the stay-at-home measures enacted by the government, thus signifying a drop in the volume of taxi transactions. 
3. People usually travelled alone in pre-pandemic times, but this phenomenon increased during the pandemic. When lockdown measures eased in June 2020, couple passengers gradually increased.
4. We also found that cashless transactions were banned by legislators in January 2020, and people are experiencing the impacts of this legislation. 
5. With the reopening of New York, we are now seeing a small increase in volume of transactions, and this should help NYC taxi drivers.