# Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn

## AIM:
To write a program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. 
2. 
3. 
4. 

## Program:
```
/*
Program to implement the Decision Tree Classifier Model for Predicting Employee Churn.
Developed by: THANGAPAZHAM P
RegisterNumber: 212225040469
*/
```

## Program:

```
import pandas as pd
data=pd.read_csv("Employee.csv")
print("data.head():")
data.head()
```

## Output:

<img width="1196" height="186" alt="image" src="https://github.com/user-attachments/assets/07afa4a7-51e8-4f5a-9094-c1f4a92428f2" />

## Program:

```
print("data.info():")
data.info()
```

## Output:

<img width="1120" height="346" alt="image" src="https://github.com/user-attachments/assets/259843cd-0407-494f-bdbf-ca15fd71c57f" />

## Program:

```
print("isnull() and sum():")
data.isnull().sum()
```

## Output:

<img width="1196" height="263" alt="image" src="https://github.com/user-attachments/assets/99201941-1083-4204-a41d-a2aad55f8221" />

## Program:

```
print("data value counts():")
data["left"].value_counts()
```

## Output:

<img width="1217" height="115" alt="image" src="https://github.com/user-attachments/assets/2462b8c6-d43e-4b78-bc4b-28a933ba8426" />

## Program:

```
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
```
```
print("data.head() for Salary:")
data["salary"]=le.fit_transform(data["salary"])
data.head()
```

## Output:

<img width="1215" height="240" alt="image" src="https://github.com/user-attachments/assets/75013537-1d20-4aad-a5d0-84c47a968177" />

## Program:

```
print("x.head():")
x=data[["satisfaction_level","last_evaluation","number_project","average_montly_hours","time_spend_company","Work_accident","promotion_last_5years","salary"]]
x.head()
```

## Output:

<img width="1167" height="218" alt="image" src="https://github.com/user-attachments/assets/97f4c395-36a4-43c8-990a-b8348a9b45a6" />

## Program:

```
y=data["left"]
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=100)
from sklearn.tree import DecisionTreeClassifier
dt=DecisionTreeClassifier(criterion="entropy")
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)
```
```
print("Accuracy value:")
from sklearn import metrics
accuracy=metrics.accuracy_score(y_test,y_pred)
accuracy
```

## Output:

<img width="1172" height="70" alt="image" src="https://github.com/user-attachments/assets/f7e78100-5982-472a-ae92-67edf143ac6b" />

## Program:

```
import pandas as pd

sample = pd.DataFrame([[0.5,0.8,9,260,6,0,1,2]],
columns=[
"satisfaction_level",
"last_evaluation",
"number_project",
"average_montly_hours",
"time_spend_company",
"Work_accident",
"promotion_last_5years",
"salary"
])

prediction = dt.predict(sample)

print(prediction)
```

## Output:

<img width="1132" height="38" alt="image" src="https://github.com/user-attachments/assets/a4962d56-ae68-445f-9f20-00c000d678de" />

## Program:

```
from sklearn.tree import plot_tree
import matplotlib.pyplot as plt

plt.figure(figsize=(8,6))
plot_tree(dt, feature_names=x.columns, class_names=['salary', 'left'], filled=True)
plt.show()
```

## Output:

<img width="1177" height="547" alt="image" src="https://github.com/user-attachments/assets/f3c18e01-5d9f-4498-b324-172fa3024b4f" />

## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
