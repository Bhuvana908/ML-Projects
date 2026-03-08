# BrightEN — Low-Light Image Enhancement using GANs

> A deep learning system that enhances dark, low-light images using a GAN-based architecture built from scratch in PyTorch, trained on Google Colab.

---

## What It Does

Takes a dark or underexposed image as input and generates a bright, clear, enhanced version using a trained Generative Adversarial Network.

| Input | Output |
|---|---|
| Dark, low-light image | Bright, enhanced image |
| Poor visibility scene | Clear, usable output |

---

## Model Architecture

| Component | Architecture |
|---|---|
| Generator | U-Net (Encoder-Decoder with skip connections) |
| Discriminator | PatchGAN (70x70 patch classification) |
| Loss | Adversarial Loss + L1 Loss (λ=100) |
| Framework | PyTorch |

---

## Results

| Metric | Score |
|---|---|
| PSNR (Best) | 20.54 dB |
| SSIM (Best) | 0.7856 |
| Dataset | LOL (Low-Light) Dataset |
| Training Images | 485 |
| Validation Images | 15 |

---

## Tech Stack

- Python
- PyTorch
- scikit-image
- Matplotlib
- Google Colab (T4 GPU)

---

## Project Structure

```
BrightEN/
├── BrightEN.ipynb          # Main training notebook (Google Colab)
└── README.md
```

---

## How to Run

### Requirements
- Google Colab account (T4 GPU recommended)
- Kaggle account (for dataset download)

### Step 1 — Open Notebook in Colab
Upload `BrightEN.ipynb` to Google Colab and set runtime to T4 GPU:
`Runtime → Change Runtime Type → T4 GPU`

### Step 2 — Install Dependencies
```bash
pip install torch torchvision opencv-python scikit-image matplotlib
```

### Step 3 — Download Dataset
```bash
pip install kaggle
kaggle datasets download -d soumikrakshit/lol-dataset
unzip lol-dataset.zip -d data/
```

### Step 4 — Run All Cells
Run cells in order. Training runs for 100 epochs and saves:
- Checkpoints every 10 epochs → `checkpoints/`
- Sample comparison images every 10 epochs → `results/`

### Step 5 — Enhance a Single Image
The last cell in the notebook loads the trained model and enhances a single low-light image, displaying the original vs enhanced comparison.

---

## Dataset

**LOL Dataset** — Low-Light paired image dataset
- 485 training image pairs (low/high light)
- 15 validation image pairs
- Download: https://www.kaggle.com/datasets/soumikrakshit/lol-dataset

---

## How It Works

```
Dark Image
    │
    ▼
U-Net Generator ──► Enhanced Image
    │                      │
    └──► PatchGAN ◄────────┘
         Discriminator
         (Real or Fake?)
              │
              ▼
         Generator improves
         until output looks real
```

1. Generator takes dark image and produces enhanced version
2. Discriminator checks if enhanced image looks real
3. Both compete — generator keeps improving
4. After 100 epochs — generator produces realistic bright images
   
---

## Author

**Kadasani Bhuvana Reddy**
B.Tech CSE, CR Rao AIMSCS
[GitHub](https://github.com/Bhuvana908) | [LinkedIn](http://linkedin.com/in/bhuvana-reddy-907a68339)
