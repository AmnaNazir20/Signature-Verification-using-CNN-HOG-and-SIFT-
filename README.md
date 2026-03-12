# Signature Verification using CNN, HOG, and SIFT

This project presents a comparative study of **deep learning and traditional feature extraction techniques** for signature verification.
The system evaluates three different approaches:

* Convolutional Neural Network (CNN)
* Histogram of Oriented Gradients with Support Vector Machine (HOG + SVM)
* Scale-Invariant Feature Transform with Support Vector Machine (SIFT + SVM)

The objective is to determine which method performs best for distinguishing **genuine and forged signatures**.

---

## Author

Amna Nazir
Department of Data Science
National University of Computer and Emerging Sciences (FAST)

---

## Project Overview

Signature verification is widely used in banking systems, legal documentation, and identity authentication.
This project compares **deep learning-based feature learning** with **traditional handcrafted feature extraction techniques**.

The study evaluates model performance using:

* Accuracy
* Precision
* Recall
* F1 Score

---

## Dataset

The experiments use a publicly available **Signature Verification Dataset** containing genuine and forged signatures from multiple users. 

Images are organized into user-specific folders for training and validation.

---

## Preprocessing

Before training, the following preprocessing steps were applied:

* Convert images to **grayscale**
* Resize images to **128 × 128 pixels**
* Normalize pixel values to **[0,1]**

These steps reduce computational complexity and ensure consistent input for models. 

---

## Models Implemented

### 1️⃣ Convolutional Neural Network (CNN)

The CNN model consists of:

* 3 Convolutional layers (32, 64, 128 filters)
* MaxPooling layers
* Flatten layer
* Dense layer (256 units)
* Dropout (0.5)
* Softmax output layer

Training configuration:

* Optimizer: Adam
* Loss Function: Categorical CrossEntropy
* Epochs: 15
* Batch Size: 32

---

### 2️⃣ HOG + SVM

Histogram of Oriented Gradients (HOG) extracts gradient-based features from signature images.

Parameters used:

* 9 gradient orientations
* Cell size: 8×8
* Block size: 2×2

These features are classified using a **Support Vector Machine (SVM)** classifier. 

---

### 3️⃣ SIFT + SVM

Scale-Invariant Feature Transform (SIFT) detects keypoints and extracts **128-dimensional descriptors** representing local image features.

The descriptors are flattened and used as input to an **SVM classifier**.

However, SIFT performs poorly in signature verification due to inconsistent keypoint detection across signatures. 

---

## Results

| Model      | Accuracy |
| ---------- | -------- |
| CNN        | 92.7%    |
| HOG + SVM  | 93.8%    |
| SIFT + SVM | 33.7%    |

Observations:

* **HOG + SVM achieved the highest accuracy**
* **CNN provided stable and consistent predictions**
* **SIFT performed poorly due to sparse keypoints**

---

## Technologies Used

* Python
* TensorFlow / Keras
* OpenCV
* Scikit-learn
* NumPy
* Matplotlib

---

## Project Structure

```
Signature-Verification-CNN
│
├── Q1_Notebook.ipynb
├── q1 Report.pdf
└── README.md
```

---

## How to Run

Clone the repository:

```
git clone https://github.com/username/signature-verification-cnn.git
```

Install required libraries:

```
pip install tensorflow opencv-python scikit-learn numpy matplotlib
```

Open the notebook and run all cells.

---

## Conclusion

Both **CNN and HOG+SVM models achieved strong performance** for signature verification tasks.
CNN automatically learns hierarchical features, while HOG provides robust handcrafted gradient representations.

Future work may explore **hybrid approaches combining CNN with handcrafted features or transfer learning models**.

---

## References

See the full report for detailed references and methodology.
