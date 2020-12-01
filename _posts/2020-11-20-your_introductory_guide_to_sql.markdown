---
layout: post
title:      "Your Introductory Guide to Pandas SQL "
date:       2020-11-20 13:29:29 -0500
permalink:  your_introductory_guide_to_sql
---

<img src = "https://img.favpng.com/11/4/14/microsoft-sql-server-computer-icons-oracle-corporation-oracle-database-png-favpng-k4KjYieuYpSdy2bxiud63NBP2.jpg">

While conducting a job search for "Data Scientist" or "Data Analyst" three letters often pop up in the job description section. These three letters are **SQL** also known as Structured Query Language. This is a process that is used to extract and organize data that is stored in a relational database. When hearing the term relational database think of one or more data tables that share common columns. For example, below we have two tables "stocks" and "news" which contain a similar column of date. 

<img src="https://docs.google.com/drawings/d/e/2PACX-1vSjnY-NcGuYYSCNhnfkMtCjDNC2lz1H8AF6FIiO2Qsxe1FENZX9h9TWRi0gSzVkzC48OYwAoPJakcj9/pub?w=351&amp;h=195">


<img src="https://docs.google.com/drawings/d/e/2PACX-1vRTtTxgqWafSiPUYgxGYbv3a-zoUuYI0WNvJAKwtIXqPFkf_ze0LfL3Q1omX1faUxTtGZrA4vzfVqhW/pub?w=436&amp;h=191">

Here are the steps we take to join these to tables together using pandas SQL:

Step 1. **Install pandassql on your machine.** pandasql is a library that allows users to query DataFrames using SQL style syntax within pandas.

`pip install pandasql`

Step 2. **Import pandasql**

`from pandasql import sqldf`

Step 3. **Create** `pysqldf = lambda q: sqldf(q, globals())` This allows for quicker and easier queries. 

Step 4. **Call the data you would like to join**

```
q = '''SELECT s.date, s.movement, n.headline, s.Price, s.daily_change       
      FROM stocks s					
      JOIN news n 					
     ON n.date = s.date:'''  
								 
df = pysqldf(q)	
df.head()
```
		
Step 5: **Final Product:**
	
<img src="https://docs.google.com/drawings/d/e/2PACX-1vQz72aEXPDu00vEvD0SRM2R8zVwJAwnqxvLfj3DVEXihh3um79JagQ5fIdPiajT0St9GULAsmvkkhEA/pub?w=693&amp;h=193">
	
## So what did we just do?

Shown below is the basic outline of a SQL query:


```
q= '''SELECT t.col1, t.col2, t.col3, o.col4, o.col5 
FROM table t 
JOIN othertable o 
ON  t.records = o.records;'''
```

'---'				
### '''Quotation Marks '''

You may notice that both queries above start and end with three quotation marks. This allows us to use multiple lines to complete a query. 

'---'				
### SELECT ___ FROM:

Select chooses which columns will be joined into the new dataframe. There are three different strategies for choosing these columns. 

**ONE:** If you were to start your query with ```'''SELECT *  FROM``` this would select every single column from both dataframes to join together. 

**TWO**: Another method would be to start your query with ```'''SELECT col1, col2, col3, col4 FROM```. Here you would fill in the column names you have in the spaces for col1, col2, etc. The issue with this is that some data tables will have columns with the same title although they may not carry the same information. To solve for this you would follow step three.

**THREE**: Step three is what is shown in the basic outline example. After ```FROM table``` I wrote a t, this is used as an abbreviation to indicate anything with a t in front of it is from "table". Therefore in our first example date, movement, price, and daily_change are all from the stocks dataframe because they have an s in front of their name. Where as othertable has an o behind it, so anything with an o in front of it means it comes from othertable.

'---'				
### JOIN

Join is a section we could spend a LOT of time on. There are different types of joins including inner, left, right, outer, One-to-One, One-to-Many that I encourage you to look up on your own. For now we will simply cover that join allows us to select which table we are joining together with our original. As shown above we joined othertable with table.


'---'				
### ON

On is used to select the columns where the tables will be joined. Often times two tables share similar items, but have different column names. An example could be CustomerName in table and ClientName in othertable, both of these columns have the same information therefore we can use these columns to join our tables.

```
'''SELECT * 
FROM table t
JOIN othertable o
ON t.CustomerName = o.ClientName;'''
```

'---'				
### USING

Using is a way to join two tables that have identical column names.  From my original example 
```
q= '''SELECT t.col1, t.col2, t.col3, o.col4, o.col5 
FROM table t 
JOIN othertable o 
ON  t.records = o.records;'''
```
I could have written this much simpler. Since the records column is present in both table and othertable I could have used USING instead of ON. See below:
```
q= '''SELECT t.col1, t.col2, t.col3, o.col4, o.col5 
FROM table t 
JOIN othertable o 
USING(records);'''
```
This will develop the same exact table as the previous code selecting columns 1-5 from both tables. 

'---'				

### WHERE


The ```WHERE``` clause filters the query results by a specific condition. Where is very useful if you are grabbing information from one database. If I had a dataframe of all of the stocks I could ```SELECT * FROM stocks WHERE stock_name = S&P500```. This would grab any stock information labeled S&P500 for the creation of the dataframe. 

'---'				
### ORDER BY

ORDER BY is a tool that aids in organization. When pulling results ORDER BY allows you to filter results by a specific feature/column. Perhaps I wanted to order my stocks by price, therefore my query would look like this:

```'''SELECT * FROM stocks WHERE stock_name = S&P500 ORDER BY price DESC;'''``` 

This would return the S&P500 stocks in descending price order. The default for ORDER BY is ascending therefore if you wanted an ascending list you could just drop the DESC from the example above. 

'---'				
### GROUP BY

Perhaps you wanted to group your dataframe into specific categories, this is where GROUP BY would come into play. Keeping with our example of the S&P500 lets say we wanted to see how mnay Mondays we have stock information for. To do this we would ```'''SELECT price, day, COUNT day FROM stocks GROUP BY day;'''``` 

'---'				
### LIMIT

Limit allows you to control how many results you receive. Perhaps the full dataframe would be thousands of rows and you only want 200 rows. To limit just add ```LIMIT 200``` to the end of your query. 

'---'				

### BETWEEN

Perhaps you want a list of dates where the S&P500 was between $60 and $70 a share. To find this you can use the between function. ```'''SELECT price FROM stocks WHERE price BETWEEN 60 AND 70;'''```

'---'				

### NULL
Sometimes we may want to see how many nulls we have in a dataframe. To do this we can ```'''SELECT * FROM stocks WHERE price IS null;'''``` This will return any row in which price for the S&P500 is null. 


'---'				

There is so much more one can do when you really dive into SQL. In this blog post we covered the basics to get yours started. To dive deeper I encourage you to try this out on your own and for additional information start by looking up Aggregate Functions and the different types of joins. I hope you enjoyed your first step into understanding SQL.


