---
layout: post
title:      "How to Use NewsApi"
date:       2020-11-09 14:13:00 -0500
permalink:  how_to_use_newsapi
---


The news is where we go to for up to date information going on around us. Therefore, by simply skimming over titles we can have a decent prediction about what is happening in the world around us. Within this blog post I will teach you how to connect with NewsApi in order to grab titles for your own personal use. 

## Step 1: Go to newsapi.org
Once here you will want to click on the blue rectangle in the upper right hand corner that says "Get API key".

<img src="https://docs.google.com/drawings/d/e/2PACX-1vRQdPJuEtjDJYDgxZx71GkA0_BajOo38RJzxnla1eLEgJJZdtv8a8OYQEVqJfBE16UYeC1YOFBJJxof/pub?w=848&amp;h=495">

Once selected you will be led to a screen where you need to register for an API key. Fill out the required information, confirm you are in fact a human, agreed to the terms, and hit submit.

<img src="https://docs.google.com/drawings/d/e/2PACX-1vRRzoI4XM79haPk2U7teEI-Y0Jk8AHIuuPe9ZXo1x-oqqEhfAY-w6JSFMYkE2QUTE2uL0KVSHNehKWf/pub?w=854&amp;h=690">

<img src="https://docs.google.com/drawings/d/e/2PACX-1vT_BBBt5R3Tkd-0lM71fYSoNukLFrA4CY2TvljePsQtQu6zi5JFuR8IZecf3Q2M9FJhPzKv_vtJJFXH/pub?w=876&amp;h=398">

Congrats! Your registration is now complete and you can begin connecting with NewsAPI.org

## Step 2: Installing/Connecting Newsapi
In your jupyter notebook you need to fetch the newsapi library. 
1. Type  ``` pip install newsapi-python ``` in your cell and run it in order to first install newsapi.
2. Run ```from newspi import NewsApiClient ``` to import the needed library. 
3. Connect to newsapi using your key ```newsapi = NewsApiClient(api_key = 'YOUR_API_KEY_GOES_HERE')```


## Step 3: Identify Your Endpoint
NewsApi has two main endpoints and one minor endpoint avilable (farther information can be found [here](https://newsapi.org/docs/endpoints).) The two main points are Top headlines and Everything while the minor endpoint is Sources, all three will be covered in detail below.

### Top Headlines
We will look at **Top headlines** first. You will want to use Top headlines for up to date information on breaking news and headlines. When accessing information there are many built in parameters that are very helpful to use, I will cover a couple of these below:

- *country*: If you are using the newspaper headlines to make predictions in America you are not going to want to receive headlines in Britian or France. This parameter allows you to use the 2-letter ISO code of the country you desire to receive information on. Therefore if you wanted news articles only from America you would add ```country - 'us'```


- *category*: Allows you to select which category you would like to receive headlines from. If I am creating a model based on sports headlines I could enter in ```category = 'sports```. Other categories available include business, entertainment, general, health, science, and technology. 


- *sources*: If choosing sources it is important to note that this parameter cannot be used with country or category. Sources allows you to select which news source or blog you would like to take information from. 

Example code:
```
news_headlines = newsapi.get_top_headlines(language = 'en', country = 'us', 
                                           category = 'sports')
news_titles = []
for article in news_headlines['articles']:
  news_titles.append(article['title'])
  print(article['title'])
	```


---


### Everything
The second main endpoint avilable is **Everything**. This endpoint is exactly as it sounds, it has the potential to return everything to you. It searches through millions of artcles from current news posts and blogs to older, smaller articles as well. Everything should be used for discovery and analysis of newstitles. Everything has additional parameters to help specify your search.

- *q or qinTitle*: q is used to search for keywords or phrases within the article title and body. For an exact match place quotes around your search or to find specific key words you can use the AND / OR / Not keywords. Ex: stocks AND bonds NOT mutual funds. qinTitle is the same a q except that the search will only take place in the article title.

- *sources*: Same as Top headlines above.

- *from or to*: Since you are pulling everything from or to allows you to set specific dates for finding your information. from sets the oldest article date allowed and to sets the newest article allowed. The default format is YYYY-MM-DD.

- *sortBy*: Sort by allows the article titles to be sorted by different qualifiers. These include: relevancy, popularity, and publishedAt.

Example code:
```
date = '09/28/2009'
date1 = '11/05/2020'
news_headlines_everything = newsapi.get_everything('&from = (date)', '&to = (date1)', language = 'en')
                                                
news_titles_everything = []
for article in news_headlines_everything['articles']:
  news_titles_everything.append(article['title'])
  print(article['title'])
	```
	
	
---
	
	
### Sources
Used to retrieve a small subset of the publishers that NewsApi indexes from. This is a useful endpoint to use because it allows you to see which publishers are available on the API. Just like the above endpoints category, language, and country are the parameters that can be used.
	
Example code: 
	
```
news_sources = newsapi.get_sources()
news_sourcecs_list = []
for sources in news_sources['sources']:
  news_sourcecs_list.append(sources['name'])
  print(source['name'])
	```

**Resources**:
https://newsapi.org/docs/get-started
