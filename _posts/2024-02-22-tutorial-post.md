---
layout: post
title:  "Basic Data Science and Advertising"
author: Dallin Johnston
description: How advertisers rely on simple data science for their most important day of the year.   
image: "/assets/images/lombardi.avif"
---

## Why Advertising?  

Data science is such a broad and complicated field, and I, as an Advertising major with a second major in Applied Statistics, sometimes feel like an impostor in this world.  However, as I have tried to get my feet wet in collecting and manipulating data, I have realized that we need more impostors like me.  We need more people who are willing to see that there is a vast wealth of data available for people of all professions and of all fields of study to get their hands on and to use for their benefit.  With that in mind, here is what I, an inexperienced data science derelict, have learned from just a little bit of research and looking at some advertising-related data. 


A lot of the data that we as advertisers are interested in are data that pertain to our target market: who am I trying to reach with this commercial?  Knowing your audience, even if it’s just a little bit, is crucial.  If I was told to read a story to a classroom full of kindergartners, I probably wouldn’t pull out a dusty volume by Tolstoy.  For advertisers, one of the biggest audiences of all comes around once a year on Superbowl Sunday, and this year, the viewership for the game was the biggest that it had ever been (superbowl largest nfl.com).  I looked into what predictive data was available for the Superbowl audience, and one of the biggest datasets I found was a basic age group survey asking people how likely they were to be watching the Superbowl.  Just like the kindergarten example, age group alone can be a useful demographic in determining what kind of advertising messages might be most effective.

---
---

## Superbowl Age Data and Michael CeraVe

To see what age group was most commonly predicted to be watching the Superbowl, I downloaded the dataset and ran just one or two basic pandas commands in Python to better compare the numbers I was interested in.  

![Figure]({{site.url}}/{{site.baseurl}}/assets/images/agedata.png)

Here, all I am doing is adding up the percentages in the rows for those who reported that they would “definitely” or “probably” watch Superbowl LVIII.  From this preliminary data, we can see that the most anticipated viewership group by age of those surveyed for the 2024 Superbowl was those ages 30-44, with a 63% margin reporting that they would “definitely” or at least “probably” be watching the Superbowl.  So, just by knowing that you have a lot of 30 to 44-year-old millennials watching the broadcast, how do you maximize the effectiveness of your ad? This year, CeraVe lotion showed us exactly how.  

![Figure]({{site.url}}/{{site.baseurl}}/assets/images/michael-cerave.webp)

Michael Cera is a Hollywood comedy actor who had the best years of his career from 2007-2013, and many of his films embody what many would consider to be peak “millennial humor.”  By casting Michael Cera in their commercial, CeraVe, who are just a regular competing lotion brand, were able to weld the eccentric millennial humor (and the last name) of Michael Cera with their brand.  By doing this, they imprinted a lasting image in the minds of many millennial viewers and set themselves a notch above their competitors.  While there is certainly a lot more data analysis involved in these expensive creative decisions, this just goes to show how just a tidbit of audience data in the advertising world can go a long way.

---
---

## Superbowl Gender Data and Storytelling

Another similar superbowl viewership prediction dataset that I looked at had to do with another useful audience criteria for advertisers: gender.  It should be noted that while this data was already in a form that could be read and understood before I downloaded it, I thought that it was good anyway to download it, read it into python, and try manipulating it a little on my own for some good practice.  After all, if most data was this nice-looking then the world would have no need for data scientists (insert screenshot).

![Figure]({{site.url}}/{{site.baseurl}}/assets/images/genderdata.png)

Like before, I’m just finding the percentage of women surveyed who would very likely be watching the Superbowl.  To do this, I ran a couple of basic lines of code to the percentage total for the “definitely” watching and the “probably” watching categories for the women’s column.  As seen in the picture above, 53% of women surveyed reported that they would likely be watching the Superbowl.  While this might not seem significant at first glance, we might need to reconsider that the traditional audience for the Superbowl, and for the NFL in general, has been predominantly male for years.  What isn’t important is that I was able to use a couple of pandas commands to find a number that I probably could have added up in my head.  What is important, however, is understanding what that number means, and what interesting story it bears witness to.


### Riding the Taylor Swift Wave

Any active user of social media, or really the internet in general, over the last year or so could tell you that Taylor Swift, an influential pop artist, has seen a massive explosion in popularity, and wherever she goes, she draws a lot of attention from a vast young female audience.  The NFL experienced this first-hand when Swift started publicly dating Travis Kelce, a receiver for the Kansas City Chiefs.  When the Chiefs made it to the Superbowl this year, there was little doubt that Taylor Swift’s large female following would be joining the audience.

![Figure]({{site.url}}/{{site.baseurl}}/assets/images/taylor-swift-nfl.webp)

Knowing this, and likely going off of similar data, Dove toiletries manufactured a short but poignant commercial targeted at young girls and their parents.  In front of what they knew what would be one of the largest young female audiences that television had ever seen, the ad solemnly states that most girls quit sports by the age of 14.  Why?  They have a poor body image.  In one fell swoop, Dove very effectively tells the parents of a horde of young girls who idolize Taylor Swift for being a pop princess that Dove, and not Taylor Swift, can help them to feel comfortable in their own skin.  From just a couple of data science maneuvers and a little bit of critical thinking, Dove ensured that the next time a loving parent of a young girl is meandering down the soap aisle and sees that Dove logo, they will not forget the strong message that for just a brief moment pulled at their heartstrings.

![Figure]({{site.url}}/{{site.baseurl}}/assets/images/dove-ad.png)


## Conclusion

Again, I’m no data science expert, and at first I was a little scared to dive straight in looking for data, but from just a little bit of digging, research, and light data manipulation, I have grown to better understand the true power of data for brands in preparing for the greatest advertising opportunity of the year. 

But that’s just for advertising! Whatever you may be studying, or whatever interests you, there is all kinds of data available online to help you gain a deeper understanding of it, and there are resources available to help you learn how to read that data.  Data science is relevant to so many fields. Find your motivation, find your passion, and then find your data!

