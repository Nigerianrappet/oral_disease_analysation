# Oral Disease Classification (DL) and XAI evaluation 

## Project Overview

This project explores the classification of oral diseases from images using a Convolutional Neural Network (CNN) built with PyTorch. The model learns visual features from oral images to classify them into six categories.

The project also integrates Grad-CAM (Gradient-weighted Class Activation Mapping) to visualize image regions that influence the model's predictions, providing a basic interpretability component.

## Objectives

- Develop a CNN model for oral disease image classification.
- Preprocess and augment images for model training.
- Train and evaluate the model using PyTorch.
- Apply Grad-CAM to visualize regions influencing model predictions.

## Dataset

The dataset contains 9,036 images across six classes:

- Calculus
- Gingivitis
- Hypodontia
- Mouth Ulcer
- Tooth Caries
- Tooth Discoloration

Images are resized to 224 × 224 pixels before being passed to the model.

**Note:** The dataset is not included in this repository. You must obtain the dataset separately and organize it into class-specific folders for use with `torchvision.datasets.ImageFolder`.

## Technologies Used

- Python
- PyTorch
- Torchvision
- NumPy
- Matplotlib
- Pillow
- Grad-CAM (`pytorch-grad-cam`)
- Google Colab

## Model Architecture

The project implements a custom CNN consisting of:

- Three convolutional layers
- ReLU activation functions
- Max-pooling layers
- A flattening layer
- A fully connected hidden layer with 128 neurons
- An output layer with six classes

The model uses Cross-Entropy Loss for classification and the Adam optimizer for training.

## Data Preprocessing

The preprocessing pipeline includes:

- Resizing images to 224 × 224 pixels
- Random horizontal flipping
- Random rotation of up to 20 degrees
- Color jitter for brightness, contrast, saturation, and hue
- Tensor conversion
- Normalization using ImageNet mean and standard deviation

The dataset is divided into training and testing subsets using an 80:20 split.

## Training

The model was configured with the following parameters:

| Parameter | Value |
|---|---|
| Framework | PyTorch |
| Input image size | 224 × 224 |
| Batch size | 32 |
| Optimizer | Adam |
| Learning rate | 0.001 |
| Loss function | Cross-Entropy Loss |
| Configured epochs | 100 |
| Number of classes | 6 |

Training was performed in Google Colab, with model checkpoints saved to Google Drive.

This result indicates that the model requires further optimization and evaluation before it can be considered reliable. Potential improvements include reviewing the training pipeline, using separate transformations for training and testing, evaluating class-wise performance, and experimenting with transfer learning.

## Model Interpretability with Grad-CAM

Grad-CAM is used to generate a heatmap highlighting image regions that influence the model's output for a selected class.

This helps visualize the model's attention and investigate whether its predictions rely on relevant image features.

Grad-CAM visualizations are exploratory and do not establish clinical validity or explain a diagnosis conclusively.

## Project Structure

```text
oral_disease_analysation/
├── README.md
└── oral_disease_analysis.ipynb
### nb
This project is for educational and research purposes only. It is not intended for clinical diagnosis or medical decision-making.
