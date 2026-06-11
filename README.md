# 🐾 Dogs vs Cats — CNN Image Classifier

A deep learning project that uses a **Convolutional Neural Network (CNN)** to classify images as either a **Cat** or a **Dog**. Built with **TensorFlow/Keras** and trained on the **Kaggle Dogs vs Cats Dataset**.

---

## 📁 Project Structure

```text
dogs-vs-cats-cnn/
│
├── dogs_vs_cats.ipynb       # Main Colab notebook
└── README.md                # Project documentation
```

---

## 📊 Dataset

**Source:** Kaggle — Dogs vs Cats Dataset

* Training Images: **20,000** (10,000 Cats + 10,000 Dogs)
* Validation Images: **5,000**
* Format: JPEG Images

### Dataset Structure

```text
/content/
├── train/
│   ├── cats/    → label 0
│   └── dogs/    → label 1
│
└── test/
    ├── cats/    → label 0
    └── dogs/    → label 1
```

---

## 🧠 CNN Model Architecture

```text
Input Image (256 × 256 × 3)
        ↓
Conv2D(32, 3×3, ReLU)
        ↓
BatchNormalization
        ↓
MaxPooling2D(2×2)
        ↓
Conv2D(64, 3×3, ReLU)
        ↓
BatchNormalization
        ↓
MaxPooling2D(2×2)
        ↓
Conv2D(128, 3×3, ReLU)
        ↓
BatchNormalization
        ↓
MaxPooling2D(2×2)
        ↓
Flatten
        ↓
Dense(128, ReLU)
        ↓
Dropout(0.1)
        ↓
Dense(64, ReLU)
        ↓
Dropout(0.1)
        ↓
Dense(1, Sigmoid)
        ↓
Output:
0 = Cat
1 = Dog
```

---

## 🔍 Layer Explanation

| Layer              | Purpose                                                               |
| ------------------ | --------------------------------------------------------------------- |
| Conv2D             | Extracts important image features such as edges, textures, and shapes |
| BatchNormalization | Stabilizes training and improves convergence speed                    |
| MaxPooling2D       | Reduces image dimensions while preserving important features          |
| Flatten            | Converts feature maps into a 1D vector                                |
| Dense              | Learns high-level patterns for classification                         |
| Dropout            | Reduces overfitting by randomly disabling neurons                     |
| Sigmoid            | Produces binary output between 0 and 1                                |

---

## ⚙️ Training Configuration

| Parameter        | Value               |
| ---------------- | ------------------- |
| Optimizer        | Adam                |
| Loss Function    | Binary Crossentropy |
| Metric           | Accuracy            |
| Batch Size       | 32                  |
| Epochs           | 10                  |
| Input Image Size | 256 × 256           |

---

## 📈 Model Performance

| Metric              | Result |
| ------------------- | ------ |
| Training Accuracy   | 90.26% |
| Validation Accuracy | 82.36% |

---

## 🔍 Sample Prediction

```text
Raw Prediction Value: 0.9341

Class Order:
['cats', 'dogs']

Prediction:
It's a DOG! 🐶

Confidence:
93.41%
```

---

## 🚀 How to Run

### 1. Open in Google Colab

Upload the notebook and connect to a GPU runtime.

### 2. Configure Kaggle Credentials

```python
import os

os.environ['KAGGLE_USERNAME'] = 'your_username'
os.environ['KAGGLE_KEY'] = 'your_api_key'
```

### 3. Download Dataset

```python
!pip install -q kaggle
!kaggle datasets download -d salader/dogsvscats
```

### 4. Extract Dataset

```python
import zipfile

zip_ref = zipfile.ZipFile('/content/dogsvscats.zip', 'r')
zip_ref.extractall('/content')
zip_ref.close()
```

### 5. Run All Cells

Train the CNN model and evaluate performance.

### 6. Test on Your Own Image

```python
image_path = "/content/your_image.jpg"
```

---

## 🛠️ Requirements

```text
tensorflow >= 2.x
opencv-python
numpy
matplotlib
kaggle
```

All required libraries are available by default in Google Colab.

---

## 👨‍💻 Author

**Wajahat Saif**
BS Computer Science
Iqra University Islamabad

---

## 📌 Project Highlights

* Binary Image Classification using CNN
* TensorFlow / Keras Implementation
* Batch Normalization
* Dropout Regularization
* Model Accuracy & Loss Visualization
* Real-Time Image Prediction
* Google Colab Compatible
* Kaggle Dataset Integration

```
```
