# Implementation of Random Forest Algorithm for Weather Prediction
## AIM:
To write a program to predict daily temperature , PM2.5 pollution level and Energy based on environmental sensor data using Random Forest Algorithm.

## Problem Statement and Dataset
Problem Statement:

To develop a model using the Random Forest Algorithm to predict temperature, PM2.5 level, and energy consumption based on environmental sensor data like humidity, wind speed, and pressure.

Dataset: The dataset contains environmental parameters such as: Humidity Wind Speed Pressure Temperature PM2.5 Energy Format: CSV file (weather_data.csv) Type: Numerical data

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
Step1: Import the necessary packages using import statement. 
Step2: Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head(). 
Step3: Import KMeans and use for loop to cluster the data. 
Step4: Predict the cluster and plot data graphs. Step5: Print the outputs and end the program
## Program:
```
/*
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans
import numpy as np

# Load the correct CSV file
data = pd.read_csv("/content/weather-station-eee-block_2024_07_13.csv")

# Data inspection (keeping these as they were in the original code)
data.head()
data.info()
data.isnull()
data.isnull().sum()

# Prepare data for clustering: select relevant numerical columns and handle missing values
# Using 'tem' and 'hum' for a clear 2D clustering example.
X = data[['tem', 'hum']].dropna() 

wcss = []
for i in range(1, 11):
    kmeans = KMeans(n_clusters=i, init="k-means++", random_state=42, n_init=10)
    kmeans.fit(X)
    wcss.append(kmeans.inertia_)

plt.figure(figsize=(10, 6))
plt.plot(range(1, 11), wcss, marker='o', linestyle='--')
plt.xlabel("No. of clusters")
plt.ylabel("WCSS (Within-Cluster Sum of Squares)")
plt.title("Elbow Method")
plt.grid(True)
plt.show()

# Perform K-Means clustering with 5 clusters (as per original code)
km = KMeans(n_clusters=5, random_state=42, n_init=10)
y_pred = km.fit_predict(X)

# Add the cluster labels to our prepared feature set
X_clustered = X.copy()
X_clustered["cluster"] = y_pred

# Plotting the clusters
plt.figure(figsize=(12, 8))

# Define colors for clusters
colors = ['blue', 'green', 'red', 'cyan', 'magenta', 'yellow', 'black']

# Iterate through each cluster to plot
for i in range(5):
    df_cluster = X_clustered[X_clustered["cluster"] == i]
    plt.scatter(df_cluster["tem"], df_cluster["hum"],
                s=50, c=colors[i % len(colors)], label=f"Cluster {i}")

plt.xlabel("Temperature (tem)")
plt.ylabel("Humidity (hum)")
plt.title("Cluster Segments (Temperature vs Humidity)")
plt.legend()
plt.grid(True)
plt.show()
*/
Developed by: Kavinaya V
RegisterNumber: 212225230133
*/
```

## Output:
<img width="514" height="399" alt="ml101" src="https://github.com/user-attachments/assets/60b2e08a-afca-4036-8004-7633eeda2957" />
<img width="1098" height="674" alt="ml102" src="https://github.com/user-attachments/assets/3805b569-ba1d-4ac9-b103-ae00e14b8c7e" />
<img width="1007" height="710" alt="ml 103" src="https://github.com/user-attachments/assets/bb60e840-c244-4b78-b10f-13cadec2870c" />

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
