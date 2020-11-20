---
layout: post
title:      "Your Introductory Guide to Pandas SQL "
date:       2020-11-20 13:29:29 -0500
permalink:  your_introductory_guide_to_sql
---


While conducting a job search for "Data Scientist" or "Data Analyst" three letters often pop up in the job description section. These three letters are **SQL** also known as Structured Query Language. This is a process that is used to extract and organize data that is stored in a relational database. When hearing the term relational database think of one or more data tables what share common columns. For example, below we have two tables "stocks" and "news" which contain a similar column of date. 

<img src="https://docs.google.com/drawings/d/e/2PACX-1vSjnY-NcGuYYSCNhnfkMtCjDNC2lz1H8AF6FIiO2Qsxe1FENZX9h9TWRi0gSzVkzC48OYwAoPJakcj9/pub?w=351&amp;h=195">


<img src="https://docs.google.com/drawings/d/e/2PACX-1vRTtTxgqWafSiPUYgxGYbv3a-zoUuYI0WNvJAKwtIXqPFkf_ze0LfL3Q1omX1faUxTtGZrA4vzfVqhW/pub?w=436&amp;h=191">

Here are the steps to take to merge these to tables together using pandas SQL:

Step 1. **Install pandassql on your machine.** pandasql is a library that allows users query DataFrames using SQL style syntax within pandas.

```pip install pandasql```

Step 2. **Import pandasql**

``` from pandasql import sqldf```

Step 3. **Create** ```pysqldf = lambda q: sqldf(q, globals())``` This allows for quicker and easier queries. 

Step 4. 
**q =** 

```'''SELECT s.date, s.movement, n.headline, s.Price, s.daily_change
           
					            FROM stocks s
						
					            JOIN news n 
						
						          ON n.date = s.date:'''  
								 
	 df = pysqldf(q)
		
		df.head()```
		
Step 5: **Final Product:**
	
<img src="https://docs.google.com/drawings/d/e/2PACX-1vQz72aEXPDu00vEvD0SRM2R8zVwJAwnqxvLfj3DVEXihh3um79JagQ5fIdPiajT0St9GULAsmvkkhEA/pub?w=693&amp;h=193">
	
### So what does that even mean?

Shown below is the basic outline of a SQL query:

q = 
```'''SELECT t.col1, t.col2, t.col3, o.col4, o.col5 

FROM table t 

JOIN othertable o 

ON  t.records = o.records;'''```
				
## '''Quotation Marks '''

You may notice that both queries above start and end with three quotation marks. This allows the us to use multiple lines to complete a query. 

## SELECT:

Select chooses which columns will be merged into the new dataframe. There are three different strategies for choosing these columns. 

**ONE:** If you were to write ```'''SELECT *``` this would mean to select every single column from both dataframes to merge. 

**TWO**: Another method would be to write ```'''SELECT col1, col2, col3, col4``` and to simply write out the column names here. The issue with this is that some data tables will have columns with the same title although they may not carry the same information. To solve for this you would follow step three.

**THREE**: Step three is what is shown above. After ```FROM table``` I wrote a t, this is used as an abbreviation to indicate anything with a t in front of it is from "table". Therefore in our first example date, movement, price, and daily_change are all from the stocks dataframe because they have an s infront of their name. 

## FROM:


## JOIN
## ON
## WHERE

The ```WHERE``` caluse filters the query results by a specific condition. Where is very useful if you are grabbing information from one database. If I had a dataframe of all of the stocks I could ```SELECT * FROM stocks WHERE stock_name = S&P500```. This would grab any stock information labeled S&P500 for the creation of the dataframe. 

## ORDER BY

## LIMIT
		 

