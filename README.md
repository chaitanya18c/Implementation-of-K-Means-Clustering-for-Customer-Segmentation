# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import pandas and matplotlib.pyplot.
2. Read the dataset and transform it.
3. Import KMeans and fit the data in the model.
4. Plot the Cluster graph.

## Program:
``` python
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: CHAITANYA P S
RegisterNumber:  212222230024
import pandas as pd                      
import matplotlib.pyplot as plt          
data = pd.read_csv("CSVs/Mall_Customers.csv")
data.head()
data.info() 
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = [] #Within-Cluster Sum of Square.
#It is the sum of squared distance between each point & the centroid in a cluster. 
for i in range(1,11):
    kmeans = KMeans(n_clusters = i,init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_) 
plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
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
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="clusterl")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```
## Output:
#### df.head():
<img src = "https://github.com/Adhithyaram29D/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119393540/f2909d05-c913-481a-a23d-558da6b79065" width="300">

#### df.info():
<img src = "https://github.com/Adhithyaram29D/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119393540/8fe1d138-d646-4d66-be76-b8e8c11eeb6c" width="300">

#### df.isnull().sum():
<img src = "https://github.com/Adhithyaram29D/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119393540/e164792e-7697-4ba6-8e92-da0816e7c552" width="200">

#### Elbow Method Graph:
<img src = "https://github.com/Adhithyaram29D/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119393540/92bc7baa-51e4-48c3-b5f9-fbbdc7efd87a" width="400">

#### K-Means Cluster:
<img src = "https://github.com/Adhithyaram29D/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119393540/be2281e8-31e1-4f7f-a6d4-553b99d65e9e" width="400">

#### Customer Segments Graph:
<img src = "https://github.com/Adhithyaram29D/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/119393540/2aa40179-e2c5-49e9-aa9f-ff9018dd5cff" width="300">

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
