# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1. Import pandas and matplotlib.pyplot

2. Read the dataset and transform it

3. Import KMeans and fit the data in the model

4. Plot the Cluster graph

## Program:


Program to implement the K Means Clustering for Customer Segmentation.

Developed by: CHITTOOR SARAVANA MRUDHULA

RegisterNumber: 21222404056


```
import pandas as pd
import matplotlib.pyplot as plt

data = pd.read_csv(r"C:\Users\admin\Downloads\Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()

from sklearn.cluster import KMeans
wcss = []

for i in range(1,11):
    kmeans = KMeans(n_clusters=i, init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No. of clusters")
plt.ylabel("wcss")
plt.title("Elbow method")

km = KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])

y_pred = km.predict(data.iloc[:,3:])
y_pred

data["cluster"] = y_pred

df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster 0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster 1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster 2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster 3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster 4")

plt.legend()
plt.title("customer segmentation")

```


## Output:

![image](https://github.com/user-attachments/assets/8044e855-be3a-48a3-84b4-8c9543e00ddf)

![image](https://github.com/user-attachments/assets/f809360d-f0dc-4e9d-b2fb-c7522f46dbf8)

![image](https://github.com/user-attachments/assets/03c1f95d-3bf9-4498-89c2-fcf3ee482dce)

![image](https://github.com/user-attachments/assets/53475da6-4c75-412c-aa5b-b06a76f6a813)

![image](https://github.com/user-attachments/assets/0ee1f67a-94e9-4d22-94e6-d5c9433bd2c3)

![image](https://github.com/user-attachments/assets/235874ce-fcc5-44e3-9190-e2b1c9651b79)

![image](https://github.com/user-attachments/assets/1340812d-94b1-476d-83d3-d263249578fb)



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
