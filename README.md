# Implementation-of-K-Means-Clustering-for-Customer-Segmentation
### Name: Tarun S
### Reference No: 212223040226

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
Hardware – PCs
Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1. Import pandas and matplotlib.pyplot.
2. Read the dataset and transform it.
3. Import KMeans and fit the data in the model.
4. Plot the Cluster graph.

## Program:
```
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Tarun S
RegisterNumber: 212223040226
```
```
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []  #Within-Cluster sum of square. 
for i in range(1,11):
  kmeans=KMeans(n_clusters = i,init = "k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])
y_pred = km.predict(data.iloc[:,3:])
y_pred
data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```
## Output:

### data.head() 
![image](https://github.com/Tarun-2006/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145584190/7a3100ef-72df-4058-98f8-0196d37b4132)

### data.info()
![image](https://github.com/Tarun-2006/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145584190/36664f3d-2d3d-4dfa-b3b4-8c12341716df)

### data.isnull().sum() 
![image](https://github.com/Tarun-2006/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145584190/fa52eb9e-3b41-4c61-8a74-5e7dd47121e0)

### Elbow method Graph
![image](https://github.com/Tarun-2006/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145584190/827c6a8c-2922-457f-9bf3-470fe8ef1060)

### KMeans clusters
![image](https://github.com/Tarun-2006/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145584190/4ce5159a-ad5f-4860-911d-59fb1a411811)
![image](https://github.com/Tarun-2006/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145584190/23fcf9cd-87ac-4641-9158-e042d8f94c1f)

### Customer segments Graph
![image](https://github.com/Tarun-2006/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145584190/ea7cc8fa-2ec7-4bf3-8b7e-328be0297a92)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
