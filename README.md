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
- Dataset: CIFAR-10 (50000 train images, 10000 test images) <br>

<img src="https://user-images.githubusercontent.com/99384454/188257303-e909c7c8-f48b-4138-b775-3c1ad74131bb.png" width="600>

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
The model is trained by finetuning on Resnet-50 pretrained model after changing the top layer to `Dense(10, activation='softmax')` to solve the 10-label classification problem. The image is resized to 224 x 224 to fit Resnet input dimension.


### 2. Train
![image](https://user-images.githubusercontent.com/99384454/188257083-3a331ebb-3044-44bf-8811-6fcbd439dbf8.png) <br>
Highest Validation Accuracy achieved after **10 epochs**.

## Result
Accuracy using Resnet-50 Transfer Learning on Cifar-10 dataset is **87.0%**.

![image](https://user-images.githubusercontent.com/99384454/188257218-929fe6e3-314a-4fa9-9ac5-835b4a702cde.png)



