# Sparkify User Churn prediction


***Sparkify — Digital Music Service***

Sparkify is a music streaming like (Spotify and Deezer). Users can listen music for free or paid.
They can upgrade from free to to paid user or the inverse meaning downgrad paid to free. They also can 
cancel subscription at any time

I analyze user churn behaviour and create features and churn label.
Finaly I create machine learning pipeline to predict churn.
The real relevance of the project is scaling Machine Learning by using Big Data technology like Spark.

The job is deep dive analysis the data, by cleaning, creating relevant features, create pipeline to have best Churn prediction model


# Required libraries
- Python 3
- PySpark ML
- Jupyter

# Data modeling

 ## Imbalanced data
 Most machine learning algorithms ignore unbalanced data and have poor performance.
 To address this problem there is some technique such as, Oversampling, Undersampling or an hybrid approach.
 We also have **SMOTE** sampling which is a Data augmentation for the minority class.
 ## Baseline model
 I train four classification model: Logistic Regression, Decision tree, Random Forest and Gradient boosting and  compare their performance.
 Thought Gradient boosting give best **f1-score** but take a long trainning time. I decided to take Decision tree and Logistic regression  as baseline
 model because they  both have reasonnable training time and seem to have better **f1-score** after tunning parameters 

## Stacking Model
After tuning baseline, I create new dataset by stacking prediction from baseline.
New features are the predicted probability. I stacke them an create a new Vector Assembler
## Final Model
Finaly I tune a random forest in stacked data and get approximatively  f1-score of 0.7

Considering this is only a quit mini dataset and our purpose is scaling this up to the total 12G dataset, so, the random forest is the best model from now on in this project.

Here is my medium [blog post](https://medium.com/p/e8d57c27f879/edit)

# Aknowledegments
Thanks to Udacity for providing data and making learn funny. This project help to go deep dive big data tool spark  for machine learning.
# References
[smote](https://machinelearningmastery.com/smote-oversampling-for-imbalanced-classification/)<br>
[smotepyspark](https://medium.com/@haoyunlai/smote-implementation-in-pyspark-76ec4ffa2f1d)<br>
[pysparkml](https://spark.apache.org/docs/2.2.0/ml-features.html)


