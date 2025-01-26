# Face Recognition using ML Classifier

This project implements a simple face recognition system using OpenCV and machine learning techniques. It uses the **Local Binary Pattern Histogram (LBPH)** algorithm for face recognition and leverages OpenCV's Haar Cascade Classifier for face detection.

## Overview

The goal of this project is to capture images of faces using a webcam, store them in a dataset, and then use machine learning techniques to train a classifier for recognizing faces. The model can then be used to identify faces from live video streams.

## Project Structure

- **create_data.py**: This script captures images of faces using the webcam and stores them in a dataset directory. It uses OpenCV's Haar Cascade Classifier to detect faces in real-time.
- **faceRecognition.py**: This script trains a face recognition model using images from the dataset and uses the model to recognize faces in real-time video feeds.
- **haarcascade_frontalface_default.xml**: The Haar Cascade Classifier used for face detection. It comes with OpenCV.

## Requirements

To run this project, you need the following libraries installed:

- `opencv-python`
- `numpy`
- `os`
  
You can install them using the following command:

```bash
pip install opencv-python numpy
```

## Dataset

The dataset is created dynamically by capturing face images with the `create_data.py` script. These images are stored in the `Dataset` folder, where each person's face images are stored in a subfolder named after the person.

## Running the Project

### Step 1: Collect Data
Run the `create_data.py` script to capture images of a person. This will save the images in a specific folder for later training.

```bash
python create_data.py
```

- The script will create a folder named after the person (in this case, the folder is `steve`).
- It will capture 30 images of the person, store them, and then display them.

### Step 2: Train the Model
Run the `faceRecognition.py` script to train the face recognition model using the images collected in the previous step.

```bash
python faceRecognition.py
```

- The script will train a face recognition model and start recognizing faces in a webcam feed.
- If the recognized face matches the one trained, it will display the name and the confidence score.
- If the face is not recognized, it will display "Unknown."

### Step 3: Face Recognition
Once the model is trained, the system will start detecting faces from the webcam feed and match them with the trained faces. It will display the name and the confidence score if the face is recognized.

- Press **Esc** to exit the webcam feed.

## How It Works

1. **Face Detection**: The script uses OpenCV’s Haar Cascade Classifier to detect faces in the video stream from the webcam.
2. **Face Recognition**: After detecting a face, it is resized and converted to grayscale. The model predicts the face identity using the **LBPH Face Recognizer**.
3. **Prediction**: If the confidence of the prediction is below a threshold (800), the face is recognized, and the name is displayed. If not, it is marked as "Unknown."

## Example

- After running the training script, the system will be able to recognize faces such as "Steve" from the webcam feed.
- If an unknown person appears, the system will display "Unknown" and capture an image.



