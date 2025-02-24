# Absenteeism at the workplace
In this repository, I will be going through a walkthrough project based on a [dataset](https://github.com/elvin-7/365_data_science_absenteeism/blob/main/Absenteeism-data.csv) from [365 datascience's course on udemy.](https://www.udemy.com/course/the-data-science-course-complete-data-science-bootcamp/) The project is about absenteeism at a workplace.
The dataset contains records of employee absenteeism and various factors that may influence it such as reason for absence, date, transportation expenses, distance to work, age, workload, BMI, education level, number of children and pets, and the total absenteeism time in hours.

## Goal
The purpose of the project was to predict excessive absenteeism using logistic regression. The process involved:
1. Preprocessing the dataset (Cleaning and transforming the data.)
2. Building a logistic regression model
3. Integrating the model (Using the model on new data for predictions)

## [Data Preprocessing](https://github.com/elvin-7/365_data_science_absenteeism/blob/main/Absenteeism%20Preprocessing.ipynb)
Here, we explored the dataset, removed unnecessary columns, created dummy variables and grouped different elements in some columns together.

At the end of this process the following columns had been removed:
- ID
- Reason for absence
- Date

and these were replaced with:
- Reason_1
- Reason_2
- Reason_3
- Reason_4
- Month Value
- Day of the Week

The end results were saved as a new [csv file](https://github.com/elvin-7/365_data_science_absenteeism/blob/main/Absenteeism_preprocessed.csv) so we could begin creating our logistic regression model to help predict excessive absenteeism.

[View the Data Preprocessing Notebook](https://github.com/elvin-7/365_data_science_absenteeism/blob/main/Absenteeism%20Preprocessing.ipynb)

## [Building the Logistic Regression model](https://github.com/elvin-7/365_data_science_absenteeism/blob/main/Absenteeism%20Logistic%20Regression%20Model.ipynb)
Here, we:
1. Created the target variable:
   - Used the median absenteeism hours (3) as the benchmark
   - Assigned a 1 for anything above 3 hours to represent excessive absenteeism and 0 otherwise
2. Selected and standardized numerical inputs. We did not standardize our categorical inputs (Reason for Absence and Education).
3. Split the dataset into training and test sets.
4. Trained and tested the model and obtained a training and test accuracy of 77.32% and 75% respectively
5. Interpreted the model coefficients and removed insignificant features to help simplify the model.
  
We then saved the final model and the scaler used for standardization as files using pickle.

[View the Model Building Notebook](https://github.com/elvin-7/365_data_science_absenteeism/blob/main/Absenteeism%20Logistic%20Regression%20Model.ipynb)

## [Model Integration](https://github.com/elvin-7/365_data_science_absenteeism/blob/main/Absenteeism%20Model%20Integration.ipynb)
To apply the model to new data, we:
1. Created a [Python class](https://github.com/elvin-7/365_data_science_absenteeism/blob/main/absenteeism_module.py) to preprocess new datasets in the same way as the original dataset.
2. Imported the trained model, applied preprocessing on the [new dataset](https://github.com/elvin-7/365_data_science_absenteeism/blob/main/Absenteeism_new_data.csv) and used that to predict whether or not an employee is likely to be excessively absent. [View the Absenteeism predictions](https://github.com/elvin-7/365_data_science_absenteeism/blob/main/Absenteeism_predictions.csv)

[View the Model Integration Notebook](https://github.com/elvin-7/365_data_science_absenteeism/blob/main/Absenteeism%20Model%20Integration.ipynb)

## Conclusion
This project demonstrates how logistic regression can be used to make predictions. By analyzing key factors, we developed a model with a training and test accuracy of 77.32% and 75% respectively.

We also saw that factors like Daily Work Load Average and the Day of the Week had little impact on absenteeism at this particular workplace.

This model could help businesses identify employees at risk of excessive absenteeism, reduce excessive absenteeism by addressing key factors (health programs, transportation assistance) and improve workplace policies
