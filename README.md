# CIFAR-10 Image Classification using WideResNet (93.6% Accuracy)

This project trains a WideResNet-22-6 model on the CIFAR-10 dataset using PyTorch and FastAI.  
Several experiments were conducted to study the impact of hyperparameters and training techniques on model performance.

## Experiments

The following experiments were conducted:

- Learning rate comparison
- Weight decay tuning
- Gradient clipping analysis
- Data augmentation comparison
- Random initialization effects

## Best Result

Validation Accuracy: **93.4%**

Model: WideResNet-22-6

## Techniques Used

- Data normalization
- Random crop augmentation
- Horizontal flipping
- Residual connections
- Batch normalization
- Learning rate scheduling (1-cycle)
- Weight decay regularization
- Gradient clipping

## Dataset

CIFAR-10  
60,000 images across 10 classes.

## Frameworks

- PyTorch
- FastAI

| Experiment | Accuracy |
|------------|----------|
| No augmentation | 89.0% |
| RandomCrop + Flip | 93.6% |
| Gradient clip 0.5 | 93.6% |
