# CIFAR-10 WideResNet Experiments

This document summarizes the experimental results obtained when training a WideResNet model on the CIFAR-10 dataset.

---

# Dataset

CIFAR-10  
60,000 images  
10 classes  
32×32 resolution

---

# Model

WideResNet-22-6 implemented in PyTorch.

Training techniques used:

- Batch Normalization
- Residual Connections
- Data Augmentation
- Weight Decay
- Gradient Clipping
- One-Cycle Learning Rate Policy

---

# Experiments

## 1. Data Augmentation

| Setup | Validation Accuracy |
|------|------|
| No augmentation | 89.0% |
| RandomCrop + HorizontalFlip | **93.6%** |

Conclusion:

Data augmentation improved generalization significantly and increased accuracy by **~4.6%**.

---

## 2. Gradient Clipping

| Gradient Clip | Accuracy |
|------|------|
| None | 90.8% |
| 0.1 | 90.8% |
| 0.05 | 93.55% |
| **0.5** | **93.61%** |

Conclusion:

Moderate gradient clipping improves training stability and final accuracy.

---

## 3. Weight Decay

| Weight Decay | Accuracy |
|------|------|
| 0 | 93.2% |
| 1e-5 | 93.2% |
| 1e-4 | 93.1% |
| 5e-4 | 93.4% |
| **1e-3** | **93.6%** |

Conclusion:

Weight decay helps prevent overfitting and slightly improves performance.

---

# Best Model Configuration

Learning Rate: 5e-3  
Weight Decay: 1e-3  
Gradient Clipping: 0.5  
Data Augmentation: RandomCrop + HorizontalFlip

Final Validation Accuracy:

**93.6%**

---

# Observations

- Data augmentation provided the largest performance improvement.
- Gradient clipping improved optimization stability.
- Random initialization causes small variations between runs.
- WideResNet performs significantly better than simple CNN models on CIFAR-10.

---

# Final Result

Best Validation Accuracy Achieved:

**93.6%**

Training Time:

~22 minutes for 10 epochs on GPU.
