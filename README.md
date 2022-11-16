![Headline](https://github.com/MiguelMSUB/Final_project/blob/3c993d68c8593d5380d99fb9155840085c03abf2/Images/Headline.png)

# Fake Job Predictions Final Project

# Table of Contents 

<!-- vscode-markdown-toc -->
* [Overview](#Overview)
* [Data](#Data)
* [Machine Learning](#Machine_Learning)
* [Dashboard](#Dashboard)
* [Further Study](#Further_Study)

<!-- vscode-markdown-toc-config
	numbering=true
	autoSave=true
	/vscode-markdown-toc-config -->
<!-- /vscode-markdown-toc -->

# <a name='Overview'></a>Overview

The purpose of this project is to use a Machine Learning Model to predict if job postings are for actual jobs or fraudulent postings. This topic was selected due to its relevance to past and future bootcamp graduates who will venture into the job market. 

Data for this analysis is from Shivam Bansal. February 28th, 2020. Real/Fake Job Posting Prediction. Retrieved October 20th, 2022 from [Kaggle](https://www.kaggle.com/datasets/shivamb/real-or-fake-fake-jobposting-prediction). We chose this dataset as it had a high usability score, significant input information, as well as a clear outcome that will help us train our Machine Learning Model. 

The accompanying presentation for this project can be found in [Google Slides.](https://docs.google.com/presentation/d/1-nIw2gooqZSzrCmK9mzQFAiJq0qCpu58WzJAFUr1gMI/edit#slide=id.g17ebc36a465_0_103)

## Key Questions
* What are the key features for fake job postings?
* Are fake job postings more common in certain parts of the US?

<!-- vscode-markdown-toc -->

# <a name='Data'></a>Data

<!-- vscode-markdown-toc -->

## Cleaned Data

The initial database contained a total of 18 columns and 17,880 rows. We eliminated two columns based on the high number of null values including: salary_range (84% null) and department (65% null). We also removed “function” because it appeared very similar to the “industry” column. We then converted four columns (employment_type, required_experience, required_education, and industry) to integers in order to facilitate our machine learning model. Finally, we split the location column into separate country and city, state (or addresses) columns. The data was cleaned, with empty or unneeded cells removed, using jupyter notebook. The amended csv file was used to create our Entity Relationship Diagram (ERD).

## Entity Relationship Diagram (ERD)

![Image](https://github.com/MiguelMSUB/Final_project/blob/23518c98d93319c5a360055059c4c2225c23a769/Images/erd.png)

## Data Exploration and Processing

The cleaned data included most of the information necessary to create our three tables. Coordinates for the location table were scraped from the web using gmaps, geopy, and Nominatim. After our address locations were geocoded, the subsequent csv file was loaded into pgAdmin. The geocoordinates were combined using a FULL JOIN SQL statement to create a comprehensive job_posting_location table. We created three distinct tables using pgAdmin: company_info_string, company_info_int, and job_posting_location. The updated, cleaned data contains 18 columns and 3264 rows—providing sufficient information for our machine learning model.

![](https://github.com/MiguelMSUB/Final_project/blob/abd8ad748e24afb1a37039e6eb1e1faccd4694bf/Images/SQL_Join.png)

# <a name='Machine_Learning'></a>Machine Learning

## Model Choice

Two supervised machine learning models were used: logistic regression and balance random forest classifier. Logistic Regression was selected because of its ease to implement and interpret. We also used a Balance Random Forest Classifier to sample the data and build several smaller, simpler decision trees.

Limitations: These models do not take into account the class imbalance of our data. Real job postings far outnumber those that are fraudulent, potentially skewing our model results.

Benefits: Both models are equipped to evaluate large datasets with multiple features. The Random Forest technique also ranks features by their importance, helping us answer one of our key questions.

## Data Split, Train, and Test

Logistic Regression was used in the following steps in the LogisticRegression.ipynb:
- Imported dependencies: Pandas, Path, SciKit Learn’s LabelEncoder and LogisticRegression
- Preprocessed the data by removing string features and converting employment_type, required_experience, required education, and industry to numerical values.
- Split the data into two sets: train and test. The train dataset included both real and fake job postings and the remaining data was used as the test dataset.
- Fit the training data to create our Logistic Regression model, resulting in a 95% accuracy score.

Random Forest was used in the following steps in the RandomForest.ipynb:
- Imported dependencies: Pandas, Path, SciKit Learn’s LabelEncoder, Train_test_split, Balanced Random Forest Classifier, Balance_accuracy_score, Confusion_matrix and classification_report_imbalanced
- Preprocessed the data by removing string features and converting employment_type, required_experience, required education, and industry to numerical values.
- Split the data into two sets: train and test. The train dataset included both real and fake job postings and the remaining data was used as the test dataset.
- Fit the training data to create our Random Forest classifier model, resulting in a 85% accuracy score.
- Create a data frame from the confusion matrix, print the confusion matrix and the imbalance classification report.
- Print the list of features sorted in descending order by feature importance.

## Results

We were able to accurately predict real job postings approximately 95% of the time with Logistic Regression and 85% of the time with our Random Forest machine learning models. We were far less successful at identifying fake job postings. Our Random Forest model predicted 187 fake job postings, however, only 30 were actually fraudulent. The F1-score, or summary statistic of precision and sensitivity, for fraudulent posting is 35%—is significantly lower than the F1-score of 91% for real job postings. We also sorted the features by column name in reverse order to identify the top three features for predicting job postings: industry, has_company_logo, and required_education. To improve our model, we can drop some of the lower ranked features.

Confusion Matrix     |  Top Features
:-------------------------:|:-------------------------:
![](https://github.com/MiguelMSUB/Final_project/blob/c5d75dd5825da5840d6080ec84829a09c1306c70/Images/confusion_matrix.png)  |  ![](https://github.com/MiguelMSUB/Final_project/blob/d97dff275e4d941b6d91e788c20e458055a77fbd/Images/features.png)

# <a name='Dashboard'></a>Dashboard

- We used Tableau to create the interactive dashboard.

- Interactive Features: This interactive web visualization allows us to select the breakdown of real vs. fraudulent postings by state, industry, or several other filters.

![](https://github.com/MiguelMSUB/Final_project/blob/8464636e568c7c22cc87a79a48c7f461db3e6a4d/Images/dashboard.png)

# <a name='Further_Study'></a>Further Study

When looking at our dataset we have come up with a few alternatives that could have been done. The first would be further training on the Machine Learning Model which would be to drop the least important features and then using SMOTE and Edited Nearest Neighbors algorithms. This would help to oversample the minority class which is fraudulent postings and then clean the resulting data with an undersampling strategy. 

It would also be helpful if the dataset would have more postings, while there were over 17,000 initial rows of data there were quite a few we had to drop due to null cells. It would also help the machine learning model if there was a better balance of real to fraudulent postings in the dataset. 

Future Analysis could also focus on Natural Language Processing which could help examine the data further than we were able to as there were so many columns of data that were string, we did convert some of the major ones to binary like experience and education because those were easily grouped but data that was in sentence and paragraph form was difficult to breakdown into something that was digestible to the machine learning model. That is why we would recommend looking into something like natural language processing because it could lead you in a direction of what to look for in job postings with buzzwords or continued phrases. 

What would we have done differently?
We would have engineered a new feature based on null values for all of the job postings to create more digestible data for the Machine Learning Model 
We also would have undersampled the majority class in our current Machine Learning Model. 
