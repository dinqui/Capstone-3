# Absenteeism at Work
Appropriate staffing is critical to the success of any business. For a courier company, understaffing can result in delayed deliveries and reduce both the profit and reputation of the company. How can absences of a day or more be predicted to ensure adequate staffing?

## 1. Data 
A courier company in Brazil has records of absenteeism from July 2007 to July 2010. For each absence the employee ID, reason and length of absence as well as descriptive features of the employee are recorded. The dataset consists of 36 employees and 740 incidents.

The dataset was sourced from the UCI Machine Learning Repository. 
[Absenteeism at work Data Set] (https://archive.ics.uci.edu/ml/datasets/Absenteeism+at+work)

## 2. Data Cleaning 
[Data Wrangling](https://github.com/dinqui/Capstone-3/blob/main/Capstone%203%20-%20Data%20Wrangling%20%26%20EDA%20.ipynb)

The dataset was already tidy as there was no missing values. Many of the demographic columns were coded using numerics. Therefore, description columns were added to the dataframe for these columns. 

## 3. EDA 
[EDA](https://github.com/dinqui/Capstone-3/blob/main/Capstone%203%20-%20Data%20Wrangling%20%26%20EDA%20.ipynb)

Each category was plotted compared to the number of absence instances and separated by whether the absence instance was less than a day or a day or more. This identified three abesnce reasons as causing a large number of absences that were less than a day - medical and dental consultations and physiotherapy. 

![Plot of absences by reason description](https://github.com/dinqui/Capstone-3/blob/main/Images/download.png)

It was also interesting to observe that Fridays and the summer did not have an overwhelmingly larger portion of absences compared to other days of the week or seasons. 

![Plot of absences by day](https://github.com/dinqui/Capstone-3/blob/main/Images/Day.png)
![Plot of absences by season](https://github.com/dinqui/Capstone-3/blob/main/Images/Seasons.png)

Absences were also investigated at an employee level. While there were some interesting observations, due to the small number of employees (only 36) there was not adequate data to create a model based on individuals. For example, just a couple employees accounted for many of the absences. 

![Plot of absences by employee](https://github.com/dinqui/Capstone-3/blob/main/Images/Employee.png)

## 4. Feature Engineering
[Feature Engineering](https://github.com/dinqui/Capstone-3/blob/main/Capstone%203%20-%20Data%20Wrangling%20%26%20EDA%20.ipynb)

An indicator was created to identify whether an absence was for less than a day, or for a day or more, where a day is defined as eight hours. 

## 5. Modeling
[Model Selection] (https://github.com/dinqui/Capstone-3/blob/main/Capstone%203%20-%20Pre-processing%20and%20Model%20.ipynb)

Logistic Regression, Decision Trees, and Random Forest models were applied to the dataset.

The models were evaluated using a balanced accuracy score since there are significantly more absences that are less than a day than absences that are 1 day or more. Additionally, confusion matrices were plotted. 

Since understaffing is a more critical issue for a courier company, I choose the Decision Tree model with a max depth of 6 as it minimized the number of type 2 errors - the number of absences that were predicted to be less than a day that were actually a day or more. In this business case, overstaffing would be preferable as all deliveries would be able to be made in the timeframe allotted and in the worst case employees could be sent home early. The alternative for understaffing could leave important packages undelivered at the end of the business day which is unacceptable. 

## 6. Improvements 
To continue this analysis in the future, I would consider the percentage of absences that are less than a day for each category. If certain categories are only associated with absences less than a day I would consider dropping those instances from the dataframe. 

Additionally, the dataset did not include the year that the absence was recorded so acquiring timestamped data could help identify trends in absencnes over time. 

Furthermore, since this project focused on the event level, it could be interesting to return to the data and create a model at the employee level. 

## 7. Conclusions & Recommendations 
The model performed well enough to be used to predict the length of employee absences and to plan for staffing coverage using the nature of the absence as well as various demographics of the employee using leave. 
