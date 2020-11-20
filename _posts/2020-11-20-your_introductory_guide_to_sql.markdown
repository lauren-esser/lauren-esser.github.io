---
layout: post
title:      "Your Introductory Guide to SQL "
date:       2020-11-20 13:29:29 -0500
permalink:  your_introductory_guide_to_sql
---


While conducting a job search for "Data Scientist" or "Data Analyst" three letters often pop up in the job description section. These three letters are **SQL** also known as Structured Query Language. This is a process that is used to extract and organize data that is stored in a relational database. When hearing the term relational database think of one or more data tables what share common columns. For example, below we have two tables "stocks" and "news" which contain a similar column of date. 

<img src="https://docs.google.com/drawings/d/e/2PACX-1vSjnY-NcGuYYSCNhnfkMtCjDNC2lz1H8AF6FIiO2Qsxe1FENZX9h9TWRi0gSzVkzC48OYwAoPJakcj9/pub?w=351&amp;h=195">


<img src="https://docs.google.com/drawings/d/e/2PACX-1vRTtTxgqWafSiPUYgxGYbv3a-zoUuYI0WNvJAKwtIXqPFkf_ze0LfL3Q1omX1faUxTtGZrA4vzfVqhW/pub?w=436&amp;h=191">

Here are the steps to take to merge these to tables together using pandas SQL:
1. Install pandassql on your machine

```pip install pandasql```

2. Import pandasql

``` from pandasql import sqldf```

3. Create ```pysqldf = lambda q: sqldf(q, globals())```

4. q = ```'''SELECT s.date, s.movement, n.headline, s.Price, s.daily_change```
            ```FROM stocks s```
						```JOIN news n```
						```ON n.date = s.date:'''```
								 
		```df = pysqldf(q)```
		```df.head()```
		
		**End Product:**
	
	<img src="https://docs.google.com/drawings/d/e/2PACX-1vQz72aEXPDu00vEvD0SRM2R8zVwJAwnqxvLfj3DVEXihh3um79JagQ5fIdPiajT0St9GULAsmvkkhEA/pub?w=693&amp;h=193">
	
	### So what does that even mean?