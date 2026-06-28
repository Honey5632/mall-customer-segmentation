# 🛍️ Mall Customer Segmentation — Machine Learning Project

> Segmenting 200 mall customers into **5 distinct groups** using K-Means Clustering with **Silhouette Score = 0.556**

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.x-blue?style=for-the-badge&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/scikit--learn-latest-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white"/>
  <img src="https://img.shields.io/badge/Unsupervised-Learning-1D9E75?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/K--Means-Clustering-7F77DD?style=for-the-badge"/>
</p>

---

## 📌 Overview

This project applies **unsupervised machine learning** to segment mall customers based on their age, annual income, and spending score. Using K-Means clustering with `k-means++` initialization, the model discovers 5 meaningful customer groups — without any labels or prior knowledge.

The optimal number of clusters (K=5) was validated using both the **Elbow Method** and **Silhouette Score**, and cluster separation was confirmed via **PCA visualization**.

---

## 🎯 The 5 Customer Segments

| Cluster | Age | Income | Spending | Profile |
|---|---|---|---|---|
| 0 | 42.7 | $55.3k | 49.5 | 🟣 Average Joes — middle of everything |
| 1 | 32.7 | $86.5k | 82.1 | 🟢 High Value Targets — dream customers |
| 2 | 25.3 | $25.7k | 79.4 | 🟠 Young Impulsive — low income, high spend |
| 3 | 41.1 | $88.2k | 17.1 | 🟡 Wealthy Savers — rich but barely spend |
| 4 | 45.2 | $26.3k | 20.9 | 🔴 Careful Elders — low income, low spend |

---

## 📊 Dataset

| Property | Value |
|---|---|
| Source | [Mall Customer Segmentation — Kaggle](https://www.kaggle.com/datasets/vjchoudhary7/customer-segmentation-tutorial-in-python) |
| Records | 200 customers |
| Features | CustomerID, Gender, Age, Annual Income, Spending Score |
| Missing values | 0 |
| Type | Unsupervised — no labels |

> 📥 Download `Mall_Customers.csv` from Kaggle and place it in the project root before running.

---

## 🛠️ Tech Stack

```
pandas · numpy · matplotlib · seaborn
scikit-learn (KMeans, StandardScaler, PCA, silhouette_score)
```

---

## ⚙️ Full Pipeline

```
Load Mall_Customers.csv
         │
         ▼
Exploratory Data Analysis (EDA)
  └── Age, income, spending distributions
  └── Gender split bar chart
  └── Pairplot by gender
         │
         ▼
Feature Engineering
  └── Encode gender (Male=0, Female=1)
  └── StandardScaler — normalize features
         │
         ▼
Find Optimal K
  └── Elbow Method (inertia vs K)
  └── Silhouette Score (K=5 peaks at 0.556)
         │
         ▼
Train K-Means (K=5, k-means++ init)
         │
         ▼
Visualize Clusters
  └── 2D scatter plot (income vs spending)
  └── PCA plot — confirm separation in 2D space
  └── Cluster profile heatmap
         │
         ▼
Save customers_with_clusters.csv
```

---

## 📈 Results

| Metric | Value |
|---|---|
| **Optimal K** | **5** |
| **Silhouette Score** | **0.556** |
| **Validation** | Elbow + Silhouette both confirm K=5 |
| **PCA separation** | All 5 clusters cleanly separated |

---

## 📁 Project Structure

```
mall-customer-segmentation/
│
├── Untitled.ipynb                   # Main Jupyter notebook
├── README.md                        # Project documentation
│
├── Mall_Customers.csv               # Dataset (download from Kaggle)
│
└── outputs/
    ├── eda_distributions.png        # Age, income, spending histograms
    ├── eda_gender.png               # Gender distribution bar chart
    ├── eda_pairplot.png             # Pairplot colored by gender
    ├── elbow_silhouette.png         # Elbow + silhouette score plot
    ├── clusters_2d.png              # 2D cluster scatter with centroids
    ├── clusters_pca.png             # PCA space cluster visualization
    ├── cluster_heatmap.png          # Cluster profile heatmap
    └── customers_with_clusters.csv  # Dataset with cluster labels added
```

---

## 🚀 How to Run

**1. Clone the repository**
```bash
git clone https://github.com/Honey5632/mall-customer-segmentation.git
cd mall-customer-segmentation
```

**2. Install dependencies**
```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
```

**3. Add the dataset**
Download `Mall_Customers.csv` from [Kaggle](https://www.kaggle.com/datasets/vjchoudhary7/customer-segmentation-tutorial-in-python) and place it in the project root.

**4. Run the notebook**
```bash
jupyter notebook Untitled.ipynb
```

---

## 💡 Key Insights

**1. Income + Spending tells the whole story**
Just two features — annual income and spending score — are enough to clearly separate 5 distinct customer types. The 2D scatter plot shows clean, well-separated clusters with no overlap.

**2. Silhouette Score confirms K=5 mathematically**
The silhouette score peaked at **0.556** for K=5 — meaning the clusters are well-defined and customers within each group are genuinely similar to each other.

**3. The most valuable segment is small**
Cluster 1 (High Value — young, rich, high spending) is the smallest group but the most profitable target for premium marketing campaigns.

**4. Wealthy Savers are an untapped opportunity**
Cluster 3 earns the most but spends the least. They need exclusive, premium, limited-edition offers to convert — not discounts.

---

## 🔧 Possible Improvements

- [ ] Try DBSCAN for non-spherical cluster shapes
- [ ] Add hierarchical clustering comparison
- [ ] Build an interactive Streamlit dashboard
- [ ] Include more features (visit frequency, product categories)
- [ ] Deploy as a web app for business use

---

## 🙋 Author

**Honey Rana**
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/honey-rana-6748b938a)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Honey5632)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
