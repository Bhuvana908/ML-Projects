🎯 Regression – Temperature Prediction – Weather Dataset

This repository demonstrates a complete workflow of **Temperature Prediction** using historical weather data.  
It includes data analysis, feature selection, Linear Regression model building, gradient descent implementation, and visualization of results.

📂 Contents

**Data Analysis & Visualization**
- Data cleaning and preprocessing
- Handling missing values and duplicates
- Feature extraction from dates (year, month, day)
- Correlation heatmap to identify influential features
- Scatter plots of features vs target (Temperature)

**Linear Regression Models**
- Manual implementation of **Gradient Descent**
  - Feature scaling
  - Training loop with MSE calculation
- **Sklearn Linear Regression**
  - Model fitting
  - Parameter comparison with gradient descent
- Train/test split and evaluation
  - Mean Squared Error (MSE)
  - R² Score
- Comparison of predictions (train and test sets)

**Visualization**
- MSE vs Epochs for Gradient Descent vs Sklearn LR
- Actual vs Predicted Temperature scatter plots
- Feature vs Target scatter plots
- Gradient Descent convergence visualization

**Prediction for New Data**
- Input new weather features
- Predict temperature using both Gradient Descent and Sklearn Linear Regression

📈 Project Insights
- Both Gradient Descent and Sklearn LR provide similar performance
- Feature scaling improves Gradient Descent convergence
- Visualizations help understand feature relationships and model performance
- Manual Gradient Descent helps understand underlying mechanics of Linear Regression

⚙️ Usage: 
Run the notebook in Jupyter or Google Colab:

```bash
jupyter notebook K-NN_Classification_on_Breast_Cancer_Dataset.ipynb



