# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Data Preparation: Load and explore customer data.
2. Determine Optimal Clusters: Use the Elbow Method to find the best number of clusters.
3. Apply K Means Clustering: Perform clustering on customer data.
4. Visualize Segmented Customers: Plot clustered data to visualize customer segments.

## Program:
```
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Ashqar Ahamed S.T 
RegisterNumber: 212224240018
```
```
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv(r"C:\College\SEM 2\Machine Learning\Exp10\Mall_Customers.csv")

print(data.head())

print(data.info())

data.isnull().sum()

from sklearn.cluster import KMeans
wcss = []

for i in range(1,11):
    kmeans = KMeans(n_clusters = i,init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No of Cluster")
plt.ylabel("wcss")
plt.title("Elbow Method")
plt.figure()

km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])

KMeans(n_clusters=5)

y_pred = km.predict(data.iloc[:,3:])
print("Predicted values: \n",y_pred)

data["cluster"]=y_pred
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
plt.show()
```

## Output:
## Data:
![datasets](https://github.com/user-attachments/assets/db194dcd-0006-4ebf-a8c2-5e8be87fe7e9)
## Data Info:
![datainfo](https://github.com/user-attachments/assets/4d6c844c-4c7f-404b-828b-77d5b3d5519c)
## Predicted Values:
![predicted values](https://github.com/user-attachments/assets/7202d0c9-bfad-4209-bb5c-b2cd7ef619e0)
## Elbow method:
![elbow method](https://github.com/user-attachments/assets/b72dd9cd-f41b-4604-a9db-d4d77bfe6399)
## Customer Segmentation:
![coustomer segments](https://github.com/user-attachments/assets/e7a78f31-d6a8-44fc-b54c-b509d2a5b62e)



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
