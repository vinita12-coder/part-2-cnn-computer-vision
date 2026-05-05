# Part 2: Computer Vision Problem Formulation and CNN Prototype

## Problem Statement
Given an image dataset of surface conditions, build a CNN to classify images
into 4 categories: dent, normal, scratch, stain.

## Problem Type
Image Classification

## Dataset
- 480 images across 4 classes (120 per class)
- Classes: dent, normal, scratch, stain
- Image size resized to 64x64 pixels
- Train/Test split: 80/20

## Preprocessing
- Resized all images to 64x64
- Normalized pixel values (divide by 255)
- Applied augmentation on training set (rotation, flip, zoom)
- Split into train and test sets

## CNN Architecture
| Layer | Details |
|---|---|
| Conv2D | 32 filters, 3x3, ReLU |
| Conv2D | 32 filters, 3x3, ReLU |
| MaxPooling2D | 2x2 |
| Conv2D | 64 filters, 3x3, ReLU |
| Conv2D | 64 filters, 3x3, ReLU |
| MaxPooling2D | 2x2 |
| Conv2D | 128 filters, 3x3, ReLU |
| MaxPooling2D | 2x2 |
| Flatten | - |
| Dense | 256 neurons, ReLU |
| Dropout | 0.4 |
| Dense | 4 neurons, Softmax |

## CNN Concepts Explained
- **Convolution**: A filter slides over the image to detect patterns like edges and textures
- **Pooling**: Reduces spatial dimensions while keeping important features; reduces computation
- **ReLU**: Removes negative values, keeps positive ones; adds non-linearity and speeds up training
- **Why CNNs over regular networks**: CNNs share weights across spatial locations (parameter efficiency) and automatically learn spatial hierarchies of features

## Business Use Case
Manufacturing quality control — automatically detect surface defects (dents,
scratches, stains) on products before they reach customers, reducing manual
inspection cost and improving defect detection speed.

## Results
- Training and validation accuracy/loss curves saved in results/
- Confusion matrix saved in results/
- Sample predictions saved in sample_predictions/

## Repository Structure
part-2-cnn-computer-vision/
├── README.md
├── notebook.ipynb
├── requirements.txt
├── sample_predictions/
│   └── prediction_outputs.png
└── results/
    ├── sample_class_images.png
    ├── accuracy_loss_curves.png
    └── confusion_matrix.png
