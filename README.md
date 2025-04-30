# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1.Import dataset and print head,info of the dataset

2.check for null values

3.Import kmeans and fit it to the dataset

4.Plot the graph using elbow method

5.Print the predicted array

6.Plot the customer segments

## Program:

/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: PRIYADHARSHINI P

RegisterNumber:  212224040252
*/

```python

import pandas as pd

import matplotlib.pyplot as plt

data=pd.read_csv("/content/Mall_Customers (1).csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans

wcss=[]

for i in range(1,11):

kmeans=KMeans(n_clusters=i,init="k-means++")

kmeans.fit(data.iloc[:,3:])

wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)

plt.xlabel("No_of_Clusters")

plt.ylabel("wcss")

plt.title("Elbow Method")

km=KMeans(n_clusters=5)

km.fit(data.iloc[:,3:])

y_pred=km.predict(data.iloc[:,3:])

y_pred

data["cluster"]=y_pred

df0=data[data["cluster"]==0]

df1=data[data["cluster"]==1]

df2=data[data["cluster"]==2]

df3=data[data["cluster"]==3]

df4=data[data["cluster"]==4]

plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")

plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")

plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")

plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")

plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")

plt.legend()

plt.title("Customer Segment")
```



## Output:

## 1.DATA.HEAD():

![image](https://github.com/user-attachments/assets/2eb93e3d-8216-484c-94dd-c360517d23e7)

## 2.DATA.INF0():

![image](https://github.com/user-attachments/assets/13b4226c-0178-4b21-8843-3771d66eb4fc)

## 3.DATA.ISNULL().SUM():
![image](https://github.com/user-attachments/assets/d300f02b-0ecc-4474-907d-0d4865c3793c)

## 4.PLOT USING ELBOW METHOD:
![image](https://github.com/user-attachments/assets/0041eda0-f1d1-4781-8fa8-f9bbec09603f)

## 5.K-MEANS CLUSTERING:
![image](https://github.com/user-attachments/assets/c324ed37-0453-44ac-82df-1eae4ef821f7)


## 6.Y_PRED ARRAY:
![image](https://github.com/user-attachments/assets/98bca287-7ff4-4e62-905f-9e1a562ba0ee)

## 7.CUSTOMER SEGMENT:
![image](https://github.com/user-attachments/assets/a529911a-4913-45b1-9099-f2e4e24e02a6)



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
