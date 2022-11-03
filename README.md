# Fake Job Predictions Final Project

# Table of Contents 

<!-- vscode-markdown-toc -->
* [Overview](#Overview)
* [Database](#Database)
* [Data Processing](#Data_Processing)
* [Machine Learning](#Machine_Learning)
* [Communication Protocol](#Communication_Protocol)
* [Technologies Used](#Technologies_Used)

<!-- vscode-markdown-toc-config
	numbering=true
	autoSave=true
	/vscode-markdown-toc-config -->
<!-- /vscode-markdown-toc -->

# <a name='Overview'></a>Overview

The purpose of this project is to use a Machine Learning Model to predict if job postings are for actual jobs or fraudulent postings. This topic was selected due to the relevance to past and future bootcamp graduates that will be in the job market. 

We have made our presentation for class in Google Slides [here.](https://docs.google.com/presentation/d/1-nIw2gooqZSzrCmK9mzQFAiJq0qCpu58WzJAFUr1gMI/edit#slide=id.g17ebc36a465_0_103)

The source of data for this analysis is from Shivam Bansal. 28 February 2020. Real/Fake Job Posting Prediction. Retrieved 20 October 2022 from https://www.kaggle.com/datasets/shivamb/real-or-fake-fake-jobposting-prediction.  

We chose this dataset as it had a high usability score, enough input information as well as a clear outcome that will help us train our Machine Learning Model. 

## Key Questions
* What are the primary indicators for fake job postings?
* Are fake job postings more common in certain parts of the US?

<!-- vscode-markdown-toc -->

# <a name='Database'></a>Database

<!-- vscode-markdown-toc -->

## Using the Data 

<!-- vscode-markdown-toc -->

Once the data was sourced, we needed to set up the folder to hold the CSV file as well as code needed to process the data and load it into our database. We chose to use Jupyter Notebook for our Python code, the dataset is in a CSV file and we are using PostgreSQL for the database. In the folder there will be the dataset - ours is saved as "fake_job_posting.csv", the Python file - ours is "job_posting_code.ipynb", and a "config.py" file. 

The first line of code is bringing in our dependencies, please see below for what will be needed. 

![Dependencies](https://github.com/MiguelMSUB/Final_project/blob/walzfran/segment1/Images/Dependencies.png)

Before running our code, please set up a database in PostgreSQL if you need help doing that please follow the instructions below

* Start pgAdmin and expand your local servers in the left-hand pane so you can see the Databases section
* Right-click on Databases and select Create followed by Database
* Name the database "job_posting" and click Save 

You will see that we are pulling in "db_password" from our config file, in the config file please have one line of code with " db_password = 'DATABASE PASSWORD HERE' " the database password will be unique to your database in PostgreSQL. 

In this code we cleaned it slightly before loading into PostgreSQL, there were columns taken out that had a high amount of null values and were not going to be used when training our Machine Learning Model. After the columns were taken out we made sure to clean the remaining data to take out rows that had null values, once the data was cleaned we stored it in a new dataframe and uploaded that dataframe to PostgreSQL. 

# <a name='Data_Processing'></a>Data Processing

Description of preliminary feature engineering and preliminary feature selection, including their decision-making process. 

The initial database contained a total of 18 columns. We eliminated two columns based on the high number of null values including: “salary_range” (84% null) and “department” (65% null). We also removed “function” because it appeared very similar to the “industry” column. We then created three new columns (“full_time”, “experience,” and “education_level), converting the data to integers from strings, in order to facilitate our machine learning model.  Finally, we split the location column into separate “Country,” “State,” and “City” columns. Based on our feature selection, we aim to produce three tables:
-       Company/job posting information in string format,
-       Company/job posting information with integers,
-       Location details for future mapping

Before using our data in our Machine Learning Model we focused on preparing the data to work well with Machine Learning. This included converting textual data into numerical data. 

![Image](https://github.com/MiguelMSUB/Final_project/blob/walzfran/segment2/Images/datatypes.png)

To use Scikit-learn’s Machine Learning Algorithms (LabelEncoder), the categorical features such as employment type, required experience, industry and required education will have to be converted into numbers, this process is called encoding. 

![Image_2](https://github.com/MiguelMSUB/Final_project/blob/walzfran/segment2/Images/featureselector.png)

# <a name='Machine_Learning'></a>Machine Learning

### Model Choice - Supervised Learning

We will rely on supervised learning to predict whether a job posting is fraudulent, based on data from prior job postings. We’ll use a classification model because the target variable has two possible values: real or fake. When the classification model encounters new data, it will use features such as employment type, telecommuting, includes questions, and location to predict whether the job posting is real or fake. 

![Image_3](https://github.com/MiguelMSUB/Final_project/blob/walzfran/segment2/Images/Brainstorm.png)

#### Algorithm(s)

* Logistic Regression - we will split the dataset into training and testing sets and then create a logistic regression model with specified arguments for solver, max_iter, and random_state. We’ll then train the model with the training data and use the x_test set to create predictions for y-values.  When the y-values (y-pred) are compared with the actual y-values (y_test), we’ll be able to determine if the predictions (real “0” or fake “1”) were correct. We’ll also use the sklearn.metrics.accuracy_score to determine how well our logistic regression model predicts.

* Random Forest – we’ll also use a random forest algorithm to sample the data and build several smaller, simpler decision trees. Each tree is simpler because it is built from a random subset of features. We will also be able to rank the features by their importance, which allows us to determine which features have the most impact on the decision.

* Additional Considerations - because the number of fraudulent listings is significantly smaller than the number of legitimate job postings, we may want to consider SMOTE and Edited Nearest Neighbors (ENN) algorithms to: 1) oversample the minority class with SMOTE and 2) clean the resulting data with an under sampling strategy.


# <a name='Communication_Protocol'></a>Communication Protocol

1. Slack will be used as our main communication channel.

2. Knowledge base
If the team has a searchable knowledge base, then everyone has access to all the information they might need. Instead of sending out a query and disrupting someone else’s workflow to get the answer, they can search and find it for themselves.

https://docs.google.com/spreadsheets/d/1T0JhEgFLcKty9tMg9nAYJRjBJO6YVXAEjIG_a7ZBVpk/edit#gid=891834841

3. Recurring meetings (class time and office hours)

Tuesdays and thursdays 6:30 to 7:00pm

Tuesdays and thursdays 9:00 to 9:30pm

Where? breakout room #3


4. Set expectations around response rates

Slack messages are expected to be responded within the following 24 hours

5. Emergency protocols

A text to the group (imessage) after hours / before recurring meeting signals that something needs to be deal with immediately/ASAP, whereas a late night slack message can be handled in the morning. 

Meeting room: https://meet.google.com/rhq-dtxw-cmw 

 6. Bring in efficiency tools

We'll be tracking activities status with the following google Jamboard 
https://jamboard.google.com/d/1fdHimrhyTrNP0fFamctsHDvefOIKriRsLuR9EaI3P1M/viewer?ts=6351d02a&f=0

# <a name='Technologies_Used'></a>Technologies Used

## Data Cleaning and Analysis

The data that we will extract may need to be filtered, parsed, translated, sorted, interpolated, pivoted, summarized, aggregated, merged, or more. The goal is to create a consistent structure in the data. Without a consistent structure in our data, it's almost impossible to perform any meaningful analysis. This transformation phase can be accomplished with Pandas and Python. We have decided to use these tools Python and Pandas because they provide flexibility and interactivity (especially in a Jupyter Notebook).

Jupyter Notebook

Jupyter notebook files are great for sharing code. Since Jupyter Notebook is run in a browser, we will be able to easily share our analysis within our team members. All members will need to do is download the file and run the code we provide.

## Database Storage

PostgreSQL as a great and open tool is a powerful database that uses and extends the SQL language combined with many features that safely store and scale the most complicated data workloads. PostgreSQL extremely efficient when running deep, extensive data analysis across multiple data types. We will be able to connect to PostgreSQL Database Server in Python and export PostgreSQL Table to CSV file to be able to manipulate with our machine learning.

## Machine Learning

The core tool for this project will be th supervised machine learning in which machines are trained using well "labelled" training data, and on basis of that data, machines predict the output. The labelled data means some input data is already tagged with the correct output.

Supervised learning is a process of providing input data as well as correct output data to the machine learning model. The aim of a supervised learning algorithm is to find a mapping function to map the input variable(x) with the output variable(y).

We have chosen supervised machine learning because in the real-world, it can be used for risk assessment, image classification, fraud detection, spam filtering, etc. 

We will split the dataset into training and testing sets and then create a logistic regression model with specified arguments for solver, max_iter, and random_state. Besides that we’ll also use a random forest algorithm to sample the data and build several smaller, simpler decision trees. 

## Dashboard

We will use Tableau public to transform our data into an engaging story for any audience. We will also integrate D3.js for a fully functioning and interactive dashboard. With Tableau public we can create and share publicly our data visualizations easy and free. Below is an image from our Tableau Dashbord that we are working on with an interactive map of the United States with job posting data. 

![Image_5](https://github.com/MiguelMSUB/Final_project/blob/mperez/segment2/Images/Map.png)
