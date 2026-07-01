---
title: "Ensemble Learning for Recyclable Waste Classification"
collection: teaching
type: "Machine Learning / Computer Vision Project"
permalink: /teaching/2025-waste-classification
venue: "Machine Learning Research Project"
date: 2025-01-01
location: "Bangladesh"
---

Developed an automated recyclable waste classification system using transfer learning and ensemble learning to accurately classify recyclable waste into eight categories. The system is designed for real-time deployment on a Raspberry Pi to support smart waste management and sustainable recycling.

## Project Links

- [Project Repository](https://drive.google.com/file/d/1Zm19xsYHtqfpq2MA2XSY6QhgcujbgnIG/view?usp=sharing)

## Key Contributions

- Combined the TrashNet and Garbage Classification benchmark datasets to create a custom dataset with 8 waste categories.
- Applied data augmentation techniques to improve model generalization and address class imbalance.
- Developed three transfer learning models:
  - VGG16 + DenseNet121
  - VGG16 + EfficientNetB3
  - ResNet50 + EfficientNetB3
- Implemented an ensemble learning approach using majority voting for final classification.
- Designed a Raspberry Pi-based automated waste sorting system using a USB camera, ultrasonic sensor, conveyor belt, and servo motor.
- Achieved **96.87% classification accuracy** with the ensemble model.

## Technologies Used

- Python
- TensorFlow / Keras
- Convolutional Neural Networks (CNN)
- Transfer Learning
- Ensemble Learning
- OpenCV
- TensorFlow Lite
- Raspberry Pi
