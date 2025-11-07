# The aim is to create an ML model that predicts which phone leads are likely to accept a long-term deposit, so that only those leads are called.

Link to the notebook: https://github.com/martin7x7/Assignment17_1/blob/main/prompt_III.ipynb

## Files in repository
1)	prompt_III.ipynb – contains requested code and answers to all questions
2)	bank-additional-full.7z – contains data that were analyzed and used for training
3)	bank-additional.7z - contains subset of data from bank-additional-full.7z
4)	LICENSE - license file

## Main tasks done
1) Two datasets containing the information required for model training were loaded and reviewed.
2) Data analysis was performed to understand how the features need to be processed for use in the model.
3) Data were prepared for model training:
   - Unnecessary columns were removed.
   - Label/target values were converted from yes/no to 1/0.
   - Text-based feature values were transformed into new encoded features.
   - Numerical feature columsn were scaled.
   - Training and test datasets were prepared
4) Several simple baseline models were created using only a subset of features to understand the base accuracy level.

5) Improved models were prepared:
   - Two LogisticRegression models were created using the larger dataset. The first used a subset of features, and the second used all features. The author decided to test with the 30 best features. The best model was the one using 30 features — **accuracy score: 0.8981**.
   - A process was developed to display the most important features contributing to the prediction results.
   - A DecisionTreeClassifier model was created with an **accuracy of 0.896086** and parameters: {'criterion': 'entropy', 'max_depth': 7, 'min_samples_leaf': 13, 'min_samples_split': 6}.
   - A KNeighborsClassifier model was created using the smaller dataset, with an **accuracy of 0.904854** and parameters: {'metric': 'manhattan', 'n_neighbors': 31, 'weights': 'uniform'}.
   - An SVC model was created using the smaller dataset, achieving an **accuracy of 0.904854** and parameters: {'C': 1, 'gamma': 'auto', 'kernel': 'rbf'}.
   - An SVC model was also created using the larger dataset, with an **accuracy of 0.8983** and parameters: {'C': 1, 'gamma': 'auto', 'kernel': 'rbf'}

## Main conclusions from data analysis
1) Overall, the author considers the SVC model with hyperparameters {'C': 1, 'gamma': 'auto', 'kernel': 'rbf'} to be the best, despite the KNeighborsClassifier achieving a similar result.
2) Training SVC models on large datasets is computationally intensive and significantly slower.
3) The author concludes that fewer columns can be used for model preparation than are provided in the source dataset. The SVC model was trained using 28 columns.

## Recomendations for next steps
1) It would be good to consider removing outliers for numeric features if any.
2) Maybe better subset of training data can be created by removing rows with unknown values.
3) It is quite hard to tell if tere is a point in training slower and more complicated models, if precision increasese only by 1% or 2%.
