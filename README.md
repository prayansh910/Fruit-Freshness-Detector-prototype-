# 🍎 Fruit Freshness Detector (Prototype)

## 📌 Overview

Fruit Freshness Detector is a prototype computer vision project that analyzes fruit images and estimates their freshness using image variance analysis.

The system first classifies an uploaded image into a food category using a pre-trained Zero-Shot Image Classification model from Hugging Face. If the detected category is a fruit, the image is further analyzed to estimate freshness based on variance extracted from pixel values.

This project was developed as a learning-focused prototype to explore image classification, feature extraction, and rule-based decision-making in computer vision.

---

## 🎯 Project Objective

The goal of this project is to:

* Detect whether an uploaded image belongs to a fruit category.
* Extract visual features from the image.
* Estimate fruit freshness using image variance.
* Generate a simple freshness report.

This project is intended as a prototype and proof-of-concept rather than a production-ready freshness detection system.

---

## ⚙️ Technologies Used

* Python
* Google Colab
* Hugging Face Transformers
* Zero-Shot Image Classification
* NumPy
* Pillow (PIL)

---

## 🔄 Project Workflow

Image Upload

⬇

Food Category Classification

⬇

Fruit Verification

⬇

Image Variance Calculation

⬇

Freshness Estimation

⬇

Fruit Freshness Report

---

## 🧠 Methodology

### 1. Category Detection

The uploaded image is passed through a Zero-Shot Image Classification model with the following candidate labels:

* Fruit
* Vegetable
* Baked
* Meat
* Dairy

Only fruit images proceed to freshness analysis.

---

### 2. Feature Extraction

The image is converted into a NumPy array and normalized.

Variance is then calculated from the pixel values:

* Low variance generally indicates smoother and more uniform fruit surfaces.
* High variance may indicate discoloration, dark spots, or irregular texture.

---

### 3. Freshness Classification

The freshness decision is made using variance thresholds:

| Variance Range    | Freshness Status |
| ----------------- | ---------------- |
| Less than 0.04    | Fresh            |
| 0.04 – 0.08       | Okay             |
| Greater than 0.08 | Avoid            |

---

## 📊 Sample Test Results

| Fruit         | Variance | Predicted Freshness |
| ------------- | -------- | ------------------- |
| Fresh Apple   | 0.033    | Fresh               |
| Rotten Apple  | 0.102    | Avoid               |
| Fresh Banana  | 0.029    | Fresh               |
| Rotten Banana | 0.080    | Avoid               |
| Fresh Orange  | 0.069    | Okay                |
| Rotten Orange | 0.102    | Avoid               |
| Fresh Grapes  | 0.070    | Okay                |
| Fresh Pear    | 0.053    | Okay                |
| Rotten Pear   | 0.072    | Okay                |

---

## 📈 Observations

Testing revealed that variance can successfully separate some fresh and rotten fruits, particularly apples and bananas.

However, fruits with naturally textured surfaces such as grapes, oranges, and pears produce higher variance values even when fresh.

This demonstrates both the usefulness and limitations of variance-based freshness estimation.

---

## ⚠️ Limitations

* Prototype-level implementation.
* Works only for fruit images.
* Freshness estimation relies on variance alone.
* Performance varies across different fruit types.
* Lighting conditions and image quality can affect results.
* Not suitable for commercial or real-world deployment.

---

## 🚀 Future Improvements

Potential future enhancements include:

* Training a CNN-based Fresh vs Rotten classifier.
* Using a dedicated fruit freshness dataset.
* Supporting vegetables and other food categories.
* Building a web application interface.
* Deploying the model using Streamlit or Flask.
* Combining multiple visual features instead of relying solely on variance.

---

## 📚 Learning Outcomes

Through this project, the following concepts were explored:

* Computer Vision Fundamentals
* Image Classification
* Feature Extraction
* NumPy Image Processing
* Hugging Face Transformers
* Rule-Based Decision Systems
* Model Evaluation and Testing

---

## 👨‍💻 Author

Prayansh Gupta

B.Tech – Artificial Intelligence & Data Science

Prototype project developed for learning and experimentation in Computer Vision and AI.
