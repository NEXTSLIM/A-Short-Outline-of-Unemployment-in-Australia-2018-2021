## Project: Python Data Visualization
The primary purpose of this group project was to identify unemployment trends in Australia, with particular focus to the impacts of COVID19 on the unemployment rate. My role was to focus on analysis at the state level so that we could identify which states were most heavily affected by the crisis. 

## Data Set - API

We considered data from the Victorian Government Developer website as a reliable data source for this project. We retrieved all the data through an Application Programming Interface (API) from the ABS Labour Force API. This API provides Australian Bureau of Statistics labor force data in an easily consumable format for developers. Labour force data includes employment statistics by region, sex, age groups and labour utilisation using original, seasonally adjusted and trend markers since 1978 to date. Since our project investigated the impact of COVID19 on the unemployment rate, we focused our analysis in the last 10 years from 2010 - 2020, and compared 2019 with 2020 to get an idea of the unemployment rate before and during COVID19. The data available for 2021 is only complete for January so we did not consider the year 2021 in this analysis.

## Analysis of the Unemployment in Australia by State

For my analysis section (state analysis), I retrieved the data by state. The data received in JSON format, and I created a function to traverse the dictionary to create a table out of it.

