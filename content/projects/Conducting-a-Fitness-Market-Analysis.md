+++
date = '2025-01-30T10:23:56Z'
draft = false
title = 'Conducting a Fitness Market Analysis'
+++

<!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-6KG34X3C2K"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-6KG34X3C2K');
</script>

For this project in python, the aim for me was to practice answering business questions by figuring out which methods to use for each question. I think that although multiple methods could have been used for each question, my rationale was to think of what I was logically trying to do for each question and find the most appropriate method.

This project looks at 5 different datasets, looking at the popularity of some fitness related search terms on google, along with the associated country and how the popularity has changed over time. As a fitness studio, the idea was to query the data to identify potential areas for growth of digital products and services.

### Task 1

The ‘workout.csv’ file contains a table with the ‘workout_worldwide’ field and the associated month. ‘workout_worldwide’ is an index from 1 to 100 representing the popularity of the keyword ‘workout’ on google. 

![workout_head](/img/workout_head.png)

The first task was to find when the global search for ‘workout’ was at its peak. I thought initially of using `df.query()` and writing a logical statement to get the max value of ‘workout_worldwide’ but then I thought an easier way to do this would be to sort the dataframe in descending order to get the top result, using:

`df.sort_values(‘workout_worldwide’, ascending=False)`

The month where the word ‘workout’ was searched most was April 2020, just as most places started to go into lockdown because of covid.

### Task 2

The ‘three_keywords’ table is the same as the ‘workout’ table but with 3 keywords instead: ‘home_workout’, ‘gym_workout’ and ‘home_gym’. The task was to find which keyword was most popular during covid (I assumed this was 2020-2022) and what the most popular is now. 

Because I need to see the values of the columns over a time period, I thought that it would be best to find the most searches by visualising the data with a line graph with matplotlib: 

`plt.plot([“home_workout”, “gym_workout”, “home_gym”], kind = “bar”)` 

The graph is shown below:

![keyword_graph](/img/keyword_graph.png)

This shows that ‘home_workout’ was by far the most searched term in covid, but now ‘gym workout’ is the highest but at a much lower search volume.

### Task 3
‘Workout_geo.csv’ has the ‘workout_2018_2023’ field which is a cumulative index of the popularity of the keyword ‘workout’ during the 5 year period, from 1 to 100 along with the associated country. The task was to find which country has interest in workouts out of the US, Australia or Japan.

For this task, I could have used the same method as for task 1, displaying the dataframe in descending order, but to change things up I created a logical statement to find the maximum value for ‘workout_2018_2023’, then queried the dataframe using the logical statement:

![task_three_code](/img/task_three_code.png)

This code returned these records:

![task_three_output](/img/task_three_output.png)

I realize now that this would not have worked if the USA did not search for workout the most, so I should have added a term to include only the US, Australia and Japan, similar to what I do in the next task.

Task 4

‘Three_keywords_geo’ has the cumulative search index for three_keywords from task 2 over the five year period with the associated country. The task was to find which out of the Philippines or Malaysia has the highest interest in home workouts, in theory to expand my fitness enterprise to the more interested country.

I used a mixture of the methods I used in previous tasks for this one. I used a query because I needed to include only Malaysia and the Philippines. I then sorted the 2 rows by the ‘home_workout_2018_2023’ column to find which country was more interested.

![task_four_code](/img/task_four_code.png)

This returned the records in descending order:

![task_four_output](/img/task_four_output.png)

The Philippines turned out to be the more interested country, so this is where I would start my virtual workout expansion!

### Conclusion

This project allow me to exercise my problem solving skills, requiring me to use various methods to answer the business questions. For example, using data visualization with matplotlib and using the query() method.


