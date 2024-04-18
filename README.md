# Seasonal Flu Vaccines Prediction Analysis
![image](https://github.com/MansionAnthony/Seasonal-FLU-Vaccine-Prediction_Analysis/assets/160514617/706b542b-c513-456a-9277-9cb5da0acf99)
Photo by (https://www.fda.gov/news-events/public-health-focus/seasonal-flu-influenza-and-fda)
## Project Overview
A study published in the Journal of the American Medical Association estimated that childhood vaccinations administered from 1994 to 2013 in the US would save $402 billion in direct costs and $1.5 trillion in societal costs.

This project offers a comprehensive analysis of what factors (e.g., doctor's recommendation for a vaccine) have the biggest influence on a person from getting vaccinated. The project employs two predictive models (i.e., logistic regression and decision tree) to best predict the vaccination outcome based on various factors provided by the dataset.

The analysis aims to offer valuable insights to Jelly Insurance Co's leadership team, empowering them to take the most effective actions to boost vaccination rates among policyholders. This initiative seeks to reduce insurance payouts resulting from non-vaccination.

## Business Problem
Jelly Insurance Co's policyholders have the lowest vaccination rate amongst all US insurance / healthcare companies. In order to reduce insurance payouts resulting from low vaccination rate, the leadership team has tasked the team to delve into vaccination databases for insights.

## Data Understanding and Preparation
For this project, following dataset was utilized for the analysis:

- 2009 National H1N1 and Flu Vaccination Survey by the United States National Center for Health Statistics
  
The dataset comprises of ~27k phone survey data conducted between late 2009 and early 2010. The phone survey asked respondents whether they had received the H1N1 and seasonal flu vaccines, in conjunction with questions about them. The additional questions include: social, economic, demographic background, opinions on risks of illness and vaccine effectiveness, and behaviors towards mitigating transmission.

## Analysis / Modeling
Since the target variable is binary, whether a respondent got vaccinated or not, the team used Logistic Regression and Decision Tree models, which are optimized for binary classification / prediction. 

As a starting point, the team created a baseline model based on our domain knowledge. Then, the team created 4 additional models to improve prediction/classification performance. The team chose accuracy score to evaluate the performance of the model. 

Based on our iterations, the best model was a Logistic Regression model with L1 Regularization, which had an accuracy of 83%. Please see below for the details of the model and the output. 

### Log Regression Model with All Columns and L1 Regularization
```
# Log Regression
logreg2 = LogisticRegression(penalty = 'l1', solver = 'saga',random_state = 5)
logreg2.fit(X_train_m2_concat_sc, y_train_m2)
```
```
Accuracy Score for Train Data:    0.8220455749867515
Accuracy Score for Test Data:     0.8295888088172955
Precision Score for Train Data:   0.8348603839441536
Precision Score for Test Data:    0.8344887348353552
Recall Score for Train Data:      0.8058538639713624
Recall Score for Test Data:       0.8202725724020443
```
### The roc_curve 
![image](https://github.com/MansionAnthony/Seasonal-FLU-Vaccine-Prediction_Analysis/assets/160514617/e8810834-55f8-4f5d-9214-0016792bf863)
### The confusion_matrix plot 
![image](https://github.com/MansionAnthony/Seasonal-FLU-Vaccine-Prediction_Analysis/assets/160514617/2fbef0ef-dcf1-40f1-aa19-c2407098ce5e)

### Three Factors that Have the Highest Positive Coefficient are:

- Doctor's Recommendation for Seasonal Vaccine
- Opinion on Effectiveness of Seasonal Vaccine
- Opinion on Risk of Getting Seasonal Flu
  
## Conclusion
As discussed in the introduction, mass immunization / vaccination has an immense societal and economic benefits as well as positive financial impact on insurance / healthcare companies.

In order to increase the vaccination rate, we propose Jelly Insurance Co's leadership to implement the following strategies:

- Educate primary care physicians in the network to recommend vaccination for seasonal flu
- Increase marketing campaign budget for effectiveness of seasonal flu vaccine
- Raise awareness of seasonal flu risk via various marketing and communication channels

## Future Investigations
  - Perform analysis with balanced racial representation
  - Extend the analysis to the policyholders
  - Investigate correlation amongst different vaccines

## For More Information
Please review our full analysis in jupyter notebook ([Seasonal Flu Vaccination Prediction Analysis](https://github.com/MansionAnthony/Seasonal-FLU-Vaccine-Prediction_Analysis/blob/Main/Seasonal%20Flu%20Vaccination%20Prediction%20Analysis.ipynb))\
And also refer to our ([Presentation](https://github.com/MansionAnthony/Seasonal-FLU-Vaccine-Prediction_Analysis/blob/Main/presentation.pdf)) 

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
