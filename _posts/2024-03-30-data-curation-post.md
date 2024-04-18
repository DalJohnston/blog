---
layout: post
title:  "Smash Ultimate Web Scraping"
author: Dallin Johnston
description: Using basic web scraping to find out which Super Smash Bros. Ultimate fighters are the best.   
image: "/assets/smashimages/ssbu1.webp"
---


## My Motivation

For a long time, I have greatly enjoyed playing the popular party fighting game “Super Smash Bros.”  While marketed towards casual players, this fighting game has an absurdly intense competitive scene with some even making it their life’s mission to become the very best.  As such, there exists within the game’s community a perpetual debate about who the best players are, what the best strategies are, and, especially, what fighting characters you need to use to be able to win.

![Figure]({{site.url}}/{{site.baseurl}}/assets/images/ssbu.jpg)

The newest game in the Smash franchise, “Super Smash Bros. Ultimate,” boasts a record-breaking roster of 89 playable characters, so the debate about which ones are the best has been difficult to settle.  There is a lot of personal nuance and opinion involved in character preference.  

Even so, definitive tier lists, or character ranking sheets, have been established based off of overall player performance in major tournament settings using certain characters.

![Figure]({{site.url}}/{{site.baseurl}}/assets/images/tierlist.png)

These tier lists are widely agreed upon, but they are poorly understood.  There are a plethora of videos on YouTube that attempt to explain these tier lists and why some characters are just built better than others, and then there are even more videos that take opposing views.  It can be confusing to say the least. 
Being both a burgeoning data scientist and an avid player of this game, I decided to web scrape and then compare available tier list and character data with a goal to identify what aspects really correlate with a character ranking in a higher tier. 

---
---



## Data Collection

To accomplish my goals, I used publicly available character data found at this [website](https://www.unitstatistics.com/ssbu/).  Every single in-game aspect that is shared among all characters was included in this data, from tier and relative weight to airborne acceleration values, and I used python packages such as beautifulsoup, pandas, and seaborn to read in and analyze the data.  Some code snippets along with a more comprehensive list of the packages that I used can be seen below.


![Figure]({{site.url}}/{{site.baseurl}}/assets/images/packages.png)


With BeautifulSoup, scraping this data was a fairly straightforward process. All it required was creating a simple html match function to identify the rows in the dataset, which were listed in the html as “tr,” and then looping through those rows to scrape the data into a group of lists that represent our columns.


![Figure]({{site.url}}/{{site.baseurl}}/assets/images/bsoup.png)
![Figure]({{site.url}}/{{site.baseurl}}/assets/images/rowfxn.png)
![Figure]({{site.url}}/{{site.baseurl}}/assets/images/htmlc.png)


Once that was done, I just had to convert the newly populated data lists from a dictionary to a pandas dataframe for ease of use.


![Figure]({{site.url}}/{{site.baseurl}}/assets/images/dtodf.png)


One lesson I learned during this conversion process is that it’s very important to make sure that all of your number data are actually formatted as number values before you begin analysis. 

It’s also important to consider how to handle any missing values.  Fortunately, this data included very few missing values, and since most of these values were publicly available elsewhere, I entered most of them by hand. 


![Figure]({{site.url}}/{{site.baseurl}}/assets/images/numna.png)

---
---



## DLC

Even with so many columns in the initial data set, there was one more thing that I was curious to analyze, and to do that I added one more variable.  
Since the release of Super Smash Bros. Ultimate in 2018, quite a few additional fighters have been added to the game to make the roster as big as it is today.  However, these fighters were included as paid DLC, or downloadable content.  

In other words, to get the extra fighters, your wallet needs to step into the ring.  Most consider Smash Ultimate to be a competitively balanced game, even with the extra fighters, but still, there has been a lot of debate as to whether these DLC characters are “stronger” so that loyal customers feel like they are getting their money’s worth.

![Figure]({{site.url}}/{{site.baseurl}}/assets/images/dlc.webp)

As both a starving and naturally competitive college student, I have been personally and persistently perturbed by this idea, because the last thing I want is to lose a game of skill consistently to people whose main skill is unholstering their credit card. As such, I created an extra dummy variable column called ‘DLC,’ and I assigned all paid DLC characters a 1 value and everybody else a 0.

![Figure]({{site.url}}/{{site.baseurl}}/assets/images/dlccol.png)

---
---



## Regression Analysis

To finally get a statistically founded answer as to whether or not DLC makes a difference, I decided to conduct an OLS multiple regression analysis in Python comparing other values in the data set to tier level. 
I will briefly mention that before running the analysis in Python, I used R as an added statistical measure to eliminate insignificant variables and also to check my regression model assumptions. The significant variables in my final model were DLC, max air acceleration, initial dash speed, and dash frames.

![Figure]({{site.url}}/{{site.baseurl}}/assets/images/regcode.png)
![Figure]({{site.url}}/{{site.baseurl}}/assets/images/regression.png)


All of the significant (p-value < 0.05) numerical variables in the final model were related to certain aspects of movement speed.  Maximum air acceleration just refers to how fast a character can reach a top speed in midair, which can be important for a player continuing their attack combo or escaping an opponent’s combo.  Initial dash speed and dash frames have to do with the speed and delay, respectively, of a character’s ground movement, and they are crucial to a common competitive movement style called [dash dancing](https://www.youtube.com/watch?v=mmwfe6gOTUA).

In English, it seems that the better characters in Smash Ultimate actually tend to be the quicker characters with more versatile movement options.
That is, until we come to DLC, with was the most significant variable here.  Indeed, with a p-value of 0.001 we sadly reject the hypothesis that DLC fighters are equally balanced and can unfortunately claim that Super Smash Bros. Ultimate is technically a pay-to-win game.

![Figure]({{site.url}}/{{site.baseurl}}/assets/images/money.jpg)

---
---



## Conclusion

In summary, basic web scraping coupled with just a little bit of statistical analysis can help us to end the tier list debate and determine that the best characters in Super Smash Bros. Ultimate are not just the characters that can move around a little bit better than the others; they’re the characters that you pay extra money for.  

I don’t think I’ll ever look at Smash Ultimate the same again.  Will I open my mind and my wallet so that I can win?  No way.  Will I use my newfound knowledge as a new excuse for whenever I lose? Absolutely.

The nice thing about a data set like this is that there are still a lot more variables that we can look at and compare with some further exploratory data analysis and graphing, but as for right now, I encourage all of us to keep using BeautifulSoup to scrape other publicly available data to explore all kinds of questions and topics, because with a little bit of data science magic, those questions can find all kinds of answers.

