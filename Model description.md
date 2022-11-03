





## Determine which supervised learning algorithm is best used for our data set 

The following is a more detailed explanation of the models that we have selected for this project:

**Logistic regression model:** 

*How does it work?*

Logistic regression model is a machine learning technique used for classification or prediction in data sets which have many features, but where most of them have little value and should be ignored. This model analyzes relationships between these input features (variables) and then when presented with a new sample, mathematically will determine its probability of beloging to a class . The output of this model is always binary outcomes (0/1, True/False, Yes/No ), that means there are only two possible outcomes. In our project we are expecting to get one of two answers: the job posting is fake or is not fake. 

*Why this specific model?*

Motivation: Logistic regression is easier to implement, interpret, and very efficient to train.


**Balance Random Forest Classifier** 

*How does it work?*

Random forest is a technique used in modeling predictions and behavior analysis and is built on decision trees. It contains many decision trees representing a distinct instance of the classification of data input into the random forest. The random forest technique considers the instances individually, taking the one with the majority of votes as the selected prediction.

Each tree in the classifications takes input from samples in the initial dataset. Features are then randomly selected, which are used in growing the tree at each node. Every tree in the forest should not be pruned until the end of the exercise when the prediction is reached decisively. In such a way, the random forest enables any classifiers with weak correlations to create a strong classifier.

![random-forest](https://user-images.githubusercontent.com/106939511/199645586-66b10cfa-0ca7-4d22-bf23-7c5f1fcd16f6.png)

[Image source](https://medium.com/analytics-vidhya/a-random-forest-classifier-with-imbalanced-data-7ef4d9ebedb8)

*Why this specific model?*

Motivation: Among all the available classification methods, random forests provide the highest accuracy. The random forest technique can also handle big data with numerous variables running into thousands. It can automatically balance data sets when a class is more infrequent than other classes in the data. The method also handles variables fast, making it suitable for complicated tasks.

## Improve model performance

Class imbalance is a common problem in classification. It occurs when one class is much larger than the other class. Base on the previous analysis of our data set, we have discovered that it is very imbalance, most jobs are real, and few are fraudulent. Then we have choosen SMOTEENN as one of the most effective techniques to generate synthetic minority class samples. A balanced dataset should be able to generate better results.  This strategy is a combination of the oversampling the minority class and undersampling the majority class. This strategy will let us to increase the model performance even further.
SMOTEENN. 

  
## Evaluation of the performance of the machine learning model

We will built these machine learning models and trained them on some data, so now the question is what is the most accurate model that will help us to reduce the risk of the job applicant to fall on the scammers' tricks to get personal information from them as address, bank account details, social security number etc.  The following is a detail explanation of how to evaluate our model based on what we are expecting.

**Classification matrics:**

There are four types of outcomes that we can get from the confussion matrix:

a) True positives mean that we have predicted an observation that belongs to a class and it actually belongs to that class.

b) True negatives mean that we have predicted an observation that does not belong to a class and it actually does not belogn to that class.

c) False positives mean that we have predicted an observation that belongs to a class and it actually does not belong to that class

d) False negative mean that we have predicted an obervation that does not belong to a class and it actually belongs to that class

The following diagram illustrates the confusion matrix and how we can interpretate the data that we get from each model:

<img width="296" alt="confusion matrix" src="https://user-images.githubusercontent.com/106939511/199645236-da53bd33-3bc6-43f8-aef5-2aa2d23ce163.png">


The next step once we have classified is to look at the metrics:

a) *Accuracy:* that means the number of correctly classified data instances over the total numbers of data instances.

b) *Precision:* means from all the positive predictions, how many are really positive (false positives).

c) *Recall:* means from all the real positive data values, how many are predicted positive ( false negatives).

In our case of study we should evaluate **what is worse**, false positives or false negatives. Let's evaluate this by revising our case with the 2 undesirable scenarios:

**Scenario 1: Risky job posting classified as Non- Risky job posting**

**Scenario 2: Non- Risky job posting classsified as Risky job posting**

Between these two scenarios, the more undesirable will be Risky job posting classified as Non-Risky job posting bacause the applicant doesnt what to provide his/her information to people that will misuse it. Since the impact of errors caused by False positives is assessed to be more significant, it makes sense to select a model that has a few False positives as possible. In other words, we should use precision instead of recall.


