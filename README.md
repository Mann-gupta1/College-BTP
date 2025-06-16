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

The project uses a Convolutional Neural Network (CNN) with the following workflow:
1. Image preprocessing and standardization
2. Feature extraction through convolutional layers
3. Classification into Normal/Pneumonic categories