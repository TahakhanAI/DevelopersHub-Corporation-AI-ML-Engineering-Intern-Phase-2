Task Overview

Objective of the task:

To build a reusable and production-ready machine learning pipeline for predicting customer churn using the Telco Churn Dataset. This involved implementing data preprocessing steps, training various models, performing hyperparameter tuning, and exporting the complete pipeline.

Methodology / Approach:

Data Acquisition and Initial Exploration: Fetched the Telco Churn dataset and performed initial data checks, including inspecting data types and missing values.

Data Preprocessing and Cleaning: 

Handled missing values in 'TotalCharges' by converting it to numeric and imputing with the median. Converted the 'Churn' target variable to a binary format. Removed irrelevant 'customerID' feature.

Data Splitting: 

Divided the dataset into training and testing sets to ensure robust model evaluation.

Pipeline Construction: 

Utilized sklearn.pipeline.Pipeline and sklearn.compose.ColumnTransformer to create a comprehensive preprocessing pipeline, handling numerical scaling (StandardScaler) and categorical encoding (OneHotEncoder).

Model Training and Selection: 

Integrated Logistic Regression and Random Forest classifiers into separate pipelines.

Hyperparameter Optimization: 

Employed GridSearchCV to systematically tune hyperparameters for both Logistic Regression and Random Forest models, optimizing for accuracy through cross-validation.

Model Evaluation: 

Evaluated the best-performing models on the held-out test set using metrics like accuracy and a classification report.

Pipeline Export: 

Saved the final best-performing end-to-end pipeline using joblib for future deployment and inference.
.
Key results or observations:

The ColumnTransformer effectively handled different preprocessing steps for numerical and categorical features within a single pipeline, making the workflow streamlined.
GridSearchCV identified optimal hyperparameters for both Logistic Regression and Random Forest, which can lead to improved model performance compared to default settings.
The evaluation on the test set provided a realistic assessment of how the models would perform on unseen data.
The final exported joblib file represents a complete, ready-to-use ML pipeline, encompassing all preprocessing logic and the trained model, ensuring consistency and ease of deployment.