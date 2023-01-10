# PyBer_Analysis

## Overview of the analysis:

The purpose of our analysis is to create a summary dataframe that will show ride sharing data by city type(Rural,Urban & Suburban). Once we found our data we were asked to create a multiple line graph that showed total weekly fares by each city type. How we first pulled our data by using the pandas `Groupby()` function with the `count()` and `sum()` to get the total number of drivers,rides and fares by city type. Once we pulled this information and assigned it to functions we were able to calculate our average fare per ride and driver. Once we had all of that information together we were able to create a new data frame and re-format the columns. In the second part of this excercise we used the `pivot()` and `resample` function to create a multiple line graph that shows the total fares for each week by city type between the months of January & April of 2019. 

---

## Results by city type:

#Quick facts by city type, that can be seen in the image below.
Creating the summary data frame was done using the following code:
`pyber_summary_df = pd.DataFrame({
          "Total Rides" : total_rides ,
          "Total Drivers": total_drivers ,
          "Total Fares": total_fares,
          "Average Fare per Ride": avg_ridefare,
          "Average Fare per Driver": avg_driverfare})`
          
The results of the above code produces the image seen below and the following analysis can be made from the summary.
- Rural cities have the least amount of drivers, rides and total fares.
- Urban cities have the most amount of drivers, rides and total fares.
- Suburban cities are in the middle having the 2nd most drivers, rides and total fares.
- Although Rural cities see the least amount of drivers,rides & fares the have the highest average of fare per ride and fare per driver.
- Although the Urban cities have the most drivers, their rides and fares account for the lowest average of fare per ride and fare per driver.

![](https://github.com/TONY-H83/PyBer_Analysis/blob/main/analysis/Chart.png)

---

# Total Fare by city type chart between January & April of 2019

We used the multiple line graph in order to show the avg fares by each city type. This will allow the leadership team to analyze all three city types at the same time. Being able to compare multiple data points in the same visualization can be a valuabe tool when it comes to making real-time business decisions. The fianl graph was created using the following code:

`pyber_resample_df.plot(figsize = (25,10))
from matplotlib import style
style.use('fivethirtyeight')
plt.title("Total Fare By City Type")
plt.ylabel("Fare ($USD)")
plt.xlabel("")
plt.legend(loc="center",title="Type")`


![](https://github.com/TONY-H83/PyBer_Analysis/blob/main/analysis/PyBer_fare_summary.png)

---

# Summary

From our data we are able to tell what fares be expected based on what city type the passenger is commuting in. Although we didn't explore every individual city we still have a great grasp on what fares will look like from week to week based on the city type. This will be enough information needed for the transportation board in order to accurately asses if the rates are set at such a level to be profitable. In conclusion we can effectively say that a rural area will command a higher fare because there are fewer workers that will come to this area, the travel time and distance is most likely longer making the average fare per ride & driver the most out of all city types.

---

# Recommendations 

A few reccomendations that can be given in order to create a more effiecient and effective public transportation system could be:
1. Have your drivers rotate between the different city types so they have an equal work load.
2. Increase the rates in Urban cities slightly to increase the profits which may help offset operating costs in other city types.
3. Evaluate the entire year and adjust the rates to be in-line with the seasonality trands. 
