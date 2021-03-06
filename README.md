# Kickstarter-Analysis
Performing analysis on Kickstarter data to uncover trends using Excel
# Kickstarting with Excel

## Overview of Project
Fundraising is a challenging endeaver requiring resources and the ability to target the right audiance. Data analsysis and visualization techniques in excel provide a means of uncovering ttends in the Kickstarter dataset on fundraising. Available data includes organizations fundraising goals, how much was pledged, how many people made a pledge, start and end dates, country, category and sub categories of industries. This analysis is intended to provide recomendations for a client in the theater industry.   

### Purpose
In order to uncover trends in the Kickstarter dataset and provide recomendations for Louise's fundraiser for her play *Fever*. Specifically, data visulizations will be provided and dsicussed in regards to fundraiser outcomes in relation to the launch date and Outcomes based on goals. 

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date
#### Timestamp
In the original data (see attached in the repository), launch date was coded as Unix Timestamp. Using the formula from [Lesson 1.3.3] (https://courses.bootcampspot.com/courses/587/pages/1-dot-3-3-timing-success?module_item_id=187837) new column was created called Date Created Conversion and the code  `=(((K2/60)/60)/24)+DATE(1970,1,1)` was used to convert the entire column. 

#### Pivot Table
Next a Pivot Table was created with Date Created on the rows and outcomes on the columns. The value was count of outcomes.  The table was filtered by category to show only theater and year was added as an additioanl filter (see attached "Screen Shot 2021-04-26 at 4 02 01 PM" in repository). The outcome Live was filtered out of the table and subsequent graph. 

#### Linegraph
Last a line graph was created to show the outcomes based on launch date by highlihgting the pivot table and inserting a line graph (see attached "Theater_Outcomes_vs_Launch.png" in the repository). 

This analysis was straightforward and I did not encounter any challenges. 

### Analysis of Outcomes Based on Goals
#### Table
A new sheet in the Kickstarter dataset was created with 8 columns and 12 rows. The first column was labeled Goals, the next three were number of Succesful, failed and canceled, then total projects, and the last three were precentage of Succeful, Failed and Canceled. The rows were labeld by goal amount less than $1000,  then at a range of $5000 incerments, and more then $50,000. 

Next, the COUNTIFS() function was used to populate the number of succesful, failed and canceled projects at each goal level. I used code from [Microsoft] (https://support.microsoft.com/en-us/office/countif-function-e0de10c6-f885-4e71-abb4-1f464816df34) and adapted it to fit this data set. The first row was pretty straight forward using the following code `=COUNTIFS(Kickstarter!F:F,"successful", Kickstarter!D:D,"<1000", Kickstarter!Q:Q,"plays")`. I struggled a bit on the ranges and searched for IF statments between two numbers and used example code from [Corporate Finance Institute] (https://corporatefinanceinstitute.com/resources/excel/study/if-statement-between-two-numbers/) to adapt the following code `=COUNTIFS(Kickstarter!F:F,"failed",Kickstarter!D:D,">=10000",Kickstarter!D:D,"<=14999", Kickstarter!Q:Q,"plays")`. When I got the number canceled all the columns were zero. I knew the code was working so I went to the original data set and created a pivot table with sub category on the row,  outcomes on the columns, and outcome counts as the value. I was able to see very quickly that in this data set none of the fundraisers for plays were canceled (see "Screen Shot 2021-04-27 at 12 47 49 PM" attachede in repository). 

Then, the `SUM()` function was used to add up the three number of outcomes columns to populate the total projects column using the following code `=SUM(B2:D2)`. After, that thefollowing code was used to populate the last three percentage of outcomes columns `=IFERROR(ROUND((D13/E13), 2),0)`. The last three columns were then formated to be percentages. My original code did not include the IFERROR() function and there were errors in the last row of succeful and failed and the enitre culumn for canceled. The `IFERROR()` and and `ROUND()` functions were implelemnted from [lesson 1.2.6] (https://courses.bootcampspot.com/courses/587/pages/1-dot-2-6-errors-and-debugging?module_item_id=187825). 

#### Line Graph
A line graph was created with the goal amount on the x-axis and the percent of outcomes on the y-axis. I couldnt remember how to select only part of a table to use only the percentage columns so I used the filtering to deselect all on the other four columns. This eliminated them from the line graph (see attached "Outcome_vs_goal.png" in the repository).

### Challenges and Difficulties Encountered

As described above the challenges and solutions I encountered included the following:
  1. `COUNTIFS()` with a range
  2. ensuring the resutls were accurate for the canecled columns
  3. line graph with only the percentage columns showing up.
  

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?
   1. May is the most frequest month to launch a new fundraising campaign and December is the least frequent. 
   2. Theater fundraisers are largerly more succesful than not regardless of launch date. 

- What can you conclude about the Outcomes based on Goals?
   1. Based on the line graph there were no fundraisers over $45,000. 
   2. There dosent seem to be a pattern on outcmes vs goals in predicting success or failure of a fundraiser. 

- What are some limitations of this dataset?
   1. One limitation in this data set is a variable on methods of reaching potential doners (i.e. cold calls, social media, membership lists).   
   2. Another limitiation is a variable for how much money was actually donated. There is a variable to show how much money was pledged but not how many people actaully followed through.  

- What are some other possible tables and/or graphs that we could create?
   1. A data table and line graph simialr to the outcome based on goals with launch date and pledged to see if that gives more information on the impact on launch date. Do people give more in the spring and summer than other times of the year?  
   2. Analysis on the duration of the fundraiser and outcomes might be insightful as well. I would create a column subtractng the end date from the launch date to find out how many weeks or months a fundraiser was active and then use a table and line graphs similar to the ones for outcomes based on goals. 


