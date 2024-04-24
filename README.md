# Car_Pricing
What drives the price of a car?

### Business Understanding

In this assignment, the goal is to utilize a large data set of used car sales to create an optimized regression model that can both predict the correct price for used cars and determine which factors are most important in determining that price. The dealers can use this information to purchase cars that will hopefully have the highest resale values.

### Data Understanding

I opened the spreadsheet and scrolled down to get a general feel for the data. I looked at the categories and began to think about their relevance and utility. Right off the bat, it is very apparent that there are a large number of empty cells, so I will need to drop columns. Here is how I made those decisions:

1. I decided that regional data will not be helpful. Dealerships generally do not have profit margins high enough to purchase vehicles from far away, so they will have relatively little ability to select vehicles based on regional data.
2. Included identifiers may be dropped, as that data is captured in the index
3. Columns that have categorical responses with a large number of categories can also be dropped, as they are not easy to encode, and large numbers of categories with relatively few entries are not useful for extracting patterns

