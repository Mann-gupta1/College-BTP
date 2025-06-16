# Pneumonia Detection using Deep Learning

A web-based application that uses Convolutional Neural Networks (CNN) to detect pneumonia from chest X-ray images.

## Project Overview

This project implements a deep learning model to analyze chest X-ray images and determine whether a patient has pneumonia. The system uses a trained CNN model to make predictions and provides a user-friendly web interface for medical professionals to upload and analyze X-ray images.

## Features

- Upload chest X-ray images through a web interface
- Real-time image processing and prediction
- Visual feedback with image preview
- Clear prediction results (Normal vs Pneumonic)
- Modern and responsive UI design

## Technical Architecture

### CNN Model
- Built using TensorFlow/Keras
- Input size: 150x150 pixels
- Binary classification (Normal vs Pneumonic)
- Uses VGG16 preprocessing for image standardization

### Web Application
- Backend: Flask (Python)
- Frontend: HTML, CSS, JavaScript
- Bootstrap for responsive design
- AJAX for asynchronous predictions

## How to Run Locally

1. Clone the repository
```bash
git clone <repository-url>
cd pneumonia-detector
```

2. Create a virtual environment and activate it
```bash
python -m venv env
source env/bin/activate  
```

3. Install the required dependencies
```bash
pip install -r requirements.txt
```

4. Run the Flask application
```bash
python app.py
```

5. Open your web browser and navigate to `http://127.0.0.1:5000`

## Usage

1. Click on the "Upload X-Ray Images" button to select a chest X-ray image
2. The selected image will be displayed in the preview area
3. Click "Predict" to analyze the image
4. The system will display the result as either "NORMAL" or "PNEUMONIC"

## Model Architecture

The project implements a Convolutional Neural Network (CNN) with the following architecture and workflow:

### Input Layer
- Input shape: 150x150x3 (RGB images)
- Images are resized and normalized using VGG16 preprocessing
- Pixel values are scaled to the range [-1, 1]

### Feature Extraction Layers
1. **First Convolutional Block**
   - Conv2D layer with 32 filters, 3x3 kernel
   - ReLU activation
   - MaxPooling2D with 2x2 pool size
   - Dropout (0.25) for regularization

2. **Second Convolutional Block**
   - Conv2D layer with 64 filters, 3x3 kernel
   - ReLU activation
   - MaxPooling2D with 2x2 pool size
   - Dropout (0.25)

3. **Third Convolutional Block**
   - Conv2D layer with 128 filters, 3x3 kernel
   - ReLU activation
   - MaxPooling2D with 2x2 pool size
   - Dropout (0.25)

### Classification Layers
1. **Flatten Layer**
   - Converts 3D feature maps to 1D feature vector

2. **Dense Layers**
   - First Dense layer: 512 neurons with ReLU activation
   - Dropout (0.5) for preventing overfitting
   - Final Dense layer: 2 neurons with Softmax activation

### Model Training
- Loss function: Binary Cross-Entropy
- Optimizer: Adam with learning rate of 0.001
- Metrics: Accuracy
- Early stopping to prevent overfitting
- Data augmentation used during training:
  - Random rotation
  - Horizontal flipping
  - Zoom range variation
  - Width and height shifts

### Prediction Process
1. Image Preprocessing
   - Load and resize input image to 150x150
   - Apply VGG16 preprocessing
   - Normalize pixel values

2. Feature Extraction
   - Input image passes through convolutional layers
   - Features are extracted at different scales
   - Spatial information is preserved through max pooling

3. Classification
   - Extracted features are flattened
   - Dense layers process the features
   - Softmax activation provides probability distribution
   - Final output: NORMAL or PNEUMONIC prediction