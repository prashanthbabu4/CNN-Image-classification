# CNN-Based Actor Image Classification

# Project Overview
This project uses a Convolutional Neural Network (CNN) to classify an uploaded image into one of three actor classes: AJITH, SURIYA, or VIJAY. The model predicts the most likely class and displays its confidence score.

# Objective
Build an image-classification model that learns visual features from actor images and classifies new images into the three predefined classes.

# Dataset Structure
The dataset is organized into TRAIN, VAL, and TEST folders. Each contains one folder per actor.

## Dataset Structure

The dataset is organized into TRAIN, VAL, and TEST folders. Each folder contains images of three actors.

```text
dataset/
├── TRAIN/
│   ├── AJITH/
│   ├── SURIYA/
│   └── VIJAY/
├── VAL/
│   ├── AJITH/
│   ├── SURIYA/
│   └── VIJAY/
└── TEST/
    ├── AJITH/
    ├── SURIYA/
    └── VIJAY/
```


TRAIN: Used to train the CNN model.

VAL: Used to monitor model performance during training.

TEST: Used for final evaluation on separate images.

# Image Preprocessing
Images are resized to 128 × 128 pixels. Pixel values are normalized from 0--255 to 0--1 using rescale=1./255

Training images are modified using rotation, zoom, shear, and flipping to improve model learning. Validation and test images are only resized, without any modifications.

# Dataset Loading and Class Labels
Keras loads images from folders and assigns three class labels. The same class order is used for predictions.

# CNN Model Architecture
The model is built using the Keras Sequential API.
  Layer                               Purpose
  Input                               Receives a 128 × 128 RGB image

  Conv2D (32 filters)                 Learns basic image features

  MaxPooling2D                        Reduces feature-map dimensions

  Conv2D (64 filters)                 Learns more detailed features

  MaxPooling2D                        Reduces feature-map dimensions

  Conv2D (128 filters)                Learns higher-level visual features

  MaxPooling2D                        Reduces feature-map dimensions

  Flatten                             Converts feature maps into a
                                      one-dimensional vector

  Dense (128 units)                   Learns patterns for classification

  Dropout (0.5)                       Helps reduce overfitting

  Dense (3 units, softmax)            Produces probabilities for the three actor classes


# Model Compilation

The model is compiled with: - Optimizer: Adam - Loss: Categorical crossentropy - Metric: Accuracy

model.compile() configures how the model learns. It does not train the model or display accuracy by itself.

# Model Training

The model is trained using model.fit() for 20 epochs.
- Training accuracy checks performance on training images.
- Validation accuracy checks performance on validation images.
- Loss helps identify overfitting.

# Model Evaluation
Model.evaluate(test_data) checks the model's test accuracy and loss using unseen images.

# Image Prediction
Users can upload an image from their computer. The image is resized to 128 × 128 and given to the model for prediction.
The model predicts the actor's name and confidence score.

# Training Observation
In the final training epoch:
- Training accuracy: 85.19%
- Validation accuracy: 33.33%
- Training loss: 0.3003
- Validation loss: 8.4497
These results show overfitting. The model performs well on training images but poorly on validation images.

# Conclusion
This project uses CNN for image classification. It includes image preprocessing, augmentation, model training, evaluation, and image prediction.
Further improvements are needed to reduce overfitting and improve model accuracy.





















