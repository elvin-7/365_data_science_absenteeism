# Absenteeism at the workplace
In this repository, I will be going through a walk through project based on a dataset from [365 datascience course on udemy.](https://www.udemy.com/course/the-data-science-course-complete-data-science-bootcamp/) The project focuses on absenteeism at a workplace.
The dataset contains records of employee absenteeism and various factors that may influence it such as reason for absence, date, transportation expenses, distance to work, age, workload, BMI, education level, number of children and pets, and the total absenteeism time in hours.

## Goal
The purpose of the project was to predict excessive absenteeism using logistic regression. The process involved:
1. Preprocessing the dataset (Cleaning and transforming the data.)
2. Building a logistic regression model
3. Integrating the model (Using the model on new data for predictions)

## Data Preprocessing
Here, we explored the dataset, removed unnecessary columns, created dummy variables and grouped different elements in some columns together.

At the end of this process the following columns had been removed:
- ID
- Reason for absence
- Date

and were replaced with:
- Reason_1
- Reason_2
- Reason_3
- Reason_4
- Month Value
- Day of the Week

The end results were saved as a new csv file so we could begin the creating our logistic regression model to help predict excessive absenteeism

## Building the logistic regression model
First thing we did here was to create our target variable. We did that by finding the median number of hours (3 in this case) that employees had been absent for then assigning either a 1 for anything above the median value to represent excessive absenteeism and 0 for everything else.

After doing this, we had to standardize our inputs, split the data into training and test sets, build the model, trained and tested the accuracy of the model then interpreted the results.

While interpreting the results, we realize that there are some inputs that are of little significance to the model. These inputs are the Daily Work Load Average, Day of the Week and Distance to work inputs.

We also realize that our Reasons and Education inputs should also not be standardized. This is because the values in these inputs are categorical. for example, 0 in Education represents one category while 1 represents another.
If we standardize these inputs, their values will no longer make any sense.

We then simplify our model by removing the inputs we no longer need and adjusting our model so that we only standardize our numerical inputs.

We once again train and test our model and we get a train accuracy of 77.32% and a test accuracy of 75%.

We then save the final model and the scaler used for standardization as pickle files.

## Model Integration
To apply the model to new data, we:
1. Create a Python class to preprocess new datasets in the same way as the original dataset.
2. Import the trained model, apply preprocessing on the new dataset and predict whether or not an employee is likely to be excessively absent.

## Conclusion
This project demonstrates how logistic regression can be used to make predictions. By analyzing key factors, we developed a model with a training and test accuracy of 77.32% and 75% respectively.

We also saw that factors like Daily Work Load Average and the Day of the Week had little impact on absenteeism at this particular workplace.

This model could help businesses identify employees at risk of excessive absenteeism, reduce excessive absenteeism by addressing key factors (health programs, transportation assistance) and improve workplace policies
