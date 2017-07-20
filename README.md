# More than two thirds of thefts are 'never solved'

![](https://ichef.bbci.co.uk/news/624/cpsprodpb/340D/production/_96752331_chart_crimetypes-3.png)

In July 2017 we [reported](http://www.bbc.co.uk/news/uk-england-40131277) that more than two thirds of police investigations into thefts and burglaries have been closed with no suspect ever being identified.

The report involved analysing over 37 million rows of data from [the official police data site](https://data.police.uk/data/) covering every crime in English police authorities since 2012. We then excluded anti-social behaviour as no outcome category is recorded. We also excluded the British Transport Police and Police Service Northern Ireland for the same reason. Police Scotland data is not kept at this site.

The data provides details of individual crimes at street level, including an approximate location, the month and year it occurred, the type of crime and the last known outcome.

Separate annual figures released by the Home Office show just under half of all crimes (48%) had their investigations completed with no suspects identified in 2015-16. This data is supplied by forces to the Home Office and is "quality assured" by statisticians, whereas the figures in the police data are constantly being updated, providing a "snap-shot" of crimes.

As a result of this report Surrey Police said it was re-submitting its records to the database: "As a result of the inaccuracies in the data, having been identified through this inquiry, Surrey Police is re-submitting its data to get this corrected."

## Get the data

* Data can be downloaded from [police.data.uk](https://data.police.uk/data/)
* [CSV: Outcomes by police force 2012-2016](https://github.com/BBC-Data-Unit/unsolved-crime/blob/master/outcomes_by_force.csv)
* [CSV: Outcome totals 2012-2016](https://github.com/BBC-Data-Unit/unsolved-crime/blob/master/outcomes_totals_2012-2016.csv)
* [CSV: Outcomes by year, police force, and outcome 2012-2016](https://github.com/BBC-Data-Unit/unsolved-crime/blob/master/crime%20outcomes%20by%20category%20force%20year%202012-16.csv)

## Visualisation

* Bar chart: Proportion of different crimes going unsolved (shown above)
* List: No suspect identified - Which force uses it most by crime type?
* Pie chart: Crimes by outcome (%), England and Wales, 2015-2016

## Analysis

The latest archive of data was downloaded from police.data.uk and then combined using command line tools, and uploaded to Google BigQuery. We could then run SQL queries against the data to answer questions and generate aggregate datasets. 

The analysis included the use of both multiple regression analysis and correlation to establish how strongly the composition of crimes in a given force influenced the ratio of unsolved crimes. [This is explained here](https://github.com/BBC-Data-Unit/unsolved-crime/blob/master/regression.md).

## Impact and pick up by other organisations

The Press Association picked up the story and distributed it to a number of news organisations. It was also reported across local radio. Other examples include:

* *The Times*: [Case closed: police write off unsolved crime](https://www.thetimes.co.uk/article/case-closed-police-write-off-unsolved-crime-7m9l69t3s)
