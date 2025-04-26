# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Load Data – Import the dataset containing employee details and their salaries.

2.Preprocess Data – Handle missing values, encode categorical variables, and split into training and test sets.

3.Initialize Model – Create a DecisionTreeRegressor with suitable parameters (e.g., max_depth=5).

4.Train Model – Fit the regressor using training data (model.fit(X_train, y_train)).

5.Predict & Evaluate – Predict salaries on test data and evaluate using metrics like MAE, MSE, and R² score.

6.Visualize & Interpret – Plot the tree and analyze feature importance for salary prediction.

## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: THIRISHA A
RegisterNumber: 212223040228
*/
```
```
import pandas as pd
data=pd.read_csv("/content/Salary.csv")
data.head()
```
![437671248-a91cbd50-878d-4869-9360-f7b00819b1c8](https://github.com/user-attachments/assets/730f3206-4671-41dd-a589-a1410f13a9af)

```
data.info()
data.isnull().sum()
```

![437671285-281e7ec3-584f-40bb-8215-8e4646df1027](https://github.com/user-attachments/assets/934beecd-03af-4577-a591-0b626d024c45)
```
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()
```
![437671334-8148d002-33b7-4994-934f-15dcc8b0aa70](https://github.com/user-attachments/assets/6bf78daa-9035-4834-a80e-cec25f7906f9)

```
x=data[["Position","Level"]]
x.head()
y=data["Salary"]
y.head()
```
![437671416-5856fcef-ad80-46f9-8e98-c6ba1d21dc78](https://github.com/user-attachments/assets/ef5b6271-a073-42a5-8ddf-3e7565148ed3)
```
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=2)

from sklearn.tree import DecisionTreeRegressor
dt=DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)
y_pred
```

![437671457-30da3297-2d2b-4cee-a66c-650410f83760](https://github.com/user-attachments/assets/36ad8cc4-ec32-4fcf-bb07-c07a1ed5192b)

```
from sklearn import metrics
from sklearn.metrics import r2_score
r2 = r2_score (y_test, y_pred)
r2
```
![437671494-4d6330ee-5f16-4f34-913d-2ba6aa1baa37](https://github.com/user-attachments/assets/1dd26c61-e1c2-4d82-8b80-7567af926dd4)

```
dt.predict([[5,6]])
```
![437671525-149318a3-f414-497b-a66b-8d2c86b04da2](https://github.com/user-attachments/assets/da8614df-b04d-4b7d-bfaa-1ceec79b07b2)



## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
