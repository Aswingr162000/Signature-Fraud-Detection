# Signature Verification using Siamese Neural Network

This is a Flask web application that utilizes a pre-trained Siamese neural network model (`sign.h5`) to verify the authenticity of two signature images. Users can upload two images, and the model will determine whether the signatures are real or fake based on the similarity score.

## Table of Contents
- [Project Overview](#project-overview)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Model Description](#model-description)
- [Screenshots](#screenshots)
- [License](#license)

## Project Overview
This project aims to detect forged signatures by comparing two images using a custom Siamese neural network built with TensorFlow/Keras. The Flask web application provides a simple interface where users can upload two signatures for comparison.

The core idea is to utilize the learned embeddings from a Siamese network to measure the similarity between the two input images. A score is then generated that determines whether the signatures match (genuine) or do not match (forged).

## Features
- Upload two signature images via the web interface.
- The model computes a similarity score to determine if the signatures are real or fake.
- Results are displayed to the user along with the uploaded images.
- Simple, easy-to-use web interface built with Flask.
  
## Installation

### Prerequisites
Ensure that you have the following installed:
- Python 3.x
- Flask
- TensorFlow/Keras
- NumPy
- Pillow
- OpenCV (optional)

### Clone the repository
```bash
git clone https://github.com/yourusername/signature-verification-siamese.git
cd signature-verification-siamese

Install dependencies
It's recommended to create a virtual environment before installing dependencies:

python -m venv venv
source venv/bin/activate   # On Windows: venv\Scripts\activate

Install the required Python packages:

pip install -r requirements.txt

Download the Pre-trained Model
You need to have the pre-trained model file (sign.h5). Place it in the root directory of the project. You can train your model using the code provided in this repository or download a pre-trained version (make sure it's compatible with the code).

Usage
Run the Application
Start the Flask web server by running:

python app.py
Open your web browser and navigate to http://127.0.0.1:5000/. You should see the application interface where you can upload two signature images for verification.

Verify Signatures
Go to the "Verify Signatures" page.
Upload two signature images.
Click on the Verify button.
The result will be displayed, indicating whether the signatures are real or fake, along with the images that were uploaded.
Model Description
The model is a Siamese neural network built using TensorFlow/Keras. It consists of convolutional layers followed by max pooling and fully connected layers. The network is trained to compute the similarity between two images by calculating the Manhattan distance between their learned embeddings.

Model Architecture:
Input: Two images of size (112, 112, 3)
Layers:
Convolutional layers with ReLU activation and max pooling.
Dropout layers for regularization.
Flatten and dense layers for embedding the input images.
Output: Sigmoid output layer giving a similarity score between 0 and 1.
Training Data
The model was trained on a dataset of real and forged signatures. You can find the code for training in this repository, including data augmentation and preprocessing steps.
