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

A full summary of the results of this model can be found in the Summary section of this report. However, it is our belief that this model could be used to predict whether a loan will be healthy or high-risk, with the caveat that high-risk predictions are looked over by human since this model has resulted in a small but significant percentage of false negatives, and we do not want to decline existing customers potentially healthy loans incorrectly.

-----

## Table of Contents

1. [<b>Project Steps Overview</b>](https://github.com/jonnybrammah/CryptoClustering/blob/main/README.md#Project-Steps-Overview<)
2. [<b>Results</b>](https://github.com/jonnybrammah/CryptoClustering/blob/main/README.md#Results)
3. [<b>Summary</b>](https://github.com/jonnybrammah/CryptoClustering/blob/main/README.md#Summary)
4. [<b>Acknowledgements</b>](https://github.com/jonnybrammah/CryptoClustering/blob/main/README.md#Acknowledgements)

----

### Brief Project Overview

### Results

### Summary

#### Acknowledgements

1. To understand why a balanced accuracy metric was more appropriate for analyzing this data, information was taken from [Statology](https://www.statology.org/balanced-accuracy/) (https://www.statology.org/balanced-accuracy/).
2. To write the RandomOverSampler code, and to understand what it was doing, information and code were provided by [MachineLearningMastery](https://machinelearningmastery.com/random-oversampling-and-undersampling-for-imbalanced-classification/)(https://machinelearningmastery.com/random-oversampling-and-undersampling-for-imbalanced-classification/)
3. To further help clarify the differences between precission, recall, and accuracy, information was taken from [TowardsDataScience](https://towardsdatascience.com/precision-and-recall-88a3776c8007#:~:text=Precision%20is%20calculated%20by%20dividing,was%20predicted%20as%20a%20positive.&text=Recall%20  
(or%20True%20Positive%20Rate,have%20been%20predicted%20as%20positive)

(https://towardsdatascience.com/precision-and-recall-88a3776c8007#:~:text=Precision%20is%20calculated%20by%20dividing,was%20predicted%20as%20a%20positive.&text=Recall%20(or%20True%20Positive%20Rate,have%20been%20predicted%20as%20positive)

