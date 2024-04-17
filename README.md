# Starbucks Capstone Challenge:
Understanding our customers is the key providing them a good service and sustain a profitable business. To understand them well, we need to pay attention on their purchase behaviour. One way we can collect and analyse their purchasing behaviour through an app, then identify their needs based on demographics.

## Table of Contents:
1. [Project Overview](https://github.com/Aditya-Kashyap/starbucks-capstone-challenge#Project-Overview)
2. [Problem Statement / Metrics](https://github.com/Aditya-Kashyap/starbucks-capstone-challenge#Problem-Statement-/-Metrics)
3. [Installation](https://github.com/Aditya-Kashyap/starbucks-capstone-challenge#Installation)
4. [Project Motivation](https://github.com/Aditya-Kashyap/starbucks-capstone-challenge#Project-Motivation)
5. [File Descriptions](https://github.com/Aditya-Kashyap/starbucks-capstone-challenge#File-Descriptions)
6. [Analysis Summary](https://github.com/Aditya-Kashyap/starbucks-capstone-challenge#Analysis-Summary)

## Project Overview:

Customer satisfaction drives business success and data analytics provides insight into what customers think. For example, the phrase "360-degree customer view" refers to aggregating data describing a customer's purchases and customer service interactions.

The Starbucks Udacity Data Scientist Nanodegree Capstone challenge data set is a simulation of customer behavior on the Starbucks rewards mobile application. Periodically, Starbucks sends offers to users that may be an advertisement, discount, or buy one get on free (BOGO). An important characteristic regarding this dataset is that not all users receive the same offer.

This data set contains three files. The first file describes the characteristics of each offer, including its duration and the amount a customer needs to spend to complete it (difficulty). The second file contains customer demographic data including their age, gender, income, and when they created an account on the Starbucks rewards mobile application. The third file describes customer purchases and when they received, viewed, and completed an offer. An offer is only successful when a customer both views an offer and meets or exceeds its difficulty within the offer's duration.

## Problem Statement / Metrics:

The problem that I chose to solve is to build a model that predicts whether a customer will respond to an offer. My strategy for solving this problem has four steps. First, I will combine the offer portfolio, customer profile, and transaction data. Each row of this combined dataset will describe an offer's attributes, customer demographic data, and whether the offer was successful. Second, I will assess the accuracy and F1-score of a naive model that assumes all offers were successful. This provides me a baseline for evaluating the performance of models that I construct. Accuracy measures how well a model correctly predicts whether an offer is successful. However, if the percentage of successful or unsuccessful offers is very low, accuracy is not a good measure of model performance. For this situation, evaluating a model's precision and recall provides better insight to its performance. I chose the F1-score metric because it is "a weighted average of the precision and recall metrics". Third, I will compare the performance of logistic regression, random forest, and gradient boosting models. Fourth, I will refine the parameters of the model that has the highest accuracy and F1-score.

## Installation:
This project requires **Python 3.x** and the following Python libraries installed:

- [NumPy](http://www.numpy.org/)
- [Pandas](http://pandas.pydata.org)
- [matplotlib](http://matplotlib.org/)
- [seaborn](https://seaborn.pydata.org/installing.html)
- [scikit-learn](http://scikit-learn.org/stable/)
- [Jupyter-Notbook](https://jupyter.org/install.html)

Or you could install [Anaconda](https://www.anaconda.com/products/individual), a pre-packaged Python distribution that contains all 
of the necessary libraries and software for this project.

## Project Motivation:
This data set contains simulated data that mimics customer behavior on the Starbucks rewards mobile app. Once every few days, 
Starbucks sends out an offer to users of the mobile app. Using this dataset I have built a model that predict whether customers will respond to 
offers or not.

The Starbucks Udacity Data Scientist Nanodegree Capstone challenge data set contains simulated data that mimics customer behavior on the Starbucks rewards mobile app. Periodically, Starbucks sends out an offer to users of the mobile app. An offer can be merely an advertisement for a drink or an actual offer such as a discount or BOGO (buy one get one free). However, some users might not receive any offer during certain weeks. Using the data, I aim to :

    1. Gain understanding what types of customer characteristics and demographics are there.
    2. What offer should be sent to each customer ?
    3. How well can we predict customer response to offer ?

## File Descriptions:

The data is contained in three files:
* portfolio.json - containing offer ids and meta data about each offer (duration, type, etc.).
* profile.json - demographic data for each customer.
* transcript.json - records for transactions, offers received, offers viewed, and offers completed.

Here is the schema and explanation of each variable in the files:

### portfolio.json:
* id (string) - offer id
* offer_type (string) - type of offer ie BOGO, discount, informational
* difficulty (int) - minimum required spend to complete an offer
* reward (int) - reward given for completing an offer
* duration (int) - time for offer to be open, in days
* channels (list of strings)

### profile.json:
* age (int) - age of the customer
* became_member_on (int) - date when customer created an app account
* gender (str) - gender of the customer (note some entries contain 'O' for other rather than M or F)
* id (str) - customer id
* income (float) - customer's income

### transcript.json:
* event (str) - record description (ie transaction, offer received, offer viewed, etc.)
* person (str) - customer id
* time (int) - time in hours since start of test. The data begins at time t=0
* value - (dict of strings) - either an offer id or transaction amount depending on the record

## Analysis Summary:
Analysis complete summary is present [here](https://medium.com/@adi.inhere/starbucks-capstone-challenge-3ea1c3b70d7d) in a Medium Post.

## Acknowledgements
The dataset used in this project contains simulated data that mimics customer behavior on the Starbucks rewards mobile app. [Starbucks® Rewards program: Starbucks Coffee Company](https://www.starbucks.com/rewards/).

## References
- [360-degree customer view definition](https://searchsalesforce.techtarget.com/definition/360-degree-customer-view)  
- [Model accuracy definition](https://developers.google.com/machine-learning/crash-course/classification/accuracy)  
- [F1-score definition](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.f1_score.html)  
- [Evaluation of models with unbalanced classes](https://www.manning.com/books/practical-data-science-with-r)  
- [Beyond accuracy precision and recall](https://towardsdatascience.com/beyond-accuracy-precision-and-recall-3da06bea9f6c)  
- [Logistic regression detailed overview](https://towardsdatascience.com/logistic-regression-detailed-overview-46c4da4303bc)  
- [Random forest algorithm](https://towardsdatascience.com/the-random-forest-algorithm-d457d499ffcd)  
- [Gradient boosting algorithm](https://machinelearningmastery.com/gentle-introduction-gradient-boosting-algorithm-machine-learning/)  
- [Multi label binarizer](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.MultiLabelBinarizer.html#sklearn.preprocessing.MultiLabelBinarizer)  
- [Why one hot encode data in machine learning?](https://machinelearningmastery.com/why-one-hot-encode-data-in-machine-learning/)  
- [Using categorical data with one hot encoding](https://www.kaggle.com/dansbecker/using-categorical-data-with-one-hot-encoding)  
- [Is there a rule-of-thumb for how to divide a dataset into training and validation sets?](https://stackoverflow.com/questions/13610074/is-there-a-rule-of-thumb-for-how-to-divide-a-dataset-into-training-and-validatio)  
- [The use of feature scaling in scikit-learn](https://stackoverflow.com/questions/51660001/the-use-of-feature-scaling-in-scikit-learn)  
- [Machine learning evaluate classification model](https://www.ritchieng.com/machine-learning-evaluate-classification-model/)
- [Hyperparameter tuning the random forest in Python using scikit-learn](https://towardsdatascience.com/hyperparameter-tuning-the-random-forest-in-python-using-scikit-learn-28d2aa77dd74)  
- [Random forest feature importances](https://towardsdatascience.com/running-random-forests-inspect-the-feature-importances-with-this-code-2b00dd72b92e)  
- [Gentle introduction to the bias variance trade-off in machine learning](https://machinelearningmastery.com/gentle-introduction-to-the-bias-variance-trade-off-in-machine-learning/)  
- [Decision tree or logistic regression?](https://datascience.stackexchange.com/questions/6048/decision-tree-or-logistic-regression)  
- [Random forests ensembles and performance metrics](http://blog.citizennet.com/blog/2012/11/10/random-forests-ensembles-and-performance-metrics)  
- [A Kaggle master explains gradient boosting](http://blog.kaggle.com/2017/01/23/a-kaggle-master-explains-gradient-boosting/)  
- [Gradient boosting tree vs random forest](https://stats.stackexchange.com/questions/173390/gradient-boosting-tree-vs-random-forest)  
- [How can the performance of a Gradient Boosting Machine be worse than Random Forests](https://www.quora.com/How-can-the-performance-of-a-Gradient-Boosting-Machine-be-worse-than-Random-Forests)  
- [Overfitting in machine learning](https://elitedatascience.com/overfitting-in-machine-learning)
- [Rotate axis text in Python matplotlib](https://stackoverflow.com/questions/10998621/rotate-axis-text-in-python-matplotlib)
- [Analytic dataset definition](https://github.com/jtleek/datasharing)
- [Set order of columns in pandas DataFrame](https://stackoverflow.com/questions/41968732/set-order-of-columns-in-pandas-dataframe)  
- [Python pandas selecting rows whose column value is null none nan](https://stackoverflow.com/questions/40245507/python-pandas-selecting-rows-whose-column-value-is-null-none-nan)  
- [scikit-learn MultiLabelBinarizer](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.MultiLabelBinarizer.html#sklearn.preprocessing.MultiLabelBinarizer)  
- [Python round up to the nearest ten](https://stackoverflow.com/questions/26454649/python-round-up-to-the-nearest-ten)  
- [datetime strptime in Python](https://stackoverflow.com/questions/44596077/datetime-strptime-in-python)  
- [How to match exact multiple strings in Python](https://stackoverflow.com/questions/4953272/how-to-match-exact-multiple-strings-in-python)
- [How to determine a Python variable's type](https://stackoverflow.com/questions/402504/how-to-determine-a-python-variables-type)
- [Pandas DataFrame settingwithcopywarning a value is trying to be set on a copy](https://stackoverflow.com/questions/49728421/pandas-dataframe-settingwithcopywarning-a-value-is-trying-to-be-set-on-a-copy)  
- [Should binary features be one hot encoded](https://stackoverflow.com/questions/43515877/should-binary-features-be-one-hot-encoded)  
- [Select pandas DataFrame rows and columns using iloc, loc and ix](https://www.shanelynn.ie/select-pandas-dataframe-rows-and-columns-using-iloc-loc-and-ix/)  
- [How to merge two dictionaries in a single expression](https://stackoverflow.com/questions/38987/how-to-merge-two-dictionaries-in-a-single-expression)  
- [Python to print out status bar and percentage](https://stackoverflow.com/questions/3002085/python-to-print-out-status-bar-and-percentage)  
- [Progress bar introduction](https://progressbar-2.readthedocs.io/en/latest/index.html#introduction)  
- [Progress bar documentation](https://progressbar-2.readthedocs.io/en/latest/progressbar.bar.html)  
- [Reversing one hot encoding in pandas](https://stackoverflow.com/questions/38334296/reversing-one-hot-encoding-in-pandas)  
- [If else in a list comprehension](https://stackoverflow.com/questions/4406389/if-else-in-a-list-comprehension)  
- [Pandas DataFrame groupby two columns and get counts](https://stackoverflow.com/questions/17679089/pandas-dataframe-groupby-two-columns-and-get-counts)  
- [Converting a pandas groupby object to DataFrame](https://stackoverflow.com/questions/10373660/converting-a-pandas-groupby-object-to-dataframe)  
- [Change order of columns in stacked bar plot](https://stackoverflow.com/questions/32015669/change-order-of-columns-in-stacked-bar-plot)  
- [Print Python version](https://stackoverflow.com/questions/1252163/printing-python-version-in-output)  
