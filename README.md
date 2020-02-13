# Please-Don-t-Overfit
# Please! Don't Overfit
## Introduction
### Modeling Smaller datasets <br>
One of the forefront challenges in any machine learning project is smaller datasets or unavailabilty of the data.Ofcourse collecting more data is an obvious solution but may be not a practical one always. <br>
Smaller datasets for training leads to higher bias or ***overfitting***.
The main agenda of this notebook is to use different types of Algorithms to do ***feature extraction*** in order avoid overfitting of the data.
### List of files in the repository
1. Please! Dont Oerfit.ipynb - The Jupiyter notebook with all the preprocessing ang modeling o the data
2. Train.csv - The input dataset of 250 rows.
## About Data
The dataset used in this notebook is taken from the Kaggle dataset.The training data comprises of only **250 examples** with whooping **300 features**.The **label/output** is a binary classifiaction with either a value of **0 or 1**.Neither the input nor the output has index or column names and makes absolutely no sense.The dataset has no null values in any feature/row.
## Exploratory Data Analysis
Before building my predictive models, I undertook exploratory data analysis to see some characteristics of my dataset
### 1. % Distribution of the output/labels
![EDA1](https://github.com/A-Aparna/Please-Don-t-Overfit/blob/master/Images/EDA_label.jpg)<br>
We can see that the distribution of the labels is skewed to some extent and we need to take precautions while training the data.
### 2. correlation between the different features
![EDA12](https://github.com/A-Aparna/Please-Don-t-Overfit/blob/master/Images/EDA_correlation.jpg) <br>
As expected there is no visible patter we can see and the correlation matrix looks like a crazy puzzle without any obvious recognizable pattern.
## Modeling
Standardizing the data In the following step the data is standardized by using the SKLearn libraries.In standardization,we standardize the scale for each variable so that we can compare it on the same scale.
Training and Validation set: The data in the training dataset is not manually divided into training and validation set.Instead Stratified K Fold method is used.
1. This divides the data set into n splits.
2. one split of data is used for validation and n-1 splits are used for training
3. The procedure is iterated till each of the n split is used for validation

A generic function is written which will be called by each algorithm for training and validating.For each model the ROC score is calculated for each validation split.
This ROC score is used to select the best fit model!The scores are as follows:

First Header | Second Header
------------ | -------------
Content from cell 1 | Content from cell 2
Content in the first column | Content in the second column

This method involves extracting the featured from the dataset which contains the most discrimatory infromation of the dataset.So the best curve is fitted on the subset of the dataset and not on the original dataset.Using the following methods we will be modeling on the dataset containing the reduced number of features and not on all the 300 features.We have already implemented this on Lasso tool,Extra Tree classifier and Random Tree classifier in this Notebook.

##Feature Extraction
