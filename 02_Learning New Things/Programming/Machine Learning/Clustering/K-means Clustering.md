#machine-learning #algorithms #clustering #unsupervised #kmeans 

> [!abstract] Overview
> **K-Means** is an unsupervised machine learning [[Clustering]] algorithm that groups unlabeled data into $K$ distinct, non-overlapping clusters based on feature similarity.

---

## ⚙️ Step-by-Step Algorithm

### Phase 1: Initialization
1. **Choose $K$**
   - Select the number of clusters ($K$) to divide the data into.
2. **Initialize Centroids**
   - Select $K$ random points from the dataset as the initial cluster centers (**centroids**).

---

### Phase 2: Optimization Loop
3. **Assign Points (Distance Step)**
   - Calculate the distance from each point to all $K$ centroids.
   - Assign each point to its **nearest centroid**.
4. **Update Centroids (Mean Step)**
   - Recalculate each centroid's location by taking the **mean of all points** assigned to its cluster.

---

### Phase 3: Convergence
5. **Repeat Steps 3 & 4** until:
   - Centroids stop moving.
   - Points no longer switch clusters.
   - Maximum iterations reached.

---
![[Pasted image 20260913175340.png]]

---
## 📐 Key Formulas

### [[Euclidean distance]]
$$d(p, q) = \sqrt{\sum_{i=1}^{n} (q_i - p_i)^2}$$

### Objective Function (Inertia / WCSS)
Goal is to minimize the **Within-Cluster Sum of Squares**:
$$\text{WCSS} = \sum_{k=1}^{K} \sum_{x \in S_k} ||x - \mu_k||^2$$

---

## ⚡ Pros & Cons

> [!success] Strengths
> - Fast and computationally efficient: $\mathcal{O}(n \cdot K \cdot d \cdot i)$
> - Easy to implement and understand
> - Scales well to large datasets

> [!warning] Limitations
> - Sensitive to initial centroid placement (use **K-Means++** to mitigate)
> - Sensitive to outliers
> - Must pre-define $K$ (commonly selected via the **Elbow Method**)

---

## Elbow Method

 #hyperparameters #algorithms 
 
> [!abstract] Purpose
> A heuristic used to determine the optimal number of clusters ($K$) for **K-Means** by finding the point where adding more clusters yields diminishing returns.
## ⚙️ How It Works

1. **Run K-Means** for a range of $K$ values (e.g., $K = 1 \text{ to } 10$).
2. **Calculate WCSS** (Within-Cluster Sum of Squares / Inertia) for each $K$:
   $$\text{WCSS} = \sum_{k=1}^{K} \sum_{x \in S_k} ||x - \mu_k||^2$$
3. **Plot $K$ vs. WCSS** on a line graph.
4. **Locate the "Elbow"**: Pick the value of $K$ where the curve bends sharply and drops off slow down.

![[Pasted image 20260913164211.png|650]]
## ⚡ Quick Notes

> [!tip] Rule of Thumb
> The "elbow" represents the sweet spot balancing **intra-cluster tightness** and **model simplicity**.

> [!warning] Limit
> Not always clear on smooth/gradual curves — use the **Silhouette Score** as an alternative if the elbow isn't distinct.

---
## K-means++

#kmeans #algorithms 

> [!abstract] Purpose
> An enhancement of standard K-Means that improves **initial centroid selection** to avoid poor local minima and speed up convergence.
## ⚙️ How It Works (Smart Initialization)

1. **First Centroid:** Pick 1st centroid $\mu_1$ randomly from the dataset.
2. **Compute Distances:** For each point $x$, compute $D(x)$, the distance to the nearest already-chosen centroid.
3. **Next Centroid:** Choose the next centroid randomly from remaining points with probability proportional to $D(x)^2$:
   $$P(x) = \frac{D(x)^2}{\sum D(x)^2}$$
4. **Repeat:** Repeat steps 2–3 until $K$ centroids are chosen.
5. **Standard K-Means:** Proceed with regular assignment and update steps.
## ⚡ Quick Notes

> [!success] Why Use It?
> - **Guaranteed Bounds:** Prevents bad initial seeds (e.g., centroids placed close together).
> - **Faster Convergence:** Standard K-Means converges in fewer total iterations.

> [!tip] Note
> Default initialization method in `scikit-learn` (`init='k-means++'`).

---
