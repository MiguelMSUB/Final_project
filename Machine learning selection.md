## Model Evaluation and Validation

The final model used for this analysis is Random Forest Classifier.  This is based on the results of the type of data set that we are using for this problem. 

As we mentioned before in the advantages and disadvantages of the two models previously selected for this project, the Random Forest Classifier work well with both categorical and numerical data. Besides that no scaling or transformation of variables is necessary, so that will help us to save a lot of time cleaning the data. Finally because this model also provides a very nice output with variable importance. This interpretation can help you go beyond an accurate prediction and comment on what's more important in achieving the prediction and why.

Justification

The selected model based on the evaluation above, it will be able to identify real jobs with a very high **accuracy (85%)**. However, it’s identification of fake jobs can still be improved upon.

The confusion matrix above displays the following values – categorized label, number of data points categorized under the label and percentage of data represented in each category.  Based on the confusion matrix it is evident that the model identifies real jobs 85% of the times. This shortcoming has been discussed earlier as well as Machine Learning algorithms tend to prefer the dominant classes.

From the confusion matrix results also we can get the precision for the Fraudulent Jobs is very low, indicating a large number of false positives, which indicates an unreliable positive classification. The recall is high for the Fraudulent jobs, which is indicative of a small number of false negatives. The F1 score is also low (35%).


