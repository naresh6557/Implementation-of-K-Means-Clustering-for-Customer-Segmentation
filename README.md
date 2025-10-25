# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Load and preprocess data: Import data, inspect it, and handle missing values if any.
2. Determine optimal clusters: Use the Elbow Method to identify the number of clusters by plotting WCSS against cluster numbers.
3. Fit the K-Means model: Apply K-Means with the chosen number of clusters to the selected features.
4. Assign cluster labels to each data point.
5. Plot data points in a scatter plot, color-coded by cluster assignments for interpretation.
## Program:
```
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
    kmeans = KMeans(n_clusters = i,init = "k-means++",n_init=10)
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km = KMeans(n_clusters=5, n_init=10)
km.fit(data.iloc[:, 3:])
y_pred = km.predict(data.iloc[:,3:])
y_pred

data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster1")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster2")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster3")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster4")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster5")
plt.legend()
plt.title("Customer Segments")
```
```

Program to implement the K Means Clustering for Customer Segmentation.
Developed by: R Naresh kumar
RegisterNumber: 212224040213

```

## Output:
<img width="812" height="246" alt="image" src="https://github.com/user-attachments/assets/76246857-b9e4-43ce-bfa3-c5a287e0ee8c" />

<img width="710" height="290" alt="image" src="https://github.com/user-attachments/assets/9c41e1e9-cf8f-46ea-b5f2-aa7e06725a40" />

<img width="388" height="281" alt="image" src="https://github.com/user-attachments/assets/3107fe44-ed98-4466-b3d3-9482ea62943a" />

<img width="813" height="588" alt="image" src="https://github.com/user-attachments/assets/de683306-c3d4-4e9f-a139-52e37eecc1af" />

<img width="786" height="224" alt="image" src="https://github.com/user-attachments/assets/1af5a655-c0f5-4e3e-bd43-2227e41a934e" />

<img width="954" height="679" alt="image" src="https://github.com/user-attachments/assets/b6472814-1d63-4915-aaa5-d67ac6181c74" />



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
