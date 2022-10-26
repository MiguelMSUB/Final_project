# Final_project

# Table of Contents 

<!-- vscode-markdown-toc -->
* [Overview](#Overview)
* [Machine Learning](#Machine_Learning)

<!-- vscode-markdown-toc-config
	numbering=true
	autoSave=true
	/vscode-markdown-toc-config -->
<!-- /vscode-markdown-toc -->

# <a name='Overview'></a>Overview

The purpose of this project is to predict real or fake job postings. This topic was selected due to its relevancy to bootcamp graduates. 

The source of data for this analysis is from Shivam Bansal. 28 February 2020. Real/Fake Job Posting Prediction. Retrieved 20 October 2022 from https://www.kaggle.com/datasets/shivamb/real-or-fake-fake-jobposting-prediction.  

## Key Questions
* What are the primary indicators for fake job postings?
* Are fake job postings more common in certain parts of the US?

# <a name='Machine_Learning'></a>Machine Learning
### Model Choice - Supervised Learning

We will rely on supervised learning to predict whether a job posting is fraudulent, based on data from prior job postings. We’ll use a classification model because the target variable has two possible values: real or fake. When the classification model encounters new data, it will use features such as employment type, telecommuting, includes questions, and location to predict whether the job posting is real or fake. 

#### Algorithm(s)

* Logistic Regression - we will split the dataset into training and testing sets and then create a logistic regression model with specified arguments for solver, max_iter, and random_state. We’ll then train the model with the training data and use the x_test set to create predictions for y-values.  When the y-values (y-pred) are compared with the actual y-values (y_test), we’ll be able to determine if the predictions (real “0” or fake “1”) were correct. We’ll also use the sklearn.metrics.accuracy_score to determine how well our logistic regression model predicts.

* Random Forest – we’ll also use a random forest algorithm to sample the data and build several smaller, simpler decision trees. Each tree is simpler because it is built from a random subset of features. We will also be able to rank the features by their importance, which allows us to determine which features have the most impact on the decision.

* Additional Considerations - because the number of fraudulent listings is significantly smaller than the number of legitimate job postings, we may want to consider SMOTE and Edited Nearest Neighbors (ENN) algorithms to: 1) oversample the minority class with SMOTE and 2) clean the resulting data with an under sampling strategy.

