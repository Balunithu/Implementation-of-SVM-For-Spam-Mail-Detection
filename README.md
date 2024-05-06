# Develop By : NITHYA SHREE B
# Reg No : 212223220071
# Implementation-of-SVM-For-Spam-Mail-Detection

## AIM:
To write a program to implement the SVM For Spam Mail Detection.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm:

1.Import the necessary packages using import statement.

2.Read the given csv file and print the number of contents to be displayed. 

3.Split the dataset using train_test_split. 

4.Calculate Y_Pred and accuracy. 

5.Display the result.


## Program:
```
import pandas as pd
data=pd.read_csv("spam.csv",encoding='latin-1')
data.head()
data.info()
data.isnull().sum()
x=data["EmailText"].values
y=data["Label"].values
from sklearn.model_selection import train_test_split 
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=0)
from sklearn.feature_extraction.text import CountVectorizer
cv=CountVectorizer()
x_train=cv.fit_transform(x_train)
x_test=cv.transform(x_test)
from sklearn.svm import SVC
svc=SVC()
svc.fit(x_train,y_train)
y_pred=svc.predict(x_test)
y_pred
from sklearn import metrics
accuracy=metrics.accuracy_score(y_test,y_pred)
accuracy
````
## Output:
## Data.head():
![Screenshot 2024-05-06 094352](https://github.com/Balunithu/Implementation-of-SVM-For-Spam-Mail-Detection/assets/161273477/ceb41cdc-5b9d-42e6-b15f-5564516ef9ad)

## Data.info():
![Screenshot 2024-05-06 094858](https://github.com/Balunithu/Implementation-of-SVM-For-Spam-Mail-Detection/assets/161273477/a99b8169-b8df-4239-b9f2-aabf7b581f8d)

## Accuracy:
![Screenshot 2024-05-06 094903](https://github.com/Balunithu/Implementation-of-SVM-For-Spam-Mail-Detection/assets/161273477/7bf07db5-d6ab-4a2f-a43d-2750cfd7beab)

## Result:
Thus the program to implement the SVM For Spam Mail Detection is written and verified using python programming.
