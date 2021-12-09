# Credit Risk Analysis

## Overview
The purpose of this project was to analyze loan application data and use machine learning to build a model to help determine if a future loan will be successful for a future applicant.  The loans are registered as either low-risk or high-risk.

## Results
While the general results are promising, there are a few models that seem to let a lot of bad loans through the cracks.  The main issue with this data is that there is a huge discrepancy between low and high risk loan approval.  In the test data, we have almost 69,000 loan applications, and only 347 are flagged as high risk, an extremely small percent of all the applications.  

### Random Oversampling
This method seemed to flag a lot of low-risk loans as high-risk, and a large percent of high-risk as low risk.  The accuracy score was about 64%, with precision at 0.01 and recall at 0.6.

#### Random Oversampling confusion matrix
#####--      0      1
#####0    52     35
#####1  5393  11725



### SMOTE Oversampling
This method was about the same as the random oversampling with accuracy around 63.7% and precision and recall at 0.01 and 0.6 respectively.

#### SMOTE Oversampling confusion matrix

#####--      0      1
#####0    52     35
#####1  5526  11592

### Undersampling
This method seemed a little worse than the Oversampling methods as the accuracy was about 53% and precision and recall at 0.01 and 0.61 respectively.  More high-risk loans slipped through, and more low-risk loans were classified as high-risk.

#### Undersampling confusion matrix

#####--      0     1
#####0    53    34
#####1  9424  7694

### SMOTEENN (Over and Undersampling)
This method seemed to be fairly good.  While the accuracy was not amazing at 64%, and the precision at 0.01, the recall was good at 0.7.  This is a pain in that a lot of low-risk loans were flagged as high risk, but good in that not as many high-risk loans slipped through as low-risk.

### SMOTEENN (Over and Undersampling) confusion matrix
#####--      0     1
#####0    61    26
#####1  7232  9886


### Balanced Random Forest Classifier
This method has been the best so far.  The accuracy was almost 79%, and the precision of 0.04 and recall of 0.67 have been the highest of all the models.

#### Balanced Random Forest Classifier confusion matrix
#####--      0      1
#####0    58     29
#####1  1560  15558

### Easy Ensemble AdaBoost Classifier
This is by far the best model of the 6.  The accuracy was great at 92.5%, and the precision of 0.07 and recall of 0.91 are amazing in comparison to the rest.  Of the 87 high-risk loans, all by 8 were flagged correctly.  And under 1,000 of the over 17,000 low-risk loans were flagged as high-risk. 

#### Easy Ensemble AdaBoost Classifier confusion matrix
#####--     0      1
#####0   79      8
#####1  979  16139

## Summary
In summary, the ensemble learning algorithms gave the best results from a risk perspective.  I would use one of these models if I were doing this in the real world as high-risk loans could be very costly to a company.  