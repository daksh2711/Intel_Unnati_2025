# Image Sharpening using Knowledge Distillation

This project focuses on enhancing blurry images using a lightweight student model trained via knowledge distillation from a powerful pretrained Restormer teacher model. The training is performed on image patches, with evaluation metrics such as SSIM used to assess performance.

---

## Demo

Watch the 4-minute project walkthrough:  
[Click here to view the demo video](https://drive.google.com/drive/folders/1TvC6bARB-yZrr0SRdaJr7Olm5aveK2UZ?usp=sharing)

---

## Report

You can read the full technical report here:  
[Intel_Unnati_Report_Daksh.pdf](https://github.com/daksh2711/Intel_Unnati_2025/blob/main/Intel_Unnati_Report_Daksh.pdf)

---

## Project Overview

### Objective
- Develop an efficient image sharpening pipeline using knowledge distillation.
- Train a small, fast student model to replicate the performance of a large teacher model.

### Dataset
- Custom patch-based dataset of blurry and sharp image pairs.

---

## Model Architectures

### Teacher Model: Restormer
- Pretrained Restormer for motion deblurring
- Architecture: Transformer-based, multi-stage, high-capacity
- Not trained from scratch — only used for knowledge supervision

### Student Model: Lightweight CNN
- Custom model inspired by SimpleNAFNet
- Includes:
  - Grouped Channel Attention
  - Gated Feedforward Networks
- Trained using:
  - Ground truth MSE loss
  - Distillation loss from teacher output

---

## Evaluation

- Metric: Structural Similarity Index (SSIM)
- Visualization: Side-by-side comparison of blurry input, student output, and ground truth

---

## How to Run

```bash
# Clone the repo
git clone https://github.com/daksh2711/Intel_Unnati_2025.git
cd Intel_Unnati_2025

# Install requirements
pip install -r requirements.txt

# Train student model
python train_student.py

# Evaluate
python evaluate.py
