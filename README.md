# Image Classification using TensorFlow

## Overview

This project implements an Image Classification model using TensorFlow and Keras. The workflow includes data validation, preprocessing, dataset loading, visualization, model training, and evaluation.

The model is designed to classify images into two categories using a Convolutional Neural Network (CNN).

---

## Features

* Image validation and cleaning
* Automatic dataset loading from directory structure
* Data visualization
* TensorFlow/Keras based image classification
* GPU-compatible training
* Easy-to-extend architecture

---

## Project Structure

```
Image_Classification/
│
├── data/
│   ├── class_1/
│   └── class_2/
│
├── model/
├── notebooks/
├── README.md
└── requirements.txt
```

---

## Dataset

The dataset should be organized as follows:

```
data/
├── class_1/
│   ├── image1.jpg
│   ├── image2.jpg
│   └── ...
│
└── class_2/
    ├── image1.jpg
    ├── image2.jpg
    └── ...
```

TensorFlow automatically assigns labels based on folder names.

---

## Installation

### Clone Repository

```bash
git clone https://github.com/nithinganesh1/Image_Classification.git
cd Image_Classification
```

### Install Dependencies

```bash
pip install tensorflow numpy matplotlib opencv-python
```

---

## Required Libraries

```python
import tensorflow as tf
import numpy as np
import matplotlib.pyplot as plt
import cv2
import os
import imghdr
```

---

## Data Cleaning

The project validates image formats before training.

Supported formats:

* JPEG
* JPG
* PNG
* BMP

Invalid image files are automatically removed.

```python
image_exts = ['jpeg', 'jpg', 'bmp', 'png']
```

---

## Loading Dataset

```python
data = tf.keras.utils.image_dataset_from_directory('data')
```

Example output:

```
Found 297 files belonging to 2 classes.
```

---

## Visualizing Samples

Display sample images from the dataset:

```python
data_iterator = data.as_numpy_iterator()
batch = data_iterator.next()
```

```python
fig, ax = plt.subplots(ncols=5, figsize=(20,20))
for idx, img in enumerate(batch[0][:5]):
    ax[idx].imshow(img.astype(int))
    ax[idx].title.set_text(batch[1][idx])
```

---

## Model Training

The dataset is used to train a CNN-based image classifier using TensorFlow/Keras.

Typical workflow:

1. Load dataset
2. Normalize images
3. Build CNN model
4. Train model
5. Evaluate performance
6. Save trained model

---

## Running the Project

Launch Jupyter Notebook or Google Colab and execute all cells:

```bash
jupyter notebook
```

or

```bash
python train.py
```

(if converted into a Python script)

---

## Technologies Used

* TensorFlow
* Keras
* NumPy
* OpenCV
* Matplotlib
* Python

---

## Results

The model learns image features from the training dataset and predicts the corresponding class label for unseen images.

Performance depends on:

* Dataset size
* Image quality
* Network architecture
* Training epochs

---

## Future Improvements

* Data augmentation
* Transfer learning (MobileNet, ResNet, EfficientNet)
* Hyperparameter tuning
* Multi-class classification support
* Model deployment using Flask or FastAPI

---

## Author

Developed as a TensorFlow Image Classification project for learning and experimentation.

## License

This project is available under the MIT License.
