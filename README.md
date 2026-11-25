# Customer Segmentation Using Clustering

## Project Overview

This project explores unsupervised machine learning techniques for customer segmentation. The goal is to identify groups of customers based on demographic and behavioral characteristics, particularly age, annual income, and spending score.

Three clustering algorithms are implemented and compared: K-Means, DBSCAN, and Hierarchical Clustering.

## Dataset

- **File:** `Customer.csv`
- **Initial records:** 200
- **Features:** 5 columns
- **Missing values:** None

The dataset contains the following features:

- `CustomerID`: Customer identifier
- `Gender`: Customer gender
- `Age`: Customer age
- `Annual Income (k$)`: Annual income in thousands of dollars
- `Spending Score (1-100)`: Spending score

For clustering, the following three numerical features were selected:

- Age
- Annual Income
- Spending Score

`CustomerID` and `Gender` were not included in the clustering features.

## Data Preprocessing

The following steps were performed:

1. Inspected the dataset structure and descriptive statistics.
2. Checked for missing values.
3. Explored the relationship between annual income and spending score.
4. Detected and removed outliers using the Interquartile Range (IQR) method.
5. Selected numerical features for clustering.
6. Standardized the selected features using `StandardScaler`.

After outlier removal, the dataset contained **198 records**.

## Exploratory Data Analysis

Exploratory data analysis included:
- Visualizing the relationship between annual income and spending score.
- Examining the data distribution before and after outlier removal.
- Using boxplots to inspect the cleaned data.

## Clustering Algorithms

### 1. K-Means

- Used the Elbow Method to examine different numbers of clusters.
- Applied K-Means with 4 clusters.
- Visualized the resulting customer segments.

**Silhouette Score:** 0.406

### 2. DBSCAN

- Applied DBSCAN with `eps=0.6` and `min_samples=5`.
- Identified clusters and noise points.
- Excluded noise points (label `-1`) when calculating the Silhouette Score.

**Cluster distribution:**
- Cluster 0: 135 customers
- Cluster 1: 35 customers
- Noise points: 28 customers

**Silhouette Score (excluding noise):** 0.279

### 3. Hierarchical Clustering

- Generated a dendrogram using Ward linkage.
- Applied Agglomerative Clustering with 4 clusters.
- Evaluated the clustering result using the Silhouette Score.

**Silhouette Score:** 0.369

## Model Comparison

| Algorithm | Silhouette Score |
|---|---:|
| K-Means | **0.406** |
| DBSCAN | 0.279 |
| Hierarchical Clustering | 0.369 |

Among the evaluated methods, K-Means achieved the highest Silhouette Score on this dataset and feature configuration.

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- SciPy
- Jupyter Notebook

## Repository Structure

```text
customer-segmentation-clustering/
│
├── clustering.ipynb
├── Customer.csv
└── README.md
```

## How to Run

1. Clone this repository.
2. Install the required Python libraries.
3. Place `Customer.csv` in the same directory as the notebook.
4. Open `clustering.ipynb` using Jupyter Notebook or Google Colab.
5. Run the notebook cells in order.

## Notes

This project is an educational exercise in unsupervised machine learning. The clustering results depend on the selected features, preprocessing steps, and algorithm parameters.
