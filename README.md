# Credit Risk Analysis
## Overview
In this analysis, I used four different resampling algorithms and two ensemble algorithms to predict credit risk based on user credit card data. The data was split into training and testing sets to train each model and then to test how well each model can predict credit risk. The performance of each algorithm was asssessed based on accuracy, precision, and recall.

Based on their performances, I made a recommendation as to which algorithm should be used in order to predict credit risk.

All models were created with a random state of 1.

## Results
The results for each model was as following

* Naive Random Oversampling

  - Accuracy Score: 0.662
  - Precision Score: 0.01
  - Recall Score: 0.72

![naive_oversample](https://github.com/teruki-i/Credit_Risk_Analysis/blob/main/resources/random_oversample_classification.png)

* SMOTE Oversampling

  - Accuracy Score: 0.657
  - Precision Score: 0.01
  - Recall Score: 0.61

![SMOTE](https://github.com/teruki-i/Credit_Risk_Analysis/blob/ba2202418c69f0a0e83ddc10fec7092f39dc389a/resources/SMOTE_classification.png)

* Cluster Centroids Undersampling

  - Accuracy Score: 0.657
  - Precision Score: 0.01
  - Recall Score: 0.69

![undersampling](https://github.com/teruki-i/Credit_Risk_Analysis/blob/main/resources/undersample_classification.png)

* Combination Undersampling and Oversampling (SMOTEENN)

  - Accuracy Score: 0.646
  - Precision Score: 0.01
  - Recall Score: 0.72

![SMOTEENN](https://github.com/teruki-i/Credit_Risk_Analysis/blob/main/resources/SMOTEENN_classification.png)

* Balanced Random Forest Classifier
  - Accuracy Score: 0.789
  - Precision Score: 0.03
  - Recall Score: 0.70

![Balanced_Random_Forest](https://github.com/teruki-i/Credit_Risk_Analysis/blob/main/resources/balanced_random_forest_classification.png)

* Easy Ensemble Classifier

  - Accuracy Score: 0.932
  - Precision Score: 0.09
  - Recall Score: 0.92

![easy_ensemble](https://github.com/teruki-i/Credit_Risk_Analysis/blob/main/resources/easy_ensemble_classification.png)

## Summary
All four of the resampling algorithms performed similarly at identifying credit card users with high credit risks. All had accuracy scores between 0.64 and 0.67 and precision scores of 0.01. There was more variation in recall with both the naive oversampling and combination (SMOTEENN) algorithms scoring highest at approximately 0.72 and the SMOTE oversampling algorithm scoring the lowest at approximately 0.61. 

The accuracy scores suggest that these models are moderately accurate. However, the low precision scores indicate that they also have many false positives. The recall scores then indicate that these models fail to capture between 30 to 40 % of high risk credit card users.

The balanced random forest classifier performed better than all four resampling algorithms in terms of accuracy and precision. However, recall for this model was slightly lower than both the naive oversampling and SMOTEENN algorithims. So while this algorithm has fewer false positives, it still fails to capture approximately 30% of high risk users.

The easy ensemble classifier performed the best out of all six algorithms. With an accuracy score of approximately 0.932, the model was significantly more accurate than the other five. The precision score was much also higher than the rest, thus returning the fewest false positives. And with a recall score of approximately 0.92, the algorithm failed to capture only about 8% of high risk users.

## Recommendation

Based on these results, I recommend using the easy ensemble classifier in order to predict credit risk. The high recall score suggests that this algorithm has the lowest risk of failing to identify low risk users. And as this model also has the highest precision score, there would be fewer false positives that require additional evaluation in order to re-assess their risk than there would be with the other algorithms.