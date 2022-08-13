## Problem statement
Can we know which employees will be excessively absent? if we can then we can plan our tasks assignments to ensure that the company is properly resourced to mitigate the effect of an absent employee to the overall performance of the organisation.
## Approach
  1.	In Absenteeism Data Preprocessing file, We import the raw data, clean it and export the preprocessed csv file.
  2.	In the Absenteeism Regression file, we import the preprocessed csv file, carry out feature engineering and build our regression model. After training, & evaluating       our regression model we export/ pickle the model.
  3.	In the integration file, we import and deploy the regression model. We also build the data pipeline for preprocessing new data
## Absenteeism Data Preprocessing m
  1.	Import relevant libraries and load raw data.
  2.	Descriptive analysis and data cleaning.
  3.	Data preprocessing and feature engineering: we convert the “reason for absence” column (which is a categorical nominal data) using one-hot encoding to enable us       feed it into our model without creating a bias based on the order of the numbers. Since there are 28 different reasons for absence, we will use qualitative           analysis to group them as follows: 
  
      1 – 14: Employee Absence due to diseases.
      15 – 17: Absence due to pregnancy and pregnancy related events.
      18-21: Poisoning and signs not categorized elsewhere
      21-28: light reasons such as dental appointments
  4.	Export preprocessed data as a csv file.

## Absenteeism Regression
  1.	Import relevant libraries and load preprocessed data.
  2.	Feature Engineering; 
  a.	We will use the median of the “absenteeism time in hours” as the threshold to determine if an employee is absent or not.

  3.	Scale the data set using sklearn standardscalar
  4.	Split and train a Logistic regression model.
  5.	Evaluate the model performance

## Absenteeism Integration m
  1.	Import relevant libraries.
  2.	Build data ingestion pipeline for cleaning new data.
  3.	Import/unpickle model.
  4.	Deploy model

