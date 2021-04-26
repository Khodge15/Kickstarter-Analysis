# Kickstarter-Analysis
Performing analysis on Kickstarter data to uncover trends using Excel
# Kickstarting with Excel

## Overview of Project
Fundraising is a challenging endeaver requiring resources and the ability to target the right audiance. Data analsysis and visualization techniques in excel provide a means of uncovering ttends in the Kickstarter dataset on fundraising. Available data includes organizations fundraising goals, how much was pledged, how many people made a pledge, start and end dates, country, category and sub categories of industries. This analysis is intended to provide recomendations for a client in the theater industry.   

### Purpose
In order to uncover trneds in teh Kickstarter dataset and provide recomendations for Louise's fundraiser for her play Fever. Specically, data visulizations will be provided and dsicussed in regards to fundraiser outcomes in relation to the launch date and Outcomes based on goals. 

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date
#### Timestamp
In the original data (see attached in the repository), launch date was coded as Unix Timestamp. Using the formula from Lesson 1.3.3 https://courses.bootcampspot.com/courses/587/pages/1-dot-3-3-timing-success?module_item_id=187837 new column was created called Date Created Conversion and the code =(((K2/60)/60)/24)+DATE(1970,1,1)was used to convert the entire column. 

#### Pivot Table
Next a Pivot Table was created with Date Created on the rows and outcomes on the columns. The value was count of outcomes.  The table was filtered by category to show only theater and year was added as an additioanl filter (see screen shot attached). The outcome Live was filtered out of the table and subsequent graph. 

<img width="1342" alt="Screen Shot 2021-04-26 at 4 02 01 PM" src="https://user-images.githubusercontent.com/82460401/116150574-24ae0400-a6a9-11eb-88ec-d9375b061496.png">

#### Linegraph
Last a line graph was created to show the outcomes based on launch date by highlihgting the pivot table and inserting a line graph (see attached in the repository). 

This analysis was straightforward and I did not encounter any challenges. 

### Analysis of Outcomes Based on Goals

### Challenges and Difficulties Encountered

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

- What can you conclude about the Outcomes based on Goals?

- What are some limitations of this dataset?

- What are some other possible tables and/or graphs that we could create?
