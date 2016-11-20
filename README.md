# Exercise-4
Exercise-4: Data classification and overlay analysis

This week we will practice how to do data classification and aggregation in Geopandas. We continue from the last week's exerise with rather similar idea. The overall aim this week is to define *dominance areas* \[0\] for 8 shopping centers in Helsinki with different travel modes (Public tranport, private car). The last step (optional) is to find out how many people live within the dominance areas of those big shopping centers in Helsinki Region. 

*The exercise might be a rather demanding one, so don't panic, we will go through the exercise carefully in the following weeks.*

\[0\]: Here, we define the dominance area of a service as the geographical area from where the given service (shopping center) is the closest one to reach in terms of travel time. 

### Due dates
 
 - 100 % of point total if you return your solution within 1 week (due date 28.11.2016) 
 - 85 % of point total if your return your solution within 2 weeks (due date 05.12.2016)
   - Detailed hints provided
 - 50 % of point total if you return your solution within 3 weeks (due date 12.12.2016)
   - Full solution provided

## Sections

 - [Problem 1: Join accessibility datasets into a single GeoDataFrame and visualize it](#problem-1-join-accessibility-datasets-into-a-single-geodataframe-and-visualize-it#problem-2-calculate-and-visualize-the-dominance-areas-of-shopping-centers)
 - [Problem 2: Calculate and visualize the dominance areas of shopping centers](#problem-2-calculate-and-visualize-the-dominance-areas-of-shopping-centers)
 - [Problem 3 (optional): How many people live under the dominance area of each shopping centers?](#problem-3-optional-how-many-people-live-under-the-dominance-area-of-each-shopping-centers)
 - [Answers](#answers)
 - [Hints](#hints)

## Problem 1: Join accessibility datasets into a single GeoDataFrame and visualize it

 - Download a dataset from here that includes 8 text files containing data about accessibility in Helsinki Region and a Shapefile that contains a Polygon grid that can be used to visualize and analyze the data spatially. The datasets are:
 
     - `travel_times_to_XX.txt` including travel times to specific shopping center
     - `MetropAccess_YKR_grid_EurefFIN.shp` including the Polygon grid with YKR_ID column that can be used to join the grid with the    accessibility data

 - Read those travel_time data files (one by one) with Pandas and select only following columns from them:
    
    - pt_r_tt
    - car_r
 
 - Join the accessibility data files one by one with the Polygon grid and visualize the **classified** travel times (Public transport AND Car) of at least one of the shopping centers using the classification methods that we went through in the [lesson materials](https://automating-gis-processes.github.io/2016/Lesson4-reclassify.html). You need to classify the data into a new column in your GeoDataFrame. For classification, you can either:
 
    - Use the [common classifiers from pysal](https://automating-gis-processes.github.io/2016/Lesson4-reclassify.html#classification-based-on-common-classifiers)
 
    - Or create your own [custom classifier](https://automating-gis-processes.github.io/2016/Lesson4-reclassify.html#creating-a-custom-classifier). If you create your own, remember to document it well how it works! Write a general description of it and comment your code as well. 
 
 - Upload the map(s) you have visualized into your own Exercise 4 repository (they don't need to be pretty). If visualizing takes for ever (as computer instance can be a bit slow), it is enough that you visualize only one map using plotting in Geopandas. If it is really slow, you can do the visualization also using the QuantumGIS in the computer instance or even ArcGIS in the GIS-lab (then you need to save the data as shapefiles and upload it to GitHub and download again to the local computer. 

## Problem 2: Calculate and visualize the dominance areas of shopping centers

In this problem, the aim is to define the dominance area for each of those shopping centers based on travel time. 

How you should proceed with the problem is that 

 - you iterate over the accessibility files one by one
 - rename the travel time columns so that they can be identified 
   - you can include e.g. the to_id number as part of the column name (then the column name could be e.g. pt_r_tt_5987221)
   - you can also take advantage of the name included in the data file (then the column name could be e.g. pt_r_tt_Itis
 - Join those columns into MetropAccess_YKR_grid_EurefFIN.shp 

## Problem 3 (optional): How many people live under the dominance area of each shopping centers?

Take advantage of the materials last week and find out how many people live under the dominance area of each shopping center. 

## Answers

## Hints

If you need more help with the exercise, [**read the hints**](https://github.com/Automating-GIS-processes/Lesson-4-Classification-overlay/blob/master/Lesson/Exercise4-hints.md).
