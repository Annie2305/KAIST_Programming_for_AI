# FashionMNIST Classification with ResNet (AI504 Project 1)

This repository contains my implementation of a **ResNet-based CNN model** for the **FashionMNIST** classification task, as part of **KAIST AI504: Programming for AI (Fall 2025)**.

---

## Project Overview

The objective of this project was to design, train, and evaluate a **CNN** on the FashionMNIST dataset, achieving at least **92.43% validation accuracy**.

I implemented a **ResNet-style architecture completely from scratch** using PyTorch — without relying on any pretrained model or built-in ResNet class.  
The model successfully **outperformed the baseline**, reaching **93.21% validation accuracy** 🎯.

---

## Model Architecture

### 🔹 BasicBlock
Each block contains:
- Two 3×3 convolution layers  
- Batch Normalization after each  
- ReLU activation  
- Skip connection with optional 1×1 conv (for downsampling)

### 🔹 Custom Small ResNet
| Layer | Output Channels | Stride | #Blocks |
|--------|------------------|---------|----------|
| Conv1  | 32 | 1 | - |
| Layer1 | 32 | 1 | 2 |
| Layer2 | 64 | 2 | 2 |
| Layer3 | 128 | 2 | 2 |
| AvgPool + FC | - | - | - |

---

## Training Configuration

| Setting | Value |
|----------|--------|
| Optimizer | AdamW |
| Learning Rate | 3e-4 |
| Weight Decay | 1e-4 |
| LR Scheduler | CosineAnnealingLR (T_max=40) |
| Loss Function | CrossEntropyLoss (label_smoothing=0.1) |
| Epochs | 40 |
| Batch Size | 128 |
| Data Augmentation | RandomCrop(28,2), RandomHorizontalFlip(0.5), RandomRotation(10°) |
| Normalization | Mean = 0.5, Std = 0.5 |

---

## 📊 Results

| Metric | Value |
|---------|--------|
| **Best Validation Accuracy** | **93.21%** ✅ |
| **Baseline Accuracy** | 92.43% |
| **Improvement** | **+0.78%** |
| Test Logits Shape | (10000, 10) |
| Saved Logits | `logits.npy` |

