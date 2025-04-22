# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the libraries and read the data frame using pandas.
2. Calculate the null values present in the dataset and apply label encoder.
3. Determine test and training data set and apply decison tree regression in dataset. 
4. Calculate Mean square error,data prediction and r2.




## Program:

```
Developed by: priyanka.R
RegisterNumber:  212223220081
```
```
import pandas as pd
data=pd.read_csv("Salary.csv")
data.head()
```
## output
![image](https://github.com/user-attachments/assets/37f53c4e-9469-4c8f-8e22-f815e01cd42d)
```
data.info
```
## output
![image](https://github.com/user-attachments/assets/990655b4-c782-4e26-a7f5-e2c289dd8b10)

```
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()
```
## output
![image](https://github.com/user-attachments/assets/65439851-a20e-4042-8be7-b9714e0cda35)
```
x=data[["Position","Level"]]
y=data[["Salary"]]
```
```
from sklearn.model_selection import train_test_split
x_train, x_test, y_train, y_test=train_test_split(x,y,test_size=0.2,random_state=2)
```
```
from sklearn.tree import DecisionTreeRegressor
dt=DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)
```
```
from sklearn import metrics
mse=metrics.mean_squared_error(y_test, y_pred)
mse
```
## output
![image](https://github.com/user-attachments/assets/87b8515b-a48b-429b-9039-e2a0a9b92a66)
```
r2=metrics.r2_score(y_test,y_pred)
r2
```
## output
![image](https://github.com/user-attachments/assets/6fda3205-a009-4265-8d85-4bfa42b42d8d)
```
dt.predict([[5,6]])
```
## output
![image](https://github.com/user-attachments/assets/b0fcec88-c91b-483e-b882-4f0a5d2f0c84)

## Result

Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.




