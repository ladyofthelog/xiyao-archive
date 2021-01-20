# Identifying the Xiyao Troll
2021-01-20 verity

## TL;DR
* **1469** Xiyao/3zun works scraped (100%)
* **953** works have at least one visible anon comment (65%)
* **377** works have at least one visible Xiyao Troll comment (26%)
* Of the **588** troll comments on those 377 works, **212** (36%) were the first comment left on a one-shot work or work chapter, and **306** (52%) were left within one hour of the first comment.
* *Including HTML tags*, the average length of a comment from the Xiyao Troll is **173 characters**

**My conclusion:** the Xiyao Troll is probably using a service like IFTTT to get push notifications from the Xiyao and 3zun tag RSS feeds. Since these comments are short, repetitive, anonymous, and do not appear to target any one individual or demographic, my recommendation is that all users posting to these tags disable anonymous comments on their works. Further effort toward identifying the user or users leaving these comments is not worthwhile.

## About This Project

After several of my friends received harassing comments from the Xiyao troll, I decided that I wanted to get involved in investigating what has been going on while I had time to kill over Thanksgiving break. I worked with @superborb, who added a comments scraper to [my fork the ao3 python package](https://github.com/ladyofthelog/ao3); ~10 friends who read and coded ~5k anonymous comments for Troll / Not Troll / Other; LitMoose, who reviewed my methodology; and others who contributed fandom knowledge and data science expertise. Now that I've reached what I consider a stopping point, I'm writing up my work and archiving assets related to this investigation.

Archived on Tableau Public
* [Data Visualizations](https://public.tableau.com/profile/ladyofthelog#!/vizhome/XiyaoTrollInvestigation/XiyaoTrollOverview)

Archived on Github
* [Xiyao work metadata](https://github.com/ladyofthelog/xiyao-archive/tree/main/metadata)

Archived on Google Drive
* [Xiyao comment data set, no comment text](https://drive.google.com/file/d/1EYWbGZim5kooZ6RiqHQj-zQUFutiOtLU/view?usp=sharing)
* [Troll comment data set, with comment text](https://drive.google.com/file/d/1D05czZLomZAYCPDs--5FjSk7DMkOO4wu/view?usp=sharing)

In addition to these assets, you can find information on the package I used to scrape ao3 and sample Jupyter Notebook files if you want to try scraping yourself. All of the work I've done should be easily reproducible by someone with comparable technical skill. See Resources below for links.


## About the Xiyao Troll
The Xiyao Troll leaves a comment on almost every English language fic in the **Xiyao** (Lán Huàn | Lán Xīchén/Mèng Yáo | Jīn Guāngyáo) and **3zun** (Lán Huàn | Lán Xīchén/Mèng Yáo | Jīn Guāngyáo/Niè Míngjué) tags on [AO3](https://archiveofourown.org/), including fics in which Xiyao and 3zun are not the primary pairings. These comments are unkind, critical of the works they are left on, and include personal attacks, but there are no threats of harm to the authors of these works.

Overall, this has produced a chilling effect for many Xiyao authors who post on AO3. It's made MDZS/CQL fandom less fun for many Xiyao fans.


## Data
For prior investigations, I have collected experimental data. In this case, I decided it was most reasonable to rely entirely on observational data. I collected two types of data for this analysis:

1. **Extensive metadata from all English-language Xiyao works**, which I scraped and cleaned in late November and again in late December. I ended up with 1,469 works in my data set.
2. **Timestamps and content of AO3 comments on those works**. I scraped the comments of those 1,469 works and got 122,487 total comments. Of those, 588 were comments from the Xiyao Troll that hadn't been deleted (or never let out of the moderation queue).

![Who Would Win Meme - Comments Script or Fic With 4019 Comments](/images/image3.png)

Of these 1469 works, 953 (65%) have anon comments; there were no visible or remaining anon comments on the remaining 516 (35%). 377 works (26% of all scraped works) had comments from the troll still visible when I scraped comments on December 21st. In total, there were 588 comments from the troll on those 377 works; the troll left multiple comments on several multichapter works.

The charts below that deal with comment data will have slightly different numbers from my "raw" anon comment data; I treated comments signed by "wangxian+fan" and "wangxian fan" as Not Anon. (We love you, wangxian+fan...)

![Bar Chart - Overview of Comments by User Type](/images/image1.png)
*Overall commenting patterns broken down by user type - comments from users with accounts (117,471), anon comments from people who are not the troll (4,428), and anon comments from the Xiyao Troll (588).*


## Works Which Have Received Troll Comments
The Xiyao Troll is quite comprehensive in commenting; if a work is tagged Xiyao or 3zun, regardless of whether or not they're the first or tenth pairing, that work may receive a troll comment. Here's the first pairing tagged (I've referred to this as "Prime Relationship" in my data) on all of the works in my data set with troll comments:

![Primary Relationship Tag on Works with Troll Comments](/images/image4.png)

*For works that had a comment from the Xiyao Troll, this graph shows the count of works with each relationship as first-tagged. Relationships with a count lower than 3 are hidden.*
As you can see above, 66% of the works that have a visible troll comment feature Xiyao, 3zun, or a 3-zun adjacent ship as their first-tagged pairing, while 33% feature Wangxian or other pairings. While we don't know how representative this is of the total number and span of troll comments, of course, this distribution of primary relationships is very close to that for the broader set of Xiyao works.


## Troll Comment Timeline
![Screenshot of Google Sheet showing Troll Comments and Dates](/images/image5.png)

The first comment my qual coding team felt matched the Xiyao Troll's writing pattern was left on April 12 on ["Undying" by Sabinasan](https://archiveofourown.org/works/22719904), much earlier than I've heard of the Xiyao Troll being active. The second comment, left on May 25th on ["Epistle from Gentian" by zebaoth](https://archiveofourown.org/works/23330995), seems consistent with the Xiyao Troll's style and uses "Anon" as the name. On June 6th, the string of comments about Qin Su that has been consistently identified as the Xiyao Troll kicks off, and from there on I feel relatively confident that all of the comments tagged "Is Troll" are indeed the Xiyao Troll. (Yes, I read through all of them.) 

We saw some comments that seemed to be from other trolls, including a few from the Sangcheng Troll, but the Xiyao Troll's writing style is relatively consistent. Alpheratz identified a list of keywords while coding the first batch of comments that allowed us to flag suspected comments in batch 2.


## Daily Troll Activity
Originally, I intended to do a comprehensive analysis of the troll's activity patterns. However, it became clear as I talked to more people that for the 588 comments I had scraped, there were perhaps an equal number deleted or screened. Given the incompleteness of my records, I was concerned that building a model based on troll activity would be unhelpful or misleading, especially given the scattered activity you can see below.

![Troll Activity by Hour of Day across Calendar Day](/images/image9.png)

*This graph shows hour of Xiyao Troll activity (vertical axis) plotted against calendar day (horizontal axis). Orange bars represent comments on works where Xiyao is the first-tagged work; blue bars represent comments on works where Xiyao is not.*


## Weekly Troll Activity 
As it's not possible to say how many Xiyao Troll comments have already been deleted by work authors, it's not possible to estimate the overall volume of comment activity. However, there's a lot of information about the *cadence* of the Xiyao Troll's activity still available - evidence of presence, if not level of engagement.

![Anonymous Comments on Xiyao Tag by Week](/images/image6.png)

*Number of anonymous comments by week, starting May 24th (Xiyao Troll comments are the orange line, non-troll anon comments are the green line)*
As you can see here, the Xiyao Troll has been consistently active from the end of May through the beginning of December, although the last comment I have seen from the Xiyao Troll so far was left on December 11. While I heard from one person that the Xiyao Troll went away briefly in early August, the data doesn't seem to bear that out.


## Troll Comment Latency
How long between posting a work or a chapter does it take for the troll to comment? How does this vary depending on posting time of day?

While it's possible to grab posting time of day from the RSS feed for one-shots and the latest chapter of chaptered works, chapter posting time does not persist. I decided that the best proxy for posting time was "first comment" time. Since AO3 includes information about which chapter a comment was left on in the header, it's possible to use this for both one-shots and chaptered works. 

I use the term **latency** to describe the lag in time between the first comment on a new work or chapter from any user and the first comment from the troll on that work or chapter. For works or chapters on which the first comment is from the troll, latency is zero.

Looking at comments where less than 24 hours elapsed between the first comment on a work or chapter and a troll comment (the vast majority of cases), the speed with which the Xiyao Troll has tended to comment on a work was striking. **The Xiyao Troll was the first commenter on a chapter or work for 212 of their 588 comments (36%).**

![Troll Comment Latency by Hour](/images/image2.png)

*306 of 588 comments were left within one hour of the first comment received on a work.*

I also looked at the relationship between comment latency and the hour of day a troll comment was left. Below, you can see the median and average comment latency. The median is the middle value in sorted numerical data; resistant to outliers - for example, a sleepless night of commenting shouldn't shake this number much. The average is the sum of all values divided by the count of values, so it's easily impacted by a few large or small values. 

![Median Troll Comment Latency by Hour of Day](/images/image8.png)

*The median comment latency by hour of day of troll comment time, in 24-hour time, EDT/EST. A median latency of "3.0" at 7am means that, for troll comments left at 7am, the median value for latency was 3 hours.*

The extremely low median values for comment latency reflect the quick reaction time of the troll to a new posting. Yikes.

![Average Troll Comment Latency by Hour of Day](/images/image7.png)

*The average comment latency by hour of day, in 24-hour time, EDT/EST. An average latency of "4.9" at 7am means that, for troll comments left at 7am, the average value for latency was almost 5 hours.*

Comments left at 7am EDT/EST had the longest median latency (3 hours) and third-longest average latency (5.1 hours) - but there are only 10 comments left in that hour window.


## Comment Length

![Comment Length - Bucketed by Tweet Length](/images/image10.png)

*This histogram shows troll comment character length in 240-char bins; average length was 173 characters. Character count includes HTML tags.*
The majority of the 588 troll comments I scraped are the length of a single tweet. 


## Troll Comment Content
All Xiyao Troll comments recycle the same keywords, although I don't believe these comments to have been generated by a bot. It's unclear whether the troll read (or even skimmed) most of these works. While I've seen some uncomfortable and personal comments in the anon comments we looked at, none of them fit the writing patterns of the Xiyao Troll. The Xiyao Troll doesn't appear to be focusing on any particular author or category of work. 


## Recap

* The troll is probably getting push notifications for works via RSS feed
* Their comments are essentially rude tweets
* They're not stalking anyone
* They're always anon

This is the laziest modus operandi I have ever seen from a troll. 

![Here's A Guy With Free Time](/images/image11.jpeg)

I couldn't have known these things without analyzing all the comment data, and I know for a fact that no one else has looked at latency. Still, when a friend sent me this image like, "here's the troll" I said, "oh honey, that's me, too."

**No matter how impersonal, widespread harassment produces a chilling effect on a fandom and sucks for creators, and should be stopped. The easy way to do so is to turn off anon comments if you are posting to the Xiyao tag.** This protects both you and others.


## Resources

I used a Chrome plugin (Instant Data Scraper) to scrape work URLs from the Xiyao tag, then truncated the work URLs to just the work ID and pulled more extensive metadata using the ao3 Python package. Most of my data cleaning was done in Tableau Prep.

[My fork of the AO3 package](https://github.com/ladyofthelog/ao3)
* Uses your AO3 cookie for login. 
* Actively maintained by me.

[Sample notebook using the AO3 package](https://github.com/ladyofthelog/sample-ao3-notebooks) 
