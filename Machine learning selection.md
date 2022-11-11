## Model Evaluation and Validation

The final model used for this analysis is Random Forest Classifier.  This is based on the results of the type of data set that we are using for this problem. 

As we mentioned before in the advantages and disadvantages of the two models previously selected for this project, the Random Forest Classifier work well with both categorical and numerical data. Besides that no scaling or transformation of variables is necessary, so that will help us to save a lot of time cleaning the data. Finally because this model also provides a very nice output with variable importance. This interpretation can help you go beyond an accurate prediction and comment on what's more important in achieving the prediction and why.

Justification

The selected model based on the evaluation above, it will be able to identify real jobs with a very high **accuracy (85%)**. However, it’s identification of fake jobs can still be improved upon.

The confusion matrix above displays the following values – categorized label, number of data points categorized under the label and percentage of data represented in each category.  Based on the confusion matrix it is evident that the model identifies real jobs 99.01% of the times. However, fraudulent jobs are identified only 73.5% of the times. Only 2% of the times has the model not identified the class correctly. This shortcoming has been discussed earlier as well as Machine Learning algorithms tend to prefer the dominant classes.

From the confusion matrix results, the precision for the bad loan applications is low, indicating a large number of false positives, which indicates an unreliable positive classification. The recall is also low for the bad loan applications, which is indicative of a large number of false negatives. The F1 score is also low (33).

In summary, this random forest model is not good at classifying fraudulent loan applications because the model's accuracy, 0.520, and F1 score are low.
