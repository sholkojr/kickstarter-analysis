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

### Kickstarter Launch Date

Upon reviewing the following [chart](https://github.com/sholkojr/kickstarter-analysis/blob/master/Theater_Outcomes_vs_Launch.png) based on Kickstarters in the US in the "plays" subcategory, the failure and success rates appear to more or less track with each other until May. During May, the ratio of successful to failed Kickstarters is at its best and the overall volume is highest.  However, this advantage steadily decrease over the summer months to September.  This would indicate that it is best to launch in May if possible, or during the summer months at the latest.

### Kickstarter Goal vs. Outcome

Based on the review of US Kickstarters in the "plays" subcatergory, the attached [chart](https://github.com/sholkojr/kickstarter-analysis/blob/master/Outcomes_vs_Goals.png) shows how the target amount appears to influence the chances of success.  There appears that there is an inverse relation between the size of the target and its chances of success, which makes intuitive sense.  The chart appears to reverse between $35k and $45k, but this can be attributed to the relative lack of data.  The number of Kickstarters decreases as the Goal amount increases.

### Analysis Limitations

One of the key limitation of the dataset is the lack of the information on the donations themselves.  It would have been beneficial to understand the source of the donations to answer questions on whether the success of certain plays were based on many small donations or the beneficiary of a small number of large donations (or a single patron).  As an example, if the client had information on the key patrons, they could understand these individuals possible preferences (drama vs. comedy as example) and potentially court these individuals for their patronage.

The Launch data graph would have benefitted from a showing the percentages on a second y-axis, which would have better shown the relative success rate.  The Goal vs. Outcome chart would have benefitted from the reverse, showing the absolute numbers to show the statistical significance of the data in the lower Goal ranges.

