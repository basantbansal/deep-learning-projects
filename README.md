# deep-learning-projects

# Deep Learning Projects

A collection of computer vision projects built from scratch using TensorFlow and Keras.

---

## 1. Digit Recognizer (MNIST)

**Goal:** Classify handwritten digits (0-9) from images

**Result:** 99.2% accuracy on Kaggle leaderboard (top 15%)

**What I built:**
- CNN from scratch with Conv2D, BatchNorm, Dropout layers
- Data augmentation pipeline using ImageDataGenerator
- Ensemble of 3 different CNN architectures
- Real world testing on handwritten digit photos

**Techniques used:**
- Convolutional Neural Networks (CNN)
- Batch Normalization
- Dropout regularization
- Data Augmentation
- ReduceLROnPlateau callback
- ModelCheckpoint callback

**Dataset:** MNIST - 42,000 training images, 28,000 test images

---

## 2. Facial Emotion Recognition (FER2013)

**Goal:** Classify 7 emotions from face images (angry, disgust, fear, happy, neutral, sad, surprise)

**Result:** 60% test accuracy (human level on FER2013 is 65%)

**What I built:**
- Deep CNN with 6 convolutional layers
- Real time face detection using OpenCV Haar Cascade
- Tested on real face photos achieving 98% confidence on clear expressions

**Techniques used:**
- Deep CNN Architecture (32→64→128→256 filters)
- Batch Normalization after every Conv layer
- Data Augmentation for face images
- OpenCV face detection
- Confusion Matrix and Classification Report analysis
- ModelCheckpoint to save best weights

**Dataset:** FER2013 - 35,000 grayscale face images, 7 emotion classes

**Key insight:** Identified domain shift problem — model trained on exaggerated FER2013 expressions performs differently on real world subtle expressions

---

## Skills Demonstrated

- TensorFlow / Keras
- CNN Architecture Design from scratch
- Data Augmentation strategies
- Transfer Learning concepts
- Model Evaluation (Confusion Matrix, F1 Score, Classification Report)
- OpenCV for real world image processing
- Kaggle competition workflow

---

## Tools Used

- Python
- TensorFlow / Keras
- OpenCV
- NumPy / Pandas
- Matplotlib / Seaborn
- Scikit-learn
- Kaggle (GPU training)
