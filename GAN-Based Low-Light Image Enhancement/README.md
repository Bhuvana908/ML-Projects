# BrightEN — Low-Light Image Enhancement using GANs

> A deep learning system that enhances dark, low-light images using a GAN-based architecture built from scratch in PyTorch.

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
- OpenCV
- scikit-image
- Matplotlib
- Streamlit (web app)
- Google Colab (training)

---

## Project Structure

```
BrightEN/
├── app.py                  # Streamlit web app
├── lol_generator_v1.pth    # Trained model weights
├── checkpoints/            # Epoch-wise saved checkpoints
│   ├── G_epoch_10.pth
│   ├── G_epoch_20.pth
│   └── ...
├── results/                # Sample output images per epoch
│   ├── epoch_010.png
│   ├── epoch_020.png
│   └── ...
└── README.md
```

---

## How to Run

### Training (Google Colab)

**Step 1 — Install dependencies**
```bash
pip install torch torchvision opencv-python scikit-image matplotlib
```

**Step 2 — Download dataset**
```bash
pip install kaggle
kaggle datasets download -d soumikrakshit/lol-dataset
unzip lol-dataset.zip -d data/
```

**Step 3 — Run training**
Copy and run all cells in order. Training runs for 100 epochs on the LOL dataset and saves checkpoints every 10 epochs.

---

### Web App (Streamlit)

**Run locally**
```bash
pip install streamlit torch torchvision pillow
streamlit run app.py
```

**Run on Colab**
```python
!pip install streamlit pyngrok
from pyngrok import ngrok
!streamlit run app.py &
public_url = ngrok.connect(8501)
print("App URL:", public_url)
```

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
