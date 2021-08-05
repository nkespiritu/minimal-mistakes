---
title: "Comparing travel behavior during 2019 and 2020 in the New York City Taxi and Limousine Commission trip records"
date: 2021-07-28
permalink: /nyctlceda
tags: [data wrangling, data science, exploratory data analysis, big data]
header:
  image: "images/nyctlceda_banner.png"
excerpt: "An exploratory data analysis on pandemic and pre-pandemic NYC TLC data using Dask."
mathjax: "true"
---

[![](https://img.shields.io/badge/Jupyter-View_Notebook-F37626?logo=jupyter)](https://github.com/nkespiritu/nika-espiritu.github.io/blob/master/_pages/nyctlc_eda/nyctlceda_20201130.ipynb)       [![](https://img.shields.io/badge/Github-View_HTML-181717?logo=github)](https://github.com/nkespiritu/nika-espiritu.github.io/blob/master/_pages/nyctlc_eda/nyctlceda_20201130.html)

## Purpose

This mini project was written alongside my Term 3 learning team partner, [Jasper Pangan](https://www.linkedin.com/in/jasperkristianpangan/). This was submitted for our Big Data and Cloud Computing class held from September 2020 to January 2021. In this class, we were tasked to do an exploratory data analysis on 15 GB worth of data. We were required to use Dask, a Python library specifically for wrangling big data.

## About the data

Data of trips taken by taxis and vehicles in New York City were retrieved from the NYC Taxi and Limousine Commission (TLC) Trip Record Data found in the Registry of Open Data on Amazon Web Services (AWS) S3 bucket.

As of writing this, data available was only from January 1, 2019 to June 30, 2020. This corresponds to  9.36  GB worth of data. After preprocessing, this corresponds to  80,810,133  transactions in 2019 and  15,859,906  transactions in 2020.

## Methodology

<img src="{{ site.url }}{{ site.baseurl }}/images/workflow.png" alt="Methodology">

## Insights

<img src="{{ site.url }}{{ site.baseurl }}/images/nyctlceda_viz.png" alt="Viz">

1. We found little change in routes and in travel times of New Yorkers, but instead we found that New Yorkers strictly complied with the stay-at-home measures enacted by the government, thus signifying a drop in the volume of taxi transactions. 
2. People usually travelled alone in pre-pandemic times, but this phenomenon increased during the pandemic. 
3. We also found that cashless transactions were banned by legislators, and people are experiencing the impacts of this legislation. 
4. With the reopening of New York, we are now seeing a small increase in volume of transactions, and this should help NYC taxi drivers.