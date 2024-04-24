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

### Deployment

The nice thing about ranking the attributes by importance is that we can pass this information to each client and instruct them how to apply and tailor it to their own specific markets. The important thing for them to remember is that one-hot encoding shows that the column is important, but it does not mean that a higher number for that attribute is better. Their job is to itentify the preferences of their particluar market for each preferred attribute, and aim to purchase cars for resale that have strong scores in their markets preferred range for that attribute.

As a general example, we know that the number of cylinders a car has is one of the most important factors in determining its price. That said, customers at a dealership in a rural area may prefer 8-cylinder engines and customers in a urban area may prefer 4-cylinder engines. All our model tell us is that getting cars with this number right will appeal more to buyers than getting the condition right, but it doesn't necessarily tell us what the right number (or condition) is in their particular market. 

Overall, dealers should generally make more money on their used car sales if they:

1. Purchase cars that perform well in the important categories. Let's just call these "good cars".

2. Try to purchase "hidden gems". These are cars that are strong in the most important attributes but poor in less important categories. An example would be a newer car with low mileage that is in poor condition.

3. Try to purchase "fixer-uppers" at a low price. These are cars that perform poorly in unimportant categories but still perform ok in relevant categories. For these cars, they are worth buying at a good price and it is worth making an offer under the asking price. An example of this would be a car that is in very poor condition but is only 5 years old.

4. Avoid purchasing "false hope" cars. These perform well in unimportant categories but they do not do well in important categories. An example would be a car that is in good condition from a luxury manufacturer, but it has high mileage or is old. 
