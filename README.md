# Car_Pricing
What drives the price of a car?

### Business Understanding

In this assignment, the goal is to utilize a large data set of used car sales to create an optimized regression model that can both predict the correct price for used cars and determine which factors are most important in determining that price. The dealers can use this information to purchase cars that will hopefully have the highest resale values.

### Data Understanding

I opened the spreadsheet and scrolled down to get a general feel for the data. I looked at the categories and began to think about their relevance and utility. Right off the bat, it is very apparent that there are a large number of empty cells, so I will need to drop columns. Here is how I made those decisions:

1. I decided that regional data will not be helpful. Dealerships generally do not have profit margins high enough to purchase vehicles from far away, so they will have relatively little ability to select vehicles based on regional data.
2. Included identifiers may be dropped, as that data is captured in the index
3. Columns that have categorical responses with a large number of categories can also be dropped, as they are not easy to encode, and large numbers of categories with relatively few entries are not useful for extracting patterns

### Data Preparation
See the Data Preparation section of the Jupyter notebook

### Modeling
See the Modeling section of the Jupyter notebook

### Evaluation
I was able to produce 3 different models that all performed similarly well, within 0.2% of each other. I tried a variety of alpha values, and also tried dropping many combinations of columns that were deemed least important in the model, and the models above are the best performing versions of each type. Test MSEs are all higher than Train MSEs, which is a good sign.

For pricing, the square root of the MSE score is approximately $8950. Comparing that to an average price of $16,022 for the cars in the cleaned dataset, we can see that the price predicting power of the models is somewhat limited. That said, the model can be used to help determine what price to offer on potential purchases. I would advise to use the predicted price as a starting point but to generally err low for the actual offer.

On the other hand, the model was able to determine which attributes are the most important contributors to the car's price. This is very useful information and each potential client will be able to use it to determine how to tailor their pricing to their own particular market. Here are the attributes ranked:

The most important attributes are

1. Odometer         29.3%
2. Year             10.2%
3. Cylinders        7.5%
4. Fuel Type        7.4%
5. Car body type    4.4%

The least important attributes are

6. Transmission     3.0%
7. Manufacturer     2.8%
8. Drivetrain       2.3%
9. Condition        0.7%
10. Title status    0.4%
