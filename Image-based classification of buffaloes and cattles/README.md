# 🐄🦬 Cattle vs Buffalo Image Classification using ResNet50

This project demonstrates how to classify images of **Cattle** and **Water Buffalo** using Transfer Learning with a pretrained ResNet50 model. It covers automated dataset collection, data cleaning, augmentation, model training, and evaluation into one complete deep learning workflow.

## 📘 Project Overview

The goal of this project is to:
- Collect and clean a custom image dataset using web scraping
- Apply data augmentation to improve model generalization
- Build an image classifier using fine-tuned **ResNet50**
- Evaluate the model using per-class accuracy and confusion matrix
- Predict the class of new unseen images

## 🧠 Key Concepts Covered

- Automated Image Scraping with `icrawler`
- Data Cleaning & Validation
- Image Augmentation (Flip, Rotation, Color Jitter, etc.)
- Transfer Learning with ResNet50
- Fine-tuning with Differential Learning Rates
- Model Evaluation (Per-class Accuracy, Confusion Matrix)
- Visualization of Training Curves

## 🧩 Steps in the Project

**1️⃣ Dataset Collection**
- Downloaded images per class from Bing using targeted keywords
- Keywords for Cattle: `gir cow india`, `sahiwal cow`, `dairy cattle farm`, etc.
- Keywords for Buffalo: `murrah buffalo india`, `nili ravi buffalo`, etc.

**2️⃣ Data Cleaning**
- Verified each image can be opened with PIL
- Removed corrupt files and images smaller than 50×50 pixels

**3️⃣ Data Augmentation**
- Applied Random Crop, Horizontal Flip, Rotation (±30°), Color Jitter, Random Perspective, and Random Erasing to training images
- Validation images use only Resize + Normalize (no augmentation)

**4️⃣ Model Building**
- Used pretrained **ResNet50** as the backbone
- Froze all layers except `layer4` and replaced the final FC layer with a custom head:
  `Linear(2048→256) → ReLU → Dropout(0.3) → Linear(256→2)`

**5️⃣ Training**
- Optimizer: Adam with differential LRs (`layer4`: 1e-4, head: 1e-3)
- Scheduler: ReduceLROnPlateau (patience=3)
- Loss: CrossEntropyLoss | Epochs: 25 | Batch Size: 32

**6️⃣ Evaluation**
- Computed per-class and overall accuracy on the validation set
- Plotted confusion matrix and training loss / validation accuracy curves

**7️⃣ Prediction**
- Loaded the best saved model and predicted on individual images with confidence scores

## 📊 Visualizations

- Sample images from both classes
- Augmentation examples (same image, multiple transforms)
- Training Loss curve
- Validation Accuracy curve
- Actual vs Predicted image grid
- Confusion Matrix

## 🧮 Results Summary

| Class       | Accuracy |
|-------------|----------|
| Cattle      | ~90%     |
| Buffalo     | ~90%     |
| **Overall** | **~90%** |


## ⚙️ Usage

Run the notebook in Google Colab:

```bash
pip install icrawler torch torchvision pillow matplotlib
```

```python
# Predict on a new image
label, confidence = predict_image('your_image.jpg')
print(f"Prediction: {label} ({confidence:.1f}%)")
```

> 💡 A GPU runtime is recommended. In Colab: `Runtime → Change runtime type → GPU`
