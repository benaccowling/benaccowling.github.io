+++
date = '2024-12-16T17:24:33Z'
draft = false
title = 'Visualising Dataframes'
+++

<!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-6KG34X3C2K"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-6KG34X3C2K');
</script>

Up to the point of making this website to start documenting my learning, I have done some basic python data learning on pandas, matplotlib and numpy. The learning block I am currently working through is about manipulating data in pandas. This has involved a lot of grouping data, for example in pivot tables. I'm told by people I know in data that these are the bread and butter of a data analyst, to summarize data in a tabular form, making it easier to draw insight from. This last section is about using matplotlib to visualise the manipulated data, making it even easier to spot trends. There were also a few extra bits about creating a dataframe from a dictionary, but they weren't that interesting so I won't go over these.

The section used a dataframe of avocado sales in the USA, called 'avocados', including the size of the avocados and whether they were organic. I love that you get to learn about things you didn't even know you wanted to from analysing the different datasets, like 'what size of avocado sell the most?'. Here is the first few lines of 'avocados':


|         date|         type | year | avg_price |  size |   nb_sold|
|-------------|--------------|------|-----------|-------|----------|
|  2015-12-27 | conventional | 2015 |      0.95 | small | 9.627e+06|
|  2015-12-20 | conventional | 2015 |      0.98 | small | 8.710e+06|
|  2015-12-13 | conventional | 2015 |      0.93 | small | 9.855e+06|
|  2015-12-06 | conventional | 2015 |      0.89 | small | 9.405e+06|
|  2015-11-29 | conventional | 2015 |      0.99 | small | 8.095e+06|

### Bar Charts

First, I grouped the number of avocados sold by size, showing number sold using `avocados.groupby('size')['number_sold'].sum()`. This uses the pandas `grouby()` method to group the data by size, and displays the total number sold in each group added together with `sum()`.

I used the matplotlib.plot method `df.plot(kind=bar)` to create a bar chart of the data, which is more useful given the 'size' field on the x axis is a categorical variable. 

![avocados_bar_chart](/img/avocados_bar_chart.jpg)

It seems that 'extra large' avocados sell a lot more than 'large' or 'small', potentially because less stores sell extra large avocados.

### Line Graphs

Line graphs are better for comparing 2 continuous variables and often 'date' will be on the x axis, to see the trend of something over time. This was the case when creating a line plot looking at number of sales grouped by date, using `df.plot` without using the argument `(kind=bar)`

![avocados_line_graph](/img/avocados_line_graph.png)

From this we can tell that avocado sales spike around January each year, I'm assuming because everyone wants to get their health kick in the new year.

### Creating Multiple Plots

One of the reasons to subset the data is to compare groups. This can be done by visualising 2 plots on the same graph. To demonstrate this point, I was tasked with comparing the prices of conventional vs organic avocados. 

First, I had to subset the data into 'conventional' and 'organic' groups. I did this by creating a Boolean: `avocados[avocados['type'] == 'conventional']['avg price']`. The first call of the dataframe 'avocados' outside the Boolean makes sure the result is a dataframe of the conventional avocados, instead of a list of Booleans. The second square brackets tells the computer what other column you want displayed with the group to compare with other groups. 

I added `.hist()` to the end of this line to create a histogram of this group. To add a histogram of organic avocado price, I simply wrote another line underneath this one subsetting organic avocados and ending with `.hist()`.

I added a legend to the histograms so I knew which one is which with `plt.legend(["conventional", "organic"])`, then used plt.show to show both histograms together. To make sure I could see where the histograms intersected, I added `(alpha=0.5)` as an argument to reduce the opacity of the histograms.

![avocados_histograms](/img/avocados_histograms.png)

Unsurprisingly, organic avocados are more expensive on average. As a side note, I found that every time I ran the code to show the histograms, they changed colour! It's the little things :).

### Summary

This was a great way to finish the 'data manipulation in pandas' course, as subsetting and summarizing parts of the data was a large part of the course, whether in a pivot table or as a separate dataframe altogether. Next, I'm on to joining data in pandas. I've covered this previously in SQL, so it will be interesting to see how the 2 differ in their approach. 
