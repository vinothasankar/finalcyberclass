Source code - cyberclass Presentation - finalcyber.pdf Model - random_forest_smote.pkl

Classifying Cybersecurity Incidents with Machine Learning Utilizing the comprehensive GUIDE dataset, our goal is to create a classification model that categorizes incidents as true positive (TP), benign positive (BP), or false positive (FP) based on historical evidence and customer responses. The model should be robust enough to support guided response systems in providing SOC analysts with precise, context-rich recommendations, ultimately improving the overall security posture of enterprise environments. Approach:

Data Exploration and Understanding: Initial Inspection: Started by loading the train.csv dataset and performed an initial inspection to understand the structure of the data, including the number of features, types of variables (categorical, numerical), and the distribution of the target variable (TP, BP, FP). Exploratory Data Analysis (EDA): Used visualizations and statistical summaries.

Data Preprocessing: Handling Missing Data: Identified the missing values in the dataset and decided to remove affected rows and columns. Converting numeric to Categorical Variables: Convert categorical features represented as  numeric to category(city,state)

Data Splitting: Train-Validation Split: Before diving into model training, splited the train.csv data into training and validation sets. This allows for tuning and evaluating the model before final testing on test.csv. Typically, a 80-20 split is used, but this can vary depending on the dataset's size. Stratification: As the target variable is imbalanced, used stratified sampling to ensure that both the training and validation sets have similar class distributions.

Model Selection and Training: Baseline Model: Start with a simple baseline model, such as a logistic regression. Advanced Models: Experiment with more sophisticated models such as Random Forests,DecisionTree. Each model was tuned using technique random search over hyperparameters.

Cross-Validation: Implemented cross-validation (e.g., k-fold cross-validation) to ensure the model's performance is consistent across different subsets of the data. This reduces the risk of overfitting and provides a more reliable estimate of the model's performance. And models performed well.

Advanced model: XGBoost,Neural Network,LightGBM

Model Evaluation and Tuning: Performance Metrics: Evaluated the model using the validation set, focusing on macro-F1 score, precision, and recall. Analyze these metrics across different classes (TP, BP, FP) to ensure balanced performance.

Model Interpretation: Feature Importance: After selecting the best model, analyze feature importance to understand which features contribute most to the predictions. Removed least important columns.

Feature Engineering : MitreTechniques column contained list of techniques separated by ; ,so created new columns for each technique 

Final Evaluation on Test Set: Testing: Now the model is finalized and optimized, evaluated it on the test.csv dataset. Report the final macro-F1 score, precision, and recall to assess how well the model generalizes to unseen data. Comparison to Baseline: Compare the performance on the test set to the baseline model and initial validation results to ensure consistency and improvement.

Accuracy on Known data - 75.34 Accuracy on Unknown data - 74.5

