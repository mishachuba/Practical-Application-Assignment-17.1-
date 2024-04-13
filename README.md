The business objective of this project is to create an optimal classification model that would identify the target audience for future marketing campaigns with a high probability of subscribing to the term deposit product of the bank. The model should also help to identify characteristics that lead to a higher campaign conversion rate and ultimately improve resource allocation.

According to the paper accompanying the project, there were 29 input variables (features) already removed from the original dataset during the feature engineering and exploration process as they had little or no impact on the target variable. For example, 'sex' feature was removed since the rate of success for male and female was almost the same. Therefore, after visualizing and analyzing the remaining features in the dataset, I decided to keep them all. However, I used dimensionality reduction techniques like PCA to optimize the feature selection process during subsequent modeling. The only column I discarded was 'duration', since it isn't known before a call is performed and should only be included for benchmark purposes. The final dataset was transformed using StandardSacaler for numerical columns and OneHotEncoder for categorical columns.


The  Majority Class Baseline on the test set was 0.8941 determined by the DummyClassifier. In the first iterations of the modeling, I set up four classification models with default settings. The results are displayed in Table 1 below. Logistic Regression and SVM performed the best with very similar results across all metrics, although SVM took more time to train and predict. KNN accuracy was similar to the Majority Class Baseline, whereas the Decision Tree underperformed the baseline. 

Table 2 below displays the results of the finetuned classifications models and Table 3 shows the percentage difference between them and the default settings models. In this iteration, Logistic Regression performed the best with hyperparameters set to {'logistic__C': 0.046415888336127774, 'pca__n_components': None}. Although the accuracy score improved only by 0.4% to 0.9049, the precision increased by 16% to 0.7200. Since the business objective is to identify the target audience for future marketing campaigns with a high probability of subscribing to the term deposit product, optimizing the model for the true positives will yield the highest return on investment. The Decision Tree model performed the worst again, but it had the highest percentage improvement of 4.8% in accuracy and 59.2% in precision with hyperparameters set to {'dt__max_depth': 5, 'dt__min_samples_leaf': 1, 'dt__min_samples_split': 2}.

Table 1

<img width="558" alt="Screenshot 2024-04-12 at 4 52 49 PM" src="https://github.com/mishachuba/Practical-Application-Assignment-17.1-/assets/153693308/748b993c-9a7d-4ca7-a82e-ee3ac5370161">

Table 2

<img width="554" alt="Screenshot 2024-04-12 at 4 54 23 PM" src="https://github.com/mishachuba/Practical-Application-Assignment-17.1-/assets/153693308/7b054728-1dc2-4716-86c4-9ce700e19b18">

Table 3

<img width="571" alt="Screenshot 2024-04-12 at 4 55 05 PM" src="https://github.com/mishachuba/Practical-Application-Assignment-17.1-/assets/153693308/7446e510-ab56-4638-9d13-33fec1aab08d">
