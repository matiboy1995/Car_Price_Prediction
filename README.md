# Car_Price_Prediction
Predicting the price of cars from Craig's list data:
My project is about predicting the price of used cars using a type of computer program called a "machine learning model". To do this, I used data from Craigslist, which is a popular website in the USA where people can buy and sell used items. By analyzing this data, the model can learn patterns and relationships between the different features of a car (like its age, make, model, and mileage) and its price. Once the model has learned these relationships, it can then use them to predict the price of a car that it hasn't seen before. This can be useful for people who are looking to buy or sell a used car, as it can help them understand what a fair price might be.

## DATA
The data being used is a dataset of used vehicles for sale that was scraped from Craigslist in the United States. The dataset includes information on every used vehicle entry on Craigslist, and is updated every few months. The data contains a wide range of information including the price, condition, manufacturer, latitude/longitude, and 18 other categories. 

Source: https://www.kaggle.com/datasets/austinreese/craigslist-carstrucks-data?resource=download

See data_card for more details.

## MODEL 
The machine learning model being used is Random Forest. It is a type of ensemble learning algorithm that is commonly used for regression and classification tasks. The algorithm works by constructing multiple decision trees at training time and outputs the mode (classification) or mean prediction (regression) of the individual trees.

I selected this model because it was A) used in the course previously - a requirement for model selection,  B) contains a number of hyperparameters - hyperparameter optimization was a requirement of the course assignement, and C) it's more explainable than some models, so we can interpret feature importance.

## HYPERPARAMETER OPTIMSATION - TODO
Description of which hyperparameters you have and how you chose to optimise them. 

GRIDSEARCH FROM :

para_grids = {
            "n_estimators" : [10,50,100],
            "max_features" : ["auto", "log2", "sqrt"],
            'max_depth' : [4,5,6,7,8,9,15],
            "bootstrap"    : [True, False]
        }

## RESULTS - TODO
A summary of your results and what you can learn from your model 

You can include images of plots using the code below:
![Screenshot](image.png)
