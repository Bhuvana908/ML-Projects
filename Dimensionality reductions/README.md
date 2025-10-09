# Dimensionality Reduction & Visualization Projects 🧠📊

This notebook demonstrates the application of **linear and nonlinear dimensionality reduction techniques** on different datasets to visualize and interpret high-dimensional data.  

---

## 1️⃣ ISOMAP for Face Data Visualization 🖼️🔍
- **Dataset:** Labeled Faces in the Wild (LFW), fetching individuals with ≥200 images.  
- **Steps:**  
  1. Flatten images into vectors (`X = faces.data`) and retain original images for visualization.  
  2. Display sample faces to understand the dataset.  
  3. Apply **ISOMAP** to reduce 4096-dimensional face vectors to 2D (`n_neighbors=5`, `n_components=2`).  
  4. Visualize 2D projections as scatter plots and overlay **face thumbnails** to interpret clusters.  
- **Insights:** Faces with similar orientation, lighting, or expression cluster together.  
- **Purpose:** Demonstrates nonlinear dimensionality reduction and interpretable visualization of high-dimensional image data.

---

## 2️⃣ PCA on Iris Dataset 🌸📊
- **Dataset:** Iris dataset from `sklearn.datasets`.  
- **Steps:**  
  1. Standardize features using `StandardScaler`.  
  2. Apply **PCA** to reduce dimensionality.  
  3. Plot cumulative explained variance and reduce data to 2 principal components for visualization.  
  4. Scatter plot points colored by species to observe separability and clustering.  
- **Insights:** Principal components capture most of the variance while reducing dimensions to 2D.  
- **Purpose:** Demonstrates **linear dimensionality reduction**, feature extraction, and visualization.

---

## 3️⃣ t-SNE on Digits Dataset 🔢📊
- **Dataset:** Digits dataset from `sklearn.datasets` (8x8 images flattened to 64 features).  
- **Steps:**  
  1. Standardize features using `StandardScaler`.  
  2. Apply **t-SNE** (`n_components=2`, `perplexity=30`, `learning_rate=200`, `random_state=42`).  
  3. Visualize 2D embeddings using scatter plots colored by digit labels.  
  4. Inspect the transformed data to observe clusters.  
- **Insights:** High-dimensional digit images form distinct clusters in 2D space.  
- **Purpose:** Demonstrates **nonlinear dimensionality reduction** for interpretable visualization of complex datasets.

---

### Key Learning Outcomes
✅ Understand and apply **linear (PCA) and nonlinear (ISOMAP, t-SNE) dimensionality reduction techniques**.  
✅ Visualize high-dimensional datasets in **2D space** for analysis and interpretation.  
✅ Use dimensionality reduction to detect **clusters, patterns, and separability** in data.  
✅ Gain experience with **image and tabular datasets**, making them ready for further **machine learning tasks**.  

