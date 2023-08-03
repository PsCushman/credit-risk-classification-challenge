# Module 12 Report Template

## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* Explain the purpose of the analysis.
* Explain what financial information the data was on, and what you needed to predict.
* Provide basic information about the variables you were trying to predict (e.g., `value_counts`).
* Describe the stages of the machine learning process you went through as part of this analysis.
* Briefly touch on any methods you used (e.g., `LogisticRegression`, or any resampling method).

## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
  * Description of Model 1 Accuracy, Precision, and Recall scores.

Balanced Accuracy Score: 0.95

F1-score for label 0 (healthy loan): 1.00

F1-score for label 1 (high-risk loan): 0.88


* Machine Learning Model 2:
  * Description of Model 2 Accuracy, Precision, and Recall scores.

Balanced Accuracy Score: 0.99

F1-score for label 0 (healthy loan): 1.00

F1-score for label 1 (high-risk loan): 0.92


## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

If you do not recommend any of the models, please justify your reasoning.

*The logistic regression model with RandomOverSampler shows improved performance compared to the original logistic regression model. It achieves higher balanced accuracy, indicating a better overall balance in predicting both healthy and high-risk loans. Additionally, the F1-scores for both labels have improved, suggesting better precision and recall for both classes.*

*It is important to consider the problem we are trying to solve when evaluating the model's performance. In the context of predicting loan risk, both precision and recall for both classes (healthy and high-risk loans) are critical. A high precision ensures that when the model predicts a loan as high-risk, it is very likely to be true, which helps in avoiding bad loans. A high recall ensures that the model identifies most of the actual high-risk loans, which is essential for minimizing the risk to the lender.*

*Considering the improved performance and the importance of correctly identifying both healthy and high-risk loans, the logistic regression model with RandomOverSampler is recommended for this loan risk prediction problem.*

*However, it is crucial to remember that model selection also depends on other factors such as interpretability, computational resources, and the size of the dataset. If the dataset is extremely large, other algorithms like gradient boosting or deep learning models could be considered as well. It is always a good practice to try different models and select the one that best fits the problem and data characteristics while meeting the specific requirements and constraints of the application.*
