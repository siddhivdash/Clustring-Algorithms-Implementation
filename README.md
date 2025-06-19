# Clustering Algorithms Implementation

This repository contains implementations of key unsupervised learning clustering algorithms using Python and scikit-learn. Clustering is an essential task in machine learning where the goal is to group similar data points without predefined labels.

## 📁 Algorithms Implemented

### 1. K-Means Clustering

**K-Means** is a centroid-based algorithm that partitions the data into `K` clusters by minimizing the within-cluster sum of squares (WCSS).

- **How it works:**
  - Randomly initialize `K` centroids.
  - Assign each point to the nearest centroid.
  - Recalculate centroids based on current assignments.
  - Repeat until convergence.

- **Key Parameters:**
  - `n_clusters`: Number of clusters
  - `init`: Initialization method (e.g., `k-means++`)
  - `max_iter`: Maximum number of iterations

- **Evaluation Used:**
  - **Silhouette Score** to determine how well data points fit within their cluster (higher score = better-defined clusters).
  - **Elbow Method** using WCSS to determine the optimal number of clusters.

---

### 2. Hierarchical Clustering (Agglomerative)

**Hierarchical Clustering** builds a hierarchy of clusters using a bottom-up (agglomerative) approach.

- **How it works:**
  - Each point starts as its own cluster.
  - Pairs of clusters are merged iteratively based on linkage criteria.

- **Linkage Methods Used:**
  - `ward`: Minimizes variance
  - `complete`: Max distance between clusters
  - `average`: Mean distance between clusters

- **Visualization:**
  - Dendrogram to visualize merging steps and choose the optimal cluster count.

- **Evaluation:**
  - **Silhouette Score** to evaluate the quality of clusters.

---

### 3. DBSCAN (Density-Based Spatial Clustering of Applications with Noise)

**DBSCAN** groups together points that are closely packed and marks points that lie alone as outliers.

- **How it works:**
  - Uses two parameters:
    - `eps`: Max distance between two points to be considered neighbors.
    - `min_samples`: Minimum number of points required to form a dense region.
  - Expands clusters from core points.

- **Strengths:**
  - Can detect arbitrarily shaped clusters.
  - Robust to outliers.

- **Evaluation:**
  - **Silhouette Score** (may be lower if many points are marked as noise).
  - Does not require specifying number of clusters.

---


## 📈 Evaluation Metric: Silhouette Score

The **Silhouette Score** is used throughout this project to assess the performance of clustering:

- Ranges from **-1 to 1**
- **+1**: Points are well matched to their own cluster
- **0**: Points are on or near the decision boundary between clusters
- **-1**: Points may be assigned to the wrong cluster

