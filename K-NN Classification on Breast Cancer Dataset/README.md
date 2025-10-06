🎯 Classification – K-Nearest Neighbors (KNN) – Breast Cancer Dataset

This repository demonstrates a complete workflow of **K-Nearest Neighbors (K-NN)** classification using the **Breast Cancer Wisconsin dataset**.  
It includes data analysis, K-NN model building, dimensionality reduction with PCA, and visualization of decision boundaries.

📂 Contents

**Data Analysis & Visualization**
- Class distribution plot (Malignant vs Benign)
- Boxplots to detect outliers
- Feature correlation heatmap

**K-NN Classification**
- Train/test split and feature scaling
- Cross-validation to select the best `k`
- Classification **before PCA**
  - Accuracy, confusion matrix, classification report

**Dimensionality Reduction with PCA**
- Explained variance vs number of components
- 2D PCA projection for visualization
- Classification **after PCA**
  - Accuracy, confusion matrix, classification report
- Decision boundary visualization (Benign vs Malignant)

**Project Insights**
- Comparison of K-NN performance before and after PCA
- Visualization of class separation in PCA space
- PCA helps reduce dimensionality but may slightly reduce accuracy
- Full-dimensional K-NN provides higher accuracy, while PCA provides interpretability and visualization

⚙️ Usage: 
Run the notebook in Jupyter or Google Colab:

```bash
jupyter notebook K-NN_Classification_on_Breast_Cancer_Dataset.ipynb

