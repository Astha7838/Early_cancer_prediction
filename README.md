# Early_cancer_prediction
Apply data modeling techniques to clinical data obtained using a novel blood test called CancerSEEK with relevant features to help identify cancer in early stages. 

PREDICTIVE MODELLING 

Step I: Predicting if a person is cancer positive or negative (binary classification) 
It can be used to detect if the cancer is present given the concentration of the 8 key protein biomarkers.  The output for this model is a binary class which can take either ‘positive’ or ‘negative’ values. Positive indicates that cancer is present on the test instance and negative means there is no cancer
Step 2: Localization of cancer (multi-classification)
with 8 classes for localization of cancer, which means the type of cancer is detected, out of eight common cancers - ovary, liver, esophagus, pancreas, stomach, colorectal, lung, and breast cancer.  The output will take only a single value from the above 8 classes.   

MODEL DESCRIPTION

To build cancer detection models , we consider it as a supervised learning task from the machine learning perspective. Therefore, we have selected a range of multiclass supervised learning algorithms: 
                                                         1.  Machine Learning Algorithm - Random Forest
                                                         2. Deep Learning Algorithm – feed forward neural network

Original shape of dataset: (1817, 54)
After removing Target feature and other features with no or less correlation shape of the dataset : (1817, 41)
For Binary we have considered 9 major features and target feature indicating presence of cancer or not. (shape – 1817 rows, 9 columns)
For Multiclass we have considered 41 features which includes all protein biomarkers (39) along with “Gender” and “omega score”.We have dropped all rows of ‘normal’ or healthy individuals. (1005 rows , 41 columns)
We have used the method ‘Mutual Information’ which calculates the information gain each feature adds in predicting the target variable. Higher the value, more important the feature for the target prediction. 
75% Train data, 25% Test data is allocated for both the classifications. We do not use stratified sampling here since for some type of cancers the data points are less in number and hence, we let the sampling be random. 

WHY LINEAR CLASSIFICATION?

Linear models such as Logistic regression cannot be used for this type of data Hence, we have chosen a tree-based model – random forest to start out with our analysis. Since random forest generalizes better than decision tree and works well with non-linear data 
For deep learning, since the problem here is a very typical supervised learning task with well-crafted input features. Therefore, we have adopted the deep feedforward neural networks for both binary classification and Multiclass classification problem.

BINARY EVALUATION 

Deep Learning
Sensitivity : 0.8972
Specificity : 0.8425

Random forest
Sensitivity : 0.9146
Specificity : 0.8947 

