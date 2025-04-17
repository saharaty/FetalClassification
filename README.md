# Fetal Ultrasound Plane Classification with EfficientNet

This project was developed as part of my master's studies to explore how deep learning can support clinical workflows in prenatal care. It focuses on classifying fetal ultrasound images into anatomical plane types using EfficientNet, a lightweight and accurate neural network architecture.

---

## Project Goal

The aim was to build a deep learning model capable of identifying the following fetal ultrasound planes:

- Fetal Brain
- Fetal Abdomen
- Fetal Femur
- Fetal Thorax
- Maternal Cervix
- Other

This classification task is relevant for automating parts of the diagnostic process, supporting clinicians, and improving the reproducibility of ultrasound image interpretation.

---

## Methods and Tools

- Architecture: EfficientNet-B0 (transfer learning)
- Framework: PyTorch
- Data augmentation: Random horizontal flips and rotations
- Normalization: Mean = 0.5, Std = 0.5
- Training configuration:
  - Frozen base network
  - Only the classification head was trained
  - Loss: CrossEntropyLoss
  - Optimizer: Adam (learning rate = 0.0003)
  - Epochs: 10
  - Batch size: 64

---

## Results

- Training Accuracy: ~99%
- Validation Accuracy: ~98.5%
- Test Accuracy: ~98.6%

Grad-CAM was used to visualize what regions of the ultrasound images the model used to make its decisions. The results confirmed that the model was focusing on anatomically relevant areas. The confusion matrix revealed very strong per-class performance, with some confusion in the “Other” category, which contains ambiguous cases.

---

## Why This Matters

This project demonstrates how computer vision models can be applied to support clinical workflows in fetal imaging. Interpretability and class-wise performance were emphasized to ensure that the model’s predictions could be trusted in a sensitive domain like medical imaging.

---

## Folder Structure

final_dataset_classification/ ├── fetal-classification.ipynb # Main training and evaluation notebook 
├── final_dataset/ # Preprocessed images (train/val/test subfolders)
│ ├── train/
│ │ └── [class folders] # Fetal brain, abdomen, etc. 
│ ├── val/ 
│ │ └── [class folders] 
│ └── test/ 
│ └── [class folders] 

