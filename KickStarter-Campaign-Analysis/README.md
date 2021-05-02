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
The data set is retrieved from [Kaggle](https://www.kaggle.com/) for exlration/practice purposes.

Here, we are looking at a huge dataset regarding the different kickstarter campaigns held on [Kickstarter](https://www.kickstarter.com/) between the year 2009 and 2018.
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


Here is how the **first dataset** looks like:
![image](https://user-images.githubusercontent.com/13681798/116826535-6c79d300-ab62-11eb-826e-c490b6187735.png)


And, the **second dataset** looks like this:

![image](https://user-images.githubusercontent.com/13681798/116826411-d5ad1680-ab61-11eb-8015-a186a6e6d50d.png)

Now let's see how this first dataset needs to be cleaned before we do any analysis or reporting with it.


## 2. Data Cleaning

#### Step 1: Changing the naming convention:
   From the image shared above, it is clear that the names of the fields don't align with best practices, so the names need to be changed first. Here is how the dataset looks after changing the names:
   
![image](https://user-images.githubusercontent.com/13681798/116827765-c2517980-ab68-11eb-9432-758d966ff7b4.png)

It looks more readable this way.

#### Step 2: Getting rid of the extra spaces and uppercase/lower case differences:
   There are several text columns in the dataset where there extra spaces in some recoeds,and the case of the letters is not consistent in a few columns, mainly in currency and country. So, to solve that issue we used a combination of Excel functions TRIM and PROPER.
   After using these functions, there are no extra white spaces or case differences in the worksheet.
   > This would be a very crucial step when we create a report to represent our data in charts and dashboards.
   
   Here is how the dataset looks like after formatting changes:
   
![image](https://user-images.githubusercontent.com/13681798/116828556-6dfcc880-ab6d-11eb-823e-367edc1b4d7e.png)

   We also centre aligned the columns to make it more readable.

