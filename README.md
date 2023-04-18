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

The hyperparameters used were:
-n_estimators: the number of trees in the forest for a random forest algorithm.
-max_features: the maximum number of features to consider when splitting a node in the decision tree. This parameter can take on the values "auto", "log2", or "sqrt", which correspond to different ways of selecting the maximum number of features.
-max_depth: the maximum depth of the decision tree.
-bootstrap: a Boolean flag that indicates whether bootstrap samples are used when building trees.

These were identified based on existing course material, and winning performance in regression problems related to car price prediction on kaggle

The purpose of creating a hyperparameter grid like this is to systematically explore different combinations of hyperparameters to find the best combination that leads to the best performance of the machine learning algorithm on a given task. This is typically done using a technique called grid search, where the algorithm is trained and evaluated on each combination of hyperparameters in the grid. The combination of hyperparameters that yields the best performance is then selected as the final set of hyperparameters for the algorithm.

Specific parameters utilised: 
para_grids = {
            "n_estimators" : [10,50,100],
            "max_features" : ["auto", "log2", "sqrt"],
            'max_depth' : [4,5,6,7,8,9,15],
            "bootstrap"    : [True, False]
        }
        
The output was:
RandomForestRegressor(bootstrap=False, criterion='friedman_mse', max_depth=15,
                      max_features='log2', random_state=42)        

## RESULTS

MAE: 5681.077861007316
RMSE: 8124.574066756829
R2 Score: 0.6347448554066124
------------------------------
RMSE Cross-Validation: 7954.379382945682
