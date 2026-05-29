# 🌿 An AI Based Agronomist (Final Year Project)

This project was developed as part of our Bachelor of Electrical Engineering final year work at Sukkur IBA University. The main idea is to help people identify plants using a simple mobile application powered by a deep learning model trained on a locally collected dataset.

The system is not just a model or a notebook. It is a complete pipeline that includes:

* A manually collected image dataset of local plants
* Two CNN-based training notebooks
* A trained AI model for plant identification
* A Flask backend server
* A Flutter mobile application
* Additional modules for disease detection, yield prediction, consultation, and shopping links

The goal was to build something practical for local users who often struggle with identifying plants found in Pakistan.

---

# 🌱 Project Overview

Most existing plant recognition systems are trained on global datasets and often fail to correctly identify local plant species. To solve this, we built our own dataset from scratch by collecting images from Sukkur IBA University campus.

We then trained deep learning models using CNN (Convolutional Neural Networks) and deployed them in a mobile application so users can take or upload a picture and get instant plant identification along with useful information.

---

# 📊 Dataset

We created a custom dataset instead of using public datasets.

### Key points:

* 20 plant classes in total
* Around 200 images per class
* Images captured using different mobile phones (low and mid-range devices)
* Captured under different conditions:

  * Morning, afternoon, evening
  * With and without flash
  * Different angles and distances

### Preprocessing:

* Manual image cropping was performed
* Background noise was removed
* Images were cleaned and standardized before training

Along with images, we also manually collected plant information such as:

* Name
* Season
* Region
* Growth conditions
* Water and sunlight requirements
* Short description

---

# 🧠 Notebooks Description

This repository contains two training notebooks.

## 📒 Notebook 1 — 20 Class Model

This model was trained on the full dataset (20 plant classes).

### Architecture:

* 2 Convolutional layers
* Max pooling after each conv layer
* Dropout (0.6) to reduce overfitting
* Dense layers (512 + 20 output classes)
* Adam optimizer (learning rate: 0.00001)
* 20 epochs

### Result:

* Test accuracy: ~91.1%
* Validation accuracy: ~89%
* Test loss: ~19.44

This model gave stable results but had slightly lower accuracy due to higher class complexity.

---

## 📒 Notebook 2 — 10 Class Model

This model was trained on a reduced dataset (10 selected classes).

### Architecture:

* 3 Convolutional layers
* Max pooling after each conv layer
* Dropout (0.4)
* Dense layers (512 + 10 output classes)
* Adam optimizer (learning rate: 0.00001)
* 30 epochs

### Result:

* Test accuracy: ~97.6%
* Validation accuracy: ~97.6%
* Test loss: ~3.8

This model performed significantly better due to fewer classes and improved feature separation.

---

# ⚖️ Comparison of Both Models

| Feature            | 20-Class Model                 | 10-Class Model           |
| ------------------ | ------------------------------ | ------------------------ |
| Number of Classes  | 20                             | 10                       |
| Complexity         | High                           | Medium                   |
| Convolution Layers | 2                              | 3                        |
| Dropout            | 0.6                            | 0.4                      |
| Epochs             | 20                             | 30                       |
| Test Accuracy      | ~91%                           | ~97.6%                   |
| Loss               | High (~19.44)                  | Low (~3.8)               |
| Performance        | Good but harder classification | More stable and accurate |

### Key takeaway:

Reducing the number of classes significantly improved accuracy and reduced confusion between similar plant types.

---

# 📱 System Architecture (Big Picture)

This project is not just about training a model.

### Complete system includes:

## 1. Data Collection

Manually collected plant images and information from real environment.

## 2. AI Model (Python + TensorFlow)

CNN models trained in Kaggle environment using TensorFlow/Keras.

## 3. Backend Server (Flask)

* Receives image from app
* Runs model prediction
* Returns result as text response

## 4. Mobile Application (Flutter)

Features:

* Plant identification
* Disease detection
* Yield prediction
* Shopping links (plants & pesticides)
* Consultation section

---

# 🔄 How It Works

1. User opens mobile app
2. Takes or uploads plant image
3. Image is sent to Flask server
4. CNN model predicts plant class
5. Result is returned to app
6. App displays plant name + details (translated if needed)

---

# 📈 Results Summary

* The system achieved good accuracy for real-world images captured from mobile devices
* Model worked better on controlled and cropped dataset
* Best performance achieved: ~97% accuracy (10-class model)
* End-to-end pipeline successfully tested with mobile integration

---

# 💡 Key Learnings

* Real-world dataset creation is harder than model building
* Image quality and preprocessing have major impact on accuracy
* Reducing class complexity improves performance significantly
* Mobile deployment requires careful backend optimization
* CNN models are highly sensitive to data distribution

---

# 🧩 Final Note

This project was built step by step from scratch — starting from collecting images in real environments, cleaning and labeling data manually, training CNN models, and finally deploying everything into a working mobile application.

It represents a complete AI pipeline from data → model → deployment → user application.


