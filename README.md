# Customer Segmentation Analysis

This project focuses on performing customer segmentation using clustering algorithms, specifically KMeans and DBSCAN, to identify distinct customer groups based on their spending habits and income. The analysis aims to provide actionable insights for businesses to tailor marketing strategies and improve customer engagement.

## Table of Contents

- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Methodology](#methodology)
  - [1.0 Exploratory Data Analysis (EDA)](#10-exploratory-data-analysis-eda)
  - [1.1 Data Preprocessing](#11-data-preprocessing)
  - [2.0 KMeans Clustering](#20-kmeans-clustering)
  - [3.0 DBSCAN Clustering](#30-dbscan-clustering)
- [Clustering Comparison: KMeans vs DBSCAN](#clustering-comparison-kmeans-vs-dbscan)
- [Conclusion](#conclusion)
- [Technologies Used](#technologies-used)

## Project Overview

Customer segmentation is a crucial technique for businesses to understand their customer base better. By dividing customers into groups with similar characteristics, businesses can develop more effective and personalized marketing campaigns. This project applies machine learning clustering techniques to achieve this goal using a dataset containing customer information.

## Dataset

The analysis uses the `Mall_Customers.csv` dataset. It contains the following columns:
- `CustomerID`
- `Gender`
- `Age`
- `Annual Income (k$)`
- `Spending Score (1-100)`

The dataset has 200 entries with no missing values.

## Methodology

### 1.0 Exploratory Data Analysis (EDA)

Initial data exploration involved:
- Checking the information and descriptive statistics of the dataset.
- Analyzing the distribution of `Gender` (112 Female, 88 Male).

### 1.1 Data Preprocessing

- **Label Encoding**: The 'Gender' column was transformed into numerical format (`Male`: 0, `Female`: 1).
- **Feature Selection**: 'Age', 'Annual Income (k$)', and 'Spending Score (1-100)' were selected as features for clustering.
- **Feature Scaling**: `StandardScaler` was applied to normalize the selected features to ensure that no single feature dominates the clustering process due to its scale.

### 2.0 KMeans Clustering

KMeans clustering was applied to segment customers.
- **Optimal K Selection**: The Elbow Method was used to determine the optimal number of clusters (k). The plot of inertia against the number of clusters indicated an optimal `k` value (though the specific value isn't explicitly stated in the provided snippet, the method is mentioned).
- The notebook visualizes the KMeans clusters in 3D plots, highlighting customer groups based on 'Age', 'Annual Income', and 'Spending Score'. For example, one cluster represents high-income, high-spending customers, while another represents low-income, low-spending customers.

### 3.0 DBSCAN Clustering

DBSCAN (Density-Based Spatial Clustering of Applications with Noise) was also applied for comparison.
- DBSCAN identifies clusters based on density and can discover arbitrarily shaped clusters as well as noise points.
- The notebook visualizes the DBSCAN clusters in 3D, showing identified clusters and noise points.

## Clustering Comparison: KMeans vs DBSCAN

After applying both KMeans and DBSCAN, **KMeans provided better clustering results** for this customer segmentation data due to the following reasons:
- **Clear, well-separated clusters**: KMeans formed distinct, interpretable customer groups aligning with expected business segments (e.g., high income & low spenders).
- **No noise issues**: DBSCAN marked a significant number of points as noise (`-1`), which could discard valuable customer data.
- **Balanced cluster sizes**: KMeans produced more evenly distributed clusters, making the analysis of each group more reliable.
- **Better visual alignment**: KMeans clusters formed more consistent and interpretable regions across the income-spending space in scatter plots.

**DBSCAN Limitations Observed**:
- **Highly sensitive to `eps` parameter**: Small changes in `eps` caused large shifts in results.
- **Struggles with varying density**: Customer data did not naturally form high-density blobs, leading DBSCAN to misclassify or fragment meaningful clusters.
- **Too many noise points**: Valuable data was ignored, reducing cluster coverage.

## Conclusion

**KMeans is more suitable** for this dataset because customer behavior aligns better with well-separated, spherical clusters, which KMeans captures effectively. The identified customer segments can be used for targeted marketing strategies. For instance, businesses can create personalized campaigns for high-income, high-spending customers or develop strategies to convert low-spending but high-income individuals into more engaged customers.

## Technologies Used

- Python
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn (StandardScaler, KMeans)
  
##  Contact

Marwan Ahmed  
 marwanhassen999@gmail.com  
 [LinkedIn](https://www.linkedin.com/in/marwan0/)
