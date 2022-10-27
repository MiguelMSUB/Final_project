# Final_project

<!-- vscode-markdown-toc -->

# Database

<!-- vscode-markdown-toc -->

## Overview 

<!-- vscode-markdown-toc -->

The purpose of this project is to use a Machine Learning Model to predict if job postings are for actual jobs or fraudulent postings. This topic was selected due to the relevence to past and future bootcamp graduates that will be in the job market. 

<!-- vscode-markdown-toc -->

## Data Source 

<!-- vscode-markdown-toc -->

This dataset came from Shivam Bansal who uploaded the information to Kaggle in February 2020 - Real/Fake Job Posting Prediction. 
https://www.kaggle.com/datasets/shivamb/real-or-fake-fake-jobposting-prediction

We chose this dataset as it had a high usability score, enough input information as well as a clear outcome that will help us train our Machine Learning Model. 

<!-- vscode-markdown-toc -->

## Using the Data 

<!-- vscode-markdown-toc -->

Once the data was sourced, we needed to set up the folder to hold the CSV file as well as code needed to process the data and load it into our database. We chose to use Jupyter Notebook for our Python code, the dataset is in a CSV file and we are using PostgreSQL for the database. In the folder there will be the dataset - ours is saved as "fake_job_posting.csv", the Python file - ours is "Team_Project_Starter_Code.ipynb", and a "config.py" file. 

The first line of code is bringing in our dependencies, please see below for what will be needed. 

![Dependencies](https://github.com/MiguelMSUB/Final_project/blob/walzfran/segment1/Images/Dependencies.png)

Before running our code, please set up a database in PostgreSQL if you need help doing that please follow the instructions below

* Start pgAdmin and expand your local servers in the left-hand pane so you can see the Databases section
* Right-click on Databases and select Create followed by Database
* Name the database "job_posting" and click Save 

You will see that we are pulling in "db_password" from our config file, in the config file please have one line of code with " db_password = 'DATABASE PASSWORD HERE' " the database password will be unique to your database in PostgreSQL. 

In this code we cleaned it slightly before loading into PostgreSQL, there were columns taken out that had a high amount of null values and were not going to be used when training our Machine Learning Model. After the columns were taken out we made sure to clean the remaining data to take out rows that had null values, once the data was cleaned we stored it in a new dataframe and uploaded that datafram to PostgreSQL. 






