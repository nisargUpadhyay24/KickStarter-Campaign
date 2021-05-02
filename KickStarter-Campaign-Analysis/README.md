# KICKSTARTER CAMPAIGN ANALYSIS

## About Kickstarter Campaigns
The kickstarter campaigns are used when creators/visionaries share their vision with a wider community and want this community to fund their vision/product. 

Every project creator sets their project's funding goal and deadline. If people like the project, they can pledge money to make it happen. If the project succeeds in reaching its funding goal, all backers' credit cards are charged when time expires.

## Table of Contents
#### 1) Introduction
#### 2) Data Cleaning
#### 3) Data Reporting & Dashboard
#### 4) Data Analysis
#### 5) Conclusion
____________________________________________________________________________________________________________________________________________________________________

## 1. Introduction
The data set is retrieved from [(Kaggle.com)] for exlration/practice purposes.

Here, we are looking at a huge dataset regarding the different kickstarter campaigns held on [Kickstarter.com](url) between the year 2009 and 2018.
The dataset contains more than 378,000 rowns in it. 

The dataset contains the following fields:
- **ID**: unique campaign ID
- **Name**: name of the campaign
- **Category**: which category the campaigns fall into
- **Main** **Category**: high level categories covering the sub categories
- **Currency**: which currency did this campaign was posted in (USD, CAD, GBP, etc.)
- **Deadline**: the deadline for the campaign to finish
- **Launched**: when was the campaign launched
- **Pledged**: the pledged amount in the original currency
- **State**: what is the state of the campaign (Successful, cancelled, failed, etc.)
- **Backers**: # of backers who supported a particular project
- **Country**: the two digit code for the country where the campaign took place
- **USD** **pledged**: the total amount in USD pledged for that particular campaign
- **USD** **Goal**: the goal set by the creator in USD for the campaign

We also used another data set with the country code and the corresponding country name to join with the original data set to make the reporting easier.
