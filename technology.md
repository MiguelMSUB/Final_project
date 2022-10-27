# Technologies Used

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

We will use Tableau public to transform our data into an engaging story for any audience. We will also integrate D3.js for a fully functioning and interactive dashboard. With Tableau public we can create and share publicly our data visualizations easy and free. 
