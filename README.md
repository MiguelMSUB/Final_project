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
* What are the primary indicators for fake job postings?
* Are fake job postings more common in certain parts of the US?

<!-- vscode-markdown-toc -->

# <a name='Data'></a>Data

<!-- vscode-markdown-toc -->

## Cleaned Data

The initial database contained a total of 18 columns and 17,880 rows. We eliminated two columns based on the high number of null values including: salary_range (84% null) and department (65% null). We also removed “function” because it appeared very similar to the “industry” column. We then created three new columns (full_time, experience, and education_level), converting the data to integers in order to facilitate our machine learning model. Finally, we split the location column into separate country, state, and city columns. The data was cleaned using pandas in jupyter notebook. These files were then made into three tables to create our Entity Relationship Diagram (ERD).

## Entity Relationship Diagram (ERD)

![Image](https://github.com/MiguelMSUB/Final_project/blob/df29a7e4d27172b664bc877f264e752ebde2e005/Images/ERD.png)

# <a name='Machine_Learning'></a>Machine Learning





# <a name='Dashboard'></a>Dashboard






# <a name='Further_Study'></a>Further Study

- We recommend...
