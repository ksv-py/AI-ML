[1. group by number of people left from each department (done)
2. total people in each department (done)
3. pie chart of Working People And Left People (done)
4. no of people which were getting low salary and left vs medium salary and left (done)
5. satisfaction level >0.20 , > 0.40, > 0.50, <0.50 (done)
6. left Mid vs Low salary vs high in diff department (done)



Learnings :-


Dataframe Categorization == pd.cut(data, bins, labels)
# HR Data Analysis

This project conducts exploratory data analysis (EDA) on a Human Resources dataset to gain insights into employee attrition and factors affecting employee satisfaction. Additionally, it includes the training of a logistic regression model to predict employee turnover based on various features.

## Table of Contents

1. [Introduction](#introduction)
2. [Data Exploration and Visualization](#data-exploration-and-visualization)
3. [Satisfaction Level Categories](#satisfaction-level-categories)
4. [Salary Distribution Across Departments](#salary-distribution-across-departments)
5. [Logistic Regression Model](#logistic-regression-model)
6. [Conclusion](#conclusion)

## Introduction

The code provided in this repository analyzes an HR dataset (`HR_comma_sep.csv`) using Python and popular data science libraries such as Pandas, NumPy, Matplotlib, Seaborn, and Scikit-learn. The primary objectives are to explore the distribution of employees across different departments, understand the factors influencing employee turnover, and train a logistic regression model to predict attrition.

## Data Exploration and Visualization

The initial steps involve loading the HR dataset, checking for missing values, and visualizing the distribution of employees across departments. Various plots, including count plots and pie charts, are utilized to provide a comprehensive overview of the data.

## Satisfaction Level Categories

The code categorizes employee satisfaction levels into different categories based on specified thresholds. A count plot is then used to visualize the distribution of satisfaction categories.

## Salary Distribution Across Departments

The salary distribution across different departments is visualized using a stacked bar plot. This allows for a quick comparison of the number of employees in each salary category within each department.

## Logistic Regression Model

A logistic regression model is trained to predict employee turnover. Features such as satisfaction level, average monthly hours, promotion in the last 5 years, and salary are used to train the model. The trained model is then saved using Pickle for future use.

## Conclusion

This project provides valuable insights into employee-related trends and patterns within the HR dataset. The logistic regression model serves as a predictive tool for identifying potential attrition risks based on specific employee characteristics.

Feel free to explore the code and adapt it to your specific needs. If you have any questions or suggestions, please don't hesitate to reach out.

**Note:** Make sure to replace `HR_comma_sep.csv` with your actual dataset if it has a different name.

stacked plots == stacked = True and colormap ='viridis'

rotating labels == plt.xticks(rotation = '', ha = 'right') 

instead of:
	low_salary = (df.salary == 'low').sum()
	high_salary = (df.salary == 'high').sum()
	mid_salaray = (df.salary == 'medium').sum()

this :
	salary_counts = df\['salary'\].value_counts()


instead of :
	dept_salary_low = df\[df\['salary'\] == 'low'\].groupby('Department')\['salary'\].count()
	dept_salary_mid = df\[df\['salary'\] == 'medium'\].groupby('Department')\['salary'\].count()
	dept_salary_high = df\[df\['salary'\] == 'high'\].groupby('Department')\['salary'\].count()

this :
	df.groupby(\['Department', 'salary'\]).size().unstack()](readme.md)