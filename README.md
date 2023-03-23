# Binary Classification with a Pulsar Dataset

This project was done as part of a [Kaggle competition](https://www.kaggle.com/competitions/playground-series-s3e10/) to apply our machine learning training on an interesting question and to sharpen our skills further. 

The competition data is synthetically generated from a deep learning model trained on the [Pulsar Classification dataset](https://www.kaggle.com/datasets/brsdincer/pulsar-classification-for-class-prediction). Each data point is a collection of observations from a star (some pulsar, some not) and the target is to predict whether the star is a pulsar.

## About the data

The training dataset included about 117k rows (stars) and 8 columns (various observations from the stars) with no missing values. Main challenge with this dataset was a moderate imbalance in classes:
> **Pulsar: 9%**

> Not pulsar: 91%

It was important to take this imbalance into account and that is why we used Strattified K-Folds as an appropriate cross-validation method. 

## Approach & Analysis

As the first step, an extensive exploratory data analysis (EDA) was done with the help of visualization to gather insights into this dataset. Since the dataset is generated from a smaller dataset, we explored whether including the original dataset would improve the predictions but it was not the case. We found that even though some variables appeared to be highly correlated with the target class, excluding some columns would lead to a significant information loss without any benefits in the form of improved predictions. The Principal Component Analysis supported this insight as well and all the data was included in the analysis. Other standard pre-processing approaches such as scaling the variables and feature engineering by including polynomial features did not improve the performance. 

Our analysis employed various ML models including random forest, gradient boosting models, and neural networks. At a more advanced level, we used Optuna for hyperparameter optimization and Autogluon to generate a robust ensemble based on the various models we built. In this particular problem, gradient boosting models performed the best, in particular CatBoost, and we were able to score in the top 25% of the competition. 

## Notebooks

In this repository, we include the notebooks for each major part of the project:

1. [EDA](EDA.ipynb)
2. [Pre-processing and Feature engineering](preprop_feat_eng.ipynb)
3. [Random Forest and Gradient Boosting models](RF_GB.ipynb)
4. [GB models with Optuna search](optuna.ipynb)
5. [Neural Network](NN.ipynb)
6. [Ensemble approcah with Autogluon](agl.ipynb)



We find those pulsars like they're Harris tweed jackets in a Goodwill rack!

