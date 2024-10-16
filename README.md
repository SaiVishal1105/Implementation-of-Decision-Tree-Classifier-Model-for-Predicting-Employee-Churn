# Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn

## AIM:
To write a program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import pandas module and import the required data set.
2. Find the null values and count them.
3. Count number of left values.
4. From sklearn import LabelEncoder to convert string values to numerical values.
5. From sklearn.model_selection import train_test_split.
6. Assign the train dataset and test dataset.
7. From sklearn.tree import DecisionTreeClassifier.
8. Use criteria as entropy.
9. From sklearn import metrics.
10. Find the accuracy of our model and predict the require values.

## Program:
```
Program to implement the Decision Tree Classifier Model for Predicting Employee Churn.
Developed by: SAI VISHAL D
RegisterNumber: 212223230180
import pandas as pd
data=pd.read_csv("/content/Employee.csv")
data.head()
```
![image](https://github.com/user-attachments/assets/5425cf68-ea55-44b6-9871-61a8a8b45332)
```
data.info()
```
![image](https://github.com/user-attachments/assets/ee56f76c-4492-4da6-b684-ff7431afd1f2)
```
data.isnull().sum()
```
![image](https://github.com/user-attachments/assets/11e9589c-30ac-4792-9eaf-fd7fac333d5e)
```
data["left"].value_counts()
```
![image](https://github.com/user-attachments/assets/6c44a146-e641-493b-89fd-38291bd6dd59)
```
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["salary"]=le.fit_transform(data["salary"])
data.head()
```
![image](https://github.com/user-attachments/assets/c2c01323-6fd5-445f-968b-ea8fdb43dc73)

```
x=data[["satisfaction_level","last_evaluation","number_project","average_montly_hours","Work_accident","promotion_last_5years","salary"]]
x.head()
```
![image](https://github.com/user-attachments/assets/f3b8278f-22e3-4c5c-bf6c-b2a6285d7667)

```
y=data["left"]
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=1)
from sklearn.tree import DecisionTreeClassifier
dt=DecisionTreeClassifier(criterion="entropy")
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)
from sklearn import metrics
accuracy=metrics.accuracy_score(y_test,y_pred)
accuracy
```
![image](https://github.com/user-attachments/assets/86140f94-3708-4d40-825f-e581396d1bbb)

```
dt.predict([[0.5,0.8,9,260,6,0,1,]])
```
![image](https://github.com/user-attachments/assets/a61a7ff0-7f70-4698-96a0-a44d6cd63c00)

## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
