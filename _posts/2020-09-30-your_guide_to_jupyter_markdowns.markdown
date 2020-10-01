---
layout: post
title:      "Your Guide to Jupyter Markdowns"
date:       2020-09-30 16:15:08 -0400
permalink:  your_guide_to_jupyter_markdowns
---


Just because we are working with numbers and code, doesn't mean we need to have a boring Jupyter notebok. In this blog we will go over different ways to spice up your notebook and make it visually pleasing for your readers. Ready? Let's get started.

## The Basics
### Block Quotes
<img src="https://docs.google.com/drawings/d/e/2PACX-1vR_MODhPDEDue__93s90qa4GKmSBUz0ICG0skvLbWx722YGAVMKNtH3spjLJgReIEomqI-ddS5elQtB/pub?w=281&amp;h=187">

**Here's how it looks**

> This is how we create a block quote in jupyter notebook
> > If you would like a quote to be nested with your your block quote you can add one more greater than sign.
> > > Or if you REALLY wanted a nest within a nest you can add an additional greater than sign.


### Headings
There are six different options for headings. The more #'s there are the smaller the heading. See below.

<img src = ''>

**Here's how it looks**
# Header 1
## Header 2
### Header 3
#### Header 4
##### Header 5
###### Header 6


### Hyperlinks
If you would like to add a hyperlink that doesn't show the entire weblink you can format the link where you click [here](www.google.com) to access the webpage. (I just linked mine to Google). Feel free to type in whatever words you would like in place of "here" and that is what will show up in your notebook.

**Here's how you do it**

<img src =''>

### Images
Notice all of the images in my blog? Well here is how I do it! 

<img src = ' '>


**I'd say here's how it looks, but just look above!** 

### Line Breaks
You have no idea how many times I have tried to make a line break only to hit shirt+enter and see no break whatsoever. Therefore, if you need a line break in your jupyter notebook markdown make sure to hit enter *two or more times*, depending on how large you would like the break.

**Here's how it looks**
*What to do*
<img src = ''>

*What NOT to do*
<img src = ''>

### Lists
Making lists is very similar to what you would do anywhere else. 

>Here is my unordered list:
- apples
- bananas
- oranges

**Here's how it looks**
<img src = ''>

But what if I wanted to list my favorite fruits in order?

>Here is my ordered list:
1. Oranges
2. Apples
3. Bananas

**Here's how it looks**
<img src = ''>



### Lines
If you want a line break, there is no need to create the line by doing dash marks all the way across the screen simply place three dashes and hit enter. You may choose any of the following: 
---
***
___

**Here's how it looks**


### Text
**BOLD**
*Italics*
***Bold and Italized***
~~Strikethrough~~

## Unique
### Cell Background Color
### Tasks List
### Text Box Color
BLUE:

<div class='alert alert-block alert-info">
<b>Tip:</b> Use blue boxes for tipes and notes.</div>

YELLOW:
<div class="alert alert-block alert-warning">
<b>Example:</b> Use yellow boxes for examples that are not inside code cells, or use for mathematical formulas if needed. Typically also used to display warning messages.


### Text Color
### Text Font
<span style="font-family:Comic Sans MC">This is a text</span>

### Embedding your tableu
%%HTML and then paste your embed link provided from tableu prior to publishing. 

%%HTML
<div class='tableauPlaceholder' id='viz1601559908930' style='position: relative'><noscript><a href='#'><img alt=' ' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Fu&#47;FunctionalityofWaterPumpsUsingLatitudeandLongitude&#47;Sheet1&#47;1_rss.png' style='border: none' /></a></noscript><object class='tableauViz'  style='display:none;'><param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' /> <param name='embed_code_version' value='3' /> <param name='site_root' value='' /><param name='name' value='FunctionalityofWaterPumpsUsingLatitudeandLongitude&#47;Sheet1' /><param name='tabs' value='no' /><param name='toolbar' value='yes' /><param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Fu&#47;FunctionalityofWaterPumpsUsingLatitudeandLongitude&#47;Sheet1&#47;1.png' /> <param name='animate_transition' value='yes' /><param name='display_static_image' value='yes' /><param name='display_spinner' value='yes' /><param name='display_overlay' value='yes' /><param name='display_count' value='yes' /><param name='language' value='en' /><param name='filter' value='publish=yes' /></object></div>                <script type='text/javascript'>                    var divElement = document.getElementById('viz1601559908930');                    var vizElement = divElement.getElementsByTagName('object')[0];                    vizElement.style.width='100%';vizElement.style.height=(divElement.offsetWidth*0.75)+'px';                    var scriptElement = document.createElement('script');                    scriptElement.src = 'https://public.tableau.com/javascripts/api/viz_v1.js';                    vizElement.parentNode.insertBefore(scriptElement, vizElement);                </script>

