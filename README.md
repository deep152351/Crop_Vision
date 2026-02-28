# Crop_Vision

📌 Overview

Early detection of plant diseases plays a critical role in improving crop productivity and ensuring food security. This project builds an automated potato leaf disease classification system using Deep Transfer Learning with VGG16, a pre-trained CNN model from ImageNet.

The system classifies potato leaves into:

🍂 Early Blight

🌧️ Late Blight

🌿 Healthy

The model is lightweight, accurate, and suitable for deployment in resource-constrained environments such as agricultural advisory systems.
📂 Dataset

Dataset Name: PlantVillage – Potato Subset
Source: Kaggle
Classes: 3

🔗 Kaggle Dataset:
https://www.kaggle.com/datasets/emmarex/plantdisease
📊 Data Preprocessing

Image resizing → 180 × 180 pixels
Normalization → Pixel scaling to [0, 1]
Data Augmentation:
Rotation (30°)
Shear
Zoom
Width/Height Shift
Horizontal Flip
Data augmentation ensures strong generalization and reduces overfitting.

🧠 Model Architecture

The model leverages VGG16 (Transfer Learning) as a feature extractor.

🔹 Base Model

Pre-trained on ImageNet

include_top=False

All convolutional layers frozen

🔹 Custom Classification Head

Flatten Layer

Dense (256 units, ReLU)

Dropout (0.5)

Dense (3 units, Softmax)

⚙️ Hyperparameters
Parameter	Value
Optimizer	Adam
Learning Rate	0.0001
Loss Function	Sparse Categorical Crossentropy
Batch Size	32
Epochs	15
Input Size	180×180×3

📈 Results

✅ Final Performance (After 15 Epochs)

Metric	Score

Training Accuracy	89.94%

Validation Accuracy	95.67%

Training Loss	0.2721

Validation Loss	0.1596

🔎 Observations

Validation accuracy slightly higher than training accuracy.

This is expected due to strong augmentation, which makes training harder.

Indicates strong generalization capability.

No major overfitting observed.

