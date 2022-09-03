# Computer Vision using CNN and Transfer Learning on CIFAR-10 dataset

## TABLE OF CONTENTS
  - [Problem Statement](#problem-statement)
  - [Pre-Processing](#pre-processing)
  - [Training](#training)
    - [1. Model Architecture](#1-model-architecture)
    - [2. Train](#2-train)
  - [Result](#result)

## Problem Statement
- Multi-class Classification Problem
- Image Classification
- Dataset: CIFAR-10 (50000 train images, 10000 test images)


## Pre-Processing
### Normalize Data
```
train_images = train_images / 255.0
test_images = test_images / 255.0
```

### Resize Images
```
# resize training images
minSize = 56

train_images_resized = np.zeros((50000, minSize, minSize, 3,))
for a in range(len(train_images)):
    train_images_resized[a] = cv2.resize(train_images[a], dsize=(minSize, minSize), interpolation=cv2.INTER_CUBIC)

test_images_resized = np.zeros((10000, minSize, minSize, 3,))
for a in range(len(test_images)):
    test_images_resized[a] = cv2.resize(test_images[a], dsize=(minSize, minSize), interpolation=cv2.INTER_CUBIC)
```

## Training
### 1. Model Architecture

### 2. Train

## Result


