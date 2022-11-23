# PyBer Analysis
## Overview
We were initially tasked to create visualizations of rideshare data for PyBer to improve access to ride-sharing services and determine affordability for underserved neighborhoods. We created bubble charts, box-and-whisker plots, and pie charts to show the trends of each bin based on city type as well as the summary statistics for each. Next, we were given a new assignment to create a summary DataFrame of the ride-sharing data by city type and to create a multiple-line graph that shows the total weekly fares by each city type.

## Results

We started our project by merging the city data and the ride data csv files that we had been analyzing to create visualization of rideshare data to improve access to ride-sharing services and determine affordability for underserved neighborhoods. We then used `groupby()` functions to group the data based on city type to gather the total rides, the total drivers, and the total amount of fares for each city type. In addition, we also calculated the average fare per ride and the average fare per driver using the total amount of fares for each city type and dividing it by the total rides and the total drivers respectively. These calculations were then added to a Pyber Summary DataFrame and formatted to include a thousand separator and US dollar symbols, image below

![Screenshot 2022-11-23 161323](https://user-images.githubusercontent.com/114427019/203661799-48c3a9b1-5c36-4349-aea5-2be879664d51.png)

Our second visualization was a line chart that displayed the weekly totals of the fares for each type of city. To start, we again merged the city data and ride data csv files. We then grouped the merged DataFrame using the `groupby()` function using "type" and "date" as our grouping columns to then calculate the sum of fares per day and city type. We then pivoted the DataFrame so that "date" was our index, and we used 'loc[]' to split out the dates from 2019-01-01 to 2019-04-28. Next, we converted the "date" column to be a DatetimeIndex. This was a key step for us to then use the `resample()` function to calculate the sum of the fares per week. With the new total fares per week DataFrame, we created a line chart that displayed the total fares per week, pictured below.

![Challenge_Plot](https://user-images.githubusercontent.com/114427019/203662956-5c6e15e9-9472-4528-9f7c-c18e187d8452.png)

With both of these visualizations complete, we can see that for all city types, the end of February was a high total fare time. Curiously, the end of March and beginning of April was the highest peak for Rural city types. We can also see that our snippet of time from January to April reenforces the summary table by showing that Urban city type rides have the highest total fares. In the summary table, we also see that while Rural city types have the lowest total fares, they have the highest average fare per ride and average fare per driver. On the other side, Urban city rides have the lowest average fare per ride and the lowest average fare per driver.

## Summary: Based on the results, provide three business recommendations to the CEO for addressing any disparities among the city types.

Based on the disparity between the average fare per ride and per driver for urban cities and rural cities, we suggest that executive management raise the fare in urban cities by $2-$3 and lower the fare by $2-$3 in rural cities. There is clearly a larger demand for rides in urban cities while there is not as high of a demand in rural cities. This wouldn't affect the overall total profits, and it could possibly raise the rides requested in rural areas.

The second recommendation we have for executive management would be to lower the number of drivers in urban cities. There are about 30% more drivers than riders which means that the overall average fare per driver is drastically lower than the other city types.

The third recommendation we have for executive management would be to consider hiring more drivers in the rural city type as the average fare per driver is higher than the other two city types. This could be accomplished by hiring more drivers for the rural city areas which would also help to meet the demand of the riders in rural cities.
