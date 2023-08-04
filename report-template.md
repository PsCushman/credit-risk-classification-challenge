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

*The logistic regression model, trained on the oversampled data, is a more relaiable tool and conservative model for predicting both healthy and high-risk loans, making it valuable for assessing loan risk in this scenario. While there are slighly more false positives i.e. (the oversampled model incorrectly classified 86 healthy loans as high-risk loans as opposed to 75 in the first model), this model almost emilinated false negatives i.e. (it incorrectly classified 3 high-risk loans as healthy loans as opposed to 46 in the first model).*

*For loan seekers, this model might provide for some frustating expereinces, but for a risk adverse bank, this model performs extremely well and would proably be adopted over the pervious model without the oversampled data.*

*That said, it is crucial to remember that model selection also depends on other factors such as interpretability, computational resources, and the size of the dataset. If the dataset is extremely large, other algorithms such as deep learning models might be considered. Since it is always a good practice to try different models and select the one that best fits the problem and data characteristics, it may be useful to try other models to see if we could decrease the number of false negatives to avoid fustrating loan seekers. In additional, since there are a large number of flase negatives in this model, it would be prudent to dig deeper into the loans set to be denied to make sure the model is not biased. It is crucial to ensure that the model is not biased, especially if certain loan seekers are disproportionately affected by the misclassifications. If, for instance, there is a substantial number of incorrectly classified loans that are disproportionately associated with specific demographic groups, necessary adjustments to the model should be made to ensure its fairness and equitable treatment of all loan applicants.*
