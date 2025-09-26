Logistic Regression Classifier for Breast Cancer Prediction.

This script loads the Wisconsin Breast Cancer dataset, preprocesses the data,
trains a logistic regression model, and evaluates its performance.
It includes steps for data cleaning, feature scaling, model training,
and evaluation using metrics like confusion matrix, precision, recall, and ROC-AUC curve.
It also includes an explanation of the sigmoid function and demonstrates
how to tune the classification threshold.

Step1: Data Cleaning and Preprocessing
Drop the 'id' column as it's just an identifier and not a predictive feature.
There also appears to be an unnamed, empty column at the end, which we'll drop.
The 'diagnosis' column is our target variable. We need to convert it from categorical ('M'/'B') to numerical (1/0). M (Malignant) = 1   
B (Benign) = 0.

Step 2: Train/Test Split and Feature Standardization
Split the data into training and testing sets.
80% for training, 20% for testing. stratify=y ensures the proportion of malignant/benign cases is the same in both train and test sets.
Standardize the features. Logistic Regression is sensitive to the scale of features. Standardization (or Z-score normalization) scales features to have a mean of 0 and a standard deviation of 1.

Step 3: Fit a Logistic Regression Model
Initialize and train the model

Step 4: Evaluate the Model
Make predictions on the test set: a. Confusion Matrix b. Precision, Recall, F1-Score c. ROC Curve and AUC Score

Step 5: The Sigmoid Function and Threshold Tuning
The heart of logistic regression is the sigmoid function. It takes any real-valued number
and maps it into a value between 0 and 1. This output can be interpreted as the
probability of the sample belonging to the positive class (in our case, 'Malignant').

Equation: P(y=1) = 1 / (1 + e^(-z))
where 'z' is the linear combination of features (w1*x1 + w2*x2 + ... + b).

By default, if this probability is > 0.5, the model predicts 1 (Malignant),
otherwise, it predicts 0 (Benign). This 0.5 value is the 'classification threshold'.
We can adjust this threshold to make the model more or less sensitive to predicting
the positive class, which trades off precision and recall.



