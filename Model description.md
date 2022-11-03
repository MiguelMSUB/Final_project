## Exploring and processing the data for Supervise Machine Learning 

Before data modeling a final dataset is determined. To get that, further pre-processing is required before textual data is used for any data modeling. A summary of the actions required to complete that is featured below:

![data processing 1](https://user-images.githubusercontent.com/106939511/199647220-160c61c8-4400-4bf0-8b0e-93803fecbda4.png)


1. Data is pulled from available sources. It is important that the data sources available are trustworthy and well-built so the data collected 

2. The purpose of this step is to eliminate bad data (redundant, incomplete, or incorrect data) and begin to create high-quality data for the best business intelligence. During this process we answered this questions: what data is available, what data is missing, what data can be removed. 

3. The clean data is then entered into its destination, and translated into a language that it can understand

4. During this stage, the data inputted to the computer in the previous stage is processed for interpretation. Processing is done using machine learning algorithms

5. During the interpretation stage, the information resulted is translated, readable, and often in the form of graphs, videos, images, plain text, etc.

6. The final stage of data processing is storage. Once all the data has been processed, it is important to storage for future use .

## Data processing  on job fake prediction


1.One of the tasks involved in data preparation for machine learning is to convert textual data into numerical data.Categorical and text data must therefore be converted to numerical data for use in machine learning.

Our dataset includes the following columns:

![data processing 2](https://user-images.githubusercontent.com/106939511/199647626-c63ffe41-5c67-4b6c-8f6f-e9e1a78ecb5d.png)


2. To use **Scikit-learn’s machine learning algorithms** (LabelEncoder), the categorical features (*employment_type, required _experience, required_education and industry) will have to be converted into numbers*). *This process is called encoding.*  
3. The last step in our data processing will be clean up (drop)  the unnecessary columns (all text columns).


## Feature engineering and preliminary feature selection

Feature engineering is the process of selecting, manipulating and transforming the data to create features that would make machine learning algorithms works. If the feature engineering is done correctly, then the predictive power  of the machine learning  algorithms increases.

In simple words what we are doing in this step is 
- Prepare the proper input dataset, compatible with the machine learning algorithm requirements.
- Improve the performance of machine learning models.

After performing the data processing, our clean data base includes the following features and next to them the amount of their unique input. Based on the initial analysis during the cleaning process, this project will use a dataset with these features for the final analysis:

![features](https://user-images.githubusercontent.com/106939511/199647873-aa28be1f-40b0-4a2d-bb39-854908160372.png)

### Feature Selector usage

Nevertheless we knwo that the feature selection requires experience to determine the best features to train our model, probably we are not selecting the best set of data then we are going further in processing and in order to improve the Feature Engineering Process in our project, we will use a tool created for feature selection in Python: **FeatureSelector class** for selecting features to remove from our clean dataset [available on Github](https://github.com/WillKoehrsen/feature-selector/blob/master/Feature%20Selector%20Usage.ipynb)

![feature selection](https://user-images.githubusercontent.com/106939511/199648416-95aa4dfa-5128-415f-8f1d-4caa5522d689.png)


The function that we will use is the **Collinear Features**.  The identify_collinear method finds collinear features based on a specified correlation coefficient value. For each pair of correlated features, it identifies one of the features for removal (since we only need to remove one).

Result: We will be able to access the entire list of correlated features that will be removed, or see the highly correlated pairs of features in a dataframe. 

Visualization: A heatmap that shows all the features that have at least one correlation above the threshold

The following heatmap is an example of what we will get onc we perform this function in our data set:

![heatmap](https://user-images.githubusercontent.com/106939511/199648986-8e9514e1-3b35-4bcc-a652-00801015dcc6.png)


## Data training and testing sets

Once we have processed and improved our data set, we will be ready to train and test this data. The train-test split procedure is used to estimate the performance of machine learning algorithms when they are used to make predictions on data not used to train the model. It is a fast and easy procedure to perform, the results of which allow us to compare the performance of machine learning algorithms for our predictive modeling problem. 

Here the summary of the train-test procedure that we will use in our data set:

1. Import dependencies

![1 IMPORT](https://user-images.githubusercontent.com/106939511/199649932-2078a874-287b-4e4e-b2e3-96c0b48b9126.png)


2. Read encoded data set : jobs_data_encoded.csv

![2  READ](https://user-images.githubusercontent.com/106939511/199649955-2969babb-0d07-44ac-8374-63fef179a633.png)


3. Split our dataset into features (or inputs) and target (or outputs). The features set, X, will be a copy of the df_job DataFrame without the “fraudulent” column. These features are all the variables that help determine whether a job posting should be discarded because is a fraud.

![3 SAVE](https://user-images.githubusercontent.com/106939511/199649972-2b443d7e-304b-44f6-8cef-80c4e5f0c673.png)


4. Generate the target set data: The target set is the “fraudulent” column, indicating whether or not a job posting is real (0) or fake (1). The following code helps to generate the target set data.

![4 GENERATE](https://user-images.githubusercontent.com/106939511/199649994-f30e809a-fb72-4455-8897-ed4c9ccac31f.png)


5. Split the features and target sets into training and testing sets. This will help determine the relationships between each feature in the features training set and the target training set, which we'll use to determine the validity of our model using the features and target testing sets. By default, training and testing data sets are 75% and 25%, respectively, of the original data. 

![5 SPLIT](https://user-images.githubusercontent.com/106939511/199650007-ff077e03-5bcc-456a-bc82-96dfcd1bf0d4.png)


6.Scale the training and test the data: the purpose of scaling is for accelerating learning process. Features may have different scales. One maybe from 1 to 10 and one may be from -100 to 1000. Using normalization, we make the scale of them the same as each other, helps accelerate the learning process. 

![6 SCALE](https://user-images.githubusercontent.com/106939511/199650025-4de97e31-4fb8-459a-a7b2-1212e495269e.png)




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


