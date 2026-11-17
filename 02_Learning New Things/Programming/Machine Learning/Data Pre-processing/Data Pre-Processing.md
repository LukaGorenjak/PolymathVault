## Importance of Train-Test Data Split

We usually split our data 80% training and 20% testing. That is because if we use for example linear regression with 80% of the data we can that use the same model on the last 20% and since the model has no ideas of results and we have them we get feedback on how our model is doing.

## Imputing missing data

## Feature Scaling

Used so features don’t overpower other features so the ML doesn’t skip it.  
Always applied on columns.  
Not always used on all ML models.  
Not applied to dummy variables or binary values.  
When dependent variable takes a high values regards to others you have to apply it.  
Always applied after splitting the data to prevent information leakage to the test set until the training is done.  
You have to use the same scalar as you did in x_train on x_test too.

**Standardization:** (x - mean(x)) / (standard deviation(x))  
**Result:** -3,+3  
Works all the time  
To apply it to X_test first get the standard deviation of x_train and apply it to transform all the values in X_train and then with the same mean and stand. deviation to scale the values of X_test.

**Normalization:** (x - min(x)) / (max(x) - min(x))  
**Result:** 0, 1  
When you have normal distribution in most of your features

### Inverse Feature Scaling

why?  
sc_y.inverse_transform(regressor.predict(sc_X.transform([[6.5]])).reshape(-1,1))

## Encoding Categorical Data

Why? How? When? With what?