+++
draft = false
title = 'Excel Project: Getting to the Root of Why Customers Are Churning'
+++

Excel is very accesible for anyone who wants to analyse data, but this does not detract from the power it has to perform complex insights. For this reason, I thought it imperative to build on the excel skills I learnt at school so that I could use all of the tools excel has to offer. 

I started a DataCamp excel course which culminated with a project looking to analyse the churn rate of customers at a fake broadband company, databel. 

![databel_overview](/img/databell_customer_spreadsheet.png)

The great thing about this course was that as well as going over what I had learned about the functionality of excel, it also went through the workflow of analysing a dataset, splitting this into 5 stages:

1. Check the data
2. Explore the data
3. Gather insights
4. Create a dashboard
5. Present to stakeholders

This workflow outlined how I worked through the project, although I didn't get a chance to present my analysis, so hopefully writing this article will somewhat provide a practice of this.

Preparing the data was very simple in this case as it wasn't particularly messy to begin with, although in future projects I imagine it will be useful to work with messier data. I simply used the 'remove duplicates' button, of which there were none.

I learned that a good way to explore a dataset is to find the summary statistics. In the case of this dataset looking at churned customers, the churn rate is an important KPI for Databel. To find the churn rate, I created a pivot table with the count of total customers and churned customers in the value section. I then used a calculated field to find out the churn rate from these two values. 

![churn_rate_pivot](/img/churn_rate_pivot.png)

This churn rate seemed high, so it was worth looking into the reasons why customers were leaving. I learned that it was important to have a plan to thoroughly analyze all of the data, looking through all of the columns systematically and the interplay between these columns. I thought the best place to look first was the churn reason column, where I found, by grouping these reasons in a pivot table, that better offers from competitors was the most common reason, suggesting that Databel needed to lower their prices.

![churn_reason](/img/churn_reason.png)

This project also taught me that if you have a significant and useful insight, it is worth exploring this further to see if any other connections can be made. The database has fields separating customers into 'senior' and 'under 30'. I grouped these fields together by creating a new field called 'demographics' using a nested `IF()` statement: 

`=IF([@[Under 30]]="Yes","Under 30",IF([@Senior]="Yes","Senior","Other"))`

This allowed me to easily create a pivot table and column chart looking at the number of customers and churn rate of customers based on their demographic, finding that seniors had the highest churn rate.

![demographic_churn_rate](/img/demographic_churn_rate.png)

Because this was a useful insight, I explored further into how closely age affected churn rate by visualising the churn rate against more exact age groups:

![age_churn_rate](/img/age_churn_rate.png)

This showed a direct rise in churn rate and decrease in customer count as age increases. The customer reason for this is also to do with better competetor offers, offering no extra insight into why this is happening, so in this case I would recommend Databel to explore this further through customer research to find why their customers churn as they get older.

The final step was to create a dashboard to present all of my findings. I enjoyed getting a bit creative to make the dashboard look appealing and emphasise the most important findings. Here is my completed dashboard:

![databel_dashboard](/img/databel_dashboard.png)

I really enjoyed coming back to excel because it's so easy to use! It was also very useful to learn new excel skills, such as new functions like `IFS()` to select data in more complex ways; how to make dashboards look better with the design tools; and also the techniques for how to go about analysing data. I'm looking forward to doing more projects in excel, perhaps with more data cleaning, which is such an important skill for an analyst