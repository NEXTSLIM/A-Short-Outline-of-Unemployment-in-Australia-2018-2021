## Project: Python Data Visualization
## Analysis of the Unemployment in Australia by State

The primary purpose of this group project was to identify unemployment trends in Australia, with particular focus to the impacts of COVID19 on the unemployment rate. My role was to focus on analysis at the state level so that we could identify which states were most heavily affected by the crisis. 

## Data Set - API

We considered data from the Victorian Government Developer website as a reliable data source for this project. We retrieved all the data through an Application Programming Interface (API) from the ABS Labour Force API. This API provides Australian Bureau of Statistics labor force data in an easily consumable format for developers. Labour force data includes employment statistics by region, sex, age groups and labour utilisation using original, seasonally adjusted and trend markers since 1978 to date. Since our project investigated the impact of COVID19 on the unemployment rate, we focused our analysis in the last 10 years from 2010 - 2020, and compared 2019 with 2020 to get an idea of the unemployment rate before and during COVID19. The data available for 2021 is only complete for January so we did not consider the year 2021 in this analysis.

## Data retrieval from the ABS Labour Force API by State

For my analysis section (state analysis), I retrieved the data by state. The data received in JSON format, and I created a function to traverse the dictionary to create a table out of it.

Code snippet of the retrieval loop:

![](https://user-images.githubusercontent.com/77761497/114501585-9d569e80-9c6d-11eb-98de-f0e5704f85f8.png)

This algorithm generates a dictionary for each response from the ABS Labour Force API call. Then it is just a matter of converting each dictionary to pandas data frame that needs to be filtered in order to keep only relevant data.

## Data Analysis 

I first wanted to provide an overall visualisation of the Australian map with colour-graded state polygons representing the average unemployment rate during 2020 (during COVID19) by state. 

Code snippet to integrate state polygons with Google Maps API, unemployment rate by state in 2020 with colour gradient and map output:

![](https://user-images.githubusercontent.com/77761497/114503366-86fe1200-9c70-11eb-9566-82efb74cc008.png)

Boxplot and one-way ANOVA analysis showing that there are significant differences in the 2020 unemployment rate between states:

![](https://user-images.githubusercontent.com/77761497/114504362-1a841280-9c72-11eb-9648-c1f036b7ece6.png)

From the map and the boxplot it can be easily observed that the states of Queensland, South Australia and Western Australia had the highest unemployment rates (7.1%, 6.9% and 6.6% respectively), followed by Tasmania, Victoria, New South Wales and Northern Territory (6.5%, 6.4%, 6.1% and 5.6% respectively) and Australian Capital Territory was the state with the lowest unemployment rate of 3.4% during 2020. 

This already challenged the hypothesis we had that Victoria, due to the strict lockdowns would be the state with the highest unemployment rate during the COVID19 crisis. 

Finally, I did a comparison of the unemployment rate in 2019 and 2020 per state to see whether all states had a significant increase in unemployment during the COVID19 period.

![](https://user-images.githubusercontent.com/77761497/114504933-f83ec480-9c72-11eb-8fea-3b4a8277cb1f.png)

The data was normally distributed, therefore it was applicable to apply a t test comparison between the years. All states, with the exception of Tasmania (p>0.05 represented with ns), had a significant increase in unemployment in 2020 compared to the year before (p<0.001 represented with asterisks), likely due to the COVID19 crisis. 

This raises an interesting difference between states. Thus, in a future project we would like to explore the questions: 
- What is the reason for COVID19 not impacting equally across states? 
- Is it the size of employed persons vs labour force? 
- Perhaps the different job industries per states?
To investigate this, we would need to combine datasources since this API did not contain information about job industries per state.
