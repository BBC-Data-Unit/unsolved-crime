# Using multiple regression to test the relationship between composition of crimes and rate of unsolved

The proportion of crimes with no suspect identified varies by force. However, some of this variance will be due to differences in the types of areas, and therefore crimes, that each force deals with. For example, if one force has to deal with more bicycle thefts, and that type of crime is more likely  to be unsolved, that will affect the force's overall rate.

To test how much of the variation of outcome might be accounted for by variation of crime type, we undertook a multiple regression analysis. 

Regression establishes the strength (or weakness) of the relationship between two variables: for example, years spent smoking vs proportion developing cancer. Multiple regression analysis does this for multiple variables. For example:

% burglaries vs % no suspect
% drugs vs % no suspect

First, then we had to compile the data for each. This was done by creating pivot tables of crimes by force and outcomes by force, and then calculating % of total by force

Next, activate the Analysis Toolpak in Excel and in the Data tab select Data Analysis > Regression

[You can see the data showing proportion of crimes per force, and no suspect identified rates by force, in the first sheet here](https://github.com/BBC-Data-Unit/unsolved-crime/blob/master/regression_analysis_crime_unsolved.xlsx). The second sheet shows the multiple regression analysis.

The Multiple R is .83 which is significant, and means that when combined there is indeed a relationship between crime % and $ no suspect identified

But notably, no *single* crime type has a significant enough correlation: this tells us that only the *overall* composition of crimes has that effect.
