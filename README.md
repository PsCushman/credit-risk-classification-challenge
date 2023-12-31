# Credit Risk Classification

![Screen Shot 2023-08-07 at 8 41 16 AM](https://github.com/PsCushman/credit-risk-classification-challenge/assets/122395437/75b91323-a3cc-4cb1-9b2b-f2f811fef08d)


## Overview

In this data analysis, we evaluated the performance of two machine learning models for predicting loan risk – the original logistic regression model and the logistic regression model with RandomOverSampler. The goal was to identify which model performs best in predicting both healthy and high-risk loans, taking into account precision, recall, and balanced accuracy.

There are two notebooks. One should be used for grading and it clearly marked as such (credit_risk_classification_FOR_GRADING.ipynb). The other was for my own use to gain a better understanding about how the model is making the predictions (credit_risk_classifacation_extras.ipynb).

## Results

* **Machine Learning Model 1 (Logistocal Regression)**:

  - Confusion Matrix

  ![Screen Shot 2023-08-04 at 3 01 20 PM](https://github.com/PsCushman/credit-risk-classification-challenge/assets/122395437/01965e28-0725-4549-9809-675575a39f90)

  ![confusion_matrix_plot_logistic_regression](https://github.com/PsCushman/credit-risk-classification-challenge/assets/122395437/b5a8270d-ebd6-4e47-bd55-312904da9d8d)

  - Balanced Accuracy Score: 0.95
  - F1-score for label 0 (healthy loan): 1.00
  - F1-score for label 1 (high-risk loan): 0.88
    
  ![Screen Shot 2023-08-04 at 3 00 56 PM](https://github.com/PsCushman/credit-risk-classification-challenge/assets/122395437/4894c2d1-30f3-4356-99b5-e7ca8598b0b2)
    
* **Machine Learning Model 2 (Logistocal Regression with Oversampled Data)**:
  
  - Confusion Matrix
    
  ![Screen Shot 2023-08-04 at 2 59 22 PM](https://github.com/PsCushman/credit-risk-classification-challenge/assets/122395437/6f60b38e-fab2-42b3-9043-81ad473b7c65)

  ![confusion_matrix_oversampled](https://github.com/PsCushman/credit-risk-classification-challenge/assets/122395437/9c20b37c-aa19-420c-ae20-f589039021c7)

  - Balanced Accuracy Score: 0.99
  - F1-score for label 0 (healthy loan): 1.00
  - F1-score for label 1 (high-risk loan): 0.92

  ![Screen Shot 2023-08-04 at 3 01 58 PM](https://github.com/PsCushman/credit-risk-classification-challenge/assets/122395437/6f0ff366-e76d-4f1d-bf03-646f4baaf722)


## Summary

*The logistic regression model with RandomOverSampler shows improved performance compared to the original logistic regression model. It achieves higher balanced accuracy, indicating a better overall balance in predicting both healthy and high-risk loans. Additionally, the F1-scores for both labels have improved, suggesting better precision and recall for both classes.*

*It is important to consider the problem we are trying to solve when evaluating the model's performance. In the context of predicting loan risk, both precision and recall for both classes (healthy and high-risk loans) are critical. A high precision ensures that when the model predicts a loan as high-risk, it is very likely to be true, which helps in avoiding bad loans. A high recall ensures that the model identifies most of the actual high-risk loans, which is essential for minimizing the risk to the lender.*

*Considering the improved performance and the importance of correctly identifying both healthy and high-risk loans, the logistic regression model with RandomOverSampler is recommended for this loan risk prediction problem.*

*The logistic regression model, trained on the oversampled data, is a more reliable tool and conservative model for predicting both healthy and high-risk loans, making it valuable for assessing loan risk in this scenario. While there are slightly more false positives i.e. (the oversampled model incorrectly classified 86 healthy loans as high-risk loans as opposed to 75 in the first model), this model almost eliminated false negatives i.e. (it incorrectly classified 3 high-risk loans as healthy loans as opposed to 46 in the first model).*

*For loan seekers, the oversampled model might provide for some frustrating experiences, but for a risk adverse bank, this model performs extremely well and would probably be adopted over the previous model without the oversampled data.*

## Consclusion

*It is crucial to remember that model selection also depends on other factors such as interpretability, computational resources, and the size of the dataset. If the dataset is extremely large, other algorithms such as deep learning models might be considered. Since it is always a good practice to try different models and select the one that best fits the problem and data characteristics, it may be smart to fit the data with additional models to see if we could decrease the number of false negatives to avoid frustrating loan seekers.* 

*In additional, since there is a sizeable number of false negatives in this model, it would be prudent to dig deeper into the loans set to be denied making sure the model is not biased. It is crucial to ensure that the model is not biased, especially if certain loan seekers are disproportionately affected by the misclassifications. If, for instance, there is a substantial number of incorrectly classified loans that are disproportionately associated with specific demographic groups, necessary adjustments to the model should be made to ensure its fairness and equitable treatment of all loan applicants.*

*In conclusion, the logistic regression model with RandomOverSampler emerges as the recommended model due to its improved performance and ability to predict both healthy and high-risk loans effectively. However, it is essential to continue exploring other models, consider interpretability, and conduct fairness analysis to enhance the overall loan risk prediction process and ensure equitable treatment of loan applicants.*

## "EXTRAS"

While I had a relativley easy time training and testing the models for the assigment, I was having an issue understanding how the model was making a prediction. So I did a little research and decided that trying to plot a prediction curve would be helpful, just for my own understanding. First, since I am not able plot in seven dimensions at this point, I used the permutation importance feature from scikit-learn to decide which single X column to train and test the model.

![Screen Shot 2023-08-07 at 4 24 15 PM](https://github.com/PsCushman/credit-risk-classification-challenge/assets/122395437/64a707a2-6661-4182-8491-1caa18e0ec78)

For this, I used the borrower income from the over sampled data model because it seemed to have the most imortance from the oversampled model.  

From there, I used the protected probability function from scikit-learn to plot a decision curve based on a model train just with the borrower income, just so I could see a predicted probability curve.

![Screen Shot 2023-08-07 at 4 25 06 PM](https://github.com/PsCushman/credit-risk-classification-challenge/assets/122395437/4485d939-91d9-4812-b7d8-7ee18c40a09c)

From there, I plotted the predicted values along the curve.

![Screen Shot 2023-08-07 at 4 26 59 PM](https://github.com/PsCushman/credit-risk-classification-challenge/assets/122395437/6bc11f1c-020b-471e-be39-82481190ec8a)

In the end, this helped me understand the decision making on another level. Still a lot to learn.

## Resources

For plotting a better looking confusion matrix I used code from:

https://dfrieds.com/machine-learning/visual-introduction-classification-logistic-regression-python.html#confusion-matrix

And for permutation importance, I spoke with my tutor and used code from:

https://scikit-learn.org/stable/modules/permutation_importance.html

For the final plots in the "extras" notebook, I found code at:

https://www.kaggle.com/code/aakritsinghal/logistic-regression-visualisation
