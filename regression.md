# Using multiple regression to test the relationship between composition of crimes and rate of unsolved

The proportion of crimes with no suspect identified varies by force. However, some of this variance will be due to differences in the types of areas, and therefore crimes, that each force deals with. For example, if one force has to deal with more bicycle thefts, and that type of crime is more likely  to be unsolved, that will affect the force's overall rate.

To test how much of the variation of outcome might be accounted for by variation of crime type, we undertook a multiple regression analysis. 

Regression establishes the strength (or weakness) of the relationship between two variables: for example, years spent smoking vs proportion developing cancer. Multiple regression analysis does this for multiple variables. For example:

* Percentage burglaries vs percentage no suspect
* Percentage drugs vs percentage no suspect

First, then, you need compile the data for each. (This was done by creating pivot tables of crimes by force and outcomes by force, and then calculating % of total by force.)

Next, activate the Analysis ToolPak in Excel (by going to **Tools > Excel Add-ins...** and ticking the Analysis ToolPak box) and in the Data tab select Data Analysis > Regression. 

The Y series is the cells containing the dependent variables (% unsolved); the X series is the cells containing the independent variables (the various crime rates). If you include the column headings, tick the *Labels* box and it will use those in the analysis.

[You can see the data showing proportion of crimes per force, and no suspect identified rates by force, in the first sheet here](https://github.com/BBC-Data-Unit/unsolved-crime/blob/master/regression_analysis_crime_unsolved.xlsx). The second sheet shows the multiple regression analysis. And a third sheet shows correlation between each column - in particular correlation between each crime proportion and the 'no suspect identified' rate.

The Multiple R ("multiple correlation coefficient") is 0.83 which is significant, and means that when combined there is indeed a relationship between crime composition and the percentage no suspect identified.

The R Square ("coefficient of determination") is 0.69, or 69%. This means that 69% of the variation in 'no suspect identified' rates is explained by the independent variables, i.e. the composition of crimes in that area.

But notably, no *single* crime type has a significant enough correlation. When correlation is calculated individually (i.e. not as part of a multiple regression and so not controlling for other factors), the strongest is vehicle crime at 0.48: this tells us that only the *overall* composition of crimes has a significant effect. 

Multiple regression tells us something else: it allows us to control for multiple independent variables (factors that might affect the focus of our analysis, or the dependent variable). Here's a useful example [from statsoft](http://www.statsoft.com/Textbook/Multiple-Regression#cunique):

> "You would probably find a significant negative correlation between hair length and height in the population (i.e., short people have longer hair). At first this may seem odd; however, if we were to add the variable Gender into the multiple regression equation, this correlation would probably disappear. This is because women, on the average, have longer hair than men; they also are shorter on the average than men. Thus, after we remove this gender difference by entering Gender into the equation, the relationship between hair length and height disappears because hair length does not make any unique contribution to the prediction of height, above and beyond what it shares in the prediction with variable Gender. Put another way, after controlling for the variable Gender, the partial correlation between hair length and height is zero."

Theft from the person is the only type of crime to have a P-value above 0.05; all the others are <0.05 - significant.

Robbery has the biggest coefficient, at -31. This *broadly* means that an additional 1 percentage point of robbery decreases the percentage points 'no suspect identified' by 31 points. That's quite a dramatic relationship, but when you look at the data you'll see that robbery has a very small range of between 0% and 2%. Offer coefficients also have to be factored in, as well as the 'intercept' value, as part of an overall calculation. Put another way, these coefficients are used with the intercept value to *predict* what the dependent variable ('no suspect identified') will be when given a collection of values for the independent variables. 


