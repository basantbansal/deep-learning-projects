# Deep Learning Projects

<p align="center">
  <a href="https://www.tensorflow.org/">
    <img src="https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white" alt="TensorFlow" />
  </a>
  <a href="https://keras.io/">
    <img src="https://img.shields.io/badge/Keras-D00000?style=for-the-badge&logo=keras&logoColor=white" alt="Keras" />
  </a>
  <a href="https://opencv.org/">
    <img src="https://img.shields.io/badge/OpenCV-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white" alt="OpenCV" />
  </a>
  <a href="https://jupyter.org/">
    <img src="https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white" alt="Jupyter" />
  </a>
</p>

A collection of deep learning computer vision projects built from scratch using TensorFlow and Keras. This repository focuses on practical model design, training strategies, and real-world testing on image data.

## Table of Contents

- [Overview](#overview)
- [Repository Structure](#repository-structure)
- [Project 1: Digit Recognizer](#project-1-digit-recognizer-mnist)
- [Project 2: Facial Emotion Recognition](#project-2-facial-emotion-recognition-fer2013)
- [Tech Stack](#tech-stack)
- [Key Learnings](#key-learnings)
- [Quick Start](#quick-start)
- [Results Summary](#results-summary)

## Overview

This repository contains hands-on projects that explore how CNNs learn visual patterns across different tasks:

- Handwritten digit recognition using MNIST
- Facial emotion classification using FER2013

Each project is implemented in a Jupyter Notebook and emphasizes:

- model architecture design from scratch
- data preprocessing and augmentation
- training robustness with normalization and regularization
- evaluation using meaningful metrics
- testing on real-world images beyond the benchmark dataset

## Repository Structure

```text
deep-learning-projects/
├── README.md
├── digit-recogniser_Basant.ipynb
├── fer2013-basant.ipynb
└── ...
```

## Project 1: Digit Recognizer (MNIST)

**Kaggle Score:** 0.99582 (99.58% accuracy)

### Goal
Classify handwritten digits (0–9) from 28×28 grayscale images.

### Approach
- Built CNNs from scratch without using pretrained models
- Trained an ensemble of 3 CNN architectures and averaged their predictions
- Used GPU-based training for efficient experimentation
- Applied augmentation and regularization to improve generalization

### Network Architecture

```text
Conv2D(32) → BatchNorm → Conv2D(32) → BatchNorm → MaxPool → Dropout(0.25)
Conv2D(64) → BatchNorm → Conv2D(64) → BatchNorm → MaxPool → Dropout(0.25)
Conv2D(128) → BatchNorm → MaxPool → Dropout(0.25)
Flatten → Dense(512) → Dropout(0.5) → Dense(10, softmax)
```

### Techniques Used
- Batch normalization after convolutional layers
- Data augmentation (rotation, zoom, shifts)
- Ensemble learning with different seeds
- ReduceLROnPlateau callback for better convergence
- Real-world testing on handwritten images captured externally

### Key Results
- Validation accuracy: ~99.6%
- Kaggle leaderboard score: 0.99582
- Successfully tested on real handwritten digit photos

### Dataset
- MNIST
- 42,000 training images
- 28,000 test images

---

## Project 2: Facial Emotion Recognition (FER2013)

**Test Accuracy:** ~60%  
*(Human-level performance on FER2013 is about 65%)*

### Goal
Classify 7 emotional states from face images:

- angry
- disgust
- fear
- happy
- neutral
- sad
- surprise

### Approach
- Deep CNN trained from scratch
- Real-time face detection using OpenCV Haar Cascade
- Model evaluation with classification metrics and confusion matrix
- Tested on real face photos in addition to benchmark data

### Network Architecture

```text
Conv2D(32) → BatchNorm → Conv2D(32) → BatchNorm → MaxPool → Dropout(0.25)
Conv2D(64) → BatchNorm → Conv2D(64) → BatchNorm → MaxPool → Dropout(0.25)
Conv2D(128) → BatchNorm → Conv2D(128) → BatchNorm → MaxPool → Dropout(0.25)
Conv2D(256) → BatchNorm → Conv2D(256) → BatchNorm → MaxPool → Dropout(0.25)
Flatten → Dense(256) → BatchNorm → Dropout(0.5) → Dense(7, softmax)
Total params: ~1.4M
```

### Techniques Used
- Deep CNN architecture with filter progression 32 → 64 → 128 → 256
- Batch normalization after every convolutional layer
- ImageDataGenerator for dataset augmentation and loading
- ModelCheckpoint to preserve best weights
- OpenCV face detection for real-world inference
- Confusion matrix and classification report analysis

### Key Results
- Test accuracy: ~60%
- High confidence on clear happy-face images
- Highlighted the domain shift problem between benchmark datasets and real-world photos
- Achieved near-human-level performance on FER2013

### Dataset
- FER2013
- ~35,000 grayscale face images
- 7 emotion classes

---

## Tech Stack

| Tool | Purpose |
|------|---------|
| TensorFlow / Keras | Model design and training |
| OpenCV | Face detection and image processing |
| NumPy / Pandas | Data manipulation and preprocessing |
| Matplotlib / Seaborn | Visualization and analysis |
| Scikit-learn | Metrics, evaluation, and analysis |
| Jupyter Notebook | Experimentation and reporting |
| Kaggle | GPU training and competition workflow |

---

## Key Learnings

- CNN architecture design from scratch
- Why batch normalization helps stabilize training
- How data augmentation affects model generalization
- Ensemble methods for stronger prediction performance
- Domain shift and the challenge of real-world deployment
- Class imbalance and its effect on model behavior
- Transfer learning ideas and experimentation with stronger feature extractors

---

## Quick Start

### 1. Clone the repository

```bash
git clone https://github.com/basantbansal/deep-learning-projects.git
cd deep-learning-projects
```

### 2. Create a virtual environment

```bash
python -m venv venv
source venv/bin/activate   # Linux/macOS
# venv\Scripts\activate    # Windows
```

### 3. Install dependencies

```bash
pip install tensorflow keras opencv-python numpy pandas matplotlib seaborn scikit-learn jupyterlab
```

### 4. Launch Jupyter

```bash
jupyter lab
```

Open the notebook you want to run and follow the steps inside.

> Note: GPU training is recommended for faster experiments, especially for CNN model training.

---

## Results Summary

| Project | Dataset | Accuracy | Platform |
|---------|---------|----------|----------|
| Digit Recognizer | MNIST | 99.58% | Kaggle Leaderboard |
| Emotion Recognition | FER2013 | ~60% | Test Set |

---

This repository reflects a practical learning journey in deep learning, computer vision, and model experimentation. It is intended to showcase how strong CNN-based solutions can be built from the ground up using standard tools and real datasets.

Built while learning deep learning from scratch — Feb 2026

































































































































































































































































































































