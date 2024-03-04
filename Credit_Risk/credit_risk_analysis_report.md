# Module 12 Report Template

## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* Explain the purpose of the analysis.
* Explain what financial information the data was on, and what you needed to predict.
* Provide basic information about the variables you were trying to predict (e.g., `value_counts`).
* Describe the stages of the machine learning process you went through as part of this analysis.
* Briefly touch on any methods you used (e.g., `LogisticRegression`, or any resampling method).

In this analysis of loan risk, I created two different logistic regression models to try to best predict the probability of loans being healthy or unhealthy. 

I began by reading in a CSV file of lending data including loan size, interest rate, and loan status, among other details. I then separated the loan status column into its own variable to determine how many healthy and unhealthy loans existed in the dataset (75,000+ healthy and 2,500 unhealthy). After splitting the data into training and testing sets, I was ready to create my first logistic regression model to attempt to predict loan status with high accuracy.

I fit the model with the training data and made a prediction using "classifier.predict" in order to evaluate the model's performance. The result was a model with a balanced accuracy score over 95%, which on the surface seemed fairly successful. However, a deeper dive into the classification report showed an imbalance between the accuracy of predicting healthy loans versus unhealthy loans. While the accuracy score and recall value for healthy loans were both over 99%, the same values for unhealthy loans sat at just 85% and 91% respectively. This means the model would not be nearly as trustworthy in predicting unhealthy loans and another attempt at a model would be necessary.

The second logistic regression model was created using resampled training data that created an even divide of 56,271 healthy and unhealthy loans in the dataset. After following the same steps outlined above for the new model fit with resampled data, the classification report told a different story. This time around the accuracy and recall scores for both healthy and unhealthy loans came back with over 99% precision, deeming this model much more accurate overall than the original.

## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
  * Balanced Accuracy Score: 95.2%
      Overall, the model was correct over 95% of the time across both healthy and unhealthy loans.
  
  * Precision: 100% for healthy loans, 85% for unhealthy loans
      While the model would likely do a good job of predicting a loan as healthy, it has a higher chance of incorrectly labeling a loan as unhealthy.
      
  * Recall Score: 99% for healthy loans, 91% for unhealthy loans
      The model made 1% of mistakes when predicting healthy loans and 9% of mistakes when predicting unhealthy loans.



* Machine Learning Model 2:
  * Balanced Accuracy Score: 99.5%
      Overall, the model was correct over 99% of the time across both healthy and unhealthy loans.
      
  * Precision: 99% for healthy loans, 99% for unhealthy loans
      The model would likely do a good job of predicting a loan as either healthy or unhealthy.
      
  * Recall Score: 99% for healthy loans, 99% for unhealthy loans
       The model made 1% of mistakes when predicting healthy loans and 1% of mistakes when predicting unhealthy loans.
       
## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
    The second model seems to perform best because it is highly accuracte across both healthy and unhealthy loans instead of just healthy. The lending services company would surely want a model that performs better across both loan types because otherwise they would be more likely to make mistakes in judgment (i.e. a healthy loan being mistaken as unhealthy may lead to less customers and an unhealthy loan being mistaken as healthy may lead to a loss of money for the company).
    
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )
    In this case, it is important to predict both the '1''s and the '0''s because the lending company could be handling healthy loans perfectly and still lose money due to a mishandling of unhealthy loans. Because the two loan types are linked to each other as polar opposites, they impact each other and it is crucial to understand both sides.

If you do not recommend any of the models, please justify your reasoning.
    I would recommend the second model fit with oversampled data.
