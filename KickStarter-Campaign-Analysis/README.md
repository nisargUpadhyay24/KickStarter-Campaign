# KICKSTARTER CAMPAIGN ANALYSIS

## About Kickstarter Campaigns
The kickstarter campaigns are used when creators/visionaries share their vision with a wider community and want this community to fund their vision/product. 

Every project creator sets their project's funding goal and deadline. If people like the project, they can pledge money to make it happen. If the project succeeds in reaching its funding goal, all backers' credit cards are charged when time expires.

## Table of Contents
#### 1) Introduction
#### 2) Data Cleaning
#### 3) Data Reporting & Dashboard
#### 4) Data Analysis
____________________________________________________________________________________________________________________________________________________________________

## 1. Introduction
The data set is retrieved from [Kaggle](https://www.kaggle.com/) for exlration/practice purposes.

Here, we are looking at a huge dataset regarding the different kickstarter campaigns held on [Kickstarter](https://www.kickstarter.com/) between the year 2009 and 2018.
The dataset contains more than **378,000** rows in it. 

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

**Note:** Changing the name is also important as it will be reflected in the dashboard later.

#### Step 2: Getting rid of the extra spaces and uppercase/lowercase differences:
   There are several text columns in the dataset where there extra spaces in some recoeds,and the case of the letters is not consistent in a few columns, mainly in currency and country. So, to solve that issue we used a combination of Excel functions TRIM and PROPER.
   
   After using these functions, there are no extra white spaces or case differences in the worksheet.
   > This is a very crucial step that will help us when we create a report to represent our data in charts and dashboards.
   
   Here is how the dataset looks like after formatting changes:
   
![image](https://user-images.githubusercontent.com/13681798/116828556-6dfcc880-ab6d-11eb-823e-367edc1b4d7e.png)

   We also centre aligned the columns to make it more readable.

#### Step 3: Getting rid of the corrupted data:
   In the first dataset, there are some rows with corrupted data in the Country field as below:
![image](https://user-images.githubusercontent.com/13681798/116875911-a9d57380-abe9-11eb-9c99-4c206d33e293.png)

There are total **3797** rows with N,0" as a country code in the dataset, which represents 1% of the overall data.
Based on the requirements of the projects you are working on, we can manage this in many different way.

For our project purposes, it is statistically insignificant to have an impact. So we would go ahead and delete these **3797** rows.
And now, the data looks like this:

![image](https://user-images.githubusercontent.com/13681798/116876948-43e9eb80-abeb-11eb-9839-c07430ef2695.png)

#### Step 4: Adding the actual name of the coutry in the dataset:
   If you look at the first dataset, it only has two digit country codes under the country column, which would not serve the purpose of the analysis as well as the dashboards we are going to create. _It would be pretty difficult to remember over a hundred countries from a two digit code._
   
   So, to mitigate this situation, we are going to use advanced excel functions. We are going to use the combination of **INDEX** and **MATCH**. And for this purpose, we will be using our **second dataset as mentioned above** to retrieve and match the country name.
   
   There are many ways to map the country name to the country code such as VLOOKUP, INDIRECT, etc., but from my experience INDEX+MATCH is a more robust and almost unbreakable way to map the values back. (_This methond will also work if there are any changes to the second file where you are getting the info from, which would not be the case with VLOOKUP._)
   
   After using the combination **INDEX** + **MATCH**, this is how the original dataet would look like:
   
![image](https://user-images.githubusercontent.com/13681798/117592551-fb5c9180-b106-11eb-898d-8be1384fbd3c.png)


## 3. Data Reporting & Dashboard

For this project, we want to create a dashboard that shows the project related information over the course of 10 year, with the help of different filters. To achieve that - before we jump into designing our dashboard - we need to create a couple of pivot tables from the dataset.

The first pivot table gives us the information about the cumulative project details like total # of projects, total # of backers, etc. Here is what the first pivot table looks like:

![image](https://user-images.githubusercontent.com/13681798/117742292-6757fc00-b1d2-11eb-87a0-6cadd9b6a274.png)


The second pivot table gives us the information about the number project per year, and the table looks like this:

![image](https://user-images.githubusercontent.com/13681798/117742429-c453b200-b1d2-11eb-9aca-37a8605983fd.png)


Now, based on the second pivot table mentioned above, we will create a line chart to show the # of projects every years over the course of 10 years, from 2009 to 2018.
We will use **pivot charts** from the 'Pivot Table Analyse' tab, and select column chart. It should look something like this:

![image](https://user-images.githubusercontent.com/13681798/117743220-5e682a00-b1d4-11eb-9e8c-bf0ef64ee508.png)

_**Note**_: This is just a preliminary chart, we will do modifications to it as we go along.

Once we have that ready, we will add 3 slicers from the 'Insert Slicers' menu option - one for **Country**, one for **Project** **State**, and one for **Category**.
The three slicers look like this:

![image](https://user-images.githubusercontent.com/13681798/117743763-6d031100-b1d5-11eb-904f-21c3cdb9a53b.png)

