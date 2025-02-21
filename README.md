# Absenteeism at the workplace
In this repository, I will be going through a walk through project that was on a [datascience course.](https://www.udemy.com/course/the-data-science-course-complete-data-science-bootcamp/) The project focuses on absenteeism at a workplace.
The absenteeism dataset contains records of employee absenteeism along with various factors that may influence absenteeism at a workplace. These factors include reason for absence, date, transportation expenses, distance to work, age, workload, BMI, education level, number of children and pets, and the total absenteeism time in hours.

## Goal
The purpose of the project was to predict excessive absenteeism at the workplace with the features given in the dataset.
To do this, we had to first preprocess the dataset,
create a logistic regression model,
then finally integrate the model then predict excessive absenteeism given a whole new dataset that our model has never seen.

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

## Building the model
First thing we did here was to create our target variable. We did that by finding the median number of hours (3 in this case) that employees had been absent for then assigning either a 1 for anything above the median value to represent excessive absenteeism and 0 for everything else.

After doing this, we had to standardize our inputs, split the data into training and test sets, build the model, trained and tested the accuracy of the model then interpreted the results.

While interpreting the results, we realize that there are some inputs that are of little significance to the model. We also realize that our Reasons and Education inputs should also not be standardized.
