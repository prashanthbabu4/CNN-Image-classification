# CNN-Based Actor Image Classification

# Project Overview
This project uses a Convolutional Neural Network (CNN) to classify an uploaded image into one of three actor classes: AJITH, SURIYA, or VIJAY. The model predicts the most likely class and displays its confidence score.

# Objective
Build an image-classification model that learns visual features from actor images and classifies new images into the three predefined classes.

# Dataset Structure
The dataset is organized into TRAIN, VAL, and TEST folders. Each contains one folder per actor.

dataset/
    TRAIN/
        AJITH/
        SURIYA/
        VIJAY/
    VAL/
        AJITH/
        SURIYA/
        VIJAY/
    TEST/
        AJITH/
        SURIYA/
        VIJAY/


TRAIN: Used to train the CNN model.
VAL: Used to monitor model performance during training.
TEST: Used for final evaluation on separate images.
