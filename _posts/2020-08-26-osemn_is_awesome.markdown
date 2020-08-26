---
layout: post
title:      "OSEMN is AWESOME"
date:       2020-08-26 08:53:24 -0400
permalink:  osemn_is_awesome
---


There are many popular processes for a data scientist to go through in order to complete their work, one of the most popular in the field at this time is a strategy classed OSEMN (rhymes with awesome).  Today we will cover the five steps of OSEMN and why it is such a useful tool for data scientists. 


<img src = 'https://miro.medium.com/max/1705/1*Q7VCgPKQAI7XVKEvU4fxXA@2x.jpeg' width = '50%'> 

(Drawn by Chanin Nantasenamat)
# O - Obtaining Data
Obtaining the data can be performed in a variety of ways. Depending on what company you are working for they may provide the data for you, if not you will most likely need to web scrape, use an API, or be familiar with SQL. Once obtaining the data, it is important to take a look at what you have aquired. Some helpful strategies could be to use the df.head(), df.info(), df.describe(). This allows you to be familiar with the dataset before diving into the next section of OSEMN.

# S - Scrub Data
Scrubbing data is one of the most time consuming aspects of a data scientists career. However it is cruical to get the data into a format that is easier to use. Usually whatever data you obtain there will be something missing or wrong with it. Common items to look out for are Null values. Once identifying the Nulls it is esential to decide how you are going to handle them. Code that is commonly used for handling Null values is listed below:

'''df.isna().sum()'''
