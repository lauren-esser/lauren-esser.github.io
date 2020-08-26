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
Obtaining the data can be performed in a variety of ways. Depending on what company you are working for they may provide the data for you, if not you will most likely need to web scrape, use an API, or be familiar with SQL. Once obtaining the data, it is important to take a look at what you have aquired and become familiar with your dataset. Some helpful strategies to use are:

'''df.head()''' - Provides first five rows of data frame.

'''df.info()''' - Shows if there are any missing entries within the columns, identifies data type, and provides number of columns.

'''df.describe()''' - Gives count, mean, std, min, 25%, 50%, 75%, and max per column.

# S - Scrub Data
Scrubbing data is one of the most time consuming aspects of a data scientists career. However it is cruical to get the data into a format that is easier to use. Usually whatever data you obtain there will be something missing or wrong with it. Common items to look out for are Null values, abnormal numbers or symbols, or data types that need to be converted. When identifying the Nulls it is esential to decide how you are going to handle them. Code that is commonly used for handling Null values is listed below:

'''df.isna().sum()''' - Allows you to see the quantity of null values in your data frame per column.

'''df.unique()''' - Allows you to see the unique items per column.

'''df.nunique()''' - Totals the number of unique items for you.

'''df.fillna() or df.replace()''' - Are great tools to filling or replacing your nulls with something else. 

'''df.drop()''' - If you would like to drop an entire row or column for excessive null values. 

To switch data type:

'''df.col = df.col.astype('new_data_type')'''

Other items to look for while scrubbing the data are categorical variables (sometimes this is done within the exploration step). 

'''cat_cols = df.select_dtypes('object').columns''' - identifies any categoricals listed as an object. You will have to get familiar with your dataset to see if any categoricals are listed as numerical columns; common examples of these would be zipcode, age group, education level.

Then check for multicollinearity:

1. Chose columns to check. Dropping whatever the dependent value is. '''data = df.iloc[:, 1:20]
2. '''data.corr()''' 
3. Take a look at correlation over .75 '''abs(data.corr()0 > .75'''
4. '''df1 = data.corr().abs().stack().reset_index().sort_values(0, ascending=False)
df1['pairs'] = list(zip(df1.level_0, df1.level_1))
df1.set_index(['pairs'], inplace=True)
df1.drop(columns=['level_1', 'level_0'], inplace=True)
df1.columns = ['cc']
df1.drop_duplicates(inplace=True)'''
5. Identify pairs with a correlation over .75 '''df1[(df1.cc>.75) & df1.cc<1)]'''
6. Choose what you would like to drop or keep.




and finally normalize the data set:



# Explore

# Model

# N = Interpret
