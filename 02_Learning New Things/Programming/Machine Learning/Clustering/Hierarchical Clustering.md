#machine-learning #algorithms #clustering #unsupervised

> [!abstract] Overview
> **Hierarchical [[Clustering]]** is an unsupervised learning technique that builds a nested tree of clusters. Unlike K-Means, it does **not** require specifying the number of clusters ($K$) upfront.

---

# 🌳 Types of Hierarchical Clustering

### 1. Agglomerative (Bottom-Up) — *Most Common*
Starts with every data point as its own individual cluster, then iteratively merges the closest pairs of clusters until a single cluster remains.

### 2. Divisive (Top-Down)
Starts with all data points in one single cluster, then recursively splits the clusters until every point is in its own cluster.

---

## 🔗 Agglomerative Clustering (Deep Dive)

### What It Is
A **bottom-up** approach that forms clusters by sequentially combining smaller clusters into larger ones based on distance.

### ⚙️ How It Works (Step-by-Step)
1. **Initialize:** Treat each of the $n$ data points as a single-point cluster.
2. **Distance Matrix:** Compute a proximity matrix containing distances between all pairs of clusters.
3. **Merge:** Find the two closest clusters and merge them into a single cluster.
4. **Update Matrix:** Recalculate distances between the new cluster and all remaining clusters using a **linkage criterion**.
5. **Repeat:** Repeat Steps 3 & 4 until only one top-level cluster remains.

### 📏 Linkage Criteria (Measuring Cluster Distance)

> [!info] How to measure distance between two multi-point clusters $A$ and $B$:
> - **Single Linkage:** Minimum distance between any point in $A$ and any point in $B$ (prone to "chaining").
> - **Complete Linkage:** Maximum distance between any point in $A$ and any point in $B$ (creates compact, spherical clusters).
> - **Average Linkage:** Average distance between all pairs of points across $A$ and $B$.
> - **Ward’s Linkage:** Minimizes the variance within merged clusters (most popular default).

---

# 📊 Dendrograms

> [!abstract] What Is a Dendrogram?
> A tree-like diagram that records and displays the sequence of merges or splits performed during hierarchical clustering.

### Key Components & Properties
- **Leaves (Bottom):** Individual data points.
- **Branches:** Merges between clusters.
- **Vertical Height:** Represents the **distance/dissimilarity** at which two clusters were merged. (Higher branch = larger distance between merged clusters).

## ✂️ How We Use Dendrograms

1. **Determine the Number of Clusters ($K$):**
   - Identify the longest vertical line that is **not intersected** by any horizontal merge line.
   - Draw a horizontal "cut line" across it.
   - The **number of vertical lines crossed** by the cut line equals the optimal $K$.

2. **Understand Data Relationships:**
   - Shows similarity between data points at a glance (points connected at lower heights are more similar).

## Within Cluster Variance
The dendrograms are based on this metric. It measures how spread out the data points are around the centroid of their assigned cluster. 
# ⚡ Pros & Cons

> [!success] Strengths
> - No need to pre-specify the number of clusters ($K$).
> - Dendrograms provide an intuitive visual representation of data hierarchy.
> - Deterministic result (same initial conditions always yield the same tree).

> [!warning] Limitations
> - High computational complexity: $\mathcal{O}(n^3)$ space/time without optimization ($\mathcal{O}(n^2)$ space).
> - Does not scale well to large datasets.
> - Merges/splits are irreversible (once two points are merged, they cannot be separated).


