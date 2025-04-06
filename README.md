# CryptoClustering

## Project Overview

The **CryptoClustering** project uses unsupervised machine learning techniques—specifically K-means clustering and Principal Component Analysis (PCA)—to analyze and group cryptocurrencies based on their 24-hour and 7-day price change percentages. 

The primary objective is to determine whether these short-term price changes affect how cryptocurrencies cluster together, and how dimensionality reduction via PCA influences those groupings.

---

## Project Goals

- Normalize cryptocurrency market data for consistent analysis.
- Identify the optimal number of clusters (k) using the elbow method.
- Apply K-means clustering to group cryptocurrencies based on price change metrics.
- Use PCA to reduce feature dimensionality and assess its impact on clustering.
- Visualize clustering results with interactive hvPlot charts.
- Compare clustering outcomes before and after PCA transformation.

---

## Key Analyses and Steps

### 1. Data Loading and Exploration
- Loaded `crypto_market_data.csv` into a Pandas DataFrame.
- Generated summary statistics and visualized data distributions.

### 2. Data Preprocessing
- Normalized data using `StandardScaler()` from scikit-learn.
- Created a new DataFrame indexed by `coin_id` with scaled features.

### 3. Finding Optimal Clusters (Elbow Method)
- Iterated through k-values from 1 to 11.
- Computed inertia for each k.
- Plotted an elbow curve to determine the best k.

### 4. K-means Clustering (Scaled Data)
- Trained K-means on scaled data using the optimal k.
- Predicted clusters and visualized them using `hvPlot`:
  - `x = price_change_percentage_24h`
  - `y = price_change_percentage_7d`
  - Colored by cluster label, with `coin_id` as hover info.

### 5. Dimensionality Reduction with PCA
- Applied PCA to reduce the dataset to 3 principal components.
- Calculated explained variance to evaluate feature retention.
- Created a PCA-transformed DataFrame indexed by `coin_id`.

### 6. Elbow Method on PCA Data
- Repeated elbow method on PCA-transformed data.
- Compared k-values from PCA vs. original scaled data.

### 7. K-means Clustering (PCA Data)
- Trained K-means on PCA data using new optimal k.
- Visualized clusters using `hvPlot`:
  - `x = PC1`
  - `y = PC2`
  - Colored by cluster label, with `coin_id` as hover info.

### 8. Composite Visual Comparisons
- Used `+` operator in `hvPlot` to:
  - Compare elbow curves (original vs PCA).
  - Compare clustering plots (original vs PCA).
- Discussed the impact of feature reduction on clustering outcomes.

---

## Tools and Libraries

- Python  
- Pandas  
- Scikit-learn (`StandardScaler`, `KMeans`, `PCA`)  
- hvPlot  
- Jupyter Notebook  

---

## Acknowledgements

Special thanks to Dr. Carl Arrington for guidance during the PCA and K-means clustering implementation. Some snippets and logic were developed following in-class tutorial support and discussions.

