# ♻️ Ensemble Learning for Recyclable Waste Classification

A deep learning-based recyclable waste classification system that combines **transfer learning** and **ensemble learning** to accurately classify waste into recyclable categories. The project is designed for deployment on a **Raspberry Pi** for real-time automated waste sorting.

## 📌 Overview

This project uses multiple pre-trained Convolutional Neural Network (CNN) models and an ensemble learning strategy to classify waste images into eight recyclable categories. The system is intended to support smart waste management by reducing manual sorting and improving recycling efficiency.

## 🚀 Features

* Image classification using Transfer Learning
* Ensemble learning with Majority Voting
* Eight recyclable waste categories
* Data augmentation for class balancing
* Raspberry Pi deployment for real-time classification
* TensorFlow Lite optimization for edge devices

## 🗂️ Dataset

A custom dataset was created by combining two public benchmark datasets:

* TrashNet
* Garbage Classification Dataset

**Classes**

* Cardboard
* Clothes
* Glass
* Metal
* Paper
* Plastic
* Shoes
* Trash

**Dataset Size**

* 4,614 images
* 80% Training
* 10% Validation
* 10% Testing

## 🧠 Models Used

Three transfer learning models were trained:

* VGG16 + DenseNet121
* VGG16 + EfficientNetB3
* ResNet50 + EfficientNetB3

The final prediction is obtained using **Majority Voting Ensemble Learning**.

## 🛠️ Technologies

* Python
* TensorFlow / Keras
* CNN
* Transfer Learning
* Ensemble Learning
* OpenCV
* TensorFlow Lite
* Raspberry Pi

## 📊 Results

| Model                     | Accuracy   |
| ------------------------- | ---------- |
| VGG16 + DenseNet121       | 90%        |
| VGG16 + EfficientNetB3    | 96%        |
| ResNet50 + EfficientNetB3 | 95%        |
| **Ensemble Model**        | **96.87%** |

## 🔧 Hardware Implementation

The system is designed for real-world deployment using:

* Raspberry Pi
* USB Camera
* Ultrasonic Sensor
* Servo Motor
* Conveyor Belt
* LCD Display

The camera captures waste images, the trained model classifies them, and recyclable items are automatically sorted into the correct bin.

## 📈 Future Improvements

* Expand the dataset with additional waste categories.
* Improve model performance using newer architectures.
* Deploy the system on edge devices for large-scale smart waste management.

## 📄 Research Paper

This work was developed as a machine learning research project on recyclable waste classification using transfer learning and ensemble learning.

## 🔗 Project Link

**Google Drive:**
https://drive.google.com/drive/u/0/folders/1NPOMUhHuvtaHSRPBTzkC8qb9cXn_Z_OJ

## 👩‍💻 Author

**Nafisa Islam**
MSc Artificial Intelligence
University of Hull
