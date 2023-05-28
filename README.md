# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
```
1.Import pandas as pd and matplotlib.pyplot as plt
2.Get the info and also obtain the sum of any null values
3.Importing KMeans from sklearn.cluster we group the similar datas
4.Grouping similar datas gives us a elbow shaped graph which is called the Elbow method. 5.Print the number of clusters obtained
5.Giving the clustered data differnet colors and presenting as a scatter plot
6.Print the obtained graph.
```
## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Kavinesh M
RegisterNumber: 212222230064
*/
import pandas as pd
import matplotlib.pyplot as plt
data =pd.read_csv("/content/Mall_Customers (1).csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss=[]
for i in range(1,11):
  kmeans = KMeans(n_clusters = i,init = "k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km = KMeans(n_clusters = 5)
print("K-Means")
km.fit(data.iloc[:,3:])

y_pred = km.predict(data.iloc[:,3:])
print("Array:")
y_pred

data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="yellow",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="pink",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="purple",label="cluster4")
print("Customer Segments")
print("Customer Segement")
plt.legend()
plt.title("Customer Segments")

```

## Output:
### 1. data.head() function
![head](https://github.com/kavinesh8476/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118466561/81e5908b-fd3d-4c23-9a8c-6546824d070b)

### 2. data.info()
![info](https://github.com/kavinesh8476/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118466561/4e1a6076-5199-48b8-8d4f-a222582b3b1c)

### 3. data.isnull().sum() function
![null](https://github.com/kavinesh8476/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118466561/2e318acf-d890-4aa4-b55f-11ee24f0ced2)

### 4. Elbow method Graph
![4](https://github.com/kavinesh8476/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118466561/90cbc786-fc8b-4326-b804-6f5a349856f5)

### 5. KMeans clusters
![5](https://github.com/kavinesh8476/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118466561/1cac479a-4885-47b3-b87d-c9d7c1c28333)

### 6. Customer segments Graph

![7](https://github.com/kavinesh8476/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/118466561/e4960074-56f9-462d-bb75-2985c98eca90)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
