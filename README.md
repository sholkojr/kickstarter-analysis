# Optimizing A Kickstarter Campaign

## Overview
The object of this analysis is to better understand when to launch a Kickstarter campaign and realistic funding targets based on recent data for theater production Kickstarters.
This report was completed for Louise (the project client) to enable her to better understand how her Kickstarter campaign is performing relative to other similar campaigns.  

This report will break down the analysis of the data (including challenges encountered) and provide a summary of the results of the analysis.

## Analysis and Challenges
The analysis was performed using MS Excel utilizing Pivot Tables and Charts to summarize.  The data was supplied from Kickstarter via the Project Client.  The analysis can be broken into three parts:
1. Plays in Scotland
2. Kickstarter Launch Date
3. Kickstarter Goal vs. Outcome

### 1. Plays in Scotland
Initial focus on specific plays in Scotland of interest to the Project Client. This data was pulled from the main dataset with a VLOOKUP Function to understand if the plays had been successful as an example:
```=VLOOKUP(A2, Kickstarter!B:E, 3, FALSE)```,
where "A2" is the play referenced, "Kickstarter!B:E" is a subset of the data table (Specific Scottish Plays in this case).

### 2. Kickstarter Launch Date
Also of interest was to investigate if there was any correlation of the success of theater kickstarter campaigns base on what month of the year that they were initiated.  This was done by creating a pivot table based on the launch date and isolating for the Month-of-the year.  The resulting table can be found below.

### 3. Kickstarter Goal vs. Outcome
The third investigation was to understand if the was any relationship between the size of the goal of the campaign and whether or not it was successful.  This was done by using Excel's COUNTIFS function to create discreet dollar amount buckets to group campaigns.  For example:
```=COUNTIFS(Kickstarter!$F:$F,"successful",Kickstarter!$D:$D,"<1000", Kickstarter!$O:$O,"plays")```, which counts the number of rows of the Kickstarter data filtered based on "successfull", that the goal is less than 1000 and that the kickstarter subcategory is "plays."

### Challenges
One of the challenges was validating that the COUNTIFS equations were providing the correct answer.  This took some trial-and-error but what accomplished by matching the result of the formula with matching filters on the dataset table and selecting all rows of the resulting filtered data (with count, total and average of the selected cells at the bottom corner of Excel).

Another challenge or discovery found was when rows were added to the Datatable.  Even though Excel would recognize that the additional row is now part of the Table, it would not be automatically added to the Pivot Table fields (Columns that converted the Oracle date stamp to a readable date as an example).  This had to be performed by Refreshing the data.  This saved time that otherwise would have been spent blowing away the existing Power Pivot table and creating a new one.

## Results

Analysis of the Kickstarter data provided the following conclusions.

## Kickstarter Launch Date





