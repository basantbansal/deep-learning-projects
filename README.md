# Deep Learning Projects

A collection of computer vision projects built from scratch using TensorFlow and Keras.

---

## 1. Digit Recognizer (MNIST)

**Kaggle Score: 0.99582 (99.58% accuracy)**

**Goal:** Classify handwritten digits (0-9) from 28x28 grayscale images

**Approach:**
- Built CNN from scratch — no pretrained models
- Ensemble of 3 different CNN architectures averaged together
- Each model trained for 50 epochs on GPU

**Architecture:**
```
Conv2D(32) → BN → Conv2D(32) → BN → MaxPool → Dropout(0.25)
Conv2D(64) → BN → Conv2D(64) → BN → MaxPool → Dropout(0.25)  
Conv2D(128) → BN → MaxPool → Dropout(0.25)
Flatten → Dense(512) → Dropout(0.5) → Dense(10, softmax)
```

**Techniques used:**
- Batch Normalization after every Conv layer
- Data Augmentation (rotation, zoom, shift)
- Ensemble of 3 models with different random seeds
- ReduceLROnPlateau callback
- Real world testing on handwritten digit photos

**Key results:**
- Validation accuracy: 99.6%
- Kaggle leaderboard score: 0.99582
- Successfully tested on real handwritten digit photos

**Dataset:** MNIST — 42,000 training images, 28,000 test images

---

## 2. Facial Emotion Recognition (FER2013)

**Test Accuracy: ~60% (Human level on FER2013 is 65%)**

**Goal:** Classify 7 emotions from face images
(angry, disgust, fear, happy, neutral, sad, surprise)

**Approach:**
- Deep CNN with 6 convolutional layers trained from scratch
- Real time face detection using OpenCV Haar Cascade
- Tested on real face photos

**Architecture:**
```
Conv2D(32) → BN → Conv2D(32) → BN → MaxPool → Dropout(0.25)
Conv2D(64) → BN → Conv2D(64) → BN → MaxPool → Dropout(0.25)
Conv2D(128) → BN → Conv2D(128) → BN → MaxPool → Dropout(0.25)
Conv2D(256) → BN → Conv2D(256) → BN → MaxPool → Dropout(0.25)
Flatten → Dense(256) → BN → Dropout(0.5) → Dense(7, softmax)
Total params: 1.4M
```

**Techniques used:**
- Deep CNN Architecture (32 → 64 → 128 → 256 filters)
- Batch Normalization after every Conv layer
- ImageDataGenerator with flow_from_directory
- ModelCheckpoint to save best weights
- OpenCV face detection for real world testing
- Confusion Matrix and Classification Report analysis

**Key results:**
- Test accuracy: ~60%
- 98% confidence on clear happy face photo
- Identified domain shift problem between dataset and real world photos
- Near human level performance (humans score 65% on FER2013)

**Dataset:** FER2013 — 35,000 grayscale face images, 7 emotion classes

---

## Key Learnings

- CNN architecture design from scratch
- Why BatchNormalization stabilizes training
- Data augmentation strategies for different problem types
- Ensemble methods for improving accuracy
- Domain shift — why models behave differently on real world data
- Class imbalance impact on model performance
- Transfer learning concepts (InceptionV3 experimentation)

---

## Tools and Libraries

| Tool | Purpose |
|------|---------|
| TensorFlow / Keras | Model building and training |
| OpenCV | Real world image processing and face detection |
| NumPy / Pandas | Data manipulation |
| Matplotlib / Seaborn | Visualization |
| Scikit-learn | Evaluation metrics |
| Kaggle | GPU training and competition submission |

---

## Results Summary

| Project | Dataset | Accuracy | Platform |
|---------|---------|----------|----------|
| Digit Recognizer | MNIST | 99.58% | Kaggle Leaderboard |
| Emotion Recognition | FER2013 | ~60% | Test Set |

---

*Built while learning deep learning from scratch — Feb 2026*
