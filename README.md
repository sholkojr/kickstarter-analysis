# Optimizing Your Kickstarter Campaign

## Overview
The object of this analysis is to better understand when to launch a Kickstarter campaign and realistic funding targets based on recent data for theater production Kickstarters.
This report was completed for Louise to enable her to better understand how her Kickstarter campaign is performing relative to other similar campaigns

## Analysis and Challenges
The analysis was performed using MS Excel utilizing Pivot Tables and Charts to summarize.  The data was supplied from Kickstarter via the Project Client.

Initial focus on specific plays in Scotland of interest to the Project Client. This data was pulled from the main dataset with a VLOOKUP Function to understand if the plays had been successful as an example:
```=VLOOKUP(A2, Kickstarter!B:E, 3, FALSE)```
Where "A2" is the play referenced, "Kickstarter!B:E" is a subset of the data table.

Also of interest was to investigate if there was any correlation of the success of theater kickstarter campaigns base on what month of the year that they were initiated.  This was done by creating a pivot table based on the launch date and isolating for the Month-of-the year.  The resulting table can be found below.

The third investigation was to understand if the was any relationship between the size of the goal of the campaign and whether or not it was successful.  This was done by using Excel's COUNTIFS function to create discreet dollar amount buckets to group campaigns.  For example:
```=COUNTIFS(Kickstarter!$F:$F,"successful",Kickstarter!$D:$D,"<"&$B2, Kickstarter!$O:$O,"plays")```
