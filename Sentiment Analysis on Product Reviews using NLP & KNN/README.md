# Sentiment Analysis on Product Reviews using NLP & KNN

This project implements an **end-to-end sentiment analysis system** on product reviews using **Natural Language Processing (NLP)** and a **K-Nearest Neighbors (KNN)** classifier. Reviews are classified as **positive or negative** based on textual content extracted from a SQLite database.

---

## 📌 Project Overview

The goal of this project is to analyze customer reviews and automatically determine sentiment by applying text preprocessing, feature engineering, dimensionality reduction, and machine learning techniques.

The pipeline demonstrates how raw text data can be transformed into meaningful numerical representations and used for classification and visualization.

---

## 📂 Dataset

- **Source**: Amazon Fine Food Reviews Dataset
- **Format**: SQLite database (`database.sqlite`)
- **Table Used**: `Reviews`

Due to GitHub file size limitations, the dataset is **not included directly in this repository**.

🔗 **Download the dataset from Google Drive:**  
[https://drive.google.com/drive/folders/1bu3AfChWT5yBwLuSMHg757LchFEccq0m?usp=sharing]

After downloading, place the file below in the **project root directory**:


### Dataset Description
- Ratings < 3 → **Negative sentiment**
- Ratings ≥ 3 → **Positive sentiment**
- Neutral reviews (rating = 3) are excluded to improve classification clarity


---

## ⚙️ Workflow

### 1. Data Extraction & Cleaning
- Loaded review data using SQLite
- Removed neutral reviews and duplicate entries
- Converted ratings into binary sentiment labels

### 2. Text Preprocessing
- HTML tag and punctuation removal
- Lowercasing and stopword removal
- Word stemming using Snowball Stemmer
- Generated cleaned review corpus

### 3. Feature Engineering
- Bag of Words (Unigrams & Bigrams)
- TF-IDF vectorization for word importance
- Extraction of top TF-IDF features
- Word2Vec embedding trained on review corpus
- Averaged Word2Vec vectors for each review

### 4. Dimensionality Reduction
- Applied **Truncated SVD** to reduce TF-IDF features to 2D
- Enabled visual interpretation and faster distance-based learning

### 5. Model Development
- Implemented **K-Nearest Neighbors (KNN)** classifier
- Tuned hyperparameter `k` using GridSearchCV
- Evaluated using accuracy and classification report

### 6. Visualization
- Cross-validation accuracy vs. number of neighbors
- KNN decision boundary visualization in reduced feature space

### 7. Prediction
- Predicted sentiment for custom user-defined reviews

---

## 📊 Results

- Optimized KNN model achieved strong classification performance
- TF-IDF features effectively captured sentiment-bearing words
- Dimensionality reduction enabled clear class separation
- Decision boundary visualization improved model interpretability

---

## 🧰 Tools & Libraries

- **Python**
- **Pandas, NumPy**
- **NLTK**
- **Scikit-learn**
- **Gensim**
- **Matplotlib, Seaborn**
- **SQLite**

---

## 🚀 How to Run

1. Open the notebook in **Jupyter Notebook** or **Google Colab**
2. Upload `database.sqlite` when prompted
3. Run cells sequentially to reproduce results

---

## 📌 Key Learnings

- End-to-end NLP workflow on real-world text data
- Feature extraction using TF-IDF and Word2Vec
- Distance-based classification with KNN
- Importance of dimensionality reduction for visualization
- Hyperparameter tuning using cross-validation

---

## 🔮 Future Improvements

- Compare KNN with Logistic Regression, SVM, and Naive Bayes
- Implement deep learning models (LSTM / Transformers)
- Deploy sentiment classifier as a web application or API
- Perform topic modeling on review data

---

## 👤 Author

**Kadasani Bhuvana Reddy**

If you found this project useful, feel free to ⭐ the repository!

