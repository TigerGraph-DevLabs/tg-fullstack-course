---
template: overrides/main.html
---

# Chapter 01 - Introduction to Fullstack

Welcome to TigerGraph’s Fullstack tutorial!

With each of these seven chapters, we’ll walk through creating a COVID-19 tracker that utilizes TigerGraph’s Coronavirus Starter Kit to visualize, interact with, and gain insights into South Korea’s population movements and disease spread. By the end of this tutorial, you’ll have the tools necessary to create and deploy your very own full-stack application using TigerGraph!

## Tracker Overview

&nbsp; &nbsp;

> TODO: Insert introduction overview here!

&nbsp; &nbsp;

This COVID-19 tracker has several key benefits.


???+ tip "Patient Table"

    ### Patient Table

    This patient table allows for easy access to all patient data, stored in a tabular format. In total, this table will contain <> distinct patients. The columns list each patient’s name and  ID number. By scrolling through, one can click on any patient to learn more about their information, consisting of statistics, timelines, and a map.

???+ tip "Quick Statistics"

    ### Quick Statistics

    Upon selecting a patient, several figures will be displayed. These values include “People Contacted”, “People Infected”, “Travel Events”, and a custom “Risk Score”. This “Risk Score” is a measure of how likely it is that the given individual is infected. In order to calculate this value, <insert Leo’s description here>.

???+ tip "Travel Timeline"

    ### Travel Timeline

    Furthermore, one valuable insight is the various locations an individual has visited. This timeline displays the dates, location names, and latitude/longitudes of each of the places the individual has travelled to. This timeline is displayed in chronological order and is compared with other individual’s travel timelines to determine risk scores.

???+ tip "Movement Map"

    ### Movement Map

    In order to take this travel timeline one step further, each location is visualized on a map of South Korea. Each major point of interest is represented by a circle. The larger the circle, the more individuals that have travelled to that specific location. The darker the color, the riskier the location. This color value is determined by the number of individuals with COVID-19 that visited the location immediately before reporting a positive test.


All combined, these features allow for quick analysis of this large dataset.

In order to create our Covid-19 tracker, we will need to utilize a few powerful tools. Let’s take a closer look at all of the required components and examine how these pieces will fit together…

## Talkin' TigerGraph

We start with the most pertinent question: how will we store the data for this application?

For this integral task, we turn to TigerGraph.

### Intro To TigerGraph

TigerGraph is a native parallel graph database that can load and analyze large amounts of data in real-time. In comparison to traditional relational databases, TigerGraph's architecture and accompanying graph query language (GSQL) allow for quick, efficient, and powerful analytics.

TigerGraph has transformed the following fields:

&nbsp; &nbsp;

**Increase Revenue**

+ Product and Service Marketing
+ Entity Resolution
+ Customer Journey/360
+ Recommendation Engine

&nbsp; &nbsp;

**Reduce Cost and Manage Risks**

+ Anti-Money Laundering (AML)
+ Cybersecurity Threat Detection
+ Fraud Protection
+ Risk Assessment and Monitoring

&nbsp; &nbsp;

**Improve Operational Efficiency**

+ Energy Management System
+ Network Resources Optimization
+ Supply Chain Analysis

&nbsp; &nbsp;

**Foundational**

+ AI and Machine Learning
+ Geospatial Analysis
+ Time Series Analysis

In order to learn more about the evolution and proven potential of graph databases, feel free to check out the following four-part video series created by TigerGraph.

> TODO: Format these videos properly (embed them)

* https://youtu.be/g_yhkMA3xoE
* https://youtu.be/qLTiyg7972o
* https://youtu.be/ZE2u9oLW18k
* https://youtu.be/mfP6oHNZv34

How does TigerGraph achieve such an edge over traditional relational databases? To answer this, we must take a deeper dive into the methodology of data storage in a native parallel graph.

### Native Parallel Graphs

> TODO: Coming soon!
