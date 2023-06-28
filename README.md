# credit-risk-classification

![Loan Risk](https://miro.medium.com/v2/resize:fit:828/format:webp/0*1kuLl_N1AsrWDdd2.jpg)

## Project Description

The purpose of this project was to use Machine Learning to categorize loan applications into two categories, Healthy and High-Risk.

The model was trained and tested on a list of 77,500 historic loan applications, including whether they turned out to by healthy or high-risk, and the inputs included:
- The Loan Amount
- The Interest Rate provided
- The borrower's annual income
- The borrower's debt to income ratio
- How many accounts the borrower has with the institution
- How many "Derogatory marks" against them the borrower has
- The total debt the borrower carries

A summary of the conclusions drawn from the results of this model can be found in the [<b>Summary</b>](https://github.com/jonnybrammah/credit-risk-classification/blob/main/README.md#Summary) section of this report.

-----

## Table of Contents

1. [<b>Project Steps Overview</b>](https://github.com/jonnybrammah/credit-risk-classification/blob/main/README.md#Project-Steps-Overview)
- [<b>Training the model with Raw Data</b>](https://github.com/jonnybrammah/credit-risk-classification/blob/main/README.md#Training-the-model-with-Raw-Data)
- [<b>Training the model Randomly Oversampled Data</b>](https://github.com/jonnybrammah/credit-risk-classification/blob/main/README.md#Training-the-model-with-Randomly-Oversampled-Data)
2. [<b>Results</b>](https://github.com/jonnybrammah/credit-risk-classification/blob/main/README.md#Results)
- [<b>Model Trained on Raw Data/b>](https://github.com/jonnybrammah/credit-risk-classification/blob/main/README.md#Model-Trained-on-Raw-Data)
- [<b>Model Trained on Randomly Oversampled Data</b>](https://github.com/jonnybrammah/credit-risk-classification/blob/main/README.md#Model-Trained-on-Randomly-Oversampled-Data)
3. [<b>Summary</b>](https://github.com/jonnybrammah/credit-risk-classification/blob/main/README.md#Summary)
4. [<b>Acknowledgements</b>](https://github.com/jonnybrammah/credit-risk-classification/blob/main/README.md#Acknowledgements)

----

## Project Steps Overview

### Training the model with Raw Data

Since the goal of this project was to categorize whether a loan was likely to be healthy or high-risk, this column was removed from the dataset, and stored as a y-variable. The remaining columns were stored as the X-variable.

Looking at the data showed the number of healthy and high-risk loans was very unbalanced, with significantly more loans having been healthy than high-risk

| Type of Loan | Number |
| --- | --- |
| Healthy | 75,036 |
| High-Risk | 2500 |

_Table 1_

The data was then split into training and testing sets in order to be able to assess its accuracy later.

The logistic regression model was then trained on the training sets, and then evaluated using the testing set.


### Training the model with Randomly Oversampled Data

To overcome the potential errors that may stem from having such a significant imbalance in sample-size for healthy and high-risk loans, the RandomOverSampler function from the imblearn library was used. This deliberately randomly duplicates examples from the high-risk category, in order to make sure the model has equal data from both sets to train on.

After running the RandomOverSampler, you can see there are equal numbers of both loan types:

| Type of Loan | Number |
| --- | --- |
| Healthy | 56,277 |
| High-Risk | 56,277 |

_Table 2_

The same steps as above were then performed:
- The data was split into training and testing sets
- The model was trained on the training sets, and then evaluated on the testing set.

-----

## Results

### Model Trained on Raw Data

The overall accuracy of the model trained on Raw Data was 99.24%, however this is a very unbalanced dataset, and simply predicting all loans as healthy would result in an accuracy score of almost 97%. To check the accuracy given this imbalance, a balanced accuracy score was created which was shown to be 94.43%, so still reasonably good but not as high as the simple accuracy score would imply.

The number of Healthy and High-Risk Loans vs what the model predicted they should be is shown in the table below:

| | Predicted Healthy | Predicted-High-risk |
| --- | --- | --- |
| Actual Healthy | 18,679 | 80 |
| Actual High-Risk | 67 | 558 |

_Table 3_

- This means we have a very high accuracy rate for predicting healthy loans (99.57%), and the precision and recall are both also 100%.
- This high recall means that the ratio of healthy loans to all predicted healthy loans is high, meaning very few healthy loans were misclassified as high-risk.
- Similarly, the high precision means that relatively few high-risk loans were inaccurately predicted as healthy.

However, due to the much smaller sample size of high-risk loans, the accuracy for predicting these loans was also  lower.
- Of the total 625 high-risk loans, about 67 were incorrectly predicted as healthy, which is about 10%.
- The precision for high-risk loans was only 87%, meaning a significant number of these loans that are predicted as high-risk, even when healthy.
- Similarly, the recall for high-risk loans is around 89%, meaning a significant portion of healthy loans are being misidentified as healthy.

This discrepancy in our accuracy in predicting healthy loans when compared to our accuracy in predicting high-risk loans is shown in the figure below:

![Logistic Regression Raw Data Accuracy](https://raw.githubusercontent.com/jonnybrammah/credit-risk-classification/main/Output/Raw_Data_Accuracy.png)

_Please be aware that the scale for the y-axis begins at 50% to make the difference more visually apparent._

### Model Trained on Randomly Oversampled Data

In this case, the accuracy for the model trained on the oversampled data was around 99.52%, with a balanced accuracy score of 99.52%, so already this model is clearly providing more useful categorization.

The number of Healthy and High-Risk Loans vs what this model predicted they should be is shown in the table below:

| | Predicted Healthy | Predicted-High-risk |
| --- | --- | --- |
| Actual Healthy | 18,668 | 91 |
| Actual High-Risk | 2 | 623 |

_Table 4_

Based on this table, when compared to Table 3, above, you can see that there is a slight increase in healthy loans that are being misidentified as high-risk (from 80 to 91), but a significant decrease in the number of high-risk loans that are being misidentified as healthy (from 67 to only 2).

This improvement in our accuracy in predicting high-risk loans can be seen in the following graph when compared to the previous graph::

![Logistic Regression Raw Data Accuracy](https://raw.githubusercontent.com/jonnybrammah/credit-risk-classification/main/Output/Random_Oversampling_Accuracy.png)

_Please be aware that the scale for the y-axis begins at 50% to make the difference more visually apparent._

- As with the previous model, the precision and recall for the healthy loans are both very close to 100%, meaning that these loans are being predicted correctly almost all of the time.

- The recall for high-risk loans is also close to 100%, meaning that very few loans are being predicted as healthy when they are actually high risk. This is very good news for the model, since it means that we are correctly identifying high-risk loans that may cause issues for the bank.

- The precision for high-risk loans, however, is still only around 87%. This means that relative to the total number of high-risk loans, the model is identifying a significant number of healthy loans into this category. This issue is discussed further in the [Summary](https://github.com/jonnybrammah/credit-risk-classification/blob/main/README.md#Summary) section of this report.

-----

### Summary

It is our belief that the second model (using RandomOverSampler) can be used to predict whether a loan will be healthy or high-risk.
- The model accurately predicts that a loan will be high-risk, with only 2 loans in the dataset being misidentified as healthy. This means there is a low chance for losing money due to a misidentified high-risk loan. In our opinion, this is an important factor in evaluating the success of the model.
- The model also generally accurately predicts healthy loans, meaning we can be confident that a loan identified as healthy is actually going to be.
- The main caveat we have to add here is that there is a significant number of loans that are misidentified as high-risk when they are actually healthy. While the number of misidentified actually is small in relation to the number of healthy loans, it is notable in relation to the number of high-risk loans. This is a generally direct small risk financially to the organization since it means we are unlikely to take on more high-risk loans, it will have an impact indirectly if we do not approve people for loans that are likely to be healthy. With this in mind, while we believe this model could be used to categorize loan risks, we strongly recommend including another layer to the process whereby loans identified as high risk are checked again, either by a human or another machine learning model. This will both reduce the number of rejected loan applications that should otherwise be accepted, and prevent attrition of customers to our competitors.

-----

#### Acknowledgements

1. To understand why a balanced accuracy metric was more appropriate for analyzing this data, information was taken from [Statology](https://www.statology.org/balanced-accuracy/) (https://www.statology.org/balanced-accuracy/).
2. To write the RandomOverSampler code, and to understand what it was doing, information and code were provided by [MachineLearningMastery](https://machinelearningmastery.com/random-oversampling-and-undersampling-for-imbalanced-classification/)(https://machinelearningmastery.com/random-oversampling-and-undersampling-for-imbalanced-classification/)
3. To further help clarify the differences between precission, recall, and accuracy, information was taken from [TowardsDataScience](https://towardsdatascience.com/precision-and-recall-88a3776c8007) (https://towardsdatascience.com/precision-and-recall-88a3776c8007)

