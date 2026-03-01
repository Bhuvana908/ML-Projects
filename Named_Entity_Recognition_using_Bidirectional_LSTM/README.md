# 🏷️ Named Entity Recognition (NER) using BiLSTM

This project demonstrates how to identify and classify named entities in text using a **Bidirectional LSTM (BiLSTM)** model built with TensorFlow/Keras. It covers data preprocessing, sequence modeling, training, evaluation, and real-time entity prediction into one complete NLP workflow.

## 📘 Project Overview

The goal of this project is to:
- Load and preprocess the `ner_dataset.csv` for sequence labeling
- Build a **BiLSTM** model with Embedding and TimeDistributed layers
- Train the model to identify named entities in sentences
- Evaluate performance using F1-Score, Precision, and Recall
- Predict entities on new unseen sentences

## 🧠 Key Concepts Covered

- Named Entity Recognition (NER)
- Sequence Labeling with Padding & Encoding
- Word Embeddings
- Bidirectional LSTM Architecture
- Token-level Classification
- Evaluation with `seqeval` metrics

## 🧩 Steps in the Project

**1️⃣ Data Loading & Exploration**
- Loaded `ner_dataset.csv` and handled missing values using forward fill
- Explored unique words, tags, and tag distribution
- Visualized NER tag distribution using a count plot

**2️⃣ Data Preprocessing**
- Built `word2idx` and `tag2idx` mappings
- Grouped tokens into sentences using `SentenceGetter`
- Padded sequences to `MAX_LEN = 50`
- One-hot encoded tags using `to_categorical`

**3️⃣ Model Architecture**
```
Input → Embedding(64) → Dropout(0.1) → BiLSTM(100) → TimeDistributed Dense(softmax)
```
- Optimizer: Adam | Loss: Categorical Crossentropy | Epochs: 5 | Batch Size: 64

**4️⃣ Training**
- Trained with 80/20 train-test split and 10% validation split
- Plotted training and validation accuracy and loss curves

**5️⃣ Evaluation**
- Predicted entity tags on the test set
- Computed Precision, Recall, and F1-Score using `seqeval`
- Reported per-entity performance

**6️⃣ Prediction**
- Built a `predict_entities()` function to tag any new input sentence
- Example: `"Barack Obama visited Paris in June 2023"`

## 📊 Visualizations

- NER Tag Distribution (Count Plot)
- Training & Validation Accuracy curve
- Training & Validation Loss curve

## 🏷️ Entity Types

| Tag   | Description               |
|-------|---------------------------|
| `geo` | Geographical Location     |
| `gpe` | Geopolitical Entity       |
| `per` | Person                    |
| `org` | Organization              |
| `tim` | Time Expression           |
| `art` | Artifact                  |
| `eve` | Event                     |
| `nat` | Natural Phenomenon        |
| `O`   | Non-entity (Outside)      |

## 🧮 Results Summary

| Entity | Precision | Recall | F1-Score |
|--------|-----------|--------|----------|
| geo    | 0.82%      | 0.89%   | 0.85     |
| gpe    | 0.97%      | 0.93%   | 0.94     |
| tim    | 0.86%      | 0.84%   | 0.85     |
| per    | 0.74%      | 0.74%   | 0.74%     |
| **Weighted Avg** | | | **0.81** |

> Rare tags like `art`, `nat`, and `eve` scored low due to class imbalance (fewer than 100 samples). Future improvements: collect more data for rare entities or use a pretrained model like BERT.

## ⚙️ Usage

```python
predict_entities("Barack Obama visited Paris in June 2023")

# Output:
# Word                 Tag
# ------------------------------
# Barack               B-per
# Obama                I-per
# visited              O
# Paris                B-geo
# ...
```

Run the notebook in Google Colab:

```bash
pip install seqeval sklearn-crfsuite
```

> 💡 GPU runtime is recommended. In Colab: `Runtime → Change runtime type → GPU`
