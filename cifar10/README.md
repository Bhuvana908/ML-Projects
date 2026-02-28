# 🖼️ CIFAR-10 Image Classification using CNN

This project demonstrates how to classify images into **10 different categories** using a custom Convolutional Neural Network (CNN) built with PyTorch. It covers data loading, augmentation, model building, training, and evaluation into one complete deep learning workflow.

## 📘 Project Overview

The goal of this project is to:
- Load and preprocess the **CIFAR-10** dataset
- Apply data augmentation to improve generalization
- Build a custom **CNN** from scratch using PyTorch
- Train the model and track loss and accuracy
- Evaluate per-class performance
- Visualize correct and incorrect predictions

## 🧠 Key Concepts Covered

- Data Loading & Augmentation with `torchvision`
- Custom CNN Architecture with BatchNorm & Dropout
- Model Training with Adam Optimizer & StepLR Scheduler
- Model Evaluation (Per-class Accuracy)
- Prediction Visualization (Green = Correct, Red = Wrong)

## 🧩 Steps in the Project

**1️⃣ Data Loading & Preprocessing**
- Loaded CIFAR-10 dataset (50,000 train / 10,000 test images)
- Applied augmentations to training data: Random Horizontal Flip, Random Crop
- Normalized using CIFAR-10 mean and std for RGB channels

**2️⃣ Dataset Visualization**
- Displayed sample images from all 10 classes with unnormalization for proper color rendering

**3️⃣ CNN Model Architecture**
- Built a 3-block CNN with the following structure:
  - **Block 1:** Conv→BN→ReLU→Conv→BN→ReLU→MaxPool→Dropout (32 filters)
  - **Block 2:** Conv→BN→ReLU→Conv→BN→ReLU→MaxPool→Dropout (64 filters)
  - **Block 3:** Conv→BN→ReLU→MaxPool→Dropout (128 filters)
  - **Classifier:** Linear(2048→512)→ReLU→Dropout→Linear(512→10)

**4️⃣ Training**
- Loss: CrossEntropyLoss | Optimizer: Adam (lr=0.001)
- Scheduler: StepLR (step=10, gamma=0.5) | Epochs: 20 | Batch Size: 64

**5️⃣ Evaluation**
- Computed per-class accuracy across all 10 categories
- Plotted training loss and test accuracy curves

**6️⃣ Prediction Visualization**
- Displayed predictions with green (correct) and red (wrong) labels on test images

## 📊 Visualizations

- Sample CIFAR-10 images from training set
- Training Loss curve
- Test Accuracy curve
- Predicted vs Actual labels on test images

## 🏷️ Classes

`Airplane` · `Car` · `Bird` · `Cat` · `Deer` · `Dog` · `Frog` · `Horse` · `Ship` · `Truck`

## 🧮 Results Summary

| Class    | Accuracy |
|----------|----------|
| Airplane | ~82%     |
| Car      | ~91%     |
| Bird     | ~67%     |
| Cat      | ~66%     |
| Deer     | ~75%     |
| Dog      | ~78%     |
| Frog     | ~94%     |
| Horse    | ~86%     |
| Ship     | ~95%     |
| Truck    | ~94%     |


## ⚙️ Usage

Run the notebook in Google Colab:

```python
# Load saved model
model = CIFAR10_CNN().to(device)
model.load_state_dict(torch.load('cifar10_model.pth'))
model.eval()
```

> 💡 A GPU runtime is recommended. In Colab: `Runtime → Change runtime type → GPU`
