# Data Analysis-Housing Insecurity Tableau
### Tableau starter project


# The accompanying [dashboard](https://public.tableau.com/app/profile/lori.bettencourt/viz/HousingInsecurity_16649964396730/Dashboard1) can be found at my [Tableau Public](https://public.tableau.com/app/profile/lori.bettencourt) projects site.


## Personal Case Study
For over 20 years, I lived in an area where it was not generally obvious that there was any significant number of residents struggling with housing security. I would see demographics for some of my students, however, that would identify these individuals as "homeless", and this had always sparked some curiosity and compassion within me. This (and a recommendation from my good friend, Paul) led me listen to the podcast ["According to Need"](https://99percentinvisible.org/need/) by reporter Katie Mingle.  

Since listening to that podcast, I have moved to a small city where I routinely see people in the same clothes day-after-day, sleeping in the park, and gathering in groups in the same area to have some company while they pass the time. Often these people will sleep during the day. I imagine this is because it feels safer than sleeping outside at night.
There are many circumstances that can lead to homelessness - and it is not as difficult to fall into as many people think. Losing a job, having high medical bills, chronic physical or mental health issues, automobile issues (having none or having one break down), lack of a general support system, and weather-related disasters are just a few scenarios that come to mind.  

Many people in the U.S. are barely scraping by to purchase food and pay their rent. One hiccough in their fragile financial system can cause it all to collapse. Once homeless, it can be a near insurmountable task to change one's circumstances.  For someone without shelter, they may not have a place to launder their clothes or bathe. This can make interviewing for a job very challengeing. Also, applications of many kinds require an address. The obstacles can be compounding.  

So, as I am still interested in the issues surrounding housing insecurity, I decided to continue my research with this case study.

## Definitions
According to ["A Guide to Counting Unsheltered Homeless People"](https://www.hudexchange.info/sites/onecpd/assets/File/Guide-for-Counting-Unsheltered-Homeless-Persons.pdf) by the U.S. Department of Housing and Urban Development or [HUD](https://www.hud.gov/), the following definitions apply to the populations in this study.

An unsheltered homeless person resides:  
• In a place not meant for human habitation, such as cars, parks, sidewalks, abandoned
buildings (on the street). 

A sheltered homeless person resides:  
• In an emergency shelter.  
• In transitional housing or supportive housing for homeless persons who originally came from the streets or emergency shelters.  
 
## Analysis Task
Let's look specifically at housing insecurity trends from 2010 until 2016: 
1. Which 2 years had the highest and lowest homelessness percentages of the U.S. Population?
2. What are the overall trends of housing insecurity among sheltered and unsheltered homeless individuals?
3. What are the two peak years for the homelessness count in the U.S.?
4. Between which two years did homelessness change the most drastically in the U.S.?
5. Which states have the highest overall count of homeless individuals in the latest year of this study, 2016? (not considering population here)  


# Response to Analysis Task

1. Of the 7 years studied (2010-2016), 2010 had the highest percentage of homeless individuals in the United States: 0.204%.  
2011 has the next highest at 0.198%.   
The percentage of homeless individuals fell consistently from 2010 to 2016. In 2016 the homeless population was 0.168% and in 2015 it was 0.174%.
2.  Throughout all years, when the values from all states are considered, the percentage of sheltered homeless individuals was greater than unsheltered. The percentage of sheltered homeless individuals become consistently more than twice that of unshelterd in 2013.
3.  The year 2010 saw the highest homeless count (630,806) with 2011 next (618,611). The total number of homeless individuals fell consistently each year of this study.
4. Homelessness had the greatest change between 2012 and 2013 when it fell from 616,556 to 584,483 and from 0.196% to 0.185%.
5.  California, New York, and Florida have the highest number of homeless individuals each of the 7 years. In 2016, their homeless populations were:  
California: 118,142  
New York: 86,352  
Florida: 33,559   
In New York, the number of sheltered homeless individuals far outnumber the unsheltered every year.
California consistently has more unsheltered individuals than sheltered.
Florida had more unsheltered until 2015, when the sheltered homeless population surpassed it.


## Suggestions For Future Analysis  
1. Add recent years of housing insecurity data and census population data to continue this study.
2. May have to pivot and start with a new dashboard for additional years as data found in newer sources include more demographic information and I may want to include such things as gender, age, LGBTQ+ identifiers, etc.
3. Focus on places that have been hit by natural disasters including weather-related events.
4. Research if it is possible to see how COVID-19 affected homelessness. Did more people become homeless due to lack of work during quarntine? Did we lose people in the homeless community because they had lack of resources (food, healthcare, media warnings, etc.)?
5. Determine if the trends found here continue during the next years.


## Data Preparation
Data preparation documentation to date can be found in [DataTransformationAndCleaning.md](/Data/DataTransformationAndCleaning.md)

## Sales Dashboard Visualizations
Explainations of visualizations can be reviewed at [Visualizations.md](/Visualizations.md)

## SQL Checks  
Queries against the dashboard reports can be reviewed at [SQLChecks.txt](/SQLChecks.txt)

## Resources
[According to Need Podcast](https://99percentinvisible.org/need/)  
["A Guide to Counting Unsheltered Homeless People"](https://www.hudexchange.info/sites/onecpd/assets/File/Guide-for-Counting-Unsheltered-Homeless-Persons.pdf)  
[HUD](https://www.hud.gov/)  
[Kaggle](https://www.kaggle.com/)
[2007-2016-Homelessness-USA.csv](https://www.kaggle.com/datasets/adamschroeder/homelessness?select=2007-2016-Homelessnewss-USA.csv)  
[Population-by-state.csv](https://www.kaggle.com/datasets/adamschroeder/homelessness?select=Population-by-state.csv)   
[National Alliance to End Homelessness - CoC](https://endhomelessness.org/resource/what-is-a-continuum-of-care/)  
[National Alliance to End Homelessness - Stats](https://endhomelessness.org/homelessness-in-america/homelessness-statistics/state-of-homelessness/)  
[Sreadsheet Guru's State Abbreviations](https://www.thespreadsheetguru.com/blog/list-united-states-capitals-abbreviations)  
[Learn Tableau Basic Calculations (Calculated Fields) in Tableau (with 10+ examples) | Part 1](https://www.youtube.com/watch?v=QimVQl5AoYM&list=PLdeA_5rmA1Ecl1MnWUsyuV3IjiPSOqbU7&index=8)  
[Tableau Tutorial - Parameters - Complete Introduction - with 10 use cases step-by-step for beginners](https://www.youtube.com/watch?v=0Uar_D57QhU&list=PLdeA_5rmA1Ecl1MnWUsyuV3IjiPSOqbU7&index=9&t=933s)  
