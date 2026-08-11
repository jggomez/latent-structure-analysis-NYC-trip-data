## Latent Structure Analysis of NYC Trip Data

### **Project Overview**
This repository contains a comprehensive data science project focused on identifying latent structures within New York City taxi trip data. By applying multiple dimensionality reduction and factor analysis techniques (PCA, Sparse PCA, Kernel PCA, ICA, and EFA), we decompose complex urban mobility data into interpretable and actionable business segments.

### **Methodologies**
To extract the most meaningful insights, the following techniques were compared:
- **Standard PCA:** For basic dimensionality reduction.
- **Sparse PCA:** Used to obtain clean, interpretable factors by eliminating statistical noise.
- **Kernel PCA (RBF):** Applied to capture non-linear relationships such as traffic congestion.
- **Independent Component Analysis (ICA):** Used to isolate independent signals (like premium airport trips).
- **Exploratory Factor Analysis (EFA):** Used to validate latent constructs.
- **Clustering (K-Means & GMM):** To evaluate how well these projections segment the data.

### **Repository Sections**
1. **Data Acquisition:** Automatic downloading and merging of NYC Parquet datasets.
2. **Preprocessing:** Memory-efficient sampling, cleaning, and standardization.
3. **Linear & Sparse Reduction:** Comparative analysis of PCA vs. Sparse PCA.
4. **Non-Linear Manifold Learning:** Capturing non-linear traffic topology via Kernel PCA.
5. **Source Separation:** Using ICA to detect niche trip segments.
6. **Cluster Evaluation:** Validating segments using K-Means, GMM, and Silhouette scores.

### **Key Results**
- **Interpretability:** Sparse PCA successfully isolated three constructs: **Trip Physics**, **Regulatory Burden**, and **Infrastructure Logistics**.
- **Redundancy:** EFA revealed that time, distance, and base fare are highly collinear and represent a single 'Magnitude' dimension.
- **Topology:** Kernel PCA demonstrated that urban trip dynamics are non-linear, following a curved 'crescent' manifold rather than a straight line.
- **Segmentation:** ICA was superior at isolating 'Premium' segments (airport trips and tolls).

### **Conclusion & Proposed Hybrid Architecture**
We recommend a hybrid model approach for production environments:
- **Structural Model (Explainability):** Use **Sparse PCA** for reporting and business logic.
- **Predictive Model (Accuracy):** Use **Kernel PCA** components as features for high-precision regressions.
- **Segmentation Model (Strategy):** Use **ICA + K-Means** to identify niche customer groups.
