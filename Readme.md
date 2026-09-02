# Customer Segmentation using K-Means Clustering

## Overview
This project applies **unsupervised machine learning** to segment customers based on their purchasing behavior. Using the **RFM (Recency, Frequency, Monetary)** framework and **K-Means clustering**, we group 4,339 customers into distinct segments to support targeted marketing and business strategy.

---

## Dataset
- **Source:** Online Retail Dataset
- **Records:** 4,339 unique customers
- **Key Columns:** `CustomerID`, `Recency`, `Frequency`, `Monetary`

| Column      | Description                                      |
|-------------|--------------------------------------------------|
| CustomerID  | Unique identifier for each customer              |
| Recency     | Days since the customer's last purchase          |
| Frequency   | Total number of transactions made                |
| Monetary    | Total amount of money spent                      |

---

## Project Pipeline

### 1. Data Preprocessing
- Handled missing values and duplicate records.
- Aggregated transaction-level data to the customer level.
- Computed RFM features for each customer.

### 2. Outlier Treatment
- Clipped `Monetary` and `Frequency` at the **95th percentile** to reduce the influence of extreme values.
- Capped `Recency` at **365 days**.

### 3. Feature Scaling
- Applied `StandardScaler` to normalize features, ensuring K-Means treats all dimensions equally.

### 4. Clustering
- Used the **Elbow Method** to determine the optimal number of clusters.
- Trained a **K-Means** model with **K = 3**.

### 5. Cluster Interpretation
| Cluster | Label              | Description                                        |
|---------|--------------------|----------------------------------------------------|
| 0       | Regular Customer   | Moderate recency, frequency, and monetary values   |
| 1       | Big Spender        | Low recency, high frequency, high monetary value   |
| 2       | At Risk            | High recency, low frequency, low monetary value    |

### 6. Visualization
- Scatter plots (Frequency vs. Monetary) with cluster-colored data points.
- Cluster centers plotted as labeled markers.
- Bar charts showing segment size distribution.

---

## Tech Stack
- **Language:** Python 3.14
- **Libraries:**
  - `pandas` — Data manipulation and analysis
  - `numpy` — Numerical operations
  - `matplotlib` — Data visualization
  - `scikit-learn` — StandardScaler, KMeans

---


