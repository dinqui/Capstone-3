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

The total number of hours absent by absence reason was investigated. Diseases of the musculoskeletal system and injuries led to the highest number of hours absent over the three year period.

During the exploratory data analysis, absences were investigated at an employee level. While there were some interesting observations, due to the small number of employees (only 36) there was not adequate data to create a model based on individuals. For example, just a couple employees accounted for many of the absences  



## 4. Feature Engineering
[Feature Engineering](https://github.com/dinqui/Capstone-3/blob/main/Capstone%203%20-%20Data%20Wrangling%20%26%20EDA%20.ipynb)

An indicator was created to identify whether an absence was for less than a day, or for a day or more, where a day is defined as eight hours. 

## 5. Modeling
[Model Selection] (https://github.com/dinqui/Capstone-3/blob/main/Capstone%203%20-%20Pre-processing%20and%20Model%20.ipynb)

Logistic Regression, Decision Trees, and a Random Forest model were applied to the dataset.

The models were evaluated using a balanced accuracy score since there are significantly more absences that are less than a day than absences that are 1 day or more. Additionally, confusion matrices were plotted. 

## 6. Improvements 
To continue this analysis in the future, I would consider the percentage of absences that are less than a day for each category. If certain categories are only associated with absences less than a day I would consider dropping those instances from the dataframe. 

Furthermore, the dataset did not include the year that the absence was recorded so acquiring timestamped data could help identify trends in absencnes over time. 

## 7. Conclusions & Recommendations 
