# Seasonal Flu Vaccines Prediction Analysis
## Project Overview
A study published in the Journal of the American Medical Association estimated that childhood vaccinations administered from 1994 to 2013 in the US would save $402 billion in direct costs and $1.5 trillion in societal costs.

This project offers a comprehensive analysis of what factors (e.g., doctor's recommendation for a vaccine) have the biggest influence on a person from getting vaccinated. The project employs two predictive models (i.e., logistic regression and decision tree) to best predict the vaccination outcome based on various factors provided by the dataset.

The analysis aims to offer valuable insights to Jelly Insurance Co's leadership team, empowering them to take the most effective actions to boost vaccination rates among policyholders. This initiative seeks to reduce insurance payouts resulting from non-vaccination.
## Business Problem
Jelly Insurance Co's policyholders have the lowest vaccination rate amongst all US insurance / healthcare companies. In order to reduce insurance payouts resulting from low vaccination rate, the leadership team has tasked the team to delve into vaccination databases for insights.
## Data Understanding and Preparation
For this project, following dataset was utilized for the analysis:

- 2009 National H1N1 and Flu Vaccination Survey by the United States National Center for Health Statistics
- The dataset comprises of ~27k phone survey data conducted between late 2009 and early 2010.
  
The phone survey asked respondents whether they had received the H1N1 and seasonal flu vaccines, in conjunction with questions about them. The additional questions include: social, economic, demographic background, opinions on risks of illness and vaccine effectiveness, and behaviors towards mitigating transmission.
## Analaysis / Modeling section
First we created simple logistic regression model as a baseline and two more each from logistic regression from decision tree.
Then we evaluate our model based on accuracy. For our case the best model is a logistic regression and  has an accuracy of 83%. 
### Log Regression Model with All Columns and L1 Regularization
```
# Log Regression
logreg2 = LogisticRegression(penalty = 'l1', solver = 'saga',random_state = 5)
logreg2.fit(X_train_m2_concat_sc, y_train_m2)
```
```
# Predict based on Log Regression model
y_train_m3_pred = logreg2.predict(X_train_m2_concat_sc)
y_test_m3_pred = logreg2.predict(X_test_m2_concat_sc)
```
```
# Evaluation Metric #1 - Accuracy, Precision, Recall scores
m3_train_acc_score = accuracy_score(y_train_m2, y_train_m3_pred)
m3_test_acc_score = accuracy_score(y_test_m2, y_test_m3_pred)
m3_train_pre_score = precision_score(y_train_m2, y_train_m3_pred)
m3_test_pre_score = precision_score(y_test_m2, y_test_m3_pred)
m3_train_recall_score = recall_score(y_train_m2, y_train_m3_pred)
m3_test_recall_score = recall_score(y_test_m2, y_test_m3_pred)
```

## Future Investigations

  - Perform analysis with balanced racial representation
  - Extend the analysis to the policyholders
  - Investigate correlation amongst different vaccines
## For More Information
Please review our full analysis in jupyter notebook ([Seasonal Flu Vaccination Prediction Analysis](https://github.com/MansionAnthony/Seasonal-FLU-Vaccine-Prediction_Analysis/blob/Main/Seasonal%20Flu%20Vaccination%20Prediction%20Analysis.ipynb))\
And also refer to our 
- ([Presentation](https://github.com/MansionAnthony/Seasonal-FLU-Vaccine-Prediction_Analysis/blob/Main/presentation.pdf)) 

## Contributors

[Sang-won Shim](https://github.com/sangwon224)

[Anthony Mansion](https://github.com/MansionAnthony)

[Ermiyas Sidama](https://github.com/ermiyas-sidama)

## Repository Structure
```
|— .gitignore                                                <- gitignore exclude selected file execute
|— README.md                                                 <- The top-level README for reviewers of this project
|— Seasonal Flu Vaccination Prediction Analysis.ipynb        <- Interactive computing environment including analysis in Jupyter notebook
|— Data                                                      <- Both sourced externally and generated from code
    |— master_dataset.csv                                    <- Cleaned data
    |— training_set_features.csv                             <- Raw data
    |— training_set_labels.csv                               <- Raw data
|_ presentation.pdf                                          <- PDF version of project presentation
```
