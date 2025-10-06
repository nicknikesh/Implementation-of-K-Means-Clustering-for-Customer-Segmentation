# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm:
1.Choose the number of clusters 𝑘 and initialize centroids randomly.

2.Assign each customer (data point) to the nearest centroid.

3.Recalculate the centroids as the mean of the points in each cluster.

4.Repeat steps 2–3 until centroids stabilize or maximum iterations are reached.
## Program:
Program to implement the K Means Clustering for Customer Segmentation.

Developed by: NIKESH KUMAR C

RegisterNumber: 212223040132
```
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("Mall_Customers.csv")
print(data.head())
data.isnull().sum()
from sklearn.cluster import KMeans
wcss=[]
for i in range(1,11):
    kmeans = KMeans(n_clusters=i,init="k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
KMeans(n_clusters=5)
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
plt.title("Customer Segments")
```

## Output:

<img width="573" height="632" alt="Screenshot 2025-10-06 114550" src="https://github.com/user-attachments/assets/02fe9a09-efca-4eb4-9bf0-ffc430857e42" />
<img width="514" height="388" alt="Screenshot 2025-10-06 114559" src="https://github.com/user-attachments/assets/43f992b6-e025-40b1-8d71-afcb6de372f3" />

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
