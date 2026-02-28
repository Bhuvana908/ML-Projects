# 🫁 Lung Cancer Classification using VGG16 & ResNet50

This project demonstrates how to classify **lung cancer histopathological images** into 3 categories using Transfer Learning with both **TensorFlow (VGG16)** and **PyTorch (ResNet50)**. Both models are trained and compared on the same dataset to find the better performer.

## 📘 Project Overview

The goal of this project is to:
- Load and split the **LC25000 Lung & Colon Cancer** dataset
- Apply data augmentation for better generalization
- Build and train two models:
  1. **TensorFlow VGG16** (Keras API)
  2. **PyTorch ResNet50**
- Evaluate both using accuracy, classification report, and confusion matrix
- Compare results and declare the better model

## 🧠 Key Concepts Covered

- Medical Image Classification
- Transfer Learning (VGG16 & ResNet50)
- Data Augmentation (TensorFlow & PyTorch)
- Model Evaluation (Accuracy, Precision, Recall, F1-Score)
- Confusion Matrix & Classification Report
- Side-by-side Model Comparison

## 🧩 Steps in the Project

**1️⃣ Dataset Setup**
- Downloaded the LC25000 dataset from Kaggle using Kaggle API
- Extracted and explored lung image classes: `lung_aca`, `lung_n`, `lung_scc`
- Split dataset into Train / Val / Test using `split-folders` (70 / 15 / 15)
- Removed non-lung classes (colon) from all splits

**2️⃣ Dataset Visualization**
- Displayed sample images from all 3 lung cancer classes

**3️⃣ TensorFlow — VGG16**
- Used pretrained VGG16 (frozen) + custom head: `GAP → Dense(256) → BN → Dropout → Softmax`
- Augmentation: Rotation, Zoom, Flip, Shear, Shift
- Callbacks: EarlyStopping, ReduceLROnPlateau, ModelCheckpoint
- Optimizer: Adam (lr=1e-4) | Loss: Categorical Crossentropy | Epochs: 20

**4️⃣ PyTorch — ResNet50**
- Used pretrained ResNet50 (frozen) + custom head: `Linear(2048→256) → ReLU → Dropout → Linear(256→3)`
- Augmentation: Horizontal Flip, Rotation, Color Jitter
- Scheduler: ReduceLROnPlateau | Optimizer: Adam (lr=1e-4) | Epochs: 20

**5️⃣ Evaluation**
- Computed test accuracy, classification report, and confusion matrix for both models
- Plotted training and validation accuracy/loss curves for each model

**6️⃣ Model Comparison**
- Side-by-side confusion matrices
- Final accuracy comparison to determine the winning model

## 📊 Visualizations

- Sample histopathological images from all 3 classes
- TensorFlow VGG16 — Accuracy & Loss curves
- PyTorch ResNet50 — Accuracy & Loss curves
- Confusion matrices for both models (side-by-side)

## 🏷️ Classes

| Label      | Description                        |
|------------|------------------------------------|
| `lung_aca` | Lung Adenocarcinoma                |
| `lung_n`   | Lung Benign Tissue (Normal)        |
| `lung_scc` | Lung Squamous Cell Carcinoma       |

## 🧮 Results Summary

| Model                  | Test Accuracy |
|------------------------|---------------|
| TensorFlow VGG16       | ~96%          |
| PyTorch ResNet50       | ~96%          |


## ⚙️ Usage

Run the notebook in Google Colab with GPU enabled:

```python
# Load TensorFlow model
tf_model = tf.keras.models.load_model('tf_lung_vgg16.h5')

# Load PyTorch model
pt_model = torch_models.resnet50(pretrained=False)
pt_model.fc = nn.Sequential(nn.Linear(2048, 256), nn.ReLU(), nn.Dropout(0.5), nn.Linear(256, 3))
pt_model.load_state_dict(torch.load('pt_lung_resnet50.pth'))
pt_model.eval()
```

> 💡 GPU runtime is recommended. In Colab: `Runtime → Change runtime type → GPU`

## 📦 Dataset

**LC25000 — Lung and Colon Cancer Histopathological Images**
Available on Kaggle: [andrewmvd/lung-and-colon-cancer-histopathological-images](https://www.kaggle.com/datasets/andrewmvd/lung-and-colon-cancer-histopathological-images)
