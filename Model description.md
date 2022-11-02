# Machine learning: data processing, algorithms and techniques

Description of preliminary data preprocessing 

Data preprocessing is a process of preparing the raw data and making it suitable for a machine learning model. When creating a machine learning project, it is not always a case that we come across the clean and formatted data. And while doing any operation with data, it is mandatory to clean it and put in a formatted way. So for this, we use data preprocessing task.

Description of preliminary feature engineering and preliminary feature selection, including their decision-making process 

Description of how data was split into training and testing sets 

Explanation of model choice, including limitations and benefits





















There are several questions to keep in mind as you work through this segment:

Logistic regression model: 

How does it work?
Logistic regression model is a machine learning technique used for classification or prediction in data sets which have many features, but where most of them have little value and should be ignored. This model analyzes relationships between these input features (variables) and then when presented with a new sample, mathematically will determine its probability of beloging to a class . The output of this model is always binary outcomes (0/1, True/False, Yes/No ), that means there are only two possible outcomes. In our project we are expecting to get one of two answers: the job posting is fake or is not fake. 


Why this specific model?
Motivation: Logistic regression is easier to implement, interpret, and very efficient to train.


Balance Random Forest Classifier 

How does it work?
Random forest is a technique used in modeling predictions and behavior analysis and is built on decision trees. It contains many decision trees representing a distinct instance of the classification of data input into the random forest. The random forest technique considers the instances individually, taking the one with the majority of votes as the selected prediction.

Each tree in the classifications takes input from samples in the initial dataset. Features are then randomly selected, which are used in growing the tree at each node. Every tree in the forest should not be pruned until the end of the exercise when the prediction is reached decisively. In such a way, the random forest enables any classifiers with weak correlations to create a strong classifier.


Why this specific model?
Motivation: Among all the available classification methods, random forests provide the highest accuracy. The random forest technique can also handle big data with numerous variables running into thousands. It can automatically balance data sets when a class is more infrequent than other classes in the data. The method also handles variables fast, making it suitable for complicated tasks.


SMOTEENN


How does it work?
There are many methods to overcome imbalanced datasets in classification modeling by oversampling the minority class or undersampling the majority class. To increase the model performance even further, many researchers suggest combining oversampling and undersampling methods to balance the dataset better.


Why this specific model?
Motivation: because during the cleaning data, we discovered that the data set used in this project is very imbalanced, most jobs are real, and few are fraudulent. We have choosen SMOTEENN as one of the most effective techniques to generat synthetic minority class samples. A balanced dataset should be able to generate better results.  

Evaluation of the performance of the machine learning model

